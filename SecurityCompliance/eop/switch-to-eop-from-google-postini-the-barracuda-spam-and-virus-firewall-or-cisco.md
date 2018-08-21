---
title: Google Postini、Barracuda Spam & Virus Firewall、または Cisco IronPort から EOP に切り替える
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
description: このトピックの目的は、社内の電子メール検疫アプライアンスまたはクラウドベースの保護サービスから Exchange Online Protection (EOP) に切り替えるプロセスを理解していただくことと、着手に役立つリソースを提供することにあります。
ms.openlocfilehash: d1dc75e8d020f865e4f358899802d0da320deeb5
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026404"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a><span data-ttu-id="6fe3c-103">Google Postini、Barracuda Spam & Virus Firewall、または Cisco IronPort から EOP に切り替える</span><span class="sxs-lookup"><span data-stu-id="6fe3c-103">Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort</span></span>

 <span data-ttu-id="6fe3c-p101">このトピックの目的は、社内の電子メール検疫アプライアンスまたはクラウドベースの保護サービスから Exchange Online Protection (EOP) に切り替えるプロセスを理解していただくことと、着手に役立つリソースを提供することにあります。多数のスパム対策フィルター ソリューションがありますが、多くの場合 EOP への切り替えプロセスは同様です。</span><span class="sxs-lookup"><span data-stu-id="6fe3c-p101">The purpose of this topic is to help you understand the process for switching to Exchange Online Protection (EOP) from an on-premises email hygiene appliance or cloud-based protection service, and then to provide you with help resources to get started. There are many spam-filtering solutions, but the process for switching to EOP is similar in most cases.</span></span>
  
<span data-ttu-id="6fe3c-106">EOP を初めてお使いで、切り替えを決定する前に機能の概要を確認したい場合は、まず TechNet の「[Exchange Online Protection の概要](exchange-online-protection-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6fe3c-106">If you are new to EOP and you want to read an overview of its features before you decide to switch, start with the [Exchange Online Protection overview](exchange-online-protection-overview.md) on TechNet.</span></span> 
  
<span data-ttu-id="6fe3c-p102">EOP に切り替える前に、Exchange Online、社内、またはハイブリッド シナリオによってクラウド内で EOP 保護されたメールボックスをホストするかどうかを検討することが重要です (ハイブリッドとは、社内でいくつかのメールボックスをホストし、Exchange Online で別の部分をホストすることを意味します)。候補となるこれらの各ホスト シナリオ:クラウド、社内、およびハイブリッドは、セットアップの手順が異なる場合があります。適切な展開を選択するための、いくつかの考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6fe3c-p102">Before you switch to EOP, it's important to think about whether you want to host your EOP-protected mailboxes in the cloud, with Exchange Online, on-premises, or in a hybrid scenario. (Hybrid means that you have some mailboxes hosted on-premises and another portion hosted with Exchange Online.) Each of these hosting scenarios: cloud, on-premises, and hybrid, is possible, but the setup steps can vary. Here are a few considerations to help you choose the appropriate deployment:</span></span>
  
- <span data-ttu-id="6fe3c-p103">**社内メールボックスを使用した EOP 保護** このシナリオは、使用したい既存のメール ホスティング インフラストラクチャがあるか、または社内のメールボックスを保持しなければならないビジネス要件があり、さらに EOP のクラウドベースの電子メール保護を希望する場合に適しています。「 [EOP スタンドアロンに切り替える](#BKMK_SwitchStandalone.md)」で、このシナリオの詳細を説明しています。</span><span class="sxs-lookup"><span data-stu-id="6fe3c-p103">**EOP protection with on-premises mailboxes** This scenario is appropriate if you have existing mail-hosting infrastructure you want to use, or you have business requirements to keep mailboxes on-premises, and you want EOP's cloud-based email protection. [Switch to EOP standalone](#BKMK_SwitchStandalone.md) describes this scenario in more detail.</span></span> 
    
- <span data-ttu-id="6fe3c-p104">**Exchange Online メールボックスを使用した EOP 保護** このシナリオは、EOP 保護とすべてのメールボックスをクラウドでホストしたい場合に適しています。社内メッセージング サーバーを維持する必要がないため、複雑さを軽減できます。このシナリオについては、「 [Exchange Online に切り替える](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md#BKMK_SwitchEXO)」で説明しています。</span><span class="sxs-lookup"><span data-stu-id="6fe3c-p104">**EOP protection with Exchange Online mailboxes** This scenario is appropriate if you want EOP protection and all of your mailboxes hosted in the cloud. It can help you reduce complexity, because you don't have to maintain on-premises messaging servers. [Switch to Exchange Online](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md#BKMK_SwitchEXO) describes this scenario.</span></span> 
    
- <span data-ttu-id="6fe3c-p105">**ハイブリッド メールボックスを使用した EOP 保護** クラウド メールボックスを希望していても、一部のユーザーのためにメールボックスを社内で保持する必要がある場合があります。いくつかのメールボックスを社内でホストし、別の部分を Exchange Online でホストする場合は、このシナリオを選択してください。このシナリオについては、「 [ハイブリッド ソリューションに切り替える](#BKMK_SwitchHybrid.md)」で説明しています。</span><span class="sxs-lookup"><span data-stu-id="6fe3c-p105">**EOP protection with hybrid mailboxes** Perhaps you want cloud mailboxes, but you need to keep mailboxes for some users on-premises. Choose this scenario if you want some mailboxes hosted on-premises and another portion hosted with Exchange Online. [Switch to a hybrid solution](#BKMK_SwitchHybrid.md) describes this scenario.</span></span> 
    
## <a name="switch-to-eop-standalone"></a><span data-ttu-id="6fe3c-118">EOP スタンドアロンに切り替える</span><span class="sxs-lookup"><span data-stu-id="6fe3c-118">Switch to EOP standalone</span></span>
<span data-ttu-id="6fe3c-119"><a name="BKMK_SwitchStandalone"> </a></span><span class="sxs-lookup"><span data-stu-id="6fe3c-119"></span></span>

<span data-ttu-id="6fe3c-p106">現在、メールボックスを社内でホストし、社内保護アプライアンスまたはクラウド メッセージング保護サービスを使用している場合は、EOP に切り替えて、その保護機能と可用性を活かすことができます。スタンドアロン シナリオ、つまり、社内でメールボックスをホストし EOP を使用して電子メール保護を提供するように EOP を設定するには、「[EOP サービスを設定する](set-up-your-eop-service.md)」で概説されている手順に従います。このトピックでは、サインアップ、ドメインの追加、コネクタとのメール フローの設定などの、EOP 保護の設定に関する手順を概説しています。</span><span class="sxs-lookup"><span data-stu-id="6fe3c-p106">If you currently host your mailboxes on premises and use an on-premises protection appliance or a cloud messaging-protection service, you can switch to EOP to take advantage of its protection features and availability. To set up EOP in a standalone scenario, which means you host your mailboxes on premises and use EOP to provide email protection, you can follow the steps outlined in [Set up your EOP service](set-up-your-eop-service.md). The topic outlines the steps for setting up EOP protection, which include sign up, adding your domain, and setting up mail flow with connectors.</span></span>
  
## <a name="switch-to-exchange-online"></a><span data-ttu-id="6fe3c-123">Exchange Online に切り替える</span><span class="sxs-lookup"><span data-stu-id="6fe3c-123">Switch to Exchange Online</span></span>
<span data-ttu-id="6fe3c-124"><a name="BKMK_SwitchEXO"> </a></span><span class="sxs-lookup"><span data-stu-id="6fe3c-124"></span></span>

<span data-ttu-id="6fe3c-p107">社内アプライアンスによって保護された社内メールボックスがあり、Exchange Online クラウドホスト型メールボックスと EOP 保護に切り替えて Office 365 クラウド メッセージングおよび保護機能を利用したいと考えていることでしょう。ここでは始めに、Office 365 にサインアップして、ドメインを追加できます。このシナリオでは、社内メールボックスへのルーティングがないため、コネクタを設定する必要はありません。「[Office 365 のサインアップ ページ](https://www.microsoft.com/en-us/office365/online-software.aspx)」から始めます。(「[Office 365 の使用を開始](https://go.microsoft.com/fwlink/p/?LinkId=275407)」では、さらに機能を理解するためのリソースを提供しています。)</span><span class="sxs-lookup"><span data-stu-id="6fe3c-p107">Perhaps you have on-premises mailboxes protected by an on-premises appliance, and you want to jump to Exchange Online cloud-hosted mailboxes and EOP protection to take advantage of Office 365 cloud messaging and protection features. To get started, you can sign up for Office 365 and add your domain. This scenario doesn't require you to setup connectors, because there isn't any routing to on-premises mailboxes. Begin at the [Office 365 sign up page](https://www.microsoft.com/en-us/office365/online-software.aspx). ([Get started with Office 365](https://go.microsoft.com/fwlink/p/?LinkId=275407) provides resources to get familiar with its features.)</span></span> 
  
<span data-ttu-id="6fe3c-130">Office 365 の設定プロセスでは、クラウド ベースのメールボックス ユーザーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6fe3c-130">During the Office 365 setup process, you will create your cloud-based mailbox users.</span></span>
  
## <a name="switch-to-a-hybrid-solution"></a><span data-ttu-id="6fe3c-131">ハイブリッド ソリューションに切り替える</span><span class="sxs-lookup"><span data-stu-id="6fe3c-131">Switch to a hybrid solution</span></span>
<span data-ttu-id="6fe3c-132"><a name="BKMK_SwitchHybrid"> </a></span><span class="sxs-lookup"><span data-stu-id="6fe3c-132"></span></span>

<span data-ttu-id="6fe3c-p108">ビジネス要件または規制に関する考慮事項があるため、メールボックスの一部のみをクラウドに移行したい場合があります。このようなケースでは、ハイブリッド シナリオを展開すると、ビジネス要件に従ってメールボックスをクラウドに移行できます。EOP 保護を使用したハイブリッド シナリオへの移行は、すべてにおいてクラウドを採用するシナリオより複雑ですが、Microsoft には、ハイブリッドへの移行が簡単に行える数多くのハイブリッド サポートとリソースが用意されています。</span><span class="sxs-lookup"><span data-stu-id="6fe3c-p108">You may want to move only a portion of your mailboxes to the cloud because of business requirements or regulatory considerations. When you deploy a hybrid scenario, you can move mailboxes to the cloud as your business requirements dictate. Migrating to a hybrid scenario with EOP protection is more complicated than moving to an all-cloud scenario, but Microsoft provides full hybrid support and ample resources to make the move to hybrid easier.</span></span>
  
<span data-ttu-id="6fe3c-p109">ハイブリッド展開を検討している場合は、まず「[Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx)」をご確認ください。さらに、ハイブリッド シナリオではメールをルーティングできるいくつかの異なる方法があり、それらを理解しておくことが重要です。「[Transport Routing in Exchange 2013 Hybrid Deployments](http://technet.microsoft.com/library/36c2cea3-2e2f-40ac-88bd-7e1b6bd27828.aspx)」では、ビジネス要件に基づいて最適なルーティング シナリオを選択できるように、各タイプについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="6fe3c-p109">The best place to start, if you are considering a hybrid deployment, is [Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx). Additionally, there are a few different ways you can route mail in a hybrid scenario that are important to understand. [Transport Routing in Exchange 2013 Hybrid Deployments](http://technet.microsoft.com/library/36c2cea3-2e2f-40ac-88bd-7e1b6bd27828.aspx) explains each type, so you can choose the best routing scenario, based on your business requirements.</span></span> 
  
## <a name="migration-planning"></a><span data-ttu-id="6fe3c-139">移行の計画</span><span class="sxs-lookup"><span data-stu-id="6fe3c-139">Migration planning</span></span>
<span data-ttu-id="6fe3c-140"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="6fe3c-140"></span></span>

<span data-ttu-id="6fe3c-141">EOP への切り替えを決定したら、特に次の分野について考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fe3c-141">When you decide to switch to EOP, make sure you give special consideration to the following areas:</span></span>
  
- <span data-ttu-id="6fe3c-p110">**カスタム フィルター処理ルール** 特定のスパムを検知するためのカスタム フィルター処理またはビジネス ポリシー ルールがある場合は、一定期間、既定の設定で EOP を試行してからルールを移行することをお勧めします。EOP は既定の設定でエンタープライズ レベルのスパム対策を提供しているため、一部のルールを EOP に移行する必要がない場合があります。当然、特定のカスタム ビジネス ポリシーを適用するルールがある場合には、それらを作成できます。EOP でトランスポート ルールを作成する手順の詳細については、「 [Transport Rules](http://technet.microsoft.com/library/c3d2031c-fb7b-4866-8ae1-32928d0138ef.aspx)」で説明しています。</span><span class="sxs-lookup"><span data-stu-id="6fe3c-p110">**Custom Filtering Rules** If you have custom filtering or business-policy rules to catch specific spam, we recommend that you try EOP with the default settings for a period, before you migrate your rules. EOP offers enterprise-level spam protection with the default settings, it may turn out that you don't need to migrate some of your rules to EOP. Of course, if you have rules in place that enforce specific custom business policies, you can create those. [Transport Rules](http://technet.microsoft.com/library/c3d2031c-fb7b-4866-8ae1-32928d0138ef.aspx) provides detailed instructions for creating transport rules in EOP.</span></span> 
    
- <span data-ttu-id="6fe3c-p111">**IP の許可リストとブロック リストの IP**あればリストとブロック リストでは、EOP に、セットアップ プロセスの一環として、リストをコピーするのにはいくつかの時間を許可するユーザーごとを許可します。IP の詳細については、リストとブロック リストの IP を許可する、[接続フィルター ポリシーを構成する](../configure-the-connection-filter-policy.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fe3c-p111">**IP allow lists and IP block lists** If you have per-user allow lists and block lists, allow some time to copy the lists to EOP as part of your setup process. For more information about IP allow lists and IP block lists, see [Configure the connection filter policy](../configure-the-connection-filter-policy.md).</span></span>
    
- <span data-ttu-id="6fe3c-p112">**セキュリティで保護された通信** 暗号化メッセージングが必要なパートナーがいる場合は、これを Exchange 管理センターで設定することをお勧めします。このシナリオを構成するには、「 [Create connectors for a secure mail channel using transport layer security (TLS)](http://technet.microsoft.com/library/1ce4d6a4-41ba-4d1e-9ca9-e826252c1041.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fe3c-p112">**Secure Communication** If you have a partner that requires encrypted messaging, we recommend that you set this up in the Exchange admin center. To configure this scenario, see [Create connectors for a secure mail channel using transport layer security (TLS)](http://technet.microsoft.com/library/1ce4d6a4-41ba-4d1e-9ca9-e826252c1041.aspx).</span></span>
    
> [!TIP]
> <span data-ttu-id="6fe3c-p113">社内アプライアンスから EOP に切り替える場合は、ビジネス ルールのチェックを実行するアプライアンスまたはサーバーを配置したままにしておくことができます。たとえば、アプライアンスが送信メールのカスタム フィルター処理を実行しており、それを継続して実行させたい場合は、メールをインターネットにルーティングする前に、直接アプライアンスに送信し、追加のフィルター処理を行うように EOP を構成できます。この場合のメール フローの設定方法については、「[Exchange Online Protection Connectors - Outbound Smart Host Scenario](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx)」で説明しています。</span><span class="sxs-lookup"><span data-stu-id="6fe3c-p113">When you switch from an on-premises appliance to EOP, it is possible to leave your appliance or a server in place that performs business rule checks. For instance, if your appliance performs custom filtering on outbound mail, and you want it to continue doing so, you can configure EOP to send mail directly to the appliance for additional filtering, before it is routed to the Internet. [Exchange Online Protection Connectors - Outbound Smart Host Scenario](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx) shows you how to set up mail flow in this case.</span></span> 
  
