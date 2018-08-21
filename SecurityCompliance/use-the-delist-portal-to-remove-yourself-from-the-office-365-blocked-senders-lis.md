---
title: リストから除外のポータルを使って、Office 365 の受信拒否リストから自分自身を削除する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/18/2016
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
description: Office 365 にメール アドレスがある受信者にメールを送信しようとするときに、エラー メッセージが返される場合があります。エラー メッセージを受信しないようにするには、リストから除外のポータルを使って、Office 365 の受信拒否リストから自分自身を削除します。
ms.openlocfilehash: 127b305cdb27cffadc7ad6a43a5d2db2440365ca
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026234"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-list"></a><span data-ttu-id="60fb1-104">リストから除外のポータルを使って、Office 365 の受信拒否リストから自分自身を削除する</span><span class="sxs-lookup"><span data-stu-id="60fb1-104">Use the delist portal to remove yourself from the Office 365 blocked senders list</span></span>

<span data-ttu-id="60fb1-p102">Office 365 にメール アドレスがある受信者にメールを送信しようとするときに、エラー メッセージが返される場合があります。エラー メッセージを受信しないようにするには、リストから除外のポータルを使って、Office 365 の受信拒否リストから自分自身を削除します。</span><span class="sxs-lookup"><span data-stu-id="60fb1-p102">Are you getting an error message when you try to send an email to a recipient whose email address is in Office 365? If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the Office 365 blocked senders list.</span></span>
  
## <a name="what-is-the-office-365-blocked-senders-list"></a><span data-ttu-id="60fb1-107">Office 365 の 受信拒否リストとは何か</span><span class="sxs-lookup"><span data-stu-id="60fb1-107">What is the Office 365 blocked senders list?</span></span>

<span data-ttu-id="60fb1-p103">Microsoft は、受信拒否リストを使って、スパム、スプーフィング、フィッシング攻撃からお客様を保護しています。お客様のメール サーバーの IP アドレス、つまりお客様のメール サーバーがインターネット上でそれ自身を識別するために使うアドレスが、さまざまな理由によって Office 365 への潜在的な脅威としてタグ付けされる場合があります。Office 365 がその IP アドレスを受信拒否リストに追加すると、それ以降、データセンターを介してその IP アドレスと他のユーザーはまったく通信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="60fb1-p103">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks. Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Office 365 for one of a variety of reasons. When Office 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>
  
<span data-ttu-id="60fb1-111">メール メッセージに対して、次のようなエラーが含まれた応答を受信する場合、お客様は受信拒否リストに追加されています。</span><span class="sxs-lookup"><span data-stu-id="60fb1-111">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>
  
<span data-ttu-id="60fb1-p104">550 5.7.606-649 のアクセスが拒否されると、[ _IP アドレス_] の IP の送信を禁止されています。要求をこのリストからの削除を参照してくださいhttps://sender.office.com/し、指示に従います。詳細については、 [Office 365 の電子メールの配信不能レポート](http://go.microsoft.com/fwlink/?LinkID=526653)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60fb1-p104">550 5.7.606-649 Access denied, banned sending IP [ _IP address_]; To request removal from this list please visit https://sender.office.com/ and follow the directions. For more information please see [Email non-delivery reports in Office 365](http://go.microsoft.com/fwlink/?LinkID=526653).</span></span>
  
<span data-ttu-id="60fb1-114">ここで、 _IP address_ は、メール サーバーを稼働しているコンピューターの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="60fb1-114">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span> 
  
### <a name="to-use-the-office-365-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="60fb1-115">Office 365 のリストから除外のポータルを使って、受信拒否リストから自分自身を除外するには</span><span class="sxs-lookup"><span data-stu-id="60fb1-115">To use the Office 365 delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="60fb1-116">Web ブラウザーで、[https://sender.office.com](https://sender.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="60fb1-116">In a web browser, go to [https://sender.office.com](https://sender.office.com).</span></span>
    
2. <span data-ttu-id="60fb1-p105">ページ上の指示に従います。エラー メッセージを受信したメール アドレス、エラー メッセージで特定されている IP アドレスを使っていることを確認してください。1 回のアクセスにつき、1 つのメール アドレス、1 つの IP アドレスのみ入力できます。</span><span class="sxs-lookup"><span data-stu-id="60fb1-p105">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>
    
3. <span data-ttu-id="60fb1-120">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60fb1-120">Click **Submit**.</span></span>
    
    <span data-ttu-id="60fb1-p106">ポータルでは、指定した電子メール アドレスに電子メールを送信します。電子メールは次のようになります: ![delist ポータルを通じて要求を送信するときに受信した電子メールのスクリーン ショット](media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="60fb1-p106">The portal sends an email to the email address that you supply. The email will look something like the following:  ![Screenshot of email received when you submit a request through the delist portal](media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>
  
4. <span data-ttu-id="60fb1-123">リストから除外のポータルから受信したメールの中にある確認のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="60fb1-123">Click the confirmation link in the email sent to you by the delisting portal.</span></span>
    
    <span data-ttu-id="60fb1-124">これで、リストから除外のポータルに戻ります。</span><span class="sxs-lookup"><span data-stu-id="60fb1-124">This brings you back to the delist portal.</span></span>
    
5. <span data-ttu-id="60fb1-125">リストから除外のポータルで **[IP をリストから除外]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60fb1-125">In the delist portal, click **Delist IP**.</span></span>
    
    <span data-ttu-id="60fb1-p107">IP アドレスが受信拒否リストから削除されると、その IP アドレスからのメール メッセージが、Office 365 を使用する受信者に配信されるようになります。その IP アドレスから送信されるメールに不正や悪意のある内容が含まれていないことを確認してください。そのような内容が含まれていると、IP アドレスが再びブロックされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="60fb1-p107">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Office 365. So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>
    
