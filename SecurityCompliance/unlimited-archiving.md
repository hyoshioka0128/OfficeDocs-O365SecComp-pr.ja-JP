---
title: Office 365 での無制限アーカイブの概要
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Exchange Online メールボックスに無制限のアーカイブ記憶域を提供する Office 365 の自動拡張アーカイブについて説明します。
ms.openlocfilehash: 9b63bcd7cbf8c1cef8df336553debdbf7af2ba12
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158069"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a>Office 365 での無制限アーカイブの概要

Office 365 のアーカイブ メールボックスは、ユーザーに追加のメールボックス記憶領域を提供します。 ユーザーのアーカイブ メールボックスを有効にすると、最大 100 GB の追加記憶域を使用できます。 100 GB の記憶域クォータに達したとき、組織は、Microsoft に問い合わせてアーカイブ メールボックス用の追加記憶領域を要求する必要がありました。 このようなことはもうなくなります。 Office 365 の新しい無制限アーカイブ機能 (*自動拡張アーカイブと呼ばれる*) は、アーカイブ メールボックスで無制限の記憶域を提供します。 アーカイブ メールボックスの記憶域クォータに達した場合、Office 365 はアーカイブのサイズを自動的に増やします。これにより、ユーザーはメールボックスの記憶領域を使い切ることがなくなり、管理者はアーカイブ メールボックス用の追加記憶域を要求する必要がなくなります。
  
自動拡張アーカイブを有効にする詳しい手順については、「[Office 365 で無制限アーカイブを有効にする](enable-unlimited-archiving.md)」を参照してください。
  
> [!NOTE]
> アーカイブの自動拡張では、共有メールボックスもサポートされます。 共有メールボックスのアーカイブを有効にするには、Exchange Online プラン 2 のライセンス、または Exchange Online Archiving のライセンスの付いた Exchange Online プラン 1 のライセンスが必要です。 
  
## <a name="how-auto-expanding-archiving-works"></a>自動拡張アーカイブのしくみ

前に説明したように、ユーザーのアーカイブ メールボックスが有効になっていると、追加のメールボックス記憶領域が作成されます。 自動拡張アーカイブを有効にすると、Office 365 は定期的にアーカイブ メールボックスのサイズを確認します。 アーカイブ メールボックスが記憶域の制限に近づくと、Office 365 はアーカイブに対する追加の記憶領域を自動的に作成します。 ユーザーがこの追加記憶領域を使い切ると、Office 365 はユーザーのアーカイブの記憶領域をさらに追加します。 この処理は自動的に行われるので、管理者は追加のアーカイブ記憶域を要求したり、自動拡張アーカイブを管理したりする必要はありません。 
  
処理の概要は次のとおりです。
  
![自動拡張アーカイブ プロセスの概要](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. ユーザーのメールボックスまたは共有のメールボックスに対してアーカイブが有効になります。 100 GB の記憶領域を持つアーカイブ メールボックスが作成され、アーカイブ メールボックスの警告のクォータが 90 GB に設定されます。
    
2. 管理者がメールボックスの自動拡張アーカイブを有効にします。 次に、アーカイブ メールボックス ([回復可能なアイテム] フィルダーを含む) が 90 GB に達すると、自動拡張アーカイブに変換されて、Office 365 はアーカイブに記憶領域を追加します。 追加の記憶領域がプロビジョニングされるには、最大 30 日かかる場合があります。
    
3. Office 365 は、必要に応じて自動的にアーカイブにさらに記憶領域を追加します。
  
> [!IMPORTANT]
> メールボックスが保留にされているか、Office 365 のアイテム保持ポリシーに割り当てられている場合は、自動拡張アーカイブを有効にするとアーカイブ メールボックスの記憶領域のクォータが 110 GB に増やされます。 同様に、アーカイブ警告クォータは、100 GB に増やされます。

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>追加のアーカイブ記憶領域に移動されるもの

自動拡張アーカイブ記憶域を効率的に使用するために、フォルダーは移動される場合があります。 Office 365 では、追加記憶域がアーカイブに追加されたときに、どのフォルダーを移動するかを決定します。 フォルダーが移動されると、Outlook のフォルダー一覧のアーカイブ部分の元のフォルダーの下にサブフォルダーが自動的に作成されます。 この新しいサブフォルダーは、移動されたアイテムを参照します。 Office 365 は、このフォルダーに **\<フォルダー名\>_yyyy (作成日: mmm dd、yyyy h_mm)** という名前を付けます。 
  
- **yyyy** は、フォルダー内のメッセージが受信された年です。 
    
- **mmm dd, yyyy h_m** は、Office 365 によってサブフォルダーが作成された日時 (UTC 形式) であり、Outlook でのユーザーのタイム ゾーンと地域の設定に基づきます。 
    
次のスクリーンショットは、メッセージが自動拡張アーカイブに移動される前と後のフォルダー一覧です。
  
 **追加記憶域が追加される前**
  
![自動拡張アーカイブがプロビジョニングされる前のアーカイブ メールボックスのフォルダー一覧](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 **追加記憶域が追加された後**
  
![自動拡張アーカイブがプロビジョニングされた後のアーカイブ メールボックスのフォルダー一覧](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>自動拡張アーカイブ内のアイテムにアクセスするための Outlook の要件

自動拡張アーカイブに保存されているメッセージにアクセスするには、ユーザーは次のいずれかの Outlook クライアントを使う必要があります。
  
- Windows 版の Outlook 2016、Outlook 2019
    
- Outlook on the web 
    
- Mac 版の Outlook 2016、Outlook 2019 
    
> [!NOTE]
> Outlook 2013 ユーザーは、アーカイブ メールボックスにもともと保存されていたアイテムのみにアクセスできます。 追加アーカイブ記憶域に移動されたアイテムにはアクセスできません。 
  
Outlook または Outlook on the web を使って自動拡張アーカイブに保存されているメッセージにアクセスするときは、いくつかのことを考慮する必要があります。
  
- 自動拡張記憶域に移動されたものも含め、アーカイブ メールボックスの任意のフォルダーにアクセスできます。
    
- フォルダー自体を検索することによってのみ、追加記憶域に移動されたアイテムを検索できます。 つまり、フォルダー一覧でアーカイブ フォルダーを選び、検索範囲として [**現在の​​フォルダー**] オプションを選ぶ必要があります。 同様に、自動拡張記憶域内のフォルダーにサブフォルダーがある場合は、各サブフォルダーを個別に検索する必要があります。 
    
- 自動拡張アーカイブ内の Outlook のアイテム数および閲覧済み/未読数 (Outlook および Outlook on the web) は正しくないことがあります。
    
- 自動拡張記憶域を参照しているサブフォルダー内のアイテムを削除することはできますが、フォルダー自体を削除することはできません。
    
- [削除済みアイテムを復元] 機能を使って、自動拡張記憶域から削除されたアイテムを復元することはできません。
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a>自動拡張アーカイブと Office 365 のその他の法令遵守機能

ここでは、自動拡張アーカイブと、Office 365 のその他の法令遵守およびデータ ガバナンス機能の間の機能について説明します。
  
- **電子情報開示** - コンテンツ検索やインプレース電子情報開示などの Office 365 の電子情報開示ツールを使うと、自動拡張アーカイブ内の追加記憶域も検索されます。
    
- **保持** - Exchange Online の訴訟ホールドや、のセキュリティ/コンプライアンス センターの電子情報開示ケースの保留リストと保持ポリシーなどのツールを使ってメールボックスを保留にすると、自動拡張アーカイブ内のコンテンツも保留になります。
    
- **メッセージング レコード管理 (MRM)** - Exchange Online の MRM 削除ポリシーを使って期限切れのメールボックス アイテムを完全に削除した場合、自動拡張アーカイブにある期限切れアイテムも削除されます。
    
- **インポート サービス** - Office 365 のインポート サービスを使うと、ユーザーの自動拡張アーカイブに PST ファイルをインポートできます。 PST ファイルの最大 100 GB のデータをユーザーのアーカイブ メールボックスにインポートできます。 

## <a name="more-information"></a>詳細情報

自動拡張アーカイブについての技術的な詳細については、「[Office 365: 自動拡張アーカイブに関する FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)」を参照してください。