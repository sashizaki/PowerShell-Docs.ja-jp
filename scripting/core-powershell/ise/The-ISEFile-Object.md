---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "ISEFile オブジェクト"
ms.assetid: 1c6d91f3-c556-42a2-a017-79b6b7b4b7db
ms.openlocfilehash: 0e1c09c4a92868448d76cc7b4954d250773ce2f2
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="the-isefile-object"></a><span data-ttu-id="a973b-103">ISEFile オブジェクト</span><span class="sxs-lookup"><span data-stu-id="a973b-103">The ISEFile Object</span></span>
  <span data-ttu-id="a973b-104">**ISEFile** オブジェクトは、Windows PowerShell® Integrated Scripting Environment (ISE) のファイルを表します。</span><span class="sxs-lookup"><span data-stu-id="a973b-104">An **ISEFile** object represents a file in Windows PowerShell® Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="a973b-105">これは Microsoft.PowerShell.Host.ISE.ISEFile クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="a973b-105">It is an instance of the Microsoft.PowerShell.Host.ISE.ISEFile class.</span></span> <span data-ttu-id="a973b-106">このトピックでは、そのメンバー メソッドとメンバー プロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a973b-106">This topic lists its member methods and member properties.</span></span> <span data-ttu-id="a973b-107">**$PsISE.CurrentFile** と、PowerShell タブのファイル コレクション内のファイルは、Microsoft.PowerShell.Host.ISE.ISEFile クラスのすべてのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="a973b-107">The **$psISE.CurrentFile** and the files in the Files collection in a PowerShell tab are all instances of the Microsoft.PowerShell.Host.ISE.ISEFile class.</span></span>

## <a name="methods"></a><span data-ttu-id="a973b-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="a973b-108">Methods</span></span>

###  <span data-ttu-id="a973b-109"><a name="save-override"></a> Save\( \[saveEncoding\] \)</span><span class="sxs-lookup"><span data-stu-id="a973b-109"><a name="save-override"></a> Save\( \[saveEncoding\] \)</span></span>
  <span data-ttu-id="a973b-110">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a973b-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="a973b-111">ファイルをディスクに保存します。</span><span class="sxs-lookup"><span data-stu-id="a973b-111">Saves the file to disk.</span></span>

 <span data-ttu-id="a973b-112">**\[saveEncoding\]** - 省略可能な [System.Text.Encoding](http://msdn.microsoft.com/library/system.text.encoding.aspx)
。保存したファイルで使用する省略可能な文字エンコード パラメーター。</span><span class="sxs-lookup"><span data-stu-id="a973b-112">**\[saveEncoding\]** - optional [System.Text.Encoding](http://msdn.microsoft.com/library/system.text.encoding.aspx)
 An optional character encoding parameter to be used for the saved file.</span></span> <span data-ttu-id="a973b-113">既定値は **UTF8** です。</span><span class="sxs-lookup"><span data-stu-id="a973b-113">The default value is **UTF8**.</span></span>

 <span data-ttu-id="a973b-114">**例外**</span><span class="sxs-lookup"><span data-stu-id="a973b-114">**Exceptions**</span></span>
 -   <span data-ttu-id="a973b-115">**System.IO.IOException**: ファイルを保存できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a973b-115">**System.IO.IOException**: The file could not be saved.</span></span>

```
# Save the file using the default encoding (UTF8)
$psIse.CurrentFile.Save()

# Save the file as ASCII.
$psIse.CurrentFile.Save( [System.Text.Encoding]::ASCII )

# Gets the current encoding.
$myfile=$psIse.CurrentFile
$myfile.Encoding

```

###  <span data-ttu-id="a973b-116"><a name="saveas"></a> SaveAs\(filename, \[saveEncoding\]\)</span><span class="sxs-lookup"><span data-stu-id="a973b-116"><a name="saveas"></a> SaveAs\(filename, \[saveEncoding\]\)</span></span>
  <span data-ttu-id="a973b-117">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a973b-117">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="a973b-118">指定したファイル名およびエンコードでファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="a973b-118">Saves the file with the specified file name and encoding.</span></span>

 <span data-ttu-id="a973b-119">**filename** - ファイルを保存するために使用する名前の文字列。</span><span class="sxs-lookup"><span data-stu-id="a973b-119">**filename** - String The name to be used to save the file.</span></span>

 <span data-ttu-id="a973b-120">**\[saveEncoding\]** - 省略可能な [System.Text.Encoding](http://msdn.microsoft.com/library/system.text.encoding.aspx)
。保存したファイルで使用する省略可能な文字エンコード パラメーター。</span><span class="sxs-lookup"><span data-stu-id="a973b-120">**\[saveEncoding\]** - optional [System.Text.Encoding](http://msdn.microsoft.com/library/system.text.encoding.aspx)
 An optional character encoding parameter to be used for the saved file.</span></span> <span data-ttu-id="a973b-121">既定値は **UTF8** です。</span><span class="sxs-lookup"><span data-stu-id="a973b-121">The default value is **UTF8**.</span></span>

 <span data-ttu-id="a973b-122">**例外**</span><span class="sxs-lookup"><span data-stu-id="a973b-122">**Exceptions**</span></span>
 -   <span data-ttu-id="a973b-123">**System.ArgumentNullException**: **filename** パラメーターが null です。</span><span class="sxs-lookup"><span data-stu-id="a973b-123">**System.ArgumentNullException**: The **filename** parameter is null.</span></span>

-   <span data-ttu-id="a973b-124">**System.ArgumentException**: **filename** パラメータが空です。</span><span class="sxs-lookup"><span data-stu-id="a973b-124">**System.ArgumentException**: The **filename** parameter is empty.</span></span>

-   <span data-ttu-id="a973b-125">**System.IO.IOException**: ファイルを保存できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a973b-125">**System.IO.IOException**: The file could not be saved.</span></span>

```
# Save the file with a full path and name. 
$fullpath = "c:\temp\newname.txt"
$psIse.CurrentFile.SaveAs($fullPath) 
# Save the file with a full path and name and explicitly as UTF8. 
$psIse.CurrentFile.SaveAs( $fullPath, [System.Text.Encoding]::UTF8 )

```

## <a name="properties"></a><span data-ttu-id="a973b-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a973b-126">Properties</span></span>

###  <span data-ttu-id="a973b-127"><a name="Displayname"></a> DisplayName</span><span class="sxs-lookup"><span data-stu-id="a973b-127"><a name="Displayname"></a> DisplayName</span></span>
  <span data-ttu-id="a973b-128">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a973b-128">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="a973b-129">このファイルの表示名が含まれている文字列を取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="a973b-129">The read-only property that gets the string that contains the display name of this file.</span></span> <span data-ttu-id="a973b-130">名前は、エディターの上部の **[ファイル]** タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a973b-130">The name is shown on the **File** tab at the top of the editor.</span></span> <span data-ttu-id="a973b-131">名前の末尾のアスタリスク \(\*\) は、保存されていない変更がファイルに含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="a973b-131">The presence of an asterisk \(\*\) at the end of the name indicates that the file has changes that have not been saved.</span></span>

```
# Shows the display name of the file.
$psIse.CurrentFile.DisplayName

```

###  <span data-ttu-id="a973b-132"><a name="Editor"></a> Editor</span><span class="sxs-lookup"><span data-stu-id="a973b-132"><a name="Editor"></a> Editor</span></span>
  <span data-ttu-id="a973b-133">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a973b-133">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="a973b-134">指定したファイルで使用される[エディター オブジェクト](The-ISEEditor-Object.md)を取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="a973b-134">The read-only property that gets the [editor object](The-ISEEditor-Object.md) that is used for the specified file.</span></span>

```
# Gets the editor and the text.
$psIse.CurrentFile.Editor.Text

```

###  <span data-ttu-id="a973b-135"><a name="Encoding"></a> Encoding</span><span class="sxs-lookup"><span data-stu-id="a973b-135"><a name="Encoding"></a> Encoding</span></span>
  <span data-ttu-id="a973b-136">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a973b-136">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="a973b-137">元のファイル エンコードを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="a973b-137">The read-only property that gets the original file encoding.</span></span> <span data-ttu-id="a973b-138">これは **System.Text.Encoding** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="a973b-138">This is a **System.Text.Encoding** object.</span></span>

```
# Shows the encoding for the file. 
$psIse.CurrentFile.Encoding

```

###  <span data-ttu-id="a973b-139"><a name="FullPath"></a> FullPath</span><span class="sxs-lookup"><span data-stu-id="a973b-139"><a name="FullPath"></a> FullPath</span></span>
  <span data-ttu-id="a973b-140">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a973b-140">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="a973b-141">開いているファイルの完全パスを指定する文字列を取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a973b-141">The read-only property that gets the string that specifies the full path of the opened file.</span></span>

```
# Shows the full path for the file. 
$psIse.CurrentFile.FullPath

```

###  <span data-ttu-id="a973b-142"><a name="IsSaved"></a> IsSaved</span><span class="sxs-lookup"><span data-stu-id="a973b-142"><a name="IsSaved"></a> IsSaved</span></span>
  <span data-ttu-id="a973b-143">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a973b-143">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="a973b-144">ファイルが最後に変更された後にファイルが保存されている場合に **$true** を返す読み取り専用のブール型プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a973b-144">The read-only Boolean property that returns **$true** if the file has been saved after it was last modified.</span></span>

```
# Determines whether the file has been saved since it was last modified.
$myfile=$psIse.CurrentFile
$myfile.IsSaved

```

###  <span data-ttu-id="a973b-145"><a name="IsUntitled"></a> IsUntitled</span><span class="sxs-lookup"><span data-stu-id="a973b-145"><a name="IsUntitled"></a> IsUntitled</span></span>
  <span data-ttu-id="a973b-146">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a973b-146">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="a973b-147">ファイルにタイトルが指定されたことがない場合に **$true** を返す読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="a973b-147">The read-only property that returns **$true** if the file has never been given a title.</span></span>

```
# Determines whether the file has never been given a title.
$psISE.CurrentFile.IsUntitled
$psISE.CurrentFile.SaveAs("temp.txt")
$psISE.CurrentFile.IsUntitled

```

## <a name="see-also"></a><span data-ttu-id="a973b-148">参照</span><span class="sxs-lookup"><span data-stu-id="a973b-148">See Also</span></span>
- [<span data-ttu-id="a973b-149">The ISEFileCollectionObject</span><span class="sxs-lookup"><span data-stu-id="a973b-149">The ISEFileCollectionObject</span></span>](The-ISEFileCollection-Object.md) 
- [<span data-ttu-id="a973b-150">Windows PowerShell ISE スクリプト オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="a973b-150">The Windows PowerShell ISE Scripting Object Model</span></span>](The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
- [<span data-ttu-id="a973b-151">Windows PowerShell ISE オブジェクト モデル リファレンス</span><span class="sxs-lookup"><span data-stu-id="a973b-151">Windows PowerShell ISE Object Model Reference</span></span>](Windows-PowerShell-ISE-Object-Model-Reference.md) 
- [<span data-ttu-id="a973b-152">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="a973b-152">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)

  
