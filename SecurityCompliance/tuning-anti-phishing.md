---
title: Office 365 でフィッシング対策保護を調整する
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 管理者は、フィッシングメッセージがどのように使用されたのかや、今後のフィッシング対策メッセージを回避するために何を行う必要があるかを特定する方法について説明します。
ms.openlocfilehash: efda9e16c23e4533b6951e43ac085b7640e84576
ms.sourcegitcommit: 8a65a29aa3bfe5dcad0ff152a7cd795e02877dd9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2019
ms.locfileid: "30937826"
---
# <a name="tune-anti-phishing-protection-in-office-365"></a><span data-ttu-id="11b3a-103">Office 365 でフィッシング対策保護を調整する</span><span class="sxs-lookup"><span data-stu-id="11b3a-103">Tune anti-phishing protection in Office 365</span></span>

<span data-ttu-id="11b3a-104">Office 365 には、既定で有効になっているさまざまなフィッシング対策機能が用意されていますが、一部のフィッシングメッセージが依然としてメールボックスに届く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="11b3a-104">Although Office 365 comes with a variety of anti-phishing features that are enabled by default, it's possible that some phishing messages could still get through to your mailboxes.</span></span> <span data-ttu-id="11b3a-105">このトピックでは、フィッシングメッセージが通過した理由を検出するために実行できることと、誤って事態を発生さ_せず_に、Exchange Online 組織のフィッシング対策設定を調整する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="11b3a-105">This topic describes what you can do to discover why a phishing message got through, and what you can do to adjust the anti-phishing settings in your Exchange Online organization _without accidentally making things worse_.</span></span>

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a><span data-ttu-id="11b3a-106">最初に、侵害されたアカウントを処理して、より多くのフィッシングメッセージを取得することを禁止していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="11b3a-106">First things first: deal with any compromised accounts and make sure you block any more phishing messages from getting through</span></span>

<span data-ttu-id="11b3a-107">フィッシングメッセージの結果として受信者のアカウントが侵害された場合は、「 [Office 365 で侵害された電子メールアカウントに応答する](responding-to-a-compromised-email-account.md)」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="11b3a-107">If a recipient's account was compromised as a result of the phishing message, follow the steps in [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="11b3a-108">サブスクリプションに Advanced Threat Protection (ATP) が含まれている場合は、 [Office 365 脅威インテリジェンス](office-365-ti.md)を使用して、フィッシングメッセージを受信した他のユーザーを識別できます。</span><span class="sxs-lookup"><span data-stu-id="11b3a-108">If your subscription includes Advanced Threat Protection (ATP), you can use [Office 365 Threat Intelligence](office-365-ti.md) to identify other users who also received the phishing message.</span></span> <span data-ttu-id="11b3a-109">フィッシングメッセージをブロックするための追加のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="11b3a-109">You have additional options to block phishing messages:</span></span>

- [<span data-ttu-id="11b3a-110">ATP の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="11b3a-110">ATP Safe Links</span></span>](set-up-atp-safe-links-policies.md)

- [<span data-ttu-id="11b3a-111">ATP の安全な添付ファイル機能</span><span class="sxs-lookup"><span data-stu-id="11b3a-111">ATP Safe Attachments</span></span>](set-up-atp-safe-attachments-policies.md)

- <span data-ttu-id="11b3a-112">[ATP のフィッシング対策ポリシー](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="11b3a-112">[ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="11b3a-113">ポリシーの**高度なフィッシングしきい値**は、**標準**から**アグレッシブ**、アグレッシブ、または**最も積極的**なものに一時的に増やすことができます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="11b3a-113">Note that you can temporarily increase the **Advanced phishing thresholds** in the policy from **Standard** to **Aggressive**, **More aggressive**, or **Most aggressive**.</span></span>

<span data-ttu-id="11b3a-114">これらの ATP 機能が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="11b3a-114">Verify these ATP features are turned on.</span></span>

## <a name="report-the-phishing-message-to-microsoft"></a><span data-ttu-id="11b3a-115">フィッシングメッセージを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="11b3a-115">Report the phishing message to Microsoft</span></span>

<span data-ttu-id="11b3a-116">フィッシングメッセージの報告は、Office 365 のすべてのお客様を保護するために使用されるフィルターを調整するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="11b3a-116">Reporting phishing messages is helpful in tuning the filters that are used to protect all customers in Office 365.</span></span>

<span data-ttu-id="11b3a-117">フィッシングメッセージを新しい、それ以外の空のメッセージの_添付ファイルとして_ **phish@office365.microsoft.com**に送信します。</span><span class="sxs-lookup"><span data-stu-id="11b3a-117">Send the phishing message _as an attachment_ in a new, otherwise empty message to **phish@office365.microsoft.com**.</span></span> <span data-ttu-id="11b3a-118">元のメッセージを転送するだけではありません。それ以外の場合は、元のメッセージヘッダーを調べることはできません。</span><span class="sxs-lookup"><span data-stu-id="11b3a-118">Don't just forward the original message; otherwise, we can't examine the original message headers.</span></span> <span data-ttu-id="11b3a-119">または、outlook または web 上の outlook (旧称 outlook web App) で[レポートメッセージ](https://docs.microsoft.com/office365/securitycompliance/enable-the-report-message-add-in)アドインを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="11b3a-119">Or, you can use the [Report Message](https://docs.microsoft.com/office365/securitycompliance/enable-the-report-message-add-in) add-in in Outlook or Outlook on the web (formerly known as Outlook Web App).</span></span>

<span data-ttu-id="11b3a-120">詳細については、「[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11b3a-120">For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span>

## <a name="inspect-the-message-headers"></a><span data-ttu-id="11b3a-121">メッセージヘッダーを検査する</span><span class="sxs-lookup"><span data-stu-id="11b3a-121">Inspect the message headers</span></span>

<span data-ttu-id="11b3a-122">フィッシングメッセージのヘッダーを調べて、より多くのフィッシングメッセージが送られないようにすることができるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="11b3a-122">You can examine the headers of the phishing message to see if there's anything that you can do yourself to prevent more phishing messages from coming through.</span></span> <span data-ttu-id="11b3a-123">言い換えると、メッセージヘッダーを調べると、でフィッシングメッセージを許可する責任がある、組織内のすべての設定を識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="11b3a-123">In other words, examining the messages headers can help you identify any settings in your organization that were responsible for allowing the phishing messages in.</span></span>

<span data-ttu-id="11b3a-124">具体的には、メッセージヘッダーの**スパム対策**ヘッダーフィールドを調べて、スパムフィルター Verdict (sfv) の値で、スキップされたスパムまたはフィッシングのフィルター処理が表示されることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11b3a-124">Specifically, you should check the **X-Forefront-Antispam-Report** header field in the message headers for indications of skipped spam or phish filtering in the Spam Filtering Verdict (SFV) value.</span></span> <span data-ttu-id="11b3a-125">フィルター処理をスキップするメッセージには、 `SCL:-1`のエントリがあります。これは、サービスによって決定されたスパムまたはフィッシング verdicts を上書きすることによって、このメッセージが許可される設定の1つになります。</span><span class="sxs-lookup"><span data-stu-id="11b3a-125">Messages that skip filtering will have an entry of `SCL:-1`, which means one of your settings allowed this message through by overriding the spam or phish verdicts that were determined by the service.</span></span> <span data-ttu-id="11b3a-126">メッセージヘッダーと、使用可能なすべてのスパム対策およびフィッシングメッセージヘッダーの完全な一覧を取得する方法の詳細については、「[スパム対策メッセージヘッダー](https://docs.microsoft.com/office365/SecurityCompliance/anti-spam-message-headers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11b3a-126">For more details on how to get message headers and the complete list of all available anti-spam and anti-phish message headers, see [Anti-spam message headers](https://docs.microsoft.com/office365/SecurityCompliance/anti-spam-message-headers).</span></span>

## <a name="best-practices-to-stay-protected"></a><span data-ttu-id="11b3a-127">保護を維持するためのベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="11b3a-127">Best practices to stay protected</span></span>

- <span data-ttu-id="11b3a-128">office 365 のセキュリティ設定を評価するために、月単位で[office のセキュリティで保護されたスコア](office-365-secure-score.md)を実行します。</span><span class="sxs-lookup"><span data-stu-id="11b3a-128">On a monthly basis, run [Office 365 Secure Score](office-365-secure-score.md) to assess your Office 365 organization's security settings.</span></span>

- <span data-ttu-id="11b3a-129">[スプーフィングインテリジェンスレポート](learn-about-spoof-intelligence.md)を定期的に確認し、[フィッシング対策ポリシーのスプーフィング対策保護を有効](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy)にして、疑わしいメッセージをユーザーの迷惑メールフォルダーに配信する代わりに、そのメッセージを**検疫**します。</span><span class="sxs-lookup"><span data-stu-id="11b3a-129">Periodically review the [Spoof intelligence report](learn-about-spoof-intelligence.md) and [enable anti-spoofing protection in the anti-phishing policy](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy) to **quarantine** suspicious messages instead of delivering them to the user's Junk Email folder.</span></span>

- <span data-ttu-id="11b3a-130">[脅威保護状態レポート](view-reports-for-atp.md#threat-protection-status-report)を定期的に確認します。</span><span class="sxs-lookup"><span data-stu-id="11b3a-130">Periodically review the [Threat Protection Status report](view-reports-for-atp.md#threat-protection-status-report).</span></span>

- <span data-ttu-id="11b3a-131">ユーザーによっては、スパム対策ポリシーの [送信者を許可する] または [ドメインを許可する] の一覧に独自のドメインを設定することで、フィッシングメッセージを誤って許可することがあります。</span><span class="sxs-lookup"><span data-stu-id="11b3a-131">Some customers inadvertently allow phishing messages through by putting their own domains in the Allow sender or Allow domain list in anti-spam policies.</span></span> <span data-ttu-id="11b3a-132">これを行う場合は、細心の注意を払う必要があります。</span><span class="sxs-lookup"><span data-stu-id="11b3a-132">If you choose to do this, you must use extreme caution.</span></span> <span data-ttu-id="11b3a-133">この構成では、一部の正当なメッセージが許可されますが、通常は Office 365 スパムまたはフィッシングフィルターによってブロックされる悪意のあるメッセージも許可されます。</span><span class="sxs-lookup"><span data-stu-id="11b3a-133">Although this configuration will allow some legitimate messages through, it will also allow malicious messages that would normally be blocked by the Office 365 spam and/or phish filters.</span></span>

  <span data-ttu-id="11b3a-134">ドメイン内の送信者によって禁止されている正当なメッセージ (誤検知) を処理する最善の方法は、office 365 の_すべて_の電子メールドメインについて、DNS の SPF、dkim、および DMARC レコードを完全に完全に構成することです。</span><span class="sxs-lookup"><span data-stu-id="11b3a-134">The best way to deal with legitimate messages that are blocked by Office 365 (false positives) that involve senders in your domain is to fully and completely configure the SPF, DKIM, and DMARC records in DNS for _all_ of your email domains in Office 365:</span></span>

  - <span data-ttu-id="11b3a-135">SPF レコードが、ドメイン内の送信者の電子メールの_すべて_のソースを識別していることを確認します (サードパーティのサービスを忘れないでください)。</span><span class="sxs-lookup"><span data-stu-id="11b3a-135">Verify that your SPF record identifies _all_ sources of email for senders in your domain (don't forget third-party services!).</span></span>

  - <span data-ttu-id="11b3a-136">ハード fail (\-) を使用して、承認されていない送信者が電子メールシステムによって拒否されるようにします。</span><span class="sxs-lookup"><span data-stu-id="11b3a-136">Use hard fail (\-) to ensure that unauthorized senders are rejected by email systems that are configured to do so.</span></span> <span data-ttu-id="11b3a-137">[スプーフィングインテリジェンス](https://docs.microsoft.com/office365/securitycompliance/learn-about-spoof-intelligence)を使用すると、ドメインを使用している送信者を特定し、SPF レコードに承認されたサードパーティの送信者を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="11b3a-137">You can use [spoof intelligence](https://docs.microsoft.com/office365/securitycompliance/learn-about-spoof-intelligence) to help identify senders that are using your domain so that you can include authorized third-party senders in your SPF record.</span></span>

  <span data-ttu-id="11b3a-138">構成手順については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11b3a-138">For configuration instructions, see:</span></span>
  
  - [<span data-ttu-id="11b3a-139">スプーフィングを防止するために Office 365 で SPF を設定する</span><span class="sxs-lookup"><span data-stu-id="11b3a-139">Set up SPF in Office 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [<span data-ttu-id="11b3a-140">DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する</span><span class="sxs-lookup"><span data-stu-id="11b3a-140">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md)

  - [<span data-ttu-id="11b3a-141">DMARC を使用して Office で電子メールを検証する365</span><span class="sxs-lookup"><span data-stu-id="11b3a-141">Use DMARC to validate email in Office 365</span></span>](use-dmarc-to-validate-email.md)

- <span data-ttu-id="11b3a-142">可能な限り、自分のドメインのメールを Office 365 に直接配信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="11b3a-142">Whenever possible, we recommend that you deliver email for your domain directly to Office 365.</span></span> <span data-ttu-id="11b3a-143">言い換えると、office 365 ドメインの MX レコードを office 365 にポイントします。</span><span class="sxs-lookup"><span data-stu-id="11b3a-143">In other words, point your Office 365 domain's MX record to Office 365.</span></span> <span data-ttu-id="11b3a-144">Exchange Online protection (EOP) は、メールが Office 365 に直接配信される場合に、クラウドユーザーに最高の保護を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="11b3a-144">Exchange Online Protection (EOP) is able to provide the best protection for your cloud users when their mail is delivered directly to Office 365.</span></span> <span data-ttu-id="11b3a-145">EOP の前にサードパーティの電子メールの検疫システムを使用する必要がある場合は、[ここに記載](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)されているガイダンスに従っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="11b3a-145">If you must use a third-party email hygiene system in front of EOP, ensure you have followed the guidance [here](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span></span>

- <span data-ttu-id="11b3a-146">複数要素認証 (MFA) は、侵害されたアカウントを防止するための最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="11b3a-146">Multi factor authentication (MFA) is a really good way to prevent compromised accounts.</span></span> <span data-ttu-id="11b3a-147">すべてのユーザーに対して MFA を有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="11b3a-147">You should strongly consider enabling MFA for all of your users.</span></span> <span data-ttu-id="11b3a-148">段階的なアプローチの場合は、すべてのユーザーに対して mfa を有効にする前に、最も機密性の高いユーザー (管理者、役員など) に対して mfa を有効にすることから始めます。</span><span class="sxs-lookup"><span data-stu-id="11b3a-148">For a phased approach, start by enabling MFA for your most sensitive users (admins, executives, etc.) before you enable MFA for everyone.</span></span> <span data-ttu-id="11b3a-149">手順については、「[多要素認証をセットアップ](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11b3a-149">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="11b3a-150">外部の受信者へのルールの転送は、多くの場合、攻撃者がデータを抽出するために使用します。</span><span class="sxs-lookup"><span data-stu-id="11b3a-150">Forwarding rules to external recipients are often used by attackers to extract data.</span></span> <span data-ttu-id="11b3a-151">「 [Office 365 のセキュリティで保護されたスコア](office-365-secure-score.md)の情報を**確認**する」の情報を使用して、外部の受信者に対する転送ルールを見つけて、それを防止します。</span><span class="sxs-lookup"><span data-stu-id="11b3a-151">Use the **Review mailbox forwarding rules** information in [Office 365 Secure Score](office-365-secure-score.md) to find and even prevent forwarding rules to external recipients.</span></span> <span data-ttu-id="11b3a-152">詳細については、「[セキュリティで保護されたスコアでクライアントの外部転送ルールを軽減](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11b3a-152">For more information, see [Mitigating Client External Forwarding Rules with Secure Score](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/).</span></span>