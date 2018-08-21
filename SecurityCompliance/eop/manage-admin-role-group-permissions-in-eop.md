---
title: EOP で管理役割グループのアクセス許可を管理する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Microsoft Exchange Online Protection (EOP) では、Exchange 管理センター (EAC) を使用して、特定の管理タスクを実行するアクセス許可を割り当てるために、ユーザーを役割グループのメンバーにすることができます。また、EAC を使用して、ユーザーを役割グループから削除することもできます。
ms.openlocfilehash: 5d50c77c97f2c345aa3994e7fa3ecd2eea93a13a
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026664"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a><span data-ttu-id="31832-104">EOP で管理役割グループのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="31832-104">Manage admin role group permissions in EOP</span></span>
  
<span data-ttu-id="31832-p102">Microsoft Exchange Online Protection (EOP) では、Exchange 管理センター (EAC) を使用して、特定の管理タスクを実行するアクセス許可を割り当てるために、ユーザーを役割グループのメンバーにすることができます。また、EAC を使用して、ユーザーを役割グループから削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="31832-p102">In Microsoft Exchange Online Protection (EOP), you can use the Exchange admin center (EAC) to make a user a member of a role group or groups in order to assign them permissions to perform specific administrative tasks. You can also remove a user from a role group or groups by using the EAC.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="31832-107">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="31832-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="31832-108">予想所要時間 : 5 ～ 10 分</span><span class="sxs-lookup"><span data-stu-id="31832-108">Estimated time to complete: 5-10 minutes</span></span>
    
- <span data-ttu-id="31832-p103">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「ユーザー、連絡先、および役割グループ」。</span><span class="sxs-lookup"><span data-stu-id="31832-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
    
- <span data-ttu-id="31832-p104">Office 365 内の特定のアクセス許可が EOP 管理役割グループのアクセス許可にマップされます。詳細については、「[管理者ロールを割り当てる](https://go.microsoft.com/fwlink/p/?LinkId=286708)」の「Office 365 権限の対象になるのはどのサービスですか。」セクションの「Exchange Online の役割」列を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31832-p104">Certain permissions in Office 365 map to EOP admin role group permissions. For more information, see the "Role in Exchange Online" column in the "Which services do my Office 365 permissions extend to?" section in [Assigning Admin Roles](https://go.microsoft.com/fwlink/p/?LinkId=286708).</span></span>
    
- <span data-ttu-id="31832-114">このトピックの手順で使用可能なキーボード ショートカットについては、「**Exchange 管理センターのキーボード ショートカット**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31832-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="31832-p105">問題がある場合は、Exchange のフォーラムで質問してください。 次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、 または [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="31832-p105">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="what-do-you-want-to-do"></a><span data-ttu-id="31832-118">必要な作業</span><span class="sxs-lookup"><span data-stu-id="31832-118">What do you want to do?</span></span>

### <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a><span data-ttu-id="31832-119">EAC を使用してメンバーを管理役割グループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="31832-119">Use the EAC to assign members to admin role groups</span></span>

1. <span data-ttu-id="31832-120">EAC で、 **[アクセス許可]** \> **[管理役割]** の順に移動し、ユーザー (複数可) を追加する役割グループを選択して **[編集]**![編集アイコン](../media/ITPro-EAC-EditIcon.png) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31832-120">In the EAC, navigate to **Permissions** \> **Admin Roles**, click the role group that you want to add the user or users to, and then click **Edit**![Edit icon](../media/ITPro-EAC-EditIcon.png).</span></span>
    
2. <span data-ttu-id="31832-p106">[メンバー] の **[追加]**![[追加] アイコン](../media/ITPro-EAC-AddIcon.png) をクリックします。[メンバーの選択] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="31832-p106">Under Members, click **Add**![Add Icon](../media/ITPro-EAC-AddIcon.png). The Select Members window will appear.</span></span>
    
3. <span data-ttu-id="31832-123">追加するユーザーを検索するか、または一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="31832-123">Search for the user or users that you wish to add, or select them from the list.</span></span>
    
4. <span data-ttu-id="31832-p107">追加するユーザーを選択したら、 **[追加]**、 **[OK]** の順にクリックします。[メンバーの選択] ウィンドウが閉じます。</span><span class="sxs-lookup"><span data-stu-id="31832-p107">When you have selected the user or users that you want to add, click **Add**, and then click **OK**. The Select Members window will close.</span></span>
    
5. <span data-ttu-id="31832-p108">ユーザーが **[メンバー]** ウィンドウに追加された状態になります。 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31832-p108">You will see that the user has been added to the **Members** pane. Click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="31832-128">役割グループに対してメンバーを追加または削除した後、ユーザーは自身の管理者権限の変更を確認するためにサインアウトしてから、再度サインインしなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="31832-128">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span> 
  
### <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a><span data-ttu-id="31832-129">EAC を使用して管理役割グループからメンバーを削除する</span><span class="sxs-lookup"><span data-stu-id="31832-129">Use the EAC to remove members from admin role groups</span></span>

1. <span data-ttu-id="31832-130">EAC で、 **[アクセス許可]** \> **[管理役割]** の順に移動し、ユーザー (複数可) を削除する役割グループを選択して **[編集]**![編集アイコン](../media/ITPro-EAC-EditIcon.png) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31832-130">In the EAC, navigate to **Permissions** \> **Admin Roles**, click the role group that you want to remove a user or users from, and then click **Edit**![Edit icon](../media/ITPro-EAC-EditIcon.png).</span></span>
    
2. <span data-ttu-id="31832-131">[メンバー] で削除するユーザーを選択し、 **[削除]**![[削除] アイコン](../media/ITPro-EAC-RemoveIcon.png) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31832-131">Under Members, select the user or users that you want to remove and click **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.png).</span></span>
    
3. <span data-ttu-id="31832-p109">**[保存]** をクリックして役割グループに対する変更内容を保存し、 **[管理役割]** ページに戻ります。ユーザーが管理者役割グループから正常に削除されているかは、選択した役割グループの詳細ウィンドウの [メンバー] に、該当するメンバーが表示されていないことで確認します。</span><span class="sxs-lookup"><span data-stu-id="31832-p109">Click **Save** to save the change to the role group and return to the **Admin Roles** page. To verify that you've successfully removed the user from the administrator role group, make sure the member is no longer displayed under Members in the details pane for the selected role group.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="31832-134">役割グループに対してメンバーを追加または削除した後、ユーザーは自身の管理者権限の変更を確認するためにサインアウトしてから、再度サインインしなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="31832-134">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="31832-135">詳細情報</span><span class="sxs-lookup"><span data-stu-id="31832-135">For more information</span></span>

[<span data-ttu-id="31832-136">EOP の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="31832-136">Feature permissions in EOP</span></span>](feature-permissions-in-eop.md)
  
