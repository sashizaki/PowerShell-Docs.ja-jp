---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Item
ms.openlocfilehash: d034baf42f064149696f54a198dc97d7ee4e8fe7
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "97693078"
---
# <span data-ttu-id="283e7-103">Get-Item</span><span class="sxs-lookup"><span data-stu-id="283e7-103">Get-Item</span></span>

## <span data-ttu-id="283e7-104">概要</span><span class="sxs-lookup"><span data-stu-id="283e7-104">SYNOPSIS</span></span>
<span data-ttu-id="283e7-105">指定された場所にある項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="283e7-105">Gets the item at the specified location.</span></span>

## <span data-ttu-id="283e7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="283e7-106">SYNTAX</span></span>

### <span data-ttu-id="283e7-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="283e7-107">Path (Default)</span></span>

```
Get-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="283e7-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="283e7-108">LiteralPath</span></span>

```
Get-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Force] [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="283e7-109">Description</span><span class="sxs-lookup"><span data-stu-id="283e7-109">DESCRIPTION</span></span>

<span data-ttu-id="283e7-110">`Get-Item`コマンドレットは、指定した場所にある項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="283e7-110">The `Get-Item` cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="283e7-111">ワイルドカード文字 () を使用して `*` 項目のすべての内容を要求しない限り、その場所にある項目の内容は取得されません。</span><span class="sxs-lookup"><span data-stu-id="283e7-111">It doesn't get the contents of the item at the location unless you use a wildcard character (`*`) to request all the contents of the item.</span></span>

<span data-ttu-id="283e7-112">このコマンドレットは、さまざまな種類のデータストア間を移動するために、PowerShell プロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="283e7-112">This cmdlet is used by PowerShell providers to navigate through different types of data stores.</span></span>

## <span data-ttu-id="283e7-113">例</span><span class="sxs-lookup"><span data-stu-id="283e7-113">EXAMPLES</span></span>

### <span data-ttu-id="283e7-114">例 1: 現在のディレクトリを取得する</span><span class="sxs-lookup"><span data-stu-id="283e7-114">Example 1: Get the current directory</span></span>

<span data-ttu-id="283e7-115">この例では、現在のディレクトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="283e7-115">This example gets the current directory.</span></span> <span data-ttu-id="283e7-116">ドット ('. ') は、その内容ではなく、現在の場所にある項目を表します。</span><span class="sxs-lookup"><span data-stu-id="283e7-116">The dot ('.') represents the item at the current location (not its contents).</span></span>

```powershell
Get-Item .
```

```output
Directory: C:\

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006  10:01 AM            ps-test
```

### <span data-ttu-id="283e7-117">例 2: 現在のディレクトリ内のすべての項目を取得する</span><span class="sxs-lookup"><span data-stu-id="283e7-117">Example 2: Get all the items in the current directory</span></span>

<span data-ttu-id="283e7-118">この例では、現在のディレクトリ内のすべての項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="283e7-118">This example gets all the items in the current directory.</span></span> <span data-ttu-id="283e7-119">ワイルドカード文字 ( `*` ) は、現在の項目のすべての内容を表します。</span><span class="sxs-lookup"><span data-stu-id="283e7-119">The wildcard character (`*`) represents all the contents of the current item.</span></span>

```powershell
Get-Item *
```

```output
Directory: C:\ps-test

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006   9:29 AM            Logs
d----         7/26/2006   9:26 AM            Recs
-a---         7/26/2006   9:28 AM         80 date.csv
-a---         7/26/2006  10:01 AM         30 filenoext
-a---         7/26/2006   9:30 AM      11472 process.doc
-a---         7/14/2006  10:47 AM         30 test.txt
```

### <span data-ttu-id="283e7-120">例 3: ドライブの現在のディレクトリを取得する</span><span class="sxs-lookup"><span data-stu-id="283e7-120">Example 3: Get the current directory of a drive</span></span>

<span data-ttu-id="283e7-121">この例では、ドライブの現在のディレクトリを取得し `C:` ます。</span><span class="sxs-lookup"><span data-stu-id="283e7-121">This example gets the current directory of the `C:` drive.</span></span> <span data-ttu-id="283e7-122">ここで取得するオブジェクトは、ディレクトリのみを表します。その内容は表しません。</span><span class="sxs-lookup"><span data-stu-id="283e7-122">The object that is retrieved represents only the directory, not its contents.</span></span>

```powershell
Get-Item C:\
```

### <span data-ttu-id="283e7-123">例 4: 指定したドライブの項目を取得する</span><span class="sxs-lookup"><span data-stu-id="283e7-123">Example 4: Get items in the specified drive</span></span>

<span data-ttu-id="283e7-124">この例では、ドライブ内の項目を取得し `C:` ます。</span><span class="sxs-lookup"><span data-stu-id="283e7-124">This example gets the items in the `C:` drive.</span></span> <span data-ttu-id="283e7-125">ワイルドカード文字 () は、コンテナー `*` だけでなく、コンテナー内のすべての項目を表します。</span><span class="sxs-lookup"><span data-stu-id="283e7-125">The wildcard character (`*`) represents all the items in the container, not just the container.</span></span>

```powershell
Get-Item C:\*
```

<span data-ttu-id="283e7-126">PowerShell では、1つのアスタリスク () を使用し `*` て、従来のではなくコンテンツを取得し `*.*` ます。</span><span class="sxs-lookup"><span data-stu-id="283e7-126">In PowerShell, use a single asterisk (`*`) to get contents, instead of the traditional `*.*`.</span></span> <span data-ttu-id="283e7-127">形式は文字どおりに解釈されるため、 `*.*` ドットなしでディレクトリやファイル名を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="283e7-127">The format is interpreted literally, so `*.*` wouldn't retrieve directories or filenames without a dot.</span></span>

### <span data-ttu-id="283e7-128">例 5: 指定したディレクトリ内のプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="283e7-128">Example 5: Get a property in the specified directory</span></span>

<span data-ttu-id="283e7-129">この例では、ディレクトリの **LastAccessTime** プロパティを取得し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="283e7-129">This example gets the **LastAccessTime** property of the `C:\Windows` directory.</span></span> <span data-ttu-id="283e7-130">**LastAccessTime** は、ファイルシステムディレクトリの1つのプロパティにすぎません。</span><span class="sxs-lookup"><span data-stu-id="283e7-130">**LastAccessTime** is just one property of file system directories.</span></span> <span data-ttu-id="283e7-131">ディレクトリのすべてのプロパティを表示するには、「」と入力 `(Get-Item <directory-name>) | Get-Member` します。</span><span class="sxs-lookup"><span data-stu-id="283e7-131">To see all the properties of a directory, type `(Get-Item <directory-name>) | Get-Member`.</span></span>

```powershell
(Get-Item C:\Windows).LastAccessTime
```

### <span data-ttu-id="283e7-132">例 6: レジストリキーの内容を表示する</span><span class="sxs-lookup"><span data-stu-id="283e7-132">Example 6: Show the contents of a registry key</span></span>

<span data-ttu-id="283e7-133">この例は、 **Microsoft PowerShell** レジストリキーの内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="283e7-133">This example shows the contents of the **Microsoft.PowerShell** registry key.</span></span> <span data-ttu-id="283e7-134">このコマンドレットを PowerShell レジストリプロバイダーと共に使用して、レジストリキーとサブキーを取得でき `Get-ItemProperty` ますが、レジストリ値とデータを取得するには、コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="283e7-134">You can use this cmdlet with the PowerShell Registry provider to get registry keys and subkeys, but you must use the `Get-ItemProperty` cmdlet to get the registry values and data.</span></span>

```powershell
Get-Item HKLM:\Software\Microsoft\Powershell\1\Shellids\Microsoft.Powershell\
```

### <span data-ttu-id="283e7-135">例 7: 除外されているディレクトリ内の項目を取得する</span><span class="sxs-lookup"><span data-stu-id="283e7-135">Example 7: Get items in a directory that have an exclusion</span></span>

<span data-ttu-id="283e7-136">この例では、ドット () を含む名前を持つ Windows ディレクトリ内の項目を取得 `.` しますが、では開始しません `w*` 。この例は、パスにワイルドカード文字 () が含まれている場合にのみ機能し、 `*` 項目の内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="283e7-136">This example gets items in the Windows directory with names that include a dot (`.`), but don't begin with `w*`.This example works only when the path includes a wildcard character (`*`) to specify the contents of the item.</span></span>

```powershell
Get-Item C:\Windows\*.* -Exclude "w*"
```

### <span data-ttu-id="283e7-137">例 8: ハードリンク情報の取得</span><span class="sxs-lookup"><span data-stu-id="283e7-137">Example 8: Getting hardlink information</span></span>

<span data-ttu-id="283e7-138">PowerShell 6.2 では、リンクの情報を取得するために代替ビューが追加されました。</span><span class="sxs-lookup"><span data-stu-id="283e7-138">In PowerShell 6.2, an alternate view was added to get hardlink information.</span></span> <span data-ttu-id="283e7-139">ハードリンク情報を取得するには、出力をにパイプ処理します。 `Format-Table -View childrenWithHardlink`</span><span class="sxs-lookup"><span data-stu-id="283e7-139">To get the hardlink information, pipe the output to `Format-Table -View childrenWithHardlink`</span></span>

```powershell
Get-Item -Path C:\PathWhichIsAHardLink | Format-Table -View childrenWithHardlink
```

### <span data-ttu-id="283e7-140">例 9: Windows 以外のオペレーティングシステムの出力</span><span class="sxs-lookup"><span data-stu-id="283e7-140">Example 9: Output for Non-Windows Operating Systems</span></span>

<span data-ttu-id="283e7-141">Unix システムの PowerShell 7.1 では、 `Get-Item` コマンドレットは unix のような出力を提供します。</span><span class="sxs-lookup"><span data-stu-id="283e7-141">In PowerShell 7.1 on Unix systems, the `Get-Item` cmdlet provides Unix-like output:</span></span>

```powershell
PS> Get-Item /Users
```

```Output
    Directory: /

UnixMode    User  Group   LastWriteTime      Size  Name
--------    ----  -----   -------------      ----  ----
drwxr-xr-x  root  admin   12/20/2019 11:46   192   Users
```

<span data-ttu-id="283e7-142">出力の一部である新しいプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="283e7-142">The new properties that are now part of the output are:</span></span>

- <span data-ttu-id="283e7-143">**UnixMode** は、Unix システムで表されるファイルのアクセス許可です。</span><span class="sxs-lookup"><span data-stu-id="283e7-143">**UnixMode** is the file permissions as represented on a Unix system</span></span>
- <span data-ttu-id="283e7-144">**ユーザー** はファイルの所有者です</span><span class="sxs-lookup"><span data-stu-id="283e7-144">**User** is the file owner</span></span>
- <span data-ttu-id="283e7-145">**グループは** グループの所有者です</span><span class="sxs-lookup"><span data-stu-id="283e7-145">**Group** is the group owner</span></span>
- <span data-ttu-id="283e7-146">**サイズ** は、Unix システムで表されるファイルまたはディレクトリのサイズです。</span><span class="sxs-lookup"><span data-stu-id="283e7-146">**Size** is the size of the file or directory as represented on a Unix system</span></span>

> [!NOTE]
> <span data-ttu-id="283e7-147">この機能は、PowerShell 7.1 の試験段階からメインストリームに移行されました。</span><span class="sxs-lookup"><span data-stu-id="283e7-147">This feature was moved from experimental to mainstream in PowerShell 7.1.</span></span>

## <span data-ttu-id="283e7-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="283e7-148">PARAMETERS</span></span>

### <span data-ttu-id="283e7-149">-ストリーム</span><span class="sxs-lookup"><span data-stu-id="283e7-149">-Stream</span></span>

> [!NOTE]
> <span data-ttu-id="283e7-150">このパラメーターは Windows でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="283e7-150">This Parameter is only available on Windows.</span></span>

<span data-ttu-id="283e7-151">指定した代替 NTFS ファイル システムをファイルから取得します。</span><span class="sxs-lookup"><span data-stu-id="283e7-151">Gets the specified alternate NTFS file stream from the file.</span></span> <span data-ttu-id="283e7-152">ストリーム名を入力します。</span><span class="sxs-lookup"><span data-stu-id="283e7-152">Enter the stream name.</span></span> <span data-ttu-id="283e7-153">ワイルドカードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="283e7-153">Wildcards are supported.</span></span> <span data-ttu-id="283e7-154">すべてのストリームを取得するには、アスタリスク () を使用し `*` ます。</span><span class="sxs-lookup"><span data-stu-id="283e7-154">To get all streams, use an asterisk (`*`).</span></span> <span data-ttu-id="283e7-155">このパラメーターはフォルダーでは無効です。</span><span class="sxs-lookup"><span data-stu-id="283e7-155">This parameter isn't valid on folders.</span></span>

<span data-ttu-id="283e7-156">**Stream** は、 **FileSystem** プロバイダーによってコマンドレットに追加される動的パラメーターです `Get-Item` 。</span><span class="sxs-lookup"><span data-stu-id="283e7-156">**Stream** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Item` cmdlet.</span></span>
<span data-ttu-id="283e7-157">このパラメーターはファイル システム ドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="283e7-157">This parameter works only in file system drives.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: No alternate file streams
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="283e7-158">-Credential</span><span class="sxs-lookup"><span data-stu-id="283e7-158">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="283e7-159">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="283e7-159">This parameter isn't supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="283e7-160">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="283e7-160">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="283e7-161">-除外</span><span class="sxs-lookup"><span data-stu-id="283e7-161">-Exclude</span></span>

<span data-ttu-id="283e7-162">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="283e7-162">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="283e7-163">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="283e7-163">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="283e7-164">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="283e7-164">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="283e7-165">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="283e7-165">Wildcard characters are permitted.</span></span> <span data-ttu-id="283e7-166">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="283e7-166">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="283e7-167">-Filter</span><span class="sxs-lookup"><span data-stu-id="283e7-167">-Filter</span></span>

<span data-ttu-id="283e7-168">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="283e7-168">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="283e7-169">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターをサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="283e7-169">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="283e7-170">フィルターは他のパラメーターよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="283e7-170">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="283e7-171">プロバイダーは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得したときにフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="283e7-171">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="283e7-172">フィルター文字列は、ファイルを列挙するために .NET API に渡されます。</span><span class="sxs-lookup"><span data-stu-id="283e7-172">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="283e7-173">API では、とのワイルドカードのみがサポートさ `*` `?` れています。</span><span class="sxs-lookup"><span data-stu-id="283e7-173">The API only supports `*` and `?` wildcards.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="283e7-174">-Force</span><span class="sxs-lookup"><span data-stu-id="283e7-174">-Force</span></span>

<span data-ttu-id="283e7-175">このコマンドレットが、非表示の項目など、アクセスできない項目を取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="283e7-175">Indicates that this cmdlet gets items that can't otherwise be accessed, such as hidden items.</span></span>
<span data-ttu-id="283e7-176">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="283e7-176">Implementation varies from provider to provider.</span></span> <span data-ttu-id="283e7-177">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="283e7-177">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span> <span data-ttu-id="283e7-178">**Force** パラメーターを使用しても、コマンドレットはセキュリティ制限を上書きできません。</span><span class="sxs-lookup"><span data-stu-id="283e7-178">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

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

### <span data-ttu-id="283e7-179">-Include</span><span class="sxs-lookup"><span data-stu-id="283e7-179">-Include</span></span>

<span data-ttu-id="283e7-180">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="283e7-180">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="283e7-181">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="283e7-181">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="283e7-182">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="283e7-182">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="283e7-183">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="283e7-183">Wildcard characters are permitted.</span></span> <span data-ttu-id="283e7-184">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="283e7-184">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="283e7-185">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="283e7-185">-LiteralPath</span></span>

<span data-ttu-id="283e7-186">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="283e7-186">Specifies a path to one or more locations.</span></span> <span data-ttu-id="283e7-187">**LiteralPath** の値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="283e7-187">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="283e7-188">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="283e7-188">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="283e7-189">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="283e7-189">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="283e7-190">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="283e7-190">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="283e7-191">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="283e7-191">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="283e7-192">-Path</span><span class="sxs-lookup"><span data-stu-id="283e7-192">-Path</span></span>

<span data-ttu-id="283e7-193">項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="283e7-193">Specifies the path to an item.</span></span> <span data-ttu-id="283e7-194">このコマンドレットは、指定した場所にある項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="283e7-194">This cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="283e7-195">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="283e7-195">Wildcard characters are permitted.</span></span> <span data-ttu-id="283e7-196">このパラメーターは必須ですが、パラメーター名の **パス** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="283e7-196">This parameter is required, but the parameter name **Path** is optional.</span></span>

<span data-ttu-id="283e7-197">現在の場所を指定するには、ドット () を使用し `.` ます。</span><span class="sxs-lookup"><span data-stu-id="283e7-197">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="283e7-198">現在の場所のすべての項目を指定するには、ワイルドカード文字 ( `*` ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="283e7-198">Use the wildcard character (`*`) to specify all the items in the current location.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="283e7-199">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="283e7-199">CommonParameters</span></span>

<span data-ttu-id="283e7-200">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="283e7-200">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="283e7-201">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="283e7-201">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="283e7-202">入力</span><span class="sxs-lookup"><span data-stu-id="283e7-202">INPUTS</span></span>

### <span data-ttu-id="283e7-203">System.String</span><span class="sxs-lookup"><span data-stu-id="283e7-203">System.String</span></span>

<span data-ttu-id="283e7-204">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="283e7-204">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="283e7-205">出力</span><span class="sxs-lookup"><span data-stu-id="283e7-205">OUTPUTS</span></span>

### <span data-ttu-id="283e7-206">System.Object</span><span class="sxs-lookup"><span data-stu-id="283e7-206">System.Object</span></span>

<span data-ttu-id="283e7-207">このコマンドレットは、取得したオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="283e7-207">This cmdlet returns the objects that it gets.</span></span> <span data-ttu-id="283e7-208">この型は、パス内のオブジェクトの型によって決まります。</span><span class="sxs-lookup"><span data-stu-id="283e7-208">The type is determined by the type of objects in the path.</span></span>

## <span data-ttu-id="283e7-209">注</span><span class="sxs-lookup"><span data-stu-id="283e7-209">NOTES</span></span>

<span data-ttu-id="283e7-210">このコマンドレットには、内容ではなく項目だけを取得するため、 **再帰** パラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="283e7-210">This cmdlet does not have a **Recurse** parameter, because it gets only an item, not its contents.</span></span>
<span data-ttu-id="283e7-211">項目の内容を再帰的に取得するには、を使用し `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="283e7-211">To get the contents of an item recursively, use `Get-ChildItem`.</span></span>

<span data-ttu-id="283e7-212">レジストリ内を移動するには、このコマンドレットを使用してレジストリキーを取得し、を使用して `Get-ItemProperty` レジストリ値とデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="283e7-212">To navigate through the registry, use this cmdlet to get registry keys and the `Get-ItemProperty` to get registry values and data.</span></span> <span data-ttu-id="283e7-213">レジストリ値はレジストリ キーのプロパティと見なされます。</span><span class="sxs-lookup"><span data-stu-id="283e7-213">The registry values are considered to be properties of the registry key.</span></span>

<span data-ttu-id="283e7-214">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="283e7-214">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="283e7-215">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="283e7-215">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="283e7-216">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="283e7-216">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="283e7-217">関連リンク</span><span class="sxs-lookup"><span data-stu-id="283e7-217">RELATED LINKS</span></span>

[<span data-ttu-id="283e7-218">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="283e7-218">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="283e7-219">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="283e7-219">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="283e7-220">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="283e7-220">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="283e7-221">Move-Item</span><span class="sxs-lookup"><span data-stu-id="283e7-221">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="283e7-222">New-Item</span><span class="sxs-lookup"><span data-stu-id="283e7-222">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="283e7-223">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="283e7-223">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="283e7-224">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="283e7-224">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="283e7-225">Set-Item</span><span class="sxs-lookup"><span data-stu-id="283e7-225">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="283e7-226">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="283e7-226">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="283e7-227">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="283e7-227">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="283e7-228">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="283e7-228">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="283e7-229">about_Providers</span><span class="sxs-lookup"><span data-stu-id="283e7-229">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

