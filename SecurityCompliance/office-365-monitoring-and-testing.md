---
title: Office 365 テナント境界の監視とテスト
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '概要: Microsoft が Office 365 のテナント境界を監視およびテストする方法について説明します。'
ms.openlocfilehash: c0d6058a1ac4c0395f800b9b0da4108cb212bef9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262523"
---
# <a name="monitoring-and-testing-tenant-boundaries"></a>テナント境界の監視とテスト
Microsoft は継続的に監視し、侵入の監視、アクセス許可違反の試行、リソースの枯渇など、テナントの境界の弱点と脆弱性を明示的にテストします。 また、複数の内部システムを使用して、リソースの使用率を継続的に監視し、検出された場合は組み込みの調整をトリガーします。

Office 365 には、障害が検出された場合に障害を継続的に監視し、自動回復を実行する内部監視システムがあります。 Office 365 システムは、サービスの動作のずれを分析し、システムに組み込まれた自己復旧プロセスを開始します。 Office 365 では、信頼されたサードパーティ製のサービス (独立した SLA 確認用) と独自のデータセンターの両方から、複数の場所から監視を実行する、外部の監視も使用します。 診断の場合は、ログ、監査、およびトレースを拡張します。 詳細なトレースと監視は、問題を特定し、迅速かつ効果的な根本原因分析を実行するのに役に立ちます。

Office 365 には可能な場合は自動の回復操作がありますが、Microsoft のオンプレコールエンジニアは24時間365日のセキュリティに関するすべてのエスカレーションを調査でき、すべてのサービスインシデントが継続的な学習に貢献したすべてのサービスを事後レビューしています。改良. このチームには、サポートエンジニア、製品開発者、プログラムマネージャー、製品マネージャー、およびシニアリーダーシップが含まれています。 オンプレコールの専門家は、タイムリーなバックアップを提供し、多くの場合、回復操作を自動化することができます。そのため、次回イベントが発生したときに、自己 healed にすることができます。

Microsoft は、影響の大きさに関係なく、Office 365 セキュリティインシデントが発生するたびに、インシデントの詳細なレビューを行います。 インシデントレビューのレビューには、発生したこと、応答方法、および今後の類似インシデントを防ぐ方法が含まれています。 透明性とアカウンタビリティの目的として、影響を受けるお客様の主要なサービスインシデントについて、インシデントレビュー後のレビューを共有します。 詳細については、「 [Office 365 セキュリティインシデントの管理](http://aka.ms/Office365SIM)」を参照してください。

## <a name="assume-breach-methodology"></a>違反の方法論を想定する
セキュリティ傾向の詳細な分析に基づいて、Microsoft は、リアクティブなセキュリティプロセスや、新たな脅威への対応に重点を置いているその他の投資の必要性を重視して強調しています。これらの脅威。 脅威の状況や詳細な分析に変更が加えられたため、Microsoft はセキュリティ侵害を防止するだけでなく、セキュリティ上の問題が発生した場合に対処できるように改良しています。これは、重要なセキュリティイベントを考慮しないという戦略if の問題として、when。

microsoft では、多くの年に対して[違反](https://www.microsoft.com/en-us/TrustCenter/Security/default.aspx)の慣行が実施されていますが、多くのお客様は、microsoft クラウドを強化するためにバックグラウンドで実行されている作業については認識していません。 違反とは、セキュリティ投資、設計決定、運用のセキュリティ慣行をガイドするマインドセットです。 違反として、アプリケーション、サービス、id、およびネットワークに格納されている信頼が、セキュリティで保護されていない状態と、既に侵害されていることを前提としています。 [ブリーチ] 戦略は、Microsoft enterprise または cloud サービスの実際の違反からは利用できませんでしたが、これを回避しようとしても、多くの組織が侵害されていました。 違反が発生しないようにすることは、組織のあらゆる運用の重要な部分になりますが、これらのプラクティスを継続的にテストして、最新の敵対者と高度な脅威に効果的に対処する必要があります。 何らかの組織が侵害を準備するには、まず、堅牢で反復可能なテスト済みのセキュリティ対応手順を構築して維持する必要があります。

脅威のモデル化、コードレビュー、セキュリティテストなどのブリーチセキュリティプロセスは、[セキュリティ開発ライフサイクル](http://www.microsoft.com/security/sdl/default.aspx)の一部として非常に便利ですが、違反としては、全体的なセキュリティのために役立つさまざまな利点があります。違反が発生した場合に、リアクティブな機能を行使し、測定します。

Microsoft では、これを実現するために、お客様の継続的なゲームと、セキュリティ対応プランのライブサイトのペネトレーションテストを行って、検出と応答の機能を改善することを目指しています。 microsoft は、現実世界の侵害をシミュレートし、継続的なセキュリティ監視を行い、プラクティスセキュリティインシデント管理を実施して、Office 365、Azure、その他の Microsoft クラウドサービスのセキュリティを検証および改善します。

マイクロソフトは、次の2つのコアグループを使用して、"引き受け" というセキュリティ戦略を行います。
- Red Teams (攻撃者)
- Blue Teams (defenders)

Microsoft Azure と Office 365 の両方のスタッフは、フルタイムの赤のチームと青のチームを分離しています。

「[Red チーミング](http://go.microsoft.com/fwlink/?linkid=518599)」と呼ばれるアプローチは、実際の敵対者と同じ戦術、手法、手順を使用して、Azure と Office 365 のシステムおよび運用をテストすることです。エンジニアリングチームまたは運用チーム。 これは、Microsoft のセキュリティの検出と応答の機能をテストし、管理された方法で、運用上の脆弱性、構成エラー、無効な前提条件、その他のセキュリティ問題を特定するのに役立てることができます。 赤のチームのすべての違反は、その後に両方のチーム間で完全な公開が行われ、ギャップを特定し、結果を解決して、ブリーチの応答を改善します。

**注**: Red チーミングまたはライブサイトのペネトレーションテストでは、お客様のデータは意図的に対象化されません。 このテストは、Office 365 と Azure のインフラストラクチャとプラットフォーム、および Microsoft のテナント、アプリケーション、データに対して行われます。 Office 365 または Azure でホストされているお客様のテナント、アプリケーション、およびコンテンツは対象となりません。

## <a name="red-teams"></a>赤の Teams
赤色のチームは、microsoft の breaching microsoft のインフラストラクチャ、プラットフォーム、および microsoft 独自のテナントとアプリケーションに焦点を当てた、microsoft のフルタイムスタッフのグループです。 これは、専任の敵対者 (倫理的ハッカーのグループ) で、オンラインサービス (Microsoft のインフラストラクチャ、プラットフォーム、およびアプリケーションはエンドユーザーのアプリケーションやコンテンツではない) に対して、対象となる攻撃を行います。

赤のチームの役割は、敵対者と同じ手順を使用して環境を攻撃し、浸透させることです。
 
![違反のステージ](media/office-365-isolation-breach-stages.png)

その他の機能として、red teams では特に、分離設計のバグまたはギャップを見つけるためにテナント分離境界を侵害しようとしています。

## <a name="blue-teams"></a>Blue Teams
青のチームは、セキュリティインシデントの応答、エンジニアリング、運用組織にわたって、専用のセキュリティレスポンダーまたはメンバーのセットで構成されています。 作成者に関係なく、それらは独立しており、赤のチームとは別個に動作します。 ブルーチームは、確立されたセキュリティプロセスに従い、最新のツールとテクノロジを使用して、攻撃と侵入を検出して対応します。 実世界の攻撃と同様に、青のチームは、赤のチームの攻撃がいつ、どのような状況で行われるか、またどの方法が使用されるかを知ることはできません。 その仕事は、赤色のチーム攻撃であっても、実際の攻撃であっても、すべてのセキュリティインシデントを検出して対応することです。 このため、青色のチームは常に通話中であり、他の違反についてと同じ方法で、赤色のチーム違反に反応する必要があります。

赤のチームなどの敵対が環境を侵害した場合、青のチームは次のことを行う必要があります。
- 敵対者が残された証拠を収集する
- 侵害の兆候として証拠を検出する
- 適切なエンジニアリングおよび運用チームに警告する
- アラートをトリアージして、さらに調査することが保証されているかどうかを判断する
- 環境からコンテキストを収集して違反の範囲を取得する
- 敵対を含めるまたは削除するための修復計画を形成する
- 修復計画を実行し、ブリーチから回復する

これらの手順は、次のように、敵対者に対して平行して実行されるセキュリティインシデントの応答を形成します。
 
![違反の応答ステージ](media/office-365-isolation-breach-response-stages.png)

赤のチーム違反は、ブルーのチームがエンドツーエンドで現実の攻撃を検出して対応することを可能にします。 最も重要なことは、本物の違反が発生する前にセキュリティインシデントへの対応を行うことができることです。 さらに、赤色のチーム違反により、ブルーチームは状況の認識を向上させ、今後の侵害 (レッドチームまたは他の敵対者のいずれか) に対処する際に価値があります。 検出と応答のプロセスにおいて、青色のチームは操作可能なインテリジェンスを生成し、防御を試みている環境の実際の条件についての可視性を向上させることができます。 多くの場合、この作業はデータ分析と科学捜査によって実行され、赤のチーム攻撃への対応と、侵害の兆候などの脅威インジケーターの確立が行われます。 赤のチームがセキュリティストーリーのギャップを識別するのと同じように、青のチームは、検出して応答する機能のギャップを特定します。 さらに、赤の teams では現実世界の攻撃をモデル化しているため、青色のチームは、敵対者の能力または機能を正確に評価できます。 最後に、赤のチーム侵害は、違反への対応の準備と影響の両方を測定します。
