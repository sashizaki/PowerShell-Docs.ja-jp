---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: ISEFileCollection オブジェクト
ms.assetid: 0f86a427-ea38-4bce-85f8-06c98d30d508
ms.openlocfilehash: eb4b2784820cbe51f662fd2fd945d8760ef9dbff
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
ms.locfileid: "30953091"
---
# <a name="the-isefilecollection-object"></a><span data-ttu-id="2baef-103">ISEFileCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="2baef-103">The ISEFileCollection Object</span></span>

<span data-ttu-id="2baef-104">**ISEFileCollection** オブジェクトは **ISEFile** オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="2baef-104">The **ISEFileCollection** object is a collection of **ISEFile** objects.</span></span> <span data-ttu-id="2baef-105">たとえば $psISE.CurrentPowerShellTab.Files コレクションです。</span><span class="sxs-lookup"><span data-stu-id="2baef-105">An example is the $psISE.CurrentPowerShellTab.Files collection.</span></span>

## <a name="methods"></a><span data-ttu-id="2baef-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="2baef-106">Methods</span></span>

### <a name="add-fullpath-"></a><span data-ttu-id="2baef-107">Add\( \[fullPath\] \)</span><span class="sxs-lookup"><span data-stu-id="2baef-107">Add\( \[fullPath\] \)</span></span>

<span data-ttu-id="2baef-108">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2baef-108">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="2baef-109">新しい無題ファイルを作成して返し、コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="2baef-109">Creates and returns a new untitled file and adds it to the collection.</span></span> <span data-ttu-id="2baef-110">新しく作成されたファイルの **IsUntitled** プロパティは **$true** です。</span><span class="sxs-lookup"><span data-stu-id="2baef-110">The **IsUntitled** property of the newly created file is **$true**.</span></span>

<span data-ttu-id="2baef-111">**\[fullPath\]** - 省略可能な文字列。ファイルの完全指定パス。</span><span class="sxs-lookup"><span data-stu-id="2baef-111">**\[fullPath\]** - Optional string The fully specified path of the file.</span></span> <span data-ttu-id="2baef-112">**fullPath** パラメーターと相対パスを含める、または完全パスではなくファイル名を使用すると、例外が生成されます。</span><span class="sxs-lookup"><span data-stu-id="2baef-112">An exception is generated if you include the **fullPath** parameter and a relative path, or if you use a file name instead of the full path.</span></span>

```powershell
# Adds a new untitled file to the collection of files in the current PowerShell tab.
$newFile = $psISE.CurrentPowerShellTab.Files.Add()

# Adds a file specified by its full path to the collection of files in the current PowerShell tab.
$psISE.CurrentPowerShellTab.Files.Add("$pshome\Examples\profile.ps1")
```

### <a name="remove-file-force-"></a><span data-ttu-id="2baef-113">Remove\( File, \[Force\] \)</span><span class="sxs-lookup"><span data-stu-id="2baef-113">Remove\( File, \[Force\] \)</span></span>

<span data-ttu-id="2baef-114">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2baef-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="2baef-115">現在の PowerShell タブから指定されたファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="2baef-115">Removes a specified file from the current PowerShell tab.</span></span>

<span data-ttu-id="2baef-116">**File** - 文字列。コレクションから削除する ISEFile ファイル。</span><span class="sxs-lookup"><span data-stu-id="2baef-116">**File** - String The ISEFile file that you want to remove from the collection.</span></span> <span data-ttu-id="2baef-117">ファイルが保存されていない場合、このメソッドにより例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="2baef-117">If the file has not been saved, this method throws an exception.</span></span> <span data-ttu-id="2baef-118">**Force** スイッチ パラメーターを使用すると、保存されていないファイルが強制的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="2baef-118">Use the **Force** switch parameter to force the removal of an unsaved file.</span></span>

<span data-ttu-id="2baef-119">**\[Force\]** - 省略可能な Boolean。**$true** に設定すると、最後に使用してからファイルが保存されていない場合でも、そのファイルを削除する権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="2baef-119">**\[Force\]** - optional Boolean If set to **$true**, grants permission to remove the file even if it has not been saved after last use.</span></span> <span data-ttu-id="2baef-120">既定値は **$false** です。</span><span class="sxs-lookup"><span data-stu-id="2baef-120">The default is **$false**.</span></span>

```powershell
# Removes the first opened file from the file collection associated with the current PowerShell tab.
# If the file has not yet been saved, then an exception is generated.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.Remove($firstfile)

# Removes the first opened file from the file collection associated with the current PowerShell tab, even if it has not been saved.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.Remove($firstfile, $true)
```

### <a name="setselectedfile-selectedfile-"></a><span data-ttu-id="2baef-121">SetSelectedFile\( selectedFile \)</span><span class="sxs-lookup"><span data-stu-id="2baef-121">SetSelectedFile\( selectedFile \)</span></span>

<span data-ttu-id="2baef-122">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2baef-122">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="2baef-123">**selectedFile** パラメーターにより指定されたファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="2baef-123">Selects the file that is specified by the **selectedFile** parameter.</span></span>

<span data-ttu-id="2baef-124">**selectedFile** - Microsoft.PowerShell.Host.ISE.ISEFile。選択する ISEFile ファイル。</span><span class="sxs-lookup"><span data-stu-id="2baef-124">**selectedFile** - Microsoft.PowerShell.Host.ISE.ISEFile The ISEFile file that you want to select.</span></span>

```powershell
# Selects the specified file.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.SetSelectedFile($firstfile)
```

## <a name="see-also"></a><span data-ttu-id="2baef-125">参照</span><span class="sxs-lookup"><span data-stu-id="2baef-125">See Also</span></span>

- [<span data-ttu-id="2baef-126">ISEFile オブジェクト</span><span class="sxs-lookup"><span data-stu-id="2baef-126">The ISEFile Object</span></span>](The-ISEFile-Object.md)
- [<span data-ttu-id="2baef-127">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="2baef-127">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="2baef-128">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="2baef-128">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)