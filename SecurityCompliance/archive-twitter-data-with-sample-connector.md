---
title: サンプルコネクタを使用して Office 365 で Twitter データをアーカイブする (プレビュー)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理者は、Office 365 に Twitter データをインポートするためのネイティブコネクタをセットアップできます。 これにより、Office 365 でサードパーティのデータソースのデータをアーカイブできるため、組織のサードパーティデータのガバナンスを管理するために、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用できます。
ms.openlocfilehash: 6780e3fbb53e2326994e03815403c1e5ae0d0616
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014686"
---
# <a name="use-a-sample-connector-to-archive-twitter-data-in-office-365-preview"></a>サンプルコネクタを使用して Office 365 で Twitter データをアーカイブする (プレビュー)

Office 365 で Twitter データをアーカイブするためのサンプルコネクタ機能は、プレビュー段階にあります。

Office 365 のセキュリティ & コンプライアンスセンターのサンプルコネクタを使用して、Twitter からデータをインポートおよびアーカイブします。 サンプルコネクタをセットアップして構成すると、組織の Twitter アカウントに (スケジュールに従って) 接続され、アイテムのコンテンツが電子メールメッセージの形式に変換されてから、それらのアイテムを Office 365 のメールボックスにインポートします。

Twitter データをインポートすると、メールボックスに格納されているデータに、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、監督、Office 365 アイテム保持ポリシーなどの Office 365 コンプライアンス機能を適用できます。 たとえば、コンテンツ検索を使用して Twitter データを検索したり、保管担当者でデータが格納されているメールボックスを、高度な電子情報開示ケースに関連付けたりすることができます。 サンプルコネクタを使用して Office 365 で Twitter データをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。

> [!NOTE]
> 現時点では、Twitter および[Facebook のビジネスページ](archive-facebook-data-with-sample-connector.md)用のサンプルコネクタのみをプレビューで利用できます。 その他のサンプルコネクタは近日中に公開されます。


## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a>Twitter 用のコネクタを設定するための前提条件

セキュリティ & コンプライアンスセンターでサンプルコネクタを設定および構成するには、次の前提条件を満たしている必要があります。これにより、組織の Twitter アカウントからデータをインポートしてアーカイブすることができます。 

- 組織のために Twitter アカウントが必要です。コネクタを設定するときに、このアカウントにサインインする必要があります。

- 組織が有効な Azure サブスクリプションを持っている必要があります。 既存の Azure サブスクリプションがない場合は、次のオプションのいずれかにサインアップできます。

    - [1年間の無料の Azure サブスクリプションにサインアップする](https://azure.microsoft.com/free) 

    - [Azure へのご購入のサブスクリプションへのサインアップ](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Office 365 サブスクリプションに含まれている[無料の Azure Active Directory サブスクリプション](use-your-free-azure-ad-subscription-in-office-365.md)は、セキュリティ & コンプライアンスセンターのサンプルコネクタをサポートしていません。

- 組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 この要求に同意するには、[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Office 365 グローバル管理者の資格情報でサインインし、要求を承諾します。

- セキュリティ & コンプライアンス (手順 7) でカスタムコネクタをセットアップするユーザーに、Exchange Online のメールボックスのインポートのエクスポート役割を割り当てる必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、新しい役割グループを作成し、メールボックスインポートエクスポートの役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「[役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)」または「[役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)」のセクションを参照してください。

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a>手順 1: Github から事前に作成されたコネクタアプリパッケージをダウンロードする

最初の手順として、twitter API を使用して twitter アカウントに接続し、データを抽出して Office 365 にインポートできるようにする Twitter サンプルコネクタアプリのソースコードをダウンロードします。

1. [この GitHub サイト](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)に移動します。 
2. 最新のリリースで、 **SampleConnector**ファイルをクリックします。
3. ZIP ファイルをローカルコンピューターの場所に保存します。 この zip ファイルを手順4で Azure にアップロードします。

## <a name="step-2-create-an-app-in-azure-active-directory"></a>手順 2: Azure Active Directory でアプリを作成する

次の手順では、Azure Active Directory (AAD) に新しいアプリを登録します。 このアプリは、Twitter connector の手順4で実装した web app リソースに対応します。 

詳細な手順については、「[手順 2: Azure Active Directory でアプリを作成](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory)する」を参照してください。

この手順が完了すると (手順に従って)、次の情報がテキストファイルに保存されます。 これらの値は、展開プロセスの後の手順で使用されます。

- AAD アプリケーション ID
- AAD アプリケーションシークレット
- AAD アプリケーション Uri
- テナント Id

## <a name="step-3-create-an-azure-storage-account"></a>手順 3: Azure storage アカウントを作成する

組織用に展開する Twitter コネクタは、Twitter から、この手順で作成した Azure ストレージの場所にアイテムをアップロードします。 セキュリティ & コンプライアンスセンター (手順 7) でカスタムコネクタを作成すると、Office 365 インポートサービスによって、Azure ストレージの場所から Office 365 のメールボックスに Twitter データがコピーされます。 前述の「[前提条件](#prerequisites-for-setting-up-a-connector-for-twitter)」セクションで説明したように、azure storage アカウントを作成するには、有効な azure サブスクリプションを用意する必要があります。

詳細な手順については、「[手順 3: Azure ストレージアカウントを作成する](deploy-twitter-connector.md#step-3-create-an-azure-storage-account)」を参照してください。

この手順が完了すると (手順に従って)、生成された接続文字列 Uri が保存されます。 この文字列は、手順4で Azure で web app リソースを作成するときに使用します。

## <a name="step-4-create-a-web-app-resource-in-azure"></a>手順 4: Azure で web app リソースを作成する

次の手順では、Twitter コネクタ用に Azure で web app リソースを作成します。 

詳細な手順については、「 [step 4: Create a new web app resource In Azure](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure)」を参照してください。

この手順が完了すると (手順に従って)、次の情報が提供されます (前の手順を完了した後、テキストファイルにコピーしたもの) web app リソースを作成します。

- APISecretKey –この手順の完了時にこのシークレットを作成します。手順7で使用します。
- StorageAccountConnectionString –手順3で Azure storage アカウントを作成した後にコピーした接続文字列 Uri。
- tenantId –手順2で、Azure Active Directory で Twitter connector アプリを作成した後にコピーした Office 365 組織のテナント ID。

また、この手順で SampleConnector ファイル (手順1でダウンロードした) をアップロードして、Twitter connector アプリのソースコードを展開します。

この手順を完了したら、Azure app service の URL (たとえば、) https://twitterconnector.azurewebsites.net)を必ずコピーしてください。 手順5、手順6、手順7を完了するには、これを使用する必要があります。

## <a name="step-5-create-developer-app-on-twitter"></a>手順 5: Twitter で開発者用アプリを作成する

次の手順では、Twitter で開発者用アプリを作成して構成します。 手順7で作成したカスタムコネクタは、twitter アプリを使用して、組織の Twitter アカウントからデータを取得する Twitter API と対話します。

詳細な手順については、「[手順 5: Twitter アプリを作成](deploy-twitter-connector.md#step-5-create-the-twitter-app)する」を参照してください。

この手順が完了したら (手順に従って)、次の情報をテキストファイルに保存します。 これらの値は、手順6で Twitter connector アプリを構成するために使用されます。

- Twitter API キー
- Twitter API の秘密キー
- Twitter アクセストークン
- Twitter アクセストークンシークレット

## <a name="step-6-configure-the-twitter-connector-app"></a>手順 6: Twitter connector アプリを構成する

次の手順では、手順4で Azure web app リソースの作成時にアップロードした Twitter connector アプリに構成設定を追加します。 これを行うには、コネクタアプリのホームページにアクセスして構成します。

詳細な手順については、「 [step 6: Configure the connector web app](deploy-twitter-connector.md#step-6-configure-the-connector-web-app)」を参照してください。

この手順が完了すると (手順に従って)、次の情報が提供されます (前の手順を完了した後、テキストファイルにコピーしたことになります)。

- Twitter API キー (手順5で取得)
- Twitter API の秘密キー (手順5で取得)
- Twitter アクセストークン (手順5で取得)
- Twitter アクセストークンシークレット (手順5で取得)
- Azure Active Directory アプリケーション ID (手順2で取得した AAD アプリケーション ID)
- Azure Active Directory アプリケーションシークレット (手順2で取得した AAD アプリケーションシークレット)
- Azure Active Directory アプリケーション Uri (手順2で取得した AAD アプリケーション Uri、たとえば、https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>手順 7: セキュリティ & コンプライアンスセンターでカスタムコネクタをセットアップする

最後の手順として、セキュリティ & コンプライアンスセンターでカスタムコネクタを設定して、組織の Twitter アカウントから Office 365 の指定したメールボックスにデータをインポートします。 この手順を正常に完了すると、Office 365 インポートサービスは、Twitter から Office 365 にデータをインポートするプロセスを開始します。 

詳細な手順については、「[手順 7: セキュリティ/コンプライアンスセンターでカスタムコネクタを設定する](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center)」を参照してください。 

この手順が完了すると (手順に従って)、次の情報が提供されます (手順を完了したら、テキストファイルにコピーしたことになります)。

- Azure app service の URL (手順4で取得)。たとえば、https://twitterconnector.azurewebsites.net)
- APISecretKey (手順4で作成したもの)
