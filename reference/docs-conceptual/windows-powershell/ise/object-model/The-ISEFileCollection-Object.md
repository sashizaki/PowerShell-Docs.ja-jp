---
ms.date: 12/31/2019
title: ISEFileCollection オブジェクト
description: ISEFileCollection オブジェクトは ISEFile オブジェクトのコレクションです。
ms.openlocfilehash: 2feef1200c611d5181bcbc55d5464a0bd390084e
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646746"
---
# <a name="the-isefilecollection-object"></a><span data-ttu-id="0aece-103">ISEFileCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="0aece-103">The ISEFileCollection Object</span></span>

<span data-ttu-id="0aece-104">**ISEFileCollection** オブジェクトは **ISEFile** オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="0aece-104">The **ISEFileCollection** object is a collection of **ISEFile** objects.</span></span> <span data-ttu-id="0aece-105">例は、`$psISE.CurrentPowerShellTab.Files` コレクションです。</span><span class="sxs-lookup"><span data-stu-id="0aece-105">An example is the `$psISE.CurrentPowerShellTab.Files` collection.</span></span>

## <a name="methods"></a><span data-ttu-id="0aece-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="0aece-106">Methods</span></span>

### <a name="add-fullpath-"></a><span data-ttu-id="0aece-107">Add\( \[FullPath\] \)</span><span class="sxs-lookup"><span data-stu-id="0aece-107">Add\( \[FullPath\] \)</span></span>

<span data-ttu-id="0aece-108">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0aece-108">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="0aece-109">新しい無題ファイルを作成して返し、コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="0aece-109">Creates and returns a new untitled file and adds it to the collection.</span></span> <span data-ttu-id="0aece-110">新しく作成されたファイルの **IsUntitled** プロパティは `$true` です。</span><span class="sxs-lookup"><span data-stu-id="0aece-110">The **IsUntitled** property of the newly created file is `$true`.</span></span>

<span data-ttu-id="0aece-111">**\[FullPath\]** - 省略可能な文字列。ファイルの完全指定パス。</span><span class="sxs-lookup"><span data-stu-id="0aece-111">**\[FullPath\]** - Optional string The fully specified path of the file.</span></span> <span data-ttu-id="0aece-112">**FullPath** パラメーターと相対パスを含める、または完全パスではなくファイル名を使用すると、例外が生成されます。</span><span class="sxs-lookup"><span data-stu-id="0aece-112">An exception is generated if you include the **FullPath** parameter and a relative path, or if you use a file name instead of the full path.</span></span>

```powershell
# Adds a new untitled file to the collection of files in the current PowerShell tab.
$newFile = $psISE.CurrentPowerShellTab.Files.Add()

# Adds a file specified by its full path to the collection of files in the current PowerShell tab.
$psISE.CurrentPowerShellTab.Files.Add("$pshome\Examples\profile.ps1")
```

### <a name="remove-file-force-"></a><span data-ttu-id="0aece-113">Remove\( File, \[Force\] \)</span><span class="sxs-lookup"><span data-stu-id="0aece-113">Remove\( File, \[Force\] \)</span></span>

<span data-ttu-id="0aece-114">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0aece-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="0aece-115">現在の PowerShell タブから指定されたファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="0aece-115">Removes a specified file from the current PowerShell tab.</span></span>

<span data-ttu-id="0aece-116">**File** - 文字列。コレクションから削除する ISEFile ファイル。</span><span class="sxs-lookup"><span data-stu-id="0aece-116">**File** - String The ISEFile file that you want to remove from the collection.</span></span> <span data-ttu-id="0aece-117">ファイルが保存されていない場合、このメソッドにより例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="0aece-117">If the file has not been saved, this method throws an exception.</span></span> <span data-ttu-id="0aece-118">**Force** スイッチ パラメーターを使用すると、保存されていないファイルが強制的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="0aece-118">Use the **Force** switch parameter to force the removal of an unsaved file.</span></span>

<span data-ttu-id="0aece-119">**\[Force\]** - 省略可能な Boolean。`$true` に設定すると、最後に使用してからファイルが保存されていない場合でも、そのファイルを削除する権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="0aece-119">**\[Force\]** - optional Boolean If set to `$true`, grants permission to remove the file even if it has not been saved after last use.</span></span> <span data-ttu-id="0aece-120">既定では、 `$false`です。</span><span class="sxs-lookup"><span data-stu-id="0aece-120">The default is `$false`.</span></span>

```powershell
# Removes the first opened file from the file collection associated with the current PowerShell tab.
# If the file has not yet been saved, then an exception is generated.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.Remove($firstfile)

# Removes the first opened file from the file collection associated with the current PowerShell tab, even if it has not been saved.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.Remove($firstfile, $true)
```

### <a name="setselectedfile-selectedfile-"></a><span data-ttu-id="0aece-121">SetSelectedFile\( selectedFile \)</span><span class="sxs-lookup"><span data-stu-id="0aece-121">SetSelectedFile\( selectedFile \)</span></span>

<span data-ttu-id="0aece-122">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0aece-122">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="0aece-123">**SelectedFile** パラメーターにより指定されたファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="0aece-123">Selects the file that is specified by the **SelectedFile** parameter.</span></span>

<span data-ttu-id="0aece-124">**SelectedFile** - Microsoft.PowerShell.Host.ISE.ISEFile。選択する ISEFile ファイル。</span><span class="sxs-lookup"><span data-stu-id="0aece-124">**SelectedFile** - Microsoft.PowerShell.Host.ISE.ISEFile The ISEFile file that you want to select.</span></span>

```powershell
# Selects the specified file.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.SetSelectedFile($firstfile)
```

## <a name="see-also"></a><span data-ttu-id="0aece-125">参照</span><span class="sxs-lookup"><span data-stu-id="0aece-125">See Also</span></span>

- [<span data-ttu-id="0aece-126">ISEFile オブジェクト</span><span class="sxs-lookup"><span data-stu-id="0aece-126">The ISEFile Object</span></span>](The-ISEFile-Object.md)
- [<span data-ttu-id="0aece-127">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="0aece-127">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="0aece-128">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="0aece-128">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
