---
title: 迷惑メールとバルク メールの違い
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/7/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: お客様が迷惑メールとバルクメールメッセージの違いを askwhat ことがありますか。このトピックの目的は、Exchange Online と Exchange Online Protection (EOP) の両方で使用可能なさまざまなオプションについて説明し、その違いを説明することです。
ms.openlocfilehash: ee684fb079b11fd345eae6e2c8f5980fcbca5cb0
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598293"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>迷惑メールとバルク メールの違い

お客様から「迷惑メール メッセージとバルク メール メッセージの違いは何ですか」という質問を受けることがよくあります。このトピックの目的は、この違いを説明することと、Exchange Online と Exchange Online Protection (EOP) の両方で使用可能なさまざまなオプションに関する情報を提供することです。
  
 **迷惑メールとは何か**
  
迷惑メール メッセージは "スパム" メッセージで、サービスによってフィルター処理される未承諾 (かつ通常は不要な) 電子メール メッセージです。既定で、サービスは、送信元の IP アドレスの評価に基づいてスパム メッセージを拒否します。ただし、そのメッセージが IP 検査を通過しても、コンテンツ フィルターでスパムに分類された場合は、宛先になっている受信者の迷惑メール フォルダーに送信されます。 
  
> [!NOTE]
> 「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」に記載されているように、コンテンツ フィルター処理されたメッセージに対して実行されるアクションは、Exchange 管理センター (EAC) のコンテンツ フィルター ポリシーを介して構成することができます。また、スパム分類に同意できない場合は、「[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」に記載されているように、スパムまたは非スパムであると思われるメッセージをいくつかの方法で Microsoft に報告することができます。 
  
 **バルク メールとは何か**
  
グレー メールとも呼ばれるバルク メールは、分類がより困難な電子メール メッセージのことです。迷惑メールは「常にある脅威」であるのに対して、バルク メールは、通常、繰り返し送られてくるわけではない広告メッセージまたはマーケティング メッセージで構成されます。バルク メールは一部のユーザーによって要求されたものであり、事実、彼らは意図的にそれらのメッセージの受信を申し込んでいるのに対して、それ以外のユーザーはその種のメッセージをスパムと見なしています。たとえば、一部のユーザーは Contoso Corporation からの広告メールまたは次回のサイバー セキュリティに関するカンファレンスの招待状を受信したいと思っているのに対して、その他のユーザーはそのような電子メールをスパムと見なしている場合です。
  
## <a name="how-to-manage-bulk-email"></a>バルク メールの管理方法

バルク メールの管理方法は簡単に結論を出すことができません。すべてのバルク メールをスパムとして分類した場合は、そのメールを必要とするユーザーがそれに反対して、間違ってスパムにマークされた誤検知 (非スパム) メッセージとして提出する可能性があります。一方、すべてのバルク メールを通過させた場合は、そのメールを必要としないユーザーがそれに反対して、間違って受信トレイに到着した、見逃されたスパム メッセージ (偽陰性) として提出する可能性があります。
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a>コンテンツ フィルター ポリシーのバルク メールの秘密度の制御を有効にします。

バルクメールメッセージに関する会社のポリシーに応じて、管理者はバルクメールを割り当てるしきい値を選択できます。 この設定は、EAC のコンテンツフィルターポリシーを使用して構成できます。 手順については、「[スパムフィルターポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。 しきい値は1-9 から選択できます。1の場合、1はスパムとして最も多くのバルクメールをマークし、9では大量の電子メールを配信することができます。 その後、サービスは、メッセージを受信者の迷惑メールフォルダーに送信するなど、構成されたアクションを実行します。 
  

