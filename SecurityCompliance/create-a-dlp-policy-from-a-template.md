---
title: テンプレートからの DLP ポリシーの作成
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: 'DLP ポリシーを開始する最も簡単で最も一般的な方法では、Office 365 に含まれているテンプレートのいずれかを使用します。 '
ms.openlocfilehash: 4e3a5d731538e4998858b5f9f7a296c43e6774ac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532203"
---
# <a name="create-a-dlp-policy-from-a-template"></a><span data-ttu-id="1237e-103">テンプレートからの DLP ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="1237e-103">Create a DLP policy from a template</span></span>

<span data-ttu-id="1237e-p101">DLP ポリシーを開始する最も簡単で最も一般的な方法では、Office 365 に含まれているテンプレートのいずれかを使用します。同様に、これらのテンプレートのいずれかを使用したり、組織の特定のコンプライアンス要件を満たすためにルールをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="1237e-p101">The easiest, most common way to get started with DLP policies is to use one of the templates included in Office 365. You can use one of these templates as is, or customize the rules to meet your organization's specific compliance requirements.</span></span>
  
<span data-ttu-id="1237e-p102">Office 365 には 40 を超えるすぐに使用可能なテンプレートが備わっていて、広範囲におよぶ一般的な規定やビジネス ポリシーのニーズに対応できます。たとえば、以下を対象とした DLP ポリシー テンプレートがあります。</span><span class="sxs-lookup"><span data-stu-id="1237e-p102">Office 365 includes over 40 ready-to-use templates that can help you meet a wide range of common regulatory and business policy needs. For example, there are DLP policy templates for:</span></span>
  
- <span data-ttu-id="1237e-108">グラム リーチ ブライリー法 (GLBA)</span><span class="sxs-lookup"><span data-stu-id="1237e-108">Gramm-Leach-Bliley Act (GLBA)</span></span>
    
- <span data-ttu-id="1237e-109">クレジット カード業界データ セキュリティ基準 (PCI DSS)</span><span class="sxs-lookup"><span data-stu-id="1237e-109">Payment Card Industry Data Security Standard (PCI-DSS)</span></span>
    
- <span data-ttu-id="1237e-110">米国の個人情報 (U.S. PII)</span><span class="sxs-lookup"><span data-stu-id="1237e-110">United States Personally Identifiable Information (U.S. PII)</span></span>
    
- <span data-ttu-id="1237e-111">米国の医療保険法 (HIPAA)</span><span class="sxs-lookup"><span data-stu-id="1237e-111">United States Health Insurance Act (HIPAA)</span></span>
    
<span data-ttu-id="1237e-p103">既存のルールを変更したり、新しいルールを追加したりして、テンプレートを調整できます。たとえば、ルールに新しい種類の機密情報を追加したり、トリガーの難度を変更するためにルール内のカウントを変えたり、業務上の理由を提供することによってルールのアクションをユーザーが上書きできるようにしたり、通知とインシデント レポートの通知先を変更したりできます。DLP ポリシー テンプレートは、多くの一般的なコンプライアンス シナリオの柔軟な開始点となります。</span><span class="sxs-lookup"><span data-stu-id="1237e-p103">You can fine tune a template by modifying any of the existing rules or adding new ones. For example, you can add new types of sensitive information to a rule, modify the counts in a rule to make it harder or easier to trigger, allow people to override the actions in a rule by providing a business justification, or change who notifications and incident reports are sent to. A DLP policy template is a flexible starting point for many common compliance scenarios.</span></span>
  
<span data-ttu-id="1237e-115">カスタム テンプレートを選択することもできます。カスタム テンプレートには既定のルールがなく、組織の特定のコンプライアンス要件を満たすようにゼロから DLP ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="1237e-115">You can also choose the Custom template, which has no default rules, and configure your DLP policy from scratch, to meet the specific compliance requirements for your organization.</span></span>
  
## <a name="example-identify-sensitive-information-across-all-onedrive-for-business-sites-and-restrict-access-for-people-outside-your-organization"></a><span data-ttu-id="1237e-116">例: ビジネス サイトのすべての OneDrive の間で機密情報を識別し、組織外のユーザーのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="1237e-116">Example: Identify sensitive information across all OneDrive for Business sites and restrict access for people outside your organization</span></span>

<span data-ttu-id="1237e-p104">ビジネス アカウント用の OneDrive やすく人の共同作業し、ドキュメントを共有する組織全体にわたって。コンプライアンス担当役員の一般的な懸念事項は、ビジネス アカウントを OneDrive に保存された機密情報を誤って、組織外のユーザーと共有可能性があります。DLP ポリシーは、このリスクを軽減できます。</span><span class="sxs-lookup"><span data-stu-id="1237e-p104">OneDrive for Business accounts make it easy for people across your organization to collaborate and share documents. But a common concern for compliance officers is that sensitive information stored in OneDrive for Business accounts may be inadvertently shared with people outside your organization. A DLP policy can help mitigate this risk.</span></span>
  
<span data-ttu-id="1237e-p105">この例では、米国の個人情報データは、個々 の納税者識別番号 (ITIN)、社会保障番号、および米国のパスポート番号が含まれていますを識別する DLP ポリシーを作成します。テンプレートを使用して開始することし、組織のコンプライアンス要件に対応するテンプレートを変更してみましょう-具体的には、ことがわかります。</span><span class="sxs-lookup"><span data-stu-id="1237e-p105">In this example, you'll create a DLP policy that identifies U.S. PII data, which includes Individual Taxpayer Identification Numbers (ITIN), Social Security Numbers, and U.S. passport numbers. You'll get started by using a template, and then you'll modify the template to meet your organization's compliance requirements—specifically, you'll:</span></span>
  
- <span data-ttu-id="1237e-122">いくつかの重要な information—U.S です。 銀行口座番号と u. s. 運転免許証番号の種類を追加: DLP ポリシーは、機密性の高いデータのさらに多くを保護できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1237e-122">Add a couple of types of sensitive information—U.S. bank account numbers and U.S. driver's license numbers—so that the DLP policy protects even more of your sensitive data.</span></span>
    
- <span data-ttu-id="1237e-123">ようにポリシー、重要度の高い機密情報の 1 回の発生は、外部ユーザーのアクセスを制限するのには十分です。</span><span class="sxs-lookup"><span data-stu-id="1237e-123">Make the policy more sensitive, so that a single occurrence of sensitive information is enough to restrict access for external users.</span></span>
    
- <span data-ttu-id="1237e-p106">ビジネス ・ ジャスティフィケーションを提供することや、誤検出を報告して動作をオーバーライドできるようにします。この方法では、DLP ポリシーは、機密情報を共有するための有効なビジネスの理由であれば、作業を完了するには、組織内のユーザーを防ぐためはありません。</span><span class="sxs-lookup"><span data-stu-id="1237e-p106">Allow users to override the actions by providing a business justification or reporting a false positive. This way, your DLP policy won't prevent people in your organization from getting their work done, provided they have a valid business reason for sharing the sensitive information.</span></span>
    
### <a name="create-a-dlp-policy-from-a-template"></a><span data-ttu-id="1237e-126">テンプレートからの DLP ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="1237e-126">Create a DLP policy from a template</span></span>

1. <span data-ttu-id="1237e-127">[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="1237e-127">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="1237e-p107">職場、学校のアカウントを使用して Office 365 にサインインします。Office 365 のセキュリティの&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="1237e-p107">Sign in to Office 365 using your work or school account. You're now in the Office 365 Security &amp; Compliance Center.</span></span>
    
3. <span data-ttu-id="1237e-130">セキュリティ&amp;コンプライアンス センター\>左側のナビゲーション\>**データの損失防止** \> **ポリシー** \> **+ ポリシーの作成**。</span><span class="sxs-lookup"><span data-stu-id="1237e-130">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>
    
    ![[ポリシー] のボタンを作成します。](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. <span data-ttu-id="1237e-132">DLP ポリシー テンプレートを保護する必要のある機密性の高い情報の種類を選択して\>**次**です。</span><span class="sxs-lookup"><span data-stu-id="1237e-132">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>
    
    <span data-ttu-id="1237e-133">この例では、**プライバシー**を選択します\> **u. s. 個人を特定できる情報 (PII) データ**を保護する重要な情報の種類のほとんどが既に含まれているため、いくつかを後で追加します。</span><span class="sxs-lookup"><span data-stu-id="1237e-133">In this example, you'll select **Privacy** \> **U.S. Personally Identifiable Information ‎(PII)‎ Data** because it already includes most of the types of sensitive information that you want to protect—you'll add a couple later.</span></span> 
    
    <span data-ttu-id="1237e-134">テンプレートを選択するときは、機密情報、テンプレートの種類の保護については、右側の説明を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="1237e-134">When you select a template, you can read the description on the right to learn what types of sensitive information the template protects.</span></span>
    
    ![DLP ポリシー テンプレートを選択するためのページ](media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)
  
5. <span data-ttu-id="1237e-136">ポリシーの名前\>**次**です。</span><span class="sxs-lookup"><span data-stu-id="1237e-136">Name the policy \> **Next**.</span></span>
    
6. <span data-ttu-id="1237e-137">DLP ポリシーで保護するための場所を選択するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1237e-137">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>
    
  - <span data-ttu-id="1237e-138">**Office 365 内のすべての場所**を選択して\>**次**です。</span><span class="sxs-lookup"><span data-stu-id="1237e-138">Choose **All locations in Office 365** \> **Next**.</span></span>
    
  - <span data-ttu-id="1237e-p108">**自分で特定の場所を選択**を選択して\>**次**です。この例では、次のコマンドを選択します。</span><span class="sxs-lookup"><span data-stu-id="1237e-p108">Choose **Let me choose specific locations** \> **Next**. For this example, choose this.</span></span>
    
    <span data-ttu-id="1237e-141">オン/オフなど、すべての Exchange 電子メールまたは OneDrive のすべてのアカウントは、全体の場所を含めたり除外したり、その場所の**状態**を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="1237e-141">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span> 
    
    <span data-ttu-id="1237e-p109">ビジネス アカウントの特定の SharePoint サイトまたは OneDrive は、スイッチ**の状態**と特定のサイトまたはアカウントを選択するのに**含める**] で [リンク] をクリックします。サイト ポリシーは自動的にそのサイトのすべてのサブサイトに適用するという点で構成した規則にポリシーを適用するとします。</span><span class="sxs-lookup"><span data-stu-id="1237e-p109">To include only specific SharePoint sites or OneDrive for Business accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts. When you apply a policy to a site, the rules configured in that policy are automatically applied to all subsites of that site.</span></span> 
    
    ![DLP ポリシーを適用できる場所のオプション](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
    <span data-ttu-id="1237e-145">この例では、ビジネス アカウントのすべての OneDrive に格納される機密情報を保護するには、 **Exchange メール**と**SharePoint サイト**の両方**の状態**をオフし、の**OneDrive のアカウント**の**状態**のままにします。</span><span class="sxs-lookup"><span data-stu-id="1237e-145">In this example, to protect sensitive information stored in all OneDrive for Business accounts, turn off the **Status** for both **Exchange email** and **SharePoint sites**, and leave the **Status** on for **OneDrive accounts**.</span></span>
    
7. <span data-ttu-id="1237e-146">選択の**詳細設定を使用する** \> **次**です。</span><span class="sxs-lookup"><span data-stu-id="1237e-146">Choose **Use advanced settings** \> **Next**.</span></span>
    
8. <span data-ttu-id="1237e-p110">DLP ポリシー テンプレートには、条件とアクションを検出し、特定の種類の機密情報を操作する定義済みの規則が含まれています。編集して削除、または、既存のルールのいずれかをオフにするか、または新しいものを追加できます。終了したら、**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1237e-p110">A DLP policy template contains predefined rules with conditions and actions that detect and act upon specific types of sensitive information. You can edit, delete, or turn off any of the existing rules, or add new ones. When done, click **Next**.</span></span>
    
    ![米国の個人情報ポリシー テンプレートのルールの展開](media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)
  
    <span data-ttu-id="1237e-151">この例では、u. s. 個人情報のデータ テンプレートには、2 つの定義済みルールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1237e-151">In this example, the U.S. PII Data template includes two predefined rules:</span></span>
    
  - <span data-ttu-id="1237e-p111">**コンテンツ量が少ない米国の個人情報を検出します。** このルールは、1 と 10 に出現する 3 種類の機密情報 (節でこれ、SSN、u. s. パスポート番号)、組織外のユーザーとファイルを共有する場所の間を含むファイルを検索します。見つかると、ルールに送信電子メール通知、プライマリ サイト コレクション管理者は、ドキュメントの所有者と、最後のユーザーがドキュメントを変更します。</span><span class="sxs-lookup"><span data-stu-id="1237e-p111">**Low volume of content detected U.S. PII** This rule looks for files containing between 1 and 10 occurrences of each of three types of sensitive information (ITIN, SSN, and U.S. passport numbers), where the files are shared with people outside the organization. If found, the rule sends an email notification to the primary site collection administrator, document owner, and person who last modified the document.</span></span> 
    
  - <span data-ttu-id="1237e-p112">**大量コンテンツの米国の個人情報を検出します。** このルールは、組織外のユーザーとファイルを共有する場所に同じ 3 つの機密情報の種類のそれぞれの 10 個以上の出現を含むファイルを検索します。場合は検出されると、この操作も送信電子メール通知、さらにファイルへのアクセスを制限します。ビジネス アカウントは、OneDrive 内のコンテンツ、ドキュメントに対するアクセス許可のプライマリ サイト コレクション管理者、ドキュメントの所有者、およびドキュメントの最終更新者以外の全員が制限されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1237e-p112">**High volume of content detected U.S. PII** This rule looks for files containing 10 or more occurrences of each of the same three sensitive information types, where the files are shared with people outside the organization. If found, this action also sends an email notification, plus it restricts access to the file. For content in a OneDrive for Business account, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> 
    
    <span data-ttu-id="1237e-p113">組織の特定の要件を満たすためには、可能性がありますようにしますか、トリガーに規則を簡単に機密情報の 1 回の発生は、外部ユーザーのアクセスをブロックするのに十分な。低、高のカウントのルールが必要があることを理解するこれらの規則を見た後、出現するすべての機密情報が見つかった場合は、アクセスをブロックする 1 つのルールだけを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1237e-p113">To meet your organization's specific requirements, you may want to make the rules easier to trigger, so that a single occurrence of sensitive information is enough to block access for external users. After looking at these rules, you understand that you don't need low and high count rules—you need only a single rule that blocks access if any occurrence of sensitive information is found.</span></span>
    
    <span data-ttu-id="1237e-159">という名前の**コンテンツ量が少ない米国の個人情報を検出する**ルールを展開するように\>**ルールを削除**します。</span><span class="sxs-lookup"><span data-stu-id="1237e-159">So you expand the rule named **Low volume of content detected U.S. PII** \> **Delete rule**.</span></span>
    
    ![ルール] ボタンを削除します。](media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)
  
9. <span data-ttu-id="1237e-p114">ここで、この例では、必要がある 2 つの機密性の高い情報の種類 (米国の銀行口座番号、米国の運転免許証番号) を追加するのには、ルールを上書きできるようにして出現した回数の変更します。1 つのルールを編集することでは、**コンテンツ量の多い米国の個人情報を検出する**を選択することができます\>**の規則を編集**します。</span><span class="sxs-lookup"><span data-stu-id="1237e-p114">Now, in this example, you need to add two sensitive information types (U.S. bank account numbers and U.S. driver's license numbers), allow people to override a rule, and change the count to any occurrence. You can do all of this by editing one rule, so select **High volume of content detected U.S. PII** \> **Edit rule**.</span></span>
    
    ![ルール] ボタンを編集します。](media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)
  
10. <span data-ttu-id="1237e-p115">**条件**セクションで、機密性の高い情報の種類を追加するのには\>**を追加または変更の種類**です。その後、[**追加と変更の種類** \> **追加**」を選択\>**米国の銀行口座番号**と**u. s. 運転免許証番号**を選択して\>**追加** \> **行われます**。</span><span class="sxs-lookup"><span data-stu-id="1237e-p115">To add a sensitive information type, in the **Conditions** section \> **Add or change types**. Then, under **Add or change types** \> choose **Add** \> select **U.S. Bank Account Number** and **U.S. Driver's License Number** \> **Add** \> **Done**.</span></span>
    
    ![オプションを追加または変更の種類を](media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)
  
    ![追加または変更の種類] ペイン](media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)
  
11. <span data-ttu-id="1237e-p116">**インスタンス数**のカウント (機密性の高い情報、ルールをトリガーするために必要なインスタンスの数) を変更するのには\>の種類ごとに**最小**値を選択して\>1 を入力します。最小発生数を空にすることはできません。カウントの最大値は、空です。空**最大**の値は、**任意**に変換します。</span><span class="sxs-lookup"><span data-stu-id="1237e-p116">To change the count (the number of instances of sensitive information required to trigger the rule), under **Instance count** \> choose the **min** value for each type \> enter 1. The minimum count cannot be empty. The maximum count can be empty; an empty **max** value convert to **any**.</span></span>
    
    <span data-ttu-id="1237e-p117">完了したら、すべての機密情報の種類の最小数は**1**をする必要があり、最大数にする必要があります****。つまり、この種の機密情報の検索では、この条件を満たすが。</span><span class="sxs-lookup"><span data-stu-id="1237e-p117">When finished, the min count for all of the sensitive information types should be **1** and the max count should be **any**. In other words, any occurrence of this type of sensitive information will satisfy this condition.</span></span>
    
    ![機密性の高い情報の種類のインスタンスのカウント](media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)
  
12. <span data-ttu-id="1237e-174">最後のカスタマイズでは、DLP ポリシー ユーザーの有効な業務の妥当性であったり、ブロック操作を上書きするオプションを含める、ユーザーへの通知をするため、誤検知が発生したときの処理をブロックする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1237e-174">For the final customization, you don't want your DLP policies to block people from doing their work when they have a valid business justification or encounter a false positive, so you want the user notification to include options to override the blocking action.</span></span>
    
    <span data-ttu-id="1237e-175">[**ユーザー通知**] セクションで、電子メールによる通知とポリシーのヒントが入っているテンプレートでは、このルールの既定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1237e-175">In the **User notifications** section, you can see that email notifications and policy tips are turned on by default for this rule in the template.</span></span> 
    
    <span data-ttu-id="1237e-p118">**ユーザーのオーバーライド**] セクションで、業務の妥当性の上書きが有効になっているが、誤検出を報告するように上書きしていないことを確認できます。**誤検知として報告する場合に自動的にルールを上書き**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1237e-p118">In the **User overrides** section, you can see that overrides for a business justification are turned on, but overrides to report false positives are not. Choose **Override the rule automatically if they report it as a false positive**.</span></span>
    
    ![ユーザーの通知] セクションと [ユーザー] セクションをオーバーライドします。](media/62720e7a-a939-4c03-b414-67748f3d64a0.png)
  
13. <span data-ttu-id="1237e-179">規則エディターの上部には、この規則の名前デフォルトから変更**コンテンツ量の多い米国の個人情報を検出する****米国の個人情報で検出されたすべてのコンテンツ**に出現するすべての機密情報の種類のによって実行されるようになりましたので。</span><span class="sxs-lookup"><span data-stu-id="1237e-179">At the top of the rule editor, change the name of this rule from the default **High volume of content detected U.S. PII** to **Any content detected with U.S. PII** because it's now triggered by any occurrence of its sensitive information types.</span></span> 
    
14. <span data-ttu-id="1237e-180">規則エディターの下部にある\>**を保存**します。</span><span class="sxs-lookup"><span data-stu-id="1237e-180">At the bottom of the rule editor \> **Save**.</span></span>
    
15. <span data-ttu-id="1237e-181">条件とアクションを確認\>**次**です。</span><span class="sxs-lookup"><span data-stu-id="1237e-181">Review the conditions and actions for this rule \> **Next**.</span></span>
    
    <span data-ttu-id="1237e-p119">右側の [ルールのスイッチ**の状態**を確認します。全体にポリシーを無効にした場合、ポリシーに含まれるすべての規則もオフになります。ただし、ここでオフにできます、特定のルール全体のポリシーを無効にすることがなく。これは、多数の誤検知を生成するルールを調査する必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1237e-p119">On the right, notice the **Status** switch for the rule. If you turn off an entire policy, all rules contained in the policy are also turned off. However, here you can turn off a specific rule without turning off the entire policy. This can be useful when you need to investigate a rule that is generating a large number of false positives.</span></span> 
    
16. <span data-ttu-id="1237e-186">次のページでは、読み取りと、次を理解し、ルールを有効にするか、それを最初にテストするかどうかを選択し、 \> **次**です。</span><span class="sxs-lookup"><span data-stu-id="1237e-186">On the next page, read and understand the following, and then choose whether to turn on the rule or test it out first \> **Next**.</span></span>
    
     <span data-ttu-id="1237e-p120">DLP ポリシーを作成する前に、徐々 に展開の影響を評価し、これらの有効性を完全に実施する前にテストをお勧めします。たとえば、意図せずに何千もの人がその作業を行うために必要なドキュメントへのアクセスをブロックする新しい DLP ポリシーたくないです。</span><span class="sxs-lookup"><span data-stu-id="1237e-p120">Before you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before you fully enforce them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require to get their work done.</span></span> 
    
    <span data-ttu-id="1237e-189">かどうかは、大規模な潜在的な影響を持つ DLP ポリシーを作成する、お勧めしますこの順序に従います。</span><span class="sxs-lookup"><span data-stu-id="1237e-189">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
    
17. <span data-ttu-id="1237e-p121">ポリシー ヒントなしのテスト モードで開始し、DLP レポートを使用して、影響を評価します。DLP レポートを使用して、番号、場所、種類、およびポリシー一致の重要度を確認することができます。この結果に基づき、必要に応じてルールを詳細に調整できます。テスト モードでは、DLP ポリシーは組織で業務に取り組んでいるユーザーの生産性に影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="1237e-p121">Start in test mode without Policy Tips and then use the DLP reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
18. <span data-ttu-id="1237e-p122">通知とポリシー ヒントを利用するテスト モードに移行して、コンプライアンス ポリシーについてユーザーを教育し、適用されるルールに対して準備できるようにします。この段階で、ルールをさらに精緻化できるように、ユーザーに誤検知を報告するよう依頼することもできます。</span><span class="sxs-lookup"><span data-stu-id="1237e-p122">Move to Test mode with notifications and Policy Tips so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span>
    
19. <span data-ttu-id="1237e-p123">有効にするポリシー ルールが適用され、コンテンツの保護するため。DLP のレポートおよびインシデント レポートや、結果が意図したものかどうかを確認する通知の監視を続けます。</span><span class="sxs-lookup"><span data-stu-id="1237e-p123">Turn on the policies so that the rules are enforced and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 
    
    ![テスト モードを使用しポリシーで有効化するオプション](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
20. <span data-ttu-id="1237e-199">このポリシーの設定を確認\>**の作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1237e-199">Review your settings for this policy \> choose **Create**.</span></span>
    
<span data-ttu-id="1237e-200">作成し、DLP ポリシーを有効にした後、コンテンツ ソースに含まれている SharePoint Online サイトなどのビジネス アカウントでは、OneDrive ポリシーが自動的にそのコンテンツには、その規則の適用を開始する位置に配置されます。</span><span class="sxs-lookup"><span data-stu-id="1237e-200">After you create and turn on a DLP policy, it's deployed to any content sources that it includes, such as SharePoint Online sites or OneDrive for Business accounts, where the policy begins automatically enforcing its rules on that content.</span></span>
  
## <a name="view-the-status-of-a-dlp-policy"></a><span data-ttu-id="1237e-201">DLP ポリシーの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="1237e-201">View the status of a DLP policy</span></span>

<span data-ttu-id="1237e-p124">セキュリティの**データ損失の防止**] セクションの [**ポリシー** ] ページで、DLP ポリシーのステータスを表示する、いつでも&amp;コンプライアンス センターです。ここでは、ポリシーが正常に有効または無効にすると、かどうかどうかテスト モードでは、ポリシーなどの重要な情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1237e-p124">At any time, you can view the status of your DLP policies on the **Policy** page in the **Data loss prevention** section of the Security &amp; Compliance Center. Here you can find important information, such as whether a policy was successfully enabled or disabled, or whether the policy is in test mode.</span></span> 
  
<span data-ttu-id="1237e-204">以下に、さまざまな状態とその意味を示します。</span><span class="sxs-lookup"><span data-stu-id="1237e-204">Here are the different statuses and what they mean.</span></span>
  
|<span data-ttu-id="1237e-205">**状態**</span><span class="sxs-lookup"><span data-stu-id="1237e-205">**Status**</span></span>|<span data-ttu-id="1237e-206">**説明**</span><span class="sxs-lookup"><span data-stu-id="1237e-206">**Explanation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1237e-207">**有効にしています...**</span><span class="sxs-lookup"><span data-stu-id="1237e-207">**Turning on…**</span></span> <br/> |<span data-ttu-id="1237e-p125">対象のコンテンツ ソースにポリシーを展開中です。ポリシーは、まだすべてのソースに適用されていません。</span><span class="sxs-lookup"><span data-stu-id="1237e-p125">The policy is being deployed to the content sources that it includes. The policy is not yet enforced on all sources.</span></span>  <br/> |
|<span data-ttu-id="1237e-210">**テスト中 (通知あり)**</span><span class="sxs-lookup"><span data-stu-id="1237e-210">**Testing, with notifications**</span></span> <br/> |<span data-ttu-id="1237e-p126">ポリシーはテスト モードです。ルールのアクションが適用されていませんが、ポリシー一致が収集され、DLP レポートで確認できます。ポリシーの一致に関する通知は、指定した受信者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="1237e-p126">The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are sent to the specified recipients.</span></span>  <br/> |
|<span data-ttu-id="1237e-214">**テスト中 (通知なし)**</span><span class="sxs-lookup"><span data-stu-id="1237e-214">**Testing, without notifications**</span></span> <br/> |<span data-ttu-id="1237e-p127">ポリシーはテスト モードです。ルールのアクションが適用されていませんが、ポリシー一致が収集され、DLP レポートで確認できます。ポリシーの一致に関する通知は、指定した受信者に送信されません。</span><span class="sxs-lookup"><span data-stu-id="1237e-p127">The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are not sent to the specified recipients.</span></span>  <br/> |
|<span data-ttu-id="1237e-218">**有効**</span><span class="sxs-lookup"><span data-stu-id="1237e-218">**On**</span></span> <br/> |<span data-ttu-id="1237e-p128">ポリシーは有効であり、適用されています。ポリシーがすべてのコンテンツ ソースに正常に展開されました。</span><span class="sxs-lookup"><span data-stu-id="1237e-p128">The policy is active and enforced. The policy was successfully deployed to all its content sources.</span></span>  <br/> |
|<span data-ttu-id="1237e-221">**無効にしています...**</span><span class="sxs-lookup"><span data-stu-id="1237e-221">**Turning off…**</span></span> <br/> |<span data-ttu-id="1237e-p129">対象となるコンテンツ ソースからポリシーを削除しています。一部のソースではポリシーが引き続き有効であり、適用されている可能性があります。ポリシーを無効にするには、最大で 45 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1237e-p129">The policy is being removed from the content sources that it includes. The policy may still be active and enforced on some sources. Turning off a policy may take up to 45 minutes.</span></span>  <br/> |
|<span data-ttu-id="1237e-225">**無効**</span><span class="sxs-lookup"><span data-stu-id="1237e-225">**Off**</span></span> <br/> |<span data-ttu-id="1237e-p130">ポリシーは有効ではなく、適用されていません。ポリシーの設定 (ソース、キーワード、期間など) は保存されています。</span><span class="sxs-lookup"><span data-stu-id="1237e-p130">The policy is not active and not enforced. The settings for the policy (sources, keywords, duration, etc) are saved.</span></span>  <br/> |
|<span data-ttu-id="1237e-228">**削除しています...**</span><span class="sxs-lookup"><span data-stu-id="1237e-228">**Deleting…**</span></span> <br/> |<span data-ttu-id="1237e-p131">ポリシーを削除中です。ポリシーは有効ではなく、適用されていません。</span><span class="sxs-lookup"><span data-stu-id="1237e-p131">The policy is in the process of being deleted. The policy is not active and not enforced.</span></span>  <br/> |
   
## <a name="turn-off-a-dlp-policy"></a><span data-ttu-id="1237e-231">DLP ポリシーを無効にする</span><span class="sxs-lookup"><span data-stu-id="1237e-231">Turn off a DLP policy</span></span>

<span data-ttu-id="1237e-p132">編集したり、いつでも DLP ポリシーを無効にすることができます。ポリシーを無効にするには、ポリシー内の規則をすべて無効になります。</span><span class="sxs-lookup"><span data-stu-id="1237e-p132">You can edit or turn off a DLP policy at any time. Turning off a policy disables all of the rules in the policy.</span></span>
  
<span data-ttu-id="1237e-234">編集または**ポリシー**のページで、DLP ポリシーを無効にする\>ポリシーを選択して\>**のポリシーを編集**します。</span><span class="sxs-lookup"><span data-stu-id="1237e-234">To edit or turn off a DLP policy, on the **Policy** page \> select the policy \> **Edit policy**.</span></span>
  
![[ポリシー] ボタンを編集します。](media/ce319e92-0519-44fe-9507-45a409eaefe4.png)
  
<span data-ttu-id="1237e-236">さらに、ことができますオフにする各ルール、個別にポリシーを編集して、そのルールの**状態**をオフの切り替え、上記のように。</span><span class="sxs-lookup"><span data-stu-id="1237e-236">In addition, you can turn off each rule individually by editing the policy and then toggling off the **Status** of that rule, as described above.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="1237e-237">詳細情報</span><span class="sxs-lookup"><span data-stu-id="1237e-237">More information</span></span>

- [<span data-ttu-id="1237e-238">データ損失防止ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="1237e-238">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="1237e-239">DLP ポリシーに関する通知を送信してポリシー ヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="1237e-239">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="1237e-240">FCI または他のプロパティが使用されているドキュメントを保護する DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="1237e-240">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="1237e-241">DLP ポリシー テンプレートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="1237e-241">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="1237e-242">機密情報の種類のインベントリ</span><span class="sxs-lookup"><span data-stu-id="1237e-242">Sensitive information types inventory</span></span>](what-the-sensitive-information-types-look-for.md)
    
