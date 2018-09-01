---
title: Office 365 でのデータの保持、削除、および破棄
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Office 365 データの保存、削除、および破棄に関するマイクロソフトのポリシーの概要について説明します。
ms.openlocfilehash: 4d952058df8d0efb664f23e5495796fdb9e006f2
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531908"
---
# <a name="data-retention-deletion-and-destruction-in-office-365"></a><span data-ttu-id="22f59-103">Office 365 でのデータの保持、削除、および破棄</span><span class="sxs-lookup"><span data-stu-id="22f59-103">Data Retention, Deletion, and Destruction in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="22f59-104">概要</span><span class="sxs-lookup"><span data-stu-id="22f59-104">Introduction</span></span>
<span data-ttu-id="22f59-p101">マイクロソフトでは、削除した後、顧客データの保存期間を指定する Office 365 のデータ処理標準的なポリシーがあります。一般に、Office 365 内では、お客様のデータが削除される 2 つのシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="22f59-p101">Microsoft has a Data Handling Standard policy for Office 365 that specifies how long customer data will be retained after being deleted. Generally, within Office 365, there are two scenarios in which customer data is deleted:</span></span>
- <span data-ttu-id="22f59-107">**アクティブな削除**でユーザーがデータを削除または、アクティブなテナントの管理者がそのユーザーを削除した後、ユーザーのプライベート データを削除します。</span><span class="sxs-lookup"><span data-stu-id="22f59-107">**Active Deletion** - A user deletes data, or data private to a user is deleted after that user is deleted by the administrator of an active tenant.</span></span>
- <span data-ttu-id="22f59-108">**パッシブ削除**- テナント サブスクリプションを終了します。</span><span class="sxs-lookup"><span data-stu-id="22f59-108">**Passive Deletion** - The tenant subscription ends.</span></span>

<span data-ttu-id="22f59-p102">マイクロソフトの Office 365 のデータ処理標準のポリシーでは、これらのシナリオでのデータの保存期間を指定します。次のセクションでは、(マイクロソフトの Office 365 資産分類標準に基づく) のデータとシナリオのアクティブおよびパッシブの削除の保存期間のカテゴリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="22f59-p102">Microsoft's Data Handling Standard policy for Office 365 specifies how long data will be retained in each of these scenarios. The following sections describe the categories of data (based on Microsoft's Office 365 Asset Classification Standard) and the retention periods for active and passive deletion scenarios.</span></span>

## <a name="active-deletion-retention"></a><span data-ttu-id="22f59-111">アクティブな削除の保存期間</span><span class="sxs-lookup"><span data-stu-id="22f59-111">Active Deletion Retention</span></span>

| <span data-ttu-id="22f59-112">データのカテゴリ</span><span class="sxs-lookup"><span data-stu-id="22f59-112">Data Category</span></span> | <span data-ttu-id="22f59-113">以上を保持します。</span><span class="sxs-lookup"><span data-stu-id="22f59-113">Retain at Least</span></span> | <span data-ttu-id="22f59-114">最大を保持します。</span><span class="sxs-lookup"><span data-stu-id="22f59-114">Retain at Most</span></span> |
|---------------------------------------|:-----------------:|:-----------------:|:----------------------------------:|:-------------------------------:|
| <span data-ttu-id="22f59-115">コントロールのデータへのアクセス</span><span class="sxs-lookup"><span data-stu-id="22f59-115">Access Control Data</span></span> | <span data-ttu-id="22f59-116">該当なし</span><span class="sxs-lookup"><span data-stu-id="22f59-116">N/A</span></span> | <span data-ttu-id="22f59-117">該当なし</span><span class="sxs-lookup"><span data-stu-id="22f59-117">N/A</span></span> |
| <span data-ttu-id="22f59-118">お客様のコンテンツ</span><span class="sxs-lookup"><span data-stu-id="22f59-118">Customer Content</span></span> | <span data-ttu-id="22f59-119">7 日</span><span class="sxs-lookup"><span data-stu-id="22f59-119">7 days</span></span> | <span data-ttu-id="22f59-120">30 日</span><span class="sxs-lookup"><span data-stu-id="22f59-120">30 days</span></span> |
| <span data-ttu-id="22f59-121">エンドユーザーを特定できる情報</span><span class="sxs-lookup"><span data-stu-id="22f59-121">End User Identifiable Information</span></span> | <span data-ttu-id="22f59-122">90 日</span><span class="sxs-lookup"><span data-stu-id="22f59-122">90 days</span></span> | <span data-ttu-id="22f59-123">180 日</span><span class="sxs-lookup"><span data-stu-id="22f59-123">180 days</span></span> |
| <span data-ttu-id="22f59-124">アカウント データ</span><span class="sxs-lookup"><span data-stu-id="22f59-124">Account Data</span></span> | <span data-ttu-id="22f59-125">1 年</span><span class="sxs-lookup"><span data-stu-id="22f59-125">1 year</span></span> | <span data-ttu-id="22f59-126">3 年間</span><span class="sxs-lookup"><span data-stu-id="22f59-126">3 years</span></span> |
| <span data-ttu-id="22f59-127">組織を特定できる情報</span><span class="sxs-lookup"><span data-stu-id="22f59-127">Organization Identifiable Information</span></span> | <span data-ttu-id="22f59-128">90 日</span><span class="sxs-lookup"><span data-stu-id="22f59-128">90 days</span></span> | <span data-ttu-id="22f59-129">180 日</span><span class="sxs-lookup"><span data-stu-id="22f59-129">180 days</span></span> |
| <span data-ttu-id="22f59-130">システムのメタデータ</span><span class="sxs-lookup"><span data-stu-id="22f59-130">System Metadata</span></span> | <span data-ttu-id="22f59-131">セキュリティ ログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="22f59-131">See Security Logs</span></span> | <span data-ttu-id="22f59-132">セキュリティ ログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="22f59-132">See Security Logs</span></span> |
| <span data-ttu-id="22f59-133">セキュリティ ログ</span><span class="sxs-lookup"><span data-stu-id="22f59-133">Security Logs</span></span> | <span data-ttu-id="22f59-134">最小 1 年間</span><span class="sxs-lookup"><span data-stu-id="22f59-134">Min 1 year</span></span> | <span data-ttu-id="22f59-135">最大 1 年間</span><span class="sxs-lookup"><span data-stu-id="22f59-135">Max 1 year</span></span> |
| <span data-ttu-id="22f59-136">Exchange Online Archiving のログ</span><span class="sxs-lookup"><span data-stu-id="22f59-136">Exchange Online Archiving Logs</span></span> | <span data-ttu-id="22f59-137">3 年間の最小値</span><span class="sxs-lookup"><span data-stu-id="22f59-137">Min 3 years</span></span> | <span data-ttu-id="22f59-138">最大 3 年間</span><span class="sxs-lookup"><span data-stu-id="22f59-138">Max 3 years</span></span> |

## <a name="passive-deletion-retention"></a><span data-ttu-id="22f59-139">パッシブ削除の保存期間</span><span class="sxs-lookup"><span data-stu-id="22f59-139">Passive Deletion Retention</span></span>

| <span data-ttu-id="22f59-140">データのカテゴリ</span><span class="sxs-lookup"><span data-stu-id="22f59-140">Data Category</span></span> | <span data-ttu-id="22f59-141">以上を保持します。</span><span class="sxs-lookup"><span data-stu-id="22f59-141">Retain at Least</span></span> | <span data-ttu-id="22f59-142">最大を保持します。</span><span class="sxs-lookup"><span data-stu-id="22f59-142">Retain at Most</span></span> |
|---------------------------------------|:-----------------:|:-----------------:|:----------------------------------:|:-------------------------------:|
| <span data-ttu-id="22f59-143">コントロールのデータへのアクセス</span><span class="sxs-lookup"><span data-stu-id="22f59-143">Access Control Data</span></span> | <span data-ttu-id="22f59-144">(コンテンツ ・ リカバリ) の 90 日間</span><span class="sxs-lookup"><span data-stu-id="22f59-144">90 days (for content recovery)</span></span> | <span data-ttu-id="22f59-145">(コンテンツ ・ リカバリ) の 180 日間</span><span class="sxs-lookup"><span data-stu-id="22f59-145">180 days (for content recovery)</span></span> |
| <span data-ttu-id="22f59-146">お客様のコンテンツ</span><span class="sxs-lookup"><span data-stu-id="22f59-146">Customer Content</span></span> | <span data-ttu-id="22f59-147">90 日間 (機能制限付きアカウント)</span><span class="sxs-lookup"><span data-stu-id="22f59-147">90 days (limited-function account)</span></span> | <span data-ttu-id="22f59-148">180 日</span><span class="sxs-lookup"><span data-stu-id="22f59-148">180 days</span></span> |
| <span data-ttu-id="22f59-149">エンドユーザーを特定できる情報</span><span class="sxs-lookup"><span data-stu-id="22f59-149">End User Identifiable Information</span></span> | <span data-ttu-id="22f59-150">90 日</span><span class="sxs-lookup"><span data-stu-id="22f59-150">90 days</span></span> | <span data-ttu-id="22f59-151">180 日</span><span class="sxs-lookup"><span data-stu-id="22f59-151">180 days</span></span> |
| <span data-ttu-id="22f59-152">アカウント データ</span><span class="sxs-lookup"><span data-stu-id="22f59-152">Account Data</span></span> | <span data-ttu-id="22f59-153">1 年</span><span class="sxs-lookup"><span data-stu-id="22f59-153">1 year</span></span> | <span data-ttu-id="22f59-154">3 年間</span><span class="sxs-lookup"><span data-stu-id="22f59-154">3 years</span></span> |
| <span data-ttu-id="22f59-155">組織を特定できる情報</span><span class="sxs-lookup"><span data-stu-id="22f59-155">Organization Identifiable Information</span></span> | <span data-ttu-id="22f59-156">90 日</span><span class="sxs-lookup"><span data-stu-id="22f59-156">90 days</span></span> | <span data-ttu-id="22f59-157">180 日</span><span class="sxs-lookup"><span data-stu-id="22f59-157">180 days</span></span> |
| <span data-ttu-id="22f59-158">システムのメタデータ</span><span class="sxs-lookup"><span data-stu-id="22f59-158">System Metadata</span></span> | <span data-ttu-id="22f59-159">セキュリティ ログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="22f59-159">See Security Logs</span></span> | <span data-ttu-id="22f59-160">セキュリティ ログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="22f59-160">See Security Logs</span></span> |
| <span data-ttu-id="22f59-161">セキュリティ ログ</span><span class="sxs-lookup"><span data-stu-id="22f59-161">Security Logs</span></span> | <span data-ttu-id="22f59-162">最小 1 年間</span><span class="sxs-lookup"><span data-stu-id="22f59-162">Min 1 year</span></span> | <span data-ttu-id="22f59-163">最大 1 年間</span><span class="sxs-lookup"><span data-stu-id="22f59-163">Max 1 year</span></span> |
| <span data-ttu-id="22f59-164">Exchange Online Archiving のログ</span><span class="sxs-lookup"><span data-stu-id="22f59-164">Exchange Online Archiving Logs</span></span> | <span data-ttu-id="22f59-165">3 年間の最小値</span><span class="sxs-lookup"><span data-stu-id="22f59-165">Min 3 years</span></span> | <span data-ttu-id="22f59-166">最大 3 年間</span><span class="sxs-lookup"><span data-stu-id="22f59-166">Max 3 years</span></span> |

## <a name="subscription-rentention"></a><span data-ttu-id="22f59-167">サブスクリプションの保持</span><span class="sxs-lookup"><span data-stu-id="22f59-167">Subscription Rentention</span></span>

<span data-ttu-id="22f59-168">お客様のコンテンツがオンラインの Exchange メールボックスの内容として定義されている (本文、予定表エントリ、および電子メールの添付ファイルの内容を電子メールで送信し、該当する場合、ビジネス ・ コンテンツの Skype)、SharePoint Online サイトのコンテンツおよびサイト内で、格納されているファイルとファイル企業またはビジネス用の Skype の OneDrive にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="22f59-168">Customer content is defined as Exchange Online mailbox content (email body, calendar entries, and the content of email attachments, and if applicable, Skype for Business content), SharePoint Online site content and the files stored within sites, and files uploaded to OneDrive for Business or Skype for Business.</span></span>

<span data-ttu-id="22f59-p103">サブスクリプションの期間中にすべての回で、サブスクライバーにアクセスでき、Office 365 に格納されている顧客データを抽出します。無料評価版と LinkedIn のサービスを除いては、マイクロソフトは、顧客データが格納されている Office 365 の機能制限付きアカウントで 90 日の有効期限切れや、データを抽出するサブスクライバーを有効にするサブスクリプションの終了後を保持します。(無料の試用期間の場合は試用版の期限が切れると、そのアイテムに移動猶予期間では、Office 365 を購入する (ほとんどの国や地域で試行をほとんど) の 30 日間を提供します。Office 365 を購入することを決定する場合、試用版の有効期限を使用したり、キャンセルできます。30 日の猶予期間後すぐに、試用版のアカウント情報とデータが完全に消去されます。)</span><span class="sxs-lookup"><span data-stu-id="22f59-p103">At all times during the term of a subscription, a subscriber can access and extract customer data stored in Office 365. Except for free trials and LinkedIn services, Microsoft retains customer data stored in Office 365 in a limited-function account for 90 days after the expiration or termination of the subscription to enable the subscriber to extract the data. (In the case of a free trial, when the trial expires, it moves into a grace period, giving you 30 days (for most trials, in most countries and regions) to purchase Office 365. If you decide not to buy Office 365, you can let your trial expire or cancel it. Soon after the 30-day grace period, your trial account information and data is permanently erased.)</span></span>

<span data-ttu-id="22f59-p104">90 日の保存期間の終了後、マイクロソフトはアカウントを無効にし、顧客データを削除します。有効期限切れや、Office 365 のサブスクリプションの終了後、180 日間以内マイクロソフトがアカウントを無効にしてアカウントからすべての顧客データを削除します。データの最大保存期間が経過すると商業的に回復不可能なデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="22f59-p104">After the 90-day retention period ends, Microsoft disables the account and deletes the customer data. No more than 180 days after expiration or termination of a subscription to Office 365, Microsoft will disable the account and delete all customer data from the account. Once the maximum retention period for any data has elapsed, the data is rendered commercially unrecoverable.</span></span>

<span data-ttu-id="22f59-p105">リサイクルおよび廃棄のディスク ・ ドライブとサーバーの障害が発生したか、削除に対応するデータ処理標準的なポリシーもあります。Office 365 内で任意のディスク ・ ドライブで再使用する前に、マイクロソフトは NIST SP 800-88 に準拠している物理的な校正プロセスを実行します。オンサイトに破棄されているディスクを含むデータ センター内で実行される物理的な破壊処理を使用するディスク ・ ドライブを再利用することはできませんが破棄されます。これらの手順は、マイクロソフトのクラウド インフラストラクチャと運用 (MCIO) によって実行されます。詳細については、MCIO の監査[サービスを信頼のプレビュー](https://aka.ms/STP)でレポートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="22f59-p105">Microsoft also has a Data Handling Standard policy that addresses the recycling and disposal of disk drives and failed or retiring servers. Before re-using any disk drives within Office 365, Microsoft performs a physical sanitization process that is compliant with NIST SP 800-88. Disk drives that cannot be re-used are disposed of using a physical destruction process that is performed on-site within the datacenter containing the disks being destroyed. These procedures are performed by Microsoft Cloud Infrastructure & Operations (MCIO). For more information, see the MCIO audit reports on the [Service Trust Preview](https://aka.ms/STP).</span></span>

## <a name="expedited-deletion"></a><span data-ttu-id="22f59-182">迅速な削除</span><span class="sxs-lookup"><span data-stu-id="22f59-182">Expedited Deletion</span></span>
<span data-ttu-id="22f59-p106">サブスクリプションの期間中に常に、サブスクライバーはマイクロソフトのサポート、および要求を促進するサブスクリプションのプロビジョニング解除を連絡できます。このプロセスでは、SharePoint online 日、Exchange Online で可能性のあるデータを含む、すべてのユーザー データを保持または削除済みの 3 日間、管理者が Microsoft が提供するロックアウト コードを入力した後では、非アクティブなメールボックスに格納されています。迅速なプロビジョニング解除の詳細については、 [Office 365 のキャンセル](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22f59-p106">At all times during the term of a subscription, a subscriber can contact Microsoft Support and request expedited subscription deprovisioning. In this process, all user data, including data in SharePoint Online, Exchange Online that may be under hold or stored in inactive mailboxes, is deleted three days after the administrator enters the lockout code provided by Microsoft. For more information on expedited deprovisioning, see [Cancel Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a).</span></span>

## <a name="related-links"></a><span data-ttu-id="22f59-186">関連リンク</span><span class="sxs-lookup"><span data-stu-id="22f59-186">Related Links</span></span>
- [<span data-ttu-id="22f59-187">Exchange Online でのデータ削除</span><span class="sxs-lookup"><span data-stu-id="22f59-187">Exchange Online Data Deletion</span></span>](/office365/enterprise/office-365-exchange-online-data-deletion)
- [<span data-ttu-id="22f59-188">SharePoint Online でのデータ削除</span><span class="sxs-lookup"><span data-stu-id="22f59-188">SharePoint Online Data Deletion</span></span>](/office365/enterprise/office-365-sharepoint-online-data-deletion)
- [<span data-ttu-id="22f59-189">Skype for Business でのデータ削除</span><span class="sxs-lookup"><span data-stu-id="22f59-189">Skype for Business Data Deletion</span></span>](/office365/enterprise/office-365-skype-data-deletion)
- [<span data-ttu-id="22f59-190">Office 365 での不変性</span><span class="sxs-lookup"><span data-stu-id="22f59-190">Immutability in Office 365</span></span>](/office365/enterprise/office-365-data-immutability)
- [<span data-ttu-id="22f59-191">データの破棄</span><span class="sxs-lookup"><span data-stu-id="22f59-191">Data Destruction</span></span>](/office365/enterprise/office-365-data-destruction)