---
title: 調査のためにデータを処理するときのエラー修復
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: f8e253a3d38f0f4846485e3b88ea09914d9978ce
ms.sourcegitcommit: 6eb51931242d07abde2e37f1bd57d13bc724f0de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34547952"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a>調査のためにデータを処理するときのエラー修復

エラー修復を使用すると、調査担当はデータ調査 (プレビュー) がコンテンツを適切に処理できなくなるデータの問題を修正することができます。 たとえば、ファイルがロックまたは暗号化されているため、パスワードで保護されたファイルを処理することはできません。 エラー修復を使用する調査官は、このようなエラーのあるファイルをダウンロードし、パスワード保護を解除して、修復されたファイルをアップロードすることができます。

データ調査 (プレビュー) ケースでエラーが発生したファイルを修復するには、次のワークフローを使用します。

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>処理エラーが発生したファイルを修復するためのエラー修復セッションを作成する

>[!NOTE]
>次の手順の途中でエラー修復ウィザードが閉じられた場合は、[**表示**] ドロップダウンメニューから [error **** **remediations** ] を選択することにより、エラー修復セッションに戻ることができます。

1. データ調査 (プレビュー) ケースの [**処理**] タブで、[**表示**] ドロップダウンメニューから [**エラー** ] を選択します。

2. エラーの種類またはファイルの種類の横にあるラジオボタンをクリックして、修復するエラーを選択します。  次の例では、パスワードで保護されたファイルを修復しています。

3. [ **+ 新しいエラーの修復**] をクリックします。

    ![エラーの修復](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    エラー修復セッションが開始され、エラーが発生したファイルが安全な Azure 場所にコピーされ、ダウンロードできるようになります。

    ![エラー修復の準備](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. 準備が完了したら、[**次へ: ファイルのダウンロード**] をクリックして、ダウンロードを続行します。

    ![ファイルをダウンロードする](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. ファイルをダウンロードするには、**ダウンロード先のパス**を指定します。これは、ファイルをダウンロードするローカルコンピューター上のパスです。  既定のパス%USERPROFILE%\Downloads\errors は、ログインしているユーザーの [ダウンロード] フォルダーを指します。必要に応じて変更できます。

    >[!NOTE]
    >最適なパフォーマンスを得るには、リモートネットワークパスの代わりにローカルファイルパスを使用することをお勧めします。

    > [!NOTE]
    > AzCopy をインストールしていない場合は、ここからインストールできます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

6. [**クリップボードにコピー] を**クリックして、定義済みのコマンドをコピーします。 Windows コマンドプロンプトを起動し、コマンドを貼り付けて、 **enter**キーを押します。  

    ファイルがダウンロードされます。

    ![エラー修復の準備](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > このコマンドの実行に関する問題がある場合は、「 [Advanced eDiscovery での AzCopy のトラブルシューティング](../compliance20/troubleshooting-azcopy.md)」を参照してください。

7. ファイルをダウンロードした後、適切なツールを使用して修復できます。 パスワードで保護されたファイルには、いくつかのパスワードクラッキングツールを使用できます。 ファイルのパスワードがわかっている場合は、それらを開いてパスワード保護を解除することができます。
    
   > [!NOTE]
    > Tact で修復されたファイルのディレクトリ構造とファイル名を保持することが重要です。  ダウンロードしたファイルとフォルダーで使用されているすべての命名規則によって、remdiated ファイルを元のファイルに戻すことができます。

8. データの調査 (プレビュー) に戻り、[**次へ: ファイルのアップロード**] をクリックします。  これにより、次の手順に進み、ファイルをアップロードできるようになります。

    ![ファイルをアップロードする](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. [**ファイルの場所へのパス**] テキストボックスに修復したファイルの場所を指定し、[**クリップボードにコピー] を**クリックします。

10. コマンドを Windows コマンドプロンプトに貼り付け、 **enter**キーを押してファイルをアップロードします。

    ![ff2ff691-629f-4065-9b37-5333f937daf6](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. 最後に、データ調査 (プレビュー) に戻り、[**次へ: プロセスファイル**] をクリックします。

12. 処理が完了したとき。  ワーキングセットに戻り、修復されたファイルを確認することができます。

## <a name="what-happens-when-files-are-remediated"></a>ファイルが修復されたときの処理

修復済みのファイルがアップロードされると、元のメタデータは次のフィールドを除いて保持されます。 

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- テキスト
- WordCount
- WorkingsetId

データ調査 (プレビュー) 内のすべてのドキュメントメタデータフィールドの定義については、「[ドキュメントメタデータフィールド](document-metadata-fields.md)」を参照してください。