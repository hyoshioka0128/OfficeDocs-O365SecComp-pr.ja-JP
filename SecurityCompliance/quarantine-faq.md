---
title: 検疫に関する FAQ
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/16/2017
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: このトピックでは、ホストされた検疫についてのよく寄せられる質問 (FAQ) とその回答を紹介します。
ms.openlocfilehash: 907bb7eaee9c7aef490c74677b4f277b89ba3115
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35601274"
---
# <a name="quarantine-faq"></a>検疫に関する FAQ

このトピックでは、ホストされた検疫についてのよく寄せられる質問 (FAQ) とその回答を紹介します。回答は Microsoft Exchange Online および Exchange Online Protection のお客様を対象としています。
  
 **Q: 検疫でマルウェアによって検疫されたメッセージを管理するにはどうすればよいですか?**
  
検疫に送信された&amp;メッセージにマルウェアが含まれている場合に、そのメッセージを表示および操作するには、セキュリティコンプライアンスセンターを使用する必要があります。 For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).
  
 **Q. スパム検疫済みメッセージを検疫に送るには、どのようにサービスを構成しますか?**
  
A. 既定では、コンテンツ フィルターで処理されたメッセージは受信者の迷惑メール フォルダーに送信されます。しかし管理者は、代わりにコンテンツ フィルター ポリシーを構成することで、スパム検疫済みメッセージを検疫に送ることができます。コンテンツ フィルターで処理されたメッセージに対して実行できるさまざまな操作の詳細については、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。
  
 **Q. このサービスには、スパム検疫メッセージの管理者およびエンド ユーザー管理はありますか?**
  
A. 管理者は、検疫された電子メール メッセージすべてに関する詳細を Exchange 管理センター (EAC) で検索し、表示することができます。メッセージを検索したら、特定のユーザーに解放し、さらにオプションとして Microsoft スパム分析チームに誤検知 (迷惑メールではない) として報告することもできます。詳細については、「[管理者として検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-an-administrator.md)」を参照してください。
  
エンド ユーザーとして、自分のスパム検疫メッセージを以下を通じて管理することができます。 
  
- スパム検疫ユーザー インターフェース。 詳細については、「[Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)」を参照してください。
        
 **Q. エンド ユーザーにスパム検疫へのアクセスを許可するにはどのようにすればよいですか。**
  
A. エンドユーザーのスパム検疫にアクセスするには、エンドユーザーが有効な Office 365 ユーザー ID とパスワードを持っている必要があります。 社内メールボックスを保護している EOP のお客様は、ディレクトリ同期または EAC を使用して作成された有効な電子メールユーザーである必要があります。 ユーザーの管理の詳細については、EOP 管理者が[EOP でメールユーザーを管理](eop/manage-mail-users-in-eop.md)する」を参照してください。 EOP スタンドアロンのお客様の場合は、ディレクトリ同期を使用し、ディレクトリベースのエッジブロックを有効にすることをお勧めします。詳細については、「[ディレクトリベースのエッジブロックを使用して無効な受信者に送信されたメッセージを拒否する](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)」を参照してください。
  
 **Q. スパム以外のものを検疫に送信できますか?**
  
A. メールフロールール (トランスポートルールとも呼ばれる) に一致するメッセージを、管理者検疫に送信することもできます (構成済みのアクションの場合)。 エンドユーザー検疫は、スパムのみを対象としています。
  
 **Q. メッセージが検疫内に保存される期間はどのくらいですか。**
  
A. 既定では、スパム検疫メッセージは30日間検疫に保持され、メールフロールールと一致した検疫メッセージは7日間検疫に保持されます。 この期間が経過したら、メッセージは削除され、取得不能になります。 メールフロールールと一致した検疫済みメッセージの保持期間は構成できません。 ただし、スパム検疫メッセージの保持期間は、コンテンツ フィルター ポリシーの **[次の期間スパムを保持する (日)]** の設定によって短縮できます。 詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。
  
 **Q. 一度に複数の検疫メッセージを解放または報告できますか。**
  
A. EAC またはエンド ユーザー スパム検疫で一度に複数のメッセージを解放または報告する機能は現在利用できません。ただし、管理者はリモート Windows PowerShell スクリプトを作成してこのタスクを実行できます。メッセージを検索する場合は [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) コマンドレットを使用し、それらを解放する場合は [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) コマンドレットを使用します。 
  
 **Q. 隔離されたメッセージを検索する場合にワイルドカードはサポートされますか。特定のドメインの隔離されたメッセージを検索できますか。**
  
A. Exchange 管理センターで検索条件を指定する場合、ワイルドカードはサポートされません。たとえば、送信者を検索する場合には、完全な電子メール アドレスを指定する必要があります。
  
リモート Windows PowerShell を使用すれば、管理者は [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) コマンドレットで指定して、特定のドメイン (contoso.com など) の隔離されたメッセージを検索できます。 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

この結果は、[Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) コマンドレットに渡すことができます。メッセージをすべての受信者に解放するために、ReleaseToAll パラメーターを組み込みます。いったんメッセージが解放されると、再び解放することはできません。 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```


