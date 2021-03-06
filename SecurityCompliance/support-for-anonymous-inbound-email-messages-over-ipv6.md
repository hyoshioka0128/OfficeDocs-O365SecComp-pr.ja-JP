---
title: IPv6 経由の匿名受信電子メール メッセージのサポート
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: Exchange Online Protection および Exchange Online の IPv6 ソースからの匿名メッセージのサポートを構成する方法について説明します。
ms.openlocfilehash: b6b1a0f42d879929de5059b6e197bd5fe14887dc
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600730"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a>IPv6 経由の匿名受信電子メール メッセージのサポート

Exchange Online Protection (EOP) および Exchange Online は、トランスポート層セキュリティ (TLS) 経由でメッセージを送信しない送信者からの IPv6 通信経由の匿名受信電子メール メッセージの受信をサポートしています。 Microsoft 365 管理センターを開いて、[ [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home)**サポート**] をクリックし、[**新しいサービスリクエスト**] をクリックすることによって、IPv6 経由でメッセージを受信するようにオプトインできます。 IPv6 にオプトインしない場合は、引き続き、IPv4 経由でメッセージを受信することになります。
  
IPv6 経由でメッセージをサービスに送信する送信者は、次の 2 つの要件を満たす必要があります。
  
1. 送信 IPv6 アドレスに有効な PTR レコード (送信 IPv6 アドレスの [DNS 逆引きレコード](https://en.wikipedia.org/wiki/Reverse_DNS_lookup)) を含める必要があります。 
    
2. また、送信者は、SPF 検証 ([RFC 7208](https://tools.ietf.org/html/rfc7208) で既定されている) と [DKIM 検証](http://dkim.org/) ( [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) で既定されている) のどちらかに合格する必要があります。
    
これらの要件は、どの構成を使用する場合でも IPv6 にオプトインする前に満たす必要があります。両方の要件が満たされている場合、メッセージはサービスによって提供される通常の電子メール メッセージ フィルタリングを通過します。どちらかの要件が満たされていない場合には、メッセージは次の 450 応答のいずれかで拒否されます。
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
IPv6 経由でメッセージを受信するためにオプトインしていない状態で、送信者がメール サーバーに手動で接続することによって IPv6 経由のメッセージを強制しようとした場合には、メッセージは次のような 550 応答で拒否されます。
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a>関連情報

[DKIM 署名付きメッセージの検証をサポートする](support-for-validation-of-dkim-signed-messages.md)
  

