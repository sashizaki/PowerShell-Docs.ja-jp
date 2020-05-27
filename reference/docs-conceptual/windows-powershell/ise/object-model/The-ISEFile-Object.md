---
ms.date: 12/31/2019
keywords: powershell,コマンドレット
title: ISEFile オブジェクト
ms.openlocfilehash: 1069e46aa586b8df2050129194a909b90f77b745
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809888"
---
# <a name="the-isefile-object"></a><span data-ttu-id="a6e18-103">ISEFile オブジェクト</span><span class="sxs-lookup"><span data-stu-id="a6e18-103">The ISEFile Object</span></span>

<span data-ttu-id="a6e18-104">**ISEFile** オブジェクトは、Windows PowerShell® Integrated Scripting Environment (ISE) のファイルを表します。</span><span class="sxs-lookup"><span data-stu-id="a6e18-104">An **ISEFile** object represents a file in Windows PowerShell® Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="a6e18-105">これは **Microsoft.PowerShell.Host.ISE.ISEFile** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="a6e18-105">It is an instance of the **Microsoft.PowerShell.Host.ISE.ISEFile** class.</span></span> <span data-ttu-id="a6e18-106">このトピックでは、そのメンバー メソッドとメンバー プロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a6e18-106">This topic lists its member methods and member properties.</span></span> <span data-ttu-id="a6e18-107">`$psISE.CurrentFile` と、PowerShell タブのファイル コレクション内のファイルは、\*\***Microsoft.PowerShell.Host.ISE.ISEFile** クラスのすべてのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="a6e18-107">The `$psISE.CurrentFile` and the files in the Files collection in a PowerShell tab are all instances of the \*\*\*\*Microsoft.PowerShell.Host.ISE.ISEFile\*\* class.</span></span>

## <a name="methods"></a><span data-ttu-id="a6e18-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="a6e18-108">Methods</span></span>

### <a name="save-saveencoding-"></a><span data-ttu-id="a6e18-109">Save\( \[saveEncoding\] \)</span><span class="sxs-lookup"><span data-stu-id="a6e18-109">Save\( \[saveEncoding\] \)</span></span>

<span data-ttu-id="a6e18-110">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a6e18-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="a6e18-111">ファイルをディスクに保存します。</span><span class="sxs-lookup"><span data-stu-id="a6e18-111">Saves the file to disk.</span></span>

<span data-ttu-id="a6e18-112">**\[saveEncoding\]** - 省略可能な [System.Text.Encoding](https://msdn.microsoft.com/library/system.text.encoding.aspx)。保存したファイルで使用する省略可能な文字エンコード パラメーター。</span><span class="sxs-lookup"><span data-stu-id="a6e18-112">**\[saveEncoding\]** - optional [System.Text.Encoding](https://msdn.microsoft.com/library/system.text.encoding.aspx) An optional character encoding parameter to be used for the saved file.</span></span> <span data-ttu-id="a6e18-113">既定値は **UTF8** です。</span><span class="sxs-lookup"><span data-stu-id="a6e18-113">The default value is **UTF8**.</span></span>

### <a name="exceptions"></a><span data-ttu-id="a6e18-114">例外</span><span class="sxs-lookup"><span data-stu-id="a6e18-114">Exceptions</span></span>

- <span data-ttu-id="a6e18-115">**System.IO.IOException**: ファイルを保存できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a6e18-115">**System.IO.IOException**: The file could not be saved.</span></span>

```powershell
# Save the file using the default encoding (UTF8)
$psISE.CurrentFile.Save()

# Save the file as ASCII.
$psISE.CurrentFile.Save([System.Text.Encoding]::ASCII)

# Gets the current encoding.
$myfile = $psISE.CurrentFile
$myfile.Encoding
```

### <a name="saveasfilename-saveencoding"></a><span data-ttu-id="a6e18-116">SaveAs\(filename, \[saveEncoding\]\)</span><span class="sxs-lookup"><span data-stu-id="a6e18-116">SaveAs\(filename, \[saveEncoding\]\)</span></span>

<span data-ttu-id="a6e18-117">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a6e18-117">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="a6e18-118">指定したファイル名およびエンコードでファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="a6e18-118">Saves the file with the specified file name and encoding.</span></span>

<span data-ttu-id="a6e18-119">**filename** - ファイルを保存するために使用する名前の文字列。</span><span class="sxs-lookup"><span data-stu-id="a6e18-119">**filename** - String The name to be used to save the file.</span></span>

<span data-ttu-id="a6e18-120">**\[saveEncoding\]** - 省略可能な [System.Text.Encoding](https://msdn.microsoft.com/library/system.text.encoding.aspx)。保存したファイルで使用する省略可能な文字エンコード パラメーター。</span><span class="sxs-lookup"><span data-stu-id="a6e18-120">**\[saveEncoding\]** - optional [System.Text.Encoding](https://msdn.microsoft.com/library/system.text.encoding.aspx) An optional character encoding parameter to be used for the saved file.</span></span> <span data-ttu-id="a6e18-121">既定値は **UTF8** です。</span><span class="sxs-lookup"><span data-stu-id="a6e18-121">The default value is **UTF8**.</span></span>

### <a name="exceptions"></a><span data-ttu-id="a6e18-122">例外</span><span class="sxs-lookup"><span data-stu-id="a6e18-122">Exceptions</span></span>

- <span data-ttu-id="a6e18-123">**System.ArgumentNullException**: **filename** パラメーターが null です。</span><span class="sxs-lookup"><span data-stu-id="a6e18-123">**System.ArgumentNullException**: The **filename** parameter is null.</span></span>
- <span data-ttu-id="a6e18-124">**System.ArgumentException**: **filename** パラメータが空です。</span><span class="sxs-lookup"><span data-stu-id="a6e18-124">**System.ArgumentException**: The **filename** parameter is empty.</span></span>
- <span data-ttu-id="a6e18-125">**System.IO.IOException**: ファイルを保存できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a6e18-125">**System.IO.IOException**: The file could not be saved.</span></span>

```powershell
# Save the file with a full path and name.
$fullpath = "c:\temp\newname.txt"
$psISE.CurrentFile.SaveAs($fullPath)
# Save the file with a full path and name and explicitly as UTF8.
$psISE.CurrentFile.SaveAs($fullPath, [System.Text.Encoding]::UTF8)
```

## <a name="properties"></a><span data-ttu-id="a6e18-126">Properties</span><span class="sxs-lookup"><span data-stu-id="a6e18-126">Properties</span></span>

### <a name="displayname"></a><span data-ttu-id="a6e18-127">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a6e18-127">DisplayName</span></span>

<span data-ttu-id="a6e18-128">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a6e18-128">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="a6e18-129">このファイルの表示名が含まれている文字列を取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="a6e18-129">The read-only property that gets the string that contains the display name of this file.</span></span> <span data-ttu-id="a6e18-130">名前は、エディターの上部の **[ファイル]** タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6e18-130">The name is shown on the **File** tab at the top of the editor.</span></span> <span data-ttu-id="a6e18-131">名前の末尾のアスタリスク (`(*)`) は、保存されていない変更がファイルに含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="a6e18-131">The presence of an asterisk `(*)` at the end of the name indicates that the file has changes that have not been saved.</span></span>

```powershell
# Shows the display name of the file.
$psISE.CurrentFile.DisplayName
```

### <a name="editor"></a><span data-ttu-id="a6e18-132">エディター</span><span class="sxs-lookup"><span data-stu-id="a6e18-132">Editor</span></span>

<span data-ttu-id="a6e18-133">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a6e18-133">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="a6e18-134">指定したファイルで使用される[エディター オブジェクト](The-ISEEditor-Object.md)を取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="a6e18-134">The read-only property that gets the [editor object](The-ISEEditor-Object.md) that is used for the specified file.</span></span>

```powershell
# Gets the editor and the text.
$psISE.CurrentFile.Editor.Text
```

### <a name="encoding"></a><span data-ttu-id="a6e18-135">エンコード</span><span class="sxs-lookup"><span data-stu-id="a6e18-135">Encoding</span></span>

<span data-ttu-id="a6e18-136">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a6e18-136">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="a6e18-137">元のファイル エンコードを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="a6e18-137">The read-only property that gets the original file encoding.</span></span> <span data-ttu-id="a6e18-138">これは **System.Text.Encoding** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="a6e18-138">This is a **System.Text.Encoding** object.</span></span>

```powershell
# Shows the encoding for the file.
$psISE.CurrentFile.Encoding
```

### <a name="fullpath"></a><span data-ttu-id="a6e18-139">FullPath</span><span class="sxs-lookup"><span data-stu-id="a6e18-139">FullPath</span></span>

<span data-ttu-id="a6e18-140">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a6e18-140">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="a6e18-141">開いているファイルの完全パスを指定する文字列を取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a6e18-141">The read-only property that gets the string that specifies the full path of the opened file.</span></span>

```powershell
# Shows the full path for the file.
$psISE.CurrentFile.FullPath
```

### <a name="issaved"></a><span data-ttu-id="a6e18-142">IsSaved</span><span class="sxs-lookup"><span data-stu-id="a6e18-142">IsSaved</span></span>

<span data-ttu-id="a6e18-143">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a6e18-143">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="a6e18-144">ファイルが最後に変更された後にファイルが保存されている場合に `$true` を返す読み取り専用のブール型プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a6e18-144">The read-only Boolean property that returns `$true` if the file has been saved after it was last modified.</span></span>

```powershell
# Determines whether the file has been saved since it was last modified.
$myfile = $psISE.CurrentFile
$myfile.IsSaved
```

### <a name="isuntitled"></a><span data-ttu-id="a6e18-145">IsUntitled</span><span class="sxs-lookup"><span data-stu-id="a6e18-145">IsUntitled</span></span>

<span data-ttu-id="a6e18-146">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a6e18-146">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="a6e18-147">ファイルにタイトルが指定されたことがない場合に `$true` を返す読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="a6e18-147">The read-only property that returns `$true` if the file has never been given a title.</span></span>

```powershell
# Determines whether the file has never been given a title.
$psISE.CurrentFile.IsUntitled
$psISE.CurrentFile.SaveAs("temp.txt")
$psISE.CurrentFile.IsUntitled
```

## <a name="see-also"></a><span data-ttu-id="a6e18-148">参照</span><span class="sxs-lookup"><span data-stu-id="a6e18-148">See Also</span></span>

- [<span data-ttu-id="a6e18-149">The ISEFileCollectionObject</span><span class="sxs-lookup"><span data-stu-id="a6e18-149">The ISEFileCollectionObject</span></span>](The-ISEFileCollection-Object.md)
- [<span data-ttu-id="a6e18-150">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="a6e18-150">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="a6e18-151">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="a6e18-151">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
