---
title: 電子情報開示検索結果での重複除去
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/21/2016
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
description: 場合でも、別のメールボックスに同じメッセージの複数のインスタンスが検出された可能性がありますが、電子メール メッセージのコピーを 1 つだけをエクスポートするためにエクスポートされる電子的証拠開示検索結果の重複を除外するオプションがあります。
ms.openlocfilehash: 02a4f9f6db0fb8831d5e5cc13adaffbd0c4dcecc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532691"
---
# <a name="de-duplication-in-ediscovery-search-results"></a><span data-ttu-id="27a8c-103">電子情報開示検索結果での重複除去</span><span class="sxs-lookup"><span data-stu-id="27a8c-103">De-duplication in eDiscovery search results</span></span>

<span data-ttu-id="27a8c-104">この資料では、電子的証拠開示検索結果の重複除外の機能し、データ重複除外アルゴリズムの制限についての説明を説明します。</span><span class="sxs-lookup"><span data-stu-id="27a8c-104">This article describes how de-duplication of eDiscovery search results works and explains the limitations of the de-duplication algorithm.</span></span>
  
<span data-ttu-id="27a8c-p101">EDiscovery ツールを Office 365 を使用して、電子的証拠開示検索結果をエクスポートするのには、エクスポートされた結果の重複を除外するオプションがあります。これはどういうことでしょうか。重複除外を有効にすると (既定では、重複除外が有効になって)、場合でも、検索されたメールボックスに同じメッセージの複数のインスタンスが検出された可能性がありますが、電子メール メッセージのコピーを 1 つだけがエクスポートされます。重複を確認し、検索結果をエクスポートした後に分析する必要がある項目の数を減らすことで時間を節約することができます。重複除外の仕組みを理解し、エクスポート プロセス中に、重複としてマークするのには一意の項目を引き起こす可能性のあるアルゴリズムに制限があることに注意してくださいすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="27a8c-p101">When using Office 365 eDiscovery tools to export the results of an eDiscovery search, you have the option to de-duplicate the results that are exported. What does this mean? When you enable de-duplication (by default, de-duplication isn't enabled), only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched. De-duplication helps you save time by reducing the number of items that you have to review and analyze after the search results are exported. But it's important to understand how de-duplication works and be aware that there are limitations to the algorithm that might cause a unique item to be marked as a duplicate during the export process.</span></span>
  
## <a name="how-duplicate-messages-are-identified"></a><span data-ttu-id="27a8c-110">重複するメッセージを識別する方法</span><span class="sxs-lookup"><span data-stu-id="27a8c-110">How duplicate messages are identified</span></span>

<span data-ttu-id="27a8c-111">Office 365 の電子的証拠開示のツールは、メッセージが重複しているかどうかを確認するのには次の電子メールのプロパティの組み合わせを使用します。</span><span class="sxs-lookup"><span data-stu-id="27a8c-111">Office 365 eDiscovery tools use a combination of the following email properties to determine whether a message is a duplicate:</span></span>
  
- <span data-ttu-id="27a8c-p102">**InternetMessageId** - このプロパティは、特定のメッセージの特定のバージョンを参照するグローバルに一意の識別子には、電子メール メッセージのインターネット メッセージ id を指定します。この ID は、送信者の電子メール クライアント プログラムまたはメッセージの送信元ホストのメール システムによって生成されます。ユーザーは、複数の受信者にメッセージを送信する場合、メッセージの各インスタンスで同じをインターネット メッセージ ID になります。さまざまなメッセージ識別子は、元のメッセージにそれ以降のリビジョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27a8c-p102">**InternetMessageId** - This property specifies the Internet message identifier of an email message, which is a globally unique identifier that refers to a specific version of a specific message. This ID is generated by the sender's email client program or host email system that sends the message. If a person sends a message to more than one recipient, the Internet message ID will be the same for each instance of the message. Subsequent revisions to the original message will receive a different message identifier.</span></span> 
    
- <span data-ttu-id="27a8c-p103">**ConversationTopic** - このプロパティは、メッセージのテーマ スレッドの件名を指定します。**ConversationTopic**プロパティの値は、全体の会話のトピックを説明する文字列です。この活動は、最初のメッセージと、初期メッセージに返信を送信するすべてのメッセージで構成されます。同じ会話内でのメッセージは、 **ConversationTopic**プロパティに同じ値を持ちます。このプロパティの値は、通常は会話を生成する最初のメッセージの件名です。</span><span class="sxs-lookup"><span data-stu-id="27a8c-p103">**ConversationTopic** - his property specifies the subject of the conversation thread of a message. The value of the **ConversationTopic** property is the string that describes the overall topic of the conversation. A conservation consists of an initial message and all messages sent in reply to the initial message. Messages within the same conversation have the same value for the **ConversationTopic** property. The value of this property is typically the Subject line from the initial message that spawned the conversation.</span></span> 
    
- <span data-ttu-id="27a8c-p104">**BodyTagInfo** - これは、内部の Exchange ストアのプロパティです。このプロパティの値は、メッセージの本文内のさまざまな属性を確認することによって計算されます。このプロパティを使用して、メッセージの本文内の相違点を識別します。</span><span class="sxs-lookup"><span data-stu-id="27a8c-p104">**BodyTagInfo** - This is an internal Exchange store property. The value of this property is calculated by checking various attributes in the body of the message. This property is used to identify differences in the body of messages.</span></span> 
    
<span data-ttu-id="27a8c-p105">エクスポートの際に電子的証拠開示、これら 3 つのプロパティは、検索条件に一致するすべてのメッセージに対して比較されます。これらのプロパティが 2 つ (以上) のメッセージが同じ場合は、それらのメッセージが重複しているように決定され、重複除外が有効になっている場合にメッセージのコピーを 1 つだけがエクスポートされることになります。エクスポートされたメッセージは、[ソース アイテム"と呼ばれます。エクスポートした検索結果に含まれている**Results.csv**と**Manifest.xml**レポートでは、重複したメッセージに関する情報が含まれます。**Results.csv**ファイル内**の項目に重複する**列の値のことで、重複するメッセージが識別されます。この列の値は、エクスポートされたメッセージの**項目の Id**列の値と一致します。</span><span class="sxs-lookup"><span data-stu-id="27a8c-p105">During the eDiscovery export process, these three properties are compared for every message that matches the search criteria. If these properties are identical for two (or more) messages, those messages are determined to be duplicates and the result is that only one copy of the message will be exported if de-duplication is enabled. The message that is exported is known as the "source item". Information about duplicate messages is included in the **Results.csv** and **Manifest.xml** reports that are included with the exported search results. In the **Results.csv** file, a duplicate message is identified by having a value in the **Duplicate to Item** column. The value in this column matches the value in the **Item Identity** column for the message that was exported.</span></span> 
  
<span data-ttu-id="27a8c-p106">次の図には、重複したメッセージが表示する検索結果のエクスポートは**Results.csv**と**Manifest.xml**レポートに表示されます。これらのレポートには、データ重複除外アルゴリズムで使用される前に説明した、電子メール プロパティが含まれていません。代わりに、レポートには、Exchange ストアでのアイテムに割り当てられている**アイテムの Id**プロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="27a8c-p106">The following graphics show how duplicate messages are displayed in the **Results.csv** and **Manifest.xml** reports that are exported with the search results. These reports don't include the email properties previously described, which are used in the de-duplication algorithm. Instead, the reports include the **Item Identity** property that is assigned to items by the Exchange store.</span></span> 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a><span data-ttu-id="27a8c-133">Results.csv のレポート (Excel で表示)</span><span class="sxs-lookup"><span data-stu-id="27a8c-133">Results.csv report (viewed in Excel)</span></span>
  
![Results.csv レポートに重複するアイテムについての情報を表示します。](media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a><span data-ttu-id="27a8c-135">Manifest.xml のレポート (Excel で表示)</span><span class="sxs-lookup"><span data-stu-id="27a8c-135">Manifest.xml report (viewed in Excel)</span></span>
  
![Manifest.xml レポートに重複するアイテムについての情報を表示します。](media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
<span data-ttu-id="27a8c-p107">さらに、重複したメッセージからの他のプロパティは、レポートをエクスポートに含められます。これには、重複するメッセージにある、メッセージが配布グループに送信されたかどうか、および [cc]、または [bcc] に別のユーザーに指定された受信者にメッセージがされているかどうか、メールボックスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="27a8c-p107">Additionally, other properties from duplicate messages are included in the export reports. This includes the mailbox the duplicate message is located in, whether the message was sent to a distribution group, and whether the message was Cc'd or Bcc'd to another user.</span></span>
  
## <a name="limitations-of-the-de-duplication-algorithm"></a><span data-ttu-id="27a8c-139">データ重複除外アルゴリズムの制限事項</span><span class="sxs-lookup"><span data-stu-id="27a8c-139">Limitations of the de-duplication algorithm</span></span>

<span data-ttu-id="27a8c-p108">重複としてマークを取得するのには固有のアイテムを引き起こす可能性のあるデータ重複除外アルゴリズムのいくつかの既知の制限事項があります。オプションのデータ重複除外機能を使用するかどうかを決定するためにこれらの制限事項を理解する重要です。</span><span class="sxs-lookup"><span data-stu-id="27a8c-p108">There are some known limitations of the de-duplication algorithm that might cause unique items to get marked as duplicates. It's important to understand these limitations so you can decide whether or not to use the optional de-duplication feature.</span></span>
  
<span data-ttu-id="27a8c-p109">状況の 1 つ、重複除外機能可能性があります誤って重複メッセージを識別されエクスポートしません (が、まだエクスポート レポート内の重複として引用すること) があります。これらは、ユーザーが編集、送信しないメッセージです。、たとえばユーザーは、Outlook でメッセージを選択して、メッセージの内容をコピーし、新しいメッセージに貼り付けます。ユーザーが変更、コピーの 1 つを削除するか、添付ファイルを追加するまたは件名または本文自体を変更します。これら 2 つのメッセージには、電子的証拠開示検索クエリが一致すると、検索結果をエクスポートする際に、重複除外が有効になっている場合、メッセージの 1 つだけがエクスポートされます。元のメッセージまたはコピーされたメッセージが変更された場合でも変更後のメッセージのどちらに送信され、 **InternetMessageId**、 **BodyTagInfo** 、 **ConversationTopic**プロパティの値は更新されませんでしたので。説明したよう、レポートをエクスポートに両方のメッセージが表示されますが、</span><span class="sxs-lookup"><span data-stu-id="27a8c-p109">There's one situation where the de-duplication feature might mistakenly identify a message as a duplicate and not export it (but still cite it as a duplicate in the export reports). These are messages that a user edits but doesn't send. For example, let's say a user selects a message in Outlook, copies the contents of the message, and then pastes it in a new message. Then the user changes one of the copies by removing or adding an attachment, or changing the subject line or the body itself. If these two messages match the query of an eDiscovery search, only one of the messages will be exported if de-duplication is enabled when the search results are exported. So even though the original message or the copied message was changed, neither of the revised messages were sent and therefore the values of **InternetMessageId**, **ConversationTopic** and **BodyTagInfo** properties weren't updated. But as previously explained, both messages will be listed in the export reports</span></span> 
  
<span data-ttu-id="27a8c-p110">一意なメッセージもとしてマークできる重複証拠保全またはインプレース保持しているメールボックスの場合、コピー オン ライト ページ保護機能が有効になっているときに注意してください。書き込み時コピー機能、元のメッセージのコピー (およびユーザーの回復可能なアイテム] フォルダーの [バージョン] フォルダーに保存) を元の項目のリビジョンを保存する前にします。この例では、重複したメッセージとして改訂版のコピーと元のメッセージで、[回復可能なアイテム] フォルダー) を考慮する場合があり、それらの 1 つだけがエクスポートすること。</span><span class="sxs-lookup"><span data-stu-id="27a8c-p110">Note that unique messages can also be marked as duplicates when the Copy-on-Write page protection feature is enabled, as in the case of a mailbox being on Litigation Hold or In-Place Hold. The Copy-on-Write feature copies the original message (and saves it in the Versions folder of the user's Recoverable Items folder) before the revision to original item is saved. In this case, the revised copy and the original message (in the Recoverable Items folder) might be considered as duplicate messages and therefore only one of them would be exported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="27a8c-p111">データ重複除外アルゴリズムの制限は、検索結果の品質に影響を与える可能性がありますし、べきではない有効にした場合の重複除外アイテムをエクスポートするとき。このセクションで説明する状況は、検索結果に影響する可能性がありますが、重複しているように最も可能性の高い項目の数を減らしたい場合は、重複除外を有効にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="27a8c-p111">If the limitations of the de-duplication algorithm might impact the quality of your search results, then you shouldn't enable de-duplication when you export items. If the situations described in this section are unlikely to be a factor in your search results, and you want to reduce the number of items most likely to be duplicates, then you should consider enabling de-duplication.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="27a8c-154">詳細情報</span><span class="sxs-lookup"><span data-stu-id="27a8c-154">More information</span></span>

- <span data-ttu-id="27a8c-155">この資料の情報は、電子的証拠開示ツールは、次のいずれかを使用して検索結果をエクスポートするときに適用。</span><span class="sxs-lookup"><span data-stu-id="27a8c-155">The information in this article is applicable when exporting search results using one of the following eDiscovery tools:</span></span>
    
  - <span data-ttu-id="27a8c-156">Office 365 のセキュリティでのコンテンツの検索&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="27a8c-156">Content search in the Office 365 Security &amp; Compliance Center</span></span>
    
  - <span data-ttu-id="27a8c-157">Exchange Online のインプレース電子情報開示</span><span class="sxs-lookup"><span data-stu-id="27a8c-157">In-Place eDiscovery in Exchange Online</span></span>
    
  - <span data-ttu-id="27a8c-158">SharePoint Online の電子情報開示センター</span><span class="sxs-lookup"><span data-stu-id="27a8c-158">The eDiscovery Center in SharePoint Online</span></span>
    
- <span data-ttu-id="27a8c-159">検索結果のエクスポートの詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="27a8c-159">For more information about exporting search results, see:</span></span>
    
  - [<span data-ttu-id="27a8c-160">Office 365 のセキュリティの検索結果のエクスポート&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="27a8c-160">Export search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
  - [<span data-ttu-id="27a8c-161">Office 365 のセキュリティ コンテンツの検索レポートをエクスポートする&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="27a8c-161">Export a Content Search report from the Office 365 Security &amp; Compliance Center</span></span>](export-a-content-search-report.md)
    
  - [<span data-ttu-id="27a8c-162">PST ファイルにエクスポート、インプレース電子証拠開示の検索結果</span><span class="sxs-lookup"><span data-stu-id="27a8c-162">Export In-Place eDiscovery search results to a PST file</span></span>](https://go.microsoft.com/fwlink/p/?linkid=832671)
    
  - [<span data-ttu-id="27a8c-163">電子情報開示センターでのコンテンツのエクスポートとレポートの作成</span><span class="sxs-lookup"><span data-stu-id="27a8c-163">Export content and create reports in the eDiscovery Center</span></span>](https://support.office.com/article/7b2ea190-5f9b-4876-86e5-4440354c381a)