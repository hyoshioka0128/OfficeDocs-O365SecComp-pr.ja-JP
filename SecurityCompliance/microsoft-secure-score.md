---
title: Microsoft セキュリティスコア
description: Microsoft 365 のセキュリティスコア、詳細の計算方法、およびセキュリティ管理者がどのように使用することを期待できるかについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティで保護されたスコア、セキュリティセンター、改善アクション
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: de3abe7ca0e84efd2412984e172202d8f3962476
ms.sourcegitcommit: 9d48b656406e916e93651352692c5c6bcbbd645f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "30203731"
---
# <a name="microsoft-secure-score-preview"></a>Microsoft セキュリティスコア (プレビュー)

microsoft 365 セキュリティセンターでは、microsoft セキュリティスコアを使用して、組織のセキュリティ体制をさらに可視化し、制御することができます。一元管理されたダッシュボードから、Microsoft 365 の id、データ、アプリ、デバイス、およびインフラストラクチャのセキュリティを監視し、強化することができます。

microsoft のセキュリティで保護されたスコアは、堅牢な視覚エフェクト、他の Microsoft 製品との統合、他の企業とのスコアの比較、カテゴリ別のフィルタリングなどを提供します。このツールを使用すると、組織内のセキュリティ強化アクションを完了し、スコアの履歴を追跡することができます。このスコアは、サードパーティ製のソリューションが推奨される改善アクションに対応している場合にも反映できます。  

## <a name="how-it-works"></a>しくみ

推奨されるセキュリティ機能を構成するためのポイント、セキュリティ関連タスクの実行 (レポートの表示など)、またはサードパーティ製のアプリケーションまたはソフトウェアを使用した改善アクションへの対応を行います。一部のアクションは、ユーザーに対して多要素認証 (MFA) を有効にするなど、部分的な完了のスコアを獲得します。セキュリティは常にユーザビリティにバランスをとる必要があり、お客様の環境ですべての推奨事項が機能するわけではありません。

## <a name="required-permissions"></a>必要な権限:

現時点では、Microsoft セキュリティスコアを表示するには、Azure Active Directory に次のいずれかのロールが割り当てられている必要があります。

* グローバル管理者
* セキュリティ管理者
* セキュリティリーダ

## <a name="rich-experiences--additional-security-recommendations"></a>豊富なエクスペリエンス & その他のセキュリティに関する推奨事項

Microsoft のセキュリティで保護されたスコアでは、azure の AD、Intune、および Cloud App Security から推奨事項が追加されており、azure セキュリティセンターと Windows Defender ATP の推奨事項が近日中に提供されています。また、Office 365 のセキュリティに関する推奨事項をさらに追加しました。より広範な Microsoft 製品およびサービスのセットについて、さらに洞察を得られるようになるため、組織のセキュリティの状態についての管理者による報告を自信を持って考えることができます。[Microsoft Graph API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta)を使用してスコアを取得することもできます。

より迅速に必要な情報を提供するために、Microsoft の推奨事項がグループに分類されています。

* Identity (Azure AD アカウントとロールの保護状態)
* データ (Office 365 ドキュメントの保護状態)
* デバイス (デバイスの保護状態。Windows Defender ATP の改善アクションが近日中に予定される)
* アプリ (電子メールとクラウドアプリの保護状態)
* インフラストラクチャ (Azure リソースの保護状態、近日予定)

[Microsoft セキュリティスコアの概要] ページでは、これらのグループ間のポイントの分割方法と、使用可能なポイントを確認できます。また、概要ページでは、スコアの合計を表示し、セキュリティで保護されたスコアの傾向をベンチマーク比較によって把握し、スコアを向上させるために実行できる改善措置の優先順位付けを行うことができます。このデータを使用して、セキュリティに関する姿勢を高めることができます。  

![M365 ホーム](./media/secure-score/homepage-original.png)
ページ*図 1: Microsoft のセキュリティで保護されたスコアの概要ページ*

## <a name="take-action-to-improve-your-score"></a>スコアを向上させるためのアクションを実行する

[向上したアクション] タブには、テナントに適用可能なすべてのセキュリティ推奨が表示されます (完了、完了、未完了、サードパーティによる解決、無視)。すべてのコントロールを検索、フィルター、およびグループ化することができます。 ランク付けは、Microsoft による、セキュリティ価値と完了作業の両方の評価に基づいて行われます。

[採点なし] というラベルの付いたアクションは、Microsoft セキュリティスコアで追跡されません。それでもアクションを実行することはできますが、スコアに影響を与えることはありません。将来的に Microsoft セキュリティスコアによってアクションが追跡され、既に完了している場合は、その変更がセキュリティスコアに自動的に反映されます。

向上アクションをクリックすると、フライアウトが表示されます。この操作を完了するには、いくつかのオプションがあります。

1. [**ビューの設定**] を選択して構成画面に移動し、変更を行います。その後、スライドの上部に表示される、アクションに価値があるポイントを取得します。ポイントの更新には最大24時間かかる場合があります。

2. 向上アクションがサードパーティ製のアプリケーションまたはソフトウェアによって既に処理されているため、[**サードパーティによる解決**] を選択します。この操作に必要なポイントが得られます。したがって、セキュリティの全体的な姿勢がより適切に反映されます。サードパーティがコントロールをカバーしなくなった場合は、[改善] アクションを未完了としてマークすることができます。Microsoft は、改善アクションがサードパーティによって解決済みとしてマークされている場合に、スコア要件が満たされているかどうかを確認することに注意してください。

3. リスクを受け入れることを決定していて、改善アクションが実行されていないため、[**無視**] を選択します。[改善] アクションを無視すると、達成できるセキュリティで保護されたスコアポイントの合計数が減少します。このアクションは、履歴で表示するか、いつでも元に戻すことができます。

4. 改善アクションでは、環境の一部を定期的に確認してポイントを取得および保持する必要があるので、[**確認**] を選択します。たとえば、ネットワークからデータが抜き出しされないように、メールボックス転送ルールを週単位で確認する必要があります。変更を加える必要はありませんが、アクションを実行する必要があります。ルールを定期的に確認すると、ポイントが表示されます。指定しない場合は、スコアが減少します。

![M365 ホームページ](./media/secure-score/secure-score1x450.png) ![M365 ホームページ](./media/secure-score/secure-score2x450.png)

*図 2 & 3: 改善アクションの flyouts*

## <a name="monitor-improvements-over-time"></a>時間の経過に伴う向上を監視する

時間の経過とともに組織のスコアをグラフで確認するには、[**履歴**] タブを使用します。このビューには、選択した時間範囲内で行われたすべてのアクションと共に、グローバルな平均、業界の平均、および同様の座席数が含まれます。日付範囲をカスタマイズしたり、カテゴリ別にフィルター処理したりすることもできます。

スコアは1日に1回 (約 1:00 AM PST) 計算されます。測定されたアクションに変更を加えると、スコアは翌日を自動的に更新します。また、他のいくつかのポータルは Microsoft のセキュリティで保護されたスコア (Windows Defender セキュリティセンターなど) の一部を示していることにも注意する必要があります。改善アクションを完了し、これらのポータルでスコアが増加した場合は、更新されたスコアが Microsoft 365 セキュリティセンターに表示されるまでに最大24時間かかる場合があります。  

## <a name="risk-awareness"></a>リスクの認識

Microsoft Secure Score は、システム構成、ユーザーの行動、およびその他のセキュリティ関連の測定値に基づいて、セキュリティの状況を示す数値の概要です。システムまたはデータが侵害される可能性の絶対的な測定値ではありません。そうではなく、侵害されるリスクを相殺できるように、Microsoft 環境にセキュリティコントロールを採用している範囲を表しています。セキュリティ侵害から完全に保護されていないオンラインサービスはないため、セキュリティ違反に対する保証として、どのような方法でも安全スコアを解釈しないようにする必要があります。

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください

問題がある場合は、「 [Security, Privacy & コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)コミュニティ」に投稿してお知らせください。コミュニティを監視しており、ヘルプを提供しています。