---
title: Office 365 監査ログの検索を有効または無効にする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: セキュリティ & コンプライアンスセンターで、監査ログ検索機能を有効にすることができます。 変更した場合は、いつでもオフにすることができます。 監査ログ検索がオフになっている場合、管理者は、組織内のユーザーおよび管理者のアクティビティに対して Office 365 監査ログを検索することはできません。
ms.openlocfilehash: c5e1106617aa4828ec2db5afcc44ac55e91f2383
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158299"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a>Office 365 監査ログの検索を有効または無効にする

Office 365 監査ログの検索を開始する前に、自分 (または別の管理者) が監査ログを有効にする必要があります。 セキュリティ & コンプライアンスセンターで監査ログの検索が有効になっている場合、組織からのユーザーおよび管理者のアクティビティが監査ログに記録され、90日間保存されます。 ただし、監査ログデータを記録して保持したくない組織もあります。 または、サードパーティのセキュリティ情報およびイベント管理 (SIEM) アプリケーションを使用して、監査データにアクセスしている可能性があります。 そのような場合、グローバル管理者は Office 365 で監査ログの検索を無効にすることができます。
  
## <a name="before-you-begin"></a>始める前に

- Office 365 組織で監査ログの検索をオンまたはオフにするには、Exchange Online の Audit Logs 役割が割り当てられている必要があります。 既定では、この役割は、Exchange 管理センターの [**アクセス許可**] ページで、コンプライアンス管理および組織の管理役割グループに割り当てられます。 Office 365 のグローバル管理者は、Exchange Online の Organization Management 役割グループのメンバーです。 
    
    > [!IMPORTANT]
    > 監査ログの検索を有効または無効にするには、Exchange Online のアクセス許可をユーザーに割り当てる必要があります。 セキュリティ & コンプライアンスセンターの [**アクセス許可**] ページで監査ログの役割をユーザーに割り当てると、監査ログの検索をオンまたはオフにすることができなくなります。 これは、基礎となるコマンドレットが Exchange Online のコマンドレットであるためです。 
  
- Office 365 で監査ログの検索を無効にすると、Office 365 Management Activity API を使用して組織の監査データにアクセスできなくなります。 この記事の手順に従って監査ログの検索を無効にすると、Security & コンプライアンスセンターを使用して監査ログを検索したとき、または Exchange Online で**search-unifiedauditlog**コマンドレットを実行したときに結果が返されないことを意味します。PowerShell. これは、Office 365 Management Activity API を介して監査ログを利用できないことも意味します。  
    
- Office 365 監査ログの検索の詳細な手順については、「 [Security _AMP_ コンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。
    
## <a name="turn-on-audit-log-search"></a>監査ログ検索を有効にする

Security & コンプライアンスセンターまたは PowerShell を使用して、Office 365 で監査ログの検索を有効にすることができます。 監査ログの検索を有効にすると、監査ログの検索時に結果を返す前に、数時間かかる場合があります。 監査ログ検索を有効にするには、Exchange Online で Audit Logs 役割を割り当てられている必要があります。
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a>セキュリティ & コンプライアンスセンターを使用して監査ログの検索を有効にする

1. セキュリティ & コンプライアンスセンターで、[**検索** \> **監査ログの検索**] に移動します。
    
2. [**ユーザーと管理者のアクティビティの記録を開始**する] をクリックします。
    
    ![[ユーザーと管理者のアクティビティの記録を開始する] をクリックして、監査を有効にします。](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    組織内のユーザーおよび管理者のアクティビティが Office 365 の監査ログに記録され、レポートで表示できることを示すダイアログボックスが表示されます。 
    
3. 監査ログ検索の下で、 **[ユーザーと管理者のアクティビティの記録を開始する]** リンクを選択します (既にこの操作を実行済みの場合は、リンクは表示されません)。
    
    監査ログが準備されていて、準備が完了してから数時間で検索を実行できることを示すメッセージが表示されます。
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a>PowerShell を使用して監査ログの検索を有効にする

1. [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. Office 365 で監査ログの検索を有効にするには、次の PowerShell コマンドを実行します。
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    変更が有効になるまでに最大60分かかる可能性があることを伝えるメッセージが表示されます。
  
## <a name="turn-off-audit-log-search"></a>監査ログの検索を無効にする

監査ログの検索を無効にするには、Exchange Online 組織に接続されたリモート PowerShell を使用する必要があります。 監査ログ検索を有効にするのと同様に、監査ログ検索を無効にするには、Exchange Online の Audit Logs 役割を割り当てられている必要があります。
  
1. [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. Office 365 で監査ログの検索を無効にするには、次の PowerShell コマンドを実行します。
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. しばらくした後、監査ログの検索がオフ (無効) になっていることを確認します。 これを行うには 2 つの方法があります。
    
    - PowerShell で、次のコマンドを実行します。

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        UnifiedAuditLogIngestionEnabled プロパティの`False`の値__ は、監査ログの検索がオフになっていることを示します。 
    
    - セキュリティ & コンプライアンスセンターで、[ **** \> **監査ログ**の検索] に移動し、[**検索**] をクリックします。
    
      監査ログの検索が有効になっていないことを示すメッセージが表示されます。 
    
      ![監査がオフになっている場合は、メッセージが表示されます。](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
