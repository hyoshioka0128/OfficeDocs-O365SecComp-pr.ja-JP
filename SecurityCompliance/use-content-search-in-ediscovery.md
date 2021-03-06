---
title: 電子情報開示ワークフローでコンテンツ検索を使用する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: 'セキュリティ & コンプライアンスセンターで作成された検索に基づいて、Exchange Online でインプレース電子情報開示検索を作成するには、PowerShell スクリプトを使用します。 '
ms.openlocfilehash: f3d5eb76dfa91334bccae42e0ddb66a71f739a6f
ms.sourcegitcommit: 044003455eb36071806c9f008ac631d54c64dde6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2019
ms.locfileid: "35199824"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a>電子情報開示ワークフローでコンテンツ検索を使用する

セキュリティ & コンプライアンスセンターのコンテンツ検索機能を使用すると、組織内のすべてのメールボックスを検索できます。 Exchange Online のインプレース電子情報開示とは異なり (1万メールボックスを検索することができます)、単一の検索の対象メールボックスの数に制限はありません。 組織全体の検索を実行する必要があるシナリオでは、コンテンツ検索を使用してすべてのメールボックスを検索できます。 その後、インプレース電子情報開示のワークフロー機能を使用して、メールボックスを保持に配置したり、検索結果をエクスポートしたりするなど、電子情報開示関連のその他のタスクを実行できます。 たとえば、すべてのメールボックスを検索して、訴訟に応答する特定の保管担当者を識別する必要があるとします。 セキュリティ & コンプライアンスセンターでコンテンツ検索を使用して、組織内のすべてのメールボックスを検索し、そのケースに応答するものを特定することができます。 その後、保管担当者メールボックスのリストを、Exchange Online のインプレース電子情報開示検索用のソースメールボックスとして使用できます。 インプレース電子情報開示を使用すると、これらのソースメールボックスを保持でき、検索結果を証拠開示用メールボックスにコピーして、検索結果をエクスポートすることもできます。
  
このトピックには、セキュリティ & コンプライアンスセンターで作成された検索からソースメールボックスと検索クエリの一覧を使用して、Exchange Online でインプレース電子情報開示検索を作成するために実行できるスクリプトが含まれています。 プロセスの概要は次のとおりです。
  
[手順 1: 組織内のすべてのメールボックスを検索するためのコンテンツ検索を作成する](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[手順 2: 1 つのリモート\& PowerShell セッションでセキュリティコンプライアンスセンターと Exchange Online に接続する](#step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[手順 3: コンテンツ検索からインプレースの電子情報開示検索を作成するスクリプトを実行する](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[手順 4: インプレースの電子情報開示検索を開始する](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a>手順 1: 組織内のすべてのメールボックスを検索するためのコンテンツ検索を作成する

最初の手順として、セキュリティ & コンプライアンスセンター (またはセキュリティ & コンプライアンスセンター PowerShell) を使用して、組織内のすべてのメールボックスを検索するコンテンツ検索を作成します。 単一のコンテンツ検索のメールボックス数に制限はありません。 適切なキーワード クエリ (または機密情報の種類に関するクエリ) を指定し、検索によって対象に関連する検索メールボックスだけが返されるようにします。 必要に応じて、検索クエリを調整し、返される検索結果とソース メールボックスの範囲を絞り込みます。
  
> [!NOTE]
> ソースコンテンツ検索で結果が返されない場合は、手順3でスクリプトを実行しても、インプレース電子情報開示は作成されません。 検索クエリを変更してから、検索結果を返すためにコンテンツ検索を再実行する必要がある場合があります。 
  
### <a name="use-the-security--compliance-center-to-search-all-mailboxes"></a>セキュリティ & コンプライアンスセンターを使用してすべてのメールボックスを検索する

1. [セキュリティ & コンプライアンスセンターに移動](go-to-the-securitycompliance-center.md)します。 
    
2. [**検索** > **コンテンツ検索**] をクリックし、[**新しい検索** ![の追加] アイコン](media/O365-MDM-CreatePolicy-AddIcon.gif)をクリックします。
    
3. **[新規検索]** ページで、コンテンツ検索の名前を入力します。 
    
4. [**どこを調べますか?**] で、[**すべてのメールボックスを検索**する] をクリックし、[**次へ**] をクリックします。
    
5. **[何をお探しですか?]** の下にあるボックスに、検索クエリを入力します。 キーワード、メッセージ プロパティ (送信日付や受信日付など)、ドキュメント プロパティ (ファイル名や、ドキュメントの最終変更日など) を指定できます。 AND、OR、NOT、NEAR などのブール演算子を使用するより複雑なクエリを使用することも、メッセージで機密情報 (社会保障番号など) を検索することもできます。 検索クエリの作成方法の詳細については、「[コンテンツ検索のキーワードクエリ](keyword-queries-and-search-conditions.md)」を参照してください。
    
6. **[検索]** をクリックして、検索設定を保存して検索を開始します。 
    
    しばらくすると、詳細ウィンドウに検索結果の推定値が表示されます。 この推定値には、検索結果の合計サイズと項目数が含まれています。 検索が完了すると、検索結果をプレビューできます。 必要に応じて****![、[最新](media/O365-MDM-Policy-RefreshIcon.gif)の情報に更新] アイコンをクリックして、詳細ウィンドウの情報を更新します。 
    
7.  必要に応じて、検索結果の範囲を絞り込むために検索クエリを調整し、検索を再開します。 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a>セキュリティ & コンプライアンスセンターの PowerShell を使用してすべてのメールボックスを検索する

**New-compliancesearch**コマンドレットを使用して、組織内のすべてのメールボックスを検索することもできます。 最初の手順として、[セキュリティ & コンプライアンスセンター PowerShell に接続](https://go.microsoft.com/fwlink/p/?LinkID=627084)します。
  
ここでは、PowerShell を使用して組織内のすべてのメールボックスを検索する例を示します。 検索クエリは、2015年1月1日から2015年6月30日までの間に送信されたすべてのメッセージを返します。これには件名行に「財務報告」という語句が含まれています。 1 番目のコマンドは検索を作成し、2 番目のコマンドは検索を実行します。 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

詳細については、「[New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935)」を参照してください。
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a>コンテンツ検索のソースメールボックスの数を確認する

コンテンツ検索では、検索結果を含む最大1000のソースメールボックスが返されます。 検索クエリに一致するコンテンツを含む1000個を超えるメールボックスがある場合、前の手順で作成したコンテンツ検索には、最も検索結果がある上位1000のメールボックスのみが含まれます。 そのため、1000以上のメールボックスに検索結果が含まれている場合、これらのメールボックスの一部は、手順3で作成した新しいインプレース電子情報開示検索にコピーされたソースメールボックスの一覧には含まれません。 
  
1000を超えるソースメールボックスを持つコンテンツ検索を作成するのに役立つように、次の手順に従って、手順1で作成したコンテンツ検索によって返されるソースメールボックスの数 (検索結果が含まれる) を表示するスクリプトを実行します。 
  
1. 次のテキストを、ファイル名サフィックス. ps1 を使用して PowerShell スクリプトファイルに保存します。 たとえば、という名前`SourceMailboxes.ps1`のファイルに保存することができます。
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
                  "Please wait until the search finishes.";
                  break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
                  "The Content Search " + $SearchName + " didn't return any useful results.";
                  break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  "Number of mailboxes that have search hits: " + $mailboxes.Count
  ```

2. [セキュリティ & コンプライアンスセンター] PowerShell で、前の手順で作成したスクリプトが置かれているフォルダーに移動し、スクリプトを実行します。例えば：
    
    ```
    .\SourceMailboxes.ps1
    ```

3. スクリプトによってメッセージが表示されたら、手順1で作成したコンテンツ検索の名前を入力します。
    
    スクリプトで検索結果が含まれるソース メールボックスの数が表示されます。
    
1000個を超えるソースメールボックスがある場合は、2つ以上のコンテンツ検索を作成してみてください。 たとえば、組織のメールボックスの半分を1つのコンテンツ検索で検索し、別のコンテンツ検索でその残りの部分を検索します。 検索結果が含まれるメールボックスの数が減るように検索条件を変更することもできます。 たとえば、日付範囲を指定したり、キーワードクエリを絞り込んだりすることができます。
  
## <a name="step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>手順 2: 1 つのリモート\& PowerShell セッションでセキュリティコンプライアンスセンターと Exchange Online に接続する

次の手順では、Windows PowerShell をセキュリティ & コンプライアンスセンターおよび Exchange Online 組織に接続します。 この手順が必要になるのは、手順3で実行するスクリプトで、セキュリティ & コンプライアンスセンターおよび Exchange Online のインプレース電子情報開示のコマンドレットにあるコンテンツ検索コマンドレットにアクセスする必要があるためです。
  
1. ファイル名のサフィックスに .ps1 を使って、次のテキストを Windows PowerShell スクリプト ファイルに保存します。 たとえば、という名前`ConnectEXO-CC.ps1`のファイルに保存することができます。
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. ローカル コンピューター上で、Windows PowerShell を開き、前の手順で作成したスクリプトが配置されているフォルダーに移動し、スクリプトを実行します。例:
    
    ```
    .\ConnectEXO-CC.ps1
    ```

これが機能したかどうかを知る方法 スクリプトを実行すると、セキュリティ & コンプライアンスセンターおよび Exchange Online のコマンドレットがローカルの PowerShell セッションにインポートされます。 何もエラーが表示されなければ、正常に接続されています。 簡単に確かめるには、セキュリティ/コンプライアンス センターのコマンドレット (**Install-UnifiedCompliancePrerequisite** など) および Exchange Online のコマンドレット (**Get-Mailbox** など) を実行して結果を確認します。 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a>手順 3: コンテンツ検索からインプレースの電子情報開示検索を作成するスクリプトを実行する

手順2で2つの PowerShell セッションを作成した後、次の手順では、既存のコンテンツ検索をインプレース電子情報開示検索に変換するスクリプトを実行します。 スクリプトは次の処理を行います。
  
- 変換するコンテンツ検索の名前を入力するように求めるメッセージが表示されます。
    
- コンテンツ検索の実行が完了したことを確認します。 コンテンツ検索で結果が返されない場合、インプレース電子情報開示は作成されません。
    
- 検索結果が含まれるコンテンツ検索からソースメールボックスの一覧を変数に保存します。
    
- 以下のプロパティが設定されたインプレースの電子情報開示検索を新たに作成します。 新しい検索が開始されていないことに注目してください。 手順 4 で開始します。
    
  - **Name** -新しい検索の名前は、次\<の形式を使用します。\>コンテンツ検索 _MBSearch1 の名前です。 スクリプトをもう一度実行して同じソースコンテンツ検索を使用した場合、検索に\<は「Content search\>_MBSearch2」という名前が付けられます。
    
  - **ソースメールボックス**-検索結果が含まれるコンテンツ検索からのすべてのメールボックス。 
    
  - **検索クエリ**-新しい検索では、コンテンツ検索の検索クエリが使用されます。 コンテンツ検索にすべてのコンテンツが含まれている場合 (検索クエリが空白の場合)、新しい検索には空の検索クエリがあり、ソースメールボックス内のすべてのコンテンツが含まれます。 
    
  - **推定のみ検索**-新しい検索は、推定のみの検索としてマークされます。 開始した後、検索結果は探索メールボックスにコピーされません。 
    
1. ファイル拡張子 ps1 の Windows PowerShell スクリプト ファイルに以下のテキストを保存します。 たとえば、という名前`CreateMBSearchFromComplianceSearch.ps1`のファイルに保存することができます。
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName,
      [switch]$original,
      [switch]$restoreOriginal
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
    "Please wait until the search finishes";
    break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
    "The Content Search " + $SearchName + " didn't return any useful results";
    "A mailbox search object wasn't created";
    break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  $msPrefix = $SearchName + "_MBSearch";
  $I = 1;
  $mbSearches = Get-MailboxSearch;
  while ($true)
  {
      $found = $false;
      $mbsName = "$msPrefix$I";
      foreach ($mbs in $mbSearches)
      {
          if ($mbs.Name -eq $mbsName)
          {
              $found = $true;
              break;
          }
      }
      if (!$found)
      {
          break;
      }
      $I++;
  }
  $query = $search.KeywordQuery;
  if ([string]::IsNullOrWhiteSpace($query))
  {
      $query = $search.ContentMatchQuery;
  }
  if ([string]::IsNullOrWhiteSpace($query))
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -EstimateOnly;
  }
  else
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -SearchQuery $query -EstimateOnly;
  }
  
  ```

2. 手順2で作成した Windows PowerShell セッションで、前の手順で作成したスクリプトが置かれているフォルダーに移動して、スクリプトを実行します。例えば：
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. スクリプトによってメッセージが表示されたら、インプレース電子情報開示検索に変換するコンテンツ検索の名前を入力し (たとえば、手順1で作成した検索)、enter キーを押し**** ます。
    
    スクリプトが正常に実行されると、新しいインプレースの電子情報開示検索が **NotStarted** というステータスで作成されます。  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` コマンドを実行し、新しい検索のプロパティを表示します。 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a>手順 4: インプレースの電子情報開示検索を開始する

手順 3 で実行したスクリプトでは新しいインプレースの電子情報開示検索が作成されますが、検索は開始しません。この手順では、検索を開始して検索結果の推定値を取得します。
  
1. In the Exchange admin center (EAC), go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
2. 一覧表示から、手順 3 で作成したインプレースの電子情報開示検索を選択します。
    
3. ![[ **** 検索検索アイコン](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **** ] をクリックして検索を開始し、検索によって返されるアイテムの合計サイズと件数の推定値を返します。 
    
    推定は、詳細ウィンドウに表示されます。 [最新の情報](media/O365-MDM-Policy-RefreshIcon.gif)に更新] アイコンをクリックして、詳細ウィンドウに表示される情報を更新します。 **** ![ 
    
4. 検索が完了した後で結果をプレビューするには、詳細ウィンドウで [ **検索結果のプレビュー**] をクリックします。
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a>インプレースの電子情報開示検索の作成と実行後の手順

手順 3 でスクリプトによって作成されたインプレースの電子情報開示検索を開始した後は、通常のインプレースの電子情報開示ワークフローを使用して、検索結果で各種の電子情報開示アクションを実行できます。
  
### <a name="create-an-in-place-hold"></a>インプレース保持を作成する

1. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
2. リストビューで、手順3で作成したインプレースの電子情報開示検索を選択し、[編集**** ![] 編集アイコン](media/O365-MDM-CreatePolicy-EditIcon.gif)をクリックします。
    
3. [ **インプレース保持**] ページで、[ **選択したメールボックス内の検索クエリに一致したコンテンツを保持する**] チェック ボックスをオンにして、次のいずれかのオプションを選択します。 
    
  - **無期限に保持**-検索によって返されたアイテムを無期限保持に配置するには、このオプションを選択します。 保持されたアイテムは、検索からメールボックスを削除するか、検索を削除するまで保持されます。 
    
  - [**受信日を基準としてアイテムを保持する日数を指定**する-特定の期間のアイテムを保持するには、このオプションを選択します。 期間は、メールボックス アイテムが受信または作成された日から計算されます。 
    
4. [ **保存**] をクリックしてインプレース保持を作成し、検索を再開します。 
    
[Return to top](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a>検索結果をコピーする

1. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
2. リスト表示から、手順 3 で作成したインプレースの電子情報開示検索を選択します。
    
3. [ **** ![検索検索]](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)アイコンをクリックし、ドロップダウンリストから [**検索結果のコピー** ] をクリックします。 
    
4. **[検索結果のコピー]** で、次のオプションの中から選択します。
    
    - [**検索不能アイテムを含める**]: このチェックボックスをオンにすると、検索できなかったメールボックスアイテム (たとえば、Exchange Search によってインデックスが作成されていないファイルの種類の添付ファイルを含むメッセージ) が含まれます。 
    
    - 重複**除外を有効**にする-重複するメッセージを除外するには、このチェックボックスをオンにします。 探索メールボックスには、メッセージの 1 つのインスタンスだけがコピーされます。 
    
    - **完全なログ出力を有効**にする-検索結果に完全なログを含めるには、このチェックボックスをオンにします。 
    
    - **コピーが完了したらメールを送信**する-検索が完了したときに電子メール通知を受信するには、このチェックボックスをオンにします。 
    
    - [**結果をこの探索メールボックスにコピーする**]-[**参照**] をクリックして、検索結果のコピー先の探索メールボックスを選択します。 
    
5. **[コピー]** をクリックして検索結果を指定された探索メールボックスにコピーするプロセスを開始します。 
    
6. [最新の情報](media/O365-MDM-Policy-RefreshIcon.gif)に更新] アイコンをクリックして、詳細ウィンドウに表示されるコピー状態に関する情報を更新します。 **** ![ 
    
7. コピーが完了したら、[**開く**] をクリックして、検索結果を表示する探索メールボックスを開きます。 
  
### <a name="export-the-search-results"></a>検索結果をエクスポートする

1. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
2. 一覧表示から、手順 3 で作成したインプレースの電子情報開示検索を選択し、[ **PST ファイルにエクスポートする**] をクリックします。
    
3. [ **Exchange eDiscovery PST エクスポート ツール**] ウィンドウで、次の操作を行います。 
    
    - [ **参照**] をクリックして、PST ファイルをダウンロードする場所を指定します。 
    
    - [ **重複除去を有効にする**] ボックスをクリックして重複メッセージを除外します。PST ファイルには、メッセージのインスタンスが 1 つだけ含まれます。 
    
    - [ **検索不能アイテムを含める**] チェック ボックスをオンにすると、検索できなかったメールボックス アイテム (たとえば、Exchange 検索でインデックスが作成できなかった種類のファイルが添付されたメッセージ) が含まれます。検索できないアイテムは、別の PST ファイルにエクスポートされます。 
    
4. [ **開始**] をクリックして、検索結果を PST ファイルにエクスポートします。 
    
    エクスポート プロセスに関するステータス情報が含まれているウィンドウが表示されます。
