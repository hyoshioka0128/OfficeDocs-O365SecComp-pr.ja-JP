---
title: EOP で管理役割グループのアクセス許可を管理する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Microsoft Exchange Online Protection (EOP) では、Exchange 管理センター (EAC) を使用して、特定の管理タスクを実行するアクセス許可を割り当てるために、ユーザーを役割グループのメンバーにすることができます。また、EAC を使用して、ユーザーを役割グループから削除することもできます。
ms.openlocfilehash: 35f248bce26d28c8ab7465ff983629eb01db407b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150159"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a>EOP で管理役割グループのアクセス許可を管理する
  
Microsoft Exchange Online Protection (EOP) では、Exchange 管理センター (EAC) を使用して、特定の管理タスクを実行するアクセス許可を割り当てるために、ユーザーを役割グループのメンバーにすることができます。また、EAC を使用して、ユーザーを役割グループから削除することもできます。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- 予想所要時間 : 5 ～ 10 分
    
- この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「ユーザー、連絡先、および役割グループ」。 
    
- Office 365 内の特定のアクセス許可が EOP 管理役割グループのアクセス許可にマップされます。詳細については、「[管理者ロールを割り当てる](https://go.microsoft.com/fwlink/p/?LinkId=286708)」の「Office 365 権限の対象になるのはどのサービスですか。」セクションの「Exchange Online の役割」列を参照してください。
    
- このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。
    
> [!TIP]
> 問題がある場合は、Exchange のフォーラムで質問してください。 次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、 または [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="what-do-you-want-to-do"></a>必要な作業

### <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a>EAC を使用してメンバーを管理役割グループに割り当てる

1. EAC で、[**アクセス許可** \> **管理者の役割**] に移動し、ユーザーを追加する役割グループをクリックし、[編集] **** ![編集アイコン](../media/ITPro-EAC-EditIcon.gif)をクリックします。
    
2. [メンバー] の **[追加]**![[追加] アイコン](../media/ITPro-EAC-AddIcon.gif) をクリックします。[メンバーの選択] ウィンドウが表示されます。
    
3. 追加するユーザーを検索するか、または一覧からユーザーを選択します。
    
4. 追加するユーザーを選択したら、 **[追加]**、 **[OK]** の順にクリックします。[メンバーの選択] ウィンドウが閉じます。
    
5. ユーザーが **[メンバー]** ウィンドウに追加された状態になります。 **[保存]** をクリックします。
    
    > [!NOTE]
    > 役割グループに対してメンバーを追加または削除した後、ユーザーは自身の管理者権限の変更を確認するためにサインアウトしてから、再度サインインしなければならない場合があります。 
  
### <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a>EAC を使用して管理役割グループからメンバーを削除する

1. EAC で、[**アクセス許可** \> **管理者の役割**] に移動し、ユーザーを削除する役割グループをクリックしてから、[ **** ![編集アイコン](../media/ITPro-EAC-EditIcon.gif)の編集] をクリックします。
    
2. [メンバー] で削除するユーザーを選択し、 **[削除]**![[削除] アイコン](../media/ITPro-EAC-RemoveIcon.gif) をクリックします。
    
3. **[保存]** をクリックして役割グループに対する変更内容を保存し、 **[管理役割]** ページに戻ります。ユーザーが管理者役割グループから正常に削除されているかは、選択した役割グループの詳細ウィンドウの [メンバー] に、該当するメンバーが表示されていないことで確認します。 
    
    > [!NOTE]
    > 役割グループに対してメンバーを追加または削除した後、ユーザーは自身の管理者権限の変更を確認するためにサインアウトしてから、再度サインインしなければならない場合があります。 
  
## <a name="for-more-information"></a>詳細情報

[EOP の機能アクセス許可](feature-permissions-in-eop.md)
  

