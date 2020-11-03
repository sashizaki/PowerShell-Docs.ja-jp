---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ChildItem
ms.openlocfilehash: c29a938fc73b8b69ea1bbf96f12f5d42d16f79bf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217659"
---
# <span data-ttu-id="709f7-103">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="709f7-103">Get-ChildItem</span></span>

## <span data-ttu-id="709f7-104">概要</span><span class="sxs-lookup"><span data-stu-id="709f7-104">SYNOPSIS</span></span>

<span data-ttu-id="709f7-105">1 つ以上の指定された場所から項目および子項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="709f7-105">Gets the items and child items in one or more specified locations.</span></span>

## <span data-ttu-id="709f7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="709f7-106">SYNTAX</span></span>

### <span data-ttu-id="709f7-107">項目 (既定)</span><span class="sxs-lookup"><span data-stu-id="709f7-107">Items (Default)</span></span>

```
Get-ChildItem [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>]
 [-Recurse] [-Depth <uint32>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>]
 [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]
```

### <span data-ttu-id="709f7-108">LiteralItems</span><span class="sxs-lookup"><span data-stu-id="709f7-108">LiteralItems</span></span>

```
Get-ChildItem [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>]
 [-Exclude <string[]>] [-Recurse] [-Depth <uint32>] [-Force] [-Name]
 [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden]
 [-ReadOnly] [-System] [<CommonParameters>]
```

## <span data-ttu-id="709f7-109">Description</span><span class="sxs-lookup"><span data-stu-id="709f7-109">DESCRIPTION</span></span>

<span data-ttu-id="709f7-110">`Get-ChildItem`コマンドレットは、指定された1つまたは複数の場所にある項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="709f7-110">The `Get-ChildItem` cmdlet gets the items in one or more specified locations.</span></span> <span data-ttu-id="709f7-111">項目がコンテナーの場合は、コンテナーの中にある項目 (子項目) を取得します。</span><span class="sxs-lookup"><span data-stu-id="709f7-111">If the item is a container, it gets the items inside the container, known as child items.</span></span> <span data-ttu-id="709f7-112">**再帰** パラメーターを使用すると、すべての子コンテナー内の項目を取得し、 **Depth** パラメーターを使用して再帰的なレベル数を制限できます。</span><span class="sxs-lookup"><span data-stu-id="709f7-112">You can use the **Recurse** parameter to get items in all child containers and use the **Depth** parameter to limit the number of levels to recurse.</span></span>

<span data-ttu-id="709f7-113">`Get-ChildItem` 空のディレクトリは表示されません。</span><span class="sxs-lookup"><span data-stu-id="709f7-113">`Get-ChildItem` doesn't display empty directories.</span></span> <span data-ttu-id="709f7-114">コマンドに `Get-ChildItem` **深度** パラメーターまたは **再帰** パラメーターが含まれている場合、空のディレクトリは出力に含まれません。</span><span class="sxs-lookup"><span data-stu-id="709f7-114">When a `Get-ChildItem` command includes the **Depth** or **Recurse** parameters, empty directories aren't included in the output.</span></span>

<span data-ttu-id="709f7-115">場所は、PowerShell プロバイダーによってに公開され `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="709f7-115">Locations are exposed to `Get-ChildItem` by PowerShell providers.</span></span> <span data-ttu-id="709f7-116">場所には、ファイルシステムディレクトリ、レジストリハイブ、または証明書ストアを指定できます。</span><span class="sxs-lookup"><span data-stu-id="709f7-116">A location can be a file system directory, registry hive, or a certificate store.</span></span> <span data-ttu-id="709f7-117">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="709f7-117">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="709f7-118">例</span><span class="sxs-lookup"><span data-stu-id="709f7-118">EXAMPLES</span></span>

### <span data-ttu-id="709f7-119">例 1: ファイルシステムディレクトリから子項目を取得する</span><span class="sxs-lookup"><span data-stu-id="709f7-119">Example 1: Get child items from a file system directory</span></span>

<span data-ttu-id="709f7-120">この例では、ファイルシステムディレクトリから子項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="709f7-120">This example gets the child items from a file system directory.</span></span> <span data-ttu-id="709f7-121">ファイル名とサブディレクトリ名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="709f7-121">The filenames and subdirectory names are displayed.</span></span> <span data-ttu-id="709f7-122">空の場所の場合、コマンドは出力を返さず、PowerShell プロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="709f7-122">For empty locations, the command doesn't return any output and returns to the PowerShell prompt.</span></span>

<span data-ttu-id="709f7-123">コマンドレットでは、 `Get-ChildItem` **Path** パラメーターを使用してディレクトリを指定し `C:\Test` ます。</span><span class="sxs-lookup"><span data-stu-id="709f7-123">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test`.</span></span>
<span data-ttu-id="709f7-124">`Get-ChildItem` ファイルとディレクトリを PowerShell コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-124">`Get-ChildItem` displays the files and directories in the PowerShell console.</span></span>

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

<span data-ttu-id="709f7-125">既定で `Get-ChildItem` は、モード ( **属性** )、 **lastwritetime** 、ファイルサイズ ( **長さ** )、およびアイテムの **名前** が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="709f7-125">By default `Get-ChildItem` lists the mode ( **Attributes** ), **LastWriteTime** , file size ( **Length** ), and the **Name** of the item.</span></span> <span data-ttu-id="709f7-126">**Mode** プロパティの文字は、次のように解釈できます。</span><span class="sxs-lookup"><span data-stu-id="709f7-126">The letters in the **Mode** property can be interpreted as follows:</span></span>

- <span data-ttu-id="709f7-127">`l` リンク</span><span class="sxs-lookup"><span data-stu-id="709f7-127">`l` (link)</span></span>
- <span data-ttu-id="709f7-128">`d` 名簿</span><span class="sxs-lookup"><span data-stu-id="709f7-128">`d` (directory)</span></span>
- <span data-ttu-id="709f7-129">`a` アイテム</span><span class="sxs-lookup"><span data-stu-id="709f7-129">`a` (archive)</span></span>
- <span data-ttu-id="709f7-130">`r` (読み取り専用)</span><span class="sxs-lookup"><span data-stu-id="709f7-130">`r` (read-only)</span></span>
- <span data-ttu-id="709f7-131">`h` 表示</span><span class="sxs-lookup"><span data-stu-id="709f7-131">`h` (hidden)</span></span>
- <span data-ttu-id="709f7-132">`s` (システム)。</span><span class="sxs-lookup"><span data-stu-id="709f7-132">`s` (system).</span></span>

<span data-ttu-id="709f7-133">モードフラグの詳細については、「 [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="709f7-133">For more information about the mode flags, see [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression).</span></span>

### <span data-ttu-id="709f7-134">例 2: ディレクトリ内の子項目の名前を取得する</span><span class="sxs-lookup"><span data-stu-id="709f7-134">Example 2: Get child item names in a directory</span></span>

<span data-ttu-id="709f7-135">この例では、ディレクトリ内の項目の名前のみを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-135">This example lists only the names of items in a directory.</span></span>

<span data-ttu-id="709f7-136">コマンドレットでは、 `Get-ChildItem` **Path** パラメーターを使用してディレクトリを指定し `C:\Test` ます。</span><span class="sxs-lookup"><span data-stu-id="709f7-136">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test`.</span></span> <span data-ttu-id="709f7-137">**Name** パラメーターは、指定されたパスからファイル名またはディレクトリ名のみを返します。</span><span class="sxs-lookup"><span data-stu-id="709f7-137">The **Name** parameter returns only the file or directory names from the specified path.</span></span>

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

### <span data-ttu-id="709f7-138">例 3: 現在のディレクトリとサブディレクトリ内の子項目を取得する</span><span class="sxs-lookup"><span data-stu-id="709f7-138">Example 3: Get child items in the current directory and subdirectories</span></span>

<span data-ttu-id="709f7-139">この例では、現在のディレクトリとそのサブディレクトリにある .txt ファイルを表示し **ます。**</span><span class="sxs-lookup"><span data-stu-id="709f7-139">This example displays **.txt** files that are located in the current directory and its subdirectories.</span></span>

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

<span data-ttu-id="709f7-140">この `Get-ChildItem` コマンドレットは、 **Path** パラメーターを使用してを指定し `C:\Test\*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="709f7-140">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify `C:\Test\*.txt`.</span></span> <span data-ttu-id="709f7-141">**Path** はアスタリスク ( `*` ) ワイルドカードを使用して、ファイル名拡張子を持つすべてのファイルを指定し `.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="709f7-141">**Path** uses the asterisk (`*`) wildcard to specify all files with the filename extension `.txt`.</span></span> <span data-ttu-id="709f7-142">**再帰** パラメーターは、 **ディレクトリ:** 見出しに示されているように、 **パス** ディレクトリ内のサブディレクトリを検索します。</span><span class="sxs-lookup"><span data-stu-id="709f7-142">The **Recurse** parameter searches the **Path** directory its subdirectories, as shown in the **Directory:** headings.</span></span> <span data-ttu-id="709f7-143">**Force** パラメーターは、 `hiddenfile.txt` モードが **h** のなどの非表示ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-143">The **Force** parameter displays hidden files such as `hiddenfile.txt` that have a mode of **h**.</span></span>

### <span data-ttu-id="709f7-144">例 4: Include パラメーターを使用して子項目を取得する</span><span class="sxs-lookup"><span data-stu-id="709f7-144">Example 4: Get child items using the Include parameter</span></span>

<span data-ttu-id="709f7-145">この例では、 `Get-ChildItem` **Include** パラメーターを使用して、 **Path** パラメーターで指定されたディレクトリから特定の項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="709f7-145">In this example `Get-ChildItem` uses the **Include** parameter to find specific items from the directory specified by the **Path** parameter.</span></span>

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

<span data-ttu-id="709f7-146">この `Get-ChildItem` コマンドレットでは、 **Path** パラメーターを使用して、ディレクトリ **C:\Test** を指定します。</span><span class="sxs-lookup"><span data-stu-id="709f7-146">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory **C:\Test**.</span></span> <span data-ttu-id="709f7-147">**Path** パラメーターには、ディレクトリの内容を指定するための末尾のアスタリスク () ワイルドカードが含まれてい `*` ます。</span><span class="sxs-lookup"><span data-stu-id="709f7-147">The **Path** parameter includes a trailing asterisk (`*`) wildcard to specify the directory's contents.</span></span>
<span data-ttu-id="709f7-148">**Include** パラメーターでは、アスタリスク ( `*` ) ワイルドカードを使用して、ファイル名拡張子 **.txt** を持つすべてのファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="709f7-148">The **Include** parameter uses an asterisk (`*`) wildcard to specify all files with the file name extension **.txt**.</span></span>

<span data-ttu-id="709f7-149">**Include** パラメーターを使用する場合、 **Path** パラメーターには、 `*` ディレクトリの内容を指定するための末尾のアスタリスク () ワイルドカードが必要です。</span><span class="sxs-lookup"><span data-stu-id="709f7-149">When the **Include** parameter is used, the **Path** parameter needs a trailing asterisk (`*`) wildcard to specify the directory's contents.</span></span> <span data-ttu-id="709f7-150">たとえば、「 `-Path C:\Test\*` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="709f7-150">For example, `-Path C:\Test\*`.</span></span>

- <span data-ttu-id="709f7-151">**再帰** パラメーターがコマンドに追加された場合、Path パラメーターの末尾のアスタリスク ( `*` ) は省略可能です。 **Path**</span><span class="sxs-lookup"><span data-stu-id="709f7-151">If the **Recurse** parameter is added to the command, the trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="709f7-152">**再帰** パラメーターは、 **パス** ディレクトリとそのサブディレクトリから項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="709f7-152">The **Recurse** parameter gets items from the **Path** directory and its subdirectories.</span></span> <span data-ttu-id="709f7-153">たとえば、`-Path C:\Test\ -Recurse -Include *.txt` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="709f7-153">For example, `-Path C:\Test\ -Recurse -Include *.txt`</span></span>
- <span data-ttu-id="709f7-154">パスパラメーターに末尾のアスタリスク () が含まれていない場合 `*` 、コマンドは出力を返さず、PowerShell プロンプトに戻ります。 **Path**</span><span class="sxs-lookup"><span data-stu-id="709f7-154">If a trailing asterisk (`*`) isn't included in the **Path** parameter, the command doesn't return any output and returns to the PowerShell prompt.</span></span> <span data-ttu-id="709f7-155">たとえば、「 `-Path C:\Test\` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="709f7-155">For example, `-Path C:\Test\`.</span></span>

### <span data-ttu-id="709f7-156">例 5: Exclude パラメーターを使用して子項目を取得する</span><span class="sxs-lookup"><span data-stu-id="709f7-156">Example 5: Get child items using the Exclude parameter</span></span>

<span data-ttu-id="709f7-157">この例の出力は、ディレクトリ **C:\Test\Logs** の内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="709f7-157">The example's output shows the contents of the directory **C:\Test\Logs**.</span></span> <span data-ttu-id="709f7-158">出力は、 **Exclude** および **再帰** パラメーターを使用する他のコマンドの参照です。</span><span class="sxs-lookup"><span data-stu-id="709f7-158">The output is a reference for the other commands that use the **Exclude** and **Recurse** parameters.</span></span>

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

<span data-ttu-id="709f7-159">コマンドレットでは、 `Get-ChildItem` **Path** パラメーターを使用してディレクトリを指定し `C:\Test\Logs` ます。</span><span class="sxs-lookup"><span data-stu-id="709f7-159">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test\Logs`.</span></span>
<span data-ttu-id="709f7-160">**Exclude** パラメーターでは、アスタリスク () ワイルドカードを使用して、 `*` またはで **A** 始まる任意のファイルまたはディレクトリを出力から除外します。 **a**</span><span class="sxs-lookup"><span data-stu-id="709f7-160">The **Exclude** parameter uses the asterisk (`*`) wildcard to specify any files or directories that begin with **A** or **a** are excluded from the output.</span></span>

<span data-ttu-id="709f7-161">**Exclude** パラメーターを使用する場合、Path パラメーターの末尾のアスタリスク ( `*` ) は省略可能です。 **Path**</span><span class="sxs-lookup"><span data-stu-id="709f7-161">When the **Exclude** parameter is used, a trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="709f7-162">たとえば、`-Path C:\Test\Logs` または `-Path C:\Test\Logs\*` です。</span><span class="sxs-lookup"><span data-stu-id="709f7-162">For example, `-Path C:\Test\Logs` or `-Path C:\Test\Logs\*`.</span></span>

- <span data-ttu-id="709f7-163">Path パラメーターに末尾のアスタリスク ( `*` ) が含ま **Path** れていない場合は、 **path** パラメーターの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="709f7-163">If a trailing asterisk (`*`) isn't included in the **Path** parameter, the contents of the **Path** parameter are displayed.</span></span> <span data-ttu-id="709f7-164">例外は、 **Exclude** パラメーターの値と一致するファイル名またはサブディレクトリ名です。</span><span class="sxs-lookup"><span data-stu-id="709f7-164">The exceptions are filenames or subdirectory names that match the **Exclude** parameter's value.</span></span>
- <span data-ttu-id="709f7-165">Path パラメーターに末尾のアスタリスク ( `*` ) が含ま **Path** れている場合、コマンドは **path** パラメーターのサブディレクトリに繰り返しします。</span><span class="sxs-lookup"><span data-stu-id="709f7-165">If a trailing asterisk (`*`) is included in the **Path** parameter, the command recurses into the **Path** parameter's subdirectories.</span></span> <span data-ttu-id="709f7-166">例外は、 **Exclude** パラメーターの値と一致するファイル名またはサブディレクトリ名です。</span><span class="sxs-lookup"><span data-stu-id="709f7-166">The exceptions are filenames or subdirectory names that match the **Exclude** parameter's value.</span></span>
- <span data-ttu-id="709f7-167">**再帰パラメーターが** コマンドに追加された場合、 **Path** パラメーターに末尾のアスタリスク () が含まれているかどうかにかかわらず、再帰の出力は同じに `*` なります。</span><span class="sxs-lookup"><span data-stu-id="709f7-167">If the **Recurse** parameter is added to the command, the recursion output is the same whether or not the **Path** parameter includes a trailing asterisk (`*`).</span></span>

### <span data-ttu-id="709f7-168">例 6: レジストリハイブからレジストリキーを取得する</span><span class="sxs-lookup"><span data-stu-id="709f7-168">Example 6: Get the registry keys from a registry hive</span></span>

<span data-ttu-id="709f7-169">この例では、からすべてのレジストリキーを取得し `HKEY_LOCAL_MACHINE\HARDWARE` ます。</span><span class="sxs-lookup"><span data-stu-id="709f7-169">This example gets all the registry keys from `HKEY_LOCAL_MACHINE\HARDWARE`.</span></span>

<span data-ttu-id="709f7-170">`Get-ChildItem`**Path** パラメーターを使用して、レジストリキーを指定し `HKLM:\HARDWARE` ます。</span><span class="sxs-lookup"><span data-stu-id="709f7-170">`Get-ChildItem` uses the **Path** parameter to specify the registry key `HKLM:\HARDWARE`.</span></span> <span data-ttu-id="709f7-171">PowerShell コンソールには、ハイブのパスとレジストリキーの最上位レベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="709f7-171">The hive's path and top level of registry keys are displayed in the PowerShell console.</span></span>

<span data-ttu-id="709f7-172">詳細については、「 [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="709f7-172">For more information, see [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md).</span></span>

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

<span data-ttu-id="709f7-173">最初のコマンドは、レジストリキーの内容を表示し `HKLM:\HARDWARE` ます。</span><span class="sxs-lookup"><span data-stu-id="709f7-173">The first command shows the contents of the `HKLM:\HARDWARE` registry key.</span></span> <span data-ttu-id="709f7-174">**Exclude** パラメーターは、 `Get-ChildItem` で始まるサブキーを返さないように指示 `D*` します。</span><span class="sxs-lookup"><span data-stu-id="709f7-174">The **Exclude** parameter tells `Get-ChildItem` not to return any subkeys that start with `D*`.</span></span> <span data-ttu-id="709f7-175">現在、 **Exclude** パラメーターは、項目のプロパティではなく、サブキーに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="709f7-175">Currently, the **Exclude** parameter only works on subkeys, not item properties.</span></span>

### <span data-ttu-id="709f7-176">例 7: コード署名権限を持つすべての証明書を取得する</span><span class="sxs-lookup"><span data-stu-id="709f7-176">Example 7: Get all certificates with code-signing authority</span></span>

<span data-ttu-id="709f7-177">この例では、コード署名権限を持つ、PowerShell **Cert:** ドライブ内の各証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="709f7-177">This example gets each certificate in the PowerShell **Cert:** drive that has code-signing authority.</span></span>

<span data-ttu-id="709f7-178">コマンドレットでは、 `Get-ChildItem` **Path** パラメーターを使用して **Cert:** provider を指定します。</span><span class="sxs-lookup"><span data-stu-id="709f7-178">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the **Cert:** provider.</span></span> <span data-ttu-id="709f7-179">**再帰** パラメーターは、 **Path** とそのサブディレクトリで指定されたディレクトリを検索します。</span><span class="sxs-lookup"><span data-stu-id="709f7-179">The **Recurse** parameter searches the directory specified by **Path** and its subdirectories.</span></span> <span data-ttu-id="709f7-180">**Codesigningcert** パラメーターは、コード署名権限を持つ証明書のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="709f7-180">The **CodeSigningCert** parameter gets only certificates that have code-signing authority.</span></span>

```powershell
Get-ChildItem -Path Cert:\* -Recurse -CodeSigningCert
```

<span data-ttu-id="709f7-181">証明書プロバイダーと Cert: ドライブの詳細については、「 [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="709f7-181">For more information about the Certificate provider and the Cert: drive, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

### <span data-ttu-id="709f7-182">例 8: Depth パラメーターを使用して項目を取得する</span><span class="sxs-lookup"><span data-stu-id="709f7-182">Example 8: Get items using the Depth parameter</span></span>

<span data-ttu-id="709f7-183">この例では、ディレクトリとそのサブディレクトリ内の項目を表示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-183">This example displays the items in a directory and its subdirectories.</span></span> <span data-ttu-id="709f7-184">**Depth** パラメーターは、再帰に含めるサブディレクトリレベルの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="709f7-184">The **Depth** parameter determines the number of subdirectory levels to include in the recursion.</span></span> <span data-ttu-id="709f7-185">空のディレクトリは、出力から除外されます。</span><span class="sxs-lookup"><span data-stu-id="709f7-185">Empty directories are excluded from the output.</span></span>

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

<span data-ttu-id="709f7-186">この `Get-ChildItem` コマンドレットは、 **path** パラメーターを使用して、 **c:\ 親** を指定します。</span><span class="sxs-lookup"><span data-stu-id="709f7-186">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify **C:\Parent**.</span></span> <span data-ttu-id="709f7-187">**Depth** パラメーターでは、2つのレベルの再帰が指定されています。</span><span class="sxs-lookup"><span data-stu-id="709f7-187">The **Depth** parameter specifies two levels of recursion.</span></span> <span data-ttu-id="709f7-188">`Get-ChildItem`**Path** パラメーターで指定したディレクトリの内容と、サブディレクトリの2つのレベルを表示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-188">`Get-ChildItem` displays the contents of the directory specified by the **Path** parameter and the two levels of subdirectories.</span></span>

### <span data-ttu-id="709f7-189">例 9: ハードリンク情報を取得する</span><span class="sxs-lookup"><span data-stu-id="709f7-189">Example 9: Getting hard link information</span></span>

<span data-ttu-id="709f7-190">PowerShell 6.2 では、ハードリンク情報を取得するために代替ビューが追加されました。</span><span class="sxs-lookup"><span data-stu-id="709f7-190">In PowerShell 6.2, an alternate view was added to get hard link information.</span></span>

```powershell
Get-ChildItem -Path C:\PathContainingHardLink | Format-Table -View childrenWithHardLink
```

### <span data-ttu-id="709f7-191">例 9: 試験的な特徴 PSUnixFileStat の出力</span><span class="sxs-lookup"><span data-stu-id="709f7-191">Example 9: Output for experimental feature PSUnixFileStat</span></span>

<span data-ttu-id="709f7-192">Unix システムの PowerShell 7 では、試験的な機能 **PSUnixFileStat** が unix に似た出力を提供します。</span><span class="sxs-lookup"><span data-stu-id="709f7-192">In PowerShell 7 on Unix systems, the experimental feature **PSUnixFileStat** provides Unix-like output:</span></span>

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

<span data-ttu-id="709f7-193">出力の一部である新しいプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="709f7-193">The new properties that are now part of the output are:</span></span>

- <span data-ttu-id="709f7-194">**UnixMode** は、Unix システムで表されるファイルのアクセス許可です。</span><span class="sxs-lookup"><span data-stu-id="709f7-194">**UnixMode** is the file permissions as represented on a Unix system</span></span>
- <span data-ttu-id="709f7-195">**ユーザー** はファイルの所有者です</span><span class="sxs-lookup"><span data-stu-id="709f7-195">**User** is the file owner</span></span>
- <span data-ttu-id="709f7-196">**グループは** グループの所有者です</span><span class="sxs-lookup"><span data-stu-id="709f7-196">**Group** is the group owner</span></span>
- <span data-ttu-id="709f7-197">**サイズ** は、Unix システムで表されるファイルまたはディレクトリのサイズです。</span><span class="sxs-lookup"><span data-stu-id="709f7-197">**Size** is the size of the file or directory as represented on a Unix system</span></span>

## <span data-ttu-id="709f7-198">パラメーター</span><span class="sxs-lookup"><span data-stu-id="709f7-198">Parameters</span></span>

### <span data-ttu-id="709f7-199">-属性</span><span class="sxs-lookup"><span data-stu-id="709f7-199">-Attributes</span></span>

<span data-ttu-id="709f7-200">指定した属性のファイルとフォルダーを取得します。</span><span class="sxs-lookup"><span data-stu-id="709f7-200">Gets files and folders with the specified attributes.</span></span> <span data-ttu-id="709f7-201">このパラメーターはすべての属性をサポートします。複雑な属性の組み合わせを指定できます。</span><span class="sxs-lookup"><span data-stu-id="709f7-201">This parameter supports all attributes and lets you specify complex combinations of attributes.</span></span>

<span data-ttu-id="709f7-202">たとえば、暗号化または圧縮されている非システム ファイル (非ディレクトリ) を取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="709f7-202">For example, to get non-system files (not directories) that are encrypted or compressed, type:</span></span>

`Get-ChildItem -Attributes !Directory+!System+Encrypted, !Directory+!System+Compressed`

<span data-ttu-id="709f7-203">よく使用される属性を持つファイルとフォルダーを検索するには、 **attributes** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="709f7-203">To find files and folders with commonly used attributes, use the **Attributes** parameter.</span></span> <span data-ttu-id="709f7-204">または、パラメーター **Directory** 、 **File** 、 **Hidden** 、 **ReadOnly** 、および **System** です。</span><span class="sxs-lookup"><span data-stu-id="709f7-204">Or, the parameters **Directory** , **File** , **Hidden** , **ReadOnly** , and **System**.</span></span>

<span data-ttu-id="709f7-205">**Attributes** パラメーターでは、次のプロパティがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="709f7-205">The **Attributes** parameter supports the following properties:</span></span>

- <span data-ttu-id="709f7-206">**Archive**</span><span class="sxs-lookup"><span data-stu-id="709f7-206">**Archive**</span></span>
- <span data-ttu-id="709f7-207">**Compressed**</span><span class="sxs-lookup"><span data-stu-id="709f7-207">**Compressed**</span></span>
- <span data-ttu-id="709f7-208">**[デバイス]**</span><span class="sxs-lookup"><span data-stu-id="709f7-208">**Device**</span></span>
- <span data-ttu-id="709f7-209">**ディレクトリ**</span><span class="sxs-lookup"><span data-stu-id="709f7-209">**Directory**</span></span>
- <span data-ttu-id="709f7-210">**Encrypted**</span><span class="sxs-lookup"><span data-stu-id="709f7-210">**Encrypted**</span></span>
- <span data-ttu-id="709f7-211">**[非表示]**</span><span class="sxs-lookup"><span data-stu-id="709f7-211">**Hidden**</span></span>
- <span data-ttu-id="709f7-212">**IntegrityStream**</span><span class="sxs-lookup"><span data-stu-id="709f7-212">**IntegrityStream**</span></span>
- <span data-ttu-id="709f7-213">**標準**</span><span class="sxs-lookup"><span data-stu-id="709f7-213">**Normal**</span></span>
- <span data-ttu-id="709f7-214">**NoScrubData**</span><span class="sxs-lookup"><span data-stu-id="709f7-214">**NoScrubData**</span></span>
- <span data-ttu-id="709f7-215">**NotContentIndexed**</span><span class="sxs-lookup"><span data-stu-id="709f7-215">**NotContentIndexed**</span></span>
- <span data-ttu-id="709f7-216">**なっ**</span><span class="sxs-lookup"><span data-stu-id="709f7-216">**Offline**</span></span>
- <span data-ttu-id="709f7-217">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="709f7-217">**ReadOnly**</span></span>
- <span data-ttu-id="709f7-218">**ReparsePoint**</span><span class="sxs-lookup"><span data-stu-id="709f7-218">**ReparsePoint**</span></span>
- <span data-ttu-id="709f7-219">**Sparc ファイル**</span><span class="sxs-lookup"><span data-stu-id="709f7-219">**SparseFile**</span></span>
- <span data-ttu-id="709f7-220">**システム**</span><span class="sxs-lookup"><span data-stu-id="709f7-220">**System**</span></span>
- <span data-ttu-id="709f7-221">**一時**</span><span class="sxs-lookup"><span data-stu-id="709f7-221">**Temporary**</span></span>

<span data-ttu-id="709f7-222">これらの属性の詳細については、「 [Fileattributes 列挙型](/dotnet/api/system.io.fileattributes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="709f7-222">For a description of these attributes, see the [FileAttributes Enumeration](/dotnet/api/system.io.fileattributes).</span></span>

<span data-ttu-id="709f7-223">属性を結合するには、次の演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="709f7-223">To combine attributes, use the following operators:</span></span>

- <span data-ttu-id="709f7-224">`!` 非</span><span class="sxs-lookup"><span data-stu-id="709f7-224">`!` (NOT)</span></span>
- <span data-ttu-id="709f7-225">`+` と</span><span class="sxs-lookup"><span data-stu-id="709f7-225">`+` (AND)</span></span>
- <span data-ttu-id="709f7-226">`,` もしくは</span><span class="sxs-lookup"><span data-stu-id="709f7-226">`,` (OR)</span></span>

<span data-ttu-id="709f7-227">演算子とその属性の間にはスペースを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="709f7-227">Don't use spaces between an operator and its attribute.</span></span> <span data-ttu-id="709f7-228">コンマの後にスペースを入れることができます。</span><span class="sxs-lookup"><span data-stu-id="709f7-228">Spaces are accepted after commas.</span></span>

<span data-ttu-id="709f7-229">共通属性の場合は、次の省略形を使用します。</span><span class="sxs-lookup"><span data-stu-id="709f7-229">For common attributes, use the following abbreviations:</span></span>

- <span data-ttu-id="709f7-230">`D` 名簿</span><span class="sxs-lookup"><span data-stu-id="709f7-230">`D` (Directory)</span></span>
- <span data-ttu-id="709f7-231">`H` 表示</span><span class="sxs-lookup"><span data-stu-id="709f7-231">`H` (Hidden)</span></span>
- <span data-ttu-id="709f7-232">`R` (読み取り専用)</span><span class="sxs-lookup"><span data-stu-id="709f7-232">`R` (Read-only)</span></span>
- <span data-ttu-id="709f7-233">`S` (システム)</span><span class="sxs-lookup"><span data-stu-id="709f7-233">`S` (System)</span></span>

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

### <span data-ttu-id="709f7-234">-深さ</span><span class="sxs-lookup"><span data-stu-id="709f7-234">-Depth</span></span>

<span data-ttu-id="709f7-235">このパラメーターは、PowerShell 5.0 で追加され、再帰の深さを制御できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="709f7-235">This parameter was added in PowerShell 5.0 and enables you to control the depth of recursion.</span></span> <span data-ttu-id="709f7-236">既定では、 `Get-ChildItem` 親ディレクトリの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="709f7-236">By default, `Get-ChildItem` displays the contents of the parent directory.</span></span> <span data-ttu-id="709f7-237">**Depth** パラメーターは、再帰に含まれるサブディレクトリレベルの数を決定し、その内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-237">The **Depth** parameter determines the number of subdirectory levels that are included in the recursion and displays the contents.</span></span>

<span data-ttu-id="709f7-238">たとえば、には、 `Depth 2` **パス** パラメーターのディレクトリ、サブディレクトリの最初のレベル、およびサブディレクトリの第2レベルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="709f7-238">For example, `Depth 2` includes the **Path** parameter's directory, first level of subdirectories, and second level of subdirectories.</span></span> <span data-ttu-id="709f7-239">既定では、ディレクトリ名とファイル名が出力に含まれます。</span><span class="sxs-lookup"><span data-stu-id="709f7-239">By default directory names and filenames are included in the output.</span></span>

> [!NOTE]
> <span data-ttu-id="709f7-240">PowerShell または **cmd.exe** の Windows コンピューターでは、 **tree.com** コマンドを使用してディレクトリ構造のグラフィカルビューを表示できます。</span><span class="sxs-lookup"><span data-stu-id="709f7-240">On a Windows computer from PowerShell or **cmd.exe** , you can display a graphical view of a directory structure with the **tree.com** command.</span></span>

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

### <span data-ttu-id="709f7-241">-Directory</span><span class="sxs-lookup"><span data-stu-id="709f7-241">-Directory</span></span>

<span data-ttu-id="709f7-242">ディレクトリの一覧を取得するには、 **directory パラメーターまた** は **Attributes** パラメーターを **directory** プロパティと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="709f7-242">To get a list of directories, use the **Directory** parameter or the **Attributes** parameter with the **Directory** property.</span></span> <span data-ttu-id="709f7-243">**再帰** パラメーターは **ディレクトリ** と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="709f7-243">You can use the **Recurse** parameter with **Directory**.</span></span>

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

### <span data-ttu-id="709f7-244">-除外</span><span class="sxs-lookup"><span data-stu-id="709f7-244">-Exclude</span></span>

<span data-ttu-id="709f7-245">このコマンドレットによって操作から除外されるプロパティまたはプロパティを、文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="709f7-245">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="709f7-246">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="709f7-246">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="709f7-247">パス要素またはパターン (やなど) を入力し `*.txt` `A*` ます。</span><span class="sxs-lookup"><span data-stu-id="709f7-247">Enter a path element or pattern, such as `*.txt` or `A*`.</span></span> <span data-ttu-id="709f7-248">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="709f7-248">Wildcard characters are accepted.</span></span>

<span data-ttu-id="709f7-249">Path パラメーターの末尾のアスタリスク ( `*` ) は省略可能です。 **Path**</span><span class="sxs-lookup"><span data-stu-id="709f7-249">A trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="709f7-250">たとえば、`-Path C:\Test\Logs` または `-Path C:\Test\Logs\*` です。</span><span class="sxs-lookup"><span data-stu-id="709f7-250">For example, `-Path C:\Test\Logs` or `-Path C:\Test\Logs\*`.</span></span> <span data-ttu-id="709f7-251">末尾のアスタリスク ( `*` ) が含まれている場合、コマンドは **Path** パラメーターのサブディレクトリに繰り返しします。</span><span class="sxs-lookup"><span data-stu-id="709f7-251">If a trailing asterisk (`*`) is included, the command recurses into the **Path** parameter's subdirectories.</span></span> <span data-ttu-id="709f7-252">アスタリスク () がない `*` 場合は、 **Path** パラメーターの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="709f7-252">Without the asterisk (`*`), the contents of the **Path** parameter are displayed.</span></span> <span data-ttu-id="709f7-253">詳細については、例5とメモのセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="709f7-253">More details are included in Example 5 and the Notes section.</span></span>

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

### <span data-ttu-id="709f7-254">-File</span><span class="sxs-lookup"><span data-stu-id="709f7-254">-File</span></span>

<span data-ttu-id="709f7-255">ファイルの一覧を取得するには、 **File** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="709f7-255">To get a list of files, use the **File** parameter.</span></span> <span data-ttu-id="709f7-256">**ファイル** では、 **再帰** パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="709f7-256">You can use the **Recurse** parameter with **File**.</span></span>

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

### <span data-ttu-id="709f7-257">-Filter</span><span class="sxs-lookup"><span data-stu-id="709f7-257">-Filter</span></span>

<span data-ttu-id="709f7-258">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="709f7-258">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="709f7-259">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターをサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="709f7-259">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="709f7-260">フィルターは他のパラメーターよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="709f7-260">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="709f7-261">プロバイダーは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得したときにフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="709f7-261">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="709f7-262">フィルター文字列は、ファイルを列挙するために .NET API に渡されます。</span><span class="sxs-lookup"><span data-stu-id="709f7-262">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="709f7-263">API では、とのワイルドカードのみがサポートさ `*` `?` れています。</span><span class="sxs-lookup"><span data-stu-id="709f7-263">The API only supports `*` and `?` wildcards.</span></span>

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

### <span data-ttu-id="709f7-264">-のシンボリックリンク</span><span class="sxs-lookup"><span data-stu-id="709f7-264">-FollowSymlink</span></span>

<span data-ttu-id="709f7-265">既定では、この `Get-ChildItem` コマンドレットは再帰中に検出されたディレクトリへのシンボリックリンクを表示しますが、それらのリンクには再帰しません。</span><span class="sxs-lookup"><span data-stu-id="709f7-265">By default, the `Get-ChildItem` cmdlet displays symbolic links to directories found during recursion, but doesn't recurse into them.</span></span> <span data-ttu-id="709f7-266">これらのシンボリックリンクを対象としているディレクトリを検索するに **は、のようにします** 。</span><span class="sxs-lookup"><span data-stu-id="709f7-266">Use the **FollowSymlink** parameter to search the directories that target those symbolic links.</span></span> <span data-ttu-id="709f7-267">この **引数は動的** パラメーターであり、 **FileSystem** プロバイダーでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="709f7-267">The **FollowSymlink** is a dynamic parameter and is supported only in the **FileSystem** provider.</span></span>

<span data-ttu-id="709f7-268">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="709f7-268">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="709f7-269">-Force</span><span class="sxs-lookup"><span data-stu-id="709f7-269">-Force</span></span>

<span data-ttu-id="709f7-270">隠しファイルやシステムファイルなど、ユーザーがアクセスできない項目をコマンドレットで取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="709f7-270">Allows the cmdlet to get items that otherwise can't be accessed by the user, such as hidden or system files.</span></span> <span data-ttu-id="709f7-271">**Force** パラメーターは、セキュリティ制限をオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="709f7-271">The **Force** parameter doesn't override security restrictions.</span></span> <span data-ttu-id="709f7-272">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="709f7-272">Implementation varies among providers.</span></span> <span data-ttu-id="709f7-273">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="709f7-273">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="709f7-274">-Hidden</span><span class="sxs-lookup"><span data-stu-id="709f7-274">-Hidden</span></span>

<span data-ttu-id="709f7-275">非表示の項目のみを取得するには、hidden パラメーターまたは **Attributes** パラメーターを **hidden** プロパティと共に **使用します** 。</span><span class="sxs-lookup"><span data-stu-id="709f7-275">To get only hidden items, use the **Hidden** parameter or the **Attributes** parameter with the **Hidden** property.</span></span> <span data-ttu-id="709f7-276">既定では、は非表示の `Get-ChildItem` 項目を表示しません。</span><span class="sxs-lookup"><span data-stu-id="709f7-276">By default, `Get-ChildItem` doesn't display hidden items.</span></span> <span data-ttu-id="709f7-277">**Force** パラメーターを使用して、非表示の項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="709f7-277">Use the **Force** parameter to get hidden items.</span></span>

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

### <span data-ttu-id="709f7-278">-Include</span><span class="sxs-lookup"><span data-stu-id="709f7-278">-Include</span></span>

<span data-ttu-id="709f7-279">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="709f7-279">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="709f7-280">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="709f7-280">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="709f7-281">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="709f7-281">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="709f7-282">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="709f7-282">Wildcard characters are permitted.</span></span> <span data-ttu-id="709f7-283">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="709f7-283">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="709f7-284">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="709f7-284">-LiteralPath</span></span>

<span data-ttu-id="709f7-285">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="709f7-285">Specifies a path to one or more locations.</span></span> <span data-ttu-id="709f7-286">**LiteralPath** の値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="709f7-286">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="709f7-287">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="709f7-287">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="709f7-288">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="709f7-288">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="709f7-289">単一引用符は、どの文字もエスケープシーケンスとして解釈されないように PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-289">Single quotation marks tell PowerShell to not interpret any characters as escape sequences.</span></span>

<span data-ttu-id="709f7-290">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="709f7-290">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="709f7-291">-Name</span><span class="sxs-lookup"><span data-stu-id="709f7-291">-Name</span></span>

<span data-ttu-id="709f7-292">場所内の項目の名前のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="709f7-292">Gets only the names of the items in the location.</span></span> <span data-ttu-id="709f7-293">出力は、他のコマンドにパイプラインから送信できる文字列オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="709f7-293">The output is a string object that can be sent down the pipeline to other commands.</span></span> <span data-ttu-id="709f7-294">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="709f7-294">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="709f7-295">-Path</span><span class="sxs-lookup"><span data-stu-id="709f7-295">-Path</span></span>

<span data-ttu-id="709f7-296">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="709f7-296">Specifies a path to one or more locations.</span></span> <span data-ttu-id="709f7-297">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="709f7-297">Wildcards are accepted.</span></span> <span data-ttu-id="709f7-298">既定の場所は、現在のディレクトリ ( `.` ) です。</span><span class="sxs-lookup"><span data-stu-id="709f7-298">The default location is the current directory (`.`).</span></span>

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

### <span data-ttu-id="709f7-299">-ReadOnly</span><span class="sxs-lookup"><span data-stu-id="709f7-299">-ReadOnly</span></span>

<span data-ttu-id="709f7-300">読み取り専用の項目のみを取得するには、 **readonly** パラメーターまたは **Attributes** パラメーター **readonly** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="709f7-300">To get only read-only items, use the **ReadOnly** parameter or the **Attributes** parameter **ReadOnly** property.</span></span>

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

### <span data-ttu-id="709f7-301">-再帰</span><span class="sxs-lookup"><span data-stu-id="709f7-301">-Recurse</span></span>

<span data-ttu-id="709f7-302">指定された場所にある項目と、その場所のすべての子項目にある項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="709f7-302">Gets the items in the specified locations and in all child items of the locations.</span></span>

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

### <span data-ttu-id="709f7-303">-System</span><span class="sxs-lookup"><span data-stu-id="709f7-303">-System</span></span>

<span data-ttu-id="709f7-304">システムファイルとディレクトリのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="709f7-304">Gets only system files and directories.</span></span> <span data-ttu-id="709f7-305">システムファイルとフォルダーのみを取得するには **、システムパラメーターまた** は **Attributes** パラメーター **システム** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="709f7-305">To get only system files and folders, use the **System** parameter or **Attributes** parameter **System** property.</span></span>

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

### <span data-ttu-id="709f7-306">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="709f7-306">CommonParameters</span></span>

<span data-ttu-id="709f7-307">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="709f7-307">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="709f7-308">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="709f7-308">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="709f7-309">入力</span><span class="sxs-lookup"><span data-stu-id="709f7-309">INPUTS</span></span>

### <span data-ttu-id="709f7-310">System.String</span><span class="sxs-lookup"><span data-stu-id="709f7-310">System.String</span></span>

<span data-ttu-id="709f7-311">パイプを使用して、パスを含む文字列をにパイプすることができ `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="709f7-311">You can pipe a string that contains a path to `Get-ChildItem`.</span></span>

## <span data-ttu-id="709f7-312">出力</span><span class="sxs-lookup"><span data-stu-id="709f7-312">OUTPUTS</span></span>

### <span data-ttu-id="709f7-313">System.Object</span><span class="sxs-lookup"><span data-stu-id="709f7-313">System.Object</span></span>

<span data-ttu-id="709f7-314">が返すオブジェクトの型 `Get-ChildItem` は、プロバイダーのドライブパス内のオブジェクトによって決まります。</span><span class="sxs-lookup"><span data-stu-id="709f7-314">The type of object that `Get-ChildItem` returns is determined by the objects in the provider drive path.</span></span>

### <span data-ttu-id="709f7-315">System.String</span><span class="sxs-lookup"><span data-stu-id="709f7-315">System.String</span></span>

<span data-ttu-id="709f7-316">**Name** パラメーターを使用すると、では、 `Get-ChildItem` オブジェクト名が文字列として返されます。</span><span class="sxs-lookup"><span data-stu-id="709f7-316">If you use the **Name** parameter, `Get-ChildItem` returns the object names as strings.</span></span>

## <span data-ttu-id="709f7-317">注</span><span class="sxs-lookup"><span data-stu-id="709f7-317">NOTES</span></span>

- <span data-ttu-id="709f7-318">`Get-ChildItem` は、組み込みのエイリアスである、、およびを使用して実行でき `ls` `dir` `gci` ます。</span><span class="sxs-lookup"><span data-stu-id="709f7-318">`Get-ChildItem` can be run using any of the built-in aliases, `ls`, `dir`, and `gci`.</span></span> <span data-ttu-id="709f7-319">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="709f7-319">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="709f7-320">`Get-ChildItem` 既定では、非表示の項目は取得されません。</span><span class="sxs-lookup"><span data-stu-id="709f7-320">`Get-ChildItem` doesn't get hidden items by default.</span></span> <span data-ttu-id="709f7-321">隠し項目を取得するには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="709f7-321">To get hidden items, use the **Force** parameter.</span></span>
- <span data-ttu-id="709f7-322">`Get-ChildItem`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="709f7-322">The `Get-ChildItem` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="709f7-323">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="709f7-323">To list the providers available in your session, type `Get-PSProvider`.</span></span>
  <span data-ttu-id="709f7-324">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="709f7-324">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="709f7-325">関連リンク</span><span class="sxs-lookup"><span data-stu-id="709f7-325">RELATED LINKS</span></span>

[<span data-ttu-id="709f7-326">about_Certificate_Provider</span><span class="sxs-lookup"><span data-stu-id="709f7-326">about_Certificate_Provider</span></span>](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)

[<span data-ttu-id="709f7-327">about_Providers</span><span class="sxs-lookup"><span data-stu-id="709f7-327">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="709f7-328">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="709f7-328">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="709f7-329">about_Registry_Provider</span><span class="sxs-lookup"><span data-stu-id="709f7-329">about_Registry_Provider</span></span>](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md)

[<span data-ttu-id="709f7-330">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="709f7-330">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="709f7-331">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="709f7-331">Get-Alias</span></span>](../Microsoft.PowerShell.Utility/Get-Alias.md)

[<span data-ttu-id="709f7-332">Get-Item</span><span class="sxs-lookup"><span data-stu-id="709f7-332">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="709f7-333">Get-Location</span><span class="sxs-lookup"><span data-stu-id="709f7-333">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="709f7-334">Get-Process</span><span class="sxs-lookup"><span data-stu-id="709f7-334">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="709f7-335">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="709f7-335">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="709f7-336">Split-Path</span><span class="sxs-lookup"><span data-stu-id="709f7-336">Split-Path</span></span>](Split-Path.md)

