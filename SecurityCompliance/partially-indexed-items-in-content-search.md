---
title: Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/11/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.UnindexedItemsLearnMore
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: d1691de4-ca0d-446f-a0d0-373a4fc8487b
description: 'Exchange と Office 365 のセキュリティを使用して実行、コンテンツの検索に含めることができる SharePoint のインデックスの項目について&amp;コンプライアンス センターです。 '
ms.openlocfilehash: 4624985a9c80313d0222470e6cfb2c56495f2142
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531677"
---
# <a name="partially-indexed-items-in-content-search-in-office-365"></a><span data-ttu-id="7cfb7-103">Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="7cfb7-103">Partially indexed items in Content Search in Office 365</span></span>

<span data-ttu-id="7cfb7-p101">Office 365 のセキュリティを実行するコンテンツの検索&amp;コンプライアンス センターが検索を実行すると、予定の検索結果に部分的にインデックス付きのアイテムが自動的に含まれます。部分的にインデックス付きのアイテムは、Exchange メールボックスのアイテムを何らかの理由により検索用インデックスが作成されなかった完全にビジネス サイトの SharePoint と OneDrive のドキュメントです。ファイルが通常、部分的にインデックス付きの項目に含まれている Exchange では、-、ファイルの種類のインデックスを作成することはできませんが、電子メール メッセージに追加されます。ここでは、他の理由をいくつかのアイテムの検索用インデックスを作成することはできません理由とは、検索を実行すると、部分的にインデックス付きの項目として返されます。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p101">A Content Search that you run from the Office 365 Security &amp; Compliance Center automatically includes partially indexed items in the estimated search results when you run a search. Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search. In Exchange, a partially indexed item typically contains a file—of a file type that can't be indexed—that is attached to an email message. Here are some other reasons why items can't be indexed for search and are returned as partially indexed items when you run a search:</span></span> 
  
- <span data-ttu-id="7cfb7-108">ファイルの種類が認識できないか、インデックス作成でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-108">The file type is unrecognized or unsupported for indexing.</span></span>
    
-  <span data-ttu-id="7cfb7-109">イメージ ファイルの有効なハンドラーがない場合、添付ファイルがあるメッセージこれは、部分的にインデックス付きの電子メール アイテムの最も一般的な原因です。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-109">Messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items.</span></span> 
    
- <span data-ttu-id="7cfb7-110">この種のファイルのインデックス付けはサポートされているが、特定のファイルでインデックス付けエラーが発生した。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-110">The file type is supported for indexing but an indexing error occurred for a specific file.</span></span>
    
- <span data-ttu-id="7cfb7-111">メール メッセージに添付されているファイルが多すぎる。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-111">Too many files attached to an email message.</span></span>
    
- <span data-ttu-id="7cfb7-112">メール メッセージの添付ファイルが大きすぎる。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-112">A file attached to an email message is too large.</span></span>
    
- <span data-ttu-id="7cfb7-113">ファイルは Microsoft 以外の手法によって暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-113">A file is encrypted with non-Microsoft technologies.</span></span>
    
- <span data-ttu-id="7cfb7-114">ファイルがパスワードで保護されている。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-114">A file is password-protected.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7cfb7-p102">Office 365 組織内にある部分的にインデックスが設定されたサイズでボリュームを 12% より小さいコンテンツの 1% 未満です。ボリュームとサイズの違いの理由は、サイズの大きいファイルで、完全にインデックスを作成できないコンテンツが含まれているの可能性が高くです。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p102">Most Office 365 organizations have less than 1% of content by volume and less than 12% by size that is partially indexed. The reason for the difference between volume and size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span> 
  
<span data-ttu-id="7cfb7-p103">法的な調査は、組織が部分的にインデックス付きの項目を確認するのには必要な可能性があります。ローカル コンピューターまたは電子的証拠開示の Office 365 の詳細な分析の結果を準備するときに検索結果をエクスポートする場合は、部分的にインデックス付きの項目を含めるかどうかを指定することもできます。詳細については、 [Investigating は、Office 365 の電子的証拠開示の項目を部分的にインデックス](investigating-partially-indexed-items-in-ediscovery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p103">For legal investigations, your organization may be required to review partially indexed items. You can also specify whether to include partially indexed items when you export search results to a local computer or when you prepare the results for analysis with Office 365 Advanced eDiscovery. For more information, see [Investigating partially indexed items in Office 365 eDiscovery](investigating-partially-indexed-items-in-ediscovery.md).</span></span>
  
## <a name="file-types-not-indexed-for-search"></a><span data-ttu-id="7cfb7-120">検索用にインデックス付けされないファイルの種類</span><span class="sxs-lookup"><span data-stu-id="7cfb7-120">File types not indexed for search</span></span>

<span data-ttu-id="7cfb7-p104">ビットマップなどのファイルや MP3 ファイルの特定の種類は、コンテンツ インデックスを作成することができますが含まれていません。その結果、Exchange サーバーをインデックスの検索と SharePoint を実行しないこれらの種類のファイルでフルテキスト インデックスを作成します。これらの種類のファイルは、サポートされていないファイルの種類と見なされます。対象のフルテキスト インデックス処理が無効で、既定または管理者のいずれかのファイルの種類が用意されています。サポートされていないと無効になっているファイルの種類は、コンテンツの検索でインデックス付けされない項目としてラベルが付けられます。前述したように、部分的にインデックス付きのアイテムは、検索を実行すると、検索結果のセットに含めることが、ローカル コンピューターに検索結果をエクスポートまたは検索結果を高度な電子的証拠開示に備えます。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p104">Certain types of files, such as Bitmap or MP3 files, don't contain content that can be indexed. As a result, the search indexing servers in Exchange and SharePoint don't perform full-text indexing on these types of files. These types of files are considered to be unsupported file types. There are also file types for which full-text indexing has been disabled, either by default or by an administrator. Unsupported and disabled file types are labeled as unindexed items in Content Searches. As previously stated, partially indexed items can be included in the set of search results when you run a search, export the search results to a local computer, or prepare search results for Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="7cfb7-127">サポートされているファイル形式と無効なファイル形式のリストは、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-127">For a list of supported and disabled file formats, see the following topics:</span></span>
  
- <span data-ttu-id="7cfb7-128">**Exchange** - [Exchange 検索によってインデックス付けされたファイルの形式](https://go.microsoft.com/fwlink/p/?LinkID=386618)</span><span class="sxs-lookup"><span data-stu-id="7cfb7-128">**Exchange** - [File formats indexed by Exchange Search](https://go.microsoft.com/fwlink/p/?LinkID=386618)</span></span>
    
- <span data-ttu-id="7cfb7-129">**Exchange** - [Get SearchDocumentFormat](https://go.microsoft.com/fwlink/p/?LinkID=724037)</span><span class="sxs-lookup"><span data-stu-id="7cfb7-129">**Exchange** - [Get-SearchDocumentFormat](https://go.microsoft.com/fwlink/p/?LinkID=724037)</span></span>
    
- <span data-ttu-id="7cfb7-130">**SharePoint** - [既定のファイル名拡張子をクロールし SharePoint でのファイルの種類を解析](https://go.microsoft.com/fwlink/p/?LinkID=404033)</span><span class="sxs-lookup"><span data-stu-id="7cfb7-130">**SharePoint** - [Default crawled file name extensions and parsed file types in SharePoint](https://go.microsoft.com/fwlink/p/?LinkID=404033)</span></span>
    

  
## <a name="messages-and-documents-with-partially-indexed-file-types-can-be-returned-in-search-results"></a><span data-ttu-id="7cfb7-131">メッセージや文書を部分的にインデックス付けされたファイルが検索結果の型を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-131">Messages and documents with partially indexed file types can be returned in search results</span></span>

<span data-ttu-id="7cfb7-p105">部分的にインデックス付きのファイルの添付ファイルを含むすべての電子メール メッセージ、または部分的にインデックス付きのすべての SharePoint ドキュメントが自動的に部分的にインデックス付きの項目として返されます。その他のメッセージまたは電子メール メッセージの**件名**プロパティなど、ドキュメントのプロパティとドキュメントの**タイトル**や**作成者**のプロパティは、インデックスを作成し、検索対象となる利用可能なためにです。などの「財務」のキーワード検索は返品、部分的にインデックス付きファイルを添付した電子メール メッセージの件名または、ファイル名や文書のタイトルにキーワードが表示された場合。ただし場合は、キーワード、ファイルの本文のみが表示されたら、メッセージやドキュメントは返される部分的にインデックス付きの項目として。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p105">Not every email message with an partially indexed file attachment or every partially indexed SharePoint document is automatically returned as an partially indexed item. That's because other message or document properties, such as the **Subject** property in email messages and the **Title** or **Author** properties for documents are indexed and available to be searched. For example, a keyword search for "financial" will return items with an partially indexed file attachment if that keyword appears in the subject of an email message or in the file name or title of a document. However, if the keyword appears only in the body of the file, the message or document would be returned as a partially indexed item.</span></span> 
  
<span data-ttu-id="7cfb7-p106">同様に、部分的にインデックス付きのファイルの添付ファイルと、部分的にインデックス付きのファイルの種類のドキュメントとメッセージは、他のメッセージまたはドキュメントのプロパティは、インデックスを作成し、検索可能な検索条件に一致すると、検索結果に取り込まれます。検索用インデックス付けされたメッセージのプロパティには、メッセージの本文で送信および受信した日付、送信者、受信者、添付ファイル、およびテキストのファイル名が含まれます。検索用インデックス付けされたドキュメントのプロパティには、作成および変更された日付が含まれます。たとえメッセージの添付ファイルがある場合、部分的にインデックス付きの項目、メッセージ含まれます、通常の検索結果にその他のメッセージまたはドキュメントのプロパティの値が検索条件に一致する場合。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p106">Similarly, messages with partially indexed file attachments and documents of an partially indexed file type are included in search results when other message or document properties, which are indexed and searchable, meet the search criteria. Message properties that are indexed for search include sent and received dates, sender and recipient, the file name of an attachment, and text in the message body. Document properties indexed for search include created and modified dates. So even though a message attachment may be an partially indexed item, the message will be included in the regular search results if the value of other message or document properties matches the search criteria.</span></span>
  
<span data-ttu-id="7cfb7-140">セキュリティの検索機能を使用して検索することができます電子メールとドキュメントのプロパティの一覧については&amp;コンプライアンス センターでは、[キーワード クエリとコンテンツの検索の検索条件](keyword-queries-and-search-conditions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-140">For a list of email and document properties that you can search for by using the Search feature in the Security &amp; Compliance Center, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  

  
## <a name="partially-indexed-items-included-in-the-search-results"></a><span data-ttu-id="7cfb7-141">部分的にインデックス付きのアイテムが検索結果に含まれています。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-141">Partially indexed items included in the search results</span></span>
<span data-ttu-id="7cfb7-142"><a name="unindexeditemsresults"> </a></span><span class="sxs-lookup"><span data-stu-id="7cfb7-142"></span></span>

<span data-ttu-id="7cfb7-p107">組織の特定し、は何か、その内容、および特定の調査に関連しているかどうかを決定するのには部分的にインデックス付きの項目の追加の分析を実行する必要があります。説明したようが検索されたコンテンツの場所で部分的にインデックス付きのアイテムは、予定の検索結果に自動的に含まれるです。検索結果をエクスポートするか、検索結果を高度な電子的証拠開示に備える場合、これらの部分的にインデックス付きのアイテムを含めるためのオプションがあります。部分的にインデックス付きのアイテムが検索結果をエクスポートする場合や、高度な電子的証拠開示の準備をするときは、形式が認識されない、暗号化されている、または他の理由によりインデックスが作成されなかったアイテムを含めるためのオプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p107">Your organization might be required to identify and perform additional analysis on partially indexed items to determine what they are, what they contain, and whether they're relevant to a specific investigation. As previously explained, the partially indexed items in the content locations that are searched are automatically included with the estimated search results. You have the option to include these partially indexed items when you export search results or prepare the search results for Advanced eDiscovery. To include partially indexed items when you're exporting search results or preparing them for Advanced eDiscovery, select one of the options to include items that have an unrecognized format, are encrypted, or weren't indexed for other reasons.</span></span>
  
<span data-ttu-id="7cfb7-147">次を部分的にインデックス付きの項目について注意してください。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-147">Keep the following in mind about partially indexed items:</span></span>
  
- <span data-ttu-id="7cfb7-148">コンテンツの検索を実行すると総数と総合サイズ (検索クエリによって返される) 部分的にインデックス付きのアイテムの表示されます詳細ウィンドウで、検索の統計情報のインデックスを持たないアイテム」としてラベル付けされました。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-148">When you run a content search, the total number and size of partially indexed items (returned by the search query) are displayed in search statistics in the details pane, as labeled as "unindexed items".</span></span>
    
- <span data-ttu-id="7cfb7-p108">として Exchange アイテムをダウンロードするオプションを選択した場合、Exchange の部分的にインデックス付きのアイテムが先に置かれる、または個別のメッセージとしては、各メールボックスの別の PST ファイルにエクスポートされた検索結果をエクスポートすると、部分的にインデックス付きの項目が含まれますメッセージです。部分的にインデックス付きの SharePoint アイテムは、 **Uncrawlable**をという名前のフォルダーにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p108">When you export search results and include partially indexed items, partially indexed Exchange items are exported to a separate PST file for each mailbox in which they are located, or as individual messages if you select the option to download Exchange items as messages. partially indexed SharePoint items are exported to a folder named **Uncrawlable**.</span></span>
    
- <span data-ttu-id="7cfb7-p109">コンテンツの特定の場所または組織内のすべてのコンテンツの場所の検索、検索から結果をエクスポートする場合は、検索条件に一致する項目が含まれているコンテンツの場所からインデックスを持たないアイテムのみがエクスポートされます。つまり、メールボックス内またはサイト内検索結果が見つからない場合、そのメールボックス ストアまたはサイトのインデックスを持たない項目、エクスポートされません。この理由は、組織内の場所の多数の部分的にインデックス付きのアイテムをエクスポートする可能性がありますエクスポート エラーの可能性が高く、エクスポートし、検索結果のダウンロードにかかる時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p109">If the search that you're exporting results from was a search of specific content locations or all content locations in your organization, only the unindexed items from content locations that contain items that match the search criteria will be exported. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. The reason for this is that exporting partially indexed items from lots of locations in the organization might increase the likelihood of export errors and increase the time it takes to export and download the search results.</span></span>
    
    <span data-ttu-id="7cfb7-154">(任意のキーワードを削除して、検索クエリから) ですべての項目を返す検索を構成する、一部だけをエクスポートしを検索のすべてのコンテンツの場所から部分的にインデックス付きのアイテムをエクスポートするには、インデックス作成済みアイテム] をクリックして**のみの検索結果をエクスポートする場合認識できない形式では、暗号化されている、または他の理由によりインデックスが作成されなかった****出力オプション**] の下)。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-154">To export partially indexed items from all content locations for a search, configure the search to return all items (by removing any keywords from the search query) and then export only partially indexed items when you export the search results (by clicking **Only items that have an unrecognized format, are encrypted, or weren't indexed for other reasons** under **Output options**).</span></span>
    
- <span data-ttu-id="7cfb7-p110">検索の結果にすべてのメールボックス アイテムを含めるように選択する場合、または検索クエリのキーワードを指定していないまたはのみ、日付の範囲を指定する場合は、部分的にインデックス付きのアイテムは、部分的にインデックス付きの項目を格納する PST ファイルにはコピーされません。通常の検索結果で、部分的にインデックス付きのアイテムを含むすべてのアイテムが自動的に含まれているためにです。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p110">If you choose to include all mailbox items in the search results, or if a search query doesn't specify any keywords or only specifies a date range, partially indexed items might not be copied to the PST file that contains the partially indexed items. This is because all items, including any partially indexed items, will be automatically included in the regular search results.</span></span>
    
- <span data-ttu-id="7cfb7-p111">部分的にインデックス付きの項目は、プレビューを表示するのには使用できません。検索によって返される部分的にインデックス付きの項目を表示するのには検索結果をエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p111">Partially indexed items aren't available to be previewed. You have to export the search results to view partially indexed items returned by the search.</span></span>

## <a name="partially-indexed-items-excluded-from-the-search-results"></a><span data-ttu-id="7cfb7-159">部分的にインデックス付きのアイテムが検索結果から除外</span><span class="sxs-lookup"><span data-stu-id="7cfb7-159">Partially indexed items excluded from the search results</span></span>

<span data-ttu-id="7cfb7-p112">アイテムのインデックスは部分的に検索クエリの抽出条件を満たしていない場合は、検索結果に部分的にインデックス付きの項目として含まれている場合ができません。つまり、アイテムは、検索結果から除外されます。、たとえば、検索を実行し、含まれていないすべてのキーワードまたはプロパティのすべてのコンテンツを追加するためです。クエリの日付範囲の条件を含めることはできます。その日付の範囲外にある場合、部分的にインデックス付きの項目は、部分的にインデックス付きの項目として含まれているができません。日付の範囲は、部分的にインデックス付きの項目を検索結果から除外するのには効果的な方法です。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p112">If an item is partially indexed but it doesn't meet the search query criteria, it won't be included as a partially indexed item in the search results. In other words, the item is excluded from the search results. For example, let's say you run a search and don't include any keywords or properties because you want to include all content. But you include a date range condition for the query. If a partially indexed item falls outside of that date range, it won't be included as a partially indexed item. Date ranges are an effective way to exclude partially indexed items from your search results.</span></span>
  
<span data-ttu-id="7cfb7-166">同様に、検索の結果をエクスポートすると、部分的にインデックス付きの項目を含める場合は、検索結果から除外された部分的にインデックス付きのアイテムはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-166">Similarly, if you choose to include partially indexed items when you export the results of a search, partially indexed items that were excluded from the search results won't be exported.</span></span>
  
<span data-ttu-id="7cfb7-p113">この規則に例外が 1 つは、電子的証拠開示のサポート案件に関連付けられているクエリに基づく保留リストを作成するときです。クエリ ベースの保留リストを作成すると、保留中のすべての部分的にインデックス付けされたアイテムが配置されます。これには、検索クエリの抽出条件に一致しない一部のインデックス付きの項目と部分的にインデックス付きのアイテムを日付の範囲の条件を超える場合がありますが含まれます。ベースのクエリを作成する方法の詳細を保持しているは、[電子的証拠開示の場合](ediscovery-cases.md#step-4-place-content-locations-on-hold)で手順 4 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p113">One exception to this rule is when you create a query-based hold that's associated with an eDiscovery case. If you create a query-based hold, all partially indexed items are placed on hold. This includes partially indexed items that don't match the search query criteria and partially indexed items that might fall outside of a date range condition. For more information about creating query-based holds, see Step 4 in  [eDiscovery cases in the Office 365 Security & Compliance Center](ediscovery-cases.md#step-4-place-content-locations-on-hold).</span></span>
  
## <a name="indexing-limits-for-messages-in-content-search"></a><span data-ttu-id="7cfb7-171">コンテンツの検索でのメッセージのインデックス作成の制限</span><span class="sxs-lookup"><span data-stu-id="7cfb7-171">Indexing limits for messages in Content Search</span></span>

<span data-ttu-id="7cfb7-172">次の表では、Office 365 でのコンテンツの検索で部分的にインデックス付きの項目として返される電子メール メッセージのインデックスの制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-172">The following table describes the indexing limits that might result in an email message being returned as a partially indexed item in a Content Search in Office 365.</span></span>
  
<span data-ttu-id="7cfb7-173">SharePoint ドキュメントの制限値のインデックスのリストは、 [SharePoint Online の検索制限](https://support.office.com/article/7c06e9ed-98b6-4304-a900-14773a8fa32f)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-173">For a list of indexing limits for SharePoint documents, see [Search limits for SharePoint Online](https://support.office.com/article/7c06e9ed-98b6-4304-a900-14773a8fa32f).</span></span>
  
|<span data-ttu-id="7cfb7-174">**インデックスの制限**</span><span class="sxs-lookup"><span data-stu-id="7cfb7-174">**Indexing limit**</span></span>|<span data-ttu-id="7cfb7-175">**メモ**</span><span class="sxs-lookup"><span data-stu-id="7cfb7-175">**Maximum value**</span></span>|<span data-ttu-id="7cfb7-176">**説明**</span><span class="sxs-lookup"><span data-stu-id="7cfb7-176">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7cfb7-177">(Excel ファイルを除く) の添付ファイルの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="7cfb7-177">Maximum attachment size (excluding Excel files)</span></span>  <br/> |<span data-ttu-id="7cfb7-178">150 MB</span><span class="sxs-lookup"><span data-stu-id="7cfb7-178">150 MB</span></span>  <br/> |<span data-ttu-id="7cfb7-p114">インデックス作成のための解析は、電子メールの添付ファイルの最大サイズです。インデックスを作成すると、この制限よりも大きい添付ファイルを解析しないし、一部がインデックスを作成、添付ファイル付きメッセージがマークされます。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p114">The maximum size of an email attachment that will parse for indexing. Any attachment that's larger than this limit won't be parsed for indexing, and the message with the attachment will be marked as partially indexed.  </span></span><br/><br/> <span data-ttu-id="7cfb7-181">**注:** 解析は、インデックス サービス、添付ファイルからテキストを抽出し、句読点やスペースなどの不要な文字を削除、インデックスに保存されます (プロセスのトークン化と呼ばれる)、単語のテキストを分割し、プロセスです。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-181">**Note:** Parsing is the process where the indexing service extracts text from the attachment, removes unnecessary characters like punctuation and spaces, and then divides the text into words (in a process called tokenization), that are then stored in the index.</span></span>           |
|<span data-ttu-id="7cfb7-182">Excel ファイルの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="7cfb7-182">Maximum size of Excel files</span></span>  <br/> |<span data-ttu-id="7cfb7-183">4 MB</span><span class="sxs-lookup"><span data-stu-id="7cfb7-183">4 MB</span></span>  <br/> |<span data-ttu-id="7cfb7-p115">Excel ファイルの最大サイズは、サイト上にあるか、インデックス作成のために解析される電子メール メッセージに添付します。任意の Excel ファイルがこの制限値を解析できないとファイルまたは電子メールの添付ファイルをメッセージとしてマークされますインデックスよりも大きいです。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p115">The maximum size of an Excel file located on a site or attached to an email message that will be parsed for indexing. Any Excel file that's larger than this limit won't be parsed, and the file or the email the message with the file attachment will be marked as unindexed.</span></span>  <br/> |
|<span data-ttu-id="7cfb7-186">添付ファイルの最大数</span><span class="sxs-lookup"><span data-stu-id="7cfb7-186">Maximum number of attachments</span></span>  <br/> |<span data-ttu-id="7cfb7-187">250</span><span class="sxs-lookup"><span data-stu-id="7cfb7-187">250</span></span>  <br/> |<span data-ttu-id="7cfb7-p116">インデックス作成のために解析される電子メール メッセージに添付ファイルの最大数です。メッセージに 250 を超える添付ファイルがある場合は、最初の 250 の添付ファイルが解析され、インデックスが作成し、メッセージ解析されないその他の添付ファイルが必要があるために一部がインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p116">The maximum number of files attached to an email message that will be parsed for indexing. If a message has more than 250 attachments, the first 250 attachments are parsed and indexed, and the message is marked as partially indexed because it had additional attachments that weren't parsed.</span></span>  <br/> |
|<span data-ttu-id="7cfb7-190">添付ファイルの最大の深さ</span><span class="sxs-lookup"><span data-stu-id="7cfb7-190">Maximum attachment depth</span></span>  <br/> |<span data-ttu-id="7cfb7-191">30</span><span class="sxs-lookup"><span data-stu-id="7cfb7-191">30</span></span>  <br/> |<span data-ttu-id="7cfb7-p117">解析される入れ子になった添付ファイルの最大数です。などは、それに接続されている別のメッセージを電子メール メッセージと添付の Word 文書が添付されたメッセージには、Word 文書と、添付されたメッセージがインデックスを作成します。この現象は、入れ子になった添付ファイルの最大 30 個まで続行されます。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p117">The maximum number of nested attachments that are parsed. For example, if an email message has another message attached to it and the attached message has an attached Word document, the Word document and the attached message will be indexed. This behavior will continue for up to 30 nested attachments.</span></span>  <br/> |
|<span data-ttu-id="7cfb7-195">接続されているイメージの最大数</span><span class="sxs-lookup"><span data-stu-id="7cfb7-195">Maximum number of attached images</span></span>  <br/> |<span data-ttu-id="7cfb7-196">0</span><span class="sxs-lookup"><span data-stu-id="7cfb7-196">0</span></span>  <br/> |<span data-ttu-id="7cfb7-197">電子メール メッセージに関連付けられているイメージは、パーサーによってスキップされ、インデックスが作成されていません。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-197">An image that's attached to an email message is skipped by the parser and isn't indexed.</span></span>  <br/> |
|<span data-ttu-id="7cfb7-198">項目を解析するのにかかった時間が最大</span><span class="sxs-lookup"><span data-stu-id="7cfb7-198">Maximum time spent parsing an item</span></span>  <br/> |<span data-ttu-id="7cfb7-199">30 秒</span><span class="sxs-lookup"><span data-stu-id="7cfb7-199">30 seconds</span></span>  <br/> |<span data-ttu-id="7cfb7-p118">最大 30 秒間は、インデックス作成のための項目を解析中に費やされています。解析の時間は、30 秒を超えている場合に部分的にインデックス付けされたアイテムがマークされます。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p118">A maximum of 30 seconds is spent parsing an item for indexing. If the parsing time exceeds 30 seconds, the item is marked as partially indexed.</span></span>  <br/> |
|<span data-ttu-id="7cfb7-202">最大のパーサの出力</span><span class="sxs-lookup"><span data-stu-id="7cfb7-202">Maximum parser output</span></span>  <br/> |<span data-ttu-id="7cfb7-203">200 万文字</span><span class="sxs-lookup"><span data-stu-id="7cfb7-203">2 million characters</span></span>  <br/> |<span data-ttu-id="7cfb7-p119">インデックスが設定されたパーサーからのテキスト出力の最大の量。たとえば、パーサーは、ドキュメントから 8 個の文字を抽出、その最初の 200万文字のみにインデックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p119">The maximum amount of text output from the parser that's indexed. For example, if the parser extracted 8 million characters from a document, only the first 2 million characters are indexed.</span></span>  <br/> |
|<span data-ttu-id="7cfb7-206">最大のコメント トークン</span><span class="sxs-lookup"><span data-stu-id="7cfb7-206">Maximum annotation tokens</span></span>  <br/> |<span data-ttu-id="7cfb7-207">200万</span><span class="sxs-lookup"><span data-stu-id="7cfb7-207">2 million</span></span>  <br/> |<span data-ttu-id="7cfb7-p120">電子メール メッセージのインデックスを作成するときは、その単語をインデックス付けする方法を指定する別の処理命令に各単語が付きます。処理命令の各セットは、コメント トークンと呼ばれます。Office 365 のサービスの品質を維持するためには、電子メール メッセージのコメント トークンを 2 個の制限があります。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p120">When an email message is indexed, each word is annotated with different processing instructions that specify how that word should be indexed. Each set of processing instructions is called an annotation token. To maintain the quality of service in Office 365, there is a limit of 2 million annotation tokens for an email message.</span></span>  <br/> |
|<span data-ttu-id="7cfb7-211">インデックス内の本文の最大サイズ</span><span class="sxs-lookup"><span data-stu-id="7cfb7-211">Maximum body size in index</span></span>  <br/> |<span data-ttu-id="7cfb7-212">6700万文字</span><span class="sxs-lookup"><span data-stu-id="7cfb7-212">67 million characters</span></span>  <br/> |<span data-ttu-id="7cfb7-p121">電子メール メッセージとその添付ファイルの本文の文字の合計数です。電子メール メッセージにインデックスを作成、メッセージの本文およびすべての添付ファイルのすべてのテキストが 1 つの文字列に連結されます。このインデックスが設定された文字列の最大サイズは、6700万文字です。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p121">The total number of characters in the body of an email message and all its attachments. When an email message is indexed, all text in the body of the message and in all attachments is concatenated into a single string. The maximum size of this string that is indexed is 67 million characters.</span></span>  <br/> |
|<span data-ttu-id="7cfb7-216">本文の最大の一意のトークン</span><span class="sxs-lookup"><span data-stu-id="7cfb7-216">Maximum unique tokens in body</span></span>  <br/> |<span data-ttu-id="7cfb7-217">100 万個</span><span class="sxs-lookup"><span data-stu-id="7cfb7-217">1 million</span></span>  <br/> |<span data-ttu-id="7cfb7-p122">前に説明すると、トークンのコンテンツからテキストを抽出、句読点やスペースを削除し、インデックスに格納されている単語 (トークンと呼ばれます) に分割することの結果であります。フレーズでは、 `"cat, mouse, bird, dog, dog"` 5 のトークンが含まれています。一意のトークンは、これらの 4 人だけです。1 つの電子メール メッセージは、インデックスがランダムなトークンで巨大化するを防ぐのに役立ちます一意のトークンを 1 個の制限があります。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p122">As previously explained, tokens are the result of extracting text from content, removing punctuation and spaces, and then dividing it into words (called tokens) that are stored in the index. For example, the phrase  `"cat, mouse, bird, dog, dog"` contains 5 tokens. But only 4 of these are unique tokens. There is a limit of 1 million unique tokens per email message, which helps prevent the index from getting too large with random tokens.  </span></span><br/> |
   

  
## <a name="more-information-about-partially-indexed-items"></a><span data-ttu-id="7cfb7-222">部分的にインデックス付きのアイテムの詳細について</span><span class="sxs-lookup"><span data-stu-id="7cfb7-222">More information about partially indexed items</span></span>
<span data-ttu-id="7cfb7-223"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="7cfb7-223"></span></span>

- <span data-ttu-id="7cfb7-p123">前述したように、メッセージとドキュメントのプロパティおよびメタデータのインデックスが付けられます、のでキーワード検索可能性があります結果を返すインデックス付きのメタデータ内でそのキーワードが表示された場合。ただし、同じキーワード検索、キーワードのみが表示される場合、サポートされていないファイルの種類のアイテムの内容を同じ項目を返さない可能性があります。この例では、項目が部分的にインデックス付きの項目として返されます。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p123">As previously stated, because message and document properties and their metadata are indexed, a keyword search might return results if that keyword appears in the indexed metadata. However, that same keyword search might not return the same item if the keyword only appears in the content of an item with an unsupported file type. In this case, the item would be returned as a partially indexed item.</span></span>
    
- <span data-ttu-id="7cfb7-p124">検索クエリの条件が満たされる (および除外されなかった) ため、部分的にインデックス付きの項目が検索結果に含まれている場合、その含めることはできません、予想される検索の統計で部分的にインデックス付きの項目として。含めることはできません部分的にインデックス付きの項目を含む検索結果をエクスポートする場合。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p124">If a partially indexed item is included in the search results because it met the search query criteria (and wasn't excluded) then it won't be included as a partially indexed item in the estimated search statistics. Also, it won't be included with partially indexed items when you export search results.</span></span>
    
- <span data-ttu-id="7cfb7-p125">ファイルの種類のインデックス作成はサポートされて、インデックスを作成できますが、部分的にインデックス付きの項目として返されるファイルの原因となるエラーがインデックスを作成または検索します。などの非常に大きな Excel ファイルを検索する場合があります部分的に成功した (最初の 4 MB のインデックスが付けられます) ため、ファイル サイズの制限を超えているため失敗します。この例では、同じファイルが検索結果とは、部分的にインデックス付きの項目として返されることが可能です。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p125">Although a file type is supported for indexing and is indexed, there can be indexing or search errors that will cause a file to be returned as a partially indexed item. For example, searching a very large Excel file might be partially successful (because the first 4 MB are indexed), but then fails because the file size limit is exceeded. In this case, it's possible that the same file is returned with the search results and as a partially indexed item.</span></span>
    
- <span data-ttu-id="7cfb7-p126">マイクロソフトのテクノロジを使用して暗号化の添付ファイルはインデックスが、検索することができます。マイクロソフト以外のテクノロジを使用して暗号化ファイルは部分的にインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p126">Attached files encrypted with Microsoft technologies are indexed and can be searched. Files encrypted with non-Microsoft technologies are partially indexed.</span></span>
    
- <span data-ttu-id="7cfb7-p127">S/MIME で暗号化された電子メール メッセージは部分的にインデックスを作成します。これには、暗号化されたメッセージ添付ファイルの有無にはが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-p127">Email messages encrypted with S/MIME are partially indexed. This includes encrypted messages with or without file attachments.</span></span>
    
- <span data-ttu-id="7cfb7-236">Information Rights Management (IRM) を使用して保護されたメッセージは、インデックスが付けられるため、検索クエリと一致した場合に検索結果に含まれます。</span><span class="sxs-lookup"><span data-stu-id="7cfb7-236">Messages protected using Information Rights Management (IRM) are indexed and will be included in the search results if they match the search query.</span></span>

## <a name="see-also"></a><span data-ttu-id="7cfb7-237">関連項目</span><span class="sxs-lookup"><span data-stu-id="7cfb7-237">See also</span></span>

[<span data-ttu-id="7cfb7-238">Office 365 の電子情報開示で部分的にインデックスが作成されたアイテムを調査する</span><span class="sxs-lookup"><span data-stu-id="7cfb7-238">Investigating partially indexed items in Office 365 eDiscovery</span></span>](investigating-partially-indexed-items-in-ediscovery.md)
