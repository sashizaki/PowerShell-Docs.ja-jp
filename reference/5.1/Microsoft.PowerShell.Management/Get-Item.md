---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Item
ms.openlocfilehash: 1498c7eb254e0d21b108c4016d8b737d5b33298d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215424"
---
# <span data-ttu-id="9a791-103">Get-Item</span><span class="sxs-lookup"><span data-stu-id="9a791-103">Get-Item</span></span>

## <span data-ttu-id="9a791-104">概要</span><span class="sxs-lookup"><span data-stu-id="9a791-104">SYNOPSIS</span></span>
<span data-ttu-id="9a791-105">指定された場所にある項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="9a791-105">Gets the item at the specified location.</span></span>

## <span data-ttu-id="9a791-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9a791-106">SYNTAX</span></span>

### <span data-ttu-id="9a791-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="9a791-107">Path (Default)</span></span>

```
Get-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-UseTransaction] [-Stream <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="9a791-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9a791-108">LiteralPath</span></span>

```
Get-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-UseTransaction] [-Stream <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="9a791-109">Description</span><span class="sxs-lookup"><span data-stu-id="9a791-109">DESCRIPTION</span></span>

<span data-ttu-id="9a791-110">`Get-Item`コマンドレットは、指定した場所にある項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="9a791-110">The `Get-Item` cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="9a791-111">ワイルドカード文字 () を使用して `*` 項目のすべての内容を要求しない限り、その場所にある項目の内容は取得されません。</span><span class="sxs-lookup"><span data-stu-id="9a791-111">It doesn't get the contents of the item at the location unless you use a wildcard character (`*`) to request all the contents of the item.</span></span>

<span data-ttu-id="9a791-112">このコマンドレットは、さまざまな種類のデータストア間を移動するために、PowerShell プロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="9a791-112">This cmdlet is used by PowerShell providers to navigate through different types of data stores.</span></span>

## <span data-ttu-id="9a791-113">例</span><span class="sxs-lookup"><span data-stu-id="9a791-113">EXAMPLES</span></span>

### <span data-ttu-id="9a791-114">例 1: 現在のディレクトリを取得する</span><span class="sxs-lookup"><span data-stu-id="9a791-114">Example 1: Get the current directory</span></span>

<span data-ttu-id="9a791-115">この例では、現在のディレクトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="9a791-115">This example gets the current directory.</span></span> <span data-ttu-id="9a791-116">ドット ('. ') は、その内容ではなく、現在の場所にある項目を表します。</span><span class="sxs-lookup"><span data-stu-id="9a791-116">The dot ('.') represents the item at the current location (not its contents).</span></span>

```powershell
Get-Item .
```

```output
Directory: C:\

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006  10:01 AM            ps-test
```

### <span data-ttu-id="9a791-117">例 2: 現在のディレクトリ内のすべての項目を取得する</span><span class="sxs-lookup"><span data-stu-id="9a791-117">Example 2: Get all the items in the current directory</span></span>

<span data-ttu-id="9a791-118">この例では、現在のディレクトリ内のすべての項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="9a791-118">This example gets all the items in the current directory.</span></span> <span data-ttu-id="9a791-119">ワイルドカード文字 ( `*` ) は、現在の項目のすべての内容を表します。</span><span class="sxs-lookup"><span data-stu-id="9a791-119">The wildcard character (`*`) represents all the contents of the current item.</span></span>

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

### <span data-ttu-id="9a791-120">例 3: ドライブの現在のディレクトリを取得する</span><span class="sxs-lookup"><span data-stu-id="9a791-120">Example 3: Get the current directory of a drive</span></span>

<span data-ttu-id="9a791-121">この例では、ドライブの現在のディレクトリを取得し `C:` ます。</span><span class="sxs-lookup"><span data-stu-id="9a791-121">This example gets the current directory of the `C:` drive.</span></span> <span data-ttu-id="9a791-122">ここで取得するオブジェクトは、ディレクトリのみを表します。その内容は表しません。</span><span class="sxs-lookup"><span data-stu-id="9a791-122">The object that is retrieved represents only the directory, not its contents.</span></span>

```powershell
Get-Item C:\
```

### <span data-ttu-id="9a791-123">例 4: 指定したドライブの項目を取得する</span><span class="sxs-lookup"><span data-stu-id="9a791-123">Example 4: Get items in the specified drive</span></span>

<span data-ttu-id="9a791-124">この例では、ドライブ内の項目を取得し `C:` ます。</span><span class="sxs-lookup"><span data-stu-id="9a791-124">This example gets the items in the `C:` drive.</span></span> <span data-ttu-id="9a791-125">ワイルドカード文字 () は、コンテナー `*` だけでなく、コンテナー内のすべての項目を表します。</span><span class="sxs-lookup"><span data-stu-id="9a791-125">The wildcard character (`*`) represents all the items in the container, not just the container.</span></span>

```powershell
Get-Item C:\*
```

<span data-ttu-id="9a791-126">PowerShell では、1つのアスタリスク () を使用し `*` て、従来のではなくコンテンツを取得し `*.*` ます。</span><span class="sxs-lookup"><span data-stu-id="9a791-126">In PowerShell, use a single asterisk (`*`) to get contents, instead of the traditional `*.*`.</span></span> <span data-ttu-id="9a791-127">形式は文字どおりに解釈されるため、 `*.*` ドットなしでディレクトリやファイル名を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="9a791-127">The format is interpreted literally, so `*.*` wouldn't retrieve directories or filenames without a dot.</span></span>

### <span data-ttu-id="9a791-128">例 5: 指定したディレクトリ内のプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="9a791-128">Example 5: Get a property in the specified directory</span></span>

<span data-ttu-id="9a791-129">この例では、ディレクトリの **LastAccessTime** プロパティを取得し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="9a791-129">This example gets the **LastAccessTime** property of the `C:\Windows` directory.</span></span> <span data-ttu-id="9a791-130">**LastAccessTime** は、ファイルシステムディレクトリの1つのプロパティにすぎません。</span><span class="sxs-lookup"><span data-stu-id="9a791-130">**LastAccessTime** is just one property of file system directories.</span></span> <span data-ttu-id="9a791-131">ディレクトリのすべてのプロパティを表示するには、「」と入力 `(Get-Item <directory-name>) | Get-Member` します。</span><span class="sxs-lookup"><span data-stu-id="9a791-131">To see all the properties of a directory, type `(Get-Item <directory-name>) | Get-Member`.</span></span>

```powershell
(Get-Item C:\Windows).LastAccessTime
```

### <span data-ttu-id="9a791-132">例 6: レジストリキーの内容を表示する</span><span class="sxs-lookup"><span data-stu-id="9a791-132">Example 6: Show the contents of a registry key</span></span>

<span data-ttu-id="9a791-133">この例は、 **Microsoft PowerShell** レジストリキーの内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="9a791-133">This example shows the contents of the **Microsoft.PowerShell** registry key.</span></span> <span data-ttu-id="9a791-134">このコマンドレットを PowerShell レジストリプロバイダーと共に使用して、レジストリキーとサブキーを取得でき `Get-ItemProperty` ますが、レジストリ値とデータを取得するには、コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a791-134">You can use this cmdlet with the PowerShell Registry provider to get registry keys and subkeys, but you must use the `Get-ItemProperty` cmdlet to get the registry values and data.</span></span>

```powershell
Get-Item HKLM:\Software\Microsoft\Powershell\1\Shellids\Microsoft.Powershell\
```

### <span data-ttu-id="9a791-135">例 7: 除外されているディレクトリ内の項目を取得する</span><span class="sxs-lookup"><span data-stu-id="9a791-135">Example 7: Get items in a directory that have an exclusion</span></span>

<span data-ttu-id="9a791-136">この例では、ドット () を含む名前を持つ Windows ディレクトリ内の項目を取得 `.` しますが、では開始しません `w*` 。この例は、パスにワイルドカード文字 () が含まれている場合にのみ機能し、 `*` 項目の内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a791-136">This example gets items in the Windows directory with names that include a dot (`.`), but don't begin with `w*`.This example works only when the path includes a wildcard character (`*`) to specify the contents of the item.</span></span>

```powershell
Get-Item C:\Windows\*.* -Exclude "w*"
```

## <span data-ttu-id="9a791-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9a791-137">PARAMETERS</span></span>

### <span data-ttu-id="9a791-138">-ストリーム</span><span class="sxs-lookup"><span data-stu-id="9a791-138">-Stream</span></span>

<span data-ttu-id="9a791-139">指定した代替 NTFS ファイル システムをファイルから取得します。</span><span class="sxs-lookup"><span data-stu-id="9a791-139">Gets the specified alternate NTFS file stream from the file.</span></span> <span data-ttu-id="9a791-140">ストリーム名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9a791-140">Enter the stream name.</span></span> <span data-ttu-id="9a791-141">ワイルドカードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="9a791-141">Wildcards are supported.</span></span> <span data-ttu-id="9a791-142">すべてのストリームを取得するには、アスタリスク () を使用し `*` ます。</span><span class="sxs-lookup"><span data-stu-id="9a791-142">To get all streams, use an asterisk (`*`).</span></span> <span data-ttu-id="9a791-143">このパラメーターはフォルダーでは無効です。</span><span class="sxs-lookup"><span data-stu-id="9a791-143">This parameter isn't valid on folders.</span></span>

<span data-ttu-id="9a791-144">**Stream** は、 **FileSystem** プロバイダーによってコマンドレットに追加される動的パラメーターです `Get-Item` 。</span><span class="sxs-lookup"><span data-stu-id="9a791-144">**Stream** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Item` cmdlet.</span></span>
<span data-ttu-id="9a791-145">このパラメーターはファイル システム ドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="9a791-145">This parameter works only in file system drives.</span></span>

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

### <span data-ttu-id="9a791-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="9a791-146">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="9a791-147">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9a791-147">This parameter isn't supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="9a791-148">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="9a791-148">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="9a791-149">-除外</span><span class="sxs-lookup"><span data-stu-id="9a791-149">-Exclude</span></span>

<span data-ttu-id="9a791-150">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="9a791-150">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="9a791-151">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="9a791-151">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="9a791-152">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="9a791-152">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="9a791-153">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9a791-153">Wildcard characters are permitted.</span></span> <span data-ttu-id="9a791-154">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="9a791-154">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="9a791-155">-Filter</span><span class="sxs-lookup"><span data-stu-id="9a791-155">-Filter</span></span>

<span data-ttu-id="9a791-156">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9a791-156">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="9a791-157">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターをサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="9a791-157">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="9a791-158">フィルターは他のパラメーターよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="9a791-158">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="9a791-159">プロバイダーは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得したときにフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="9a791-159">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="9a791-160">フィルター文字列は、ファイルを列挙するために .NET API に渡されます。</span><span class="sxs-lookup"><span data-stu-id="9a791-160">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="9a791-161">API では、とのワイルドカードのみがサポートさ `*` `?` れています。</span><span class="sxs-lookup"><span data-stu-id="9a791-161">The API only supports `*` and `?` wildcards.</span></span>

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

### <span data-ttu-id="9a791-162">-Force</span><span class="sxs-lookup"><span data-stu-id="9a791-162">-Force</span></span>

<span data-ttu-id="9a791-163">このコマンドレットが、非表示の項目など、アクセスできない項目を取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="9a791-163">Indicates that this cmdlet gets items that can't otherwise be accessed, such as hidden items.</span></span>
<span data-ttu-id="9a791-164">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="9a791-164">Implementation varies from provider to provider.</span></span> <span data-ttu-id="9a791-165">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a791-165">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span> <span data-ttu-id="9a791-166">**Force** パラメーターを使用しても、コマンドレットはセキュリティ制限を上書きできません。</span><span class="sxs-lookup"><span data-stu-id="9a791-166">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

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

### <span data-ttu-id="9a791-167">-Include</span><span class="sxs-lookup"><span data-stu-id="9a791-167">-Include</span></span>

<span data-ttu-id="9a791-168">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a791-168">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="9a791-169">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="9a791-169">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="9a791-170">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="9a791-170">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="9a791-171">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9a791-171">Wildcard characters are permitted.</span></span> <span data-ttu-id="9a791-172">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="9a791-172">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="9a791-173">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9a791-173">-LiteralPath</span></span>

<span data-ttu-id="9a791-174">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9a791-174">Specifies a path to one or more locations.</span></span> <span data-ttu-id="9a791-175">**LiteralPath** の値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9a791-175">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="9a791-176">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="9a791-176">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="9a791-177">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="9a791-177">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="9a791-178">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="9a791-178">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="9a791-179">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a791-179">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9a791-180">-Path</span><span class="sxs-lookup"><span data-stu-id="9a791-180">-Path</span></span>

<span data-ttu-id="9a791-181">項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9a791-181">Specifies the path to an item.</span></span> <span data-ttu-id="9a791-182">このコマンドレットは、指定した場所にある項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="9a791-182">This cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="9a791-183">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9a791-183">Wildcard characters are permitted.</span></span> <span data-ttu-id="9a791-184">このパラメーターは必須ですが、パラメーター名の **パス** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9a791-184">This parameter is required, but the parameter name **Path** is optional.</span></span>

<span data-ttu-id="9a791-185">現在の場所を指定するには、ドット () を使用し `.` ます。</span><span class="sxs-lookup"><span data-stu-id="9a791-185">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="9a791-186">現在の場所のすべての項目を指定するには、ワイルドカード文字 ( `*` ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="9a791-186">Use the wildcard character (`*`) to specify all the items in the current location.</span></span>

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

### <span data-ttu-id="9a791-187">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="9a791-187">-UseTransaction</span></span>

<span data-ttu-id="9a791-188">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9a791-188">Includes the command in the active transaction.</span></span>
<span data-ttu-id="9a791-189">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="9a791-189">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="9a791-190">詳細については、「[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a791-190">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9a791-191">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9a791-191">CommonParameters</span></span>

<span data-ttu-id="9a791-192">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="9a791-192">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="9a791-193">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a791-193">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9a791-194">入力</span><span class="sxs-lookup"><span data-stu-id="9a791-194">INPUTS</span></span>

### <span data-ttu-id="9a791-195">System.String</span><span class="sxs-lookup"><span data-stu-id="9a791-195">System.String</span></span>

<span data-ttu-id="9a791-196">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="9a791-196">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="9a791-197">出力</span><span class="sxs-lookup"><span data-stu-id="9a791-197">OUTPUTS</span></span>

### <span data-ttu-id="9a791-198">System.Object</span><span class="sxs-lookup"><span data-stu-id="9a791-198">System.Object</span></span>

<span data-ttu-id="9a791-199">このコマンドレットは、取得したオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="9a791-199">This cmdlet returns the objects that it gets.</span></span> <span data-ttu-id="9a791-200">この型は、パス内のオブジェクトの型によって決まります。</span><span class="sxs-lookup"><span data-stu-id="9a791-200">The type is determined by the type of objects in the path.</span></span>

## <span data-ttu-id="9a791-201">注</span><span class="sxs-lookup"><span data-stu-id="9a791-201">NOTES</span></span>

<span data-ttu-id="9a791-202">このコマンドレットには、内容ではなく項目だけを取得するため、 **再帰** パラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="9a791-202">This cmdlet does not have a **Recurse** parameter, because it gets only an item, not its contents.</span></span>
<span data-ttu-id="9a791-203">項目の内容を再帰的に取得するには、を使用し `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="9a791-203">To get the contents of an item recursively, use `Get-ChildItem`.</span></span>

<span data-ttu-id="9a791-204">レジストリ内を移動するには、このコマンドレットを使用してレジストリキーを取得し、を使用して `Get-ItemProperty` レジストリ値とデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="9a791-204">To navigate through the registry, use this cmdlet to get registry keys and the `Get-ItemProperty` to get registry values and data.</span></span> <span data-ttu-id="9a791-205">レジストリ値はレジストリ キーのプロパティと見なされます。</span><span class="sxs-lookup"><span data-stu-id="9a791-205">The registry values are considered to be properties of the registry key.</span></span>

<span data-ttu-id="9a791-206">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="9a791-206">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="9a791-207">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="9a791-207">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="9a791-208">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a791-208">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="9a791-209">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9a791-209">RELATED LINKS</span></span>

[<span data-ttu-id="9a791-210">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="9a791-210">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="9a791-211">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="9a791-211">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="9a791-212">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="9a791-212">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="9a791-213">Move-Item</span><span class="sxs-lookup"><span data-stu-id="9a791-213">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="9a791-214">New-Item</span><span class="sxs-lookup"><span data-stu-id="9a791-214">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="9a791-215">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="9a791-215">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="9a791-216">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="9a791-216">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="9a791-217">Set-Item</span><span class="sxs-lookup"><span data-stu-id="9a791-217">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="9a791-218">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="9a791-218">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="9a791-219">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9a791-219">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="9a791-220">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="9a791-220">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="9a791-221">about_Providers</span><span class="sxs-lookup"><span data-stu-id="9a791-221">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
