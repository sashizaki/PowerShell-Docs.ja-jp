---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-item?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Item
ms.openlocfilehash: 8483fd374ee973256633e3711322561fc14b8ae2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216336"
---
# <span data-ttu-id="fcdf3-103">Get-Item</span><span class="sxs-lookup"><span data-stu-id="fcdf3-103">Get-Item</span></span>

## <span data-ttu-id="fcdf3-104">概要</span><span class="sxs-lookup"><span data-stu-id="fcdf3-104">SYNOPSIS</span></span>
<span data-ttu-id="fcdf3-105">指定された場所にある項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-105">Gets the item at the specified location.</span></span>

## <span data-ttu-id="fcdf3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fcdf3-106">SYNTAX</span></span>

### <span data-ttu-id="fcdf3-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="fcdf3-107">Path (Default)</span></span>

```
Get-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="fcdf3-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="fcdf3-108">LiteralPath</span></span>

```
Get-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Force] [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="fcdf3-109">Description</span><span class="sxs-lookup"><span data-stu-id="fcdf3-109">DESCRIPTION</span></span>

<span data-ttu-id="fcdf3-110">`Get-Item`コマンドレットは、指定した場所にある項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-110">The `Get-Item` cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="fcdf3-111">ワイルドカード文字 () を使用して `*` 項目のすべての内容を要求しない限り、その場所にある項目の内容は取得されません。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-111">It doesn't get the contents of the item at the location unless you use a wildcard character (`*`) to request all the contents of the item.</span></span>

<span data-ttu-id="fcdf3-112">このコマンドレットは、さまざまな種類のデータストア間を移動するために、PowerShell プロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-112">This cmdlet is used by PowerShell providers to navigate through different types of data stores.</span></span>

## <span data-ttu-id="fcdf3-113">例</span><span class="sxs-lookup"><span data-stu-id="fcdf3-113">EXAMPLES</span></span>

### <span data-ttu-id="fcdf3-114">例 1: 現在のディレクトリを取得する</span><span class="sxs-lookup"><span data-stu-id="fcdf3-114">Example 1: Get the current directory</span></span>

<span data-ttu-id="fcdf3-115">この例では、現在のディレクトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-115">This example gets the current directory.</span></span> <span data-ttu-id="fcdf3-116">ドット ('. ') は、その内容ではなく、現在の場所にある項目を表します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-116">The dot ('.') represents the item at the current location (not its contents).</span></span>

```powershell
Get-Item .
```

```output
Directory: C:\

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006  10:01 AM            ps-test
```

### <span data-ttu-id="fcdf3-117">例 2: 現在のディレクトリ内のすべての項目を取得する</span><span class="sxs-lookup"><span data-stu-id="fcdf3-117">Example 2: Get all the items in the current directory</span></span>

<span data-ttu-id="fcdf3-118">この例では、現在のディレクトリ内のすべての項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-118">This example gets all the items in the current directory.</span></span> <span data-ttu-id="fcdf3-119">ワイルドカード文字 ( `*` ) は、現在の項目のすべての内容を表します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-119">The wildcard character (`*`) represents all the contents of the current item.</span></span>

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

### <span data-ttu-id="fcdf3-120">例 3: ドライブの現在のディレクトリを取得する</span><span class="sxs-lookup"><span data-stu-id="fcdf3-120">Example 3: Get the current directory of a drive</span></span>

<span data-ttu-id="fcdf3-121">この例では、ドライブの現在のディレクトリを取得し `C:` ます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-121">This example gets the current directory of the `C:` drive.</span></span> <span data-ttu-id="fcdf3-122">ここで取得するオブジェクトは、ディレクトリのみを表します。その内容は表しません。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-122">The object that is retrieved represents only the directory, not its contents.</span></span>

```powershell
Get-Item C:\
```

### <span data-ttu-id="fcdf3-123">例 4: 指定したドライブの項目を取得する</span><span class="sxs-lookup"><span data-stu-id="fcdf3-123">Example 4: Get items in the specified drive</span></span>

<span data-ttu-id="fcdf3-124">この例では、ドライブ内の項目を取得し `C:` ます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-124">This example gets the items in the `C:` drive.</span></span> <span data-ttu-id="fcdf3-125">ワイルドカード文字 () は、コンテナー `*` だけでなく、コンテナー内のすべての項目を表します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-125">The wildcard character (`*`) represents all the items in the container, not just the container.</span></span>

```powershell
Get-Item C:\*
```

<span data-ttu-id="fcdf3-126">PowerShell では、1つのアスタリスク () を使用し `*` て、従来のではなくコンテンツを取得し `*.*` ます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-126">In PowerShell, use a single asterisk (`*`) to get contents, instead of the traditional `*.*`.</span></span> <span data-ttu-id="fcdf3-127">形式は文字どおりに解釈されるため、 `*.*` ドットなしでディレクトリやファイル名を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-127">The format is interpreted literally, so `*.*` wouldn't retrieve directories or filenames without a dot.</span></span>

### <span data-ttu-id="fcdf3-128">例 5: 指定したディレクトリ内のプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="fcdf3-128">Example 5: Get a property in the specified directory</span></span>

<span data-ttu-id="fcdf3-129">この例では、ディレクトリの **LastAccessTime** プロパティを取得し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-129">This example gets the **LastAccessTime** property of the `C:\Windows` directory.</span></span> <span data-ttu-id="fcdf3-130">**LastAccessTime** は、ファイルシステムディレクトリの1つのプロパティにすぎません。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-130">**LastAccessTime** is just one property of file system directories.</span></span> <span data-ttu-id="fcdf3-131">ディレクトリのすべてのプロパティを表示するには、「」と入力 `(Get-Item <directory-name>) | Get-Member` します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-131">To see all the properties of a directory, type `(Get-Item <directory-name>) | Get-Member`.</span></span>

```powershell
(Get-Item C:\Windows).LastAccessTime
```

### <span data-ttu-id="fcdf3-132">例 6: レジストリキーの内容を表示する</span><span class="sxs-lookup"><span data-stu-id="fcdf3-132">Example 6: Show the contents of a registry key</span></span>

<span data-ttu-id="fcdf3-133">この例は、 **Microsoft PowerShell** レジストリキーの内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-133">This example shows the contents of the **Microsoft.PowerShell** registry key.</span></span> <span data-ttu-id="fcdf3-134">このコマンドレットを PowerShell レジストリプロバイダーと共に使用して、レジストリキーとサブキーを取得でき `Get-ItemProperty` ますが、レジストリ値とデータを取得するには、コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-134">You can use this cmdlet with the PowerShell Registry provider to get registry keys and subkeys, but you must use the `Get-ItemProperty` cmdlet to get the registry values and data.</span></span>

```powershell
Get-Item HKLM:\Software\Microsoft\Powershell\1\Shellids\Microsoft.Powershell\
```

### <span data-ttu-id="fcdf3-135">例 7: 除外されているディレクトリ内の項目を取得する</span><span class="sxs-lookup"><span data-stu-id="fcdf3-135">Example 7: Get items in a directory that have an exclusion</span></span>

<span data-ttu-id="fcdf3-136">この例では、ドット () を含む名前を持つ Windows ディレクトリ内の項目を取得 `.` しますが、では開始しません `w*` 。この例は、パスにワイルドカード文字 () が含まれている場合にのみ機能し、 `*` 項目の内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-136">This example gets items in the Windows directory with names that include a dot (`.`), but don't begin with `w*`.This example works only when the path includes a wildcard character (`*`) to specify the contents of the item.</span></span>

```powershell
Get-Item C:\Windows\*.* -Exclude "w*"
```

### <span data-ttu-id="fcdf3-137">例 8: ハードリンク情報の取得</span><span class="sxs-lookup"><span data-stu-id="fcdf3-137">Example 8: Getting hardlink information</span></span>

<span data-ttu-id="fcdf3-138">PowerShell 6.2 では、リンクの情報を取得するために代替ビューが追加されました。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-138">In PowerShell 6.2, an alternate view was added to get hardlink information.</span></span> <span data-ttu-id="fcdf3-139">ハードリンク情報を取得するには、出力をにパイプ処理します。 `Format-Table -View childrenWithHardlink`</span><span class="sxs-lookup"><span data-stu-id="fcdf3-139">To get the hardlink information, pipe the output to `Format-Table -View childrenWithHardlink`</span></span>

```powershell
Get-Item -Path C:\PathWhichIsAHardLink | Format-Table -View childrenWithHardlink
```

## <span data-ttu-id="fcdf3-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fcdf3-140">PARAMETERS</span></span>

### <span data-ttu-id="fcdf3-141">-ストリーム</span><span class="sxs-lookup"><span data-stu-id="fcdf3-141">-Stream</span></span>

<span data-ttu-id="fcdf3-142">指定した代替 NTFS ファイル システムをファイルから取得します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-142">Gets the specified alternate NTFS file stream from the file.</span></span> <span data-ttu-id="fcdf3-143">ストリーム名を入力します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-143">Enter the stream name.</span></span> <span data-ttu-id="fcdf3-144">ワイルドカードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-144">Wildcards are supported.</span></span> <span data-ttu-id="fcdf3-145">すべてのストリームを取得するには、アスタリスク () を使用し `*` ます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-145">To get all streams, use an asterisk (`*`).</span></span> <span data-ttu-id="fcdf3-146">このパラメーターはフォルダーでは無効です。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-146">This parameter isn't valid on folders.</span></span>

<span data-ttu-id="fcdf3-147">**Stream** は、 **FileSystem** プロバイダーによってコマンドレットに追加される動的パラメーターです `Get-Item` 。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-147">**Stream** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Item` cmdlet.</span></span>
<span data-ttu-id="fcdf3-148">このパラメーターはファイル システム ドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-148">This parameter works only in file system drives.</span></span>

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

### <span data-ttu-id="fcdf3-149">-Credential</span><span class="sxs-lookup"><span data-stu-id="fcdf3-149">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="fcdf3-150">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-150">This parameter isn't supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="fcdf3-151">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-151">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="fcdf3-152">-除外</span><span class="sxs-lookup"><span data-stu-id="fcdf3-152">-Exclude</span></span>

<span data-ttu-id="fcdf3-153">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-153">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="fcdf3-154">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-154">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="fcdf3-155">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-155">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="fcdf3-156">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-156">Wildcard characters are permitted.</span></span> <span data-ttu-id="fcdf3-157">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-157">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="fcdf3-158">-Filter</span><span class="sxs-lookup"><span data-stu-id="fcdf3-158">-Filter</span></span>

<span data-ttu-id="fcdf3-159">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-159">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="fcdf3-160">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターをサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-160">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="fcdf3-161">フィルターは他のパラメーターよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-161">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="fcdf3-162">プロバイダーは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得したときにフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-162">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="fcdf3-163">フィルター文字列は、ファイルを列挙するために .NET API に渡されます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-163">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="fcdf3-164">API では、とのワイルドカードのみがサポートさ `*` `?` れています。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-164">The API only supports `*` and `?` wildcards.</span></span>

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

### <span data-ttu-id="fcdf3-165">-Force</span><span class="sxs-lookup"><span data-stu-id="fcdf3-165">-Force</span></span>

<span data-ttu-id="fcdf3-166">このコマンドレットが、非表示の項目など、アクセスできない項目を取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-166">Indicates that this cmdlet gets items that can't otherwise be accessed, such as hidden items.</span></span>
<span data-ttu-id="fcdf3-167">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-167">Implementation varies from provider to provider.</span></span> <span data-ttu-id="fcdf3-168">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-168">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span> <span data-ttu-id="fcdf3-169">**Force** パラメーターを使用しても、コマンドレットはセキュリティ制限を上書きできません。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-169">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

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

### <span data-ttu-id="fcdf3-170">-Include</span><span class="sxs-lookup"><span data-stu-id="fcdf3-170">-Include</span></span>

<span data-ttu-id="fcdf3-171">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-171">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="fcdf3-172">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-172">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="fcdf3-173">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-173">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="fcdf3-174">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-174">Wildcard characters are permitted.</span></span> <span data-ttu-id="fcdf3-175">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-175">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="fcdf3-176">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="fcdf3-176">-LiteralPath</span></span>

<span data-ttu-id="fcdf3-177">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-177">Specifies a path to one or more locations.</span></span> <span data-ttu-id="fcdf3-178">**LiteralPath** の値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-178">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="fcdf3-179">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-179">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="fcdf3-180">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-180">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="fcdf3-181">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-181">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="fcdf3-182">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-182">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="fcdf3-183">-Path</span><span class="sxs-lookup"><span data-stu-id="fcdf3-183">-Path</span></span>

<span data-ttu-id="fcdf3-184">項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-184">Specifies the path to an item.</span></span> <span data-ttu-id="fcdf3-185">このコマンドレットは、指定した場所にある項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-185">This cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="fcdf3-186">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-186">Wildcard characters are permitted.</span></span> <span data-ttu-id="fcdf3-187">このパラメーターは必須ですが、パラメーター名の **パス** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-187">This parameter is required, but the parameter name **Path** is optional.</span></span>

<span data-ttu-id="fcdf3-188">現在の場所を指定するには、ドット () を使用し `.` ます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-188">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="fcdf3-189">現在の場所のすべての項目を指定するには、ワイルドカード文字 ( `*` ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-189">Use the wildcard character (`*`) to specify all the items in the current location.</span></span>

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

### <span data-ttu-id="fcdf3-190">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fcdf3-190">CommonParameters</span></span>

<span data-ttu-id="fcdf3-191">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-191">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="fcdf3-192">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-192">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="fcdf3-193">入力</span><span class="sxs-lookup"><span data-stu-id="fcdf3-193">INPUTS</span></span>

### <span data-ttu-id="fcdf3-194">System.String</span><span class="sxs-lookup"><span data-stu-id="fcdf3-194">System.String</span></span>

<span data-ttu-id="fcdf3-195">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-195">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="fcdf3-196">出力</span><span class="sxs-lookup"><span data-stu-id="fcdf3-196">OUTPUTS</span></span>

### <span data-ttu-id="fcdf3-197">System.Object</span><span class="sxs-lookup"><span data-stu-id="fcdf3-197">System.Object</span></span>

<span data-ttu-id="fcdf3-198">このコマンドレットは、取得したオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-198">This cmdlet returns the objects that it gets.</span></span> <span data-ttu-id="fcdf3-199">この型は、パス内のオブジェクトの型によって決まります。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-199">The type is determined by the type of objects in the path.</span></span>

## <span data-ttu-id="fcdf3-200">注</span><span class="sxs-lookup"><span data-stu-id="fcdf3-200">NOTES</span></span>

<span data-ttu-id="fcdf3-201">このコマンドレットには、内容ではなく項目だけを取得するため、 **再帰** パラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-201">This cmdlet does not have a **Recurse** parameter, because it gets only an item, not its contents.</span></span>
<span data-ttu-id="fcdf3-202">項目の内容を再帰的に取得するには、を使用し `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-202">To get the contents of an item recursively, use `Get-ChildItem`.</span></span>

<span data-ttu-id="fcdf3-203">レジストリ内を移動するには、このコマンドレットを使用してレジストリキーを取得し、を使用して `Get-ItemProperty` レジストリ値とデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-203">To navigate through the registry, use this cmdlet to get registry keys and the `Get-ItemProperty` to get registry values and data.</span></span> <span data-ttu-id="fcdf3-204">レジストリ値はレジストリ キーのプロパティと見なされます。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-204">The registry values are considered to be properties of the registry key.</span></span>
  
<span data-ttu-id="fcdf3-205">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-205">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="fcdf3-206">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-206">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="fcdf3-207">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcdf3-207">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="fcdf3-208">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fcdf3-208">RELATED LINKS</span></span>

[<span data-ttu-id="fcdf3-209">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="fcdf3-209">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="fcdf3-210">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="fcdf3-210">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="fcdf3-211">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="fcdf3-211">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="fcdf3-212">Move-Item</span><span class="sxs-lookup"><span data-stu-id="fcdf3-212">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="fcdf3-213">New-Item</span><span class="sxs-lookup"><span data-stu-id="fcdf3-213">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="fcdf3-214">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="fcdf3-214">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="fcdf3-215">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="fcdf3-215">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="fcdf3-216">Set-Item</span><span class="sxs-lookup"><span data-stu-id="fcdf3-216">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="fcdf3-217">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="fcdf3-217">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="fcdf3-218">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="fcdf3-218">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="fcdf3-219">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="fcdf3-219">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="fcdf3-220">about_Providers</span><span class="sxs-lookup"><span data-stu-id="fcdf3-220">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
