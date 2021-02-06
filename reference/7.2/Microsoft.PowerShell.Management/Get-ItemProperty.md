---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: 20116c12f09d6a9a36f33b656a36e30c2096db70
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599931"
---
# <span data-ttu-id="7ea29-102">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7ea29-102">Get-ItemProperty</span></span>

## <span data-ttu-id="7ea29-103">概要</span><span class="sxs-lookup"><span data-stu-id="7ea29-103">SYNOPSIS</span></span>
<span data-ttu-id="7ea29-104">指定した項目のプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-104">Gets the properties of a specified item.</span></span>

## <span data-ttu-id="7ea29-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7ea29-105">SYNTAX</span></span>

### <span data-ttu-id="7ea29-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="7ea29-106">Path (Default)</span></span>

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="7ea29-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7ea29-107">LiteralPath</span></span>

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="7ea29-108">Description</span><span class="sxs-lookup"><span data-stu-id="7ea29-108">DESCRIPTION</span></span>

<span data-ttu-id="7ea29-109">`Get-ItemProperty`コマンドレットは、指定された項目のプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-109">The `Get-ItemProperty` cmdlet gets the properties of the specified items.</span></span>
<span data-ttu-id="7ea29-110">たとえば、このコマンドレットを使用すると、ファイルオブジェクトの LastAccessTime プロパティの値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-110">For example, you can use this cmdlet to get the value of the LastAccessTime property of a file object.</span></span> <span data-ttu-id="7ea29-111">このコマンドレットを使用して、レジストリエントリとその値を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-111">You can also use this cmdlet to view registry entries and their values.</span></span>

## <span data-ttu-id="7ea29-112">例</span><span class="sxs-lookup"><span data-stu-id="7ea29-112">EXAMPLES</span></span>

### <span data-ttu-id="7ea29-113">例 1: 特定のディレクトリに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="7ea29-113">Example 1: Get information about a specific directory</span></span>

<span data-ttu-id="7ea29-114">このコマンドは、ディレクトリに関する情報を取得し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-114">This command gets information about the `C:\Windows` directory.</span></span>

```powershell
Get-ItemProperty C:\Windows
```

### <span data-ttu-id="7ea29-115">例 2: 特定のファイルのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="7ea29-115">Example 2: Get the properties of a specific file</span></span>

<span data-ttu-id="7ea29-116">このコマンドは、ファイルのプロパティを取得し `C:\Test\Weather.xls` ます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-116">This command gets the properties of the `C:\Test\Weather.xls` file.</span></span>
<span data-ttu-id="7ea29-117">結果は、 `Format-List` 出力を一覧として表示するためにコマンドレットにパイプされます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-117">The result is piped to the `Format-List` cmdlet to display the output as a list.</span></span>

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### <span data-ttu-id="7ea29-118">例 3: レジストリサブキーにレジストリエントリの値名とデータを表示する</span><span class="sxs-lookup"><span data-stu-id="7ea29-118">Example 3: Display the value name and data of registry entries in a registry subkey</span></span>

<span data-ttu-id="7ea29-119">このコマンドは、"CurrentVersion" レジストリサブキーに格納されている各レジストリエントリの値の名前とデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-119">This command displays the value name and data of each of the registry entries contained in the "CurrentVersion" registry subkey.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

> [!NOTE]
> <span data-ttu-id="7ea29-120">このコマンドでは、という名前の PowerShell ドライブが `HKLM:` レジストリの "HKEY_LOCAL_MACHINE" ハイブにマップされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ea29-120">This command requires that there is a PowerShell drive named `HKLM:` that is mapped to the "HKEY_LOCAL_MACHINE" hive of the registry.</span></span>
>
> <span data-ttu-id="7ea29-121">既定では、その名前とマッピングを持つドライブが PowerShell で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-121">A drive with that name and mapping is available in PowerShell by default.</span></span>
> <span data-ttu-id="7ea29-122">また、プロバイダー名の後に 2 つのコロンを続けた以下の代替パスを使用して、このレジストリ サブキーのパスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-122">Alternatively, the path to this registry subkey can be specified by using the following alternative path that begins with the provider name followed by two colons:</span></span>
>
> <span data-ttu-id="7ea29-123">`Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span><span class="sxs-lookup"><span data-stu-id="7ea29-123">`Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span></span>

### <span data-ttu-id="7ea29-124">例 4: レジストリサブキーのレジストリエントリの値の名前とデータを取得する</span><span class="sxs-lookup"><span data-stu-id="7ea29-124">Example 4: Get the value name and data of a registry entry in a registry subkey</span></span>

<span data-ttu-id="7ea29-125">このコマンドは、"CurrentVersion" レジストリサブキーの "ProgramFilesDir" レジストリエントリの値の名前とデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-125">This command gets the value name and data of the "ProgramFilesDir" registry entry in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="7ea29-126">**パス** はサブキーを指定し、 **name** パラメーターはエントリの値の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-126">The **Path** specifies the subkey and the **Name** parameter specifies the value name of the entry.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### <span data-ttu-id="7ea29-127">例 5: レジストリキー内のレジストリエントリの値の名前とデータを取得する</span><span class="sxs-lookup"><span data-stu-id="7ea29-127">Example 5: Get the value names and data of registry entries in a registry key</span></span>

<span data-ttu-id="7ea29-128">このコマンドは、"PowerShellEngine" レジストリキーのレジストリエントリの値の名前とデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-128">This command gets the value names and data of the registry entries in the "PowerShellEngine" registry key.</span></span> <span data-ttu-id="7ea29-129">次のサンプル出力に結果を示します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-129">The results are shown in the following sample output.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\PowerShellEngine
```

```output
ApplicationBase         : C:\Windows\system32\WindowsPowerShell\v1.0\
ConsoleHostAssemblyName : Microsoft.PowerShell.ConsoleHost, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, ProcessorArchitecture=msil
PowerShellVersion       : 2.0
RuntimeVersion          : v2.0.50727
CTPVersion              : 5
PSCompatibleVersion     : 1.0,2.0
```

## <span data-ttu-id="7ea29-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7ea29-130">PARAMETERS</span></span>

### <span data-ttu-id="7ea29-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="7ea29-131">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="7ea29-132">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7ea29-132">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="7ea29-133">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-133">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="7ea29-134">-除外</span><span class="sxs-lookup"><span data-stu-id="7ea29-134">-Exclude</span></span>

<span data-ttu-id="7ea29-135">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-135">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="7ea29-136">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-136">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="7ea29-137">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-137">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="7ea29-138">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-138">Wildcard characters are permitted.</span></span> <span data-ttu-id="7ea29-139">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-139">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="7ea29-140">-Filter</span><span class="sxs-lookup"><span data-stu-id="7ea29-140">-Filter</span></span>

<span data-ttu-id="7ea29-141">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-141">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="7ea29-142">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="7ea29-142">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="7ea29-143">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ea29-143">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="7ea29-144">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="7ea29-144">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="7ea29-145">-Include</span><span class="sxs-lookup"><span data-stu-id="7ea29-145">-Include</span></span>

<span data-ttu-id="7ea29-146">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-146">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="7ea29-147">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-147">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="7ea29-148">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-148">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="7ea29-149">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-149">Wildcard characters are permitted.</span></span> <span data-ttu-id="7ea29-150">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-150">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="7ea29-151">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7ea29-151">-LiteralPath</span></span>

<span data-ttu-id="7ea29-152">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-152">Specifies a path to one or more locations.</span></span> <span data-ttu-id="7ea29-153">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-153">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="7ea29-154">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="7ea29-154">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="7ea29-155">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-155">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="7ea29-156">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="7ea29-156">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="7ea29-157">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ea29-157">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="7ea29-158">-Name</span><span class="sxs-lookup"><span data-stu-id="7ea29-158">-Name</span></span>

<span data-ttu-id="7ea29-159">取得するプロパティの名前を 1 つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-159">Specifies the name of the property or properties to retrieve.</span></span>
<span data-ttu-id="7ea29-160">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-160">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="7ea29-161">-Path</span><span class="sxs-lookup"><span data-stu-id="7ea29-161">-Path</span></span>

<span data-ttu-id="7ea29-162">項目のパスを 1 つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-162">Specifies the path to the item or items.</span></span>
<span data-ttu-id="7ea29-163">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-163">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="7ea29-164">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7ea29-164">CommonParameters</span></span>

<span data-ttu-id="7ea29-165">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-165">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="7ea29-166">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ea29-166">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="7ea29-167">入力</span><span class="sxs-lookup"><span data-stu-id="7ea29-167">INPUTS</span></span>

### <span data-ttu-id="7ea29-168">System.String</span><span class="sxs-lookup"><span data-stu-id="7ea29-168">System.String</span></span>

<span data-ttu-id="7ea29-169">パイプを使用して、パスを含む文字列をにパイプすることができ `Get-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-169">You can pipe a string that contains a path to `Get-ItemProperty`.</span></span>

## <span data-ttu-id="7ea29-170">出力</span><span class="sxs-lookup"><span data-stu-id="7ea29-170">OUTPUTS</span></span>

### <span data-ttu-id="7ea29-171">System.string、System.string、System.string です。</span><span class="sxs-lookup"><span data-stu-id="7ea29-171">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="7ea29-172">`Get-ItemProperty` 取得する項目プロパティごとにオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-172">`Get-ItemProperty` returns an object for each item property that it gets.</span></span> <span data-ttu-id="7ea29-173">オブジェクトの型は、取得するオブジェクトによって異なります。</span><span class="sxs-lookup"><span data-stu-id="7ea29-173">The object type depends on the object that is retrieved.</span></span> <span data-ttu-id="7ea29-174">たとえば、ファイル システム ドライブでは、ファイルまたはフォルダーが返されます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-174">For example, in a file system drive, it might return a file or folder.</span></span>

## <span data-ttu-id="7ea29-175">注</span><span class="sxs-lookup"><span data-stu-id="7ea29-175">NOTES</span></span>

<span data-ttu-id="7ea29-176">`Get-ItemProperty`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="7ea29-176">The `Get-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="7ea29-177">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-177">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="7ea29-178">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ea29-178">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="7ea29-179">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7ea29-179">RELATED LINKS</span></span>

[<span data-ttu-id="7ea29-180">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7ea29-180">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="7ea29-181">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7ea29-181">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="7ea29-182">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7ea29-182">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="7ea29-183">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7ea29-183">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="7ea29-184">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7ea29-184">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="7ea29-185">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7ea29-185">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="7ea29-186">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7ea29-186">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="7ea29-187">about_Providers</span><span class="sxs-lookup"><span data-stu-id="7ea29-187">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

