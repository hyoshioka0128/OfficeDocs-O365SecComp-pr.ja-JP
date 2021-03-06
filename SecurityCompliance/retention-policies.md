---
title: アイテム保持ポリシーの概要
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: アイテム保持ポリシーでは、コンテンツを保持するか、コンテンツを削除するか、またはコンテンツを保持した後で削除するかを事前に決定できます。さらに、1 つのポリシーを組織全体に適用するか、特定の場所やユーザーにのみ適用するか、すべてのコンテンツにポリシーを適用するか、特定の条件を満たしているコンテンツにのみポリシーを適用するかも事前に決定できます。
ms.openlocfilehash: 87abb5bde49204a465e820afd522d6757a10e97c
ms.sourcegitcommit: a6f046f1529b0515f4f0e918a19ec83f4138b871
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2019
ms.locfileid: "35587116"
---
# <a name="overview-of-retention-policies"></a>アイテム保持ポリシーの概要

ほとんどの組織では、電子メール、ドキュメント、インスタント メッセージなどのデータの量と複雑さが日々増しています。この情報の効果的な管理が重要になる理由は、次の事項が必要になるためです。
  
- **業界の規制や内部ポリシーを遵守する**: このために、コンテンツは最小限の期間保持する必要があります。たとえば、米国企業改革法では、特定の種類のコンテンツを 7 年間保持するように定められています。 
    
- **訴訟やセキュリティ違反が発生した場合にリスクを軽減する**: このために、保持する必要がなくなった古いコンテンツは完全に削除します。 
    
- **組織内での効率的な知識の共有と迅速な対応に役立てる**: このために、ユーザーは現時点で関連性のあるコンテンツのみを対象に作業するようにします。 
    
アイテム保持ポリシーは、これらすべての目標の達成に役立ちます。一般に、コンテンツの管理に求められる操作は次の 2 つです。
  
- **コンテンツの保持**: 保持期間が満了するまではコンテンツの完全な削除ができないようにします。 
    
- **コンテンツの削除**: 保持期間の満了時点でコンテンツを完全に削除します。 
    
アイテム保持ポリシーにより、次のことが可能になります。
  
- コンテンツを保持するか、コンテンツを削除するか、コンテンツを保持した後に削除するかを事前に決定する。
    
- 1 つのポリシーを組織全体または特定の場所やユーザーにのみ適用する。
    
- すべてのコンテンツにポリシーを適用する。または、特定の条件を満たしているコンテンツ (たとえば、特定のキーワードや[特定の種類の機密情報](what-the-sensitive-information-types-look-for.md)を含むコンテンツ) にのみポリシーを適用する。
    
コンテンツがアイテム保持ポリシーの対象になったときに、そのコンテンツは所定の場所に維持されるため、ユーザーは何も変更されなかったかのように元の場所でコンテンツに対する編集や作業を続行できます。ただし、ポリシーの対象になっているコンテンツを編集または削除すると、コピーが安全な場所に保存され、ポリシーが有効な間はその場所で保持されます。
  
最後に、一部の組織は、米国証券取引委員会 (SEC) 規則 17a-4 のような規制に準拠する必要があります。この規則では、アイテム保持ポリシーをオンにした後で、そのポリシーをオフにすることや制限を緩和することが禁止されています。この要件を満たすために、保持ロックを使用できます。ポリシーがロックされていると、そのポリシーは誰も (管理者でも) オフにすることや制限を緩和することができなくなります。
  
アイテム保持ポリシーの作成と管理は、次の場所で実行します

- Microsoft 365 コンプライアンス センターの **[ポリシー]** ページ。
- Office 365 セキュリティ/コンプライアンス センターの **[データ ガバナンス]** にある **[保持]** ページ。
  
## <a name="how-a-retention-policy-works-with-content-in-place"></a>アイテム保持ポリシーは所定の場所にあるコンテンツに対してどのように作用するか

サイトやメールボックスなどの場所をアイテム保持ポリシーに含めたときにも、コンテンツは元の場所に引き続き保持されます。そのため、ユーザーは何事もなかったかのように、自分のドキュメントやメールに対する作業を継続できます。ただし、ポリシーに含まれるコンテンツを編集したり削除したりした場合、ポリシーを適用したときの状態でコンテンツのコピーが保持されます。
  
SharePoint サイト コレクションの場合、ユーザーがコンテンツを編集または削除すると、元のコンテンツのコピーが [アイテム保管ライブラリ] に保持されます。メールやパブリック フォルダーの場合、コピーは [回復可能なアイテム] フォルダーに保持されます。これらの安全な場所と保持されたコンテンツは、ほとんどのユーザーに表示されません。アイテム保持ポリシーでは、ユーザーは自分のコンテンツがポリシーの対象になっていることを知る必要もありません。
  
注: 
  
- Skype のコンテンツは Exchange に格納されます。ここでは、メッセージの種類 (メールまたは会話) に応じてポリシーが適用されます。
    
- Office 365 のグループに適用されるアイテム保持ポリシーには、グループのメールボックスとサイトが両方とも含まれます。
    
### <a name="content-in-onedrive-accounts-and-sharepoint-sites"></a>OneDrive アカウントと SharePoint サイトのコンテンツ

アイテム保持ポリシーは、サイト コレクション レベルで適用されます。アイテム保持ポリシーに SharePoint サイトや OneDrive アカウントを含めると、[アイテム保管ライブラリ] が作成されます (このライブラリが存在しない場合)。このライブラリは、サイト コレクションのトップレベル サイトの [**サイト コンテンツ**] に表示されます。[アイテム保管ライブラリ] はサイト コレクションの管理者のみに表示されるため、ほとんどのユーザーは参照できません。
  
ユーザーがアイテム保持ポリシーの対象になっているサイトのコンテンツを変更または削除しようとすると、ポリシーによって、まず、そのコンテンツがポリシーの適用以降に変更されているかどうかが確認されます。アイテム保持ポリシーが適用されてから初めての変更である場合は、ポリシーによって、そのコンテンツがアイテム保管ライブラリにコピーされます。その後で、ユーザーは元のコンテンツを変更または削除できるようになります。アイテム保持ポリシーで使用しているクエリとコンテンツが一致しない場合でも、サイト コレクションのあらゆるコンテンツがアイテム保管ライブラリにコピーされることがあります。
  
その次に、タイマー ジョブにより、アイテム保管ライブラリがクリーンアップされます。タイマー ジョブは定期的に実行され、アイテム保管ライブラリ内のすべてのコンテンツが、サイトのアイテム保持ポリシーで使用されているすべてのクエリと比較されます。コンテンツは、少なくとも 1 つのクエリと一致する場合を除いて、タイマー ジョブによってアイテム保持ライブラリから完全に削除されます。
  
これは、アイテム保持ポリシーが適用されたときに存在していたコンテンツに当てはまります。これに加えて、サイト コレクションがポリシーの対象になった後で作成または追加された新しいコンテンツは、削除後も保持されます。ただし、新しいコンテンツは、削除された場合にのみアイテム保管ライブラリにコピーされ、最初の編集時にはコピーされません。すべてのファイルのバージョンを保持するには、バージョン管理を有効にする必要があります。バージョン管理については、後述のセクションで説明します。
  
ユーザーがライブラリ、リスト、フォルダー、またはアイテム保持ポリシーの対象になっているサイトを削除しようとするとエラーが発生することに注意してください。ユーザーはフォルダーを削除できますが、最初にポリシーの対象になっているファイルをすべてフォルダーから移動または削除する必要があります。[アイテム保管ライブラリ] が作成されるのは、アイテム保持ポリシーが作成されたときではなく、このライブラリにコピーする必要がある最初のアイテムが出現したときであることに注意してください。そのため、ポリシーをテストするには、最初にポリシーの対象になっているサイトでドキュメントを編集または削除し、それから [アイテム保管ライブラリ] を参照して保持されたコピーの確認を行うようにします。
  
![SharePoint および OneDrive のコンテンツのライフサイクルの図](Retention_Diagram_of_retention_flow_in_sites.png)
  
OneDrive アカウントまたは SharePoint サイトにアイテム保持ポリシーが割り当てられていると、コンテンツは次の 2 つの経路のどちらかで処理されます。
  
1. 保持期間中、**コンテンツが変更または削除された場合**、元のコンテンツがアイテム保持ポリシーが割り当てられたときの状態でコピーされたものは、[アイテム保管ライブラリ] で作成されます。 ここで、タイマー ジョブが定期的に実行され、アイテム保持ポリシーの有効期間が過ぎたアイテムを特定します。このようなアイテムは、 第 2 段階の [ごみ箱] に移動され、移動から 93 日目に完全に削除されます。 第 2 段階のごみ箱はエンドユーザーには表示されないことに注意してください (第1 段階のごみ箱のみ表示)。サイトコレクション管理者はそこにあるコンテンツを表示および復元できます。

    > [!NOTE]
    > アイテム保管ライブラリからコンテンツを削除する方法が変更されました。 不注意によるデータの損失を防ぐために、アイテム保管ライブラリからコンテンツを完全に削除しないようになりました。 代わりに、ごみ箱のコンテンツのみを完全に削除するようになるため、保持アイテムライブラリのすべてのコンテンツは、第 2 段階のごみ箱を通過するようになります。
    
2. 保持期間中に**コンテンツが変更または削除されていない場合**。保持期間の満了日に、コンテンツは [第 1 段階のごみ箱] に移動されます。ユーザーが [第 1 段階のごみ箱] からコンテンツを削除した場合や、このごみ箱を空にした場合、ドキュメントは [第 2 段階のごみ箱] に移動されます。第 1 段階と第 2 段階の両方のごみ箱で保持期間は 93 日間です。93 日目に、ドキュメントは第 1 段階と第 2 段階のどちらにあっても完全に削除されます。[ごみ箱] にはインデックスが作成されないため、検索機能でコンテンツを見つけることができない点に注意してください。そのため、電子情報開示の保留リストでは、コンテンツの保留ために [ごみ箱] 内を検索できません。 
    
### <a name="content-in-mailboxes-and-public-folders"></a>メールボックス内およびパブリック フォルダー内にあるコンテンツ

ユーザーのメールや予定表などのアイテムには、メールボックス レベルでアイテム保持ポリシーが適用されます。パブリック フォルダーには、メールボックス レベルではなく、フォルダー レベルでアイテム保持ポリシーが適用されます。メールボックスとパブリック フォルダーの両方で、アイテム保持のために [回復可能なアイテム] フォルダーが使用されます。別のユーザーの [回復可能なアイテム] フォルダーに含まれるアイテムは、電子情報開示のアクセス許可が割り当てられているユーザーのみが閲覧できます。
  
既定では、ユーザーが [削除済みアイテム] フォルダー以外のフォルダー内のメッセージを削除すると、そのメッセージは [削除済みアイテム] フォルダーに移動されます。ユーザーが [削除済みアイテム] フォルダー内のアイテムを削除すると、そのメッセージは [回復可能なアイテム] フォルダーに移動されます。また、ユーザーは任意のフォルダー内のアイテムを論理的に削除できます (Shift キーと Delete キーを同時に押します)。この操作により、アイテムは [削除済みアイテム] フォルダーをバイパスして、[回復可能なアイテム] フォルダーに直接移動されます。
  
[回復可能なアイテム] フォルダー内のアイテムは、プロセスによって定期的に評価されます。どのアイテム保持ポリシーとも一致しないアイテムは、[回復可能なアイテム] フォルダーから完全に削除されます (この削除は物理的な削除とも呼ばれます)。
  
ユーザーがメールボックス アイテムの特定のプロパティ (件名、本文、添付ファイル、送信者と受信者、メッセージの送信日や受信日など) を変更しようとすると、変更の確定前に、元のアイテムのコピーが [回復可能なアイテム] フォルダーに保存されます。それ以降、この処理は変更があるたびに実行されます。[回復可能なアイテム] フォルダー内のコピーは、保持期間の満了日に完全に削除されます。
  
組織を退職するユーザーのメールボックスがアイテム保持ポリシーに含まれている場合は、そのユーザーの Office 365 アカウントが削除されたときに、メールボックスが非アクティブなメールボックスになります。非アクティブなメールボックスのコンテンツは、引き続きメールボックスが非アクティブになる前に実施されたアイテム保持ポリシーの適用対象であり、電子情報開示の検索に表示されます。詳細については、「[Exchange Online の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。
  
![メールおよびパブリック フォルダーの保持フローについての図](media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)
  
メールボックスまたはパブリック フォルダーにアイテム保持ポリシーが割り当てられていると、コンテンツは次の 2 つの経路のどちらかで処理されます。
  
1. 保持期間中に**ユーザーがアイテムを変更または完全に削除した場合**。ユーザーが Shift キーと Delete キーを同時に押すか、[削除済みアイテム] から削除を実行すると、アイテムは [回復可能なアイテム] フォルダーに移動されます (編集の場合はコピーされます)。ここでは、プロセスが定期的に実行され、アイテム保持ポリシーの有効期間を経過したアイテムが識別されます。これに該当するアイテムは、保持期間の満了日から 14 日以内に完全に削除されます。既定の設定は 14 日間ですが、最長 30 日間にまで変更できます。
    
2. 保持期間中に**アイテムが変更または削除されていない場合**。同じプロセスがメールボックス内のすべてのフォルダーに対して定期的に実行され、アイテム保持ポリシーの有効期間を経過したアイテムが識別されます。これに該当するアイテムは、保持期間の満了日から 14 日以内に完全に削除されます。既定の設定では 14 日間ですが、最長 30 日間にまで変更できます。 
    
## <a name="how-a-retention-policy-works-with-document-versions-in-a-site-collection"></a>アイテム保持ポリシーはサイト コレクションのドキュメントのバージョンにどのように作用するか

バージョン管理は、SharePoint Online と OneDrive for Business のすべてのドキュメント ライブラリの機能です。既定では、少なくとも 500 件のメジャー バージョンが保持されます (この制限は増やすことができます)。詳細については、「[リストまたはライブラリのバージョン管理を有効にして構成する](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37)」を参照してください。
  
アイテム保持ポリシーにより、SharePoint サイト コレクションまたは OneDrive アカウントのドキュメントのすべてのバージョンが保持されます。アイテム保持ポリシーの対象になっているドキュメントが編集または削除されるたびに、アイテム保管ライブラリにバージョンがコピーされます。アイテム保管ライブラリ内のドキュメントの各バージョンは、独自の保持期間が設定された個別のアイテムとして存在します。
  
- アイテム保持ポリシーがコンテンツの作成日時に基づいている場合、それぞれのバージョンには、元のドキュメントと同じ有効期限日が設定されます。元のドキュメントとそのバージョンは、すべて同時に期限が切れます。
    
- アイテム保持ポリシーがコンテンツの最終更新日時に基づいている場合、それぞれのバージョンには、そのバージョンを作成するために元のドキュメントを変更した日時に基づいた独自の有効期限日が設定されます。元のドキュメントとそのバージョンは、個別に期限が切れます。
    
## <a name="retaining-content-for-a-specific-period-of-time"></a>コンテンツを特定の期間保持する

アイテム保持ポリシーでは、コンテンツを無期限に保持することも、指定した日数、月数、または年数で保持することもできます。コンテンツの保持期間は、アイテム保持ポリシーの適用時点からではなく、コンテンツの経過時間で計算されます。コンテンツの経過時間は、コンテンツが作成された日時、または最後に更新された日時 (OneDrive や SharePoint の場合) のどちらかを基準に計算するように選択できます。
  
たとえば、サイト コレクションのコンテンツを最終変更日から 7 年間保持するとします。そのサイト コレクションのドキュメントが過去 6 年間変更されていない場合、そのドキュメントは、もう 1 年間のみ保持されます。そのドキュメントが再度編集された場合、ドキュメントの経過時間は新しい最終変更日から計算され、その時点から 7 年間保持されます。
  
同様に、メールボックスのコンテンツを 7 年間保持するとします。メッセージが 6 年前に送信されていた場合、そのメッセージは、もう 1 年間のみ保持されます。Exchange のコンテンツの経過時間は、常に、受信日または送信日に基づいて計算されます。最終更新日に基づいてコンテンツを保持するポリシーは、OneDrive および SharePoint のサイト コンテンツにのみ適用されます。
  
保持期間の満了日にコンテンツを完全に削除するかどうかは選択できます。アイテム保持ポリシーでは、古いコンテンツを保持しないで削除することもできます。次のセクションを参照してください。
  
![[アイテム保持設定] ページ](media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
## <a name="deleting-content-thats-older-than-a-specific-age"></a>特定の経過時間を超えた古いコンテンツを削除する

アイテム保持ポリシーでは、コンテンツを保持してから削除することも、古いコンテンツを保持しないで削除することもできます。
  
アイテム保持ポリシーによってコンテンツを削除する場合、アイテム保持ポリシーに指定した期間は、ポリシーが割り当てられた時点からではなく、コンテンツが作成または変更された時点から計算されることを理解しておくことが重要です。
  
![[削除の設定]](media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
たとえば、3 年間経過後のコンテンツを削除するアイテム保持ポリシーを作成して、そのポリシーをすべての OneDrive アカウントに割り当てるとします。また、該当するアカウントには 4 年から 5 年前に作成されたコンテンツが数多く含まれているとします。この場合、そのアイテム保持ポリシーを初めて割り当てたときに、多数のコンテンツがすぐに削除されます。こうした理由から、**コンテンツを削除するアイテム保持ポリシーは、コンテンツに大きな影響を与えることになります**。 
  
そのため、サイト コレクションに初めてポリシーを割り当てるときには、その前に、既存のコンテンツの経過時間と、そのコンテンツにポリシーが及ぼす影響について考慮する必要があります。また、新しいポリシーを割り当てる前に、サイト所有者に連絡して、発生する可能性のある影響について評価するための時間を与えるようにしてください。アイテム保持ポリシーの作成前に設定を確認すると、この警告が表示されます。
  
![コンテンツの削除に関する警告](media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-that-apply-a-policy-only-to-content-that-meets-certain-conditions"></a>特定の条件を満たすコンテンツにのみポリシーを適用するための高度な設定

アイテム保持ポリシーは、その場所に含まれるすべてのコンテンツに適用することも、特定のキーワードや[特定の種類の機密情報](what-the-sensitive-information-types-look-for.md)を含むコンテンツにのみ適用するように選択することもできます。
  
![高度なアイテム保持のオプション](media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="retain-content-that-contains-specific-keywords"></a>特定のキーワードを含むコンテンツを保持する

特定の条件を満たすコンテンツにのみアイテム保持ポリシーを適用して、そのコンテンツのみを保持できます。現時点で利用可能な条件では、特定の単語や語句を含むコンテンツにアイテム保持ポリシーを適用することがサポートされています。AND、OR、NOT などの検索演算子を使用すると、クエリの範囲を絞り込むことができます。これらの演算子の詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。
  
検索可能なプロパティ (**件名:** など) の追加については間もなくサポートされます。
  
クエリ ベースのアイテム保持では、コンテンツの識別に検索インデックスが使用される点に注意してください。
  
![クエリ エディター](media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="retain-content-that-contains-sensitive-information"></a>機密情報が含まれているコンテンツを保持する

アイテム保持ポリシーは、[特定の種類の機密情報](what-the-sensitive-information-types-look-for.md)が含まれているコンテンツにのみ適用できます。たとえば、納税者番号、社会保障番号、パスポート番号などの個人を特定できる情報 (PII) が含まれているコンテンツにのみ固有の保持要件を適用することができます。
  
![機密情報の種類のページ](media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
注:
  
- 機密情報に対応する高度な保持は、Exchange のパブリック フォルダーや Skype for Business には適用されません (これらの場所が機密情報の種類をサポートしていないため)。
    
- Exchange Online では、機密情報の識別にメール フロー ルール (トランスポート ルールとも呼ばれる) が使用されていることを理解している必要があります。このルールは、転送中のメッセージには有効ですが、既にメールボックスに保存されているアイテムには作用しません。つまり、Exchange Online の場合、アイテム保持ポリシーでは、そのポリシーがメールボックスに適用された**後**に受信したメッセージに対してのみ機密情報の識別と保持が可能になります (前のセクションで説明したクエリ ベースの保持では、コンテンツを識別する際に検索インデックスが使用されるため、このような制限はありません)。 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a>アイテム保持ポリシーを組織全体または特定の場所に適用する

アイテム保持ポリシーは、組織全体、場所全体、または特定の場所やユーザーのみに簡単に適用できます。
  
### <a name="org-wide-policy"></a>組織全体のポリシー

アイテム保持ポリシーの強力な機能の 1 つとして、既定ではポリシーが Office 365 全体の場所に適用されます。これには、次の場所が含まれます。
  
- Exchange 電子メール
    
- SharePoint サイト コレクション
    
- OneDrive アカウント
    
- Office 365 のグループ (グループのメールボックスとサイトのコンテンツ、およびドキュメントに適用されます。Planner、Yammer、および CRM のコンテンツについては間もなくサポートされます)。
    
- Exchange パブリック フォルダー
    
![すべての場所のオプション](media/c343bd8e-42ac-4f17-a338-36f3c9598a86.png)
  
その他の組織全体のアイテム保持ポリシーに関する重要な機能は、次のとおりです。
  
- ポリシーに含めることができるメールボックスまたはサイトの数に制限はありません。
    
- Exchange の場合、ポリシーの適用後に作成された新しいメールボックスには、そのポリシーが自動的に継承されます。
  
### <a name="a-policy-that-applies-to-entire-locations"></a>場所全体に適用されるポリシー

場所を選択するときには、Exchange 電子メールや OneDrive アカウントなどの場所全体を簡単に含めたり除外したりできます。この操作は、該当する場所の **[状態]** をオンまたはオフに切り替えるだけです。 
  
組織全体のポリシーと同様に、場所全体の任意の組み合わせにポリシーを適用する場合は、ポリシーに含めることができるメールボックスまたはサイトの数に制限はありません。たとえば、ポリシーにすべての Exchange 電子メールとすべての SharePoint サイトを含めると、数に関係なくすべてのサイトとメールボックスが含まれるようになります。また、Exchange の場合、ポリシーの適用後に作成された新しいメールボックスには、そのポリシーが自動的に継承されます。
 
![[場所の選択] ページ](media/6ac0c2d6-1abf-4690-b3f6-9ca506887ba3.png)
  
### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>特定の追加または除外を含むポリシー

アイテム保持ポリシーは、特定のユーザーに適用することもできます。そのためには、目的の場所の **[状態]** をオンに切り替えてから、リンクを使用して特定のユーザー、Office 365 グループ、または場所を含めたり除外したりします。 
  
ただし、1,000 人を超える特定ユーザーを含めたり除外したりするアイテム保持ポリシーには、次の制限があります。
  
- これに該当する保持ポリシーに含めることができるメールボックスは 1,000 個以下、サイト コレクションは 100 個以下です。
    
- 1 つのテナントに含めることができる、アイテム保持ポリシーは 10,000 個以下です。
    
こうした制限はありますが、組織全体のポリシーまたは場所全体に適用されるポリシーを適用することで、この制限を取り除くことができます。
  
### <a name="skype-locations"></a>Skype の場所

Exchange 電子メールとは異なり、Skype の場所の状態を切り替えるだけでは、すべてのユーザーを含めることができません。ただし、その場所をオンにしてから、会話を保持するユーザーを手動で選択することはできます。
  
Skype for Business のユーザーを選択するときには、列のヘッダーの **[名前]** ボックスを選択すると、簡単にすべてのユーザーを含めることができます。ただし、それぞれのユーザーが、このポリシーに個別に含まれるものとしてカウントされる点に注意してください。そのため、1,000 人以上のユーザーを含めると、前のセクションで説明した制限が適用されるようになります。すべての Skype ユーザーをここで選択することは、組織全体のポリシーに既定ですべての Skype ユーザーが含まれることと同じではありません。 
  
![Skype ユーザーの選択ページ](media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
Outlook のフォルダー **[会話履歴]** は、Skype のアーカイブには作用しない機能です。**[会話履歴]** はエンド ユーザーが無効にできますが、Skype のアーカイブの場合はユーザーがアクセスできない (電子情報開示には使用できる) 非表示フォルダーに Skype の会話のコピーが保存されます。

### <a name="office-365-groups-locations"></a>Office 365 グループの場所

Office 365 グループのコンテンツを保持するには、Office 365 グループの場所を使用する必要があります。Office 365 グループには Exchange メールボックスがありますが、Exchange の場所全体が含まれるアイテム保持ポリシーには、Office 365 グループのメールボックスのコンテンツは含まれません。Office 365 グループに適用されるアイテム保持ポリシーには、グループのメールボックスとサイトが両方とも含まれます。

また、Exchange の場所を使用して、特定のグループのメールボックスを含めたり除外したりすることはできません。最初は Exchange の場所でグループのメールボックスを選択できますが、アイテム保持ポリシーを保存しようとすると、Exchange の場所では "RemoteGroupMailbox" を選択できないことを示すエラーを受け取ります。 
  
### <a name="teams-locations"></a>Teams の場所

アイテム保持ポリシーは、Teams のチャットとチャネル メッセージの保持に使用できます。Teams のチャットは、チャットに参加していた各ユーザーのメールボックス内の隠しフォルダーに保存されます。また、Teams のチャネル メッセージは、チーム用のグループ メールボックス内の同様の隠しフォルダーに保存されます。ただし、Teams は Azure が提供するチャット サービスを使用し、そのサービスでも、このデータが保存されることを理解しておくことが重要です。また、このサービスは、既定でデータを無期限に保存します。このため、Teams のデータの保持および削除する場合は、Teams の場所を使用することを強くお勧めします。Teams の場所を使用すると、Exchange メールボックスと基になる Azure が提供するチャット サービスの両方から完全にデータが削除されます。詳細については、「[Microsoft Teams のセキュリティとコンプライアンスの概要](https://go.microsoft.com/fwlink/?linkid=871258)」を参照してください。
  
Teams のチャットとチャネル メッセージは、Exchange または Office 365 グループの場所にあるユーザーまたはグループのメールボックスに適用されているアイテム保持ポリシーの影響を受けない点に注意してください。Teams のチャットとチャネル メッセージは Exchange に保存されていても、Teams の場所に適用されるアイテム保持ポリシーのみの影響を受けます。
  
Microsoft では、Teams のアイテム保持に関する作業を継続していて、近日中に追加機能が公開される予定です。それまでの間は、注意が必要な制限がいくつかあります。
  
- **Teams には個別のアイテム保持ポリシーが必要**: アイテム保持ポリシーを作成して、Teams の場所をオンに切り替えると、その他のすべての場所がオフに切り替わります。Teams を含むアイテム保持ポリシーには、Teams のみを含めることが可能です (その他の場所は含めることができません)。 
    
- **Teams は組織全体のポリシーには含まれない**: 組織全体のポリシーを作成する場合、Teams は含まれません。Teams には個別のアイテム保持ポリシーが必要になるためです。 
    
- **Teams は高度なアイテム保持をサポートしていない**: アイテム保持ポリシーを作成するときに、[特定の条件を満たすコンテンツにのみポリシーを適用する高度な設定](#advanced-settings-that-apply-a-policy-only-to-content-that-meets-certain-conditions)を選択すると、Teams の場所は利用できなくなります。現時点では、Teams のアイテム保持はすべてのチャットおよびチャネル メッセージのコンテンツに適用されます。
    
- **Teams コンテンツは削除されるまでに少なくとも 30 日間かかる**: 現時点では、経過時間が 30 日未満の Teams コンテンツを削除するポリシーの作成はサポートされていません。このポリシーを Teams コンテンツに適用する必要がある場合は、30 日以上のアイテム保持期間を指定します。 
    
- **Teams では保持されたコンテンツをクリーンアップするまでに最大 30 日間かかる可能性がある**: Teams に適用されているアイテム保持ポリシーでは、すべての関連するストレージの場所からコンテンツが削除されます。ただし、Teams クライアントが、アイテム保持ポリシーを基にコンテンツをクリーンアップするまでに、起動直後から最大 30 日間かかる可能性があります。コンテンツが Teams クライアントに引き続き表示される場合であっても、そのコンテンツはアイテム保持期間の終了後にコンテンツの検索や電子情報開示には表示されなくなります。 
    
チームでは、チャットで共有されるファイルが、ファイルを共有したユーザーの OneDrive アカウントに保存されます。チャネルにアップロードされたファイルは、チームの SharePoint 内に保存されます。そのため、チーム内のファイルを保持または削除するには、SharePoint の場所と OneDrive の場所に適用されるアイテム保持ポリシーを作成する必要があります。特定のチームのみのファイルにポリシーを適用する場合は、チーム用の SharePoint サイトおよびチーム内のユーザーの OneDrive アカウントを選択できます。
  
Teams に適用するアイテム保持ポリシーには、[保持ロック](#locking-a-retention-policy)を使用できます。
  
![チャットおよびチャネル メッセージに対応する Teams の場所](media/127345da-e802-4b3a-afc7-6e354dc3f409.png)
  
## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a>アイテム保持ポリシーから特定の種類の Exchange アイテムを除外する
PowerShell を使用すると、アイテム保持ポリシーから特定の種類の Exchange アイテムを除外できます。たとえば、メールボックス内のボイスメール メッセージや IM 会話などの Skype for Business Online のコンテンツを除外できます。さらに、予定表、メモ、タスク アイテムを除外することもできます。この機能は、PowerShell を使用してのみ利用できます。アイテム保持ポリシーを作成するときの UI では、この機能を利用できません。
  
この操作を行うには、`New-RetentionComplianceRule` および `Set-RetentionComplianceRule` コマンドレットの `ExcludedItemClasses` パラメーターを使用します。PowerShell の詳細については、後述のセクション「[アイテム保持ポリシーの PowerShell コマンドレットを検索する](#find-the-powershell-cmdlets-for-retention-policies)」を参照してください。


## <a name="locking-a-retention-policy"></a>アイテム保持ポリシーをロックする
一部の組織は、米国証券取引委員会 (SEC) 規則 17a-4 のような規制機関によって定義された規則に準拠する必要があります。その規則には、アイテム保持ポリシーをオンにした後で、そのポリシーをオフにすることや、制限を緩和したりすることが禁止されています。保持ロックを使用すると、管理者を含めて誰もポリシーをオフにしたり、制限を緩和したりできなくなるようにポリシーをロックできます。
  
ポリシーがロックされると、そのポリシーは誰もオフにしたり、無効にしたりできなくなります。また、ポリシーが適用されているコンテンツを保持期間中に変更したり削除したりすることもできません。ポリシーがロックされると、アイテム保持ポリシーには、場所を追加する変更または保持期間を延長する変更のみが可能になります。ロックされたポリシーは増強することができますが、縮小したりオフにしたりすることはできません。
  
そのため、アイテム保持ポリシーをロックする前に、組織のコンプライアンス要件を理解しておくことと、ポリシーのロックが必要であると確信するまでは**ポリシーをロックしない**ことが**非常に重要**になります。

### <a name="lock-a-retention-policy-by-using-powershell"></a>PowerShell を使用してアイテム保持ポリシーをロックする
  
アイテム保持ポリシーは、PowerShell を使用してのみロックできます。

まず、[Office 365 セキュリティ/コンプライアンス センター PowerShell へ接続します](http://go.microsoft.com/fwlink/p/?LinkID=799771)。

次に、アイテム保持ポリシーの一覧を表示し、ロックするポリシーの名前を検索し、`Get-RetentionCompliancePolicy` を実行します。

![PowerShell のアイテム保持ポリシーの一覧](media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3 番目に、アイテム保持ポリシーの保持ロックを配置するために、`Set-RetentionCompliancePolicy` を実行し、`RestrictiveRetention` パラメーターを true に設定します。たとえば、

`Set-RetentionCompliancePolicy -Identity “<Name of Policy>” – RestrictiveRetention $true`

![PowerShell の RestrictiveRetention パラメーター](media/retention-policy-preservation-lock-restrictiveretention.PNG)

そのコマンドレットを実行すると、確認メッセージが表示されます。**[すべてにはい]** を選択します。

![PowerShell のアイテム保持ポリシーをロックするかを確認するダイアログ](media/retention-policy-preservation-lock-confirmation-prompt.PNG)

アイテム保持ポリシーの保持ロックをが配置されました。`Get-RetentionCompliancePolicy` を実行すると、`RestrictiveRetention` パラメーターは true に設定されます。たとえば、

`Get-RetentionCompliancePolicy -Identity “<Name of Policy>” |Fl`

![PowerShell に表示されるすべてのパラメーターでロックされたポリシー](media/retention-policy-preservation-lock-locked-policy.PNG)
  
## <a name="releasing-a-retention-policy"></a>アイテム保持ポリシーを解除する

アイテム保持ポリシーはいつでもオフまたは削除できます。 この操作を行うと、保持されている SharePoint や OneDrive のコンテンツは、すぐには完全に削除されません。 代わりに、不注意によるデータの損失を防ぐために、30日間の猶予期間があります。そのポリシーのコンテンツの有効期限は、[アイテム保管ライブラリ] には表示されず、必要に応じてコンテンツを復元できます。 猶予期間中はアイテム保持ポリシーをもう一度有効にすることもできます。そのポリシーのコンテンツは削除されません。 PowerShell を使用して、猶予期間の設定は変更できます。

まず、[Office 365 セキュリティ/コンプライアンス センター PowerShell へ接続](http://go.microsoft.com/fwlink/p/?LinkID=799771) します。

その後、PowerShell スクリプトを実行します。 テナントのサブスクリプション設定で、0 から 100 日までの間で`ip_tenantGracePeriodInDays` プロパティを設定できます。 これを 0 に設定すると、猶予期間はありません。アイテム保持ポリシーは直ちに解除されます。 

`
$siteSubscription = Get-SPSiteSubscription -Identity 
$siteSubScriptionId 
$siteSubSettingsMgr = [Microsoft.SharePoint.SPSiteSubscriptionSettingsManager]::Local
$properties = $siteSubSettingsMgr.GetProperties($siteSubscription)
$properties.SetValue("ip_tenantGracePeriodInDays",  30)
`

この SharePoint と OneDrive の 30 日の猶予期間は、Exchange の 30 日の保留期間に対応しています。 詳しくは、[メールボックスの管理についての詳細](https://docs.microsoft.com/ja-JP/office365/securitycompliance/identify-a-hold-on-an-exchange-online-mailbox#managing-mailboxes-on-delay-hold) をご覧ください。。

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>保持の原則、すなわち優先順位について

コンテンツには複数のアイテム保持ポリシーが適用され、各ポリシーに異なるアクション (保持または削除、あるいはその両方) と保持期間が設定されている場合が多くあります。どれが優先されるのでしょうか? 概ね、あるポリシーで保持されているコンテンツを別のポリシーで完全に削除することはできないので、ご安心ください。
  
![保持の原則の図](media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
さまざまなアイテム保持ポリシーが、どのようにコンテンツに適用されるかを理解するために、次に示す保持の原則を覚えておいてください。
  
1. **保持は削除よりも優先されます。** たとえば、Exchange 電子メールを 3 年後に削除するアイテム保持ポリシーと、Exchange 電子メールを 5 年間保持した後に削除するアイテム保持ポリシーがあるとします。この場合、3 年を経過したコンテンツはすべて削除されてユーザーには表示されなくなりますが、[回復可能なアイテム] フォルダーに保持され、5 年経過したときに完全に削除されます。 
    
2. **最長の保持期間が優先されます。** コンテンツを保持する複数のポリシーの対象となるコンテンツは、最長の保持期間が終了するまで保持されます。 
    
3. **明示的な包含は暗黙的な包含に優先します。** これは次を意味します。 
    
    1. 保持設定を持つラベルをユーザーが Exchange メールや OneDrive ドキュメントなどのアイテムに手動で割り当てると、そのラベルはサイト レベルまたはメールボックス レベルで割り当てられたポリシー、およびドキュメント ライブラリによって割り当てられた既定のラベルよりも優先されます。たとえば、明示的なラベルで 10 年間保持するように設定されているときに、サイトに割り当てられたポリシーでは 5 年間のみ保持するように設定されている場合は、ラベルが優先されます。自動適用ラベルは、Office 365 によって自動的に適用されるため、明示的ではなく暗黙的に指定されます。
    
    2. アイテム保持ポリシーに特定のユーザーのメールボックスまたは OneDrive for Business のアカウントなどの特定の場所が含まれている場合、そのポリシーは、すべてのユーザーのメールボックスまたは OneDrive for Business のアカウントに適用されるが、そのユーザーのメールボックスを特に含まない別の保持ポリシーよりも優先されます。
    
4. **最短の削除期間が優先されます。** 同様に、コンテンツを削除する複数のポリシー (保持なし) の対象となるコンテンツは、最短保持期間の終了時に削除されます。 
    
保持の原則は上位から下位のタイブレーク フローとして機能することを理解します。すべてのポリシーまたはラベルによって適用された複数のルールがあるレベルで同じ場合、フローは次の下位レベルに移動し、ルールが適用される優先順位を決定します。
  
最後に、アイテム保持ポリシーまたはラベルでは、電子情報開示のために保留中のコンテンツを完全に削除することはできません。保留が解除されると、コンテンツは再び上記に記載されたクリーンアップ プロセスの対象となります。
  
## <a name="use-a-retention-policy-instead-of-these-features"></a>別の機能の代わりにアイテム保持ポリシーを使用する

1 つのアイテム保持ポリシーは、組織全体や Office 365 のすべての場所 (Exchange Online、SharePoint Online、OneDrive for Business、Office 365 グループなど) に簡単に適用できます。Office 365 のいずれかの場所にあるコンテンツを保持または削除する必要がある場合は、アイテム保持ポリシーの使用をお勧めします (保持設定付きのラベルを使用することもできます。詳細については、「[ラベルの概要](labels.md)」を参照してください)。
  
Office 365 のコンテンツを保持または削除するために以前使用されていた別の機能がいくつかあります。 その一覧を次に示します。 これらの機能は、保持ポリシーおよび保持ラベルと共存して引き続き機能します。 ただし、データ ガバナンスについては、今後、これらの機能ではなく、アイテム保持ポリシーまたはラベルの使用をお勧めします。 アイテム保持ポリシーのみ、Office 365 全体でコンテンツの保持と削除の両方を行えます。
  
### <a name="exchange-online"></a>Exchange Online

- [Office 365 のセキュリティ センター/コンプライアンス センターでの電子情報開示のケースの管理](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) (電子情報開示の保留リスト) 
    
- [インプレース ホールドと訴訟ホールド](https://go.microsoft.com/fwlink/?linkid=846124) (電子情報開示の保留リスト) 
    
- [保持タグおよびアイテム保持ポリシー](https://go.microsoft.com/fwlink/?linkid=846125)。[メッセージング レコード管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) とも呼ばれます (削除のみ) 
    
### <a name="sharepoint-online-and-onedrive-for-business"></a>Sharepoint Online と OneDrive for Business

- [Office 365 のセキュリティ センター/コンプライアンス センターでの電子情報開示のケースの管理](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) (電子情報開示の保留リスト) 
    
- [電子情報開示センターでのコンテンツのケースへの追加とソースの保留リストへの配置](https://support.office.com/article/54d70de9-1ec2-4325-84f3-aeb588554479) (電子情報開示の保留リスト) 
    
- [ドキュメント削除ポリシーの概要](https://support.office.com/article/55e8d858-f278-482b-a198-2e62d6a2e6e5) (削除のみ) 
    
- [インプレース レコード管理の構成](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (保持) 
    
- [サイトのクローズと削除のポリシーを使用する](https://support.office.com/article/a8280d82-27fd-48c5-9adf-8a5431208ba5) (削除のみ) 
    
- [情報管理ポリシー](intro-to-info-mgmt-policies.md) (削除のみ) 
    
これまでにデータ ガバナンスの目的で電子情報開示の保留のいずれかを使用していた場合は、将来に向けて法令を遵守するためにアイテム保持ポリシーを使用する必要があります。 保留は電子情報開示にのみ使用するようにしてください。
  
### <a name="retention-policies-override-information-management-policies"></a>アイテム保護ポリシーによる情報管理ポリシーの上書き

SharePoint のサイトでは、[情報管理ポリシー](intro-to-info-mgmt-policies.md)を使用してコンテンツを保持している場合があります。 リストまたはライブラリに対してコンテンツ タイプ ポリシーまたは情報管理ポリシーを既に使用しているサイトに、保持ポリシーを適用すると、前者のポリシーは無視され、保持ポリシーが有効になります。 
  
## <a name="what-happened-to-preservation-policies"></a>保持ポリシーの変更点

保持ポリシーを使用していた場合、そのポリシーは自動的にアイテム保持ポリシーに変換されます。このポリシーは保持操作にのみ使用され、コンテンツを削除することはありません。 保持ポリシーは、引き続き機能してコンテンツを保持します。ユーザーが変更を加える必要はありません。 こうしたポリシーは、Microsoft 365 コンプライアンス センターの **[ポリシー]** ページか、セキュリティ/コンプライアンス センターの **[データ ガバナンス]** にある **[保持]** ページで検索できます。 保持ポリシーを編集して保持期間を変更することはできますが、それ以外の変更 (場所の追加や削除など) はできません。 
  
## <a name="permissions"></a>アクセス許可

アイテム保持ポリシーを作成するコンプライアンス チームのメンバーには、セキュリティ/コンプライアンス センターへのアクセス許可が必要です。既定では、テナント管理者はこの場所へのアクセス許可を持っています。そのため、法令遵守責任者や他のユーザーに対し、テナント管理者のすべてのアクセス許可を付与せずに、セキュリティ/コンプライアンス センターへのアクセスを許可できます。これを行うには、セキュリティ/コンプライアンス センターの **[アクセス許可]** ページに移動して、**[コンプライアンス管理者]** 役割グループを編集し、メンバーをその役割グループに追加することをお勧めします。 
  
詳細については、「[ユーザーに Office 365 セキュリティ センター/コンプライアンス センターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)」を参照してください。
  
これらのアクセス許可は、アイテム保持ポリシーを作成して適用するためにのみ必要です。ポリシーを適用するために、コンテンツへのアクセスは必要ありません。
  
## <a name="find-the-powershell-cmdlets-for-retention-policies"></a>アイテム保持ポリシーの PowerShell コマンドレットを検索する

アイテム保持ポリシーのコマンドレットを使用するには、次の操作を行う必要があります。
  
1. [リモート PowerShell を使用して Office 365 セキュリティ/コンプライアンス センターに接続する](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. [Office 365 セキュリティ/コンプライアンス センターのコマンドレット](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)を使用する
    
## <a name="more-information"></a>詳細情報

- [ラベルの概要](labels.md)
    

