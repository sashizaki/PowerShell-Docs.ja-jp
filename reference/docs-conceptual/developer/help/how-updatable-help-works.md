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
ms.openlocfilehash: e555741185f3d17b4099671d70dbc0545bfd5306
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811501"
---
# <a name="how-updatable-help-works"></a>更新可能なヘルプのしくみ

このトピックでは、更新可能なヘルプが各モジュールの HelpInfo XML ファイルと CAB ファイルを処理し、ユーザーの更新されたヘルプをインストールする方法について説明します。

## <a name="the-update-help-process"></a>Update-help プロセス

次の一覧では、ユーザーが特定の UI カルチャのモジュールのヘルプファイルを更新するコマンドを実行したとき[の update-help コマンドレットの](/powershell/module/Microsoft.PowerShell.Core/Update-Help)動作について説明します。

1. `Update-Help`モジュールマニフェストの**Helpinfouri**キーの値によって指定された場所からリモートの HelpInfo XML ファイルを取得し、スキーマに対してファイルを検証します。 (スキーマを表示するには、「 [HELPINFO XML schema](./helpinfo-xml-schema.md)」を参照してください)。は、 `Update-Help` ユーザーのコンピューターのモジュールディレクトリにあるモジュールのローカル HELPINFO XML ファイルを検索します。

2. `Update-Help`モジュールのリモートおよびローカルの HelpInfo XML ファイル内にある、指定した UI カルチャのヘルプファイルのバージョン番号を比較します。 リモートファイルのバージョン番号がローカルファイルのバージョン番号よりも大きい場合、またはモジュールのローカル HelpInfo XML ファイルがない場合は、によって `Update-Help` 新しいヘルプファイルのダウンロードが準備されます。

3. `Update-Help`リモート HelpInfo XML ファイルの**Helpcontenturi**要素によって指定された場所からモジュールの CAB ファイルを選択します。 モジュール名、モジュール GUID、および UI カルチャを使用して、CAB ファイルを識別します。

4. `Update-Help`CAB ファイルをダウンロードしてアンパックし、ヘルプコンテンツファイルを検証して、ヘルプコンテンツファイルをユーザーのコンピューターのモジュールディレクトリの言語固有のサブディレクトリに保存します。

5. `Update-Help`リモートの HelpInfo XML ファイルをコピーすることによって、ローカルの HelpInfo XML ファイルを作成します。 ローカルの HelpInfo XML ファイルを編集して、インストールした CAB ファイルの要素のみが含まれるようにします。 次に、ローカルの HelpInfo XML ファイルをモジュールディレクトリに保存し、更新を終了します。

## <a name="the-save-help-process"></a>保存時のヘルプ

次の一覧では、ユーザーがファイル共有内のヘルプファイルを更新するコマンドを実行し、そのファイルを使用してユーザーのコンピューター上のヘルプファイルを更新するときの、 [help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)および[update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドレットの動作について説明します。

`Save-Help`コマンドレットは、 **DestinationPath**パラメーターで指定されたファイル共有内のモジュールのヘルプファイルを保存するコマンドに応答して、次の操作を実行します。

1. `Save-Help`モジュールマニフェストの**Helpinfouri**キーの値によって指定された場所からリモートの HelpInfo XML ファイルを取得し、スキーマに対してファイルを検証します。 (スキーマを表示するには、「 [HELPINFO XML schema](./helpinfo-xml-schema.md)」を参照してください)。は、 `Save-Help` コマンドで**DestinationPath**パラメーターで指定されたディレクトリでローカル HelpInfo XML ファイルを検索し `Save-Help` ます。

2. `Save-Help`モジュールのリモートおよびローカルの HelpInfo XML ファイル内にある、指定した UI カルチャのヘルプファイルのバージョン番号を比較します。 リモートファイルのバージョン番号がローカルファイルのバージョン番号よりも大きい場合、または**DestinationPath**ディレクトリにモジュール用のローカル HelpInfo XML ファイルがない場合は、によって `Save-Help` 新しいヘルプファイルのダウンロードが準備されます。

3. `Save-Help`リモート HelpInfo XML ファイルの**Helpcontenturi**要素によって指定された場所からモジュールの CAB ファイルを選択します。 モジュール名、モジュール GUID、および UI カルチャを使用して、CAB ファイルを識別します。

4. `Save-Help`CAB ファイルをダウンロードし、 **DestinationPath**ディレクトリに保存します。 (言語固有のサブディレクトリは作成されません)。

5. `Save-Help`リモートの HelpInfo XML ファイルをコピーすることによって、ローカルの HelpInfo XML ファイルを作成します。 ローカルの HelpInfo XML ファイルを編集して、保存された CAB ファイルの要素のみが含まれるようにします。 次に、ローカルの HelpInfo XML ファイルを**DestinationPath**ディレクトリに保存し、更新を終了します。

   `Update-Help`コマンドレットは、 **SourcePath**パラメーターで指定されたファイル共有内のファイルからユーザーのコンピューター上のヘルプファイルを更新するコマンドに応答して、次の操作を実行します。

1. `Update-Help`**SourcePath**ディレクトリからリモートの HelpInfo XML ファイルを取得します。 次に、ユーザーのコンピューターのモジュールディレクトリでローカル HelpInfo XML ファイルを検索します。

2. `Update-Help`モジュールのリモートおよびローカルの HelpInfo XML ファイル内にある、指定した UI カルチャのヘルプファイルのバージョン番号を比較します。 リモートファイルのバージョン番号がローカルファイルのバージョン番号よりも大きい場合、またはローカルの HelpInfo XML ファイルがない場合は、によって `Update-Help` 新しいヘルプファイルのインストールが準備されます。

3. `Update-Help`**SourcePath**ディレクトリからモジュールの CAB ファイルを選択します。 モジュール名、モジュール GUID、および UI カルチャを使用して、CAB ファイルを識別します。

4. `Update-Help`CAB ファイルをアンパックし、ヘルプコンテンツファイルを検証して、ヘルプコンテンツファイルをユーザーのコンピューターのモジュールディレクトリの言語固有のサブディレクトリに保存します。

5. `Update-Help`リモートの HelpInfo XML ファイルをコピーすることによって、ローカルの HelpInfo XML ファイルを作成します。 ローカルの HelpInfo XML ファイルを編集して、インストールした CAB ファイルの要素のみが含まれるようにします。 次に、ローカルの HelpInfo XML ファイルをモジュールディレクトリに保存し、更新を終了します。
