---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-itemproperty?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ItemProperty
ms.openlocfilehash: b1ee17e09a85c7f8afd3b41e7f9fb8b8dd5f019e
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210968"
---
# <span data-ttu-id="7c2e1-103">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7c2e1-103">New-ItemProperty</span></span>

## <span data-ttu-id="7c2e1-104">概要</span><span class="sxs-lookup"><span data-stu-id="7c2e1-104">SYNOPSIS</span></span>
<span data-ttu-id="7c2e1-105">項目の新しいプロパティを作成し、その値を設定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-105">Creates a new property for an item and sets its value.</span></span>

## <span data-ttu-id="7c2e1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7c2e1-106">SYNTAX</span></span>

### <span data-ttu-id="7c2e1-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="7c2e1-107">Path (Default)</span></span>

```
New-ItemProperty [-Path] <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7c2e1-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7c2e1-108">LiteralPath</span></span>

```
New-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7c2e1-109">Description</span><span class="sxs-lookup"><span data-stu-id="7c2e1-109">DESCRIPTION</span></span>

<span data-ttu-id="7c2e1-110">コマンドレットにより、 `New-ItemProperty` 指定した項目の新しいプロパティが作成され、その値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-110">The `New-ItemProperty` cmdlet creates a new property for a specified item and sets its value.</span></span>
<span data-ttu-id="7c2e1-111">通常、レジストリ値がレジストリ キー項目のプロパティになるため、このコマンドレットを使用して新しいレジストリ値が作成されます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-111">Typically, this cmdlet is used to create new registry values, because registry values are properties of a registry key item.</span></span>

<span data-ttu-id="7c2e1-112">このコマンドレットではプロパティがオブジェクトに追加されません。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-112">This cmdlet does not add properties to an object.</span></span>

- <span data-ttu-id="7c2e1-113">オブジェクトのインスタンスにプロパティを追加するには、コマンドレットを使用し `Add-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-113">To add a property to an instance of an object, use the `Add-Member` cmdlet.</span></span>
- <span data-ttu-id="7c2e1-114">特定の種類のすべてのオブジェクトにプロパティを追加するには、Types.ps1xml ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-114">To add a property to all objects of a particular type, modify the Types.ps1xml file.</span></span>

## <span data-ttu-id="7c2e1-115">例</span><span class="sxs-lookup"><span data-stu-id="7c2e1-115">EXAMPLES</span></span>

### <span data-ttu-id="7c2e1-116">例 1: レジストリエントリを追加する</span><span class="sxs-lookup"><span data-stu-id="7c2e1-116">Example 1: Add a registry entry</span></span>

<span data-ttu-id="7c2e1-117">このコマンドは、"HKLM:\ Software hive" の "MyCompany" キーに新しいレジストリエントリ "NoOfEmployees" を追加します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-117">This command adds a new registry entry, "NoOfEmployees", to the "MyCompany" key of the "HKLM:\Software hive".</span></span>

<span data-ttu-id="7c2e1-118">最初のコマンドは、 **path** パラメーターを使用して、"MyCompany" レジストリキーのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-118">The first command uses the **Path** parameter to specify the path of the "MyCompany" registry key.</span></span>
<span data-ttu-id="7c2e1-119">**Name** パラメーターを使用してエントリの名前を指定し、 **value** パラメーターを使用してその値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-119">It uses the **Name** parameter to specify a name for the entry and the **Value** parameter to specify its value.</span></span>

<span data-ttu-id="7c2e1-120">2番目のコマンドは、 `Get-ItemProperty` コマンドレットを使用して、新しいレジストリエントリを確認します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-120">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>

```powershell
New-ItemProperty -Path "HKLM:\Software\MyCompany" -Name "NoOfEmployees" -Value 822
Get-ItemProperty "HKLM:\Software\MyCompany"
```

```output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\mycompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : mycompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 822
```

### <span data-ttu-id="7c2e1-121">例 2: キーにレジストリエントリを追加する</span><span class="sxs-lookup"><span data-stu-id="7c2e1-121">Example 2: Add a registry entry to a key</span></span>

<span data-ttu-id="7c2e1-122">このコマンドは、新しいレジストリ エントリをレジストリ キーに追加します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-122">This command adds a new registry entry to a registry key.</span></span>
<span data-ttu-id="7c2e1-123">キーを指定するために、パイプライン演算子 () を使用して、 `|` キーを表すオブジェクトをに送信し `New-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-123">To specify the key, it uses a pipeline operator (`|`) to send an object that represents the key to `New-ItemProperty`.</span></span>

<span data-ttu-id="7c2e1-124">コマンドの最初の部分では、コマンドレットを使用して `Get-Item` "MyCompany" レジストリキーを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-124">The first part of the command uses the `Get-Item` cmdlet to get the "MyCompany" registry key.</span></span>
<span data-ttu-id="7c2e1-125">パイプライン演算子は、コマンドの結果をに送信します `New-ItemProperty` 。これにより、新しいレジストリエントリ ("NoOfLocations") とその値 (3) が "MyCompany" キーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-125">The pipeline operator sends the results of the command to `New-ItemProperty`, which adds the new registry entry ("NoOfLocations"), and its value (3), to the "MyCompany" key.</span></span>

```powershell
Get-Item -Path "HKLM:\Software\MyCompany" | New-ItemProperty -Name NoOfLocations -Value 3
```

<span data-ttu-id="7c2e1-126">このコマンドが機能するのは、PowerShell のパラメーターバインド機能によって、が返すオブジェクトのパスが `RegistryKey` `Get-Item` の **LiteralPath** パラメーターに関連付けられているため `New-ItemProperty` です。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-126">This command works because the parameter-binding feature of PowerShell associates the path of the `RegistryKey` object that `Get-Item` returns with the **LiteralPath** parameter of `New-ItemProperty`.</span></span> <span data-ttu-id="7c2e1-127">詳細については、「 [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-127">For more information, see [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span></span>

### <span data-ttu-id="7c2e1-128">例 3: Here-String を使用してレジストリに文字列値を作成する</span><span class="sxs-lookup"><span data-stu-id="7c2e1-128">Example 3: Create a MultiString value in the registry using a Here-String</span></span>

<span data-ttu-id="7c2e1-129">この例では、次の文字列を使用して、文字列値を作成します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-129">This example creates a MultiString value using a Here-String.</span></span>

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'HereString' -PropertyType MultiString -Value @"
This is text which contains newlines
It can also contain "quoted" strings
"@
$newValue.multistring
```

```output
This is text which contains newlines
It can also contain "quoted" strings
```

### <span data-ttu-id="7c2e1-130">例 4: 配列を使用してレジストリに文字列値を作成する</span><span class="sxs-lookup"><span data-stu-id="7c2e1-130">Example 4: Create a MultiString value in the registry using an array</span></span>

<span data-ttu-id="7c2e1-131">この例では、値の配列を使用して値を作成する方法を示し `MultiString` ます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-131">The example shows how to use an array of values to create the `MultiString` value.</span></span>

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'MultiString' -PropertyType MultiString -Value ('a','b','c')
$newValue.multistring[0]
```

```output
a
```

## <span data-ttu-id="7c2e1-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7c2e1-132">PARAMETERS</span></span>

### <span data-ttu-id="7c2e1-133">-Credential</span><span class="sxs-lookup"><span data-stu-id="7c2e1-133">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="7c2e1-134">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-134">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="7c2e1-135">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-135">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="7c2e1-136">-除外</span><span class="sxs-lookup"><span data-stu-id="7c2e1-136">-Exclude</span></span>

<span data-ttu-id="7c2e1-137">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-137">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="7c2e1-138">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-138">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="7c2e1-139">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-139">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="7c2e1-140">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-140">Wildcard characters are permitted.</span></span> <span data-ttu-id="7c2e1-141">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-141">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="7c2e1-142">-Filter</span><span class="sxs-lookup"><span data-stu-id="7c2e1-142">-Filter</span></span>

<span data-ttu-id="7c2e1-143">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-143">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="7c2e1-144">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-144">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="7c2e1-145">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-145">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="7c2e1-146">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-146">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="7c2e1-147">-Force</span><span class="sxs-lookup"><span data-stu-id="7c2e1-147">-Force</span></span>

<span data-ttu-id="7c2e1-148">ユーザーがアクセスできないオブジェクトのプロパティをコマンドレットに強制的に作成します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-148">Forces the cmdlet to create a property on an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="7c2e1-149">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-149">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="7c2e1-150">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-150">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="7c2e1-151">-Include</span><span class="sxs-lookup"><span data-stu-id="7c2e1-151">-Include</span></span>

<span data-ttu-id="7c2e1-152">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-152">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="7c2e1-153">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-153">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="7c2e1-154">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-154">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="7c2e1-155">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-155">Wildcard characters are permitted.</span></span> <span data-ttu-id="7c2e1-156">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-156">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="7c2e1-157">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7c2e1-157">-LiteralPath</span></span>

<span data-ttu-id="7c2e1-158">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-158">Specifies a path to one or more locations.</span></span> <span data-ttu-id="7c2e1-159">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-159">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="7c2e1-160">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-160">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="7c2e1-161">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-161">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="7c2e1-162">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-162">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="7c2e1-163">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-163">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="7c2e1-164">-Name</span><span class="sxs-lookup"><span data-stu-id="7c2e1-164">-Name</span></span>

<span data-ttu-id="7c2e1-165">新しいプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-165">Specifies a name for the new property.</span></span>
<span data-ttu-id="7c2e1-166">プロパティがレジストリ エントリである場合、このパラメーターはエントリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-166">If the property is a registry entry, this parameter specifies the name of the entry.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7c2e1-167">-Path</span><span class="sxs-lookup"><span data-stu-id="7c2e1-167">-Path</span></span>

<span data-ttu-id="7c2e1-168">項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-168">Specifies the path of the item.</span></span>
<span data-ttu-id="7c2e1-169">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-169">Wildcard characters are permitted.</span></span>
<span data-ttu-id="7c2e1-170">このパラメーターは、このコマンドレットによって新しいプロパティが追加される項目を識別します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-170">This parameter identifies the item to which this cmdlet adds the new property.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="7c2e1-171">-PropertyType</span><span class="sxs-lookup"><span data-stu-id="7c2e1-171">-PropertyType</span></span>

<span data-ttu-id="7c2e1-172">このコマンドレットによって追加されるプロパティの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-172">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="7c2e1-173">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-173">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7c2e1-174">**String** : null で終わる文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-174">**String** : Specifies a null-terminated string.</span></span> <span data-ttu-id="7c2e1-175">**REG_SZ** と同じです。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-175">Equivalent to **REG_SZ** .</span></span>
- <span data-ttu-id="7c2e1-176">**Expandstring** : 値の取得時に展開される環境変数への展開されていない参照を含む、null で終わる文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-176">**ExpandString** : Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="7c2e1-177">**REG_EXPAND_SZ** と同じです。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-177">Equivalent to **REG_EXPAND_SZ** .</span></span>
- <span data-ttu-id="7c2e1-178">**Binary** : 任意の形式のバイナリデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-178">**Binary** : Specifies binary data in any form.</span></span> <span data-ttu-id="7c2e1-179">**REG_BINARY** と同じです。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-179">Equivalent to **REG_BINARY** .</span></span>
- <span data-ttu-id="7c2e1-180">**DWord** :32 ビットのバイナリ数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-180">**DWord** : Specifies a 32-bit binary number.</span></span> <span data-ttu-id="7c2e1-181">**REG_DWORD** と同じです。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-181">Equivalent to **REG_DWORD** .</span></span>
- <span data-ttu-id="7c2e1-182">Strings: 2 つの null 文字で終了する null で終わる文字列の配列を指定 **します。**</span><span class="sxs-lookup"><span data-stu-id="7c2e1-182">**MultiString** : Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="7c2e1-183">**REG_MULTI_SZ** と同じです。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-183">Equivalent to **REG_MULTI_SZ** .</span></span>
- <span data-ttu-id="7c2e1-184">**Qword** :64 ビットのバイナリ数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-184">**Qword** : Specifies a 64-bit binary number.</span></span> <span data-ttu-id="7c2e1-185">**REG_QWORD** と同じです。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-185">Equivalent to **REG_QWORD** .</span></span>
- <span data-ttu-id="7c2e1-186">**不明** : **REG_RESOURCE_LIST** など、サポートされていないレジストリデータ型を示します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-186">**Unknown** : Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST** .</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7c2e1-187">-Value</span><span class="sxs-lookup"><span data-stu-id="7c2e1-187">-Value</span></span>

<span data-ttu-id="7c2e1-188">プロパティ値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-188">Specifies the property value.</span></span>
<span data-ttu-id="7c2e1-189">プロパティがレジストリ エントリである場合、このパラメーターはエントリの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-189">If the property is a registry entry, this parameter specifies the value of the entry.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7c2e1-190">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7c2e1-190">-Confirm</span></span>

<span data-ttu-id="7c2e1-191">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-191">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7c2e1-192">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7c2e1-192">-WhatIf</span></span>

<span data-ttu-id="7c2e1-193">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-193">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7c2e1-194">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-194">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7c2e1-195">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7c2e1-195">CommonParameters</span></span>

<span data-ttu-id="7c2e1-196">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-196">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="7c2e1-197">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-197">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="7c2e1-198">入力</span><span class="sxs-lookup"><span data-stu-id="7c2e1-198">INPUTS</span></span>

### <span data-ttu-id="7c2e1-199">なし</span><span class="sxs-lookup"><span data-stu-id="7c2e1-199">None</span></span>

<span data-ttu-id="7c2e1-200">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-200">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="7c2e1-201">出力</span><span class="sxs-lookup"><span data-stu-id="7c2e1-201">OUTPUTS</span></span>

### <span data-ttu-id="7c2e1-202">システムの管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="7c2e1-202">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="7c2e1-203">`New-ItemProperty` 新しいプロパティを含むカスタムオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-203">`New-ItemProperty` returns a custom object that contains the new property.</span></span>

## <span data-ttu-id="7c2e1-204">注</span><span class="sxs-lookup"><span data-stu-id="7c2e1-204">NOTES</span></span>

<span data-ttu-id="7c2e1-205">`New-ItemProperty` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-205">`New-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="7c2e1-206">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-206">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="7c2e1-207">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c2e1-207">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="7c2e1-208">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7c2e1-208">RELATED LINKS</span></span>

[<span data-ttu-id="7c2e1-209">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7c2e1-209">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="7c2e1-210">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7c2e1-210">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="7c2e1-211">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7c2e1-211">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="7c2e1-212">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7c2e1-212">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="7c2e1-213">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7c2e1-213">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="7c2e1-214">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7c2e1-214">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="7c2e1-215">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7c2e1-215">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="7c2e1-216">about_Providers</span><span class="sxs-lookup"><span data-stu-id="7c2e1-216">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
