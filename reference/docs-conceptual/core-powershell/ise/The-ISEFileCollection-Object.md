---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "ISEFileCollection オブジェクト"
ms.assetid: 0f86a427-ea38-4bce-85f8-06c98d30d508
ms.openlocfilehash: 284891c9812a22bb1759678074dc7f967f324c0b
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="the-isefilecollection-object"></a><span data-ttu-id="8b3b3-103">ISEFileCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="8b3b3-103">The ISEFileCollection Object</span></span>
  <span data-ttu-id="8b3b3-104">**ISEFileCollection** オブジェクトは **ISEFile** オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-104">The **ISEFileCollection** object is a collection of **ISEFile** objects.</span></span> <span data-ttu-id="8b3b3-105">たとえば $psISE.CurrentPowerShellTab.Files コレクションです。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-105">An example is the $psISE.CurrentPowerShellTab.Files collection.</span></span>

## <a name="methods"></a><span data-ttu-id="8b3b3-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="8b3b3-106">Methods</span></span>

### <a name="add-fullpath-"></a><span data-ttu-id="8b3b3-107">Add\( \[fullPath\] \)</span><span class="sxs-lookup"><span data-stu-id="8b3b3-107">Add\( \[fullPath\] \)</span></span>
  <span data-ttu-id="8b3b3-108">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-108">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="8b3b3-109">新しい無題ファイルを作成して返し、コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-109">Creates and returns a new untitled file and adds it to the collection.</span></span> <span data-ttu-id="8b3b3-110">新しく作成されたファイルの **IsUntitled** プロパティは **$true** です。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-110">The **IsUntitled** property of the newly created file is **$true**.</span></span>

 <span data-ttu-id="8b3b3-111">**\[fullPath\]** - 省略可能な文字列。ファイルの完全指定パス。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-111">**\[fullPath\]** - Optional string The fully specified path of the file.</span></span> <span data-ttu-id="8b3b3-112">**fullPath** パラメーターと相対パスを含める、または完全パスではなくファイル名を使用すると、例外が生成されます。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-112">An exception is generated if you include the **fullPath** parameter and a relative path, or if you use a file name instead of the full path.</span></span>

```
# Adds a new untitled file to the collection of files in the current PowerShell tab.
$newFile = $psISE.CurrentPowerShellTab.Files.Add()

# Adds a file specified by its full path to the collection of files in the current PowerShell tab.
$psISE.CurrentPowerShellTab.Files.Add("$pshome\Examples\profile.ps1")

```

### <a name="remove-file-force-"></a><span data-ttu-id="8b3b3-113">Remove\( File, \[Force\] \)</span><span class="sxs-lookup"><span data-stu-id="8b3b3-113">Remove\( File, \[Force\] \)</span></span>
  <span data-ttu-id="8b3b3-114">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="8b3b3-115">現在の PowerShell タブから指定されたファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-115">Removes a specified file from the current PowerShell tab.</span></span>

 <span data-ttu-id="8b3b3-116">**File** - 文字列。コレクションから削除する ISEFile ファイル。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-116">**File** - String The ISEFile file that you want to remove from the collection.</span></span> <span data-ttu-id="8b3b3-117">ファイルが保存されていない場合、このメソッドにより例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-117">If the file has not been saved, this method throws an exception.</span></span> <span data-ttu-id="8b3b3-118">**Force** スイッチ パラメーターを使用すると、保存されていないファイルが強制的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-118">Use the **Force** switch parameter to force the removal of an unsaved file.</span></span>

 <span data-ttu-id="8b3b3-119">**\[Force\]** - 省略可能な Boolean。**$true** に設定すると、最後に使用してからファイルが保存されていない場合でも、そのファイルを削除する権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-119">**\[Force\]** - optional Boolean If set to **$true**, grants permission to remove the file even if it has not been saved after last use.</span></span> <span data-ttu-id="8b3b3-120">既定値は **$false** です。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-120">The default is **$false**.</span></span>

```
# Removes the first opened file from the file collection associated with the current PowerShell tab.
# If the file has not yet been saved, then an exception is generated.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.Remove($firstfile)

# Removes the first opened file from the file collection associated with the current PowerShell tab, even if it has not been saved.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.Remove($firstfile, $true)
```

### <a name="setselectedfile-selectedfile-"></a><span data-ttu-id="8b3b3-121">SetSelectedFile\( selectedFile \)</span><span class="sxs-lookup"><span data-stu-id="8b3b3-121">SetSelectedFile\( selectedFile \)</span></span>
  <span data-ttu-id="8b3b3-122">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-122">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="8b3b3-123">**selectedFile** パラメーターにより指定されたファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-123">Selects the file that is specified by the **selectedFile** parameter.</span></span>

 <span data-ttu-id="8b3b3-124">**selectedFile** - Microsoft.PowerShell.Host.ISE.ISEFile。選択する ISEFile ファイル。</span><span class="sxs-lookup"><span data-stu-id="8b3b3-124">**selectedFile** - Microsoft.PowerShell.Host.ISE.ISEFile The ISEFile file that you want to select.</span></span>

```

# Selects the specified file.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.SetSelectedFile($firstfile)

```

## <a name="see-also"></a><span data-ttu-id="8b3b3-125">参照</span><span class="sxs-lookup"><span data-stu-id="8b3b3-125">See Also</span></span>
- [<span data-ttu-id="8b3b3-126">ISEFile オブジェクト</span><span class="sxs-lookup"><span data-stu-id="8b3b3-126">The ISEFile Object</span></span>](The-ISEFile-Object.md) 
- [<span data-ttu-id="8b3b3-127">Windows PowerShell ISE スクリプト オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="8b3b3-127">The Windows PowerShell ISE Scripting Object Model</span></span>](The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
- [<span data-ttu-id="8b3b3-128">Windows PowerShell ISE オブジェクト モデル リファレンス</span><span class="sxs-lookup"><span data-stu-id="8b3b3-128">Windows PowerShell ISE Object Model Reference</span></span>](Windows-PowerShell-ISE-Object-Model-Reference.md) 
- [<span data-ttu-id="8b3b3-129">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="8b3b3-129">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)

  
