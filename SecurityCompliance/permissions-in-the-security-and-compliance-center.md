---
title: Office 365 セキュリティ センターとコンプライアンス センターのアクセス許可
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 07/01/2019
audience: Admin
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.AdminRoleGroups
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
description: 管理者は、Office 365 セキュリティ & コンプライアンスセンターで利用可能なアクセス許可について学習できます。
ms.openlocfilehash: 285fb17a33326126ead3640790f44f4dd6ff5756
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600563"
---
# <a name="permissions-in-the-office-365-security--compliance-center"></a>Office 365 セキュリティ センターとコンプライアンス センターのアクセス許可

Office 365 セキュリティ & コンプライアンスセンターを使用すると、デバイス管理、データ損失防止、電子情報開示、保持などのコンプライアンスタスクを実行するユーザーにアクセス許可を付与することができます。 これらのユーザーは、明示的にアクセス権を付与されたタスクのみを実行できます。 セキュリティ & コンプライアンスセンターにアクセスするには、ユーザーは Office 365 のグローバル管理者であるか、1つ以上のセキュリティ & コンプライアンスセンターの役割グループのメンバーである必要があります。
  
セキュリティ & コンプライアンスセンターのアクセス許可は、役割ベースのアクセス制御 (RBAC) アクセス許可モデルに基づいています。 これは Exchange によって使用されるものと同じアクセス許可モデルです。 Exchange に精通している場合は、セキュリティ & コンプライアンスセンターでアクセス許可を付与すると非常によく似ています。 ただし、Exchange の役割グループとセキュリティ & コンプライアンスセンターの役割グループは、メンバーシップやアクセス許可を共有しないことに注意することが重要です。 どちらにも [組織の管理] 役割グループがありますが、同じではありません。 この役割グループが付与するアクセス許可およびメンバーシップは異なります。 以下に、セキュリティ & コンプライアンスセンターの役割グループの一覧があります。
  
![Office 365 セキュリティ/コンプライアンス センターの [アクセス許可] ページ](media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)
  
## <a name="relationship-of-members-roles-and-role-groups"></a>メンバー、役割、役割グループの関係

**役割**は、一連のタスクを実行するアクセス許可を付与します。たとえば、[ケース管理] 役割は電子情報開示ケースをユーザーが扱えるようにします。
  
**役割グループ**は、ユーザーがセキュリティ & コンプライアンスセンターを越えてジョブを実行できるようにする一連の役割です。たとえば、コンプライアンス管理者の役割グループには、コンプライアンス管理者がそのタスクを実行するためのアクセス許可を必要とするため、ケース管理、コンテンツ検索、組織の構成 (その他) の役割が含まれます。
  
セキュリティ & コンプライアンスセンターには、ユーザーを割り当てる必要がある最も一般的なタスクと機能の既定の役割グループが含まれています。 単に、個々のユーザーを既定の役割グループに**メンバー**として追加することをお勧めします。
  
![役割グループと、ロールおよびメンバーとの関係を示す図](media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)
  
既存の役割グループを編集または削除することはできますが、この方法はお勧めしません。 既定の役割グループを編集する代わりに、それをコピーしてから変更を加え、別の名前で保存できます。
  
## <a name="permissions-needed-to-use-features-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターで機能を使用するために必要なアクセス許可

次の表に、セキュリティ & コンプライアンスセンターで使用できる既定の役割グループと、既定で役割グループに割り当てられる役割を示します。 コンプライアンスタスクを実行する権限をユーザーに付与するには、適切なセキュリティ & コンプライアンスセンターの役割グループに追加します。
  
セキュリティ & コンプライアンスセンターでのアクセス許可の管理は、ユーザーにのみ、セキュリティ & コンプライアンスセンター自体で利用できるコンプライアンス機能へのアクセス権を付与します。 Exchange メールフロールール (トランスポートルールとも呼ばれます) など、セキュリティ & コンプライアンスセンターにない他のコンプライアンス機能に対する権限を付与する場合は、Exchange 管理センターを使用する必要があります。
  
セキュリティ & コンプライアンスセンターへのアクセス権を付与する方法を確認するには、「 [Office 365 コンプライアンス管理センターへのアクセス権をユーザー](grant-access-to-the-security-and-compliance-center.md)に付与する」を参照してください。
  
|**役割グループ**|**説明**|**割り当てられた既定の役割**|
|:-----|:-----|:-----|
|**コンプライアンス管理者**<sup>1</sup>|メンバーは、デバイス管理、データ損失防止、レポート、および保持の設定を管理できます。|ケース管理 <br/><br/> コンプライアンス管理者 <br/><br/> コンプライアンス検索 <br/><br/> DLP コンプライアンス管理 <br/><br/> デバイスの管理 <br/><br/> 廃棄管理 <br/><br/> 保留 <br/><br/> IB コンプライアンス管理 <br/><br/> 通知の管理 <br/><br/> 組織の構成 <br/><br/> RecordManagement <br/><br/> 保持管理 <br/><br/> 表示のみの監査ログ <br/><br/> 表示のみの保持管理 <br/><br/> 表示のみの DLP コンプライアンス管理 <br/><br/> 表示専用のデバイス管理 <br/><br/> 表示専用 IB のコンプライアンス管理 <br/><br/> 表示のみの通知の管理 <br/><br/> "View-Only Recipients/表示専用受信者" <br/><br/> 表示専用のレコード管理|
|**コンプライアンスデータ管理者**|メンバーは、デバイス管理、データ保護、データ損失防止、レポート、および保持の設定を管理できます。|コンプライアンス管理者 <br/><br/> コンプライアンス検索 <br/><br/> DLP コンプライアンス管理 <br/><br/> デバイスの管理 <br/><br/> 廃棄管理 <br/><br/> IB コンプライアンス管理 <br/><br/> 通知の管理 <br/><br/> 組織の構成 <br/><br/> RecordManagement <br/><br/> 保持管理 <br/><br/> 機密ラベル管理者 <br/><br/> 表示のみの監査ログ <br/><br/> 表示のみの DLP コンプライアンス管理 <br/><br/> 表示専用のデバイス管理 <br/><br/> 表示専用 IB のコンプライアンス管理 <br/><br/> 表示のみの通知の管理 <br/><br/> "View-Only Recipients/表示専用受信者" <br/><br/> 表示専用のレコード管理 <br/><br/> 表示のみの保持管理|
|**データの調査員**|メンバーは、メールボックス、SharePoint サイト、および OneDrive アカウントに対して検索を実行できます。|情報 <br/><br/> コンプライアンス検索 <br/><br/> Custodian <br/><br/> データ調査の管理 <br/><br/> エクスポート<br/><br/> プレビュー <br/><br/> RMS の暗号化解除 <br/><br/> レビュー|
|**電子情報開示マネージャー**|メンバーは、メールボックス、SharePoint Online サイト、OneDrive for Business ロケーションで検索およびホールドの適用を実行できます。 メンバーは、電子情報開示ケースの作成と管理、ケースへのメンバーの追加および削除、ケースに関連付けられたコンテンツ検索の作成と編集、Office 365 Advanced eDiscovery でのサポート案件データへのアクセスも行うことができます。 <br/><br/> 電子情報開示管理者は電子情報開示マネージャー役割グループのメンバーで、追加のアクセス許可が割り当てられています。 電子情報開示管理者が実行できるタスクに加えて、電子情報開示管理者は次のことを行うことができます。 <br/>•組織内のすべての電子情報開示ケースを表示します。 <br/>•電子情報開示ケースのメンバーとして自身を追加した後で、そのケースを管理します。 <br/><br/> 電子情報開示マネージャーと電子情報開示管理者の主な違いは、電子情報開示管理者がセキュリティ & コンプライアンスセンターの [**電子情報開示ケース**] ページに記載されているすべてのケースにアクセスできることです。 電子情報開示マネージャーは、作成したケース、またはそのメンバーが所属するケースのみにアクセスできます。 電子情報開示管理者としてユーザーを作成する方法の詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。|ケース管理 <br/><br/> 情報 <br/><br/> コンプライアンス検索 <br/><br/> Custodian <br/><br/> エクスポート <br/><br/> 保留 <br/><br/> プレビュー <br/><br/> RMS の暗号化解除 <br/><br/> レビュー|
|**グローバル閲覧者**|メンバーは、レポートや通知に対する読み取り専用アクセス権を持ち、すべての構成と設定を表示できます。<br/><br/> グローバルリーダーとセキュリティリーダーの主な違いは、グローバル閲覧者が**構成と設定**にアクセスできることです。|表示のみの保持管理 <br/><br/> 表示のみの通知の管理 <br/><br/> 表示専用のデバイス管理 <br/><br/> 表示専用 IB のコンプライアンス管理 <br/><br/> 表示のみの DLP コンプライアンス管理 <br/><br/> セキュリティリーダ <br/><br/> サービス保証ビュー <br/><br/> 表示のみの監査ログ <br/><br/> 表示専用のレコード管理 <br/><br/> "View-Only Recipients/表示専用受信者"|
|**メールフロー管理者**|メンバーは、セキュリティ & コンプライアンスセンターで、メールフローの洞察とレポートを監視および表示できます。 グローバル管理者は、通常のユーザーをこのグループに追加できますが、ユーザーが Exchange 管理者グループのメンバーでない場合、ユーザーは Exchange 管理関連のタスクにアクセスできません。|"View-Only Recipients/表示専用受信者"|
|**組織の管理**<sup>1</sup>|メンバーは、セキュリティ & コンプライアンスセンターの機能にアクセスするためのアクセス許可を制御したり、デバイス管理、データ損失防止、レポート、および保持の設定を管理したりすることもできます。 <br/><br/> グローバル管理者以外のユーザーが、Office 365 用 MDM によって管理されているデバイスの一覧を表示して、これらの365デバイスでアクションを実行するためには、ユーザーは Exchange 管理者である必要があります。 <br/><br/> Office 365 のグローバル管理者は、この役割グループのメンバーとして自動的に追加されます。|監査ログ <br/><br/> ケース管理 <br/><br/> コンプライアンス管理者 <br/><br/> コンプライアンス検索 <br/><br/> DLP コンプライアンス管理 <br/><br/> デバイスの管理 <br/><br/> 廃棄管理 <br/><br/> 保留 <br/><br/> IB コンプライアンス管理 <br/><br/> 通知の管理 <br/><br/> 組織の構成 <br/><br/> RecordManagement <br/><br/> 保持管理 <br/><br/> 役割管理 <br/><br/> 検索と消去 <br/><br/> セキュリティ管理者 <br/><br/> セキュリティリーダ <br/><br/> 機密ラベル管理者 <br/><br/> サービス保証ビュー <br/><br/> 表示のみの監査ログ <br/><br/> 表示のみの DLP コンプライアンス管理 <br/><br/> 表示専用のデバイス管理 <br/><br/> 表示専用 IB のコンプライアンス管理 <br/><br/> 表示のみの通知の管理 <br/><br/> "View-Only Recipients/表示専用受信者" <br/><br/> 表示専用のレコード管理 <br/><br/> 表示のみの保持管理|
|**レコードの管理**|メンバーは、レコードの内容を管理および破棄できます。|監査ログ <br/><br/> RecordManagement <br/><br/> 保持管理|
|**レビュー担当者**|メンバーは、セキュリティ & コンプライアンスセンターの [電子情報開示ケース] ページでのみ、ケースの一覧を表示できます。 電子情報開示ケースを作成したり、開いたり、管理したりすることはできません。 この役割グループの主な目的は、メンバーが Advanced 電子情報開示のケースデータを表示してアクセスできるようにすることです。 <br/><br/> この役割グループが持っている電子情報開示関連のアクセス許可は最も厳しくなっています。|レビュー|
|**セキュリティ管理者**|この役割グループのメンバーには、サービス間管理者、外部パートナーグループ、Microsoft サポートを含めることができます。 既定では、このグループに役割を割り当てることはできません。 ただし、Azure Active Directory のセキュリティ管理者の役割のメンバーとなり、その役割の機能を継承します。 アクセス許可を一元的に管理するには、Azure Active Directory 管理センターでこの役割を変更します。詳細については、「 [Azure Active directory の管理者ロールのアクセス許可](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」を参照してください。 <br/><br/> セキュリティ & コンプライアンスセンターでこの役割グループを編集する場合、これらの変更はセキュリティ & コンプライアンスセンターにのみ適用され、他のサービスには適用されませんが、Azure Active Directory 管理センターで行われた変更はすべてのサービスに影響します。 <br/><br/> セキュリティリーダーの役割のすべての読み取り専用アクセス許可、および同じサービスに対するその他の管理アクセス許可: Azure Information Protection、Identity Protection Center、特権 Id 管理、Office 365 サービスを監視するHealth、Office 365 Security & コンプライアンスセンター。|監査ログ <br/><br/> DLP コンプライアンス管理 <br/><br/> デバイスの管理 <br/><br/> IB コンプライアンス管理 <br/><br/> 通知の管理 <br/><br/> セキュリティ管理者 <br/><br/> 機密ラベル管理者 <br/><br/> 表示のみの監査ログ <br/><br/> 表示のみの DLP コンプライアンス管理 <br/><br/> 表示専用のデバイス管理 <br/><br/> 表示専用 IB のコンプライアンス管理 <br/><br/> 表示のみの通知の管理|
|**セキュリティオペレーター**|メンバーはセキュリティの警告を管理でき、セキュリティ機能のレポートと設定も表示できます。|コンプライアンス検索 <br/><br/> 通知の管理 <br/><br/> セキュリティリーダ <br/><br/> 表示のみの監査ログ <br/><br/> 表示のみの DLP コンプライアンス管理 <br/><br/> 表示専用のデバイス管理 <br/><br/> 表示専用 IB のコンプライアンス管理 <br/><br/> 表示のみの通知の管理|
|**セキュリティリーダ**|メンバーは、Id 保護センター、特権 Id 管理、Office 365 サービス正常性の監視、および Office 365 Security & コンプライアンスセンターのさまざまなセキュリティ機能への読み取り専用アクセス権を持ちます。 <br/><br/> この役割グループのメンバーシップは、複数のサービス間で同期され、一元管理されます。 この役割グループのメンバーには、サービス間管理者、外部パートナーグループ、Microsoft サポートを含めることができます。 既定では、このグループに役割を割り当てることはできません。 ただし、Azure Active Directory のセキュリティリーダーの役割のメンバーとなり、その役割の機能を継承します。 アクセス許可を一元的に管理するには、Azure Active Directory 管理センターでこの役割を変更します。詳細については、「 [Azure Active directory の管理者ロールのアクセス許可](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」を参照してください。 この役割グループをセキュリティ & コンプライアンスセンターで編集する場合、これらの変更はセキュリティ & コンプライアンスセンターにのみ適用され、他のサービスには適用されませんが、Azure Active Directory 管理センターで行われた変更はすべてのサービスに影響します。|セキュリティリーダ <br/><br/> 表示のみの DLP コンプライアンス管理 <br/><br/> 表示専用のデバイス管理 <br/><br/> 表示専用 IB のコンプライアンス管理 <br/><br/> 表示のみの通知の管理|
|**Service Assurance User**|メンバーは、Office 365 セキュリティ & コンプライアンスセンターの [サービス保証] セクションにアクセスできます。 サービスアシュアランス Office 365 に保存されている顧客データに関する Microsoft のセキュリティプラクティスを説明するレポートとドキュメントを提供します。 また、Office 365 の独立したサードパーティの監査レポートも提供します。 詳細については、「 [Office 365 セキュリティ & コンプライアンスセンター」の「サービスアシュアランス](http://go.microsoft.com/fwlink/p/?LinkID=717765)」を参照してください。|サービス保証ビュー|
|**Supervisory Review**|メンバーは、組織内で確認する対象となる通信を定義するポリシーを作成および管理できます。 詳細については、「[組織の監督レビューポリシーを構成する](configure-supervision-policies.md)」を参照してください。|監督レビュー管理者|

> [!NOTE]
> <sup>1</sup>この役割グループは、Office 365 監査ログを検索するために必要なアクセス許可、または DLP または ATP レポートなどの Exchange データが含まれるレポートを使用するために、メンバーを割り当てません。 監査ログを検索したり、すべてのレポートを表示したりするには、Exchange Online でユーザーにアクセス許可を割り当てる必要があります。 これは、監査ログの検索に使用される基礎となるコマンドレットが Exchange Online のコマンドレットであるためです。 Office 365 グローバル管理者は、Exchange Online の組織の管理役割グループのメンバーとして自動的に追加されているため、監査ログを検索し、すべてのレポートを表示できます。 詳細については、「[Office 365 セキュリティ/コンプライアンス センターで監査ログを検索する](https://go.microsoft.com/fwlink/p/?LinkID=708432)」を参照してください。
  
## <a name="roles-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターの役割

次の表に、既定で使用可能な役割と、それらに割り当てられている役割グループを示します。

既定では、次の役割は組織の管理役割グループに割り当てられていないことに注意してください。

- 情報

- Custodian

- データ調査の管理

- エクスポート

- プレビュー

- レビュー

- RMS の暗号化解除

- 監督レビュー管理者

|**役割**|**説明**|**既定の役割グループの割り当て**|
|:-----|:-----|:-----|
|**監査ログ**|Office 365 組織の監査を有効にして構成し、組織の監査レポートを表示して、これらのレポートをファイルにエクスポートします。|組織の管理 <br/><br/> レコード管理 <br/><br/> セキュリティ管理者|
|**ケース管理**|電子情報開示ケースへのアクセスを作成、編集、削除、制御します。|コンプライアンス管理者 <br/><br/> 電子情報開示マネージャー <br/><br/> 組織の管理|
|**データの調査員**|メールボックス、SharePoint Online サイト、および OneDrive for Business の場所に対して検索を実行します。|エクスポート <br/><br/> RMS の暗号化解除 <br/><br/> Custodian <br/><br/> 情報 <br/><br/> レビュー <br/><br/> プレビュー <br/><br/> コンプライアンス検索 <br/><br/> データ調査の管理|
|**情報**|高度な電子情報開示ケースで特定された保管担当者とのすべての通信を管理します。  保留通知の作成、アラームの保持、および管理へのエスカレーションを行います。 保管担当者の受信確認を追跡し、各保管担当者で使用されている保管担当者ポータルへのアクセスを管理します。ケースでは、保管担当者として識別された場合の通信を追跡するために使用されます。|電子情報開示マネージャー|
|**コンプライアンス管理者**|コンプライアンス機能の設定とレポートを表示および編集します。|コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 組織の管理|
|**コンプライアンス検索**|メールボックス全体にわたって検索を実行し、結果の推定値を取得します。|コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 電子情報開示マネージャー <br/><br/> 組織の管理 <br/><br/> セキュリティオペレーター|
|**Custodian**|高度な電子情報開示ケースの保管担当者を特定して管理し、Azure Active Directory およびその他のソースからの情報を使用して、保管担当者に関連付けられているデータソースを検索します。 ケースでは、メールボックス、SharePoint サイト、Teams などの他のデータソースを保管担当者に関連付けます。  訴訟のコンテキストでコンテンツを保持するために、保管担当者に関連付けられているデータソースに法的情報を保持します。|電子情報開示マネージャー|
|**データ調査の管理**|データ調査を作成、編集、削除、およびアクセスを制御します。|データの調査員|
|**デバイスの管理**|デバイス管理機能の設定とレポートを表示および編集します。|コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 組織の管理 <br/><br/> セキュリティ管理者|
|**廃棄管理**|セキュリティ & コンプライアンスセンターで手動による廃棄にアクセスするためのアクセス許可を制御します。|コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 組織の管理|
|**DLP コンプライアンス管理**|データ損失防止 (DLP) ポリシーの設定とレポートを表示および編集します。|コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 組織の管理 <br/><br/> セキュリティ管理者|
|**Export**|検索によって返されたメールボックスとサイトコンテンツをエクスポートします。|電子情報開示マネージャー|
|**保留**|メールボックス、サイト、およびパブリックフォルダーにコンテンツを保持します。 保留中は、コンテンツのコピーが安全な場所に保存されます。 コンテンツ所有者は、引き続き元のコンテンツを変更または削除することができます。|コンプライアンス管理者 <br/><br/> 電子情報開示マネージャー <br/><br/> 組織の管理|
|**IB コンプライアンス管理**|情報バリアポリシーを表示、作成、削除、変更、およびテストします。|コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 組織の管理 <br/><br/> セキュリティ管理者|
|**通知の管理**|通知の設定とレポートを表示および編集します。|コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 組織の管理 <br/><br/> セキュリティ管理者 <br/><br/> セキュリティオペレーター|
|**組織の構成**|監査レポートを実行、表示、およびエクスポートし、DLP、デバイス、および保持のコンプライアンスポリシーを管理します。|コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 組織の管理|
|**プレビュー**|コンテンツ検索から返されるアイテムのリストを表示し、リストから各アイテムを開いてコンテンツを表示します。|電子情報開示マネージャー|
|**RecordManagement**|レコード管理機能の構成とレポートを表示および編集します。|コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 組織の管理 <br/><br/> レコード管理|
|**保持管理**|アイテム保持ポリシーを管理します。|レコード管理 <br/><br/> コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 組織の管理|
|**確認**|Office 365 Advanced eDiscovery を使用して、割り当てられているドキュメントを追跡、タグ付け、分析、およびテストします。|電子情報開示マネージャー <br/><br/> レビュー担当者|
|**RMS の暗号化解除**|検索結果をエクスポートするときに、RM で保護されたコンテンツの暗号化を解除します。|電子情報開示マネージャー|
|**役割管理**|役割グループのメンバーシップを管理し、カスタム役割グループを作成または削除します。|組織の管理|
|**検索と消去**|コンテンツ検索の条件に一致するデータをユーザーが一括削除できるようにします。|組織の管理|
|**セキュリティ管理者**|セキュリティ機能の構成とレポートを表示および編集します。|組織の管理 <br/><br/> セキュリティ管理者|
|**セキュリティリーダ**|セキュリティ機能の構成とレポートを表示します。|組織の管理 <br/><br/> セキュリティオペレーター <br/><br/> セキュリティリーダ|
|**機密ラベル管理者**|機密ラベルを表示、作成、変更、および削除します。|コンプライアンスデータ管理者 <br/><br/> 組織の管理 <br/><br/> セキュリティ管理者|
|**サービス保証ビュー**|利用可能なドキュメントをサービスアシュアランスセクションからダウンロードします。 コンテンツには、独立した監査、コンプライアンスに関するドキュメント、および Office 365 機能を使用して法令遵守やセキュリティリスクを管理するための信頼関連ガイダンスが含まれています。|Service Assurance User <br/><br/> 組織の管理|
|**監督レビュー管理者**|レビュー対象の通信やレビューを実行するユーザーを含む監督レビューポリシーを管理します。|Supervisory Review|
|**表示のみの監査ログ**|監査レポートを表示およびエクスポートします。 これらのレポートには機密情報が含まれている可能性があるため、この情報を明示的に確認する必要があるユーザーにのみ、この役割を割り当てる必要があります。|コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 組織の管理 <br/><br/> セキュリティ管理者 <br/><br/> セキュリティオペレーター|
|**表示専用のデバイス管理**|デバイス管理機能の構成とレポートを表示します。|コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 組織の管理 <br/><br/> セキュリティ管理者 <br/><br/> セキュリティオペレーター <br/><br/> セキュリティリーダ|
|**表示のみの DLP コンプライアンス管理**|データ損失防止 (DLP) ポリシーの設定とレポートを表示します。|コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 組織の管理 <br/><br/> セキュリティ管理者 <br/><br/> セキュリティオペレーター <br/><br/> セキュリティリーダ|
|**表示専用 IB のコンプライアンス管理**|情報障壁機能の構成とレポートを表示します。|コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 組織の管理 <br/><br/> セキュリティ管理者 <br/><br/> セキュリティオペレーター <br/><br/> セキュリティリーダ|
|**表示のみの通知の管理**|通知の管理機能の構成とレポートを表示します。|セキュリティ管理者 <br/><br/> セキュリティオペレーター <br/><br/> セキュリティリーダ <br/><br/> コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 組織の管理|
|**"View-Only Recipients/表示専用受信者"**|ユーザーおよびグループに関する情報を表示します。|メールフロー管理者 <br/><br/> コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 組織の管理|
|**表示専用のレコード管理**|レコード管理機能の構成とレポートを表示します。|コンプライアンス管理者 <br/><br/> コンプライアンスデータ管理者 <br/><br/> 組織の管理|
|**表示のみの保持管理**|アイテム保持管理機能の構成とレポートを表示します。|コンプライアンスデータ管理者 <br/><br/> 組織の管理 <br/><br/> コンプライアンス管理者|
