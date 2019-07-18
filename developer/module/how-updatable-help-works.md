---
title: 更新可能な方法のヘルプ Works |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7674636e-a0f2-4587-bfc5-dd3e6ce5489e
caps.latest.revision: 6
ms.openlocfilehash: 5b6ae54ee6c843996c875189b6ee553be5e4f614
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082262"
---
# <a name="how-updatable-help-works"></a>更新可能なヘルプのしくみ

このトピックでは、ファイルの各モジュールの HelpInfo XML ファイルと CAB し、インストール プロセスの更新可能なヘルプがユーザーのヘルプを更新する方法について説明します。

## <a name="the-update-help-process"></a>Update-help プロセス

次の一覧の動作の説明、 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドレットをユーザーが特定の UI カルチャでモジュールのヘルプ ファイルを更新するコマンドを実行するとします。

1. `Update-Help` 値によって指定された場所からリモートの HelpInfo XML ファイルを取得、 **HelpInfoURI**モジュール マニフェストでキーし、スキーマに対してファイルを検証します。 (スキーマを表示するには、次を参照してください[HelpInfo XML スキーマ](./helpinfo-xml-schema.md)。)。`Update-Help`モジュール ディレクトリ内のモジュールのユーザーのコンピューター上のローカル HelpInfo XML ファイルを探します。

2. `Update-Help` モジュールのリモートおよびローカルの HelpInfo XML ファイルで指定した UI カルチャのヘルプ ファイルのバージョン番号を比較します。 リモート ファイルにバージョン番号が、ローカル ファイルにバージョン番号より大きい場合、またはモジュールの HelpInfo XML ファイルをローカルがない場合`Update-Help`新しいヘルプ ファイルをダウンロードする準備を行います。

3. `Update-Help` 指定された場所から、モジュール用の CAB ファイルを選択、 **HelpContentUri**リモート HelpInfo XML ファイル内の要素。 CAB ファイルを識別するために、モジュール名、モジュールの GUID、および UI カルチャを使用します。

4. `Update-Help` CAB ファイルをダウンロード、アンパックしのヘルプ コンテンツ ファイルを検証およびユーザーのコンピューターに、モジュール ディレクトリの言語固有のサブディレクトリにヘルプ コンテンツ ファイルを保存します。

5. `Update-Help` リモートの HelpInfo XML ファイルをコピーしてローカルの HelpInfo XML ファイルを作成します。 のみにインストールされた CAB ファイルの要素が含まれるように、ローカルの HelpInfo XML ファイルを編集します。 モジュールのディレクトリにローカルの HelpInfo XML ファイルを保存し、で更新プログラムは終了です。

## <a name="the-save-help-process"></a>Save-help プロセス

次の一覧の動作の説明、 [Save-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)と[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドレットをユーザーがファイル共有では、ヘルプ ファイルを更新し、それらのファイルを使用して、ヘルプ ファイルを更新するためのコマンドを実行すると、ユーザーのコンピューター。

`Save-Help`コマンドレットで指定されているファイル共有で、モジュールのヘルプ ファイルを保存するコマンドを応答で、次の操作を実行する、 **DestinationPath**パラメーター。

1. `Save-Help` 値によって指定された場所からリモートの HelpInfo XML ファイルを取得、 **HelpInfoURI**モジュール マニフェストでキーし、スキーマに対してファイルを検証します。 (スキーマを表示するには、次を参照してください[HelpInfo XML スキーマ](./helpinfo-xml-schema.md)。)。`Save-Help`で指定されたディレクトリでローカル HelpInfo XML ファイルを検索、 **DestinationPath**パラメーター、`Save-Help`コマンド。

2. `Save-Help` モジュールのリモートおよびローカルの HelpInfo XML ファイルで指定した UI カルチャのヘルプ ファイルのバージョン番号を比較します。 リモート ファイルにバージョン番号が、ローカル ファイルにバージョン番号より大きい場合、または、モジュールの HelpInfo XML ファイルをローカルがない場合、 **DestinationPath**ディレクトリ、`Save-Help`新しいヘルプ ファイルをダウンロードする準備を行います。

3. `Save-Help` 指定された場所から、モジュール用の CAB ファイルを選択、 **HelpContentUri**リモート HelpInfo XML ファイル内の要素。 CAB ファイルを識別するために、モジュール名、モジュールの GUID、および UI カルチャを使用します。

4. `Save-Help` CAB ファイルをダウンロードしで保存、 **DestinationPath**ディレクトリ。 (これは作成されません、言語固有のサブディレクトリ。)

5. `Save-Help` リモートの HelpInfo XML ファイルをコピーしてローカルの HelpInfo XML ファイルを作成します。 のみに保存されている CAB ファイルの要素が含まれるように、ローカルの HelpInfo XML ファイルを編集します。 ローカルの HelpInfo XML ファイルを保存し、 **DestinationPath**ディレクトリ、最後に更新します。

   `Update-Help`コマンドレットで指定されているファイル共有のファイルからユーザーのコンピューター上のヘルプ ファイルを更新するコマンドに応じて、次の操作を実行します、 **SourcePath**パラメーター。

1. `Update-Help` リモートの HelpInfo XML ファイルを取得、 **SourcePath**ディレクトリ。 モジュールのディレクトリでユーザーのコンピューター上のローカル HelpInfo XML ファイルを検索します。

2. `Update-Help` モジュールのリモートおよびローカルの HelpInfo XML ファイルで指定した UI カルチャのヘルプ ファイルのバージョン番号を比較します。 リモート ファイルにバージョン番号が、ローカル ファイルにバージョン番号より大きい場合、またはローカルの HelpInfo XML ファイルがない場合`Update-Help`新しいヘルプ ファイルをインストールする準備を行います。

3. `Update-Help` モジュール用の CAB ファイルを選択します。 **SourcePath**ディレクトリ。 CAB ファイルを識別するために、モジュール名、モジュールの GUID、および UI カルチャを使用します。

4. `Update-Help` CAB ファイルをアンパック、ヘルプ コンテンツ ファイルを検証し、ユーザーのコンピューターに、モジュール ディレクトリの言語固有のサブディレクトリにヘルプ コンテンツ ファイルを保存します。

5. `Update-Help` リモートの HelpInfo XML ファイルをコピーしてローカルの HelpInfo XML ファイルを作成します。 のみにインストールされた CAB ファイルの要素が含まれるように、ローカルの HelpInfo XML ファイルを編集します。 モジュールのディレクトリにローカルの HelpInfo XML ファイルを保存し、で更新プログラムは終了です。