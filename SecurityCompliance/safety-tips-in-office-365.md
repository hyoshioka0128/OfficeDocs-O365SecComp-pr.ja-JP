---
title: Office 365 の電子メールメッセージの安全性に関するヒント
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/6/2016
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: EOP および Office 365 スパムフィルターによってフィルター処理された電子メールメッセージの安全のヒントを紹介します。
ms.openlocfilehash: e3edf439a24339bb13cc8c884827a6e5d95edef9
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35601084"
---
# <a name="safety-tips-in-email-messages-in-office-365"></a>Office 365 の電子メールメッセージの安全性に関するヒント

Exchange Online Protection (EOP) と Office 365 は、スパム、フィッシング、マルウェアの防止を強化します。 今日では、これらの攻撃の一部は正当なものであることがよく細工されています。 [迷惑メール] フォルダーにメッセージを送信するだけでは不十分なわけではありません。 これで、Outlook または web 上の Outlook で電子メールを確認すると、EOP は自動的に送信者をチェックし、安全のヒントを電子メールの先頭に追加します。 
  
安全性に関するヒント (色分けされたメッセージ) は、潜在的に有害なメッセージに関する警告を表示します。 受信トレイ内のほとんどのメッセージには安全なヒントがありません。 スパム、フィッシング、およびマルウェア攻撃を防ぐために必要な情報が EOP および Office 365 にある場合にのみ表示されます。 受信トレイに安全のヒントが表示される場合は、次の例を使用して、安全に関するヒントの種類について詳しく調べることができます。
  
- 疑わしいメール (赤安全ヒント)。
    
    ![赤の安全ヒントを示すスクリーンショット。](media/5078a0be-e556-44a1-b169-09d780d26898.png)
  
    電子メールの赤の安全ヒントは、受信したメッセージに疑わしいものが含まれていることを意味します (フィッシング詐欺など)。 この種類の電子メールメッセージは、受信トレイからは開かずに削除することをお勧めします。
    
- スパム (黄色の安全性ヒント)。
    
    ![黄色の安全性ヒントを示すスクリーンショット。](media/793c9265-ea44-48fd-a98f-804fadd4163b.png)
  
    電子メールの黄色の安全ヒントは、メッセージがスパムとしてマークされていることを意味します。 メッセージの送信者を認識して信頼していない場合は、添付ファイルや画像をダウンロードしないで、メッセージ内のリンクをクリックしないでください。 Outlook on the web では、迷惑メールアイテムの黄色のバーにある [**スパムではない**] をクリックして、メッセージを受信トレイに移動できます。 受信トレイに配信されたメッセージに黄色の安全ヒントが表示される場合は、迷惑メールフォルダーへのスパムの移動を無効にしている可能性があります。 
    
- 安全なメール (緑色の安全ヒント)。
    
    ![緑の安全ヒントを示すスクリーンショット。](media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)
  
    安全でないメッセージに加えて、信頼できる送信者からの有効なメッセージについても、緑色の安全ヒントを示しています。 電子メールのグリーンセーフヒントは、メッセージの送信者を確認し、安全であることを確認したことを意味します。 Microsoft では、多くの場合、頻繁にスプーフィングまたは偽装される金融機関やその他の信頼できる差出人のリストを保持しています。
    
- フィルター処理なしのメール (灰色の安全ヒント)。
    
    ![灰色の安全なヒントを示すスクリーンショット。](media/c4d0cf8f-08e9-4c84-beee-1d9e0b022e0a.png)
  
    また、差出人セーフリストにある送信者からのメールの確認や、フィルターをバイパスするメールフロールールがある場合にも、メールのチェックをスキップしたことについてもお知らせします。 
    
    また、外部画像がブロックされている場合、つまりメッセージが受信トレイにあり、スパムではないが、ダウンロードしていない外部画像が含まれている場合にも、灰色の安全なヒントが表示されます。
    
## <a name="working-with-safety-tips"></a>安全に関するヒントの使用

セキュリティヒントは、すべてのメッセージが受信するわけではありませんが、Outlook on the web では常に有効になります。 Office 365 管理者は、Outlook などの他の電子メールクライアントに対して安全のヒントを無効にすることができます。 詳細については、「 [Office 365 の安全なヒントを有効または無効](enable-or-disable-safety-tips.md)にする」を参照してください。
  
Office 365 と EOP がどのようにメッセージに分類されているか (つまり、スパムではないか、または正当でないか) に同意しない場合は、分析のためにメッセージを送信して、快適な操作を行うことができます。 詳細については、「 [Outlook on the web で迷惑メールとフィッシング詐欺を報告する](https://technet.microsoft.com/library/dn594557.aspx)」を参照してください。 また、安全性ヒントの [フィードバック] リンクをクリックして、ご意見を Microsoft に直接送信し、改善を支援することもできます。
  
## <a name="see-also"></a>関連項目

[Office 365 で安全性のヒントを有効または無効にする](enable-or-disable-safety-tips.md)

