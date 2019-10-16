---
title: 更新可能なヘルプのしくみ |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7674636e-a0f2-4587-bfc5-dd3e6ce5489e
caps.latest.revision: 6
ms.openlocfilehash: 5b6ae54ee6c843996c875189b6ee553be5e4f614
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367081"
---
# <a name="how-updatable-help-works"></a>更新可能なヘルプのしくみ

このトピックでは、更新可能なヘルプが各モジュールの HelpInfo XML ファイルと CAB ファイルを処理し、ユーザーの更新されたヘルプをインストールする方法について説明します。

## <a name="the-update-help-process"></a>Update-help プロセス

次の一覧では、ユーザーが特定の UI カルチャのモジュールのヘルプファイルを更新するコマンドを実行したとき[の update-help コマンドレットの](/powershell/module/Microsoft.PowerShell.Core/Update-Help)動作について説明します。

1. `Update-Help` は、モジュールマニフェストの**Helpinfouri**キーの値によって指定された場所から REMOTE HelpInfo XML ファイルを取得し、スキーマに対してファイルを検証します。 (スキーマを表示するには、「 [HELPINFO XML schema](./helpinfo-xml-schema.md)」を参照してください)。次に、`Update-Help` は、ユーザーのコンピューターのモジュールディレクトリにあるモジュールのローカル HelpInfo XML ファイルを検索します。

2. `Update-Help` は、指定された UI カルチャのヘルプファイルのバージョン番号を、モジュールのリモートおよびローカルの HelpInfo XML ファイルと比較します。 リモートファイルのバージョン番号がローカルファイルのバージョン番号よりも大きい場合、またはモジュールのローカル HelpInfo XML ファイルが存在しない場合、`Update-Help` は新しいヘルプファイルのダウンロードを準備します。

3. `Update-Help` は、リモートの HelpInfo XML ファイルの**Helpcontenturi**要素によって指定された場所からモジュールの CAB ファイルを選択します。 モジュール名、モジュール GUID、および UI カルチャを使用して、CAB ファイルを識別します。

4. `Update-Help` は、CAB ファイルをダウンロードしてアンパックし、ヘルプコンテンツファイルを検証し、ヘルプコンテンツファイルをユーザーのコンピューターのモジュールディレクトリの言語固有のサブディレクトリに保存します。

5. `Update-Help` は、リモートの HelpInfo XML ファイルをコピーすることによって、ローカルの HelpInfo XML ファイルを作成します。 ローカルの HelpInfo XML ファイルを編集して、インストールした CAB ファイルの要素のみが含まれるようにします。 次に、ローカルの HelpInfo XML ファイルをモジュールディレクトリに保存し、更新を終了します。

## <a name="the-save-help-process"></a>保存時のヘルプ

次の一覧では、ユーザーがファイル共有内のヘルプファイルを更新するコマンドを実行し、そのファイルを使用してユーザーのコンピューター上のヘルプファイルを更新するときの、 [help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)および[update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドレットの動作について説明します。

@No__t-0 コマンドレットは、 **DestinationPath**パラメーターで指定されたファイル共有内のモジュールのヘルプファイルを保存するコマンドに応答して、次の操作を実行します。

1. `Save-Help` は、モジュールマニフェストの**Helpinfouri**キーの値によって指定された場所から REMOTE HelpInfo XML ファイルを取得し、スキーマに対してファイルを検証します。 (スキーマを表示するには、「 [HELPINFO XML schema](./helpinfo-xml-schema.md)」を参照してください)。次に、`Save-Help` は、`Save-Help` コマンドの**DestinationPath**パラメーターで指定されたディレクトリ内のローカル HelpInfo XML ファイルを検索します。

2. `Save-Help` は、指定された UI カルチャのヘルプファイルのバージョン番号を、モジュールのリモートおよびローカルの HelpInfo XML ファイルと比較します。 リモートファイルのバージョン番号がローカルファイルのバージョン番号よりも大きい場合、または**DestinationPath**ディレクトリにモジュール用のローカル HelpInfo XML ファイルがない場合、`Save-Help` は新しいヘルプファイルのダウンロードを準備します。

3. `Save-Help` は、リモートの HelpInfo XML ファイルの**Helpcontenturi**要素によって指定された場所からモジュールの CAB ファイルを選択します。 モジュール名、モジュール GUID、および UI カルチャを使用して、CAB ファイルを識別します。

4. `Save-Help` は CAB ファイルをダウンロードし、 **DestinationPath**ディレクトリに保存します。 (言語固有のサブディレクトリは作成されません)。

5. `Save-Help` は、リモートの HelpInfo XML ファイルをコピーすることによって、ローカルの HelpInfo XML ファイルを作成します。 ローカルの HelpInfo XML ファイルを編集して、保存された CAB ファイルの要素のみが含まれるようにします。 次に、ローカルの HelpInfo XML ファイルを**DestinationPath**ディレクトリに保存し、更新を終了します。

   @No__t-0 コマンドレットは、 **SourcePath**パラメーターで指定されたファイル共有内のファイルからユーザーのコンピューター上のヘルプファイルを更新するコマンドに応答して、次の操作を実行します。

1. `Update-Help` は、 **SourcePath**ディレクトリからリモートの HelpInfo XML ファイルを取得します。 次に、ユーザーのコンピューターのモジュールディレクトリでローカル HelpInfo XML ファイルを検索します。

2. `Update-Help` は、指定された UI カルチャのヘルプファイルのバージョン番号を、モジュールのリモートおよびローカルの HelpInfo XML ファイルと比較します。 リモートファイルのバージョン番号がローカルファイルのバージョン番号よりも大きい場合、またはローカルの HelpInfo XML ファイルがない場合は、@no__t によって新しいヘルプファイルのインストールが準備されます。

3. `Update-Help` は、 **SourcePath**ディレクトリからモジュールの CAB ファイルを選択します。 モジュール名、モジュール GUID、および UI カルチャを使用して、CAB ファイルを識別します。

4. `Update-Help` を指定すると、CAB ファイルがアンパックされ、ヘルプコンテンツファイルが検証されます。また、ヘルプコンテンツファイルは、ユーザーのコンピューターのモジュールディレクトリの言語固有のサブディレクトリに保存されます。

5. `Update-Help` は、リモートの HelpInfo XML ファイルをコピーすることによって、ローカルの HelpInfo XML ファイルを作成します。 ローカルの HelpInfo XML ファイルを編集して、インストールした CAB ファイルの要素のみが含まれるようにします。 次に、ローカルの HelpInfo XML ファイルをモジュールディレクトリに保存し、更新を終了します。