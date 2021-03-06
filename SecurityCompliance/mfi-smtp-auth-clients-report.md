---
title: SMTP Auth クライアントのレポート
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードの SMTP 認証クライアントレポートについて学習できます。
ms.openlocfilehash: 21d2446bd7441f17c2371186d098118c6403de0c
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598133"
---
# <a name="smtp-auth-clients-report"></a>SMTP Auth クライアントのレポート

**Smtp auth clients**レポートでは、組織内のユーザーまたはシステムアカウントによる smtp auth クライアント送信プロトコルの使用が強調されています。 この従来のプロトコル (エンドポイント smtp.office365.com を使用します) は基本認証のみを提供し、侵害されたアカウントが電子メールを送信するために使用されやすくなります。  このレポートでは、異常な動作を確認できます。 また、SMTP 認証を使用するクライアントまたはデバイスの TLS 使用状況データも表示されます。

メールフローダッシュボードに表示されるウィジェットは、過去7日間に SMTP 認証プロトコルを使用したユーザーまたはサービスアカウントの数を示します。

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードの SMTP 認証クライアントのレポート](media/smtp-auth-clients-report-selected.png)

ウィジェットをクリックすると、過去1週間の TLS 使用量とボリュームの集計ビューを表示するポップアップが表示されます。

![SMTP Auth clients レポートのポップアップ](media/smtp-auth-clients-flyout.png)

[ **SMTP Auth Clients] レポート**リンクをクリックすると、2つの主要なデータビューと2つのデータビューが表示されます。 データピボットは、**送信ボリューム**と**TLS 使用率**です。 データビューは、グラフと詳細の表です。

**送信ボリューム**ビューには、指定された時間範囲に関して SMTP Auth を使用して送信されたメッセージの数が表示されます。 範囲を調整するには、[**フィルター**] をクリックします。 このグラフは、送信者のドメインによって整理されています。 ドメインごとに個別のデータを表示するには、[**データの表示**] ドロップダウンでそのドメインを選択します。

![SMTP Auth Clients レポートでのボリュームの送信](media/smtp-auth-clients-report-sending-volume.png)

[**詳細テーブルの表示**] をクリックすると、送信者とそのメッセージカウントに関する詳細な情報を表示できます。 グラフに戻るには、[**レポートの表示**] をクリックします。

![SMTP Auth Clients レポートでのボリューム送信の詳細表](media/smtp-auth-clients-report-details-sending-volume.png)

Tls**使用率**ピボットは、Office 365 の tls 1.0 と tls 1.1 の今後の廃止によって重要です。 多くのレガシデバイスおよびアプリケーションは、SMTP Auth で TLS 1.0 を使用できる場合にのみ電子メールを送信できなくなります。このピボットにより、以前のバージョンの TLS を使用しているユーザーとシステムアカウントを識別し、アクションを実行することができます。

![SMTP Auth Clients レポートでの TLS の使用](media/smtp-auth-clients-report-tls-usage.png)

[**詳細テーブルの表示**] をクリックすると、送信者、SMTP 認証で使用している TLS のバージョン、およびそれらのメッセージ数に関する詳細情報を表示できます。 グラフに戻るには、[**レポートの表示**] をクリックします。

[要求レポート] をクリックして、レポートの詳細バージョンをダウンロードすることもできます。

![SMTP Auth Clients レポートでの TLS 使用の詳細表](media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a>関連項目

メールフローダッシュボードのその他のメールフローインサイトの詳細については、「[セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。
