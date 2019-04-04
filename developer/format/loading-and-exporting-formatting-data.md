---
title: 読み込みと書式設定データをエクスポートする |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a48de31-7961-4b0e-b58b-93466e38370b
caps.latest.revision: 6
ms.openlocfilehash: 5c5168ffd74c15066b914ad1b39d9ead947c5e7f
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054188"
---
# <a name="loading-and-exporting-formatting-data"></a>書式設定データを読み込んでエクスポートする

書式設定、ファイルを作成した後は、現在のセッションにファイルを読み込むことによって、セッションの形式のデータを更新する必要があります。 (Windows PowerShell によって提供される書式設定ファイルは、現在のセッションを開いたときに登録されているスナップインによって読み込まれます)。現在のセッションの形式のデータを更新すると、Windows PowerShell は読み込まれている書式設定ファイルで定義されているビューに関連付けられた .NET オブジェクトを表示するのにデータを使用します。 現在のセッションに読み込み可能な書式設定ファイルの数に制限はありません。 書式設定データを更新するには、に加えて、書式設定ファイルには、現在のセッションで形式のデータをエクスポートできます。

## <a name="loading-format-data"></a>形式のデータの読み込み

書式設定ファイルは、次のメソッドを使用して、現在のセッションに読み込むことができます。

- 書式設定ファイルは、コマンドラインから現在のセッションにインポートできます。 使用して、 [Update-formatdata](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData)コマンドレットの次の手順で説明します。

- 書式設定、ファイルを参照するモジュール マニフェストを作成できます。 モジュールを使用すると、パッケージ配布用のファイルの書式設定することができます。 使用、 [New-modulemanifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) 、マニフェストを作成するコマンドレットと[Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレットを現在のセッションにモジュールを読み込めません。 モジュールの詳細については、[Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)を参照してください。

- 書式設定、ファイルを参照するスナップインを作成できます。 使用して、 [System.Management.Automation.PSSnapIn.Formats](/dotnet/api/System.Management.Automation.PSSnapIn.Formats)書式設定ファイルを参照します。 配布パッケージのコマンドレット モジュールと、関連付けられている書式設定の種類のファイルを使用する推奨になります。 モジュールの詳細については、[Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)を参照してください。

- コマンドをプログラムで起動するが場合、は、コマンドが実行される、実行空間の最初のセッション状態を書式設定ファイルのエントリを追加できます。 書式設定ファイルを追加するために使用する .NET 型の詳細については、次を参照してください。、 [System.Management.Automation.Runspaces.Sessionstateformatentry でしょうか。Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Runspaces.SessionStateFormatEntry)クラス。

書式設定ファイルが読み込まれるときに、内部のリストに追加されます、コマンドラインでオブジェクトを表示するときに使用するビューを決定する Windows PowerShell を使用しています。 リストの先頭に、書式設定ファイルを先頭に追加または一覧の末尾に追加することができます。 重要なは、Windows PowerShell コア コマンドレットによって返されるオブジェクトの方法を変更する場合など、定義されている既存のビューを持つオブジェクトのビューを定義する書式設定ファイルを読み込む場合は、書式設定ファイルをこの一覧に追加する場所を知る 表示されます。 オブジェクトの唯一のビューを定義する書式設定ファイルを読み込む場合は、前に説明した方法のいずれかを使用できます。  使用する必要がある、オブジェクトの別のビューを定義する書式設定ファイルを読み込む場合、 [Update-formatdata](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData)コマンドレットし、ファイル リストの先頭を先頭に追加します。

## <a name="storing-your-formatting-file"></a>書式設定、ファイルを保存します。

書式設定、ファイルが保存され、ディスク上の必要はありません。 ただし、次のフォルダーに格納することを強くお勧めします。 `user\documents\windowspowershell\`

#### <a name="loading-a-format-file-using-import-formatdata"></a>インポート FormatData を使用してフォーマット ファイルの読み込み

1. ディスクに書式設定ファイルを保存します。

2. 実行、 [Update-formatdata](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData)コマンドレットは、次のコマンドのいずれかを使用します。

   一覧の前にファイルを書式を追加するには、このコマンドを使用します。 オブジェクトの表示方法を変更する場合は、このコマンドを使用します。

   ```powershell
   Update-FormatData -PrependPath PathToFormattingFile
   ```

   リストの末尾にファイルを書式を追加するには、このコマンドを使用します。

   ```powershell
   Update-FormatData -AppendPath PathToFormattingFile
   ```

   使用してファイルを追加した後、 [Update-formatdata](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData)コマンドレット、ことはできませんファイルを削除する一覧から、セッションが開いているときにします。 書式設定ファイルを一覧から削除するセッションを閉じる必要があります。

## <a name="exporting-format-data"></a>形式のデータをエクスポートします。

ここにセクションの本文を挿入してください。
