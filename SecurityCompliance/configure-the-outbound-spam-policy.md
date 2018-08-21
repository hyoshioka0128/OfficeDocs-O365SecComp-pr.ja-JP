---
title: 送信スパム ポリシーを構成する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/10/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
description: 送信スパム フィルターは常に有効場合は、送信する電子メールを送るためにサービスを使用すると、サービスは、それぞれの受信者を使用して組織を保護します。
ms.openlocfilehash: 3a3e07731e16da148131ceb6f555e84ed94f7ae5
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026304"
---
# <a name="configure-the-outbound-spam-policy"></a><span data-ttu-id="f7d5b-103">送信スパム ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="f7d5b-103">Configure the outbound spam policy</span></span>

<span data-ttu-id="f7d5b-p101">送信電子メールを送信するサービスを使用している場合は、送信スパム フィルターが常時有効になっているため、このフィルターによりこのサービスを利用している組織と対象の受信者は保護されます。送信スパム フィルターは、受信フィルターと同様、接続フィルターとコンテンツ フィルターで構成されていますが、送信フィルターの設定は構成できません。送信メッセージがスパムとして判断されると、より危険度の高い配信プール経由でルーティングされます。これにより、通常の送信 IP プールが禁止リストに追加される可能性が低くなります。ユーザーがこのサービス経由で送信スパムを送信し続けると、ユーザーはメッセージの送信からブロックされます。送信スパム フィルターを無効にしたり変更したりすることはできませんが、既定の送信スパム ポリシーを使用して企業全体の送信スパム設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="f7d5b-p101">Outbound spam filtering is always enabled if you use the service for sending outbound email, thereby protecting organizations using the service and their intended recipients. Similar to inbound filtering, outbound spam filtering is comprised of connection filtering and content filtering, however the outbound filter settings are not configurable. If an outbound message is determined to be spam, it is routed through the higher risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list. If a customer continues to send outbound spam through the service, they will be blocked from sending messages. Although outbound spam filtering cannot be disabled or changed, you can configure several company-wide outbound spam settings via the default outbound spam policy.</span></span> 
  
<span data-ttu-id="f7d5b-109">次のビデオは、送信スパム ポリシーの構成方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f7d5b-109">The following video shows how to configure the outbound spam policy:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1f20d655-0d3d-4141-9cae-e57f5a6cffe8?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f7d5b-110">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="f7d5b-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="f7d5b-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="f7d5b-111"></span></span>

<span data-ttu-id="f7d5b-112">予想所要時間 : 5 分</span><span class="sxs-lookup"><span data-stu-id="f7d5b-112">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="f7d5b-p102">このプロシージャまたはプロシージャを実行する前にアクセス許可を割り当てる必要があります。必要なアクセス許可を表示するには、エントリを参照"スパム対策[機能のアクセス許可を Exchange Online で](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)トピックです。</span><span class="sxs-lookup"><span data-stu-id="f7d5b-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="f7d5b-115">このトピックの手順で使用可能なキーボード ショートカットについては、「**Exchange 管理センターのキーボード ショートカット**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7d5b-115">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
<span data-ttu-id="f7d5b-p103">リモート PowerShell を使用して次の手順を実行できます。[Get HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx)コマンドレットを使用すると、設定、および送信スパム ポリシーの設定を編集するのには[一連の HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx)を確認します。Exchange のオンライン保護への接続に Windows PowerShell を使用する方法については、 [Exchange のオンライン保護 PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=627290)を参照してください。Exchange Online に接続する Windows PowerShell を使用する方法については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7d5b-p103">The following procedure can also be performed via remote PowerShell. Use the [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) cmdlet to review your settings, and the [Set-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) to edit your outbound spam policy settings. To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290). To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
  
## <a name="use-the-eac-to-edit-the-default-outbound-spam-policy"></a><span data-ttu-id="f7d5b-120">EAC を使用して既定の送信スパム ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="f7d5b-120">Use the EAC to edit the default outbound spam policy</span></span>
<span data-ttu-id="f7d5b-121"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="f7d5b-121"></span></span>

<span data-ttu-id="f7d5b-122">既定の送信スパム ポリシーを編集するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7d5b-122">Use the following procedure to edit the default outbound spam policy:</span></span>
  
### <a name="to-configure-the-default-outbound-spam-policy"></a><span data-ttu-id="f7d5b-123">既定の送信スパム ポリシーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f7d5b-123">To configure the default outbound spam policy</span></span>

1. <span data-ttu-id="f7d5b-124">Exchange 管理センター (EAC) で、 **[保護]** \> **[送信スパム]** に移動し、既定のポリシーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7d5b-124">In the Exchange admin center (EAC), navigate to **Protection** \> **Outbound spam**, and then double-click the default policy.</span></span>
    
2. <span data-ttu-id="f7d5b-125">**[送信スパム基本設定]** メニュー オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7d5b-125">Select the **Outbound spam preferences** menu option.</span></span> 
    
3. <span data-ttu-id="f7d5b-126">送信メッセージに関連する以下のチェック ボックスにチェック マークを付けてから、付随して表示される入力ボックスに、関連する電子メール アドレスを指定します (解決結果が有効な SMTP 配信先であるなら、配信先リストも可能)。</span><span class="sxs-lookup"><span data-stu-id="f7d5b-126">Select the following check boxes pertaining to outbound messages, and then specify an associated email address or addresses in the accompanying input box (these can be distribution lists if they resolve as valid SMTP destinations):</span></span>
    
1. <span data-ttu-id="f7d5b-p104">**[すべての疑わしい送信電子メール メッセージのコピーを次の電子メール アドレスに送信します]**。(SCL 評価に関係なく) フィルターによってスパムとしてマークされたメッセージです。フィルターによって拒否されませんが、より危険度の高い配信プールでルーティングされます。複数のアドレスはセミコロンで区切ります。指定された受信者はブラインド カーボン コピー (BCC) アドレスとしてメッセージを受け取ることに注意してください (差出人フィールドと宛先フィールドは元の送信者と受信者です)。</span><span class="sxs-lookup"><span data-stu-id="f7d5b-p104">**Send a copy of all suspicious outbound email messages to the following email address or addresses**. These are messages that are marked as spam by the filter (regardless of the SCL rating). They are not rejected by the filter but are routed through the higher risk delivery pool. Separate multiple addresses with a semicolon. Note that the recipients specified will receive the messages as a Blind carbon copy (Bcc) address (the From and To fields are the original sender and recipient).</span></span>
    
2. <span data-ttu-id="f7d5b-p105">**[送信者が送信スパムの送信をブロックされているとき、次の電子メール アドレスに通知を送信]**。複数のアドレスはセミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="f7d5b-p105">**Send a notification to the following email address when a sender is blocked sending outbound spam**. Separate multiple addresses with a semicolon.</span></span>
    
    <span data-ttu-id="f7d5b-p106">特定のユーザーから膨大な数のスパムが発信されると、そのユーザーによるメール メッセージの送信は無効になります。この設定の使用を指定したドメインの管理者は、このユーザーによるメッセージ送信がブロックされていることを通知されます。この通知がどのように表示されるかを確認するには、「[送信者が送信スパムの送信をブロックされる場合の通知例](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)」をご覧ください。作業を再度有効にする方法については、「[Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f7d5b-p106">When a significant amount of spam is originating from a particular user, the user is disabled from sending email messages. The administrator for the domain, who is specified using this setting, will be informed that outbound messages are blocked for this user. To see what this notification looks like, see [Sample notification when a sender is blocked sending outbound spam](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md). For information about getting re-enabled, see [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span></span>
    
4. <span data-ttu-id="f7d5b-p107">**[保存]** をクリックします。既定のポリシー設定の概要が右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7d5b-p107">Click **save**. A summary of your default policy settings appears in the right pane.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="f7d5b-140">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f7d5b-140">For more information</span></span>
<span data-ttu-id="f7d5b-141"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="f7d5b-141"></span></span>

[<span data-ttu-id="f7d5b-142">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="f7d5b-142">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)
  
[<span data-ttu-id="f7d5b-143">スパム対策の保護に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="f7d5b-143">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  
