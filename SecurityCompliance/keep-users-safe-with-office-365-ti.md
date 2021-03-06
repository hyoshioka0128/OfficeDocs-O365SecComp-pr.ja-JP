---
title: Office 365 のユーザーに Office 365 の脅威の調査と応答機能を安全に保つ
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/09/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3387bfc3-028a-42f4-8133-4cbecfaab812
ms.collection:
- M365-security-compliance
description: Office 365 の脅威調査および応答機能を使用して、組織が侵入や脅威を検出し、脅威から迅速に脅威を軽減および回復する方法について説明します。
ms.openlocfilehash: 28fbf0a66370e2e1d407454017943e57f5f368b1
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598983"
---
# <a name="keep-your-office-365-users-safe-with-office-365-threat-investigation-and-response-capabilities"></a>Office 365 のユーザーに Office 365 の脅威の調査と応答機能を安全に保つ

## <a name="overview"></a>概要

どの Office 365 ユーザーが攻撃にさらされているか、または深刻な侵害になっているかどうかを確認します。 ユーザーを対象とする攻撃を緩和して回復する方法を理解していますか。 Office 365 で既に利用可能なセキュリティ機能を使用して、これを正確に実行できることがわかりましたか? 
  
Office [365 の脅威の調査と応答](office-365-ti.md)機能が Office 365 E5 サブスクリプション (Office 365 Advanced Threat Protection プラン2の一部として) に含まれています。 これらの機能により、Microsoft IT は、社会エンジニアリングインシデントの解決に要する平均時間を 80% に減らし、過去2四半期と比較して1か月あたりのケーススループットを 37% 増加させました。 

最近、新しい機能を追加して、脅威を検出して回復する方法を改善しました。 この記事では、更新された脅威の調査と応答の機能をさらに効率的にする方法について簡単に説明します。
  
## <a name="detect-intrusions-and-threats"></a>侵入と脅威を検出する

[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)(脅威エクスプローラーとも呼ばれます) は、セキュリティ管理者とアナリストが、安全なように見える一見したユーザー構成によって、最も複雑なセキュリティ設定を回避できるため、企業内でアクティブになっている脅威を特定して理解するのに役立つ。送信者のホワイトリスト。 エクスプローラーは、ユーザーがマルウェアやフィッシングなどの脅威によって侵害されたかどうかを、Office 365 グローバルまたはセキュリティ管理者が迅速に判断するのに役に立ちます。 これにより、脅威や必要な応答に対して最も危険度の高いユーザーに優先順位を付けることができます。 
  
エクスプローラーを使用すると、管理者はユーザーとメールの間の関係を移動することもできます。 特定のメールが正しくないことがわかりますか。 これを検索して、どのユーザーがメールを受信したかを確認してから、一連のイベントを実行し、それらのユーザーが実行したことを確認します。

これらの機能がまだ用意されていない場合は、[今すぐお試しください](https://aka.ms/tryo365threatintel3)。 [Office 365 の脅威の調査と応答の詳細に](https://aka.ms/readmoreabouto365threatintel)ついて説明します。
  
![Office 365 の脅威エクスプローラーのスクリーンショット、マルウェアファミリによる色分け](media/591338dd-252a-437d-b5f2-87aa42e74b0c.png)
  
## <a name="quickly-mitigate-and-recover-from-threats"></a>脅威を迅速に軽減および復旧する

セキュリティ管理者は、テナント内で疑わしいまたは悪意のあるものを特定すると、その脅威に迅速に対応し、**インシデントフレームワーク**を使用して対応することができます。 不要なメッセージを1回クリックしてグループ化し、ユーザーのメールボックスからすばやく電子メールメッセージを削除します。 
  
 **更新:** インシデントフレームワークから直接電子メールを削除 (ソフト削除またはハード削除) する機能を追加しました。 以前の管理者は、ユーザーの迷惑メールフォルダーにのみメールを移動でき、ユーザーはそのアイテムを回復できます。 新たにリリースされた削除機能を使用すると、悪意のあるメールまたは不要なメールが完全に削除されていることを確認できるようになりました。 
  
これらの機能がまだ用意されていない場合は、[今すぐお試しください](https://aka.ms/tryo365threatintel3)。 [Office 365 の脅威の調査と応答の詳細に](https://aka.ms/readmoreabouto365threatintel)ついて説明します。
  
![インシデント修復の電子メールリストのスクリーンショット](media/9d8452d3-d8d2-4b26-81f9-76396e08dd17.png)
  
## <a name="leverage-the-threat-telemetry-of-microsoft"></a>Microsoft の脅威テレメトリを活用する

Office 365 の脅威の調査と応答機能には、Microsoft インテリジェントセキュリティグラフからのデータが使用されています。 グラフは、10億の Windows デバイス、4500億月の Azure ログイン、および Office 365 の4000億の電子メールメッセージから最新の脅威信号を取得します。 この unrivaled の脅威の信号は、管理者およびセキュリティアナリストが組織に影響を与える脅威を完全に把握するために不可欠な、顧客のテナントに対する広範な可視性を提供します。 
  
   
## <a name="why-use-office-365-threat-investigation-and-response-capabilities"></a>Office 365 の脅威の調査および応答機能を使用する理由

2017が $ 90B を超えた場合、Gartner の推定は cybersecurity に費やされました。 Sid Deshpande、Gartner の主な研究アナリストは、「the the the the the the the the the the the the the the the the the the the the the the the the the the the the the」と言っています。 検出/応答機能に関連付けられていない限り、futile が無効であることを示すメッセージを送信します。 脅威の調査と応答は、すべての企業のサービスポートフォリオの重要な部分であり、スタンドアロンサービスとして、または Office 365 E5 の一部として使用できます。
  
## <a name="whats-next"></a>[次へ]

- この記録されたセッションの Office 365 脅威の調査および応答機能の詳細については[、「office 365 で Cyberattacks を使用する](https://myignite.microsoft.com/videos/53723)」を参照してください。
    
- [今すぐ office 365 の脅威の調査と応答機能を試す](https://aka.ms/tryo365threatintel3)か、または office E5 の試用版を開始しましょう。 
    

