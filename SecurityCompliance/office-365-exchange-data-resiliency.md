---
title: Office 365 Exchange データの復元
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Exchange Online および Office 365 内のデータの復元のさまざまな側面について説明します。
ms.openlocfilehash: 9e61efaf95d466fcb268e12317c7feab0701c062
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262759"
---
# <a name="exchange-online-data-resiliency-in-office-365"></a>Office 365 の Exchange Online データの復元

## <a name="introduction"></a>はじめに
Exchange データベースに影響を与える可能性がある破損には、次の2種類があります。物理的な破損は、通常、ハードウェア (特にストレージハードウェア) の問題、およびその他の要因によって発生する論理的な破損に起因します。 通常、Exchange データベース内で発生する可能性がある論理的な破損には、次の2種類があります。 
- **データベースの論理破損**-データベースページのチェックサムは一致しますが、ページ上のデータが論理的に間違っています。 これは、データベースエンジン (拡張記憶エンジン (ESE)) がデータベースページを作成しようとしたときに、オペレーティングシステムが成功メッセージを返した場合、データがディスクに書き込まれていないか、または正しくない場所に書き込まれている場合に発生する可能性があります。 これは、*ロスト フラッシュ*と呼ばれます。 ESE には、データベースやその他のデータ損失シナリオの物理的な破損を防止するために設計されたさまざまな機能と安全対策が用意されています。 失われたデータを失わないようにするため、ESE にはデータベース内の失われたフラッシュ検出メカニズムと機能 (単一ページ復元) が含まれています。 
- **ストレージの論理破損**-ユーザーが期待できない方法でデータが追加、削除、または操作されます。 これらの場合は通常、サード パーティ製のアプリケーションによって引き起こされます。 これは通常、ユーザーの観点から見た意味での破損にすぎません。 Exchange ストアは、論理的破損を引き起こすトランザクションを一連の有効な MAPI 操作として見なします。 Exchange Online の[インプレース保持](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)機能により、ストアの論理的破損を防止できます (ユーザーまたはアプリケーションによってコンテンツが完全に削除されることはないため)。 

Exchange Online は、ログ検査およびログ再生の両方で、レプリケートされたログファイルに対して複数の整合性チェックを実行します。 これらの整合性チェックによって、システムによって物理的破損がレプリケートされるのを防ぐことができます。 たとえば、ログ検査時には、ログファイルを検証し、ログファイルに記録されたチェックサムがメモリに生成されたチェックサムと一致することを確認する物理的な整合性チェックがあります。 さらに、ログヘッダーに記録されたログファイルの署名がログファイルの内容と一致することを確認するために、ログファイルヘッダーが検査されます。 ログ再生中に、ログファイルはさらに精査されます。 たとえば、データベースヘッダーには、ログファイルの署名と比較して、一致していることを確認するためのログ署名も含まれています。 

exchange Online のメールボックスデータの破損からの保護は、exchange ネイティブデータ保護を使用することによって実現され、複数のサーバーと複数のデータセンター間でアプリケーションレベルのレプリケーションを活用する復元戦略と、他の破損またはその他の理由によりデータが失われないように保護するための機能。 これらの機能には、次のような Microsoft または Exchange Online アプリケーション自体によって管理されるネイティブ機能が含まれます。

- [データ可用性グループ](https://docs.microsoft.com/exchange/back-up-email)
- シングルビット修正 
- オンラインデータベーススキャン 
- 失われたフラッシュの検出 
- 単一ページの復元 
- メールボックスレプリケーションサービス 
- ログファイルのチェック 
- 弾性ファイルシステムへの展開 

上記のネイティブ機能の詳細については、上記のハイパーリンクをクリックしてください。詳細については、以下を参照してください。また、ハイパーリンクのないアイテムについても説明します。 これらのネイティブ機能に加えて、Exchange Online には、お客様が管理できるデータ復元機能もあります。次のようなものがあります。 
- [単一アイテムの回復 (既定では有効)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages) 
- [インプレース保持と訴訟ホールド](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds) 
- [削除済みアイテムの保存期間と回復可能な削除によるメールボックス (既定で有効)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes) 

## <a name="database-availability-groups"></a>データベース可用性グループ 
Office 365 のすべてのメールボックスデータベースは、[データベース可用性グループ (DAG)](https://docs.microsoft.com/exchange/back-up-email)でホストされ、同じ地域内の地理的に離れた複数のデータセンターにレプリケートされます。 最も一般的な構成は、4つのデータセンター内の4つのデータベースコピーです。ただし、地域によっては、データセンターの数が少ない (インドの3つのデータセンターにデータベースがレプリケートされ、オーストラリアと日本では2つのデータセンターにレプリケートされる) 場合があります。 ただし、すべてのメールボックスデータベースには、複数のデータセンターに分散された4つのコピーがあるため、メールボックスのデータがソフトウェア、ハードウェア、およびデータセンターの障害から保護されています。 

これらの4つのコピーのうち3つは高可用性として構成されています。 4番目のコピーは、[時間差データベースコピー](https://docs.microsoft.com/Exchange/high-availability/manage-ha/activate-lagged-db-copies)として構成されます。 時間差データベースコピーは、個々のメールボックスの回復またはメールボックスのアイテムの回復を目的としたものではありません。 この目的は、システム全体に重大な致命的な破損が発生した場合に備えて回復メカニズムを提供することです。 

Exchange Online の時間差データベースコピーは、7日間のログファイル再生ラグタイムで構成されます。 さらに、Exchange 再生ラグマネージャーは、時間差コピーに対して動的ログファイルの再生を有効にして、時間差データベースコピーを自己修復し、ログファイルの拡張を管理できるようにします。 Exchange Online では時間差データベースコピーが使用されていますが、ポイントインタイムのバックアップが保証されているわけではないことを理解しておくことが重要です。 Exchange Online の時間差データベースコピーには可用性のしきい値があり、通常は、時間差コピーが格納されているディスクがディスク障害によって失われる時間のため、時間差コピーが、高可用性コピー (自動再生による) になることもあります。時間差データベースコピーがログ再生キューを再構築している期間。 

## <a name="transport-resilience"></a>トランスポートの復元性 
Exchange Online には、シャドウ冗長とセーフティネットという2つの主要なトランスポート復元機能があります。 シャドウ冗長は、送信中のメッセージの冗長コピーを保持します。 セーフティネットは、メッセージが正常に配信された後に、メッセージの冗長コピーを保持します。 

シャドウ冗長性を使用すると、各 Exchange Online トランスポートサーバーは、メッセージを送信側サーバーに正常に受信することを確認する前に、受信した各メッセージのコピーを作成します。 これにより、トランスポートパイプライン内のすべてのメッセージが送信中に冗長化されます。 Exchange Online で送信中に元のメッセージが失われたことが確認されると、メッセージの冗長コピーが再配信されます。 

セーフティネットは、メールボックスサーバー上のトランスポートサービスに関連付けられているトランスポートキューです。 このキューにより、サーバーによって正常に処理されたメッセージのコピーが保存されます。 メールボックスデータベースまたはサーバーの障害が、メールボックスデータベースの古いコピーをアクティブにする必要がある場合、セーフティネットキュー内のメッセージは、メールボックスデータベースの新しいアクティブコピーに自動的に再送信されます。 セーフティネットは冗長でもあるため、単一障害点としてのトランスポートが不要になります。 プライマリセーフティネットとシャドウセーフティネットの概念を使用して、プライマリセーフティネットが12時間以上利用できない場合、再送信要求がシャドウ再送信要求となり、メッセージがシャドウセーフティネットから再配信される場合があります。

セーフティネットからのメッセージの再送信は、dag およびメールボックスデータベースコピーを管理する Microsoft Exchange Replication サービスのアクティブマネージャーコンポーネントによって自動的に開始されます。 セーフティネットからメッセージを再送信するために手動での操作は必要ありません。 

## <a name="single-bit-correction"></a>シングルビット修正 
ESE には、ハードウェアエラーの結果である単一ビット CRC エラー (つまり、1ビットフリップ) を検出して解決するメカニズムが含まれています (つまり、物理的な破損を示す)。 これらのエラーが発生すると、ESE はそれらを自動的に修正し、イベントログにイベントを記録します。 

## <a name="online-database-scanning"></a>オンラインデータベーススキャン 
オンラインデータベーススキャン (*データベースチェックサム*とも呼ばれます) は、ESE がデータベース整合性チェッカーを使用して各ページを読み取り、ページが破損しているかどうかを確認するプロセスです。 主な目的は、トランザクション操作によって検出されない可能性がある物理的な破損および失われたフラッシュを検出することです。 データベーススキャンは、ストアのクラッシュ後のクラッシュ操作も実行します。 クラッシュによって領域がリークし、オンラインデータベーススキャンによって失われた領域が検出され、回復されることがあります。 システムは、すべてのデータベースが7日ごとに完全にスキャンされることを想定して設計されています。 

## <a name="lost-flush-detection"></a>失われたフラッシュの検出 
ディスクサブシステムまたはオペレーティングシステムが完了として返されたデータベース書き込み操作が実際にディスクに書き込まれなかったか、正しくない場所に書き込まれたときに、破損フラッシュが発生します。 失われたフラッシュインシデントはデータベースの論理的な破損につながる可能性があるため、データの損失を回避するために、ESE に失われたフラッシュ検出メカニズムが用意されています。 データベースページがパッシブコピーに書き込まれると、アクティブコピーの失われたフラッシュに対してチェックが実行されます。 失われたフラッシュが検出されると、ESE はページパッチ処理を使用してプロセスを修復できます。 

## <a name="single-page-restore"></a>単一ページの復元 
単一ページの復元、つまり*ページパッチ*は、破損したデータベースページが正常なレプリカからの正常なコピーに置き換えられる自動プロセスです。 破損したページの修復プロセスは、データベースコピーがアクティブであるかパッシブであるかによって異なります。 アクティブなデータベースコピーは、破損したページを検出すると、ページが完全に最新の状態になっていれば、そのレプリカの1つからページをコピーできます。 これは、ページの要求をログストリームに配置することによって実現されます。これは、メールボックスデータベースのレプリケーションの基礎となります。 レプリカがページ要求を検出するとすぐに、要求元のデータベースコピーにページのコピーを送信することによって応答します。 また、単一ページの復元では、レプリカが現在オフラインであっても、レプリカからページを要求するためにアクティブな非同期通信メカニズムも提供されます。 

時間差データベースコピーを含むパッシブデータベースコピーが破損した場合、これらのコピーは常にアクティブコピーの背後にあるため、アクティブコピーからパッシブコピーに任意のページをコピーするのは常に安全です。 パッシブデータベースコピーは自然に高可用性のため、ページのパッチ処理中にログの再生は中断されますが、ログのコピーは続行されます。 パッシブデータベースコピーは、アクティブなコピーから破損したページのコピーを取得し、ログ生成に必要な最大要件を満たすログファイルがコピーおよび検査されるまで待機してから、破損したページを更新します。 ページにパッチが適用されると、ログ再生が再開します。 このプロセスは、時間差データベースコピーの場合と同じですが、時間差データベースは、最初に patchable 状態を実現するために必要なすべてのログファイルを再生する点が異なります。 

## <a name="mailbox-replication-service"></a>メールボックスレプリケーションサービス 
メールボックスの移動は、大規模なメールサービスを管理するための重要な部分です。 常に更新されたテクノロジとハードウェアおよびバージョンのアップグレードがあります。これにより、エンジニアがこの作業を行い、メールボックスの移動をユーザーに対して透過的に行うことができます (オンライン状態が維持されていることを確認してください)。プロセス全体) は重要であり、メールボックスのサイズが大きくなるにつれて、プロセスが適切に拡張されるようにすることが重要です。 

Exchange メールボックスレプリケーションサービス (mr) は、データベース間でメールボックスを移動する役割を担います。 移行中、mr はメールボックス内のすべてのアイテムに対して整合性チェックを実行します。 整合性の問題が検出された場合は、問題を解決するか、破損したアイテムをスキップして、メールボックスの破損を回避することができます。 

お客様は、お客様が Exchange Online のコンポーネントであるため、今後検出される新しい形式の破損に対処するために、コードに変更を加えることができます。 たとえば、問題を解決できないという一貫性の問題が検出された場合は、破損を分析し、mr コードを変更して、矛盾を修正します (方法を理解している場合)。 

## <a name="log-file-checks"></a>ログファイルのチェック 
Exchange データベースによって生成されたすべてのトランザクションログファイルには、いくつかの形式の整合性チェックが行われます。 ログファイルが作成されると、最初に行うことはビットパターンを作成してから、一連のログ書き込みを実行するということです。 これにより、Exchange Online は一連のチェック (失われたフラッシュ、CRC、その他のチェック) を実行して、書き込まれた各ログファイルを検証したり、複製したりします。 

## <a name="deployment-on-resilient-file-system"></a>弾性ファイルシステムへの展開 
ファイルシステムレベルで破損が発生しないようにするために、Exchange Online は回復機能を強化するために、復元可能なファイルシステム (ReFS) パーティションに展開されています。 ReFS は、データ破損に対する復元性を向上させるために設計された Windows Server 2012 以降のファイルシステムで、データの可用性と整合性を最大限に高めます。 具体的には、メタデータの更新方法が向上し、データの保護が向上し、データ破損のケースが減少します。 また、チェックサムを使用して、ファイルデータの整合性と、データの破損が容易に検出および修復されることを確認します。 

Exchange Online は、次に示すいくつかの参照の利点を活用しています。 
- データ整合性の復元性が向上すると、データ破損インシデントが減少します。 破損インシデントの数を減らすと、不要なデータベースの再シードが減少します。 
- メタデータで実行されているチェックサムにより、破損のケースをより早く検出できるようになり、データボリュームでグレイエラーが発生する前に、顧客データの破損を修正できるようになります。
- パフォーマンスに影響を与えることなく、非常に大規模なデータセット (ペタバイト以上) で正常に動作するように設計されている
- Exchange Online で使用されるその他の機能のサポート (BitLocker 暗号化など)。 

Exchange Online には、他の ReFS 機能によるメリットもあります。 
- **整合性 (整合性ストリーム)** -ReFS は、通常、データ損失が発生する多くの一般的なエラーからデータを保護する方法でデータを格納します。 Office 365 検索は、整合性ストリームを使用して、ファイルコンテンツの早期のディスク破損検出とチェックサムを支援します。 また、この機能により、"欠落書き込み" によって発生する破損インシデントが減少します (停電などのために書き込み操作が完了しなかった場合)。 
- **availability (Salvage)** -ReFS は、データの可用性の優先順位を示します。 従来は、ファイルシステムがデータ破損の影響を受けやすくなり、修復のためにシステムをオフラインにする必要がありました。 まれに破損が発生した場合、ReFS は salvage を実装します。この機能は、ライブボリューム上の名前空間から破損したデータを削除し、修復できない破損データによって良好なデータが悪影響を受けないようにする機能です。 Salvage 機能を適用し、データ破損を Exchange Online データベースボリュームに分離することは、破損した状態と修復処理の間に影響を受けないデータベースを破損したボリュームに保持できることを意味します。 これにより、通常はディスク破損の問題の影響を受けるデータベースの可用性が向上します。 