---
title: Office 365 での技術による制御
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
description: '概要: Office 365 の手法がマイクロソフトのテクノロジのコントロールの概要を説明しました。'
ms.openlocfilehash: 2ef04b558f5fa82075d9aa602b83d437aa4b2ee6
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532038"
---
# <a name="office-365-technology-controls"></a><span data-ttu-id="b8b9f-103">Office 365 での技術による制御</span><span class="sxs-lookup"><span data-stu-id="b8b9f-103">Office 365 Technology Controls</span></span> 

<span data-ttu-id="b8b9f-p101">マイクロソフトでは、いくつかツールとテクノロジを制御、管理、およびオンライン Exchange ユーザーのデータへのアクセスを監査して SharePoint オンライン、ロック ボックスとお客様のロック ボックス、複数要素の認証などを使用します。[Yammer エンタープライズ ・ アクセス ・ コントロール](office-365-yammer-enterprise-access-controls.md)の説明に従って、エンタープライズのようなコントロールを使用する Yammer。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p101">Microsoft uses several tools and technologies to control, manage, and audit access to Customer Data in Exchange Online and SharePoint Online, including Lockbox and Customer Lockbox, multi-factor authentication, and more. Yammer Enterprise uses similar controls, as described in [Yammer Enterprise Access Controls](office-365-yammer-enterprise-access-controls.md).</span></span>

<span data-ttu-id="b8b9f-p102">Office 365 のエンジニア、Office 365 の顧客データへのアクセスをゼロ位置があり、マイクロソフト、および – かどうか顧客ライセンス顧客ロック ボックスの機能 Exchange Online と SharePoint Online – 承認プロセスを通過する必要があります顧客承認されると、サービス操作のための顧客データにアクセスが発生する前にします。承認が付与されるとサービスに固有の管理アカウントは、プロビジョニングされたジャスト ・ イン ・ タイム サービスの要求に必要なタスクを実行するのに十分なアクセスを持つ。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p102">Office 365 engineers have zero standing access to Office 365 Customer Data, and they must go through an approval process that includes both Microsoft and – if the customer licenses the Customer Lockbox feature for Exchange Online and SharePoint Online – customer approval, before access to Customer Data for service operations can occur. When approval is granted, service-specific administrative accounts are provisioned just-in-time with just enough access to perform the tasks required by the service request.</span></span>

## <a name="lockbox-and-customer-lockbox"></a><span data-ttu-id="b8b9f-108">ロック ボックスとお客様のロック ボックス</span><span class="sxs-lookup"><span data-stu-id="b8b9f-108">Lockbox and Customer Lockbox</span></span>
<span data-ttu-id="b8b9f-p103">非常にまれですが、顧客は問題とそれらを支援するために、マイクロソフトのエンジニアをお客様のコンテンツを失う可能性がありますをマイクロソフトから支援を要求でした。Exchange Online へのアクセスを制御する (ユーザーのメールボックスに格納されているビジネス データのすべての Skype を含む (ビジネスのカバレッジの Skype は含まれません Skype 会議のブロードキャストの記録またはユーザーがミーティングにアップロードされたコンテンツ)) とは、SharePoint Online (ビジネスの OneDrive を含む)、マイクロソフトは、ロック ボックスと呼ばれる、アクセス制御システムを使用します。マイクロソフトのエンジニアは、Exchange のオンラインまたは SharePoint のオンライン システムやデータにアクセスする前に、ロック ボックスを使用してアクセス権の要求を送信する必要があります。ロック ボックスを使用することは、Exchange Online または SharePoint Online へのすべての管理者特権のアクセスに必要です。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p103">Although it is extremely rare, a customer could request assistance from Microsoft that may expose a Microsoft engineer to the customer's content to assist them with an issue. To control access to Exchange Online (which includes any Skype for Business data stored in the users' mailboxes (Skype for Business coverage does not include Skype Meeting Broadcast recordings or content uploaded to meetings by users)) and SharePoint Online (which includes OneDrive for Business), Microsoft uses an access control system called Lockbox. Before any Microsoft engineer can access any Exchange Online or SharePoint Online systems or data, they must submit an access request using Lockbox. Using Lockbox is required for all elevated access to Exchange Online or SharePoint Online.</span></span>

<span data-ttu-id="b8b9f-p104">ロック ボックスは、エンジニア、サービス内での運用と管理の機能を実行する権限を付与するアクセス許可の要求を処理します。エンジニア ロック ボックスは、エンジニアがお客様のデータにアクセスする機能を獲得する前に管理者の承認が必要で要求を送信します。マネージャー承認されると、エンジニアはお客様の問題で動作する顧客データに時間制限範囲に限定されたアクセスを持ちます。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p104">Lockbox processes requests for permissions that grant engineers the ability to perform operational and administrative functions within the service. Engineers submit requests through Lockbox, which must be approved by a manager prior to the engineer gaining the ability to access Customer Data. Upon manager approval, the engineer has time-limited and scope-limited access to Customer Data to work on the customer's issue.</span></span>

<span data-ttu-id="b8b9f-p105">Office 365 のユーザーのロック ボックスについては、FedRAMP および HIPAA では、明示的なデータ アクセスの承認の手順が必要な場合などの遵守義務を満たすことができます。めったに Microsoft のサービス エンジニアがお客様のデータへのアクセスを必要とする場合アクセスを許可するその問題を解決するために必要なデータのみにし、限られた時間の。サポート ・ エンジニアが実行するアクションは監査目的で記録され、 [Office 365 の管理アクティビティの API](https://msdn.microsoft.com/library/office/dn707383.aspx) [セキュリティとコンプライアンスのセンター](http://protection.office.com/)経由でアクセスできます。お客様のロック ボックスは、ロック ボックスの承認プロセスに顧客を挿入し、Microsoft へのアクセス、Exchange のオンラインまたは SharePoint Online のコンテンツ サービスの操作の承認を制御する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p105">Customer Lockbox for Office 365 can help you meet compliance obligations, such as those found in FedRAMP and HIPAA, if you need procedures in place for explicit data access authorization. In the rare instance when a Microsoft service engineer needs access to your data, you grant that access only to data required to resolve the issue and for a limited amount of time. Actions taken by the support engineer are logged for auditing purposes and are accessible via the [Office 365 Management Activity API](https://msdn.microsoft.com/library/office/dn707383.aspx) and the [Security and Compliance Center](http://protection.office.com/). Customer Lockbox inserts the customer into the Lockbox approval process and provides them with the ability to control authorization of Microsoft access to their Exchange Online or SharePoint Online content for service operations.</span></span>

><span data-ttu-id="b8b9f-p106">**注**: 顧客のロック ボックスが利用可能で[Office 365 エンタープライズ E5](https://products.office.com/business/office-365-enterprise-e5-business-software)でアドオン購入では、Office 365 の管理センターで手動の操作を行う必要があります ([サービスの設定。顧客ロック ボックス) を有効にします。詳細については、 [Office 365 ユーザーのロック ボックス要求](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p106">**NOTE**: Customer Lockbox is available in [Office 365 Enterprise E5](https://products.office.com/business/office-365-enterprise-e5-business-software) and as an add-on purchase, but manual action must be taken in the Office 365 admin center (under Service Settings | Customer Lockbox) to enable it. For more information, see [Office 365 Customer Lockbox Requests](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2).</span></span>

<span data-ttu-id="b8b9f-p107">Exchange Online と SharePoint Online のすべてのサービス要求は、ロック ボックスのシステムによって処理されます。顧客のロック ボックスと露出度の顧客データにこれらのサービスへのアクセスが必要なサービスの操作、ロック ボックスの承認プロセスを通過を承認またはそれ以降の要求を拒否するお客様が有効になります。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p107">All service requests for Exchange Online and SharePoint Online are handled by the Lockbox system. And with Customer Lockbox, any service operation necessitating access to these services with exposure to Customer Data goes through the Lockbox approval process, and then enables the customer to approve or reject the request thereafter.</span></span>
 
<span data-ttu-id="b8b9f-124">*図 1 - お客様のロック ボックスのワークフロー*</span><span class="sxs-lookup"><span data-stu-id="b8b9f-124">*Figure 1 - Customer Lockbox Workflow*</span></span>

<span data-ttu-id="b8b9f-p108">顧客によって要求が拒否されると、マイクロソフトのエンジニアはお客様のコンテンツへのアクセス権がないし、サービス操作を完了することはできません。顧客によって要求が承認されると、マイクロソフトのエンジニアが制限監視、制限された管理インターフェイスを通じて、お客様のコンテンツへのアクセスをジャスト ・ イン ・ タイム。ロック ボックスとお客様のロック ボックスの両方では、承認済みのすべてのアクセスはエンジニアをお客様のデータの処理に責任を持つため、一意のユーザーにトレースできます。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p108">If the request is rejected by the customer, the Microsoft engineer will not have access to the customer's content and will not be able to complete the service operation. If the request is approved by the customer, the Microsoft engineer will have limited just-in-time access to the customer's content through monitored and constrained management interfaces. With both Lockbox and Customer Lockbox, all approved access is traceable to a unique user, making engineers accountable for their handling of Customer Data.</span></span>

## <a name="just-in-time-access"></a><span data-ttu-id="b8b9f-128">ジャスト ・ イン ・ タイムのアクセス</span><span class="sxs-lookup"><span data-stu-id="b8b9f-128">Just-in-Time Access</span></span>
<span data-ttu-id="b8b9f-p109">マイクロソフトでは、さらに資格情報を改ざんし、側面攻撃のリスクを軽減するのには Office 365 のジャスト ・ イン ・ タイム (JIT) アクセスの原則を使用します。JIT では、サービスへの永続的な管理アクセス権を削除し、それらの権利を要求時にこれらのロールに昇格させることに置き換えます。管理者から永続的な権利を削除することにより、資格情報が提供されているされ場合にのみ、必要な資格情報の盗難の場合、企業にもたらされるリスクを排除します。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p109">Microsoft uses the just-in-time (JIT) access principle for Office 365 to further mitigate the risk of credential tampering and lateral attacks. JIT removes persistent administrative access to services and replaces those entitlements with the ability to elevate into those roles on demand. Removing persistent rights from administrators ensures that credentials are available only when they are needed, and removes the risk posed to the company in cases of credential theft.</span></span>

<span data-ttu-id="b8b9f-p110">JIT のアクセス モデルでは、管理業務を実行するのには一定の特権を要求するエンジニアが必要です。さらに、OCEs は複雑なパスワードの自動生成されたを使用して作成された一時的なアカウントを使用し、必要なタスクを実行するためにこれらのロールのみを許可しました。などのロック ボックスによって付与された管理者のアクセスは期限付きで、アクセスが許可される時間は、要求されているロールによって異なります。エンジニアは、ロック ボックスのシステムへの要求時に必要な時にアクセスの継続時間を指定します。ロック ボックス システムは要求された時間が、昇格の時間を許可されている最大値を超えている要求を拒否します。昇格の要求の有効期限が切れた後、管理アクセス権の削除し、一時アカウントの期限が切れています。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p110">The JIT access model requires engineers to request elevated privileges for a limited period to perform administrative duties. In addition, OCEs use temporary accounts that are created with machine-generated complex passwords and granted only those roles that allow them to perform the necessary tasks. For example, administrative access granted by Lockbox is time-bound, and the amount of time access is granted depends on the role being requested. An engineer specifies the duration of time access needed during the request to the Lockbox system. The Lockbox system will reject requests where the time requested exceeds the maximum permitted time for the elevation. After expiration of the elevation request, administrative access is removed and the temporary account is expired.</span></span>

<span data-ttu-id="b8b9f-p111">承認され (たとえば、システムをデバッグする場合など) にアクセスできる承認済み、エンジニアでは、昇格したアクセスの要求が承認されるたびに認証システムによって生成された 1 回限りの管理用パスワードが表示されます。このパスワードは、エンジニアによって、パスワードを安全にコピー、Microsoft の企業環境では、エンジニアの資格情報とは別に、昇格したアクセスの承認対象のセッションに対してのみ有効します。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p111">When authorized and approved for access (for example, to debug a system), engineers receive a one-time use administrative password that is generated by the authorization system each time a request for elevated access is approved. This password is copied by the engineer into a password safe, is separate from the engineer's credentials for the Microsoft corporate environment, and is good only for the session for which elevated access was approved.</span></span>

## <a name="constrained-management-interfaces"></a><span data-ttu-id="b8b9f-140">制限された管理インタ フェース</span><span class="sxs-lookup"><span data-stu-id="b8b9f-140">Constrained Management Interfaces</span></span>
<span data-ttu-id="b8b9f-p112">OCEs では、2 つの管理インターフェイスを使用して、管理タスクを実行する: セキュリティで保護されたターミナル サービス ゲートウェイ (Tsg) とリモート PowerShell を使用してリモート デスクトップです。これらの管理ソフトウェアのポリシーとどのようなアプリケーションを実行することにかなり制限し、どのようなコマンドとコマンドレットを配置するアクセス制御インタ フェースを利用できます。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p112">OCEs use two management interfaces to perform administrative tasks: Remote Desktop through secured Terminal Service Gateways (TSGs) and Remote PowerShell. Within these management interfaces there are software policies and access controls that place significant restrictions on what applications can be executed and what commands and cmdlets are available.</span></span> 

<span data-ttu-id="b8b9f-p113">Office 365 のサーバーに 1 つの管理者のセッション サービスごとのチームでは、同時セッション数を制限するサーバーです。Tsg は、ユーザーの同時実行セッションを 1 つだけを許可するように構成されて、複数のセッションを許可しません。Tsg では、同時接続する複数のサーバーに、管理者がその職務を効率的に実行するように、サーバーあたり 1 つのセッションを使用して Office 365 サービス チームの管理者を使用できます。サービス チームの管理者は、自身 Tsg のすべてのアクセス許可を必要はありません。(MFA) の多要素認証と暗号化の要件を適用する場合にのみ、TSG が使用されます。サービス チームの管理者は、TSG を特定のサーバーに接続すると、管理者ごとに 1 つのセッションの制限が特定のサーバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p113">Office 365 servers restrict concurrent sessions to one session per-service team administrator, per-server. TSGs are configured to allow only a single concurrent session for users, and they do not allow multiple sessions. TSGs allow Office 365 service team administrators to connect to multiple servers concurrently, using a single session per server, so that administrators can effectively perform their duties. Service team administrators do not have any permissions on the TSGs themselves. The TSG is used only to enforce multi-factor authentication (MFA) and encryption requirements. Once the service team administrator connects to a specific server through a TSG, the specific server will enforce a session limit of one per administrator.</span></span>

<span data-ttu-id="b8b9f-p114">用途を制限し、Office 365 の担当者のための接続と構成の要件は、Active Directory グループ ポリシーによって確立されます。これらのポリシーには、次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p114">Usage restrictions and connection and configuration requirements for Office 365 personnel are established by Active Directory group policies. These policies include the following characteristics:</span></span>
- <span data-ttu-id="b8b9f-151">Tsg は、のみの[FIPS](https://www.microsoft.com/en-us/TrustCenter/Compliance/FIPS) 140-2 検証済みの暗号化を使用するよう構成されて</span><span class="sxs-lookup"><span data-stu-id="b8b9f-151">TSGs are configured to use only [FIPS](https://www.microsoft.com/en-us/TrustCenter/Compliance/FIPS) 140-2 validated encryption</span></span>
- <span data-ttu-id="b8b9f-152">TSG のセッションは 30 分間続いた接続を切断するように構成されて</span><span class="sxs-lookup"><span data-stu-id="b8b9f-152">TSG sessions are configured to disconnect after 30 minutes of inactivity</span></span>
- <span data-ttu-id="b8b9f-153">TSG のセッションは、オフの 24 時間後に構成されて自動的にログオンする</span><span class="sxs-lookup"><span data-stu-id="b8b9f-153">TSG sessions are configured to automatically log off after 24 hours</span></span>

<span data-ttu-id="b8b9f-p115">Tsg への接続には、MFA の別の物理的なスマート カードおよびエンジニアの Microsoft 企業の資格情報とは別のアカウントを使用しても必要です。エンジニアは、さまざまなプラットフォーム用の別のスマート カードを発行し、資格情報のセキュリティで保護された記憶域を確保するのには機密情報管理プラットフォームを使用します。Tsg では、セッションの最大許容、およびアイドル状態のタイムアウトの設定の数のリモート サーバーにログインできるユーザーを制御する Active Directory グループ ポリシーを使用します。追加のポリシーは、許可されたアプリケーションと、インターネットへのアクセスを制限するためのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p115">Connections to TSGs also require MFA using a separate physical smart card and an account that is separate from the engineer's Microsoft corporate credentials. Engineers are issued different smart cards for various platforms and secrets management platforms are used to ensure secure storage of credentials. TSGs use Active Directory group policies to control who can login to remote servers, the number of allowed sessions, and idle timeout settings. Additional polices are in place to limit access to allowed applications and to restrict Internet access.</span></span>

<span data-ttu-id="b8b9f-p116">Tsg の特別な構成を使用して、リモート アクセスだけでなく Exchange Online では、リモート PowerShell を使用して実稼動サーバーで特定の管理機能にアクセスするサービス エンジニア リング操作の役割を持つユーザーです。これを行うには、Office 365 の実稼働環境へのアクセスを読み取り専用 (デバッグ) のユーザーを承認する必要があります。特権エスカレーションの Tsg のロック ボックスを使用して有効になっているのと同じ方法が有効です。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p116">In addition to remote access using specially-configured TSGs, Exchange Online allows users with the Service Engineer Operations role to access certain administrative functionality on production servers using Remote PowerShell. To do this, the user must be authorized for read-only (debug) access to the Office 365 production environment. Privilege escalation is enabled the same way it is enabled for TSGs using the Lockbox process.</span></span>

<span data-ttu-id="b8b9f-p117">リモート アクセスには単一のアクセス ポイントとして機能する各データ センターに負荷分散の仮想 IP があります。実行できるリモート PowerShell コマンドレットは、認証時に取得したアクセス要求で指定された特権レベルに基づいています。これらのコマンドレットは、アクセスし、このメソッドを使用して接続するユーザーが実行できる唯一の管理機能です。リモート PowerShell を使用して、ロック ボックスのプロセスを使用して許可するアクセス権のレベルに応じた、エンジニア リングに使用できるコマンドの範囲を制限します。などの Exchange online では、Get メールボックスが使用できる場合がありますが、複数のメールボックスに設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b8b9f-p117">For remote access, there is a load-balanced virtual IP at each datacenter that serves as a single point of access. The Remote PowerShell cmdlets that can be executed are based on the privilege level identified in the access claim obtained during authentication. These cmdlets are the only administrative functionality that can be accessed and executed by users connecting using this method. Remote PowerShell is used to limit the scope of commands available to the engineer, which is based upon the level of access granted via the Lockbox process. For example, in Exchange Online, Get-Mailbox might be available, but Set-Mailbox would not be.</span></span>