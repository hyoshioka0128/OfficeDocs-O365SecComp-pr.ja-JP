---
title: Office 365 でオンプレミスのユーザーのクラウドベースのメールボックスを検索する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/4/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: Exchange ハイブリッド展開の社内ユーザーのために、Microsoft Teams のチャットデータ (1xN チャット) を検索してエクスポートするには、セキュリティ & コンプライアンスセンターのコンテンツ検索ツールを使用します。
ms.openlocfilehash: b08e1ea9ea9fb9fe834bb10948be532cbc4337b4
ms.sourcegitcommit: 6b2ca6bd153d24a717d6c537efd2d41d35c20a0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35587804"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users-in-office-365"></a>Office 365 でオンプレミスのユーザーのクラウドベースのメールボックスを検索する

組織に Exchange ハイブリッド展開があり、Microsoft Teams が有効になっている場合、ユーザーはインスタントメッセージング用に Teams chat アプリケーションを使用できます。 クラウドベースのユーザーの場合、Teams のチャットデータ (1xN チャットとも呼ばれます) は、プライマリクラウドベースのメールボックスに保存されます。 オンプレミスのユーザーがチームチャットアプリケーションを使用する場合、プライマリメールボックスはオンプレミスに配置されます。 この制限を回避するために、Microsoft は、オンプレミスのユーザーのために Teams のチャットデータを保存するために、クラウドベースのストレージ領域 (オンプレミスユーザー用のクラウドベースのメールボックスと呼ばれる) を作成する新機能をリリースしました。 これにより、セキュリティ & コンプライアンスセンターのコンテンツ検索ツールを使用して、オンプレミスのユーザーのために Teams のチャットデータを検索してエクスポートすることができます。 
  
以下に、クラウドベースのメールボックスをオンプレミスのユーザー用に設定および検索するための要件と制限事項を示します。
  
- オンプレミスのディレクトリサービス (Active Directory など) のユーザーアカウントは、Office 365 のディレクトリサービスである Azure Active Directory と同期する必要があります。 これは、メールユーザーアカウントが Office 365 で作成され、プライマリメールボックスが社内組織内にあるユーザーに関連付けられることを意味します。
    
- オンプレミスのユーザーのクラウドベースのメールボックスは、Teams のチャットデータのみを格納するために使用されます。 オンプレミスのユーザーは、クラウドベースのメールボックスにはサインインできません。また、何らかの方法でアクセスすることもできません。 電子メールメッセージを送受信するために使用することはできません。 
    
- 組織がオンプレミスユーザーのクラウドベースのメールボックスで Teams のチャットデータを検索できるようにするには、Microsoft サポートに要求を送信する必要があります。 この記事の[この機能を有効にするには、「Microsoft サポートによる要求のファイリング」を](#filing-a-request-with-microsoft-support-to-enable-this-feature)参照してください。 
    
 **注:** Teams チャネルの会話は、チームに関連付けられたクラウドベースのメールボックスに常に格納されます。 これは、コンテンツ検索を使用して、サポート要求をファイルしなくてもチャネル会話を検索できることを意味します。 Teams チャネル会話の検索の詳細については、「 [Microsoft teams および Office 365 グループの検索](content-search.md#searching-microsoft-teams-and-office-365-groups)」を参照してください。
  
## <a name="how-it-works"></a>メカニズム

Microsoft Teams が有効なユーザーがオンプレミスのメールボックスを持ち、そのユーザーアカウントまたは id がクラウドに同期されている場合、Microsoft は、1xN Teams のチャットデータを格納するためのクラウドベースのメールボックスを作成します。 Teams のチャットデータは、クラウドベースのメールボックスに格納された後、検索用にインデックスが付けられます。 これにより、コンテンツ検索 (および電子情報開示ケースに関連付けられた検索) を使用して、オンプレミスユーザーの Teams チャットデータの検索、プレビュー、エクスポートを行うことができます。 セキュリティ & コンプライアンスセンターの PowerShell で** \*new-compliancesearch**コマンドレットを使用して、オンプレミスユーザーの Teams チャットデータを検索することもできます。 
  
次の図は、オンプレミスユーザーの Teams チャットデータを検索、プレビュー、およびエクスポートできるようにするワークフローを示しています。
  
![Microsoft Teams でのオンプレミスユーザー向けのクラウドベースのストレージ](media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
この新しい機能に加えて、コンテンツ検索を使用して、各 Microsoft Teams に関連付けられたクラウドベースの SharePoint サイトと Exchange メールボックス内の Teams コンテンツを検索、プレビュー、およびエクスポートすることもできます。また、Exchange Online メールボックスで、クラウドベースのユーザー。

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a>この機能を有効にするために Microsoft サポートによる要求を提出する

組織がセキュリティ & コンプライアンスセンターでグラフィカルユーザーインターフェイスを使用して、社内ユーザーのクラウドベースのメールボックスで Teams のチャットデータを検索できるようにするには、Microsoft サポートを使用して要求をファイルにする必要があります。 この機能は、セキュリティ & コンプライアンスセンターの PowerShell で使用できます。 PowerShell を使用してオンプレミスユーザーの Teams チャットデータを検索するために、サポート要求を送信する必要はありません。 
  
Microsoft サポートに要求を送信するときに、次の情報を含めます。
  
- Office 365 組織の既定のドメイン名。
    
- Office 365 組織のテナント名とテナント ID。 これらは、Azure Active Directory ポータル ([**プロパティ**の**管理** \> ] の下) から見つけることができます。 「 [Office の Office 365 テナント ID を検索する](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b)」を参照してください。
    
- サポートリクエストの目的のタイトルまたは説明: 「オンプレミスユーザーのためにアプリケーションコンテンツ検索を有効にする」。 これにより、要求を実装する Office 365 eDiscovery エンジニアリングチームに要求をルーティングすることができます。 
    
エンジニアリングの変更が行われた後、Microsoft サポートは展開の推定日付を送信します。 通常、サポート要求を送信した後、展開プロセスには2-3 週間かかります。 
  
### <a name="what-happens-after-this-feature-is-enabled"></a>この機能を有効にした後はどうなりますか。

この機能が Office 365 組織に展開されると、次の変更が、セキュリティ & コンプライアンスセンターの電子情報開示ケースに関連付けられたコンテンツ検索と検索で行われます。
  
- **[オンプレミスユーザーの Office アプリコンテンツを追加**する] チェックボックスが [コンテンツ検索] の**場所**の下に追加されます。 
    
    ![コンテンツ検索 UI に「オンプレミスユーザーの Office アプリコンテンツを追加する」チェックボックスが追加されている](media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- オンプレミスのユーザーは、検索するユーザーメールボックスを選択するために使用するコンテンツの場所選択ウィンドウに表示されます。 
    

  
## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a>オンプレミスユーザーのクラウドベースのメールボックスで Teams のチャットコンテンツを検索する

機能が有効になったら、セキュリティ & コンプライアンスセンターでコンテンツ検索を使用して、社内ユーザーのクラウドベースのメールボックスで Teams のチャットデータを検索できます。 
  
1. [セキュリティ & コンプライアンスセンター] で、[**検索** \> **コンテンツ検索**] に移動します。
    
2. [**検索**] ページで、 ![[追加](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) ] アイコン [**新しい検索**] をクリックします。
    
    前述のように、[**場所**] の下に、 **[オンプレミスユーザーの Office アプリコンテンツを追加**する] チェックボックスが表示されます。 これは既定で選択されています。
    
3. キーワードクエリを作成し、必要に応じて検索クエリに条件を追加します。 チームのチャットデータのみを検索するには、[**キーワード**] ボックスに次のクエリを追加します。 
    
    ```
    kind:im
    ``` 

4. この時点で、[**場所**] の下にある次のオプションのいずれかを選択できます。
    
    - [**すべての場所**] 組織内のすべてのユーザーのメールボックスを検索するには、このオプションを選択します。 このチェックボックスをオンにすると、オンプレミスのユーザーのすべてのクラウドベースのメールボックスも検索されます。 
    
    - **特定の場所**-このオプションを選択し、[**変更** \> ] をクリックして、特定のメールボックスを検索するユーザー、グループ、またはチームを選択します。 前述したように、場所の選択ウィンドウを使用すると、オンプレミスのユーザーを検索できます。 
    
5. 検索を保存して実行します。 オンプレミスのユーザーのクラウドベースのメールボックスからの検索結果は、他の検索結果と同様にプレビューできます。 検索結果 (Teams のチャットデータを含む) を PST ファイルにエクスポートすることもできます。 詳細については、以下を参照してください。 
    
    - [Create a search](content-search.md#create-a-search)
    
    - [Preview search results](content-search.md#preview-search-results)
    
    - [コンテンツ検索の結果をエクスポートする](export-search-results.md)
    
## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a>PowerShell を使用してオンプレミスユーザーのクラウドベースのメールボックスで Teams チャットデータを検索する

セキュリティ & コンプライアンスセンターの PowerShell で**new-compliancesearch**および**new-compliancesearch**コマンドレットを使用して、オンプレミスのユーザーのクラウドベースのメールボックスを検索できます。 前述のように、PowerShell を使用してオンプレミスユーザーの Teams チャットデータを検索するためのサポート要求を送信する必要はありません。 
  
1. [セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)します。
    
2. 次の PowerShell コマンドを実行して、オンプレミスユーザーのクラウドベースのメールボックスを検索するコンテンツ検索を作成します。
    
    ```
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```
   
    *Includeuserappcontent*パラメーターは、 *exchangelocation*パラメーターで指定されたユーザーまたはユーザーのクラウドベースのメールボックスを指定するために使用されます。 *AllowNotFoundExchangeLocationsEnabled*では、クラウドベースのメールボックスがオンプレミスのユーザーに対して許可されています。 このパラメーターの`$true`値を使用する場合、検索では、メールボックスが実行される前に、存在しているかどうかの検証は試行されません。 この種類のメールボックスは通常のメールボックスとして解決されないため、オンプレミスのユーザーのクラウドベースのメールボックスを検索するには、これが必要になります。 
    
    次の例では、Contoso 組織のオンプレミスのユーザーである Sara Davis のクラウドベースのメールボックスに、キーワード "redstone" を含む Teams チャット (インスタントメッセージ) を検索します。
  
    ```
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   検索を作成したら、 **new-compliancesearch**コマンドレットを使用して検索を実行します。 
  
これらのコマンドレットの詳細については、以下を参照してください。
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)
    
- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)
    

## <a name="known-issues"></a>既知の問題

- 現在、社内ユーザーのクラウドベースのメールボックスに対してのみ、コンテンツの検索、プレビュー、およびエクスポートを行うことができます。 電子情報開示ケースに関連付けられている保留リストにクラウドベースのメールボックスを配置したり、Office 365 アイテム保持ポリシーに割り当てたりすることはサポートされていません。 
    
- 電子情報開示保持用のコンテンツの場所の選択は、オンプレミスのユーザーを表示し、それらを選択できるようにします。 ただし、以前に説明したように、保留はオンプレミスのユーザーには適用されません。
    
## <a name="frequently-asked-questions"></a>よく寄せられる質問

 **オンプレミスのユーザーのためのクラウドベースのメールボックスはどこにありますか?**
  
クラウドベースのメールボックスが作成され、Office 365 組織と同じデータセンターに保存されます。 
  
 **サポートリクエストを提出する以外に、その他の要件があるかどうか。**
  
 前述したように、オンプレミスのメールボックスを使用するユーザーの id は、Office 365 の社内ユーザーアカウントごとに、対応するメールユーザーアカウントが作成されるように、クラウドベースの組織に同期する必要があります。 組織には、Office 365 Enterprise E1、E3、または E5 サブスクリプションなどの Office 365 enterprise サブスクリプションも必要です。 
  
 **ユーザーのオンプレミスのメールボックスがクラウドに移行された場合、Teams のチャットデータを失う危険性がありますか。**
  
いいえ。 オンプレミスのユーザーのプライマリメールボックスをクラウドに移行すると、そのユーザーの Teams チャットデータが新しいクラウドベースのプライマリメールボックスに移行されます。
  
 **社内ユーザーに電子情報開示の保持ポリシーまたは Office 365 のアイテム保持ポリシーを適用できますか。**
  
いいえ。
  
 **コンテンツ検索は、組織がこの機能を有効にする要求を送信した時間前に、オンプレミスのユーザーのために古い Teams のチャットを見つけることができますか?**
  
Microsoft は、2018年1月31日に社内ユーザーの Teams チャットデータの保存を開始しました。 そのため、この日付以降に Active Directory と Azure Active Directory との間でオンプレミスの Teams ユーザーの id が同期されている場合、Teams のチャットデータはクラウドベースのメールボックスに保存され、コンテンツ検索を使用して検索可能になります。 Microsoft は、社内ユーザーのクラウドベースのメールボックスで2018年1月31日より前の Teams のチャットデータを保存することにも取り組んでいます。 詳細については、近日中にご利用いただけます。
