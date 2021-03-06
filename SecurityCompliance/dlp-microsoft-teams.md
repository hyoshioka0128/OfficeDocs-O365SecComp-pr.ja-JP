---
title: データ損失防止と Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 07/01/2019
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: これで、DLP ポリシーを Microsoft Teams のチャットおよびチャネルに適用できるようになります。 機能の詳細については、この記事を参照してください。
ms.openlocfilehash: 3792fd6919749510ea20d4ff84b0249b16165a9f
ms.sourcegitcommit: cc1b0281fa594cbb7c09f3e419df21aec9557831
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35417399"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>データ損失防止と Microsoft Teams

> [!NOTE]
> データ損失防止機能は、最近、Office 365 E5 および Office 365 Advanced コンプライアンスの Microsoft Teams に追加されました。 機能の可用性の詳細については、「 [office 365 Service の説明: office 365 Security & コンプライアンスセンター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)」を参照してください。

## <a name="overview-of-dlp-for-microsoft-teams"></a>Microsoft Teams の DLP の概要

最近では、Microsoft Teams を含むように[データ損失防止](data-loss-prevention-policies.md)(DLP) 機能が拡張されています。 組織に DLP がある場合は、Microsoft Teams チャネルまたはチャットセッションで機密情報を共有できないようにするポリシーを定義できるようになりました。 この保護がどのように機能するかについて、いくつかの例を示します。

- **例 1: メッセージ内の機密情報を保護**します。 チームのチャットまたはチャネル内の機密情報をゲスト (外部ユーザー) と共有しようとするユーザーがいるとします。 これを防止するように定義された DLP ポリシーがある場合、外部ユーザーに送信される機密情報を含むメッセージは削除されます。 これは、DLP ポリシーがどのように構成されているかに応じて、数秒で自動的に発生します。

    > [!NOTE]
    > Microsoft Teams の DLP は、チームとチャネルで[ゲストアクセス](https://docs.microsoft.com/MicrosoftTeams/guest-access)権を持ち、会議やチャットセッションで[外部アクセス](https://docs.microsoft.com/MicrosoftTeams/manage-external-access)権を持つユーザーと共有している場合に機密コンテンツをブロックします。 [Skype For business と共に Microsoft teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)を使用している場合は、TEAMS の DLP が相互運用またはフェデレーションチャットセッションでのメッセージをブロックしないことに注意してください。

- **例 2: ドキュメント内の機密情報を保護**します。 Microsoft Teams チャネルまたはチャットのゲストでドキュメントを共有しようとした場合に、ドキュメントに機密情報が含まれているとします。 これを防止するように定義された DLP ポリシーがある場合、ドキュメントはそれらのユーザーに対して開くことができません。 この場合、DLP ポリシーには、保護を設定するために SharePoint と OneDrive を含める必要があることに注意してください。 (これは、Microsoft Teams に表示される SharePoint の DLP の例です。)

## <a name="policy-tips-help-educate-users"></a>ユーザーを教育するためのポリシーヒント

[Exchange、outlook、および outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)、 [SharePoint および OneDrive for business サイト](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)、および[OFFICE デスクトップクライアント](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)での dlp の動作と同様に、アクションが dlp ポリシーと競合すると、ポリシーヒントが表示されます。 ポリシーヒントの例を次に示します。

![Teams でブロックされたメッセージ通知](media/dlp-teams-blockedmessage-notification.png)

この場合、送信者は Microsoft Teams チャネルでソーシャルセキュリティ番号を共有しようとしました。 [**何を行いますか?** ] リンクは、問題を解決するために送信者に対してオプションを提供するダイアログボックスを開きます。 この場合、送信者はポリシーを上書きするか、管理者に通知してそれを確認して解決するかを選択することに注意してください。

![ブロックされたメッセージを解決するためのオプション](media/dlp-teams-blockedmessage-possibleactions.png)

組織では、ユーザーが DLP ポリシーを上書きすることを許可するかどうかを選択できます。 また、DLP ポリシーを構成するときは、既定のポリシーヒントを使用するか、組織の[ポリシーヒントをカスタマイズ](#to-customize-policy-tips)できます。 

この例では、送信者が Teams チャネルで社会保障番号を共有している場合、受信者は次のように表示されています。

![ブロックされたメッセージ](media/dlp-teams-blockedmessage-notification-to-user.png)

[**ポップヒント]** リンクによって、メッセージがブロックされた理由を説明する DLP ポリシーに関する[記事](data-loss-prevention-policies.md)が開きます。

### <a name="to-customize-policy-tips"></a>ポリシーヒントをカスタマイズするには

このタスクを実行するには、DLP ポリシーを編集する権限を持つ役割が割り当てられている必要があります。 詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

1. Office 365 セキュリティ & コンプライアンスセンター ([https://protection.office.com](https://protection.office.com)) に移動し、サインインします。

2. [**データ損失防止** > **ポリシー**] を選択します。 

3. ポリシーを選択し、[**ポリシー設定**] の横にある [**編集**] を選択します。

4. 新しいルールを作成するか、ポリシーの既存のルールを編集します。<br/>![ポリシーのルールを編集する](media/dlp-teams-editrule.png)<br/>

5. [**ユーザー通知**] タブで、[**電子メールテキストのカスタマイズ**] または [**ポリシーヒントテキストオプションのカスタマイズ**] を選択します。<br/>![ユーザー通知とポリシーヒントをカスタマイズする](media/dlp-teams-editrule-usernotifications.png)<br/>  

6. 電子メール通知やポリシーヒントに使用するテキストを指定し、[**保存**] を選択します。 

7. [**ポリシー設定**] タブで、[**保存**] を選択します。

変更がデータセンターを経由して、ユーザーアカウントに同期されるまで約1時間の時間を確保します。
 
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>既存の DLP ポリシーに Microsoft Teams を場所として追加する

このタスクを実行するには、DLP ポリシーを編集する権限を持つ役割が割り当てられている必要があります。 詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

1. Office 365 セキュリティ & コンプライアンスセンター ([https://protection.office.com](https://protection.office.com)) に移動し、サインインします。

2. [**データ損失防止** > **ポリシー**] を選択します。 

3. ポリシーを選択し、[**場所**] で値を確認します。 **Teams のチャットおよびチャネルメッセージ**が表示される場合は、すべて設定されています。 表示しない場合は、[**編集**] をクリックします。<br/>![既存のポリシーの場所](media/dlp-teams-editexistingpolicy.png)<br/>

4. [**状態**] 列で、 **Teams のチャットおよびチャネルメッセージ**のポリシーをオンにします。<br/>![Teams のチャットおよびチャネルの DLP](media/dlp-teams-addteamschatschannels.png)<br/>

5. すべてのアカウントの既定の設定をそのまま使用するか、または含めるアカウントまたは除外するアカウントを指定します。

6. **[保存]** をクリックします。

変更がデータセンターを経由して、ユーザーアカウントに同期されるまで約1時間の時間を確保します。

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Microsoft Teams の新しい DLP ポリシーを定義する

このタスクを実行するには、DLP ポリシーを編集する権限を持つ役割が割り当てられている必要があります。 詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

1. Office 365 セキュリティ & コンプライアンスセンター ([https://protection.office.com](https://protection.office.com)) に移動し、サインインします。

2. [**データ損失防止** > **ポリシー** > ] を選択して **、ポリシーを作成**します。 

3. [テンプレート](data-loss-prevention-policies.md#dlp-policy-templates)を選択し、[**次へ**] を選択します。<br/>この例では、米国の個人を特定できる情報データテンプレートを選択しました。<br/>![DLP ポリシーのプライバシーテンプレート](media/dlp-teams-createnewpolicy-template.png)<br/>

4. [**ポリシーに名前**をつける] タブで、ポリシーの名前と説明を指定し、[**次へ**] を選択します。 

5. [**場所の選択**] タブで、すべての場所の既定の設定をそのまま使用するか、[特定の**場所を選択**する] を選択して、[**次へ**] を選択します。<br/>特定の場所を選択する場合は、DLP ポリシーの場所を選択し、[**次へ**] を選択します。<br/>![DLP ポリシーの場所](media/dlp-teams-selectlocationsnewpolicy.png)<br/>
    > [!NOTE]
    > 機密情報が含まれるドキュメントが不適切に共有されないようにするには、 **SharePoint サイト**と**OneDrive アカウント**が、 **Teams のチャットおよびチャネルメッセージ**と共にオンになっていることを確認してください。
<br/>

6. [**ポリシー設定**] タブの [**保護するコンテンツの種類をカスタマイズ**する] で、既定の簡易設定をそのまま使用するか、[**詳細設定**] を選択して [**次へ**] を選択します。 [詳細設定] を選択した場合は、ポリシーのルールを作成または編集することができます。 (詳細については、「 [Simple settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)」と「advanced settings」を参照してください)。

7.  [**ポリシー設定**] タブの [**機密情報が検出された場合に実行**する操作] で、設定を確認します。 (既定の[ポリシーヒントと電子メール通知](use-notifications-and-policy-tips.md)を保持するか、カスタマイズするかを選択できます)。<br/>![ヒントと通知を含む DLP ポリシー設定](media/dlp-teams-policysettings-tipsemails.png)<br/>設定の確認または編集が完了したら、[**次へ**] を選択します。

8. [**ポリシー設定**] タブの [**ポリシーをオンにするか、または最初にテストしますか?**] で、ポリシーをオンにするか、[最初にテスト](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)するか、または今すぐ有効にしないかを選択し、[**次へ**] を選択します。<br/>![ポリシーを有効にするかどうかを指定する](media/dlp-teams-policysettings-turnonnow.png)<br/>

9. [**設定の確認**] タブで、新しいポリシーの設定を確認します。 [**編集**] を選択して変更を加えます。 完了したら、[**作成**] を選択します。 

新しいポリシーがデータセンターを使用して動作し、ユーザーアカウントに同期できるようになるまで約1時間かかります。

## <a name="related-articles"></a>関連記事

[DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)

[メール通知を送信して、DLP ポリシーのヒントを表示する](use-notifications-and-policy-tips.md)
