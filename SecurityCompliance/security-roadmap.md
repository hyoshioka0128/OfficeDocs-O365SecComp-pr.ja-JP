---
title: Office 365 のセキュリティ ロードマップの最初の 30 日、90 日間での内外の最優先事項
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 'Office 365 環境を保護するセキュリティ機能を実装するためのマイクロソフトの cybersecurity のチームからの推奨事項です。 '
ms.openlocfilehash: 714f2a9c8c2883ee954f6d74eb20db01114c62a7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013731"
---
# <a name="office-365-security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a><span data-ttu-id="9eacc-103">Office 365 のセキュリティ ロードマップの最初の 30 日、90 日間での内外の最優先事項</span><span class="sxs-lookup"><span data-stu-id="9eacc-103">Office 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond</span></span>

<span data-ttu-id="9eacc-p101">この資料には、Office 365 環境を保護するセキュリティ機能を実装するためのマイクロソフトの cybersecurity のチームからの推奨事項が含まれています。出典: マイクロソフトの Ignite セッションから- [pro の cybersecurity のように Office 365 のセキュリティで保護された: 最初の 30 日、90 日間での内外の優先順位のトップ](https://www.youtube.com/watch?v=luignzNyR-o)。このセッションが開発され、マーク Simos と Matt Kemelhar、企業の Cybersecurity の設計者によって提示されます。</span><span class="sxs-lookup"><span data-stu-id="9eacc-p101">This article includes top recommendations from Microsoft's cybersecurity team for implementing security capabilities to protect your Office 365 environment. This article is adapted from a Microsoft Ignite session — [Secure Office 365 like a cybersecurity pro: Top priorities for the first 30 days, 90 days, and beyond](https://www.youtube.com/watch?v=luignzNyR-o). This session was developed and presented by Mark Simos and Matt Kemelhar, Enterprise Cybersecurity Architects.</span></span>
  
<span data-ttu-id="9eacc-107">この記事の内容</span><span class="sxs-lookup"><span data-stu-id="9eacc-107">In this article:</span></span>
  
- [<span data-ttu-id="9eacc-108">ロードマップの結果</span><span class="sxs-lookup"><span data-stu-id="9eacc-108">Roadmap outcomes</span></span>](security-roadmap.md#Roadmap)
    
- [<span data-ttu-id="9eacc-109">30 日-強力な短期</span><span class="sxs-lookup"><span data-stu-id="9eacc-109">30 days — powerful quick wins</span></span>](security-roadmap.md#Thirdaydays)
    
- [<span data-ttu-id="9eacc-110">90 日間、保護を強化</span><span class="sxs-lookup"><span data-stu-id="9eacc-110">90 days — enhanced protections</span></span>](security-roadmap.md#Ninetydays)
    
- [<span data-ttu-id="9eacc-111">を超えて</span><span class="sxs-lookup"><span data-stu-id="9eacc-111">Beyond</span></span>](security-roadmap.md#Beyond)
    
## <a name="roadmap-outcomes"></a><span data-ttu-id="9eacc-112">ロードマップの結果</span><span class="sxs-lookup"><span data-stu-id="9eacc-112">Roadmap outcomes</span></span>
<span data-ttu-id="9eacc-113"><a name="Roadmap"> </a></span><span class="sxs-lookup"><span data-stu-id="9eacc-113"></span></span>

<span data-ttu-id="9eacc-114">これらのロードマップの推奨事項は、次の要件を論理的な順序で 3 つのフェーズにわたってがステージングされます。</span><span class="sxs-lookup"><span data-stu-id="9eacc-114">These roadmap recommendations are staged across three phases in a logical order with the following goals.</span></span>

|||
|:-----|:-----|
| |<span data-ttu-id="9eacc-115">成果</span><span class="sxs-lookup"><span data-stu-id="9eacc-115">Outcomes</span></span>
|<span data-ttu-id="9eacc-116">30 日</span><span class="sxs-lookup"><span data-stu-id="9eacc-116">30 days</span></span>|<span data-ttu-id="9eacc-117">迅速に構成します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-117">Rapid configuration:</span></span>  <br/> <span data-ttu-id="9eacc-118">• 管理の基本的な保護</span><span class="sxs-lookup"><span data-stu-id="9eacc-118">•   Basic admin protections</span></span>  <br/> <span data-ttu-id="9eacc-119">• ログの記録および分析</span><span class="sxs-lookup"><span data-stu-id="9eacc-119">•   Logging and analytics</span></span>  <br/> <span data-ttu-id="9eacc-120">• 基本的な id の保護</span><span class="sxs-lookup"><span data-stu-id="9eacc-120">•   Basic identity protections</span></span>  <br/> <span data-ttu-id="9eacc-121">テナント構成</span><span class="sxs-lookup"><span data-stu-id="9eacc-121">Tenant configuration</span></span>  <br/>  <span data-ttu-id="9eacc-122">利害関係者を準備します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-122">Prepare stakeholders</span></span>  <br/> |
|<span data-ttu-id="9eacc-123">90 日</span><span class="sxs-lookup"><span data-stu-id="9eacc-123">90 days</span></span>|<span data-ttu-id="9eacc-124">高度な保護。</span><span class="sxs-lookup"><span data-stu-id="9eacc-124">Advanced protections:</span></span>  <br/> <span data-ttu-id="9eacc-125">• 管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="9eacc-125">•   Admin accounts</span></span>  <br/>  <span data-ttu-id="9eacc-126">• データ&amp;ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="9eacc-126">•   Data &amp; user accounts</span></span>  <br/>  <span data-ttu-id="9eacc-127">コンプライアンス、脅威、およびユーザーのニーズの把握</span><span class="sxs-lookup"><span data-stu-id="9eacc-127">Visibility into compliance, threat, and user needs</span></span>  <br/>  <span data-ttu-id="9eacc-128">適応し、既定のポリシーおよび保護機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-128">Adapt and implement default policies and protections</span></span>  <br/> |
|<span data-ttu-id="9eacc-129">を超えて</span><span class="sxs-lookup"><span data-stu-id="9eacc-129">Beyond</span></span>|<span data-ttu-id="9eacc-130">調整し、キーのポリシーおよび制御を調整します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-130">Adjust and refine key policies and controls</span></span>  <br/> <span data-ttu-id="9eacc-131">設置型の依存関係への保護機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-131">Extend protections to on-premises dependencies</span></span>  <br/> <span data-ttu-id="9eacc-132">(法務、内部からの脅威など) は、ビジネスおよびセキュリティのプロセスとの統合します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-132">Integrate with business and security processes (legal, insider threat, etc.)</span></span>  <br/> |
  

   
## <a name="30-days--powerful-quick-wins"></a><span data-ttu-id="9eacc-133">30 日-強力な短期</span><span class="sxs-lookup"><span data-stu-id="9eacc-133">30 days — powerful quick wins</span></span>
<span data-ttu-id="9eacc-134"><a name="Thirdaydays"> </a></span><span class="sxs-lookup"><span data-stu-id="9eacc-134"></span></span>

<span data-ttu-id="9eacc-135">これらのタスクは、迅速に行うことができ、ユーザーに影響が少ない。</span><span class="sxs-lookup"><span data-stu-id="9eacc-135">These tasks can be accomplished quickly and have low impact to users.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9eacc-136">領域</span><span class="sxs-lookup"><span data-stu-id="9eacc-136">Area</span></span>  <br/> |<span data-ttu-id="9eacc-137">タスク</span><span class="sxs-lookup"><span data-stu-id="9eacc-137">Tasks</span></span>  <br/> |
|<span data-ttu-id="9eacc-138">セキュリティの管理</span><span class="sxs-lookup"><span data-stu-id="9eacc-138">Security management</span></span>  <br/> |<span data-ttu-id="9eacc-139">• は、セキュリティで保護されたスコアを確認し、注意してください、現在のスコアの ( [https://securescore.office.com](https://securescore.office.com))。</span><span class="sxs-lookup"><span data-stu-id="9eacc-139">•   Check Secure Score and take note of your current score ( [https://securescore.office.com](https://securescore.office.com)).</span></span>  <br/>  <span data-ttu-id="9eacc-p102">• は、Office 365 の監査ログを有効にします。参照してください[では、Office 365 のセキュリティ監査ログを検索する&amp;コンプライアンス センター](search-the-audit-log-in-security-and-compliance.md)です。</span><span class="sxs-lookup"><span data-stu-id="9eacc-p102">•   Turn on audit logging for Office 365. See [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).  </span></span><br/> <span data-ttu-id="9eacc-142">•[セキュリティ強化のため、Office 365 のテナントを構成](tenant-wide-setup-for-increased-security.md)します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-142">•   [Configure your Office 365 tenant for increased security](tenant-wide-setup-for-increased-security.md) .</span></span>  <br/>  <span data-ttu-id="9eacc-143">• は、ダッシュ ボードおよびレポートでは、Office 365 のセキュリティとコンプライアンス センターおよびクラウド アプリケーションのセキュリティを定期的に確認します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-143">•   Regularly review dashboards and reports in the Office 365 Security and Compliance Center and Cloud App Security.</span></span>  <br/> |
|<span data-ttu-id="9eacc-144">脅威保護</span><span class="sxs-lookup"><span data-stu-id="9eacc-144">Threat protection</span></span>  <br/> |<span data-ttu-id="9eacc-p103">脅威の検出の既定のポリシーを使用して、異常な動作の監視を開始するのには[マイクロソフトのクラウド アプリケーションのセキュリティに Office 365 を接続](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)をします。異常検出の基準計画を作成するのには 7 日間がかかります。</span><span class="sxs-lookup"><span data-stu-id="9eacc-p103">[Connect Office 365 to Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) to start monitoring using the default threat detection policies for anomalous behaviors. It takes seven days to build a baseline for anomaly detection.  </span></span><br><br/>  <span data-ttu-id="9eacc-147">管理者アカウントの保護を実装します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-147">Implement protection for admin accounts:</span></span>  <br/> <span data-ttu-id="9eacc-148">• 専用の使用の管理では、管理アクティビティが占めています。</span><span class="sxs-lookup"><span data-stu-id="9eacc-148">•    Use dedicated admin accounts for admin activity.</span></span>  <br/>  <span data-ttu-id="9eacc-149">• は、管理者アカウント用の多要素認証 (MFA) を適用します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-149">•   Enforce multi-factor authentication (MFA) for admin accounts.</span></span>  <br/>  <span data-ttu-id="9eacc-150">[安全性の高い Windows 10 デバイス](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure)を使用して管理活動の •。</span><span class="sxs-lookup"><span data-stu-id="9eacc-150">•   Use a [highly secure Windows 10 device](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) for admin activity.</span></span>  <br/> |
|<span data-ttu-id="9eacc-151">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="9eacc-151">Identity and access management</span></span>  <br/> |<span data-ttu-id="9eacc-152">• は[Azure Active Directory Id の保護を有効に](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-152">•   [Enable Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>  <br/> <span data-ttu-id="9eacc-153">• フェデレートされた識別情報の環境では、アカウントのセキュリティ (パスワードの長さ、年齢、複雑さなど) を適用します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-153">•   For federated identity environments, enforce account security (password length, age, complexity, etc.).</span></span>  <br/> |
|<span data-ttu-id="9eacc-154">情報 proteciton</span><span class="sxs-lookup"><span data-stu-id="9eacc-154">Information proteciton</span></span>  <br/> | <span data-ttu-id="9eacc-p104">例については保護の推奨事項を確認します。情報の保護には、組織全体にわたって調整が必要です。これらのリソースを開始します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-p104">Review example information protection recommendations. Information protection requires coordination across your organization. Get started with these resources:  </span></span><br/> <span data-ttu-id="9eacc-158">• [GDPR の office 365 の情報の保護](http://aka.ms/o365gdpr)</span><span class="sxs-lookup"><span data-stu-id="9eacc-158">•   [Office 365 Information Protection for GDPR](http://aka.ms/o365gdpr)</span></span> <br/> <span data-ttu-id="9eacc-159">• [SharePoint Online のセキュリティで保護されたサイトおよびファイル](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files)(共有、クラス分け、データ損失の防止、Azure の情報の保護が含まれています)</span><span class="sxs-lookup"><span data-stu-id="9eacc-159">•   [Secure SharePoint Online sites and files](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) (includes sharing, classification, data loss prevention, and Azure Information Protection)</span></span>  <br/> |
   
## <a name="90-days--enhanced-protections"></a><span data-ttu-id="9eacc-160">90 日間、保護を強化</span><span class="sxs-lookup"><span data-stu-id="9eacc-160">90 days — enhanced protections</span></span>
<span data-ttu-id="9eacc-161"><a name="Ninetydays"> </a></span><span class="sxs-lookup"><span data-stu-id="9eacc-161"></span></span>

<span data-ttu-id="9eacc-162">これらのタスクには、計画し実装しますが、セキュリティの状態が大幅に増加するに少し時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="9eacc-162">These tasks take a bit more time to plan and implement but greatly increase your security posture.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9eacc-163">領域</span><span class="sxs-lookup"><span data-stu-id="9eacc-163">Area</span></span>  <br/> |<span data-ttu-id="9eacc-164">タスク</span><span class="sxs-lookup"><span data-stu-id="9eacc-164">Task</span></span>  <br/> |
|<span data-ttu-id="9eacc-165">セキュリティの管理</span><span class="sxs-lookup"><span data-stu-id="9eacc-165">Security management</span></span>  <br/> | <span data-ttu-id="9eacc-166">• 環境に推奨される操作をセキュリティで保護されたスコアを確認する ( [https://securescore.office.com](https://securescore.office.com))。</span><span class="sxs-lookup"><span data-stu-id="9eacc-166">•   Check Secure Score for recommended actions for your environment ( [https://securescore.office.com](https://securescore.office.com)).</span></span>  <br/>  <span data-ttu-id="9eacc-167">• は、ダッシュ ボードおよびレポートでは、Office 365 のセキュリティとコンプライアンスの中心、クラウド アプリケーションのセキュリティ、および SIEM ツールを定期的に確認」に進みます。</span><span class="sxs-lookup"><span data-stu-id="9eacc-167">•   Continue to regularly review dashboards and reports in the Office 365 Security and Compliance Center, Cloud App Security, and SIEM tools.</span></span>  <br/>  <span data-ttu-id="9eacc-168">• は、検索し、ソフトウェア更新プログラムを実装します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-168">•   Look for and implement software updates.</span></span>  <br/>  <span data-ttu-id="9eacc-169">スピアー フィッシング、スプレーのパスワード、および[攻撃のシミュレータ](https://support.office.com/article/attack-simulator-office-365-da5845db-c578-4a41-b2cb-5a09689a551b)に付属している[Office 365 の脅威インテリジェンス](office-365-ti.md)) を使用して、ブルート フォース パスワード攻撃の • 倫理規定の攻撃のシミュレーション。</span><span class="sxs-lookup"><span data-stu-id="9eacc-169">•   Conduct attack simulations for spear-phishing, password-spray, and brute-force password attacks using [Attack Simulator](https://support.office.com/article/attack-simulator-office-365-da5845db-c578-4a41-b2cb-5a09689a551b) (included with [Office 365 Threat Intelligence](office-365-ti.md)).</span></span>  <br/>  <span data-ttu-id="9eacc-170">• ファイルの場所 ([調査] タブ) のクラウド アプリケーションのセキュリティの組み込みのレポートを確認することによってリスクを共有するためです。</span><span class="sxs-lookup"><span data-stu-id="9eacc-170">•   Look for sharing risk by reviewing the built-in reports in Cloud App Security (on the Investigate tab).</span></span>  <br/>  <span data-ttu-id="9eacc-171">• は、(GDPR、NIST 800-171) などの組織に適用される規制の状態を確認するのには、[コンプライアンス マネージャー](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-171">•   Check [Compliance Manager](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md) to review status for regulations that apply to your organization (such as GDPR, NIST 800-171).</span></span>  <br/> |
|<span data-ttu-id="9eacc-172">脅威保護</span><span class="sxs-lookup"><span data-stu-id="9eacc-172">Threat protection</span></span>  <br/> | <span data-ttu-id="9eacc-173">管理者アカウントの拡張保護機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-173">Implement enhanced protections for admin accounts:</span></span>  <br/>  <span data-ttu-id="9eacc-174">• 管理アクティビティに[アクセスの権限を持つワークステーション](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations)(前足) を構成します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-174">•   Configure [Privileged Access Workstations](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) for admin activity.</span></span>  <br/>  <span data-ttu-id="9eacc-175">• は、 [Azure AD 特権 Id の管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)を構成します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-175">•   Configure [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>  <br/>  <span data-ttu-id="9eacc-p105">• は、Office 365、クラウド アプリケーションのセキュリティ、および AD FS を含むその他のサービスからログ データを収集するためにセキュリティ情報およびイベント管理 (SIEM) ツールを構成します。Office 365 の監査ログでは、90 日間のみのデータを格納します。SIEM のツールでは、このデータのキャプチャを使用するより長い期間のデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-p105">•   Configure a security information and event management (SIEM) tool to collect logging data from Office 365, Cloud App Security, and other services, including AD FS. The Office 365 Audit Log stores data for only 90 days. Capturing this data in SIEM tool allows you to store data for a longer period.  </span></span><br/> |
|<span data-ttu-id="9eacc-179">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="9eacc-179">Identity and access management</span></span>  <br/> | <span data-ttu-id="9eacc-180">• を有効にし、すべてのユーザーの MFA を適用します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-180">•   Enable and enforce MFA for all users.</span></span>  <br/>  <span data-ttu-id="9eacc-181">• は、一連の[条件付きアクセスおよび関連するポリシー](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations)を実装します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-181">•   Implement a set of [conditional access and related policies](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations).</span></span> |
|<span data-ttu-id="9eacc-182">情報 proteciton</span><span class="sxs-lookup"><span data-stu-id="9eacc-182">Information proteciton</span></span>  <br/> | <span data-ttu-id="9eacc-p106">適応し、情報保護のポリシーを実装します。これらのリソースには、例が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9eacc-p106">Adapt and implement information protection policies. These resources include examples:  </span></span><br/> <span data-ttu-id="9eacc-185">• [GDPR の office 365 の情報の保護](http://aka.ms/o365gdpr)</span><span class="sxs-lookup"><span data-stu-id="9eacc-185">•   [Office 365 Information Protection for GDPR](http://aka.ms/o365gdpr)</span></span> <br/> <span data-ttu-id="9eacc-186">• [SharePoint Online のセキュリティで保護されたサイトおよびファイル](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files)</span><span class="sxs-lookup"><span data-stu-id="9eacc-186">•   [Secure SharePoint Online sites and files](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files)</span></span> <br/> <br> <span data-ttu-id="9eacc-187">(クラウド アプリケーションのセキュリティ) の代わりに Office 365 に格納されている Office 365 のデータ損失防止のポリシーと監視ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-187">Use data loss prevention policies and monitoring tools in Office 365 for data stored in Office 365 (instead of Cloud App Security).</span></span> <br><br><span data-ttu-id="9eacc-188">詳細なアラート機能 (データ損失の防止) を除く、Office 365 でクラウド アプリケーションのセキュリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-188">Use Cloud App Security with Office 365 for advanced alerting features (other than data loss prevention).</span></span>  <br/> |
   
## <a name="beyond"></a><span data-ttu-id="9eacc-189">を超えて</span><span class="sxs-lookup"><span data-stu-id="9eacc-189">Beyond</span></span>
<span data-ttu-id="9eacc-190"><a name="Beyond"> </a></span><span class="sxs-lookup"><span data-stu-id="9eacc-190"></span></span>

<span data-ttu-id="9eacc-191">これらは、前の作業を構築する重要なセキュリティ対策です。</span><span class="sxs-lookup"><span data-stu-id="9eacc-191">These are important security measures that build on previous work.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9eacc-192">領域</span><span class="sxs-lookup"><span data-stu-id="9eacc-192">Area</span></span>  <br/> |<span data-ttu-id="9eacc-193">タスク</span><span class="sxs-lookup"><span data-stu-id="9eacc-193">Task</span></span>  <br/> |
|<span data-ttu-id="9eacc-194">セキュリティの管理</span><span class="sxs-lookup"><span data-stu-id="9eacc-194">Security management</span></span>  <br/> |<span data-ttu-id="9eacc-195">• 引き続き、セキュリティで保護されたスコアを使用して、次のアクションを計画 ( [https://securescore.office.com](https://securescore.office.com))。</span><span class="sxs-lookup"><span data-stu-id="9eacc-195">•    Continue planning next actions by using Secure Score ( [https://securescore.office.com](https://securescore.office.com)).</span></span>  <br/>  <span data-ttu-id="9eacc-196">• は、ダッシュ ボードおよびレポートでは、Office 365 のセキュリティとコンプライアンスの中心、クラウド アプリケーションのセキュリティ、および SIEM ツールを定期的に確認」に進みます。</span><span class="sxs-lookup"><span data-stu-id="9eacc-196">•   Continue to regularly review dashboards and reports in the Office 365 Security and Compliance Center, Cloud App Security, and SIEM tools.</span></span>  <br/>  <span data-ttu-id="9eacc-197">• を検索し、ソフトウェア更新プログラムを実装する」に進みます。</span><span class="sxs-lookup"><span data-stu-id="9eacc-197">•   Continue to look for and implement software updates.</span></span>  <br/>  <span data-ttu-id="9eacc-198">•、法的には、電子的証拠開示と脅威の応答のプロセスを統合します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-198">•   Integrate eDiscovery into your legal and threat response processes.</span></span>  <br/> |
|<span data-ttu-id="9eacc-199">脅威保護</span><span class="sxs-lookup"><span data-stu-id="9eacc-199">Threat protection</span></span>  <br/> | <span data-ttu-id="9eacc-200">• (AD、AD FS) は、社内設置型のコンポーネントをユーザーの[アクセス権限をセキュリティで保護された](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)(SPA) を実装します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-200">•   Implement [Secure Privileged Access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) for identity components on premises (AD, AD FS).</span></span>  <br/>  <span data-ttu-id="9eacc-201">• 内部からの脅威を監視するためのクラウド アプリケーションのセキュリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-201">•   Use Cloud App Security to monitor for insider threats.</span></span>  <br/>  <span data-ttu-id="9eacc-202">• クラウド アプリケーションのセキュリティを使用してシャドウ IT SaaS の利用状況を検出します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-202">•   Discover shadow IT SaaS usage by using Cloud App Security.</span></span>  <br/> |
|<span data-ttu-id="9eacc-203">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="9eacc-203">Identity and access management</span></span>  <br/> | <span data-ttu-id="9eacc-204">• 絞り込み情報保護ポリシー:</span><span class="sxs-lookup"><span data-stu-id="9eacc-204">•   Refine information protection policies:</span></span>  <br/>  <span data-ttu-id="9eacc-205">• Azure の情報の保護と Office 365 のデータ損失防止 (DLP)。</span><span class="sxs-lookup"><span data-stu-id="9eacc-205">•   Azure Information Protection and Office 365 data loss prevention (DLP).</span></span>  <br/>  <span data-ttu-id="9eacc-206">• クラウド アプリケーションのセキュリティ ポリシーと通知します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-206">•   Cloud App Security policies and alerts.</span></span>  <br/> |
|<span data-ttu-id="9eacc-207">情報 proteciton</span><span class="sxs-lookup"><span data-stu-id="9eacc-207">Information proteciton</span></span>  <br/> | <span data-ttu-id="9eacc-208">• 絞り込みのポリシーと運用プロセスです。</span><span class="sxs-lookup"><span data-stu-id="9eacc-208">•   Refine policies and operational processes.</span></span>  <br/>  <span data-ttu-id="9eacc-209">• は、内部からの脅威を識別するのには、Azure AD Id の保護を使用します。</span><span class="sxs-lookup"><span data-stu-id="9eacc-209">•   Use Azure AD Identity Protection to identify insider threats.</span></span>  <br/> |
   
<span data-ttu-id="9eacc-210">参照してください: [Petya や WannaCrypt などの高速 cyberattacks を軽減する方法](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)です。</span><span class="sxs-lookup"><span data-stu-id="9eacc-210">Also see: [How to mitigate rapid cyberattacks such as Petya and WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).</span></span> 
  
