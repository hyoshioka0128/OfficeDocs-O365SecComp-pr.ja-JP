---
title: Office 365 で、非アクティブなメールボックスを復元します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 新入社員や他のユーザーは、Office 365 で、非アクティブなメールボックスの内容へのアクセスを必要とする場合することができます復元 (またはマージ) 使用頻度の低い既存のメールボックスにメールボックスの内容です。
ms.openlocfilehash: e0add2b63a48edc27795143324c83153b15dcf8c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531624"
---
# <a name="restore-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="2fd7b-103">Office 365 で、非アクティブなメールボックスを復元します。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-103">Restore an inactive mailbox in Office 365</span></span>

<span data-ttu-id="2fd7b-p101">非アクティブなメールボックス (回復可能な削除によって削除されたメールボックスの一種) は、元従業員が組織を離れた後に、その電子メールを保持するために使用されます。別の従業員が退職した従業員の職責を引き継ぐ場合、またはその従業員が組織に復帰する場合には、非アクティブなメールボックスのコンテンツをユーザーが使用できるようにする 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p101">An inactive mailbox (which is a type of soft-deleted mailbox) is used to retain a former employee's email after he or she leaves your organization. If another employee takes on the job responsibilities of the departed employee or if that employee returns to your organization, there are two ways that you can make the contents of the inactive mailbox available to a user:</span></span> 
  
- <span data-ttu-id="2fd7b-p102">**非アクティブなメールボックスを復元する** 退職した従業員の職務を別の従業員が引き継ぐ場合や、非アクティブなメールボックスのコンテンツに別のユーザーがアクセスすることが必要な場合は、非アクティブなメールボックスのコンテンツを既存のメールボックスに復元 (または マージ) できます。非アクティブなメールボックスからアーカイブを復元することもできます。復元された後も、非アクティブなメールボックスは保持されて、非アクティブなメールボックスとして保存されます。このトピックでは、非アクティブなメールボックスを復元するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p102">**Restore an inactive mailbox** If another employee takes on the job responsibilities of the departed employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. You can also restore the archive from an inactive mailbox. After it's restored, the inactive mailbox is preserved and is retained as an inactive mailbox. This topic describes the procedures for restoring an inactive mailbox.</span></span> 
    
- <span data-ttu-id="2fd7b-p103">**非アクティブなメールボックスのリカバリ**組織では、ゲーム終了者の従業員が返された場合、またはゲーム終了者の従業員の業務上の責任で実行する新しい従業員が採用された場合は、非アクティブなメールボックスの内容を回復できます。このメソッドは、アクティブでないメールボックスを非アクティブなメールボックスの内容を含む新しいメールボックスに変換します。を修復した後、非アクティブなメールボックスは存在しません。ステップ バイ ステップの手順では、 [Office 365 で、非アクティブなメールボックスのリカバリ](recover-an-inactive-mailbox.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p103">**Recover an inactive mailbox** If the departed employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox. This method converts the inactive mailbox to a new mailbox that contains the contents of the inactive mailbox. After it's recovered, the inactive mailbox no longer exists. For the step-by-step procedures, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
<span data-ttu-id="2fd7b-114">復元して、アクティブでないメールボックスを回復するとの違いの詳細については、この資料の**詳細について**はを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-114">See the **More information** section in this article for more details about the differences between restoring and recovering an inactive mailbox.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="2fd7b-115">はじめに</span><span class="sxs-lookup"><span data-stu-id="2fd7b-115">Before you begin</span></span>

- <span data-ttu-id="2fd7b-p104">アクティブでないメールボックスを復元する Exchange のオンライン PowerShell を使用する必要があります。Exchange 管理センター (EAC) を使用することはできません。手順については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/?linkid=396554)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p104">You have to use Exchange Online PowerShell to restore an inactive mailbox. You can't use the Exchange admin center (EAC). For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span>
    
- <span data-ttu-id="2fd7b-119">次のコマンドを実行 Exchange オンライン組織内の非アクティブなメールボックスの id 情報を取得する PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-119">Run the following command in Exchange Online PowerShell to get identity information for the inactive mailboxes in your organization.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     <span data-ttu-id="2fd7b-120">このコマンドによって返される情報を使用して、特定の非アクティブなメールボックスを復元します。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-120">Use the information returned by this command to restore a specific inactive mailbox.</span></span>
    
- <span data-ttu-id="2fd7b-121">非アクティブなメールボックスの詳細については、 [Office 365 でアクティブでないメールボックス](inactive-mailboxes-in-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-121">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="restore-an-inactive-mailbox"></a><span data-ttu-id="2fd7b-122">非アクティブなメールボックスを復元する</span><span class="sxs-lookup"><span data-stu-id="2fd7b-122">Restore an inactive mailbox</span></span>

<span data-ttu-id="2fd7b-p105">**New-MailboxRestoreRequest** コマンドレットを  _SourceMailbox_ と  _TargetMailbox_ パラメーターと共に使用して、非アクティブなメールボックスのコンテンツを既存のメールボックスに復元します。このコマンドレットの使用方法について詳しくは、「 [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p105">Use the **New-MailboxRestoreRequest** cmdlet with the  _SourceMailbox_ and  _TargetMailbox_ parameters to restore the contents of an inactive mailbox to an existing mailbox. For more information about using this cmdlet, see [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).</span></span>
  
1. <span data-ttu-id="2fd7b-125">非アクティブなメールボックスのプロパティを含む変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-125">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="2fd7b-p106">上記のコマンドでは、 **DistinguishedName** または **ExchangeGUID** プロパティの値を使用して非アクティブなメールボックスを識別します。これらのプロパティは組織内の各メールボックスに対して一意ですが、アクティブなメールボックスと非アクティブなメールボックスとでプライマリ SMTP アドレスが等しい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p106">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="2fd7b-p107">非アクティブなメールボックスのコンテンツを既存のメールボックスに復元します。非アクティブなメールボックス (ソース メールボックス) のコンテンツは、既存のメールボックス (ターゲット メールボックス) の対応するフォルダーにマージされます。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p107">Restore the contents of the inactive mailbox to an existing mailbox. The contents of the inactive mailbox (source mailbox) will be merged into the corresponding folders in the existing mailbox (target mailbox).</span></span>
    
    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```
   
   <span data-ttu-id="2fd7b-p108">または、非アクティブなメールボックスのコンテンツの復元先として、ターゲット メールボックス内の最上位フォルダーを指定することもできます。指定したターゲット フォルダーまたはターゲット フォルダー構造がターゲット メールボックス内に存在しない場合は、復元処理中に作成されます。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p108">Alternatively, you can specify a top-level folder in the target mailbox in which to restore the contents from the inactive mailbox. If the specified target folder or target folder structure doesn't already exist in the target mailbox, it is created during the restore process.</span></span> 
    
    <span data-ttu-id="2fd7b-132">次の使用例は、非アクティブなメールボックス内のメールボックス アイテムとサブフォルダーを、ターゲット メールボックスの最上位フォルダー構造内にある「Inactive Mailbox」という名前のフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-132">This example copies mailbox items and subfolders from an inactive mailbox to a folder named "Inactive Mailbox" in the top-level folder structure of the target mailbox.</span></span>
    
   ```
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```
  
## <a name="restore-the-archive-from-an-inactive-mailbox"></a><span data-ttu-id="2fd7b-133">非アクティブなメールボックスからアーカイブを復元する</span><span class="sxs-lookup"><span data-stu-id="2fd7b-133">Restore the archive from an inactive mailbox</span></span>

<span data-ttu-id="2fd7b-p109">非アクティブなメールボックスにアーカイブ メールボックスがある場合も、それを既存のメールボックスのアーカイブ メールボックスに復元できます。非アクティブなメールボックスからアーカイブを復元するには、 _SourceIsArchive_ と  _TargetIsAchive_ スイッチを、非アクティブなメールボックスの復元に使用するコマンドに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p109">If an inactive mailbox has an archive mailbox, you can also restore it to the archive mailbox of an existing mailbox. To restore the archive from an inactive mailbox, you have to add the  _SourceIsArchive_ and  _TargetIsAchive_ switches to the command used to restore an inactive mailbox.</span></span> 
  
1. <span data-ttu-id="2fd7b-136">非アクティブなメールボックスのプロパティを含む変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-136">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="2fd7b-p110">上記のコマンドでは、 **DistinguishedName** または **ExchangeGUID** プロパティの値を使用して非アクティブなメールボックスを識別します。これらのプロパティは組織内の各メールボックスに対して一意ですが、アクティブなメールボックスと非アクティブなメールボックスとでプライマリ SMTP アドレスが等しい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p110">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="2fd7b-p111">アーカイブのコンテンツを、非アクティブなメールボックス (ソース アーカイブ) から既存のメールボックスのアーカイブ (ターゲット アーカイブ) に復元します。この例では、ソース アーカイブのコンテンツが、ターゲット メールボックスのアーカイブ内の「Inactive Mailbox Archive」という名前のフォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p111">Restore the contents of the archive from the inactive mailbox (source archive) to the archive of an existing mailbox (target archive). In this example, the contents from the source archive are copied to a folder named "Inactive Mailbox Archive" in the archive of the target mailbox.</span></span>

    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

  
## <a name="more-information"></a><span data-ttu-id="2fd7b-141">詳細情報</span><span class="sxs-lookup"><span data-stu-id="2fd7b-141">More information</span></span>

- <span data-ttu-id="2fd7b-p112">**をリカバリして、アクティブでないメールボックスを復元するには大きな違いは何ですか?** 非アクティブなメールボックスをリカバリする場合は、メールボックスを新しいメールボックスに変換されます基本的と内容と非アクティブなメールボックスのフォルダー構造は保持されますが、メールボックスを新しいユーザー アカウントにリンクします。リカバリ後、非アクティブなメールボックスが存在しない、新しいメールボックスの内容に加えられた変更がコンテンツに接続されていたことに影響を与える非アクティブなメールボックスに保持します。逆に、非アクティブなメールボックスを復元する場合、別のメールボックスには、内容はコピーだけで。非アクティブなメールボックスは保持され、非アクティブなメールボックスのまま。移動先のメールボックス内のコンテンツに加えられた変更は、非アクティブなメールボックスに保持されている元のコンテンツに影響しません。非アクティブなメールボックスを Office 365 のセキュリティ[コンテンツの検索ツール](run-a-content-search-in-the-security-and-compliance-center.md)を使用して検索もできる&amp;コンプライアンス センターでは、別のメールボックスにその内容を復元することができますまたは回復または後で削除できます。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p112">**What's the main difference between recovering and restoring an inactive mailbox?** When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account. After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox. Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox. The inactive mailbox is preserved and remains an inactive mailbox. Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox. The inactive mailbox can still be searched by using the [Content Search tool](run-a-content-search-in-the-security-and-compliance-center.md) in the Office 365 Security &amp; Compliance Center, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date.</span></span> 
    
- <span data-ttu-id="2fd7b-p113">**非アクティブなメールボックスを見つける方法。** 組織内の非アクティブなメールボックスの一覧を取得して、非アクティブなメールボックスを復元するために役立つ情報を表示するには、次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p113">**How do you find inactive mailboxes?** To get a list of the inactive mailboxes in your organization and display information that is useful for restoring an inactive mailbox, you can run this command.</span></span> 

  ```
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- <span data-ttu-id="2fd7b-p114">**訴訟ホールドまたは Office 365 アイテム保持ポリシーを使用して非アクティブなメールボックスのコンテンツを保持する。** 非アクティブなメールボックスを復元した後にその状態を保持する場合は、非アクティブなメールボックスを復元する前に、ターゲット メールボックスを [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) に設定するか、または [Office 365 アイテム保持ポリシー](retention-policies.md)を適用することができます。これにより、非アクティブなメールボックスのアイテムがターゲット メールボックスに復元された後に、完全に削除されることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p114">**Use a Litigation Hold or Office 365 retention policy to retain inactive mailbox content.** If you want to retain the state of an inactive mailbox after it's restored, you can place the target mailbox on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) or apply an [Office 365 retention policy](retention-policies.md) before you restore the inactive mailbox. This will prevent the permanent deletion of any items from the inactive mailbox after they're restored to the target mailbox.</span></span> 
    
- <span data-ttu-id="2fd7b-p115">**、アクティブでないメールボックスを復元する前に移動先のメールボックスの保存を有効にするを保持します**。非アクティブなメールボックスからメールボックスのアイテムが古い可能性があります、ため、非アクティブなメールボックスを復元する前に、移動先のメールボックスに保持を有効にすることを検討する可能性があります。配置すると、保存上のメールボックスを保持、リテンション ・ ポリシーに割り当てられているは、保持を削除または保存管理機能を保持するまでには、期間が満了するまで処理されません。ターゲット メールボックス時間の非アクティブなメールボックスから古いメッセージを管理するための所有者を示します。それ以外の場合、リテンション ・ ポリシーがあります古いアイテムを削除 (または有効になっている場合は、アーカイブ メールボックスにアイテムを移動) 移動先のメールボックスに対して構成されている保存期間の設定に基づいて期限切れです。詳細については、 [Exchange オンラインを保持保持上のメールボックスの場所](https://go.microsoft.com/fwlink/?linkid=856300)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p115">**Enable retention hold on the target mailbox before you restore an inactive mailbox.** Because mailbox items from an inactive mailbox could be old, you might consider enabling retention hold on the target mailbox before you restore an inactive mailbox. When you put a mailbox on retention hold, the retention policy that's assigned to it won't be processed until the retention hold is removed or until the retention hold period expires. This gives the owner of the target mailbox time to manage old messages from the inactive mailbox. Otherwise, the retention policy might delete old items (or move items to the archive mailbox, if it's enabled) that have expired based on the retention settings configured for the target mailbox. For more information, see [Place a mailbox on retention hold in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300).</span></span>
    
- <span data-ttu-id="2fd7b-p116">**AllowLegacyDNMismatch スイッチの機能。** 非アクティブなメールボックスを復元する前述の例では、 **AllowLegacyDNMismatch** スイッチの使用によって、非アクティブなメールボックスを別のターゲット メールボックスに復元できるようになります。一般的な復元シナリオでは、ソース メールボックスとターゲット メールボックスが同じメールボックスのときに、コンテンツを復元することが目標となります。そのため既定では、 **New-MailboxRestoreRequest** コマンドレットにより、ソース メールボックスとターゲット メールボックスの **LegacyExchangeDN** プロパティの値が同じであることが確認されます。これにより、ソース メールボックスが誤って正しくないターゲット メールボックスに復元されることを防止します。 **AllowLegacyDNMismatch** スイッチを使用しないで非アクティブなメールボックスの復元を試行すると、ソース メールボックスとターゲット メールボックスで **LegacyExchangeDN** プロパティの値が異なる場合に、コマンドは失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p116">**What does the AllowLegacyDNMismatch switch do?** In the previous examples to restore an inactive mailbox, the **AllowLegacyDNMismatch** switch is used to allow restoring the inactive mailbox to a different target mailbox. In a typical restore scenario, the goal is to restore content where the source and target mailboxes are the same mailbox. So by default, the **New-MailboxRestoreRequest** cmdlet checks to make sure that the value of the **LegacyExchangeDN** property on the source and target mailboxes is the same. This helps prevents you from accidentally restoring a source mailbox into the wrong target mailbox. If you try to restore an inactive mailbox without using the **AllowLegacyDNMismatch** switch, the command might fail if the source and target mailboxes have different values for the **LegacyExchangeDN** property.</span></span> 
    
- <span data-ttu-id="2fd7b-p117">**New-MailboxRestoreRequest コマンドレットと共に他のパラメーターを使用して、非アクティブなメールボックスのさまざまな復元シナリオを実装できます。** たとえば、次のコマンドを実行して、非アクティブなメールボックスからターゲット メールボックスのプライマリ メールボックスにアーカイブを復元できます。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p117">**You can use other parameters with the New-MailboxRestoreRequest cmdlet to implement different restore scenarios for inactive mailboxes.** For example, you can run this command to restore the archive from the inactive mailbox into the primary mailbox of the target mailbox.</span></span> 
    
  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  <span data-ttu-id="2fd7b-168">また次のコマンドを実行して、非アクティブなプライマリ メールボックスをターゲット メールボックスのアーカイブに復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-168">You can also restore the inactive primary mailbox into the archive of the target mailbox by running this command.</span></span>

  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- <span data-ttu-id="2fd7b-p118">**TargetRootFolder パラメーターの機能。** 前述のように、 **TargetRootFolder** パラメーターを使用して、非アクティブなメールボックスのコンテンツを復元するためにターゲット メールボックス内のフォルダー構造の最上位フォルダー ( ルートとも呼ばれる) を指定できます。このパラメーターを使用しない場合、非アクティブなメールボックスのメールボックス アイテムはターゲット メールボックスの対応する既定のフォルダーにマージされ、カスタム フォルダーがターゲット メールボックスのルートに再作成されます。次の図は、 **TargetRootFolder** パラメーターを使用しない場合と使用する場合の、これらの相違点を強調しています。</span><span class="sxs-lookup"><span data-stu-id="2fd7b-p118">**What does the TargetRootFolder parameter do?** As previously explained, you can use the **TargetRootFolder** parameter to specify a folder in the top of the folder structure (also called the root) in the target mailbox in which to restore the contents of the inactive mailbox. If you don't use this parameter, mailbox items from the inactive mailbox are merged into the corresponding default folders of the target mailbox, and custom folders are re-created in the root of the target mailbox. The following illustrations highlight these differences between not using and using the **TargetRootFolder** parameter.</span></span> 
    
    <span data-ttu-id="2fd7b-173">**TargetRootFolder パラメーターを使用しない場合の、ターゲット メールボックス内のフォルダー階層**</span><span class="sxs-lookup"><span data-stu-id="2fd7b-173">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter isn't used**</span></span>
    
    ![TargetRootFolder パラメーターを使用していないときのスクリーン ショット](media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    <span data-ttu-id="2fd7b-175">**TargetRootFolder パラメーターを使用する場合の、ターゲット メールボックス内のフォルダー階層**</span><span class="sxs-lookup"><span data-stu-id="2fd7b-175">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter is used**</span></span>
    
    ![TargetRootFolder パラメーターが使用されているときのスクリーン ショット](media/300da592-7323-48db-b8a4-07012259d113.png)

  
