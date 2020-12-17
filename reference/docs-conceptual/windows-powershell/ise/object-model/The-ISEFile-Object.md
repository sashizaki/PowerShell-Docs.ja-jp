---
ms.date: 12/31/2019
title: ISEFile オブジェクト
description: ISEFile オブジェクトは、Windows PowerShell ISE 内のファイルを表します。
ms.openlocfilehash: b5ea70219787f254fe85d728518cbc4746c00250
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391495"
---
# <a name="the-isefile-object"></a><span data-ttu-id="b3bb7-103">ISEFile オブジェクト</span><span class="sxs-lookup"><span data-stu-id="b3bb7-103">The ISEFile Object</span></span>

<span data-ttu-id="b3bb7-104">**ISEFile** オブジェクトは、Windows PowerShell Integrated Scripting Environment (ISE) のファイルを表します。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-104">An **ISEFile** object represents a file in Windows PowerShell Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="b3bb7-105">これは **Microsoft.PowerShell.Host.ISE.ISEFile** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-105">It is an instance of the **Microsoft.PowerShell.Host.ISE.ISEFile** class.</span></span> <span data-ttu-id="b3bb7-106">このトピックでは、そのメンバー メソッドとメンバー プロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-106">This topic lists its member methods and member properties.</span></span> <span data-ttu-id="b3bb7-107">`$psISE.CurrentFile` と、PowerShell タブのファイル コレクション内のファイルは、\*\***Microsoft.PowerShell.Host.ISE.ISEFile** クラスのすべてのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-107">The `$psISE.CurrentFile` and the files in the Files collection in a PowerShell tab are all instances of the \*\*\*\*Microsoft.PowerShell.Host.ISE.ISEFile\*\* class.</span></span>

## <a name="methods"></a><span data-ttu-id="b3bb7-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="b3bb7-108">Methods</span></span>

### <a name="save-saveencoding-"></a><span data-ttu-id="b3bb7-109">Save\( \[saveEncoding\] \)</span><span class="sxs-lookup"><span data-stu-id="b3bb7-109">Save\( \[saveEncoding\] \)</span></span>

<span data-ttu-id="b3bb7-110">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b3bb7-111">ファイルをディスクに保存します。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-111">Saves the file to disk.</span></span>

<span data-ttu-id="b3bb7-112">`[saveEncoding]` - 省略可能な [System.Text.Encoding](/dotnet/api/system.text.encoding)。保存したファイルで使用する省略可能な文字エンコード パラメーター。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-112">`[saveEncoding]` - optional [System.Text.Encoding](/dotnet/api/system.text.encoding) An optional character encoding parameter to be used for the saved file.</span></span> <span data-ttu-id="b3bb7-113">既定値は **UTF8** です。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-113">The default value is **UTF8**.</span></span>

### <a name="exceptions"></a><span data-ttu-id="b3bb7-114">例外</span><span class="sxs-lookup"><span data-stu-id="b3bb7-114">Exceptions</span></span>

- <span data-ttu-id="b3bb7-115">**System.IO.IOException**: ファイルを保存できませんでした。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-115">**System.IO.IOException**: The file could not be saved.</span></span>

```powershell
# Save the file using the default encoding (UTF8)
$psISE.CurrentFile.Save()

# Save the file as ASCII.
$psISE.CurrentFile.Save([System.Text.Encoding]::ASCII)

# Gets the current encoding.
$myfile = $psISE.CurrentFile
$myfile.Encoding
```

### <a name="saveasfilename-saveencoding"></a><span data-ttu-id="b3bb7-116">SaveAs\(filename, \[saveEncoding\]\)</span><span class="sxs-lookup"><span data-stu-id="b3bb7-116">SaveAs\(filename, \[saveEncoding\]\)</span></span>

<span data-ttu-id="b3bb7-117">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-117">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b3bb7-118">指定したファイル名およびエンコードでファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-118">Saves the file with the specified file name and encoding.</span></span>

<span data-ttu-id="b3bb7-119">**filename** - ファイルを保存するために使用する名前の文字列。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-119">**filename** - String The name to be used to save the file.</span></span>

<span data-ttu-id="b3bb7-120">`[saveEncoding]` - 省略可能な [System.Text.Encoding](/dotnet/api/system.text.encoding)。保存したファイルで使用する省略可能な文字エンコード パラメーター。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-120">`[saveEncoding]` - optional [System.Text.Encoding](/dotnet/api/system.text.encoding) An optional character encoding parameter to be used for the saved file.</span></span> <span data-ttu-id="b3bb7-121">既定値は **UTF8** です。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-121">The default value is **UTF8**.</span></span>

### <a name="exceptions"></a><span data-ttu-id="b3bb7-122">例外</span><span class="sxs-lookup"><span data-stu-id="b3bb7-122">Exceptions</span></span>

- <span data-ttu-id="b3bb7-123">**System.ArgumentNullException**: **filename** パラメーターが null です。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-123">**System.ArgumentNullException**: The **filename** parameter is null.</span></span>
- <span data-ttu-id="b3bb7-124">**System.ArgumentException**: **filename** パラメータが空です。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-124">**System.ArgumentException**: The **filename** parameter is empty.</span></span>
- <span data-ttu-id="b3bb7-125">**System.IO.IOException**: ファイルを保存できませんでした。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-125">**System.IO.IOException**: The file could not be saved.</span></span>

```powershell
# Save the file with a full path and name.
$fullpath = "c:\temp\newname.txt"
$psISE.CurrentFile.SaveAs($fullPath)
# Save the file with a full path and name and explicitly as UTF8.
$psISE.CurrentFile.SaveAs($fullPath, [System.Text.Encoding]::UTF8)
```

## <a name="properties"></a><span data-ttu-id="b3bb7-126">Properties</span><span class="sxs-lookup"><span data-stu-id="b3bb7-126">Properties</span></span>

### <a name="displayname"></a><span data-ttu-id="b3bb7-127">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b3bb7-127">DisplayName</span></span>

<span data-ttu-id="b3bb7-128">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-128">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b3bb7-129">このファイルの表示名が含まれている文字列を取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-129">The read-only property that gets the string that contains the display name of this file.</span></span> <span data-ttu-id="b3bb7-130">名前は、エディターの上部の **[ファイル]** タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-130">The name is shown on the **File** tab at the top of the editor.</span></span> <span data-ttu-id="b3bb7-131">名前の末尾のアスタリスク (`(*)`) は、保存されていない変更がファイルに含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-131">The presence of an asterisk `(*)` at the end of the name indicates that the file has changes that have not been saved.</span></span>

```powershell
# Shows the display name of the file.
$psISE.CurrentFile.DisplayName
```

### <a name="editor"></a><span data-ttu-id="b3bb7-132">エディター</span><span class="sxs-lookup"><span data-stu-id="b3bb7-132">Editor</span></span>

<span data-ttu-id="b3bb7-133">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-133">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b3bb7-134">指定したファイルで使用される[エディター オブジェクト](The-ISEEditor-Object.md)を取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-134">The read-only property that gets the [editor object](The-ISEEditor-Object.md) that is used for the specified file.</span></span>

```powershell
# Gets the editor and the text.
$psISE.CurrentFile.Editor.Text
```

### <a name="encoding"></a><span data-ttu-id="b3bb7-135">エンコード</span><span class="sxs-lookup"><span data-stu-id="b3bb7-135">Encoding</span></span>

<span data-ttu-id="b3bb7-136">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-136">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b3bb7-137">元のファイル エンコードを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-137">The read-only property that gets the original file encoding.</span></span> <span data-ttu-id="b3bb7-138">これは **System.Text.Encoding** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-138">This is a **System.Text.Encoding** object.</span></span>

```powershell
# Shows the encoding for the file.
$psISE.CurrentFile.Encoding
```

### <a name="fullpath"></a><span data-ttu-id="b3bb7-139">FullPath</span><span class="sxs-lookup"><span data-stu-id="b3bb7-139">FullPath</span></span>

<span data-ttu-id="b3bb7-140">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-140">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b3bb7-141">開いているファイルの完全パスを指定する文字列を取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-141">The read-only property that gets the string that specifies the full path of the opened file.</span></span>

```powershell
# Shows the full path for the file.
$psISE.CurrentFile.FullPath
```

### <a name="issaved"></a><span data-ttu-id="b3bb7-142">IsSaved</span><span class="sxs-lookup"><span data-stu-id="b3bb7-142">IsSaved</span></span>

<span data-ttu-id="b3bb7-143">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-143">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b3bb7-144">ファイルが最後に変更された後にファイルが保存されている場合に `$true` を返す読み取り専用のブール型プロパティ。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-144">The read-only Boolean property that returns `$true` if the file has been saved after it was last modified.</span></span>

```powershell
# Determines whether the file has been saved since it was last modified.
$myfile = $psISE.CurrentFile
$myfile.IsSaved
```

### <a name="isuntitled"></a><span data-ttu-id="b3bb7-145">IsUntitled</span><span class="sxs-lookup"><span data-stu-id="b3bb7-145">IsUntitled</span></span>

<span data-ttu-id="b3bb7-146">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-146">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b3bb7-147">ファイルにタイトルが指定されたことがない場合に `$true` を返す読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="b3bb7-147">The read-only property that returns `$true` if the file has never been given a title.</span></span>

```powershell
# Determines whether the file has never been given a title.
$psISE.CurrentFile.IsUntitled
$psISE.CurrentFile.SaveAs("temp.txt")
$psISE.CurrentFile.IsUntitled
```

## <a name="see-also"></a><span data-ttu-id="b3bb7-148">参照</span><span class="sxs-lookup"><span data-stu-id="b3bb7-148">See Also</span></span>

- [<span data-ttu-id="b3bb7-149">The ISEFileCollectionObject</span><span class="sxs-lookup"><span data-stu-id="b3bb7-149">The ISEFileCollectionObject</span></span>](The-ISEFileCollection-Object.md)
- [<span data-ttu-id="b3bb7-150">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="b3bb7-150">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="b3bb7-151">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="b3bb7-151">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
