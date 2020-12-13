---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ChildItem
ms.openlocfilehash: 0bcd46e49559ad625621a7ff81162af695f6f93c
ms.sourcegitcommit: 7f712e12ec5b3f3f3e695da804b050ea0ce58b3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "94661326"
---
# <span data-ttu-id="6555e-103">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="6555e-103">Get-ChildItem</span></span>

## <span data-ttu-id="6555e-104">概要</span><span class="sxs-lookup"><span data-stu-id="6555e-104">SYNOPSIS</span></span>

<span data-ttu-id="6555e-105">1 つ以上の指定された場所から項目および子項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="6555e-105">Gets the items and child items in one or more specified locations.</span></span>

## <span data-ttu-id="6555e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6555e-106">SYNTAX</span></span>

### <span data-ttu-id="6555e-107">項目 (既定)</span><span class="sxs-lookup"><span data-stu-id="6555e-107">Items (Default)</span></span>

```
Get-ChildItem [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>]
 [-Recurse] [-Depth <uint32>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>]
 [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]
```

### <span data-ttu-id="6555e-108">LiteralItems</span><span class="sxs-lookup"><span data-stu-id="6555e-108">LiteralItems</span></span>

```
Get-ChildItem [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>]
 [-Exclude <string[]>] [-Recurse] [-Depth <uint32>] [-Force] [-Name]
 [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden]
 [-ReadOnly] [-System] [<CommonParameters>]
```

## <span data-ttu-id="6555e-109">Description</span><span class="sxs-lookup"><span data-stu-id="6555e-109">DESCRIPTION</span></span>

<span data-ttu-id="6555e-110">`Get-ChildItem`コマンドレットは、指定された1つまたは複数の場所にある項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="6555e-110">The `Get-ChildItem` cmdlet gets the items in one or more specified locations.</span></span> <span data-ttu-id="6555e-111">項目がコンテナーの場合は、コンテナーの中にある項目 (子項目) を取得します。</span><span class="sxs-lookup"><span data-stu-id="6555e-111">If the item is a container, it gets the items inside the container, known as child items.</span></span> <span data-ttu-id="6555e-112">**再帰** パラメーターを使用すると、すべての子コンテナー内の項目を取得し、 **Depth** パラメーターを使用して再帰的なレベル数を制限できます。</span><span class="sxs-lookup"><span data-stu-id="6555e-112">You can use the **Recurse** parameter to get items in all child containers and use the **Depth** parameter to limit the number of levels to recurse.</span></span>

<span data-ttu-id="6555e-113">`Get-ChildItem` 空のディレクトリは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6555e-113">`Get-ChildItem` doesn't display empty directories.</span></span> <span data-ttu-id="6555e-114">コマンドに `Get-ChildItem` **深度** パラメーターまたは **再帰** パラメーターが含まれている場合、空のディレクトリは出力に含まれません。</span><span class="sxs-lookup"><span data-stu-id="6555e-114">When a `Get-ChildItem` command includes the **Depth** or **Recurse** parameters, empty directories aren't included in the output.</span></span>

<span data-ttu-id="6555e-115">場所は、PowerShell プロバイダーによってに公開され `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="6555e-115">Locations are exposed to `Get-ChildItem` by PowerShell providers.</span></span> <span data-ttu-id="6555e-116">場所には、ファイルシステムディレクトリ、レジストリハイブ、または証明書ストアを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6555e-116">A location can be a file system directory, registry hive, or a certificate store.</span></span> <span data-ttu-id="6555e-117">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6555e-117">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="6555e-118">例</span><span class="sxs-lookup"><span data-stu-id="6555e-118">EXAMPLES</span></span>

### <span data-ttu-id="6555e-119">例 1: ファイルシステムディレクトリから子項目を取得する</span><span class="sxs-lookup"><span data-stu-id="6555e-119">Example 1: Get child items from a file system directory</span></span>

<span data-ttu-id="6555e-120">この例では、ファイルシステムディレクトリから子項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="6555e-120">This example gets the child items from a file system directory.</span></span> <span data-ttu-id="6555e-121">ファイル名とサブディレクトリ名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6555e-121">The filenames and subdirectory names are displayed.</span></span> <span data-ttu-id="6555e-122">空の場所の場合、コマンドは出力を返さず、PowerShell プロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="6555e-122">For empty locations, the command doesn't return any output and returns to the PowerShell prompt.</span></span>

<span data-ttu-id="6555e-123">コマンドレットでは、 `Get-ChildItem` **Path** パラメーターを使用してディレクトリを指定し `C:\Test` ます。</span><span class="sxs-lookup"><span data-stu-id="6555e-123">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test`.</span></span>
<span data-ttu-id="6555e-124">`Get-ChildItem` ファイルとディレクトリを PowerShell コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="6555e-124">`Get-ChildItem` displays the files and directories in the PowerShell console.</span></span>

```powershell
Get-ChildItem -Path C:\Test
```

```Output
   Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     08:29                Logs
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

<span data-ttu-id="6555e-125">既定で `Get-ChildItem` は、モード (**属性**)、 **lastwritetime**、ファイルサイズ (**長さ**)、およびアイテムの **名前** が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="6555e-125">By default `Get-ChildItem` lists the mode (**Attributes**), **LastWriteTime**, file size (**Length**), and the **Name** of the item.</span></span> <span data-ttu-id="6555e-126">**Mode** プロパティの文字は、次のように解釈できます。</span><span class="sxs-lookup"><span data-stu-id="6555e-126">The letters in the **Mode** property can be interpreted as follows:</span></span>

- <span data-ttu-id="6555e-127">`l` リンク</span><span class="sxs-lookup"><span data-stu-id="6555e-127">`l` (link)</span></span>
- <span data-ttu-id="6555e-128">`d` 名簿</span><span class="sxs-lookup"><span data-stu-id="6555e-128">`d` (directory)</span></span>
- <span data-ttu-id="6555e-129">`a` アイテム</span><span class="sxs-lookup"><span data-stu-id="6555e-129">`a` (archive)</span></span>
- <span data-ttu-id="6555e-130">`r` (読み取り専用)</span><span class="sxs-lookup"><span data-stu-id="6555e-130">`r` (read-only)</span></span>
- <span data-ttu-id="6555e-131">`h` 表示</span><span class="sxs-lookup"><span data-stu-id="6555e-131">`h` (hidden)</span></span>
- <span data-ttu-id="6555e-132">`s` (システム)。</span><span class="sxs-lookup"><span data-stu-id="6555e-132">`s` (system).</span></span>

<span data-ttu-id="6555e-133">モードフラグの詳細については、「 [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6555e-133">For more information about the mode flags, see [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression).</span></span>

### <span data-ttu-id="6555e-134">例 2: ディレクトリ内の子項目の名前を取得する</span><span class="sxs-lookup"><span data-stu-id="6555e-134">Example 2: Get child item names in a directory</span></span>

<span data-ttu-id="6555e-135">この例では、ディレクトリ内の項目の名前のみを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="6555e-135">This example lists only the names of items in a directory.</span></span>

<span data-ttu-id="6555e-136">コマンドレットでは、 `Get-ChildItem` **Path** パラメーターを使用してディレクトリを指定し `C:\Test` ます。</span><span class="sxs-lookup"><span data-stu-id="6555e-136">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test`.</span></span> <span data-ttu-id="6555e-137">**Name** パラメーターは、指定されたパスからファイル名またはディレクトリ名のみを返します。</span><span class="sxs-lookup"><span data-stu-id="6555e-137">The **Name** parameter returns only the file or directory names from the specified path.</span></span>

```powershell
Get-ChildItem -Path C:\Test -Name
```

```Output
Logs
anotherfile.txt
Command.txt
CreateTestFile.ps1
ReadOnlyFile.txt
```

### <span data-ttu-id="6555e-138">例 3: 現在のディレクトリとサブディレクトリ内の子項目を取得する</span><span class="sxs-lookup"><span data-stu-id="6555e-138">Example 3: Get child items in the current directory and subdirectories</span></span>

<span data-ttu-id="6555e-139">この例では、現在のディレクトリとそのサブディレクトリにある .txt ファイルを表示し **ます。**</span><span class="sxs-lookup"><span data-stu-id="6555e-139">This example displays **.txt** files that are located in the current directory and its subdirectories.</span></span>

```powershell
Get-ChildItem -Path C:\Test\*.txt -Recurse -Force
```

```Output
    Directory: C:\Test\Logs\Adirectory

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 Afile4.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-a----        2/13/2019     13:26             20 LogFile4.txt

    Directory: C:\Test\Logs\Backup

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 ATextFile.txt
-a----        2/12/2019     15:50             20 LogFile3.txt

    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 Afile.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-a----        2/13/2019     13:26             20 LogFile1.txt

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

<span data-ttu-id="6555e-140">この `Get-ChildItem` コマンドレットは、 **Path** パラメーターを使用してを指定し `C:\Test\*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="6555e-140">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify `C:\Test\*.txt`.</span></span> <span data-ttu-id="6555e-141">**Path** はアスタリスク ( `*` ) ワイルドカードを使用して、ファイル名拡張子を持つすべてのファイルを指定し `.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="6555e-141">**Path** uses the asterisk (`*`) wildcard to specify all files with the filename extension `.txt`.</span></span> <span data-ttu-id="6555e-142">**再帰** パラメーターは、**ディレクトリ:** 見出しに示されているように、**パス** ディレクトリ内のサブディレクトリを検索します。</span><span class="sxs-lookup"><span data-stu-id="6555e-142">The **Recurse** parameter searches the **Path** directory its subdirectories, as shown in the **Directory:** headings.</span></span> <span data-ttu-id="6555e-143">**Force** パラメーターは、 `hiddenfile.txt` モードが **h** のなどの非表示ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="6555e-143">The **Force** parameter displays hidden files such as `hiddenfile.txt` that have a mode of **h**.</span></span>

### <span data-ttu-id="6555e-144">例 4: Include パラメーターを使用して子項目を取得する</span><span class="sxs-lookup"><span data-stu-id="6555e-144">Example 4: Get child items using the Include parameter</span></span>

<span data-ttu-id="6555e-145">この例では、 `Get-ChildItem` **Include** パラメーターを使用して、 **Path** パラメーターで指定されたディレクトリから特定の項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="6555e-145">In this example `Get-ChildItem` uses the **Include** parameter to find specific items from the directory specified by the **Path** parameter.</span></span>

```powershell
# When using the -Include parameter, if you don't include an asterisk in the path
# the command returns no output.
Get-ChildItem -Path C:\Test\ -Include *.txt
```

```Output

```

```powershell
Get-ChildItem -Path C:\Test\* -Include *.txt
```

```Output
    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

<span data-ttu-id="6555e-146">この `Get-ChildItem` コマンドレットでは、 **Path** パラメーターを使用して、ディレクトリ **C:\Test** を指定します。</span><span class="sxs-lookup"><span data-stu-id="6555e-146">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory **C:\Test**.</span></span> <span data-ttu-id="6555e-147">**Path** パラメーターには、ディレクトリの内容を指定するための末尾のアスタリスク () ワイルドカードが含まれてい `*` ます。</span><span class="sxs-lookup"><span data-stu-id="6555e-147">The **Path** parameter includes a trailing asterisk (`*`) wildcard to specify the directory's contents.</span></span>
<span data-ttu-id="6555e-148">**Include** パラメーターでは、アスタリスク ( `*` ) ワイルドカードを使用して、ファイル名拡張子 **.txt** を持つすべてのファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="6555e-148">The **Include** parameter uses an asterisk (`*`) wildcard to specify all files with the file name extension **.txt**.</span></span>

<span data-ttu-id="6555e-149">**Include** パラメーターを使用する場合、 **Path** パラメーターには、 `*` ディレクトリの内容を指定するための末尾のアスタリスク () ワイルドカードが必要です。</span><span class="sxs-lookup"><span data-stu-id="6555e-149">When the **Include** parameter is used, the **Path** parameter needs a trailing asterisk (`*`) wildcard to specify the directory's contents.</span></span> <span data-ttu-id="6555e-150">たとえば、「 `-Path C:\Test\*` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6555e-150">For example, `-Path C:\Test\*`.</span></span>

- <span data-ttu-id="6555e-151">**再帰** パラメーターがコマンドに追加された場合、Path パラメーターの末尾のアスタリスク ( `*` ) は省略可能です。 </span><span class="sxs-lookup"><span data-stu-id="6555e-151">If the **Recurse** parameter is added to the command, the trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="6555e-152">**再帰** パラメーターは、**パス** ディレクトリとそのサブディレクトリから項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="6555e-152">The **Recurse** parameter gets items from the **Path** directory and its subdirectories.</span></span> <span data-ttu-id="6555e-153">たとえば、`-Path C:\Test\ -Recurse -Include *.txt` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="6555e-153">For example, `-Path C:\Test\ -Recurse -Include *.txt`</span></span>
- <span data-ttu-id="6555e-154">パスパラメーターに末尾のアスタリスク () が含まれていない場合 `*` 、コマンドは出力を返さず、PowerShell プロンプトに戻ります。 </span><span class="sxs-lookup"><span data-stu-id="6555e-154">If a trailing asterisk (`*`) isn't included in the **Path** parameter, the command doesn't return any output and returns to the PowerShell prompt.</span></span> <span data-ttu-id="6555e-155">たとえば、「 `-Path C:\Test\` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6555e-155">For example, `-Path C:\Test\`.</span></span>

### <span data-ttu-id="6555e-156">例 5: Exclude パラメーターを使用して子項目を取得する</span><span class="sxs-lookup"><span data-stu-id="6555e-156">Example 5: Get child items using the Exclude parameter</span></span>

<span data-ttu-id="6555e-157">この例の出力は、ディレクトリ **C:\Test\Logs** の内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="6555e-157">The example's output shows the contents of the directory **C:\Test\Logs**.</span></span> <span data-ttu-id="6555e-158">出力は、 **Exclude** および **再帰** パラメーターを使用する他のコマンドの参照です。</span><span class="sxs-lookup"><span data-stu-id="6555e-158">The output is a reference for the other commands that use the **Exclude** and **Recurse** parameters.</span></span>

```powershell
Get-ChildItem -Path C:\Test\Logs
```

```Output
    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     13:21                Adirectory
d-----        2/15/2019     08:28                AnEmptyDirectory
d-----        2/15/2019     13:21                Backup
-a----        2/12/2019     16:16             20 Afile.txt
-a----        2/13/2019     13:26             20 LogFile1.txt
-a----        2/12/2019     16:24             23 systemlog1.log
```

```powershell
Get-ChildItem -Path C:\Test\Logs\* -Exclude A*
```

```Output
    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     13:21                Backup
-a----        2/13/2019     13:26             20 LogFile1.txt
-a----        2/12/2019     16:24             23 systemlog1.log
```

<span data-ttu-id="6555e-159">コマンドレットでは、 `Get-ChildItem` **Path** パラメーターを使用してディレクトリを指定し `C:\Test\Logs` ます。</span><span class="sxs-lookup"><span data-stu-id="6555e-159">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test\Logs`.</span></span>
<span data-ttu-id="6555e-160">**Exclude** パラメーターでは、アスタリスク () ワイルドカードを使用して、 `*` またはで始まる任意のファイルまたはディレクトリを出力から除外します。 </span><span class="sxs-lookup"><span data-stu-id="6555e-160">The **Exclude** parameter uses the asterisk (`*`) wildcard to specify any files or directories that begin with **A** or **a** are excluded from the output.</span></span>

<span data-ttu-id="6555e-161">**Exclude** パラメーターを使用する場合、Path パラメーターの末尾のアスタリスク ( `*` ) は省略可能です。 </span><span class="sxs-lookup"><span data-stu-id="6555e-161">When the **Exclude** parameter is used, a trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="6555e-162">たとえば、`-Path C:\Test\Logs` または `-Path C:\Test\Logs\*` です。</span><span class="sxs-lookup"><span data-stu-id="6555e-162">For example, `-Path C:\Test\Logs` or `-Path C:\Test\Logs\*`.</span></span>

- <span data-ttu-id="6555e-163">Path パラメーターに末尾のアスタリスク ( `*` ) が含まれていない場合は、 **path** パラメーターの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6555e-163">If a trailing asterisk (`*`) isn't included in the **Path** parameter, the contents of the **Path** parameter are displayed.</span></span> <span data-ttu-id="6555e-164">例外は、 **Exclude** パラメーターの値と一致するファイル名またはサブディレクトリ名です。</span><span class="sxs-lookup"><span data-stu-id="6555e-164">The exceptions are filenames or subdirectory names that match the **Exclude** parameter's value.</span></span>
- <span data-ttu-id="6555e-165">Path パラメーターに末尾のアスタリスク ( `*` ) が含まれている場合、コマンドは **path** パラメーターのサブディレクトリに繰り返しします。</span><span class="sxs-lookup"><span data-stu-id="6555e-165">If a trailing asterisk (`*`) is included in the **Path** parameter, the command recurses into the **Path** parameter's subdirectories.</span></span> <span data-ttu-id="6555e-166">例外は、 **Exclude** パラメーターの値と一致するファイル名またはサブディレクトリ名です。</span><span class="sxs-lookup"><span data-stu-id="6555e-166">The exceptions are filenames or subdirectory names that match the **Exclude** parameter's value.</span></span>
- <span data-ttu-id="6555e-167">**再帰パラメーターが** コマンドに追加された場合、 **Path** パラメーターに末尾のアスタリスク () が含まれているかどうかにかかわらず、再帰の出力は同じに `*` なります。</span><span class="sxs-lookup"><span data-stu-id="6555e-167">If the **Recurse** parameter is added to the command, the recursion output is the same whether or not the **Path** parameter includes a trailing asterisk (`*`).</span></span>

### <span data-ttu-id="6555e-168">例 6: レジストリハイブからレジストリキーを取得する</span><span class="sxs-lookup"><span data-stu-id="6555e-168">Example 6: Get the registry keys from a registry hive</span></span>

<span data-ttu-id="6555e-169">この例では、からすべてのレジストリキーを取得し `HKEY_LOCAL_MACHINE\HARDWARE` ます。</span><span class="sxs-lookup"><span data-stu-id="6555e-169">This example gets all the registry keys from `HKEY_LOCAL_MACHINE\HARDWARE`.</span></span>

<span data-ttu-id="6555e-170">`Get-ChildItem`**Path** パラメーターを使用して、レジストリキーを指定し `HKLM:\HARDWARE` ます。</span><span class="sxs-lookup"><span data-stu-id="6555e-170">`Get-ChildItem` uses the **Path** parameter to specify the registry key `HKLM:\HARDWARE`.</span></span> <span data-ttu-id="6555e-171">PowerShell コンソールには、ハイブのパスとレジストリキーの最上位レベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6555e-171">The hive's path and top level of registry keys are displayed in the PowerShell console.</span></span>

<span data-ttu-id="6555e-172">詳細については、「 [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6555e-172">For more information, see [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md).</span></span>

```powershell
Get-ChildItem -Path HKLM:\HARDWARE
```

```Output
    Hive: HKEY_LOCAL_MACHINE\HARDWARE

Name             Property
----             --------
ACPI
DESCRIPTION
DEVICEMAP
RESOURCEMAP
UEFI
```

```powershell
Get-ChildItem -Path HKLM:\HARDWARE -Exclude D*
```

```Output
   Hive: HKEY_LOCAL_MACHINE\HARDWARE

Name                           Property
----                           --------
ACPI
RESOURCEMAP
```

<span data-ttu-id="6555e-173">最初のコマンドは、レジストリキーの内容を表示し `HKLM:\HARDWARE` ます。</span><span class="sxs-lookup"><span data-stu-id="6555e-173">The first command shows the contents of the `HKLM:\HARDWARE` registry key.</span></span> <span data-ttu-id="6555e-174">**Exclude** パラメーターは、 `Get-ChildItem` で始まるサブキーを返さないように指示 `D*` します。</span><span class="sxs-lookup"><span data-stu-id="6555e-174">The **Exclude** parameter tells `Get-ChildItem` not to return any subkeys that start with `D*`.</span></span> <span data-ttu-id="6555e-175">現在、 **Exclude** パラメーターは、項目のプロパティではなく、サブキーに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="6555e-175">Currently, the **Exclude** parameter only works on subkeys, not item properties.</span></span>

### <span data-ttu-id="6555e-176">例 7: コード署名権限を持つすべての証明書を取得する</span><span class="sxs-lookup"><span data-stu-id="6555e-176">Example 7: Get all certificates with code-signing authority</span></span>

<span data-ttu-id="6555e-177">この例では、コード署名権限を持つ、PowerShell **Cert:** ドライブ内の各証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="6555e-177">This example gets each certificate in the PowerShell **Cert:** drive that has code-signing authority.</span></span>

<span data-ttu-id="6555e-178">コマンドレットでは、 `Get-ChildItem` **Path** パラメーターを使用して **Cert:** provider を指定します。</span><span class="sxs-lookup"><span data-stu-id="6555e-178">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the **Cert:** provider.</span></span> <span data-ttu-id="6555e-179">**再帰** パラメーターは、 **Path** とそのサブディレクトリで指定されたディレクトリを検索します。</span><span class="sxs-lookup"><span data-stu-id="6555e-179">The **Recurse** parameter searches the directory specified by **Path** and its subdirectories.</span></span> <span data-ttu-id="6555e-180">**Codesigningcert** パラメーターは、コード署名権限を持つ証明書のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="6555e-180">The **CodeSigningCert** parameter gets only certificates that have code-signing authority.</span></span>

```powershell
Get-ChildItem -Path Cert:\* -Recurse -CodeSigningCert
```

<span data-ttu-id="6555e-181">証明書プロバイダーと Cert: ドライブの詳細については、「 [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6555e-181">For more information about the Certificate provider and the Cert: drive, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

### <span data-ttu-id="6555e-182">例 8: Depth パラメーターを使用して項目を取得する</span><span class="sxs-lookup"><span data-stu-id="6555e-182">Example 8: Get items using the Depth parameter</span></span>

<span data-ttu-id="6555e-183">この例では、ディレクトリとそのサブディレクトリ内の項目を表示します。</span><span class="sxs-lookup"><span data-stu-id="6555e-183">This example displays the items in a directory and its subdirectories.</span></span> <span data-ttu-id="6555e-184">**Depth** パラメーターは、再帰に含めるサブディレクトリレベルの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="6555e-184">The **Depth** parameter determines the number of subdirectory levels to include in the recursion.</span></span> <span data-ttu-id="6555e-185">空のディレクトリは、出力から除外されます。</span><span class="sxs-lookup"><span data-stu-id="6555e-185">Empty directories are excluded from the output.</span></span>

```powershell
Get-ChildItem -Path C:\Parent -Depth 2
```

```Output
    Directory: C:\Parent

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:24                SubDir_Level1
-a----        2/13/2019     08:55             26 file.txt

    Directory: C:\Parent\SubDir_Level1

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:24                SubDir_Level2
-a----        2/13/2019     08:55             26 file.txt

    Directory: C:\Parent\SubDir_Level1\SubDir_Level2

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:22                SubDir_Level3
-a----        2/13/2019     08:55             26 file.txt
```

<span data-ttu-id="6555e-186">この `Get-ChildItem` コマンドレットは、 **path** パラメーターを使用して、 **c:\ 親** を指定します。</span><span class="sxs-lookup"><span data-stu-id="6555e-186">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify **C:\Parent**.</span></span> <span data-ttu-id="6555e-187">**Depth** パラメーターでは、2つのレベルの再帰が指定されています。</span><span class="sxs-lookup"><span data-stu-id="6555e-187">The **Depth** parameter specifies two levels of recursion.</span></span> <span data-ttu-id="6555e-188">`Get-ChildItem`**Path** パラメーターで指定したディレクトリの内容と、サブディレクトリの2つのレベルを表示します。</span><span class="sxs-lookup"><span data-stu-id="6555e-188">`Get-ChildItem` displays the contents of the directory specified by the **Path** parameter and the two levels of subdirectories.</span></span>

### <span data-ttu-id="6555e-189">例 9: ハードリンク情報を取得する</span><span class="sxs-lookup"><span data-stu-id="6555e-189">Example 9: Getting hard link information</span></span>

<span data-ttu-id="6555e-190">PowerShell 6.2 では、ハードリンク情報を取得するために代替ビューが追加されました。</span><span class="sxs-lookup"><span data-stu-id="6555e-190">In PowerShell 6.2, an alternate view was added to get hard link information.</span></span>

```powershell
Get-ChildItem -Path C:\PathContainingHardLink | Format-Table -View childrenWithHardLink
```

### <span data-ttu-id="6555e-191">例 9: Windows 以外のオペレーティングシステムの出力</span><span class="sxs-lookup"><span data-stu-id="6555e-191">Example 9: Output for Non-Windows Operating Systems</span></span>

<span data-ttu-id="6555e-192">Unix システムの PowerShell 7.1 では、は `Get-ChildItem` unix に似た出力を提供します。</span><span class="sxs-lookup"><span data-stu-id="6555e-192">In PowerShell 7.1 on Unix systems, the `Get-ChildItem` provides Unix-like output:</span></span>

```powershell
PS> Get-ChildItem /etc/r*
```

```Output
    Directory: /etc

UnixMode   User Group    LastWriteTime Size Name
--------   ---- -----    ------------- ---- ----
drwxr-xr-x root wheel  9/30/2019 19:19  128 racoon
-rw-r--r-- root wheel  9/26/2019 18:20 1560 rc.common
-rw-r--r-- root wheel  7/31/2017 17:30 1560 rc.common~previous
-rw-r--r-- root wheel  9/27/2019 20:34 5264 rc.netboot
lrwxr-xr-x root wheel  11/8/2019 15:35   22 resolv.conf -> /private/var/run/resolv.conf
-rw-r--r-- root wheel 10/23/2019 17:41    0 rmtab
-rw-r--r-- root wheel 10/23/2019 17:41 1735 rpc
-rw-r--r-- root wheel  7/25/2017 18:37 1735 rpc~previous
-rw-r--r-- root wheel 10/23/2019 18:42  891 rtadvd.conf
-rw-r--r-- root wheel  8/24/2017 21:54  891 rtadvd.conf~previous
```

<span data-ttu-id="6555e-193">出力の一部である新しいプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6555e-193">The new properties that are now part of the output are:</span></span>

- <span data-ttu-id="6555e-194">**UnixMode** は、Unix システムで表されるファイルのアクセス許可です。</span><span class="sxs-lookup"><span data-stu-id="6555e-194">**UnixMode** is the file permissions as represented on a Unix system</span></span>
- <span data-ttu-id="6555e-195">**ユーザー** はファイルの所有者です</span><span class="sxs-lookup"><span data-stu-id="6555e-195">**User** is the file owner</span></span>
- <span data-ttu-id="6555e-196">**グループは** グループの所有者です</span><span class="sxs-lookup"><span data-stu-id="6555e-196">**Group** is the group owner</span></span>
- <span data-ttu-id="6555e-197">**サイズ** は、Unix システムで表されるファイルまたはディレクトリのサイズです。</span><span class="sxs-lookup"><span data-stu-id="6555e-197">**Size** is the size of the file or directory as represented on a Unix system</span></span>

> [!NOTE]
> <span data-ttu-id="6555e-198">この機能は、PowerShell 7.1 の試験段階からメインストリームに移行されました。</span><span class="sxs-lookup"><span data-stu-id="6555e-198">This feature was moved from experimental to mainstream in PowerShell 7.1.</span></span>

## <span data-ttu-id="6555e-199">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6555e-199">Parameters</span></span>

### <span data-ttu-id="6555e-200">-属性</span><span class="sxs-lookup"><span data-stu-id="6555e-200">-Attributes</span></span>

<span data-ttu-id="6555e-201">指定した属性のファイルとフォルダーを取得します。</span><span class="sxs-lookup"><span data-stu-id="6555e-201">Gets files and folders with the specified attributes.</span></span> <span data-ttu-id="6555e-202">このパラメーターはすべての属性をサポートします。複雑な属性の組み合わせを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6555e-202">This parameter supports all attributes and lets you specify complex combinations of attributes.</span></span>

<span data-ttu-id="6555e-203">たとえば、暗号化または圧縮されている非システム ファイル (非ディレクトリ) を取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6555e-203">For example, to get non-system files (not directories) that are encrypted or compressed, type:</span></span>

`Get-ChildItem -Attributes !Directory+!System+Encrypted, !Directory+!System+Compressed`

<span data-ttu-id="6555e-204">よく使用される属性を持つファイルとフォルダーを検索するには、 **attributes** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6555e-204">To find files and folders with commonly used attributes, use the **Attributes** parameter.</span></span> <span data-ttu-id="6555e-205">または、パラメーター **Directory**、 **File**、 **Hidden**、 **ReadOnly**、および **System** です。</span><span class="sxs-lookup"><span data-stu-id="6555e-205">Or, the parameters **Directory**, **File**, **Hidden**, **ReadOnly**, and **System**.</span></span>

<span data-ttu-id="6555e-206">**Attributes** パラメーターでは、次のプロパティがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6555e-206">The **Attributes** parameter supports the following properties:</span></span>

- <span data-ttu-id="6555e-207">**Archive**</span><span class="sxs-lookup"><span data-stu-id="6555e-207">**Archive**</span></span>
- <span data-ttu-id="6555e-208">**Compressed**</span><span class="sxs-lookup"><span data-stu-id="6555e-208">**Compressed**</span></span>
- <span data-ttu-id="6555e-209">**[デバイス]**</span><span class="sxs-lookup"><span data-stu-id="6555e-209">**Device**</span></span>
- <span data-ttu-id="6555e-210">**ディレクトリ**</span><span class="sxs-lookup"><span data-stu-id="6555e-210">**Directory**</span></span>
- <span data-ttu-id="6555e-211">**Encrypted**</span><span class="sxs-lookup"><span data-stu-id="6555e-211">**Encrypted**</span></span>
- <span data-ttu-id="6555e-212">**[非表示]**</span><span class="sxs-lookup"><span data-stu-id="6555e-212">**Hidden**</span></span>
- <span data-ttu-id="6555e-213">**IntegrityStream**</span><span class="sxs-lookup"><span data-stu-id="6555e-213">**IntegrityStream**</span></span>
- <span data-ttu-id="6555e-214">**標準**</span><span class="sxs-lookup"><span data-stu-id="6555e-214">**Normal**</span></span>
- <span data-ttu-id="6555e-215">**NoScrubData**</span><span class="sxs-lookup"><span data-stu-id="6555e-215">**NoScrubData**</span></span>
- <span data-ttu-id="6555e-216">**NotContentIndexed**</span><span class="sxs-lookup"><span data-stu-id="6555e-216">**NotContentIndexed**</span></span>
- <span data-ttu-id="6555e-217">**オフライン**</span><span class="sxs-lookup"><span data-stu-id="6555e-217">**Offline**</span></span>
- <span data-ttu-id="6555e-218">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="6555e-218">**ReadOnly**</span></span>
- <span data-ttu-id="6555e-219">**ReparsePoint**</span><span class="sxs-lookup"><span data-stu-id="6555e-219">**ReparsePoint**</span></span>
- <span data-ttu-id="6555e-220">**Sparc ファイル**</span><span class="sxs-lookup"><span data-stu-id="6555e-220">**SparseFile**</span></span>
- <span data-ttu-id="6555e-221">**システム**</span><span class="sxs-lookup"><span data-stu-id="6555e-221">**System**</span></span>
- <span data-ttu-id="6555e-222">**一時**</span><span class="sxs-lookup"><span data-stu-id="6555e-222">**Temporary**</span></span>

<span data-ttu-id="6555e-223">これらの属性の詳細については、「 [Fileattributes 列挙型](/dotnet/api/system.io.fileattributes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6555e-223">For a description of these attributes, see the [FileAttributes Enumeration](/dotnet/api/system.io.fileattributes).</span></span>

<span data-ttu-id="6555e-224">属性を結合するには、次の演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="6555e-224">To combine attributes, use the following operators:</span></span>

- <span data-ttu-id="6555e-225">`!` 非</span><span class="sxs-lookup"><span data-stu-id="6555e-225">`!` (NOT)</span></span>
- <span data-ttu-id="6555e-226">`+` と</span><span class="sxs-lookup"><span data-stu-id="6555e-226">`+` (AND)</span></span>
- <span data-ttu-id="6555e-227">`,` もしくは</span><span class="sxs-lookup"><span data-stu-id="6555e-227">`,` (OR)</span></span>

<span data-ttu-id="6555e-228">演算子とその属性の間にはスペースを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6555e-228">Don't use spaces between an operator and its attribute.</span></span> <span data-ttu-id="6555e-229">コンマの後にスペースを入れることができます。</span><span class="sxs-lookup"><span data-stu-id="6555e-229">Spaces are accepted after commas.</span></span>

<span data-ttu-id="6555e-230">共通属性の場合は、次の省略形を使用します。</span><span class="sxs-lookup"><span data-stu-id="6555e-230">For common attributes, use the following abbreviations:</span></span>

- <span data-ttu-id="6555e-231">`D` 名簿</span><span class="sxs-lookup"><span data-stu-id="6555e-231">`D` (Directory)</span></span>
- <span data-ttu-id="6555e-232">`H` 表示</span><span class="sxs-lookup"><span data-stu-id="6555e-232">`H` (Hidden)</span></span>
- <span data-ttu-id="6555e-233">`R` (読み取り専用)</span><span class="sxs-lookup"><span data-stu-id="6555e-233">`R` (Read-only)</span></span>
- <span data-ttu-id="6555e-234">`S` (システム)</span><span class="sxs-lookup"><span data-stu-id="6555e-234">`S` (System)</span></span>

```yaml
Type: System.Management.Automation.FlagsExpression`1[System.IO.FileAttributes]
Parameter Sets: (All)
Aliases:
Accepted values: Archive, Compressed, Device, Directory, Encrypted, Hidden, IntegrityStream, Normal, NoScrubData, NotContentIndexed, Offline, ReadOnly, ReparsePoint, SparseFile, System, Temporary

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6555e-235">-深さ</span><span class="sxs-lookup"><span data-stu-id="6555e-235">-Depth</span></span>

<span data-ttu-id="6555e-236">このパラメーターは、PowerShell 5.0 で追加され、再帰の深さを制御できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6555e-236">This parameter was added in PowerShell 5.0 and enables you to control the depth of recursion.</span></span> <span data-ttu-id="6555e-237">既定では、 `Get-ChildItem` 親ディレクトリの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6555e-237">By default, `Get-ChildItem` displays the contents of the parent directory.</span></span> <span data-ttu-id="6555e-238">**Depth** パラメーターは、再帰に含まれるサブディレクトリレベルの数を決定し、その内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="6555e-238">The **Depth** parameter determines the number of subdirectory levels that are included in the recursion and displays the contents.</span></span>

<span data-ttu-id="6555e-239">たとえば、には、 `Depth 2` **パス** パラメーターのディレクトリ、サブディレクトリの最初のレベル、およびサブディレクトリの第2レベルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6555e-239">For example, `Depth 2` includes the **Path** parameter's directory, first level of subdirectories, and second level of subdirectories.</span></span> <span data-ttu-id="6555e-240">既定では、ディレクトリ名とファイル名が出力に含まれます。</span><span class="sxs-lookup"><span data-stu-id="6555e-240">By default directory names and filenames are included in the output.</span></span>

> [!NOTE]
> <span data-ttu-id="6555e-241">PowerShell または **cmd.exe** の Windows コンピューターでは、 **tree.com** コマンドを使用してディレクトリ構造のグラフィカルビューを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6555e-241">On a Windows computer from PowerShell or **cmd.exe**, you can display a graphical view of a directory structure with the **tree.com** command.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6555e-242">-Directory</span><span class="sxs-lookup"><span data-stu-id="6555e-242">-Directory</span></span>

<span data-ttu-id="6555e-243">ディレクトリの一覧を取得するには、 **directory パラメーターまた** は **Attributes** パラメーターを **directory** プロパティと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="6555e-243">To get a list of directories, use the **Directory** parameter or the **Attributes** parameter with the **Directory** property.</span></span> <span data-ttu-id="6555e-244">**再帰** パラメーターは **ディレクトリ** と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="6555e-244">You can use the **Recurse** parameter with **Directory**.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ad, d

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6555e-245">-除外</span><span class="sxs-lookup"><span data-stu-id="6555e-245">-Exclude</span></span>

<span data-ttu-id="6555e-246">このコマンドレットによって操作から除外されるプロパティまたはプロパティを、文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="6555e-246">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="6555e-247">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="6555e-247">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="6555e-248">パス要素またはパターン (やなど) を入力し `*.txt` `A*` ます。</span><span class="sxs-lookup"><span data-stu-id="6555e-248">Enter a path element or pattern, such as `*.txt` or `A*`.</span></span> <span data-ttu-id="6555e-249">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6555e-249">Wildcard characters are accepted.</span></span>

<span data-ttu-id="6555e-250">Path パラメーターの末尾のアスタリスク ( `*` ) は省略可能です。 </span><span class="sxs-lookup"><span data-stu-id="6555e-250">A trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="6555e-251">たとえば、`-Path C:\Test\Logs` または `-Path C:\Test\Logs\*` です。</span><span class="sxs-lookup"><span data-stu-id="6555e-251">For example, `-Path C:\Test\Logs` or `-Path C:\Test\Logs\*`.</span></span> <span data-ttu-id="6555e-252">末尾のアスタリスク ( `*` ) が含まれている場合、コマンドは **Path** パラメーターのサブディレクトリに繰り返しします。</span><span class="sxs-lookup"><span data-stu-id="6555e-252">If a trailing asterisk (`*`) is included, the command recurses into the **Path** parameter's subdirectories.</span></span> <span data-ttu-id="6555e-253">アスタリスク () がない `*` 場合は、 **Path** パラメーターの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6555e-253">Without the asterisk (`*`), the contents of the **Path** parameter are displayed.</span></span> <span data-ttu-id="6555e-254">詳細については、例5とメモのセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6555e-254">More details are included in Example 5 and the Notes section.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="6555e-255">-File</span><span class="sxs-lookup"><span data-stu-id="6555e-255">-File</span></span>

<span data-ttu-id="6555e-256">ファイルの一覧を取得するには、 **File** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6555e-256">To get a list of files, use the **File** parameter.</span></span> <span data-ttu-id="6555e-257">**ファイル** では、**再帰** パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6555e-257">You can use the **Recurse** parameter with **File**.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: af

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6555e-258">-Filter</span><span class="sxs-lookup"><span data-stu-id="6555e-258">-Filter</span></span>

<span data-ttu-id="6555e-259">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="6555e-259">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="6555e-260">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターをサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="6555e-260">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="6555e-261">フィルターは他のパラメーターよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="6555e-261">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="6555e-262">プロバイダーは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得したときにフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="6555e-262">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="6555e-263">フィルター文字列は、ファイルを列挙するために .NET API に渡されます。</span><span class="sxs-lookup"><span data-stu-id="6555e-263">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="6555e-264">API では、とのワイルドカードのみがサポートさ `*` `?` れています。</span><span class="sxs-lookup"><span data-stu-id="6555e-264">The API only supports `*` and `?` wildcards.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="6555e-265">-のシンボリックリンク</span><span class="sxs-lookup"><span data-stu-id="6555e-265">-FollowSymlink</span></span>

<span data-ttu-id="6555e-266">既定では、この `Get-ChildItem` コマンドレットは再帰中に検出されたディレクトリへのシンボリックリンクを表示しますが、それらのリンクには再帰しません。</span><span class="sxs-lookup"><span data-stu-id="6555e-266">By default, the `Get-ChildItem` cmdlet displays symbolic links to directories found during recursion, but doesn't recurse into them.</span></span> <span data-ttu-id="6555e-267">これらのシンボリックリンクを対象としているディレクトリを検索するに **は、のようにします** 。</span><span class="sxs-lookup"><span data-stu-id="6555e-267">Use the **FollowSymlink** parameter to search the directories that target those symbolic links.</span></span> <span data-ttu-id="6555e-268">この **引数は動的** パラメーターであり、 **FileSystem** プロバイダーでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6555e-268">The **FollowSymlink** is a dynamic parameter and is supported only in the **FileSystem** provider.</span></span>

<span data-ttu-id="6555e-269">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6555e-269">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6555e-270">-Force</span><span class="sxs-lookup"><span data-stu-id="6555e-270">-Force</span></span>

<span data-ttu-id="6555e-271">隠しファイルやシステムファイルなど、ユーザーがアクセスできない項目をコマンドレットで取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6555e-271">Allows the cmdlet to get items that otherwise can't be accessed by the user, such as hidden or system files.</span></span> <span data-ttu-id="6555e-272">**Force** パラメーターは、セキュリティ制限をオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="6555e-272">The **Force** parameter doesn't override security restrictions.</span></span> <span data-ttu-id="6555e-273">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="6555e-273">Implementation varies among providers.</span></span> <span data-ttu-id="6555e-274">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6555e-274">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6555e-275">-Hidden</span><span class="sxs-lookup"><span data-stu-id="6555e-275">-Hidden</span></span>

<span data-ttu-id="6555e-276">非表示の項目のみを取得するには、hidden パラメーターまたは **Attributes** パラメーターを **hidden** プロパティと共に **使用します**。</span><span class="sxs-lookup"><span data-stu-id="6555e-276">To get only hidden items, use the **Hidden** parameter or the **Attributes** parameter with the **Hidden** property.</span></span> <span data-ttu-id="6555e-277">既定では、は非表示の `Get-ChildItem` 項目を表示しません。</span><span class="sxs-lookup"><span data-stu-id="6555e-277">By default, `Get-ChildItem` doesn't display hidden items.</span></span> <span data-ttu-id="6555e-278">**Force** パラメーターを使用して、非表示の項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="6555e-278">Use the **Force** parameter to get hidden items.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ah, h

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6555e-279">-Include</span><span class="sxs-lookup"><span data-stu-id="6555e-279">-Include</span></span>

<span data-ttu-id="6555e-280">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="6555e-280">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="6555e-281">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="6555e-281">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="6555e-282">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="6555e-282">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="6555e-283">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6555e-283">Wildcard characters are permitted.</span></span> <span data-ttu-id="6555e-284">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="6555e-284">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="6555e-285">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="6555e-285">-LiteralPath</span></span>

<span data-ttu-id="6555e-286">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6555e-286">Specifies a path to one or more locations.</span></span> <span data-ttu-id="6555e-287">**LiteralPath** の値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6555e-287">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="6555e-288">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="6555e-288">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="6555e-289">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="6555e-289">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="6555e-290">単一引用符は、どの文字もエスケープシーケンスとして解釈されないように PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="6555e-290">Single quotation marks tell PowerShell to not interpret any characters as escape sequences.</span></span>

<span data-ttu-id="6555e-291">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6555e-291">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralItems
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6555e-292">-Name</span><span class="sxs-lookup"><span data-stu-id="6555e-292">-Name</span></span>

<span data-ttu-id="6555e-293">場所内の項目の名前のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="6555e-293">Gets only the names of the items in the location.</span></span> <span data-ttu-id="6555e-294">出力は、他のコマンドにパイプラインから送信できる文字列オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="6555e-294">The output is a string object that can be sent down the pipeline to other commands.</span></span> <span data-ttu-id="6555e-295">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6555e-295">Wildcards are permitted.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="6555e-296">-Path</span><span class="sxs-lookup"><span data-stu-id="6555e-296">-Path</span></span>

<span data-ttu-id="6555e-297">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6555e-297">Specifies a path to one or more locations.</span></span> <span data-ttu-id="6555e-298">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6555e-298">Wildcards are accepted.</span></span> <span data-ttu-id="6555e-299">既定の場所は、現在のディレクトリ ( `.` ) です。</span><span class="sxs-lookup"><span data-stu-id="6555e-299">The default location is the current directory (`.`).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Items
Aliases:

Required: False
Position: 0
Default value: Current directory
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="6555e-300">-ReadOnly</span><span class="sxs-lookup"><span data-stu-id="6555e-300">-ReadOnly</span></span>

<span data-ttu-id="6555e-301">読み取り専用の項目のみを取得するには、 **readonly** パラメーターまたは **Attributes** パラメーター **readonly** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="6555e-301">To get only read-only items, use the **ReadOnly** parameter or the **Attributes** parameter **ReadOnly** property.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ar

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6555e-302">-再帰</span><span class="sxs-lookup"><span data-stu-id="6555e-302">-Recurse</span></span>

<span data-ttu-id="6555e-303">指定された場所にある項目と、その場所のすべての子項目にある項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="6555e-303">Gets the items in the specified locations and in all child items of the locations.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: s

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6555e-304">-System</span><span class="sxs-lookup"><span data-stu-id="6555e-304">-System</span></span>

<span data-ttu-id="6555e-305">システムファイルとディレクトリのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="6555e-305">Gets only system files and directories.</span></span> <span data-ttu-id="6555e-306">システムファイルとフォルダーのみを取得するには **、システムパラメーターまた** は **Attributes** パラメーター **システム** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="6555e-306">To get only system files and folders, use the **System** parameter or **Attributes** parameter **System** property.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: as

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6555e-307">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6555e-307">CommonParameters</span></span>

<span data-ttu-id="6555e-308">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6555e-308">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6555e-309">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6555e-309">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6555e-310">入力</span><span class="sxs-lookup"><span data-stu-id="6555e-310">INPUTS</span></span>

### <span data-ttu-id="6555e-311">System.String</span><span class="sxs-lookup"><span data-stu-id="6555e-311">System.String</span></span>

<span data-ttu-id="6555e-312">パイプを使用して、パスを含む文字列をにパイプすることができ `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="6555e-312">You can pipe a string that contains a path to `Get-ChildItem`.</span></span>

## <span data-ttu-id="6555e-313">出力</span><span class="sxs-lookup"><span data-stu-id="6555e-313">OUTPUTS</span></span>

### <span data-ttu-id="6555e-314">System.Object</span><span class="sxs-lookup"><span data-stu-id="6555e-314">System.Object</span></span>

<span data-ttu-id="6555e-315">が返すオブジェクトの型 `Get-ChildItem` は、プロバイダーのドライブパス内のオブジェクトによって決まります。</span><span class="sxs-lookup"><span data-stu-id="6555e-315">The type of object that `Get-ChildItem` returns is determined by the objects in the provider drive path.</span></span>

### <span data-ttu-id="6555e-316">System.String</span><span class="sxs-lookup"><span data-stu-id="6555e-316">System.String</span></span>

<span data-ttu-id="6555e-317">**Name** パラメーターを使用すると、では、 `Get-ChildItem` オブジェクト名が文字列として返されます。</span><span class="sxs-lookup"><span data-stu-id="6555e-317">If you use the **Name** parameter, `Get-ChildItem` returns the object names as strings.</span></span>

## <span data-ttu-id="6555e-318">注</span><span class="sxs-lookup"><span data-stu-id="6555e-318">NOTES</span></span>

- <span data-ttu-id="6555e-319">`Get-ChildItem` は、組み込みのエイリアスである、、およびを使用して実行でき `ls` `dir` `gci` ます。</span><span class="sxs-lookup"><span data-stu-id="6555e-319">`Get-ChildItem` can be run using any of the built-in aliases, `ls`, `dir`, and `gci`.</span></span> <span data-ttu-id="6555e-320">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6555e-320">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="6555e-321">`Get-ChildItem` 既定では、非表示の項目は取得されません。</span><span class="sxs-lookup"><span data-stu-id="6555e-321">`Get-ChildItem` doesn't get hidden items by default.</span></span> <span data-ttu-id="6555e-322">隠し項目を取得するには、**Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6555e-322">To get hidden items, use the **Force** parameter.</span></span>
- <span data-ttu-id="6555e-323">`Get-ChildItem`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="6555e-323">The `Get-ChildItem` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="6555e-324">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="6555e-324">To list the providers available in your session, type `Get-PSProvider`.</span></span>
  <span data-ttu-id="6555e-325">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6555e-325">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="6555e-326">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6555e-326">RELATED LINKS</span></span>

[<span data-ttu-id="6555e-327">about_Certificate_Provider</span><span class="sxs-lookup"><span data-stu-id="6555e-327">about_Certificate_Provider</span></span>](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)

[<span data-ttu-id="6555e-328">about_Providers</span><span class="sxs-lookup"><span data-stu-id="6555e-328">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="6555e-329">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="6555e-329">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="6555e-330">about_Registry_Provider</span><span class="sxs-lookup"><span data-stu-id="6555e-330">about_Registry_Provider</span></span>](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md)

[<span data-ttu-id="6555e-331">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="6555e-331">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="6555e-332">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="6555e-332">Get-Alias</span></span>](../Microsoft.PowerShell.Utility/Get-Alias.md)

[<span data-ttu-id="6555e-333">Get-Item</span><span class="sxs-lookup"><span data-stu-id="6555e-333">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="6555e-334">Get-Location</span><span class="sxs-lookup"><span data-stu-id="6555e-334">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="6555e-335">Get-Process</span><span class="sxs-lookup"><span data-stu-id="6555e-335">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="6555e-336">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="6555e-336">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="6555e-337">Split-Path</span><span class="sxs-lookup"><span data-stu-id="6555e-337">Split-Path</span></span>](Split-Path.md)

