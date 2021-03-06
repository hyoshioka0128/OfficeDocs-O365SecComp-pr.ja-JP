---
title: セキュリティ/コンプライアンス センターと Exchange 管理センターでの DLP の動作
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: セキュリティ & コンプライアンスセンターの DLP が、Exchange 管理センターの DLP およびメールフロールール (トランスポートルール) とどのように連動するかについて説明します。
ms.openlocfilehash: 96fd329ce134b9a9c47b80b846ebb6050c855319
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077563"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>セキュリティ/コンプライアンス センターと Exchange 管理センターでの DLP の動作

Office 365 では、2つの異なる管理センターでデータ損失防止 (DLP) ポリシーを作成できます。
  
- **セキュリティ _AMP_ コンプライアンスセンター**では、SharePoint、OneDrive、Exchange、および Microsoft Teams のコンテンツを保護するための単一の DLP ポリシーを作成できます。 可能な場合は、ここで DLP ポリシーを作成することをお勧めします。 詳細については、「 [Security _AMP_ コンプライアンスセンターの DLP](data-loss-prevention-policies.md)」を参照してください。
    
- **Exchange 管理センター**では、exchange でのみコンテンツを保護できる DLP ポリシーを作成できます。 このポリシーでは、Exchange メールフロールール (トランスポートルールとも呼ばれます) を使用できるので、電子メールの処理に関するその他のオプションがあります。 詳細については、「 [Exchange 管理センターでの DLP](https://go.microsoft.com/fwlink/?linkid=852311)」を参照してください。
    
これらの管理センターで作成された DLP ポリシーは、並行して機能します。このトピックでは、その方法について説明します。
  
![セキュリティ/コンプライアンスセンターと Exchange 管理センターの DLP ページ](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>セキュリティ & コンプライアンスセンターの DLP が Exchange 管理センターの DLP およびメールフロールールとどのように連動するか

セキュリティ & コンプライアンスセンターで DLP ポリシーを作成すると、そのポリシーに含まれるすべての場所にポリシーが展開されます。 ポリシーに Exchange Online が含まれている場合は、Exchange 管理センターで作成された DLP ポリシーとまったく同じ方法でポリシーが同期され、適用されます。 
  
Exchange 管理センターで DLP ポリシーを作成した場合、これらのポリシーは、Security & コンプライアンスセンターで作成した電子メールのポリシーと共に引き続き機能します。 ただし、Exchange 管理センターで作成したルールは優先されることに注意してください。 最初にすべての Exchange メールフロールールが処理されてから、Security & コンプライアンスセンターの DLP ルールが処理されます。
  
これは、次のことを意味します。
  
- Exchange メールフロールールによってブロックされているメッセージは、Security & コンプライアンスセンターで作成された DLP ルールによってスキャンされることはありません。
    
- Exchange メールフロールールによって、外部ユーザーの追加など、Security & コンプライアンスセンターの DLP ポリシーに一致するようにメッセージが変更された場合、DLP ルールによって検出され、必要に応じてポリシーが適用されます。
    
また、"stop 処理" アクションを使用する Exchange メールフロールールは、セキュリティ & コンプライアンスセンターでの DLP ルールの処理には影響しません。ただし、これらは処理されます。
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>セキュリティ & コンプライアンスセンターおよび Exchange 管理センターのポリシーヒント

ポリシーヒントは、Exchange 管理センターで作成された DLP ポリシーとメールフロールール、または Security & コンプライアンスセンターで作成された DLP ポリシーによって動作しますが、両方を使用することはできません。 これは、これらのポリシーが異なる場所に格納されているため、ポリシーヒントは1つの場所からのみ描画できるからです。
  
Exchange 管理センターでポリシーヒントを構成した場合は、セキュリティ & コンプライアンスセンターで構成するポリシーヒントは、Exchange 管理センターのヒントをオフにするまで、Outlook on the web および Outlook 2013 以降のユーザーには表示されません。 これにより、セキュリティ & コンプライアンスセンターへの切り替えを選択するまでは、現在の Exchange メールフロールールが引き続き機能します。
  
ポリシーヒントは1つの場所からしか描画できませんが、セキュリティ & コンプライアンスセンターと Exchange 管理センターの両方で DLP ポリシーを使用している場合でも、電子メール通知は常に送信されることに注意してください。
  

