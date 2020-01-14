---
ms.date: 12/31/2019
keywords: powershell,コマンドレット
title: ISEFileCollection オブジェクト
ms.openlocfilehash: 4192afa9dc91d9ea4c4c084d3ba0175483620229
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736217"
---
# <a name="the-isefilecollection-object"></a>ISEFileCollection オブジェクト

**ISEFileCollection** オブジェクトは **ISEFile** オブジェクトのコレクションです。 例は、`$psISE.CurrentPowerShellTab.Files` コレクションです。

## <a name="methods"></a>メソッド

### <a name="add-fullpath-"></a>Add\( \[FullPath\] \)

Windows PowerShell ISE 2.0 以降でサポートされています。

新しい無題ファイルを作成して返し、コレクションに追加します。 新しく作成されたファイルの **IsUntitled** プロパティは `$true` です。

**\[FullPath\]** - 省略可能な文字列。ファイルの完全指定パス。 **FullPath** パラメーターと相対パスを含める、または完全パスではなくファイル名を使用すると、例外が生成されます。

```powershell
# Adds a new untitled file to the collection of files in the current PowerShell tab.
$newFile = $psISE.CurrentPowerShellTab.Files.Add()

# Adds a file specified by its full path to the collection of files in the current PowerShell tab.
$psISE.CurrentPowerShellTab.Files.Add("$pshome\Examples\profile.ps1")
```

### <a name="remove-file-force-"></a>Remove\( File, \[Force\] \)

Windows PowerShell ISE 2.0 以降でサポートされています。

現在の PowerShell タブから指定されたファイルを削除します。

**File** - 文字列。コレクションから削除する ISEFile ファイル。 ファイルが保存されていない場合、このメソッドにより例外がスローされます。 **Force** スイッチ パラメーターを使用すると、保存されていないファイルが強制的に削除されます。

**\[Force\]** - 省略可能な Boolean。`$true` に設定すると、最後に使用してからファイルが保存されていない場合でも、そのファイルを削除する権限が付与されます。 既定では、 `$false`です。

```powershell
# Removes the first opened file from the file collection associated with the current PowerShell tab.
# If the file has not yet been saved, then an exception is generated.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.Remove($firstfile)

# Removes the first opened file from the file collection associated with the current PowerShell tab, even if it has not been saved.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.Remove($firstfile, $true)
```

### <a name="setselectedfile-selectedfile-"></a>SetSelectedFile\( selectedFile \)

Windows PowerShell ISE 2.0 以降でサポートされています。

**SelectedFile** パラメーターにより指定されたファイルを選択します。

**SelectedFile** - Microsoft.PowerShell.Host.ISE.ISEFile。選択する ISEFile ファイル。

```powershell
# Selects the specified file.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.SetSelectedFile($firstfile)
```

## <a name="see-also"></a>参照

- [ISEFile オブジェクト](The-ISEFile-Object.md)
- [Windows PowerShell ISE スクリプト オブジェクト モデルの目的](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)
