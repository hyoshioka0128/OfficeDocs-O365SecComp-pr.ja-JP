---
title: EOP の機能
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: 次の表は、Exchange Online Protection (EOP) でホストされた電子メール フィルタリング サービスで使用可能な機能の一覧です。
ms.openlocfilehash: c5de41d1c24d6730367cc9cd739535ec094a99a3
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599793"
---
# <a name="eop-features"></a>EOP の機能

次の表は、Exchange Online Protection (EOP) でホストされた電子メール フィルタリング サービスで使用可能な機能の一覧です。 
  
> [!TIP]
> 「[ビジネス向けの Office 365 ロードマップ](https://office.microsoft.com/en-us/products/office-365-roadmap-FX104343353.aspx)」は新機能を調べるためのお勧めの情報源です。異なる EOP サブスクリプション プランで使用可能な機能のより広範な説明については、「[Exchange Online Protection サービスの説明](https://go.microsoft.com/fwlink/p/?LinkId=320619)」を参照してください。 
  
|||
|:-----|:-----|
|**機能**|**説明**|
|**スパム対策保護**||
|受信スパム検出|受信スパム対策保護機能は常に有効であり、無効にすることはできません。接続フィルターやコンテンツ フィルター ポリシーを使用して、カスタムの設定を構成できます。  <br/> EOP スタンドアロンのお客様の場合、既定では、EOP コンテンツフィルターはスパム検出メッセージを各受信者の迷惑メールフォルダーに送信します。 ただし、[**メッセージを迷惑メールフォルダーに移動する**] アクションがオンプレミスのメールボックスに対して機能するようにするために、オンプレミスのサーバー上で2つの Exchange メールフロールール (トランスポートルールとも呼ばれる) を構成して、追加されたスパムヘッダーを検出する必要があります。EOP によって。 詳細については、「[スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。|
|送信スパム検出|送信電子メールを送信するサービスを使用している場合は送信スパム対策保護機能が常時有効になっているため、このサービスを利用している組織と対象受信者は保護されます。 送信スパム フィルターは、受信フィルターと同様、接続フィルターとコンテンツ フィルターで構成されています。 送信スパム フィルターの設定は構成できませんが、疑わしい送信メッセージとブロックされた送信メッセージを管理者に通知するよう構成するために使用する送信スパム ポリシーの設定が存在します。 詳細については、「 [Configure the outbound spam policy](../configure-the-outbound-spam-policy.md)」を参照してください。|
|NDR バックスキャター保護|Ndr バック散布の詳細については、「 [Advanced spam filtering options](../advanced-spam-filtering-asf-options.md) 」および「[バックスキャター messages and EOP](../backscatter-messages-and-eop.md)」の「ndr バックスキャター」設定を参照してください。|
|バルク メール フィルタリング|EOP にはバルク メール メッセージを識別するための強力な検出方法があります。 ユーザー インターフェイス経由でバルク メール メッセージをマークするようにサービスを構成できます。 メールフロールールを作成して、バルクメールメッセージヘッダースタンプを検索することによって、より積極的にバルクメールをフィルター処理することもできます。 バルクメールの詳細については、「[迷惑メールとバルクメールの違い](../what-s-the-difference-between-junk-email-and-bulk-email.md)」および関連するサブトピックを参照してください。|
|悪意のある URL 禁止リスト|EOP では、メッセージ内の既知の悪意のあるリンクを検出するため、いくつかの URL 禁止リストを使用しています。|
|フィッシング対策保護|EOP には既知のスパム発信者 750,000 名のドメインが含まれています。|
|**スパム管理**||
|接続フィルター「IP 許可一覧」および「IP 禁止一覧」構成機能|この接続フィルターで指定する IP アドレスは、単一の IP アドレスと CIDR IP アドレス範囲で記述できます。 このサービスは IPv6 アドレスもサポートしています。 詳細については、「[接続フィルター ポリシーを構成する](../configure-the-connection-filter-policy.md)」を参照してください。|
|ユーザー、グループ、またはドメインごとにコンテンツ フィルター ポリシーをカスタマイズする機能|よりきめ細かく制御する場合は、カスタム コンテンツ フィルター ポリシーを作成して、それを組織内の特定のユーザー、グループ、またはドメインに適用することができます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (つまり、実行順序) を変更できます。 詳細については、「 [スパム フィルター ポリシーの構成](../configure-your-spam-filter-policies.md)」を参照してください。|
|コンテンツによりフィルター処理されたメッセージに対するアクションを構成する機能|複数の構成可能なアクションがあります。 たとえば、コンテンツによりフィルターされたメッセージを削除したり、[迷惑メール] フォルダーまたは検疫にそれらのメッセージを送信したりできます。 詳細については、「 [スパム フィルター ポリシーの構成](../configure-your-spam-filter-policies.md)」を参照してください。|
|スパム メールを積極的にフィルター処理する拡張オプションの構成機能|詳細については、「[スパムフィルターポリシーの構成](../configure-your-spam-filter-policies.md)」および「 [Advanced spam filtering options](../advanced-spam-filtering-asf-options.md) (各オプションの機能に関する具体的な詳細情報を提供します)」を参照してください。|
|国際スパム フィルタリング|EOP を構成して、特定の言語で書かれたメッセージまたは特定の国や地域から送信されたメッセージをフィルターできます。 最大 86 言語、250 地域を構成できます。 サービスが信頼度の高いスパムに対して構成されたアクションを適用します。 詳細については、「 [スパム フィルター ポリシーの構成](../configure-your-spam-filter-policies.md)」を参照してください。|
|Outlook または web 上の Outlook (旧称 Outlook Web App) を使用してスパムを管理する|管理者およびエンド ユーザーは、安全な送信者の一覧および受信拒否送信者の一覧を作成できます。 詳細情報:  <br/> Web 上の Outlook:[ブロックまたは許可 (迷惑メール設定)](https://go.microsoft.com/fwlink/p/?LinkId=294862)を参照してください。  <br/> Outlook:「[迷惑メール フィルターの概要](https://go.microsoft.com/fwlink/p/?LinkId=270065)」を参照してください。  <br/> EOP を使用してオンプレミスのメールボックスを保護している場合は、必ずディレクトリ同期を使用して、これらの設定がサービスに同期されるようにしてください。 ディレクトリ同期のセットアップ方法については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」の「ディレクトリ同期を使用してメール ユーザーを管理する」を参照してください。|
|Microsoft Office Outlook の迷惑メール報告アドイン経由のスパム報告|解析用に Microsoft にスパム メッセージを報告するためのアドインを Outlook にダウンロードできます。 このツールのダウンロードと使用の詳細については、「[レポートメッセージアドインを有効にする](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)」を参照してください。  <br/> EOP を使用して Exchange Server 2013 以降を使用している場合は、「 [web 上の outlook で迷惑メールとフィッシング詐欺を報告](../report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)する」に記載されているように、web 上の outlook で右クリックしてスパムメッセージを送信することもできます。|
|電子メール エイリアスを使用したスパムおよび非スパムの報告|スパム (迷惑メール) メッセージと非スパム (非迷惑メール) メッセージを電子メール経由で Microsoft に報告できます。 詳細については、「[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」を参照してください。|
|Outlook on the web を使用したスパムおよび非スパムの送信迷惑メールの報告|迷惑メール報告の Outlook を使用して、スパムメッセージと非スパムメッセージを Microsoft に送信することができます。 詳細については、「 [Outlook on the web で迷惑メールとフィッシング詐欺を報告する](../report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)」を参照してください。  <br/> 現在、この機能は、Exchange Server 2013 SP1 以降のメールボックスが EOP によってフィルター処理されている web 上の Outlook で使用できます。 Web 上の Exchange Online Outlook のお客様は、近い将来にこの機能を利用できます。|
|エンドユーザー スパム検疫通知|エンド ユーザーは、各自のスパム検疫メッセージを解放し、オプションとして、エンドユーザーのスパム通知メッセージを介して迷惑メールではないメールとして報告できます。 このような通知メールは、管理者によって構成および有効化される必要があります。詳細については、「 [Exchange Online でのエンドユーザースパム通知の構成](../configure-end-user-spam-notifications-in-exchange-online.md)」または「 [EOP でのエンドユーザースパム通知の構成](../configure-end-user-spam-notifications-in-eop.md)」を参照してください。|
|エンドユーザー スパム検疫通知頻度|この頻度は、既定では 3 日であり、1 ～ 15 日の範囲で構成できます。|
|エンドユーザー スパム検疫通知の言語の構成機能 (管理者向け)|これは、エンドユーザーおよび管理者が使用できます。詳細については、「[Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md)」または「[Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)」を参照してください。  |
|検疫内のメッセージへの Web ページ経由のアクセスと管理|これは、エンドユーザーおよび管理者が使用できます。詳細については、「[Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md)」または「[Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)」を参照してください。  |
|検疫を検索する機能|特定のスパム メッセージの検疫を検索する機能は、管理者とエンドユーザーの両方が使用できます。詳細については、「[Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md)」または「[Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)」を参照してください。  |
|Exchange 管理センターからのスパム検疫済みメッセージ ヘッダーを表示する|検疫内のメッセージを表示した後で、メッセージ ヘッダー テキストをコピーして[メッセージ ヘッダー アナライザー](https://testconnectivity.microsoft.com/?tabid=mha)に貼り付けます。メッセージ ヘッダー アナライザーはメッセージがどうなったかについて説明します。    |
|**マルウェア対策保護**||
|マルウェア対策保護の複数のエンジン|複数のマルウェア対策エンジンは、常にお客様を自動的に保護します。|
|マルウェア フィルターを無効にするオプション|サービスを通じてルーティングされるすべての電子メール メッセージに対するマルウェア対策スキャンは強制されるので、マルウェア フィルターを無効にすることはできません。一貫した、厳しい水準の保護をすべてのお客様に提供することは、お客様の電子メール メッセージ環境の保護に必要な綿密な防御戦略に必要不可欠であると考えています。そのため、マルウェア フィルタリングはすべてのお客様に対して自動的に有効になっています。|
|メッセージ本文と添付ファイルのマルウェア検査|このサービスは、メッセージ本文とすべての添付ファイルのアクティブなペイロードにマルウェアがないか検査します。|
|既定またはカスタム マルウェア アラート通知|メッセージがマルウェアとして検出されて配信されない場合に、送信者または管理者に通知電子メール メッセージを送信するオプションがあります。 これらの通知は、メッセージ全体が削除される場合にのみ送信されます。 詳細については、「[マルウェア対策ポリシーを構成する](../configure-anti-malware-policies.md)」を参照してください。|
|マルウェアが検出された場合に添付ファイルを削除するオプション|管理者は、メッセージ全体を削除するか、添付ファイルを除去してカスタマイズされたメッセージを受信者に送信するかを選択できます。 詳細については、「[マルウェア対策ポリシーを構成する](../configure-anti-malware-policies.md)」を参照してください。|
|スパイウェア対策保護|マルウェア対策保護には、ウイルス対策保護およびスパイウェア対策保護が含まれます。|
|ユーザー、グループ、またはドメインごとにマルウェア フィルター ポリシーをカスタマイズする機能|よりきめ細かく制御する場合は、カスタム マルウェア フィルター ポリシーを作成して、それを組織内の特定のユーザー、グループ、またはドメインに適用することができます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (つまり、実行順序) を変更できます。 詳細については、「[マルウェア対策ポリシーを構成する](../configure-anti-malware-policies.md)」を参照してください。|
|**メール ルーティングとコネクタ**||
|条件付きメール ルーティング|詳細については、「[Create Connectors for Conditional Mail Routing](http://technet.microsoft.com/library/905dc235-1d2b-487e-a65a-516d92e88347.aspx)」を参照してください。|
|便宜的な TLS または強制 TLS|便宜的または強制 TLS をコネクタで使用できます。 Oplock tls は tls 接続を試行しますが、TLS 接続が失敗した場合は SMTP 接続を使用します。 強制 tls は tls 接続を強制します。つまり、TLS 接続が失敗した場合、メッセージは拒否されます。 TLS、セキュリティ、およびコネクタの詳細については、「[Set up connectors for secure mail flow with a partner organization](http://technet.microsoft.com/library/1ce4d6a4-41ba-4d1e-9ca9-e826252c1041.aspx)」をご覧ください。|
|地域ルーティング (特定の地域へのメール フローの制限)|詳細については、「[Exchange Online Protection の概要](exchange-online-protection-overview.md)」の「EOP データセンター」セクションを参照してください。|
|SMTP 接続チェック ツール|このツールを使用してメール フローをテストする方法の詳細については、「[Test Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)」を参照してください。|
|一致サブドメイン|承認済みドメインのサブドメインとの間でメール フローを有効にする方法の詳細については、「[EOP でサブドメインの電子メール フローを有効にする](http://technet.microsoft.com/library/b5684042-dadc-4111-95b3-c2fd06e368bf.aspx)」を参照してください。|
|**メール フロー ルール**||
|ポリシー ベースのフィルタリングとアクション|カスタムポリシーは、Exchange メールフロールールに基づいています。 ドメイン、キーワード、ファイル名、ファイル タイプ、件名行、メッセージ本文、送信者、受信者、ヘッダー、IP アドレスによるフィルターが可能です。 詳細については、「 [Mail flow rules (transport rules) In Exchange Online Protection](mail-flow-rules-transport-rules-0.md)」を参照してください。|
|テキスト パターンによるフィルター|メールフロールールは、配列または正規表現を使用して、テキストと一致させることができます。 1 つの文字列または複数の文字列の配列を使用して、アドレス、件名、本文、または添付ファイル名など、多くのメッセージ プロパティと一致させることもできます。 詳細については、「 [Mail flow rules (transport rules) In Exchange Online Protection](mail-flow-rules-transport-rules-0.md) 」を参照してください。|
|ユーザー辞書|メールフロールールには、テキストとキーワードの長いリストを含めることができ、ユーザー辞書と同じ機能を提供します。|
|ドメイン単位のポリシー ルール|メールフロールールのスコープは、送信者または受信者のドメイン名、IP アドレスの範囲、アドレスのキーワードまたはパターン、グループメンバーシップ、およびその他の条件と一致するようにカスタマイズできます。|
|添付ファイル スキャン|ルールを作成して、添付ファイルのファイル名、拡張子、および内容をスキャンできます。|
|送信者へのポリシー ルール通知の送信|**[説明を示してメッセージを拒否する]** または **[次の拡張状態コードのメッセージを拒否する]** アクションを使用して、メッセージを拒否し、配信不能レポート (NDR) を送信者に送信できます。 詳細については、「[メールフロールールのアクション](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx)」を参照してください。|
|固定のアドレスへのメッセージの送信 (特定のアドレスへのメッセージのリダイレクトやコピーなど)|メールフロールールは、リダイレクト、カーボンコピーまたはブラインドカーボンコピーによる受信者の追加、受信者の追加、その他のオプションを使用できます。 詳細については、「[メールフロールールのアクション](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx)」を参照してください。|
|複数のルール間でルールの優先順位を簡単に調整する機能|Exchange 管理センターを使用して、ルールが処理される順序を変更します。|
|メッセージをフィルターしてからメッセージのルーティングまたは属性を変更する機能|さまざまな条件に基づいてメッセージをフィルターしてから、一連のアクションを各メッセージに適用できます。 詳細については、「 [Mail flow rules (transport rules) In Exchange Online Protection](mail-flow-rules-transport-rules-0.md)」を参照してください。|
|ルールによってメッセージの Spam Confidence Level レベルを変更します。|送信中のメッセージを検査し、選択した基準に基づいて Spam Confidence Level レベルを割り当てることができます。 詳細については、「[メールフロールールを使用してメッセージにスパム信頼レベル (SCL) を設定する](../use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)」を参照してください。|
|メッセージの添付ファイルの検査|添付ファイルの内容または添付ファイルの特性を調べて、調べた内容に基づいて実行するアクションを定義できます。 詳細については、「[メールフロールールを使用してメッセージの添付ファイルを検査する](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)」を参照してください。|
|**管理**||
|Web ベースの管理|EOP 管理者は、60言語でサポートされている Exchange 管理センター (EAC) インターフェイスを介してサービスを管理できます。 詳細については、「exchange [Online Protection の exchange 管理センター ](../exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。|
|ディレクトリ同期|ディレクトリ同期は、Azure Active Directory 同期ツール から利用できます。詳細については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」の「ディレクトリ同期を使用してメール ユーザーを管理する」セクションを参照してください。  |
|ディレクトリ ベースのエッジ ブロック (DBEB)|DBEB 機能では、サービス ネットワーク境界で無効な受信者宛てのメッセージを拒否することができます。管理者は DBEB を使用することにより、メールが有効な受信者を Office 365 に追加したり、Office 365 内に存在しない電子メール アドレスに送信されたすべてのメッセージをブロックしたりすることができます。DBEB の構成の詳細は、「[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)」を参照してください。  |
|リモート Windows PowerShell へのアクセス|すべての EOP 機能はリモート Windows PowerShell で利用できます。詳細については、「[Exchange Online Protection の PowerShell](http://technet.microsoft.com/library/f7918a88-774a-405e-945b-bc2f5ee9f748.aspx)」を参照してください。  |
|**レポート作成とログ記録**||
|メッセージ追跡|メッセージ追跡機能を使用すると、管理者はサービスを経由する電子メール メッセージを追跡できます。これは、対象の電子メール メッセージがサービスによって受信、拒否、延期、または配信されたかどうかを判断する上で役立ちます。したがって、効率良くユーザーの質問に回答したり、メール フローの問題をトラブルシューティングしたり、ポリシーの変更を検証したり、テクニカル サポートに支援を求める必要性を減らしたりできます。詳細については、「[Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)」を参照してください。  |
|Web ベースのレポート|Microsoft 365 管理センターのメール保護レポートは、メッセージングデータを提供します。 たとえば、検出されたスパムとマルウェアの量や、メールフロールールが一致した頻度を監視できます。 これらの対話式レポートを使用すると、概要データに関する視覚的なレポートを素早く取得し、過去 90 日間の各メッセージの詳細を確認できます。 詳細については、「[Use mail protection reports in Office 365 to view data about malware, spam, and rule detections](http://technet.microsoft.com/library/bcef7984-4bfa-4ca8-9fa5-a65af8618f5d.aspx)」を参照してください。|
|Excel レポート作成ワークブック経由の詳細なレポート作成|Excel 2013 レポート作成ワークブックのメール保護レポートも使用できます。 ただし、代わりに管理センターレポートを使用することをお勧めします。 Excel 2013 レポート ワークブックは、今後は提供されなくなる予定です。|
|監査ログ|管理者の役割グループ レポートおよび管理者監査ログは、EOP 管理者が利用できます。詳細については、「[EOP の監査レポート](auditing-reports-in-eop.md)」を参照してください。  |
|**サービス レベル アグリーメント (SLA) とサポート**||
|スパム有効性 SLA|\>99%|
|偽陽性率 SLA|\<1:250,000|
|ウイルス検出とブロック SLA|既知のウイルスの 100%|
|月間稼働時間 SLA|99.999%|
|1 日 24 時間、週 7 日の電話および Web テクニカル サポート|EOP ヘルプおよびサポート オプションの詳細については、「[EOP のヘルプとサポート](help-and-support-for-eop.md)」を参照してください。|
|**その他の機能**||
|サーバーの地域冗長グローバル ネットワーク|EOP は、最適な可用性を提供するよう設計された、複数のデータ センターから成る世界規模のネットワーク上で稼働します。詳細については、「[Exchange Online Protection の概要](exchange-online-protection-overview.md)」の「EOP データセンター」セクションを参照してください。  |
|社内サーバーでメールが受信できない場合のメッセージ キュー|保留にされたメッセージはキュー内で 2 日間保持されます。メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。平均では、5 分ごとにメッセージの送信が再試行されます。詳細については、「[EOP のキューイング、保留、返送されるメッセージに関する FAQ](eop-queued-deferred-and-bounced-messages-faq.md)」を参照してください。  |
|アドオン サービスとして利用可能な Office 365 Message Encryption|詳細については、「[Office 365 での暗号化](https://technet.microsoft.com/en-us/library/dn569286.aspx)」をご覧ください。|
   

