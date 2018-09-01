---
title: Skype for Business Server の GDPR
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: ''
localization_priority: Priority
description: オンプレミスの Skype for Business Server および Lync Server での GDPR の要件に対応する方法について説明します。
ms.openlocfilehash: 0df47f05a7853414f84db1b3ef298de624a85fb3
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272522"
---
# <a name="gdpr-for-skype-for-business-server-and-lync-server"></a><span data-ttu-id="e76cb-103">Skype for Business Server および Lync Server の GDPR</span><span class="sxs-lookup"><span data-stu-id="e76cb-103">GDPR for Skype for Business Server and Lync Server</span></span>

<span data-ttu-id="e76cb-p101">Skype for Business Server および Lync Server のデータのほとんどは、Exchange Server に保存されます。それには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e76cb-p101">Most Skype for Business Server and Lync Server data is stored in Exchange Server. This includes:</span></span>

-   <span data-ttu-id="e76cb-106">会話の履歴</span><span class="sxs-lookup"><span data-stu-id="e76cb-106">Conversation history</span></span>

-   <span data-ttu-id="e76cb-107">ボイスメールの通知とトランスクリプション</span><span class="sxs-lookup"><span data-stu-id="e76cb-107">Voicemail notifications and transcriptions</span></span>

-   <span data-ttu-id="e76cb-108">会議の招待</span><span class="sxs-lookup"><span data-stu-id="e76cb-108">Meeting invites</span></span>

<span data-ttu-id="e76cb-109">[GDPR for Exchange Server](gdpr-for-exchange-server.md) について概要が示されている手順を使用して、GDPR 要求のこれらのデータ タイプを検索、エクスポート、削除します。</span><span class="sxs-lookup"><span data-stu-id="e76cb-109">Use the procedures outlined for [GDPR for Exchange Server](gdpr-for-exchange-server.md) to find, export, or delete these types of data for GDPR requests.</span></span>

<span data-ttu-id="e76cb-p102">連絡先リストは、SQL Server のデータベースに保存されます。それらは、次の方法でエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e76cb-p102">Contact lists are stored in the SQL Server database. They can be exported in the following ways:</span></span>

-   <span data-ttu-id="e76cb-p103">エンド ユーザー自身がグループ ヘッダーを右クリックして [コピー] を選択することにより、連絡先をエクスポートできます。この場合、そのグループのすべての連絡先がクリップボードにコピーされ、任意のアプリに貼り付けることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="e76cb-p103">End users themselves can export the contacts by right clicking the group header and selecting Copy. This will copy all the contacts in that group into the clipboard, which can then be pasted into any app.</span></span>

-   <span data-ttu-id="e76cb-114">[Export-CsUserData](https://docs.microsoft.com/ja-JP/powershell/module/skype/export-csuserdata) コマンドレットを使用することにより、このデータをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e76cb-114">You can use the [Export-CsUserData](https://docs.microsoft.com/ja-JP/powershell/module/skype/export-csuserdata) cmdlet to export this data.</span></span>

<span data-ttu-id="e76cb-p104">会議にアップロードされるコンテンツ (PowerPoint のファイルや配布資料など) または会議で生成されるコンテンツ (ホワイトボード、投票、Q/A など) は、ファイラーに保存されます。また、これらは、エンド ユーザーがまだ期限切れでない会議に再びログインして、アップロードされたコンテンツをダウンロードしたり、生成されたコンテンツの場合にはスクリーンショットを撮ってエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e76cb-p104">Content uploaded into meetings (such as PowerPoint files or handouts) or content generated in a meeting (such as whiteboard, polls, or Q/A) is stored in the filer. This can also be exported if end users log back into any meeting that has not expired and download any uploaded content or take screenshots in the case of generated content.</span></span>

<span data-ttu-id="e76cb-p105">Exchange の予定表および連絡先リストにない MeetNow 会議および連絡先権限 (家族や同僚など) は、ユーザー データベース内にあります。Lync Server 2013 以降の場合は、[Export-CsUserData](https://docs.microsoft.com/ja-JP/powershell/module/skype/export-csuserdata) コマンドレットを使用することにより、このデータをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e76cb-p105">MeetNow meetings that are not in the Exchange Calendar and Contact List and contact rights (family, co-worker, etc.) are in the User Database. In Lync Server 2013 and later, you can use the [Export-CsUserData](https://docs.microsoft.com/ja-JP/powershell/module/skype/export-csuserdata) cmdlet to export this data.</span></span>