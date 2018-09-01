---
title: Office 365 Advanced eDiscovery で結果をエクスポートする
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a9951a07-10b3-48cb-b37a-0ffaa24931ad
description: 'エクスポート バッチのパラメーターを指定するための手順を含む、Office 365 の詳細の開示から結果をエクスポートするためのオプションを定義する方法について説明します。 '
ms.openlocfilehash: 92ee107ad096393fbccbc9a3dbe81d8e7dd28da9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532741"
---
# <a name="export-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="54043-103">Office 365 Advanced eDiscovery で結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="54043-103">Export results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="54043-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="54043-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="54043-106">このトピックでは、高度な電子的証拠開示の設定のエクスポート オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="54043-106">This topic describes the Advanced eDiscovery Export Setup options.</span></span>
  
 <span data-ttu-id="54043-107">**このトピックの内容**</span><span class="sxs-lookup"><span data-stu-id="54043-107">**In this topic:**</span></span>
  
- [<span data-ttu-id="54043-108">エクスポート バッチとのセッションを定義します。</span><span class="sxs-lookup"><span data-stu-id="54043-108">Defining export batches and sessions</span></span>](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [<span data-ttu-id="54043-109">増分バックアップとその他のエクスポート</span><span class="sxs-lookup"><span data-stu-id="54043-109">Incremental and additional exports</span></span>](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [<span data-ttu-id="54043-110">バッチ エクスポートのパラメーターを設定します</span><span class="sxs-lookup"><span data-stu-id="54043-110">Set up batch export parameters</span></span>](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [<span data-ttu-id="54043-111">レポートの出力ファイルをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="54043-111">Export report output files</span></span>](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a><span data-ttu-id="54043-112">エクスポート バッチとのセッションを定義します。</span><span class="sxs-lookup"><span data-stu-id="54043-112">Defining export batches and sessions</span></span>
<span data-ttu-id="54043-113"><a name="BK_Define"> </a></span><span class="sxs-lookup"><span data-stu-id="54043-113"></span></span>

<span data-ttu-id="54043-p102">エクスポートのバッチは、エクスポートの処理が定義されているパラメーターのセットを使用できます。高度な電子的証拠開示では、各エクスポートをカスタマイズするのにはバッチを定義できます。</span><span class="sxs-lookup"><span data-stu-id="54043-p102">An export batch allows export processing using a set of defined parameters. Advanced eDiscovery enables you to define batches to customize each export.</span></span>
  
<span data-ttu-id="54043-p103">パラメーターは、エクスポートのバッチごとに定義します。既定では、大文字と小文字の最初のバッチのエクスポート バッチ 01] という名前のバッチが作成されます。バッチの名前と説明を編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="54043-p103">Parameters are defined per export batch. A batch named "Export batch 01" is created by default for the first batch of a case. You can also edit the batch name and description.</span></span>
  
<span data-ttu-id="54043-119">エクスポート セッションは、高度な電子的証拠開示エクスポートするエクスポートのバッチ内での実行です。</span><span class="sxs-lookup"><span data-stu-id="54043-119">An export session is an execution of Advanced eDiscovery Export within an export batch.</span></span>
  
## <a name="incremental-and-additional-exports"></a><span data-ttu-id="54043-120">増分バックアップとその他のエクスポート</span><span class="sxs-lookup"><span data-stu-id="54043-120">Incremental and additional exports</span></span>
<span data-ttu-id="54043-121"><a name="BK_IncrementalReports"> </a></span><span class="sxs-lookup"><span data-stu-id="54043-121"></span></span>

<span data-ttu-id="54043-p104">同じテンプレートのエクスポートとパラメーターに基づく結果の一貫性を確保するのには、エクスポートのバッチ内で複数のエクスポート ・ セッションを実行することができます。新しくケース データを処理し、それぞれを「差分」処理のバッチ内での各セッションの分析をエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="54043-p104">You can run multiple export sessions within an export batch, to ensure consistent results based on the same export template and parameters. For each session within a batch, you can export analytics for newly processed case data and process each "incrementally."</span></span>
  
<span data-ttu-id="54043-p105">パラメーターの異なるセットを使用して、エクスポートするためには、まず、新しいバッチを作成する必要があります。最初のセッションで新しいバッチ ファイルをこれらのファイルがインポートされ、1 つまたは複数のインポートを処理するかどうかの場合はこれまで、処理の結果が生成されます。各バッチには、ピボット、類似性、inclusives などが再計算されます。セッションでは、バッチに対して定義されているパラメーターを使用して、ピボット、類似性、inclusives などの各セッションの実行が再計算されません。</span><span class="sxs-lookup"><span data-stu-id="54043-p105">In order to export using a different set of parameters, you first need to create a new batch. The first session in the new batch will produce results for files processed in the case so far, whether or not these files were imported and processed over one or multiple Imports. Each batch recalculates pivots, similarity, inclusives, etc. Sessions use the parameters defined for the batch and do not recalculate pivots, similarity, inclusives, etc. for each session execution.</span></span>
  
<span data-ttu-id="54043-p106">たとえば、サポート案件がインポートされましたが、そのデータを分析します。重複の近くとインクリメンタル データの結果を電子メールのスレッドを取得するために使われていたデータをエクスポートするのには同じバッチ内で**作成するセッションをエクスポートする**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54043-p106">For example, assume a case was imported and its data analyzed. In order to retrieve Near-duplicates and Email Threading results for the incremental data, click **Create export session** in the same batch that was previously used to export data.</span></span> 
  
## <a name="set-up-batch-export-parameters"></a><span data-ttu-id="54043-129">バッチ エクスポートのパラメーターを設定します</span><span class="sxs-lookup"><span data-stu-id="54043-129">Set up batch export parameters</span></span>
<span data-ttu-id="54043-130"><a name="BK_SetUpExport"> </a></span><span class="sxs-lookup"><span data-stu-id="54043-130"></span></span>

<span data-ttu-id="54043-p107">電子証拠開示のエクスポート ツールは、ローカル コンピューターに高度な電子的証拠開示から検索結果をエクスポートするのには使用されます。増やすには、データ転送のスループットとをエクスポート処理の高速化、検索結果のエクスポートに使用するコンピューターの Windows レジストリ設定を構成できます。ダウンロード時間を短縮したい場合は、エクスポートのパラメーターを設定する前に、レジストリ設定を構成します。詳細については、 [Office 365 からの電子的証拠開示検索結果をエクスポートするときのダウンロード速度を向上させる](increase-download-speeds-when-exporting-ediscovery-results.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54043-p107">The eDiscovery Export Tool is used to export search results from Advanced eDiscovery to your local computer. To increase the data transfer throughput and speed-up the export process, you can configure a Windows Registry setting on the computer that you use to export the search results. If you'd like to increase the download speed, configure the registry setting before you set up the export parameters. For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
  
1. <span data-ttu-id="54043-135">高度な電子的証拠開示で、大文字と小文字を選択し、[**エクスポート**] をクリックして\>**セットアップ**します。</span><span class="sxs-lookup"><span data-stu-id="54043-135">In Advanced eDiscovery, select a Case and click **Export** \> **Setup**.</span></span>
    
  - <span data-ttu-id="54043-136">**バッチのエクスポート**] ボックスの一覧で、バッチの名前を選択またはエクスポート バッチ 01、(既定のバッチ) に結果をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="54043-136">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
  - <span data-ttu-id="54043-p108">既存のケースに追加した新しいファイルの結果をエクスポートするには、現在のバッチを続行します。バッチ内のセッションを作成、同じバッチ番号を選択および**作成するセッションのエクスポート**] をクリックするには、前のバッチでは、増分方式で同じパラメーターをエクスポートするのにはこのオプションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="54043-p108">To export results for new files that you added to an existing case, continue with your current batch. To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
  - <span data-ttu-id="54043-p109">新しいバッチにエクスポートする場合の [**追加**] をクリックします![のアイコンを追加](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)および**バッチ名**に新しい名前を入力 (または既定値をそのまま使用) と**バッチの説明**で説明します。**[Ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54043-p109">To export to a new batch, click **Add**![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**. Click **OK**.</span></span>
    
  - <span data-ttu-id="54043-141">バッチの名前または説明を編集するには、**バッチのエクスポート**の名前を選択して、[**編集**] をクリックして![[編集] アイコン](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)、し、フィールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="54043-141">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="54043-p110">エクスポート バッチのセッションを実行すると、それらを削除することはできません。さらに、最初のセッションが実行されるにはいくつかのパラメーターのみを編集できます。</span><span class="sxs-lookup"><span data-stu-id="54043-p110">After you've run sessions for an export batch, they cannot be deleted. In addition, only some parameters can be edited once the first session is run.</span></span> 
  
  - <span data-ttu-id="54043-144">重複データのエクスポートのバッチを作成するには、**重複データのエクスポートのバッチ**を選択します![重複データのエクスポートのバッチ アイコンを作成する](media/3f6d5f59-e842-4946-a493-473528af0119.jpg)パネルの名前と重複するバッチの説明を入力するとします。</span><span class="sxs-lookup"><span data-stu-id="54043-144">To create a duplicate export batch, choose **Duplicate export batch**![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
  - <span data-ttu-id="54043-145">[**削除**] に、エクスポートのバッチを削除するには、![バッチ エクスポート アイコンを削除](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)。</span><span class="sxs-lookup"><span data-stu-id="54043-145">To delete an export batch, choose **Delete**![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
  - <span data-ttu-id="54043-146">バッチの履歴を表示するには、**バッチの履歴**を選択して![の履歴の表示アイコン](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)。</span><span class="sxs-lookup"><span data-stu-id="54043-146">To view the history of a batch, choose **Batch history**![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="54043-147">エクスポートのバッチの設定を微調整する場合は、[**カタログの作成**、**関連性の高いカットオフ スコアの上のファイルのみを含める**と**絞り込みのエクスポートのバッチ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="54043-147">Under **Population**,Select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> 
    
3. <span data-ttu-id="54043-p111">**カットオフ スコアの妥当性上のファイルのみを含む**を選択した場合、**問題**になっています。ファイルの関連性スコアが選択されている問題に対するカットオフ スコアより高い場合は、'レビュー' のフィルターによって除外されていない限り、ファイルがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="54043-p111">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled. If the file's relevance score is higher than the cut-off score for the selected issue, the file will be exported unless it's excluded by the 'For review' filter.</span></span> 
  
<span data-ttu-id="54043-p112">**エクスポートのバッチを絞り込み**を選択した場合、**重複除外**とフィルターの確認] で、フィールドのオプション ボタンは有効になっています。選択した場合 **、重複除外**、定義したポリシーによって除外されるファイルの複製し、[レベル (既定値) の場合: 全体の場合は、重複するファイルのすべてのセットから 1 つを除くすべてのファイルは除外に対してされます。管理者レベル: 同じ書の重複したファイルのすべてのセットから 1 つを除くすべてのファイルは除外に対してされます]。エクスポートの出力には、重複するファイルのすべてのレコードが含まれています。**'レビュー' のフィルター**フィールドを選択した場合は、 **'レビュー' の**フィールドの設定を入力するのには、**メタデータの変更**を選択します。パッケージ コンテンツのソース ファイルを含めることを**含む入力ファイル**を選択します。エクスポート処理を高速化するには、この設定をオフにすることができます。ネイティブのファイルがどのような場合にエクスポートされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="54043-p112">If you select **Refine export batch**, the **De-dupe** and Filter by 'For review' field radio buttons are enabled. If you choose **De-dupe**, then duplicate files will be filtered out according to the policy defined [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped. Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.] The export output contains a record of all duplicate files. If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings. Select **Include input files** to include source files in the package content. You can clear this setting to speed up the export process. Note that the Native files will be exported in any case.</span></span> 
    
4. <span data-ttu-id="54043-157">**メタデータ**では、下には、**テンプレートをエクスポート**します (セッション) ごとに次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="54043-157">Under **Metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
  - <span data-ttu-id="54043-p113">**標準**: 基本的な項目のデータ、メタデータ、およびプロパティのセットです。インポート データが高度な電子的証拠開示で既に処理されて、ファイルが既に含まれているシステムにアップロードされているデータをエクスポートするときは、このオプションを使用します。既定では、列が作成され、入力のテンプレートをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="54043-p113">**Standard**: Basic set of data items, metadata, and properties. Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files. By default, export template columns are created and filled.</span></span>
    
  - <span data-ttu-id="54043-p114">**すべて**: すべてのデータ処理を行うと分析との関連性のスコアを含む標準のメタデータの完全なセットです。このテンプレートは、高度な電子的証拠開示の処理を実行すると、最初に、外部システムにアップロードするファイル データに必要です。</span><span class="sxs-lookup"><span data-stu-id="54043-p114">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores. This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
  - <span data-ttu-id="54043-163">**問題**:**すべての懸案事項**を選択または作成した特定の問題を選択します。</span><span class="sxs-lookup"><span data-stu-id="54043-163">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
5. <span data-ttu-id="54043-164">[**宛先**:]</span><span class="sxs-lookup"><span data-stu-id="54043-164">Under **Destination**:</span></span>
    
  - <span data-ttu-id="54043-165">**ローカル マシンにダウンロードします。**</span><span class="sxs-lookup"><span data-stu-id="54043-165">**Download to local machine**</span></span>
    
  - <span data-ttu-id="54043-166">**Azure blob のユーザー定義をエクスポート**します。 これをオンにした場合は、コンテナーの URL と SAS のトークンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="54043-166">**Export to user-defined Azure blob**: If this is checked, you can specify a container URL and SAS token.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="54043-p115">エクスポート パッケージが格納されているユーザーには、Azure blob が定義されている、高度な電子的証拠開示は、データが管理されていません。Azure blob が管理します。つまり場合は、大文字と小文字を削除すると、書き出されたファイルもに残ります Azure blob です。</span><span class="sxs-lookup"><span data-stu-id="54043-p115">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery; it's managed by the Azure blob. This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
  - <span data-ttu-id="54043-169">**将来のエクスポート ・ セッションのトークンを SAS の保存**: チェックすると、SAS のトークンが将来使用するための高度な電子的証拠開示の内部データベースに暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="54043-169">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="54043-p116">現在 SAS のトークンは、1 か月後に有効期限が切れます。最後のセッションを取り消す必要が複数の月の後にダウンロードしようとする場合は、もう一度エクスポートし、します。</span><span class="sxs-lookup"><span data-stu-id="54043-p116">Currently the SAS token expires after a month. If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
6. <span data-ttu-id="54043-172">設定の**変更**] をクリックして、[確認のため ' フィールドの設定です。</span><span class="sxs-lookup"><span data-stu-id="54043-172">Click **Modify** to set the "for review' field settings.</span></span> 
    
> ![エクスポート バッチの確認フィールドの seetings の設定します。](media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
    In **For review field settings** panel, in **Select scenario**, select the scenario and scope of the review. The settings are displayed based on your selection.
    
    **Review all** (default): All emails, attachments, and documents are selected by default. 
    
    **Review all unique content in a set**: Inclusives and unique inclusive copies, unique attachments in email set level, representative from every set of exact duplicates.
    
    **Review all unique content in a set - no inclusive copies**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates.
    
    **Review all unique content and related family files**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates, expand to include family files.
    
    **Custom** (allows you to define the options in the dialog): The default is to keep current selections and enable all dialog options, to allow their selection. 
    
    If you select custom, you can then customize the settings for emails, documents, attachments and miscellaneous.
    
> <span data-ttu-id="54043-174">**電子メール**で電子メールをエクスポートするを選択します。</span><span class="sxs-lookup"><span data-stu-id="54043-174">In **Emails** select the emails you want to export:</span></span> 
    
    **All emails**: (default) All emails are selected.
    
    **Inclusives**: An inclusive email is a last email of a thread, and it contains all the other emails from the thread.
    
    **Inclusives and unique inclusive copies**: Inclusive copies and inclusives with the same subject, body and attachments; unique inclusive copies are unique copies of these emails .
    
> <span data-ttu-id="54043-175">**ドキュメント**では、エクスポートするドキュメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="54043-175">In **Documents** select the documents you want to export:</span></span> 
    
    **All documents**: (default) All documents are selected.
    
    **Pivots**: A file chosen as representative of near-duplicates set, which is typically used as the baseline when reviewing the set.
    
    **Representative from every set of exact duplicates**: Unique near-duplicate files (including the pivot).
    
> <span data-ttu-id="54043-176">**添付ファイル**の添付ファイルをエクスポートするを選択します</span><span class="sxs-lookup"><span data-stu-id="54043-176">In **Attachments** select the attachments you want to export</span></span> 
    
    **All attachments**: (default) All attachments are selected.
    
    **Unique attachment in case level**: Unique attachment files within the specified case.
    
    **Unique attachment in email set level**: Unique attachment files within the specified email case.
    
> <span data-ttu-id="54043-p117">**Micellaneous**では、**ドキュメントと添付ファイルを扱う****ドキュメントと電子メールを扱う**、または**ファミリ ファイルを含むように展開**できます。ファイルごとにフラグが設定されている確認のため **、ファミリのファイルの展開**を選択すると、同じファミリのすべてのファイルはフラグが設定もします。</span><span class="sxs-lookup"><span data-stu-id="54043-p117">In **Micellaneous** you can choose to **Treat attachments as documents**, **Treat emails as documents**, or **Expand to include family files**. When you choose **Expand to include family files**, for each file that is flagged for review, all files of the same family will also be flagged.</span></span>
    
    Choose **Save** to save the settings. 
    
7. <span data-ttu-id="54043-179">エクスポート パラメーターを指定すると、エクスポートのバッチを開始する] をクリック**を作成するセッションをエクスポートします**。</span><span class="sxs-lookup"><span data-stu-id="54043-179">After you specify export parameters, to start export batch, click **Create export session**.</span></span>
    
    <span data-ttu-id="54043-p118">書き出し時に、**タスクの進捗状況**のステータスが表示されます。**エクスポートの概要**では、結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="54043-p118">During export, the status is displayed in **Task status**. The results are displayed in **Export summary**.</span></span>
    
8. <span data-ttu-id="54043-182">**ファイルのダウンロード**ウィンドウで、エクスポート キーのコピーを**クリップボードにコピー**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54043-182">In the **Download files** window, click **Copy to clipboard** to copy the Export key.</span></span> 
    
    ![ファイルをダウンロードします。](media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
9. <span data-ttu-id="54043-184">**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54043-184">Click **Close**.</span></span> 
    
    <span data-ttu-id="54043-185">電子的証拠開示のエクスポート ツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="54043-185">The eDiscovery Export Tool is started.</span></span>
    
    ![電子情報開示のエクスポート ツール](media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
10. <span data-ttu-id="54043-187">**エクスポート ツールで電子的証拠開示**します。</span><span class="sxs-lookup"><span data-stu-id="54043-187">In the **eDiscovery Export Tool**:</span></span>
    
1. <span data-ttu-id="54043-188">**ソースへの接続に使用される、共有アクセス署名を貼り付ける**には、内には、クリップボードにその youcopied エクスポート キーを貼り付け、手順 7 で。</span><span class="sxs-lookup"><span data-stu-id="54043-188">In **Paste the Shared Access Signature that will be used to connect to the source**, paste the Export key that youcopied to the clipboard in step 7.</span></span>
    
2. <span data-ttu-id="54043-189">ローカル コンピューターにダウンロードしたエクスポート ファイルを保存するターゲットの場所を選択する**参照**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54043-189">Click **Browse** to select the target location for storing the downloaded export files on the local machine.</span></span> 
    
11. <span data-ttu-id="54043-p119">[**開始**] をクリックします。エクスポート ファイルは、ローカル コンピューターにダウンロードされます。手順 4 で**ユーザー定義の Azure blob へのエクスポート**を選択した場合は、Blob ストレージ URL 先を選択してセッションがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="54043-p119">Click **Start**.The export files are downloaded to the local machine. If you chose **Export to user-defined Azure blob** in step 4, the session is exported to a Blob storage URL destination of your choosing.</span></span> 
    
<span data-ttu-id="54043-192">エクスポート レポート内のフィールドの完全な説明は、[レポートのフィールドをエクスポートする](export-report-fields-in-advanced-ediscovery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54043-192">For a full description of the fields in the export report, see [Export report fields](export-report-fields-in-advanced-ediscovery.md).</span></span>
  
## <a name="export-report-output-files"></a><span data-ttu-id="54043-193">レポートの出力ファイルをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="54043-193">Export report output files</span></span>
<span data-ttu-id="54043-194"><a name="BK_ExportOutputFIles"> </a></span><span class="sxs-lookup"><span data-stu-id="54043-194"></span></span>

<span data-ttu-id="54043-195">エクスポートのバッチを実行するときに生成される出力ファイルを次の表に一覧します。</span><span class="sxs-lookup"><span data-stu-id="54043-195">The following table lists the output files that are generated when you run an Export batch.</span></span>
  
|<span data-ttu-id="54043-196">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="54043-196">**File name**</span></span>|<span data-ttu-id="54043-197">**ファイルの種類**</span><span class="sxs-lookup"><span data-stu-id="54043-197">**File type**</span></span>|<span data-ttu-id="54043-198">**説明**</span><span class="sxs-lookup"><span data-stu-id="54043-198">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="54043-199">エクスポートの概要</span><span class="sxs-lookup"><span data-stu-id="54043-199">Export summary</span></span>  <br/> |<span data-ttu-id="54043-200">csv</span><span class="sxs-lookup"><span data-stu-id="54043-200">csv</span></span>  <br/> |<span data-ttu-id="54043-201">ログ ファイルは、エクスポート ・ ツールを電子的証拠開示によって生成されます。</span><span class="sxs-lookup"><span data-stu-id="54043-201">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="54043-202">トレース</span><span class="sxs-lookup"><span data-stu-id="54043-202">Trace</span></span>  <br/> |<span data-ttu-id="54043-203">txt</span><span class="sxs-lookup"><span data-stu-id="54043-203">txt</span></span>  <br/> |<span data-ttu-id="54043-204">ログ ファイルは、エクスポート ・ ツールを電子的証拠開示によって生成されます。</span><span class="sxs-lookup"><span data-stu-id="54043-204">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="54043-205">抽出されたテキスト ファイル</span><span class="sxs-lookup"><span data-stu-id="54043-205">Extracted text files</span></span>  <br/> |<span data-ttu-id="54043-206">ファイル フォルダー</span><span class="sxs-lookup"><span data-stu-id="54043-206">File folder</span></span>  <br/> |<span data-ttu-id="54043-207">書き出されたファイルの抽出されたテキスト ファイルを含むフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="54043-207">Folder that contains the extracted text files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="54043-208">入力またはネイティブ ファイル</span><span class="sxs-lookup"><span data-stu-id="54043-208">Input or native files</span></span>  <br/> |<span data-ttu-id="54043-209">ファイル フォルダー</span><span class="sxs-lookup"><span data-stu-id="54043-209">File folder</span></span>  <br/> |<span data-ttu-id="54043-210">エクスポートしたファイルのネイティブと入力ファイルを含むフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="54043-210">Folder that contains the native and input files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="54043-211">ボックスの一覧をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="54043-211">Export list</span></span>  <br/> |<span data-ttu-id="54043-212">xlsx</span><span class="sxs-lookup"><span data-stu-id="54043-212">xlsx</span></span>  <br/> |<span data-ttu-id="54043-p120">Xlsx 形式でエクスポートされたファイルのメタデータ。ファイル内のフィールドはエクスポートするテンプレートのユーザーの選択に従っています。必要な場合は、いくつかのファイルが作成される、それぞれに 100-150 K の行が含まれています。Excel のセルを含めることができますを超える文字が特定の値に含まれているかどうか (現在の制限は 32,767 文字) をし、値を許可する最大の長さにトリミングされます。値をトリミングすると、セルの背景色が赤に、これをユーザーに示す」参加者の電子メール"は、大規模な配布する電子メールが送信された場合の長さの制限を超えている可能性があるフィールドの例です。出力フィールドの詳細については、[レポートのフィールドをエクスポートする](export-report-fields-in-advanced-ediscovery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54043-p120">Exported files metadata in xlsx format. Fields in files are according to template user selects to export. If needed, several files are created, each contains 100-150K rows. If a certain value contains more characters than an Excel cell can contain (currently the limit is 32,767 characters), then the value will be trimmed to the maximum length allowed. If a value is trimmed, the cell's background color is red to indicate this to the user."Email participants" is an example of a field that can exceed the length limit, if the email was sent to a large distribution. See [Export report fields](export-report-fields-in-advanced-ediscovery.md) for details about the output fields.  </span></span><br/> |
|<span data-ttu-id="54043-219">ファイルの読み込み</span><span class="sxs-lookup"><span data-stu-id="54043-219">Load file</span></span>  <br/> |<span data-ttu-id="54043-220">csv</span><span class="sxs-lookup"><span data-stu-id="54043-220">csv</span></span>  <br/> |<span data-ttu-id="54043-p121">別のアプリケーションに読み込む csv 形式でエクスポートされたファイルのメタデータ。ファイル内のフィールドはエクスポートするテンプレートのユーザーの選択に従っています。</span><span class="sxs-lookup"><span data-stu-id="54043-p121">Exported files metadata in csv format for loading into a different application. Fields in files are according to template user selects to export.</span></span>  <br/> |
|<span data-ttu-id="54043-223">成功インジケーター</span><span class="sxs-lookup"><span data-stu-id="54043-223">Success indicator</span></span>  <br/> |<span data-ttu-id="54043-224">txt</span><span class="sxs-lookup"><span data-stu-id="54043-224">txt</span></span>  <br/> |<span data-ttu-id="54043-p122">サードパーティの Azure blob にエクスポートするときにのみ作成します。エクスポートが完全に成功した場合は、ファイルが作成されます。障害発生時、または部分的な成功した場合、ファイルは作成されません。別のエクスポートのバッチまたはセッション状態の自動追跡を許可する、ルート フォルダーにファイルが作成されます。これは、空のファイルです。名前: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt。</span><span class="sxs-lookup"><span data-stu-id="54043-p122">Only created when exporting to a 3rd party Azure blob. If export succeed completely, the file will be created. In case of failure, or partial success the file will not be created. File will be created in the root folder, allowing automated tracking on different Export batches/sessions statuses. This is an empty file. Its name is: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="54043-231">関連項目</span><span class="sxs-lookup"><span data-stu-id="54043-231">See also</span></span>
<span data-ttu-id="54043-232"><a name="BK_ExportOutputFIles"> </a></span><span class="sxs-lookup"><span data-stu-id="54043-232"></span></span>

[<span data-ttu-id="54043-233">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="54043-233">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="54043-234">バッチ履歴を表示して、以前の結果をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="54043-234">Viewing batch history and exporting past results</span></span>](view-batch-history-and-export-past-results.md)
  
[<span data-ttu-id="54043-235">Office 365 Advanced eDiscovery のクイック セットアップ</span><span class="sxs-lookup"><span data-stu-id="54043-235">Quick setup for Office 365 Advanced eDiscovery</span></span>](quick-setup-for-advanced-ediscovery.md)

[<span data-ttu-id="54043-236">レポートのフィールドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="54043-236">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)
  
[<span data-ttu-id="54043-237">Office 365 から電子的証拠開示検索結果をエクスポートするときは、ダウンロード速度を上げる</span><span class="sxs-lookup"><span data-stu-id="54043-237">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>](increase-download-speeds-when-exporting-ediscovery-results.md)
