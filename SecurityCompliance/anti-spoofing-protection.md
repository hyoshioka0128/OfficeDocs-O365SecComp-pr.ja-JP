---
title: Office 365 でのスプーフィング対策保護
ms.author: tracyp
author: MSFTtracyp
manager: dansimp
ms.date: 03/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: この記事では、Office 365 で、偽造された送信者ドメイン (スプーフィングされたドメイン) を使用するフィッシング攻撃を軽減する方法について説明します。 これは、メッセージを分析して、標準の電子メール認証の方法や、その他の送信者評価の手法を使用して認証できないメッセージをブロックすることで実現します。 今回の変更は、Office 365 の組織が対象になるフィッシング攻撃の数を減らすために実装されました。
ms.openlocfilehash: 066fbee27291ad8d89a7cb9d0f2abc586835b780
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598373"
---
# <a name="anti-spoofing-protection-in-office-365"></a>Office 365 でのスプーフィング対策保護

この記事では、Office 365 で、偽造された送信者ドメイン (スプーフィングされたドメイン) を使用するフィッシング攻撃を軽減する方法について説明します。 これは、メッセージを分析して、標準の電子メール認証方法や、その他の送信者評価の手法を使用して認証できないメッセージをブロックすることで実現します。 今回の変更は、Office 365 の組織が対象になるフィッシング攻撃の数を減らすために実装されました。
  
この記事では、今回の変更が実施された理由、今回の変更に対応するように準備する方法、影響を受けるメッセージの表示方法、メッセージに関するレポートの作成方法、誤検出を減らす方法、および Microsoft への送信者が今回の変更にどのように備えるべきかについても説明します。
  
Microsoft のスプーフィング対策テクノロジは、最初に Office 365 Enterprise E5 サブスクリプションを所有する組織、またはサブスクリプションに対応する Office 365 Advanced Threat Protection (ATP) アドオンを購入した組織に導入されました。 2018 年 10 月の時点では、Exchange Online Protection (EOP) を保有する組織にも保護の範囲を広げました。 また、すべてのフィルターが相互に学習する方法のため、Outlook.com のユーザーも影響を受ける可能性があります。
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a>フィッシング攻撃でスプーフィングが使用される方法

ユーザーの保護について、Microsoft はフィッシングの脅威を重大視しています。 迷惑メールの送信者やフィッシャー (フィッシング詐欺師) がよく使用する手法の 1 つにスプーフィング (なりすまし) があります。スプーフィングによって、送信者が偽装されると、メッセージは実際の発信元とは異なる送信者または送信元から送られてきたように見えます。 この手法は、多くの場合、ユーザーの認証情報を詐取しようとするフィッシング活動で使用されます。 Microsoft のスプーフィング対策テクノロジでは、具体的には「From: ヘッダー」の偽装を調べます。Outlook などの電子メール クライアントには、このヘッダーが表示されます。 Microsoft は高確率で From: ヘッダーがスプーフィングされていると確信すると、そのメッセージをスプーフィングとして識別します。
  
スプーフィング メッセージは、実際のユーザーに 2 つの悪影響を及ぼします。
  
### <a name="1-spoofed-messages-deceive-users"></a>1. ユーザーがスプーフィングされたメッセージにだまされる
  
1 つ目は、スプーフィングされたメッセージがユーザーにリンクをクリックするように誘導し、認証情報を提出させたり、マルウェアをダウンロードさせたり、機密コンテンツを含めてメッセージに返信させたりします (最後のものは「ビジネス メール詐欺」と呼ばれます)。 たとえば、次のフィッシング メッセージにある msoutlook94@service.outlook.com は、なりすましの送信者です。
  
![service.outlook.com を偽装しているフィッシング メッセージ](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
上記のものは実際には service.outlook.com から発信されたものではありませんが、そう見えるようにフィッシャーがスプーフィングしています。 ここでは、ユーザーをだまして、メッセージ内のリンクをクリックさせようとしています。
  
次の例では、contoso.com のスプーフィングです。
  
![フィッシング メッセージ: ビジネス メール詐欺](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
このメッセージは正当なものに見えますが、実際にはなりすましです。 このフィッシング メッセージは、フィッシングのサブカテゴリであるビジネス メール詐欺の一種です。

### <a name="2-users-confuse-real-messages-for-fake-ones"></a>2. ユーザーが本物と偽物のメッセージを混同する
  
2 つ目に、スプーフィングされたメッセージために、フィッシング メッセージについての知識があっても、本物とスプーフィングされたメッセージの見分けがつかないユーザーが疑いを持つようになってしまいます。 たとえば、次のものは Microsoft Security アカウントの電子メール アドレスから送信された本物のパスワード リセットのサンプルです。
  
![Microsoft の正当なパスワード リセット](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
上記のメッセージは Microsoft から発信されたものですが、その一方で、ユーザーは今までにフィッシング メッセージを何度も受け取っています。そのメッセージは、リンクをクリックするように誘導して、認証情報を提出させたり、マルウェアをダウンロードさせたり、機密コンテンツを含めてメッセージに返信させたりしようとします。 本物と偽物のパスワード リセットを見分けることが難しいため、多くのユーザーは、こうしたメッセージを無視したり、スパムとして報告したり、間違ったフィッシング詐欺として Microsoft に不要な報告を返したりします。

スプーフィングを阻止するために、電子メールのフィルター処理分野の業界は、電子メール認証のプロトコル ([SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)、[DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、[DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email) など) を開発しました。 DMARC は、ユーザーのメール クライアントに表示されるメッセージの送信者 (前述の例では、service.outlook.com、outlook.com、および accountprotection.microsoft.com) を SPF または DKIM をパスしたドメインで検査することでスプーフィングを防止します。 つまり、ユーザーに表示されるドメインは認証されているため、スプーフィングされていないことになります。 詳細な説明については、この記事で後述するセクション「*電子メール認証がスプーフィングの阻止には不十分なことがある理由*」を参照してください。
  
ただし、電子メール認証レコードはオプションであり、必須ではないという問題があります。 そのため、microsoft.com や skype.com などの強力な認証ポリシーを公開しているドメインはスプーフィングから保護されますが、公開している認証ポリシーが弱いドメインや認証ポリシーがまったく存在しないドメインはスプーフィングの対象になります。2018 年 3 月の時点で、Fortune 500 の企業のうち強力な電子メール認証ポリシーを公開しているドメインは 9% のみです。 残りの 91% はフィッシャーによってスプーフィングされる可能性があり、その他のポリシーを使用する電子メール フィルターで検出されないと、エンド ユーザーとデバイスに配信されてしまいます。
  
![Fortune 500 企業の DMARC ポリシー](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
Fortune 500 に含まれない中小規模の企業で強力な電子メール認証ポリシーを公開している割合はさらに少なくなり、北米と西ヨーロッパ以外のドメインでは、それよりも少ない割合になります。
  
これは重大な問題です。企業は電子メール認証のしくみを認識していないことがありますが、フィッシャーはそのしくみを理解して利用するためです。
  
SPF、DKIM、および DMARC のセットアップの詳細については、この記事で後述する「*Office 365 のユーザー*」のセクションを参照してください。 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a>暗黙的な電子メール認証によるスプーフィングの防止

フィッシングやスピア フィッシングは大きな問題であり、強力な電子メール認証ポリシーの導入は限られているため、Microsoft はユーザーを保護するための機能に投資を続けています。 そのため、Microsoft は*暗黙的な電子メール認証*を進めています。これは、ドメインが認証されていない場合、Microsoft は電子メール認証レコードが公開されているもとして、パスしない場合はそれに応じて処理します。 
  
これを実現するために、Microsoft は通常の電子メール認証に対する多数の拡張機能 (送信者評価、送受信者履歴、行動分析などの高度な手法) を構築しました。 電子メール認証を公開しないドメインから送信されたメッセージは、そのメッセージが正当であることを示す別のシグナルが含まれていないときには、スプーフィングのマークが付けられます。
  
これにより、エンド ユーザーは送信されてきた電子メールがスプーフィングされていないことを確信できるようになり、送信者は自分のドメインが偽装される心配がなくなり、Office 365 のユーザーはさらに優れた偽装保護などの保護を提供できるようになります。
  
Microsoft の一般発表については、「[大量のフィッシング詐欺: 第 2 部 - 強化された Office 365 のスプーフィング対策](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)」を参照してください。
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a>スプーフィングとして分類されたメッセージの識別

### <a name="composite-authentication"></a>複合認証

SPF、DKIM、および DMARC は、いずれも単独で役立つものですが、メッセージに明示的な認証レコードが存在していないときには、認証の状態を十分に伝達しません。 そのため、Microsoft は、複数のシグナルを 1 つの値に結合する複合認証 (略称: compauth) というアルゴリズムを開発しました。 Office 365 のユーザーは、メッセージのヘッダーに含まれる *Authentication-Results* ヘッダーに compauth の値がスタンプされます。 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|**CompAuth の結果**|**説明**|
|:-----|:-----|
|fail|メッセージは明示的な認証に失敗したか (送信側ドメインが DNS で明示的にレコードを公開している場合)、暗黙的な認証に失敗した (送信側ドメインが DNS でレコードを公開していないため、そのドメインでレコードが公開されたものとして Office 365 によって結果が挿入された場合)。|
|pass|メッセージは明示的な認証をパスした (メッセージは DMARC をパスしたか、[最適な推測で DMARC をパスした](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365))、または暗黙的な認証を高確度でパスした (送信側ドメインが電子メール認証レコードを公開していないが、Office 365 にはメッセージが正当である可能性が高いことを示す強力なバックエンドのシグナルがある)。|
|softpass|メッセージは暗黙的な認証を信頼度「低」から「中」でパスした (送信側ドメインが電子メール認証を公開していないが、Office 365 にはメッセージが正当であることを示すバックエンドのシグナルがある。ただし、そのシグナルの強度は弱い)。|
|none|メッセージは認証されていない (または、認証されたが一致しなかった)。ただし、送信者評価などの要因によって複合認証は適用されていない。|
   
|||
|:-----|:-----|
|**理由**|**説明**|
|0xx|メッセージは複合認証に失敗しました。<br/>**000** は、メッセージが拒否または検疫のアクションによって DMARC に失敗したことを意味します。  <br/>**001** は、メッセージが暗黙的な電子メール認証に失敗したことを意味します。 これは、送信側ドメインが電子メール認証レコードを公開していないか、公開していた場合でも弱い失敗ポリシー (SPF soft fail または neutral、p=none の DMARC ポリシー) があったことを意味します。  <br/>**002** は、組織に、スプーフィングされたメールの送信を明示的に禁止する送信者/ドメインのペアのポリシーがあることを意味します。この設定は、管理者が手動で設定します。  <br/>**010** は、メッセージが拒否または検疫のアクションによって DMARC に失敗して、送信側ドメインが組織の承認済みドメインに含まれていることを意味します (これは、自己完結型 (つまり組織内の) スプーフィングの一部です)。  <br/>**011** は、暗黙的な電子メール認証に失敗したが、送信側ドメインが組織の承認済みドメインのいずれかであることを意味します (これは、自己完結型 (つまり組織内の) スプーフィングの一部です)。|
|その他のすべてのコード (1xx、2xx、3xx、4xx、5xx)|メッセージが暗黙の認証にパスした理由や、認証なしでもアクションが適用されなかった理由に関する、さまざまな内部コードに対応します。|
   
管理者は (エンド ユーザーも) メッセージのヘッダーを調べることで、送信者がスプーフィングされている可能性があるという結論を Office 365 が導き出した過程を確認できます。
  
### <a name="differentiating-between-different-types-of-spoofing"></a>各種のスプーフィングの区別

Microsoft では、2 種類のスプーフィング メッセージを区別しています。
  
 **組織内スプーフィング**
  
自己完結型スプーフィングとも呼ばれます。これは、From: アドレスのドメインが受信者のドメインと同じまたは一致する (受信者のドメインが組織の[承認済みドメイン](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)のいずれかに含まれる) 場合、または From: アドレスのドメインが同じ組織の一部である場合に発生します。
  
たとえば、次に示す送信者と受信者のドメインは同じドメイン (contoso.com) です。 このページでのスパムボットの収集活動を阻止するために、電子メール アドレスにはスペースが挿入されています。
  
From: sender @ contoso.com
  
To: recipient @ contoso.com
  
次に示す送信者と受信者のドメインは組織のドメイン (fabrikam.com) が一致しています。
  
From: sender @ foo.fabrikam.com
  
To: recipient @ bar.fabrikam.com
  
次に示す送信者と受信者のドメイン (microsoft.com と bing.com) は異なっていますが、どちらも同じ組織に属しています (つまり、どちらも組織の承認済みドメインの一部です)。
  
From: sender @ microsoft.com
  
To: recipient @ bing.com
  
組織内スプーフィングに失敗したメッセージのヘッダーには、次の値が含まれています。
  
X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11
  
CAT はメッセージのカテゴリであり、通常は SPM (スパム) のスタンプが設定されています。ただし、メッセージ内にある別の種類のパターンによって HSPM (高確度スパム) や PHISH (フィッシング) などになっていることもあります。
  
SFTY はメッセージの安全性レベルです。最初の数字 (9) はメッセージがフィッシングであることを意味します。ドットの後にある 2 番目の数字のセット (11) は組織内スプーフィングであることを意味します。
  
2018 年後半の時点では、組織内スプーフィングについてスタンプされる複合認証の特定の理由コードはありません (タイムラインは未定義です)。
  
 **クロスドメイン スプーフィング**
  
これは、From: アドレスの送信側ドメインが受信側組織の外部ドメインになる場合に発生します。 クロスドメイン スプーフィングのために複合認証に失敗したメッセージのヘッダーには、次の値が含まれています。
  
Authentication-Results: … compauth=fail reason=000/001
  
X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22
  
どちらの場合も、メッセージには次に示す赤色の安全のヒントがスタンプされます (同じ内容のヒントが受信者のメールボックスの言語に応じてカスタマイズされていることもあります)。
  
![赤色の安全のヒント: 不正検出](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
From: アドレスを調べて受信者の電子メールの内容を知るか、電子メールのヘッダーを調べることでのみ、組織内スプーフィングとクロスドメイン スプーフィングを区別できます。
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a>Office 365 のユーザーが自分で新しいスプーフィング対策保護の準備を整える方法

### <a name="information-for-administrators"></a>管理者向けの情報

Office 365 の組織の管理者には、いくつかの注意が必要になる重要な情報があります。
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>電子メール認証がスプーフィングの阻止には不十分なことがある理由

新しいスプーフィング対策保護は、電子メール認証 (SPF、DKIM、および DMARC) に依存してメッセージにスプーフィングのマークを付けます。 一般的な例として、これまでに送信側ドメインが SPF レコードを公開したことがない場合が挙げられます。 SPF レコードが存在しない場合やレコードが不適切に設定されている場合は、Microsoft のバックエンド インテリジェンスによってメッセージが正当であると宣言されていないと、送信メッセージにスプーフィングのマークが付けられます。
  
たとえば、スプーフィング対策が展開されるまで、SPF、DKIM、および DMARC のどのレコードもないメッセージは次のようなものになります。 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
スプーフィング対策後、Office 365 Enterprise E5、EOP、または ATP を使用している場合は、compauth 値がスタンプされます。
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

これを修正するために example.com が SPF レコードを設定した場合は、DKIM レコードを設定していない場合でも、SPF にパスしたドメインと From: アドレスのドメインが一致するため、複合認証にパスするようになります。 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

また、DKIM レコードを設定して SPF レコードを設定していない場合でも、From: アドレスのドメインとパスした DKIM-Signature のドメインが一致するため同様に複合認証にパスします。 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

ただし、フィッシャーも SPF と DKIM を設定して自分のドメインでメッセージに署名しておいて、From: アドレスに異なるドメインを指定する可能性もあります。 SPF と DKIM のどちらも From: アドレスのドメインと一致する必要はないため、example.com が DMARC レコードを公開していないときには、DMARC を使用してスプーフィングのマークが付けられることはありません。 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

電子メール クライアント (Outlook や Outlook on the web などのあらゆる電子メール クライアント) には、From: ドメインのみが表示され、SPF や DKIM のドメインは表示されません。そのため、ユーザーは実際には maliciousDomain.com から送信されたメッセージを example.com から送信されたものだと誤解してしまう可能性があります。
  
![パスした SPF または DKIM と From: ドメインが一致しないにもかかわらず認証されたメッセージ](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
こうした理由から、Office 365 では From: アドレスのドメインが SPF または DKIM 署名のドメインと一致することを必要とします。また、一致しない場合は、メッセージが正当であることを示す何らかの内部シグナルが含まれていることを必要とします。 それ以外の場合、メッセージは compauth に失敗します。 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

このようにして、Office 365 のスプーフィング対策では、認証されていないドメイン、および認証が設定されていてもユーザーが確認してメッセージの送信者だと信じる From: アドレスのドメインと一致しないドメインからの保護を実施します。 これは、組織外のドメインと組織内のドメインの両方に当てはまります。
  
そのため、SPF と DKIM をパスしていても複合認証に失敗してスプーフィングのマークが付けられたメッセージを受信した場合は、From: アドレスのドメインが SPF および DKIM をパスしたドメインと一致していないことになります。
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a>スプーフィングされた電子メールの処理方法の変更について

現時点では、Office 365 のすべての組織 (ATP および ATP 以外) について、拒否または検疫のポリシーで DMARC に失敗したメッセージにはスパムのマークが付けられ、そのほとんどは高確度スパムの処理が実行されますが、通常のスパム処理が実行されることもあります (別のスパム ルールが先にメッセージをスパムとして識別したかどうかに応じて異なります)。 組織内スプーフィングの検出では、通常のスパム処理が実行されます。 この動作は、有効にする必要はありません。また、無効にすることはできません。
  
ただし、クロスドメイン スプーフィングのメッセージについては、今回の変更が実施されるまでは、通常のスパム、フィッシング、およびマルウェアのチェックが実行され、フィルターの別の部分でメッセージが疑わしいものと識別された場合に、それぞれスパム、フィッシング、またはマルウェアのマークが付けられます。 新しいクロスドメイン スプーフィング対策では、認証できないメッセージには、[フィッシング対策] \> [スプーフィング対策ポリシー] で定義されたアクションが既定で実行されます。 これが定義されていない場合は、ユーザーの [迷惑メール] フォルダーに移動されます。 場合によっては、より疑わしいメッセージには、赤色の安全のヒントもメッセージに追加されます。
  
その結果として、これまでにスパムのマークが付けられていた一部のメッセージには、引き続きスパムのマークが付けられますが、赤色の安全のヒントも付けられるようになります。また、以前は非スパムのマークが付けられていたメッセージに、赤色の安全性のヒントが追加された状態でスパムのマーク (CAT:SPOOF) が付けられることもあります。 さらに別のケースでは、すべてのスパムとフィッシングを検疫に移動していたユーザーは、それらが [迷惑メール] フォルダーに移動されるようになったことがわかります (この動作は変更できます。「[スプーフィング対策の設定の変更](#changing-your-anti-spoofing-settings)」を参照してください)。
  
メッセージがスプーフィングされる方法は複数ありますが (この記事で前述した「[各種のスプーフィングの区別](#differentiating-between-different-types-of-spoofing)」を参照)、2018 年 3 月の時点では、そうしたメッセージを Office 365 で処理する方法は統合されていません。 次の表は、動作が新しくなったクロスドメイン スプーフィング対策の簡単な概要です。 
  
|**スプーフィングの種類**|**カテゴリ**|**安全のヒントの追加**|**適用対象**|
|:-----|:-----|:-----|:-----|
|DMARC の失敗 (検疫または拒否)  <br/> |HSPM (既定)、SPM または PHSH の可能性もあり  <br/> |なし (現時点)  <br/> |すべての Office 365 ユーザー、Outlook.com  <br/> |
|自己完結型  <br/> |SPM  <br/> |あり  <br/> |すべての Office 365 組織、Outlook.com  <br/> |
|クロスドメイン  <br/> |SPOOF  <br/> |あり  <br/> |Office 365 Advanced Threat Protection および E5 ユーザー  <br/> |

### <a name="changing-your-anti-spoofing-settings"></a>スプーフィング対策の設定の変更

スプーフィング対策 (クロスドメイン) の設定を作成または更新するには、セキュリティ/コンプライアンス センターの [脅威の管理] \> [ポリシー] タブにある [フィッシング対策] \> [スプーフィング対策の設定] に移動します。 これまでにフィッシング対策の設定を作成したことがない場合は、その設定を作成する必要があります。
  
![フィッシング対策: 新しいポリシーの作成](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
既に作成したものがある場合は、それを選択して変更できます。
  
![フィッシング対策: 既存のポリシーの変更](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
ここで作成したポリシーを選択して、「[スプーフィング インテリジェンスの詳細情報](learn-about-spoof-intelligence.md)」の手順を進めます。
  
![スプーフィング対策の有効化または無効化](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![スプーフィング対策の安全のヒントの有効化または無効化](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
PowerShell を使用して新しいポリシーを作成するには、次のようにします。 
  
```powershell
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: The name should not exclude 64 characters, including spaces.
# If it does, you will need to pick a smaller name.
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy $name -RecipientDomainIs $domains
```

その後で、PowerShell を使用してフィッシング対策ポリシーのパラメーターを変更することもできます。[Set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps) のドキュメントを参照してください。 パラメーターとして、$name を指定できます。
  
```powershell
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

2018 年の後半の時点では、既定のポリシーを作成する必要はなくなりました。組織内のすべての受信者を対象とする既定のポリシーが自動的に作成されるため、手動で指定する必要はありません (上記のスクリーンショットは、最終的な実装前に変更されることがあります)。
  
![フィッシング対策の既定のポリシー](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
ユーザーが作成したポリシーとは異なり、既定のポリシーは削除することも、優先度を変更することも、対象とするユーザー、ドメイン、またはグループを選択することもできません。
  
![フィッシング対策の既定のポリシーの詳細](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
PowerShell を使用して既定の保護を設定するには、次のようにします。
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

スプーフィング対策保護は、Office 365 の前面に別のメール サーバーがある場合にのみ無効にします (詳細については、「スプーフィング対策の無効化が正当なシナリオ」を参照してください)。
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> メール パスの最初のホップが Office 365 であり、スプーフィングのマークが付けられた正当な電子メールが多すぎる場合は、まず、スプーフィングされた電子メールの自分のドメインへの送信を許可する送信者を設定します (「*認証されていない電子メールを送信する正当な送信者の管理*」を参照)。 それでも誤検知 (正当なメッセージにスプーフィングのマークが付けられる) が多すぎる場合でも、スプーフィング対策保護を完全に無効化することはお勧めしません。 その代りに、「高」ではなく「基本」の保護を選択することをお勧めします。 スプーフィングされた電子メールを放置すると長期的には組織に相当に高いコストがかかる可能性があるため、誤検知に対処するほうが良いでしょう。

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a>認証されていない電子メールを送信する正当な送信者の管理

Office 365 は、認証されていない電子メールを組織に送信している送信者を追跡しています。 その送信者がサービスによって正当ではないと判断されると、*compauth* 失敗のマークが付けられます。 これは、SPOOF として分類されますが、そのメッセージに適用されたスプーフィング対策ポリシーによって異なります。
  
ただし、管理者は、Office 365 の決定をオーバーライドして、スプーフィングされた電子メールの送信を許可する送信者を指定できます。
  
**方法 1: 組織がドメインを所有している場合は、電子メール認証を設定する**
  
この方法は、組織内スプーフィングの解決に使用できます。また、複数のテナントを所有している場合や複数のテナントとやり取りする場合のクロスドメイン スプーフィングの解決にも使用できます。 さらに、Office 365 内の別のユーザーや、別のプロバイダーでホストされているサード パーティに送信する場合のクロスドメイン スプーフィングを解決する際にも役立ちます。
  
詳細については、「[Office 365 のユーザー](#customers-of-office-365)」を参照してください。

**方法 2: スプーフィング インテリジェンスを使用して、認証されていない電子メールが許可された送信者を構成する**
  
認証されていないメッセージを組織に送信する送信者を許可するために、[スプーフィング インテリジェンス](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)を使用することもできます。 
  
外部ドメインの場合、スプーフィングされたユーザーは From アドレスのドメインになり、送信側インフラストラクチャは送信側 IP アドレス (/24 CIDR 範囲で分割)、または PTR レコードの組織のドメインになります (次のスクリーンショットでは、送信側 IP は 131.107.18.4 で、その PTR レコードは outbound.mail.protection.outlook.com であり、送信側インフラストラクチャについては outlook.com と表示されます)。
  
この送信者に認証されていない電子メールの送信を許可するには、**[いいえ]** を **[はい]** に変更します。
  
![スプーフィング対策の許可された送信者の設定](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
PowerShell を使用して、特定の送信者にドメインのスプーフィングを許可することもできます。
  
```powershell
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```powershell
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![Powershell から取得したスプーフィングされた送信者](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
上の画像では、このスクリーンショットに収まるようにするための改行が追加されています。 通常は、すべての値が 1 行で表示されます。
  
ファイルを編集し、outlook.com と bing.com に対応する行を見つけて、AllowedToSpoof エントリを No から Yes に変更します。
  
![Powershell でスプーフィングの許可を Yes に設定する](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
ファイルを保存して、次を実行します。
  
```powershell
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

これにより、bing.com は認証されていない電子メールを \*.outlook.com から送信できるようになります。

**方法 3: 送信者/受信者ペアの許可エントリを作成する**
  
特定の送信者に対するすべてのスパム フィルター処理をバイパスすることもできます。 詳細については、「[Office 365 の許可リストに安全に送信者を追加する方法](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/)」を参照してください。
  
この方法を使用すると、スパム フィルター処理と一部のフィッシング フィルター処理がスキップされます。ただし、マルウェア フィルター処理はスキップされません。
  
**方法 4: 送信者に問い合わせて、電子メール認証を設定するように依頼する**
  
スパムとフィッシングの問題があるため、Microsoft は、すべての送信者が電子メール認証を設定することをお勧めします。 送信側ドメインの管理者がわかっている場合は、その管理者に問い合わせて、電子メール認証レコードを設定するように要求し、一切のオーバーライドが不要になるようにします。 詳細については、この記事で後述する「[Office 365 ユーザーではないドメインの管理者](#administrators-of-domains-that-are-not-office-365-customers)」を参照してください。 
  
送信側ドメインで認証することは最初は難しい場合もありますが、そのドメインからの電子メールを迷惑メールとして処理したり拒否したりする電子メール フィルターが時間の経過と共に増え続け、適切に配信されるようにするために適切なレコードを設定することになります。
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a>スプーフィングのマークが付けられたメッセージの数量に関するレポートの表示

スプーフィング対策ポリシーを有効にすると、脅威の調査と対応の機能を使用して、フィッシングのマークが付けられたメッセージの量に関する数値を取得できます。 このためには、セキュリティ/コンプライアンス センター (SCC) の [脅威の管理] \> [エクスプローラー] に移動して、[表示] を [フィッシング] に設定し、[送信者のドメイン] または [保護の状態] でグループ化します。
  
![フィッシングのマークが付けられたメッセージ数の表示](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
各種のレポートを操作して、SPOOF のマークが付けられたメッセージも含めて、フィッシングのマークが付けられた数を確認できます。 詳細については、「[Office 365 の脅威の調査と対応についての作業を開始する](get-started-with-ti.md)」を参照してください。
  
現在のところ、どのメッセージにスプーフィングのマークが付けられたかを分類することはできません。その他の種類のフィッシングは分類できます (全般的なフィッシング、ドメインまたはユーザーの偽装など)。 将来、これはセキュリティ/コンプライアンス センターから実行できるようになる予定です。 そのときには、このレポートを起点として使用して、認証に失敗したためにスプーフィングのマークが付けられている正当な送信側ドメインを特定できるようになります。
  
次のスクリーンショットは、このデータの表示形式を提案するためのものですが、リリース時には変更されている可能性があります。
  
![検出の種類別に表示されたフィッシング レポート](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
ATP なしのユーザーと E5 ユーザーの場合、こうしたレポートは、将来、脅威に対する保護の状態 (TPS) レポートで利用できるようになりますが、少なくとも 24 時間の遅れがあると見込まれます。 このページは、それらの機能をセキュリティ/コンプライアンス センターに統合したときに更新される予定です。
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a>スプーフィングのマークが付けられるメッセージの数量の予測

Office 365 の設定が更新されて、スプーフィング対策の適用をオフにしたり、「基本」または「高」の適用でオンにしたりできるようになると、さまざまな設定でメッセージの処理がどのように変化するかを確認できるようになります。 つまり、スプーフィング対策がオフのときに、「基本」にするとスプーフィングとして検出されるメッセージの数を確認できるようになり、「基本」になっているときに、「高」にするとスプーフィングとして検出されるメッセージ数の増加量を確認できるようになるということです。
  
この機能は、現在開発中です。 詳細が明らかになり次第、このページはセキュリティ/コンプライアンス センターのスクリーンショットと、PowerShell の例の両方で更新される予定です。
  
![スプーフィング対策を有効にした場合の「What-If」レポート](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![スプーフィングされた送信者を許可する際の予定される UX](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a>スプーフィング対策の無効化が正当なシナリオ

スプーフィング対策はフィッシング攻撃からのユーザーの保護を向上するためのものです。そのため、スプーフィング対策保護を無効にすることはお勧めできません。 無効にすることで、ある程度の誤検知を短期的に解決することはできますが、長期的には、より大きなリスクにさらされることになります。 送信者側で認証を設定するコストや、フィッシング ポリシーの調整のためのコストは、通常、1 回限りのイベントであり、要求されるメンテナンスは最小限の定期的なもののみです。 その一方、フィッシング攻撃によってデータが公開されてしまったり、資産が侵害されてしまうと、その回復にかかるコストは非常に高くなります。
  
このため、スプーフィング対策保護を無効にするよりも、スプーフィング対策の誤検知に対処するほうが好結果が得られます。
  
ただし、スプーフィング対策の無効化が必要になる正当なシナリオもあります。そのシナリオとは、メッセージ ルーティングに別のメールのフィルター処理製品があり、メール パスの最初のホップが Office 365 ではない場合です。
  
![ユーザーの MX レコードは Office 365 を指していません](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
その他のサーバーは、オンプレミスの Exchange メール サーバー、Ironport などのメール フィルター処理デバイス、または別のクラウドでホストされているサービスです。
  
受信者ドメインの MX レコードが Office 365 を指していない場合は、スプーフィング対策を無効にする必要はありません。Office 365 は受信側ドメインの MX レコードを検索して、そのレコードが別のサービスを指しているときには、スプーフィング対策を抑止します。 ドメインの前面に別のサーバーがあるかどうかがわからない場合は、MX Toolbox などの Web サイトを使用すると MX レコードを参照できます。 これにより、次のような表示が得られます。
  
![MX レコードはドメインが Office 365 を指していないことを示しています](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
このドメインの MX レコードは Office 365 を指していないため、Office 365 はスプーフィング対策の実施を適用しません。
  
ただし、受信者のドメインが Office 365 を指して*いる*場合は、Office 365 の前面に別のサービスが存在していても、スプーフィング対策を無効にする必要があります。 最も一般的な例は、受信者の書き換えによるものです。 
  
![受信者の書き換えのルーティング図](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
ドメイン contoso.com の MX レコードはオンプレミスのサーバーを指していますが、ドメイン @office365.contoso.net の MX レコードは Office 365 を指しています。これは、MX レコードに \*.protection.outlook.com、または \*.eo.outlook.com が含まれているためです。
  
![MX レコードは Office 365 を指しているため、受信者が書き換えられている可能性があります](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
受信者のドメインの MX レコードが Office 365 指していない場合と、受信者の書き換えが実施された場合を区別するようにしてください。 この 2 つのケースを見分けることが重要です。
  
受信側ドメインの受信者が書き換えられたかどうか不明な場合は、メッセージのヘッダーを調べることで判断できます。
  
a) まず、メッセージのヘッダーで、Authentication-Results ヘッダーにある受信者ドメインを調べます。
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

受信者のドメインは、上記の赤色で示された太字のテキストでわかります (この例では、office365.contoso.net)。 これは、To: ヘッダーの受信者と異なる場合があります。
  
To: Example Recipient \<recipient @ contoso.com\>
  
実際の受信者のドメインの MX レコード検索を実行します。 MX に \*.protection.outlook.com、mail.messaging.microsoft.com、\*.eo.outlook.com、または mail.global.frontbridge.com が含まれている場合、その MX は Office 365 を指していることを意味します。
  
これらの値が含まれていない場合、その MX は Office 365 を指していないことを意味します。 これを確認するには、MX Toolbox などを使用できます。
  
この例では、contoso.com (To: ヘッダーにあるため受信者のように見えるドメイン) の MX レコードは、次に示すようにオンプレミスのサーバーを指しています。
  
![オンプレミスのサーバーを指している MX レコード](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
ただし、実際の受信者は office365.contoso.net であり、その MX レコードは Office 365 を指しています。
  
![MX は Office 365 を指しています (受信者が書き換えられている可能性が高い)](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
そのため、このメッセージは受信者が書き換えられている可能性があります。
  
b) その次に、受信者の書き換えの一般的なユースケースを区別するようにします。 受信者のドメインを \*.onmicrosoft.com に書き換えようとしている場合は、そのドメインを \*.mail.onmicrosoft.com に書き換えます。
  
別のサーバーの背後にルーティングされる最終的な受信者のドメインを特定し、その受信者のドメインの MX レコードが実際には Office 365 を指していることを特定したら、スプーフィング対策を無効にする作業を進めることができます。
  
繰り返しになりますが、ルーティング パスでドメインの最初のホップが Office 365 の場合はスプーフィング対策を無効にしないでください (その前に 1 つ以上のサービスがある場合にのみ実行してください)。
  
### <a name="how-to-disable-anti-spoofing"></a>スプーフィング対策を無効にする方法

フィッシング対策ポリシーが作成済みの場合は、EnableAntispoofEnforcement パラメーターを $false に設定します。
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false

```

無効にするポリシーの名前がわからない場合は、次のようにして表示できます。
  
```
Get-AntiphishPolicy | fl Name
```

既存のフィッシング対策ポリシーがない場合は、そのポリシーを作成してから無効にしてください (ポリシーがない場合でも、スプーフィング対策は適用されています。2018 年後半の時点で、既定のポリシーが自動で作成されるようになったため、既定のポリシーを作成することなく無効にできます)。 これは、複数の手順で実行する必要があります。
  
```
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: If the name is more than 64 characters, you will need to choose a smaller one
```

```
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy -RecipientDomainIs $domains
# Finally, scope the anti-phishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false

```

スプーフィング対策は、コマンドレットでのみ無効化できます (将来は、セキュリティ/コンプライアンス センターでも可能になります)。 PowerShell にアクセスできない場合は、サポート チケットを作成してください。
  
繰り返しになりますが、この操作は、Office 365 への送信時に間接的にルーティングされるドメインにのみ適用してください。 ある程度の誤検出を理由にスプーフィング対策を無効にする誘惑には負けないようにしてください。長期的には、誤検出に対処するほうが好結果が得られます。
  
### <a name="information-for-individual-users"></a>個々のユーザーに関する情報

個々のユーザーは、スプーフィング対策の安全のヒントに対する操作内容が制限されています。 ただし、一般的なシナリオを解決するために、いくつかのことを実行できます。
 
### <a name="common-scenario-1---discussion-lists"></a>一般的なシナリオ #1 - ディスカッション リスト

ディスカッション リストには、スプーフィング対策に関する既知の問題があります。このリストは、メッセージを転送して、その内容を変更するにもかかわらず元の From: アドレスが保持されるという方法に問題の原因があります。
  
たとえば、自分の電子メール アドレスが user @ contoso.com で、バード ウォッチングに興味があり、ディスカッション リスト birdwatchers @ example.com に参加するとします。 このディスカッション リストにメッセージを送信するときには、次の方法で送信することになります。
  
**From:** John Doe \<user @ contoso.com\> 
  
**宛先:** Birdwatcher のディスカッション リスト \<birdwatchers @ example.com\> 
  
**件名:** 今週、レーニア山からアオカケス を見ることができます 
  
今週、レーニア山からの風景を 眺めてみませんか?
  
電子メール リストはメッセージを受信すると、そのメッセージの書式を設定し、内容を変更して、ディスカッション リストの残りのメンバーに向けてメッセージをリプレイします。このメンバーは、多様な電子メール レシーバーから構成されています。
  
**From:** John Doe \<user @ contoso.com\> 
  
**宛先:** Birdwatcher のディスカッション リスト \<birdwatchers @ example.com\> 
  
**件名:** [BIRDWATCHERS] 今週、レーニア山からアオカケス を見ることができます 
  
今週、レーニア山からの風景を 眺めてみませんか?
  
---
  
このメッセージは、Birdwatchers ディスカッション リストに送信されました。 いつでも購読を解除できます。
  
上記のリプレイされたメッセージには、同じ From: アドレス (user @ contoso.com) がありますが、元のメッセージは件名にタグを追加して、メッセージの下側にフッターを追加することで変更されています。 この種のメッセージの変更は、メーリング リストでは一般的なものですが、誤検出の原因になることがあります。
  
組織内のいずれかのユーザーがメーリング リストの管理者になっている場合は、そのメーリング リストがスプーフィング対策をパスするように構成できます。
  
- DMARC.org で次のよくある質問を確認してください: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)

- 次のブログ記事の手順を参照してください: [DMARC との相互運用で失敗を回避するためのメーリング リスト運営者向けのヒント](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)

- メーリング リスト サーバーに ARC をサポートする更新プログラムをインストールすることを検討してください ([https://arc-spec.org](https://arc-spec.org/) を参照)

メーリング リストの所有者でない場合は、次のようにします。
  
- メーリング リストの管理者に、上記のいずれかのオプションを実装するように要求してください (この管理者は、メーリング リストを中継するドメインにも電子メール認証を設定する必要があります)。

- 電子メール クライアントで、メッセージを受信トレイに移動するメールボックス ルールを作成してください。 また、組織の管理者に許可ルールを設定するように要求するか、「認証されていない電子メールを送信する正当な送信者の管理」のセクションで説明するようにオーバーライドするように要求してください。

- Office 365 でサポート チケットを作成して、メーリング リストを正当なものとして扱うためのオーバーライドを作成してください。

### <a name="other-scenarios"></a>その他のシナリオ

1. 上記の一般的なシナリオのいずれにも当てはまらない場合は、そのメッセージを誤検出として Microsoft に報告してください。 詳細については、この記事で後述する「[スパムまたは非スパムのメッセージについて、どのように Microsoft に報告すればよいですか](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft)」のセクションを参照してください。 

2. また、サポート チケットとして Microsoft にこの件を提出できる電子メール管理者に問い合わせることもできます。 Microsoft のエンジニアリング チームは、メッセージにスプーフィングのマークが付けられた理由を調査します。

3. さらに、送信者がわかっていて、悪意のあるスプーフィングでないと確信している場合は、送信者に、認証されていないメール サーバーからメッセージを送信していることを返信で知らせてください。 これにより、元の送信者は要求された電子メール認証レコードを設定する IT 管理者に問い合わせることもあります。
  
ドメインの所有者に対して相当数の送信者が電子メール認証レコードの設定が必要なことを返信することで、ドメインの所有者の行動を促します。 Microsoft は必要なレコードを公開するためにドメインの所有者と協力しますが、個々のユーザーの要求が大きな支援になります。

4. 必要に応じて、送信者を [差出人セーフ リスト] に追加します。 ただし、そのアカウントをフィッシャーがスプーフィングすると、それが自分のメールボックスに配信される点に注意してください。 そのため、このオプションは慎重に使用してください。

## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a>スプーフィング対策保護に対して Microsoft への送信者が必要になる準備

現在、Microsoft (Office 365 または Outlook.com) にメッセージを送信する管理者は、電子メールが適切に認証されていることを確認する必要があります。そうしていないと、そのメールにはスパムまたはフィッシングのマークが付けられる可能性があります。
  
### <a name="customers-of-office-365"></a>Office 365 のユーザー

Office 365 のユーザーが Office 365 を使用して送信メールを送信する場合は、次のようにします。
  
- ドメインについては、[スプーフィングを防止するために Office 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- プライマリ ドメインについては、[DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)

- 正当な送信者を判断するために、ドメインに [DMARC レコードを設定することを検討する](use-dmarc-to-validate-email.md)

Microsoft は、SPF、DKIM、および DMARC のそれぞれに関する詳細な実装ガイドラインを提供しません。 ただし、オンラインで公開されている大量の情報があります。 また、組織が電子メール認証レコードを設定する際の支援を専門としているサード パーティ企業もあります。
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a>Office 365 のユーザーではないドメインの管理者

Office 365 のユーザーではないドメインの管理者は、次のようにします。
  
- SPF を設定してドメインの送信側 IP アドレスを公開する必要があります。また、DKIM (使用可能な場合) を設定してメッセージにデジタル署名する必要があります。 さらに、DMARC レコードを設定することも検討してください。

- 自分の代りに電子メールを転送するバルク送信者がいる場合は、その送信者と協力して、From: アドレスの送信側ドメインが SPF または DMARC をパスするドメインと一致するような方法で電子メールを送信する必要があります (送信側ドメインを所有している場合)。

- オンプレミスのメール サーバーがある場合、またはサービスとしてのソフトウェア プロバイダーや、クラウド ホスティング サービス (Microsoft Azure、GoDaddy、Rackspace、アマゾン ウェブ サービスなど) からメールを送信する場合は、それらを SPF レコードに追加する必要があります。

- ISP でホストされている小規模ドメインの場合は、その ISP が用意した手順に従って SPF レコードを設定する必要があります。 ほとんどの ISP は、この種の手順を用意していて、その会社のサポート ページに掲載しています。

- これまでは電子メール認証レコードを公開する必要がなく、問題なく機能していたとしても、Microsoft に電子メールを送信するには電子メール認証レコードの公開が必要になります。 そうすることが、フィッシング詐欺の撲滅に協力することになり、自分やメール送信先の組織がフィッシング詐欺の被害を受ける可能性を減らすことになります。

### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a>自分のドメインとして電子メールを送信した送信者がわからない場合

多くのドメインは、すべての送信者を把握しているわけではないため、SPF レコードを公開していません。 そのことは問題になりません。すべての送信者がわかっている必要はありません。 その代りに、自分が知っているもの、特に会社のトラフィックがある場所の SPF レコードを公開することから始めて、次のニュートラル SPF ポリシー (?all) を公開します。
  
example.com IN TXT "v=spf1 include:spf.example.com ?all"
  
ニュートラル ポリシーとは、会社のインフラストラクチャから送信されるすべての電子メールが、その他すべての電子メール レシーバーの場所で電子メール認証にパスするという意味です。 不明な送信者から送られた電子メールは、ニュートラルにフォールバックします。これは、SPF レコードをまったく公開していないこととほとんど同じです。
  
Office 365 への送信時、会社のトラフィックから送信された電子メールには認証済みのマークが付けられますが、不明な送信元から送信された電子メールには引き続きスプーフィングのマークが付けられることがあります (Office 365 によって暗黙的に認証できるかどうかによって異なります)。 ただし、これは Office 365 によってすべての電子メールにスプーフィングのマークが付けられることからの改善に過ぎません。
  
フォールバック ポリシーが ?all の SPF レコードを出発点として、段階的に送信側インフラストラクチャを増強して、より厳密なポリシーを公開してください。 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a>メーリング リストの所有者の場合

セクション「[一般的なシナリオ #1 - ディスカッション リスト](#common-scenario-1---discussion-lists)」を参照してください。
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a>インターネット サービス プロバイダー (ISP)、電子メール サービス プロバイダー (ESP)、クラウド ホスティング サービスなどのインフラストラクチャ プロバイダーの場合

ドメインの電子メールをホストしていて、そのドメインで電子メールを送信する場合、または電子メールを送信できるホスティング インフラストラクチャを提供している場合は、次のようにします。
  
- 顧客に SPF レコードで公開する内容の詳細についてのドキュメントを提供します。

- 顧客が明示的に設定していない場合でも、送信電子メールの DKIM 署名に署名することを検討します (既定のドメインで署名)。 DKIM 署名では電子メールに二重署名することもできます (顧客のドメインで設定されている場合に 1 つ目の署名、会社の DKIM 署名で 2 つ目の署名)。

プラットフォームから送信された電子メールを認証していても Microsoft への配信が可能であることが保証されるわけではありませんが、少なくとも、認証されていないという理由で Microsoft がそのメールを迷惑メールとして処理することはなくなります。 Outlook.com での電子メールのフィルター処理に関する詳細については、[Outlook.com Postmaster ページ](https://postmaster.live.com/pm/postmaster.aspx)を参照してください。
  
サービス プロバイダーのベスト プラクティスの詳細については、「[M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)」を参照してください。
  
## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="why-is-microsoft-making-this-change"></a>Microsoft が今回の変更を行う理由

フィッシング攻撃の影響により、15 年以上前から電子メール認証が実施されているため、Microsoft は認証されていない電子メールを許可し続けるリスクのほうが、正当な電子メールを失うリスクよりも高いと判断しています。
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a>今回の変更により正当なメールにスパムのマークが付けられることがありますか

当初は、一部のメッセージにスパムのマークが付けられるようになります。 ただし、時間の経過と共に、送信者が適応するようになり、ほとんどのメール パスでスプーフィングとして間違ったラベルが付けられるメッセージの量は無視できる程度になります。
  
Microsoft は、この機能をお客様に展開する数週間前に率先して導入しました。 最初のうちは混乱もありましたが、それも次第に収まりました。
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a>Microsoft は、この機能を Outlook.com と Advanced Threat Protection のない Office 365 ユーザーに導入しますか

Microsoft のスプーフィング対策テクノロジは、最初に Office 365 Enterprise E5 サブスクリプションを所有する組織、またはサブスクリプションに対応する Office 365 Advanced Threat Protection (ATP) アドオンを購入した組織に導入されました。 2018 年 10 月の時点では、Exchange Online Protection (EOP) の所有組織にも保護の範囲を広げました。 今後は、Outlook.com にもリリースする予定です。 ただし、その場合は、レポートやカスタム オーバーライドなどの一部の機能が適用されない可能性があります。
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>スパムまたは非スパムのメッセージについて、どのように Microsoft に報告すればよいですか

[Outlook 用の迷惑メール報告アドイン](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)を使用できます。このアドインをインストールしていない場合は、[スパム、非スパム、およびフィッシング詐欺メッセージを分析のために Microsoft に送信する](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx)こともできます。
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a>ドメイン管理者ですが、把握できていない送信者がいます

「[Office 365 のユーザーではないドメインの管理者](#administrators-of-domains-that-are-not-office-365-customers)」を参照してください。
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a>Office 365 がプライマリ フィルターだとしても、自分の組織のスプーフィング対策保護を無効にすると問題が発生しますか

これについては、お勧めできません。より多くの見逃されたフィッシング メッセージやスパム メッセージにさらされるようになります。 すべてのフィッシングがスプーフィングであるわけでなく、すべてのスプーフィングが見逃されるわけでもありません。 ただし、スプーフィング対策を有効にしているお客様よりもリスクは高くなります。
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>スプーフィング対策保護を有効にすることで、すべてのフィッシングから保護されるようになりますか

残念ながら、そうはなりません。フィッシャーは侵害されたアカウントやフリー サービスのアカウントを設定するなど、別の手法を採用するようになるためです。 ただし、Office 365 の各保護層は連携するように設計されていて、相互をベースとして構築されているため、フィッシング対策保護は、そのような別の種類のフィッシング方法の検出にも優れています。
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a>他の大規模な電子メール レシーバーが認証されていない電子メールをブロックすることはありますか

ほとんどすべての大規模電子メール レシーバーが、従来型の SPF、DKIM、および DMARC を実装してます。 一部のレシーバーは、そうした標準のものよりも厳密な別のチェックを実施していますが、認証されていない電子メールをブロックしてスプーフィングとして扱う Office 365 に匹敵するものはわずかしかありません。 ただし、この業界のほとんどが、特にフィッシング詐欺の問題を理由に、この種の電子メールに対する厳しさを増しています。
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a>スプーフィング対策を有効にしていても、"SPF Hard Fail" に対して高度な迷惑メール フィルターのオプションを有効にする必要がありますか

いいえ。このオプションは不要になりました。スプーフィング対策機能では、SPF hard fail だけでなく、それよりも広範な条件のセットが考慮されます。 スプーフィング対策を有効にしているときに、SPF Hard Fail オプションも有効にすると、誤検出が多くなく可能性があります。 この機能は無効にすることをお勧めします。この機能によって、追加で捕捉されるスパムやフィッシングはほとんどなく、多くの場合に誤検出が発生します。
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a>センダー リライティング スキーム (SRS) は転送された電子メールの問題修正に役立ちますか

SRS は転送された電子メールの問題を部分的にしか解決しません。 SMTP MAIL FROM を書き換えることで、SRS では転送されたメッセージが次の宛先で確実に SPF をパスするようになります。 ただし、スプーフィング対策は MAIL FROM または DKIM 署名のドメイン (またはその他のシグナル) と組み合わせた From: アドレスに基づいているため、転送された電子メールにスプーフィングのマークが付けられることを回避するには不十分です。
