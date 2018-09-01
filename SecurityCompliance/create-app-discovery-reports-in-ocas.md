---
title: Office 365 Cloud App Security を使用して app discovery レポートを作成する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: Office 365 クラウド アプリケーションのセキュリティを使用すると、Office 365 とその他のアプリケーションに、組織内のユーザーを使用する方法を理解するには、レポートを作成します。
ms.openlocfilehash: 6842912f42072e21608955bde5250f0774c7bba4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531568"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a><span data-ttu-id="e2c15-103">Office 365 Cloud App Security を使用して app discovery レポートを作成する</span><span class="sxs-lookup"><span data-stu-id="e2c15-103">Create app discovery reports using Office 365 Cloud App Security</span></span>

<span data-ttu-id="e2c15-104">セキュリティ管理の高度な office 365 は、Office 365 のクラウド アプリケーションのセキュリティをされます。</span><span class="sxs-lookup"><span data-stu-id="e2c15-104">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="e2c15-105">評価 * *\>**</span><span class="sxs-lookup"><span data-stu-id="e2c15-105">****Evaluation** \>**</span></span>|<span data-ttu-id="e2c15-106">計画 * *\>**</span><span class="sxs-lookup"><span data-stu-id="e2c15-106">****Planning** \>**</span></span>|<span data-ttu-id="e2c15-107">配置 * *\>**</span><span class="sxs-lookup"><span data-stu-id="e2c15-107">****Deployment** \>**</span></span>|<span data-ttu-id="e2c15-108">使用率。</span><span class="sxs-lookup"><span data-stu-id="e2c15-108">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="e2c15-109">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="e2c15-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="e2c15-110">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="e2c15-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="e2c15-111">展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="e2c15-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="e2c15-112">コースです!</span><span class="sxs-lookup"><span data-stu-id="e2c15-112">You are here!</span></span>  <br/> [<span data-ttu-id="e2c15-113">次の手順</span><span class="sxs-lookup"><span data-stu-id="e2c15-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="e2c15-p101">Office 365 のクラウド アプリケーションのセキュリティは、グローバル管理者、セキュリティ管理者、およびセキュリティ リーダーが組織内のユーザーが使用しているクラウド サービスの把握に役立ちます。たとえば、データの量は、アプリケーションまたは Office 365 の外部にあるサービスにアップロードしています、ユーザーが保存してドキュメントで共同作業を行う場所を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e2c15-p101">Office 365 Cloud App Security helps global administrators, security administrators, and security readers gain insight into the cloud services people in an organization are using. For example, you can see where users are storing and collaborating on documents and how much data is being uploaded to apps or services that are outside of Office 365.</span></span>
  
<span data-ttu-id="e2c15-116">アプリケーションの探索レポートを生成するために手動でアップロードする、ファイアウォールやプロキシから、web トラフィックのログ ファイルと Office 365 のクラウド アプリケーションのセキュリティを解析し、レポートのこれらのファイルを分析しています。</span><span class="sxs-lookup"><span data-stu-id="e2c15-116">To generate an app discovery report, you manually upload your web traffic log files from your firewalls and proxies, and then Office 365 Cloud App Security parses and analyzes those files for your report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e2c15-p102">この資料に記載されているタスクを実行するグローバル管理者、セキュリティ管理者、またはセキュリティのリーダーである必要があります。詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2c15-p102">You must be a global administrator, security administrator, or security reader to perform the tasks described in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="create-a-report-with-app-discovery"></a><span data-ttu-id="e2c15-119">アプリケーションの検出とレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2c15-119">Create a report with app discovery</span></span>

<span data-ttu-id="e2c15-120">アプリの探索レポートを作成するには、仕入先のデータ ソースの分析が、ログ ファイルを選択し、レポートを要求し、使用するログ ファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="e2c15-120">To create an app discovery report, you identify the vendor data source for the log files that you want to have analyzed, select the log files, and then request the report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e2c15-121">組織の使用法の最適な表現を取得するのにはピーク トラフィックは、web トラフィックのログ ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2c15-121">Use web traffic log files that include peak traffic periods to get the best representation of usage in your organization.</span></span> 
  
1. <span data-ttu-id="e2c15-122">お客様の[web トラフィックのログ、および Office 365 のクラウド アプリケーションのセキュリティのデータ ソース](web-traffic-logs-and-data-sources-for-ocas.md)を収集します。</span><span class="sxs-lookup"><span data-stu-id="e2c15-122">Collect your [web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md).</span></span>
    
2. <span data-ttu-id="e2c15-123">[https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="e2c15-123">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account.</span></span> 
    
3. <span data-ttu-id="e2c15-124">セキュリティで&amp;コンプライアンス センターでは、**アラート**を選択して\>**管理警告の詳細**です。</span><span class="sxs-lookup"><span data-stu-id="e2c15-124">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
4. <span data-ttu-id="e2c15-125">**Office 365 のクラウド アプリケーションのセキュリティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2c15-125">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
5. <span data-ttu-id="e2c15-126">**検出**を選択して\>**新しいレポートを作成**します。</span><span class="sxs-lookup"><span data-stu-id="e2c15-126">Choose **Discover** \> **Create new report**.</span></span>
    
    ![Office 365 CA ポータルでは、検出を選択します](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
6. <span data-ttu-id="e2c15-128">名と、レポートの説明を指定し、[**データ ソース**] ボックスの一覧で、web トラフィックのログのデータ ソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2c15-128">Specify a name and description for your report, and then select the data source for your web traffic logs in the **Data source** list.</span></span> 
    
    ![O365 の CA で、検出を選択します\>新しいレポートを作成します。](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)
  
    > [!NOTE]
    > <span data-ttu-id="e2c15-p103">使用するにはデータ ソースが一覧にない場合は、追加することを要求できます。[**その他**の**データ ソース**、およびアップロードしようとしているデータ ソースの名前を入力します。ログを確認、それを生成するデータ ソースのサポートを追加したことを確認でき、します。</span><span class="sxs-lookup"><span data-stu-id="e2c15-p103">If a data source that you'd like to use is not listed, you can request that it be added. Select **Other** for **Data source**, and then type the name of the data source that you're trying to upload. We'll review the log, and let you know if we add support for the data source that generated it.</span></span> 
  
7. <span data-ttu-id="e2c15-p104">収集したログ ファイルの場所を参照し、ファイルを選択します。ログ ファイルは、レポート用に選択したデータ ソースで生成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2c15-p104">Browse to the location of the log files you collected and select the files. The log files must have been generated by the data source that you chose for the report.</span></span>
    
8. <span data-ttu-id="e2c15-135">レポート作成プロセスを開始する**を作成する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2c15-135">Click **Create** to start the report creation process.</span></span> 
    
9. <span data-ttu-id="e2c15-p105">レポートのステータスを表示するには、**レポートのスナップショットの管理**をクリックします。レポートの準備ができたら、[**レポートの表示**] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2c15-p105">To see the status of the report, click **Manage snapshot reports**. When a report is ready, you'll see the **View report** option.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="e2c15-138">次の手順</span><span class="sxs-lookup"><span data-stu-id="e2c15-138">Next steps</span></span>

- [<span data-ttu-id="e2c15-139">確認し、アラート アクションを実行</span><span class="sxs-lookup"><span data-stu-id="e2c15-139">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="e2c15-140">Office 365 Cloud App Security でアプリ検出結果を確認する</span><span class="sxs-lookup"><span data-stu-id="e2c15-140">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="e2c15-141">[Office 365 のクラウド アプリケーションのセキュリティの使用率のアクティビティ](utilization-activities-for-ocas.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="e2c15-141">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    
