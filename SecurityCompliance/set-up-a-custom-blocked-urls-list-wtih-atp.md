---
title: Office 365 の ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定します。
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 5/30/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
description: Office 365 の高度な脅威保護を使用して、組織のブロックされた Url の一覧を設定する方法の詳細については、この資料を参照してください。ブロックされた Url は、電子メール メッセージと、ATP の安全なリンク ポリシーに基づき、Office ドキュメントに適用されます。
ms.openlocfilehash: cd1e7858c8929bf468b2a4d5e09ccde9d5adc7b1
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532193"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="421af-104">Office 365 の ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定します。</span><span class="sxs-lookup"><span data-stu-id="421af-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

<span data-ttu-id="421af-p102">[Office 365 の高度な脅威保護](office-365-atp.md)(ATP)、組織はブロックされている web サイト アドレス (Url) のユーザー設定リストを持つことができます。URL がブロックされると、ブロックされた URL へのリンクをクリックするユーザーが次の図のような[警告ページ](atp-safe-links-warning-pages.md)に実行されます。</span><span class="sxs-lookup"><span data-stu-id="421af-p102">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked. When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![このサイトがブロックされています。](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="421af-108">組織の Office 365 のセキュリティ チームがブロックされている Url のリストが定義されているし、Office 365 の ATP の安全なリンク ポリシーの対象となる組織内の全員がそのリストが適用されます。</span><span class="sxs-lookup"><span data-stu-id="421af-108">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="421af-109">[Office 365 の安全なリンクを ATP](atp-safe-links.md)の組織のカスタム ブロックされた Url の一覧を設定する方法の詳細については、この資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="421af-109">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="421af-110">表示またはブロックされた Url のカスタム リストを編集します。</span><span class="sxs-lookup"><span data-stu-id="421af-110">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="421af-p103">[Office 365 の ATP の安全なリンク](atp-safe-links.md)では、組織のカスタム ブロックされた Url の一覧を含む、いくつかのリストを使用します。必要な権限があれば、組織のユーザー設定リストを設定できます。組織の安全なリンクの既定のポリシーを編集することによってこれを行います。</span><span class="sxs-lookup"><span data-stu-id="421af-p103">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list. If you have the necessary permissions, you can set up your organization's custom list. You do this by editing your organization's default Safe Links policy.</span></span>
  
1. <span data-ttu-id="421af-114">[https://protection.office.com](https://protection.office.com)と、職場、学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="421af-114">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="421af-115">**脅威の管理**の下で、左側のナビゲーションで [**ポリシー** ] を選択します\>**安全なリンク**です。</span><span class="sxs-lookup"><span data-stu-id="421af-115">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="421af-116">**組織全体に適用されるポリシー** ] セクションで **[既定**] を選択しの**編集**([編集] ボタンのような鉛筆) します。</span><span class="sxs-lookup"><span data-stu-id="421af-116">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span> 
    
    ![安全なリンクの保護のため、既定のポリシーを編集するのにはの編集] をクリックします。](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
    <span data-ttu-id="421af-p104">これでは、ブロックされた Url の一覧を表示します。最初にあることに注意して、すべての Url を一覧表示する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="421af-p104">This is where you go to view your list of blocked URLs. Note that at first, you won't have any URLs listed.</span></span>
    
    ![Url のブロック リストは、組織全体に適用される安全なリンク ポリシー、既定では。](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. <span data-ttu-id="421af-p105">**有効な URL を入力**] ボックスを選択し、URL を入力し、プラス記号 (+) を選択し。留意する点を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="421af-p105">Select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+). Here are a few things to keep in mind:</span></span> 
    
  - <span data-ttu-id="421af-p106">ドメイン専用の URL を指定することができます (のような`contoso.com`または`tailspintoys.com`)。クリック ノイズをブロックするこのドメインが含まれる任意の URL にします。</span><span class="sxs-lookup"><span data-stu-id="421af-p106">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`). This will block clicks on any URL that contains the domain.</span></span>
    
  - <span data-ttu-id="421af-p107">スラッシュが含まれていない ( **/**)、URL の末尾にします。入力するのではなく、たとえば、 `http://www.contoso.com/`、入力`http://www.contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="421af-p107">Do not include a forward slash ( **/**) at the end of the URL. For example, instead of entering `http://www.contoso.com/`, enter `http://www.contoso.com`.</span></span>
    
  - <span data-ttu-id="421af-p108">最大 3 つのワイルドカードのアスタリスクを含めることができます (\*) あたりの URL です。入力することができ、どのような効果のこれらのエントリの例をいくつかが次の表の一覧です。</span><span class="sxs-lookup"><span data-stu-id="421af-p108">You can include up to three wildcard asterisks (\*) per URL. The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="421af-129">**エントリの例**</span><span class="sxs-lookup"><span data-stu-id="421af-129">**Example Entry**</span></span>|<span data-ttu-id="421af-130">**何します。**</span><span class="sxs-lookup"><span data-stu-id="421af-130">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="421af-131">`contoso.com`または`\*contoso.com\*`</span><span class="sxs-lookup"><span data-stu-id="421af-131">`contoso.com` or `\*contoso.com\*`</span></span>  <br/> |<span data-ttu-id="421af-132">ドメイン、サブドメイン、およびパスを次のようにブロック`https://www.contoso.com`、`http://sub.contoso.com`と`http://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="421af-132">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `http://sub.contoso.com`, and `http://contoso.com/abc`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="421af-133">サイトをブロックする`http://contoso.com/a`いない追加のサブパスのような`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="421af-133">Blocks a site `http://contoso.com/a` but not additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a\*`  <br/> |<span data-ttu-id="421af-134">サイトをブロックする`http://contoso.com/a`などの他のサブパスを含めると`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="421af-134">Blocks a site `http://contoso.com/a` and additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
   
5. <span data-ttu-id="421af-135">画面の右下隅で、Url の追加が完了したら、**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="421af-135">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="what-if-i-want-to-define-exceptions-for-certain-users-in-my-organization"></a><span data-ttu-id="421af-136">場合自分の所属組織で特定のユーザーに対して例外を定義するか。</span><span class="sxs-lookup"><span data-stu-id="421af-136">What if I want to define exceptions for certain users in my organization?</span></span>

<span data-ttu-id="421af-p109">特定のグループが他のユーザーがブロックされている Url を表示できるようにする場合は、特定の受信者に適用される分析ツールの安全なリンクのポリシーを指定できます。[ATP の安全なリンクを使用してカスタム」を書き換えない"Url リストを設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="421af-p109">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients. See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="421af-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="421af-139">Related topics</span></span>

[<span data-ttu-id="421af-140">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="421af-140">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="421af-141">Office 365 で ATP の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="421af-141">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="421af-142">Office 365 の ATP の安全なリンクのポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="421af-142">Set up ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="421af-143">ATP の安全な添付ファイルを Office 365 で</span><span class="sxs-lookup"><span data-stu-id="421af-143">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)

[<span data-ttu-id="421af-144">Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="421af-144">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  
