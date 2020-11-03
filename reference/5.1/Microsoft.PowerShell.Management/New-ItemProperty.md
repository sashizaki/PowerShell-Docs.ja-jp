---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ItemProperty
ms.openlocfilehash: 2569f4778f54f6cdad22e10cf92e727b73c323e3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214611"
---
# <span data-ttu-id="c20df-103">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c20df-103">New-ItemProperty</span></span>

## <span data-ttu-id="c20df-104">概要</span><span class="sxs-lookup"><span data-stu-id="c20df-104">SYNOPSIS</span></span>
<span data-ttu-id="c20df-105">項目の新しいプロパティを作成し、その値を設定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-105">Creates a new property for an item and sets its value.</span></span>

## <span data-ttu-id="c20df-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c20df-106">SYNTAX</span></span>

### <span data-ttu-id="c20df-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="c20df-107">Path (Default)</span></span>

```
New-ItemProperty [-Path] <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="c20df-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c20df-108">LiteralPath</span></span>

```
New-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="c20df-109">Description</span><span class="sxs-lookup"><span data-stu-id="c20df-109">DESCRIPTION</span></span>

<span data-ttu-id="c20df-110">コマンドレットにより、 `New-ItemProperty` 指定した項目の新しいプロパティが作成され、その値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="c20df-110">The `New-ItemProperty` cmdlet creates a new property for a specified item and sets its value.</span></span>
<span data-ttu-id="c20df-111">通常、レジストリ値がレジストリ キー項目のプロパティになるため、このコマンドレットを使用して新しいレジストリ値が作成されます。</span><span class="sxs-lookup"><span data-stu-id="c20df-111">Typically, this cmdlet is used to create new registry values, because registry values are properties of a registry key item.</span></span>

<span data-ttu-id="c20df-112">このコマンドレットではプロパティがオブジェクトに追加されません。</span><span class="sxs-lookup"><span data-stu-id="c20df-112">This cmdlet does not add properties to an object.</span></span>

- <span data-ttu-id="c20df-113">オブジェクトのインスタンスにプロパティを追加するには、コマンドレットを使用し `Add-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="c20df-113">To add a property to an instance of an object, use the `Add-Member` cmdlet.</span></span>
- <span data-ttu-id="c20df-114">特定の種類のすべてのオブジェクトにプロパティを追加するには、Types.ps1xml ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="c20df-114">To add a property to all objects of a particular type, modify the Types.ps1xml file.</span></span>

## <span data-ttu-id="c20df-115">例</span><span class="sxs-lookup"><span data-stu-id="c20df-115">EXAMPLES</span></span>

### <span data-ttu-id="c20df-116">例 1: レジストリエントリを追加する</span><span class="sxs-lookup"><span data-stu-id="c20df-116">Example 1: Add a registry entry</span></span>

<span data-ttu-id="c20df-117">このコマンドは、"HKLM:\ Software hive" の "MyCompany" キーに新しいレジストリエントリ "NoOfEmployees" を追加します。</span><span class="sxs-lookup"><span data-stu-id="c20df-117">This command adds a new registry entry, "NoOfEmployees", to the "MyCompany" key of the "HKLM:\Software hive".</span></span>

<span data-ttu-id="c20df-118">最初のコマンドは、 **path** パラメーターを使用して、"MyCompany" レジストリキーのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-118">The first command uses the **Path** parameter to specify the path of the "MyCompany" registry key.</span></span>
<span data-ttu-id="c20df-119">**Name** パラメーターを使用してエントリの名前を指定し、 **value** パラメーターを使用してその値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-119">It uses the **Name** parameter to specify a name for the entry and the **Value** parameter to specify its value.</span></span>

<span data-ttu-id="c20df-120">2番目のコマンドは、 `Get-ItemProperty` コマンドレットを使用して、新しいレジストリエントリを確認します。</span><span class="sxs-lookup"><span data-stu-id="c20df-120">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>

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

### <span data-ttu-id="c20df-121">例 2: キーにレジストリエントリを追加する</span><span class="sxs-lookup"><span data-stu-id="c20df-121">Example 2: Add a registry entry to a key</span></span>

<span data-ttu-id="c20df-122">このコマンドは、新しいレジストリ エントリをレジストリ キーに追加します。</span><span class="sxs-lookup"><span data-stu-id="c20df-122">This command adds a new registry entry to a registry key.</span></span> <span data-ttu-id="c20df-123">キーを指定するために、パイプライン演算子 (|) を使用して、キーを表すオブジェクトをに送信し `New-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="c20df-123">To specify the key, it uses a pipeline operator (|) to send an object that represents the key to `New-ItemProperty`.</span></span>

<span data-ttu-id="c20df-124">コマンドの最初の部分では、コマンドレットを使用して `Get-Item` "MyCompany" レジストリキーを取得します。</span><span class="sxs-lookup"><span data-stu-id="c20df-124">The first part of the command uses the `Get-Item` cmdlet to get the "MyCompany" registry key.</span></span> <span data-ttu-id="c20df-125">パイプライン演算子は、コマンドの結果をに送信します `New-ItemProperty` 。これにより、新しいレジストリエントリ ("NoOfLocations") とその値 (3) が "MyCompany" キーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c20df-125">The pipeline operator sends the results of the command to `New-ItemProperty`, which adds the new registry entry ("NoOfLocations"), and its value (3), to the "MyCompany" key.</span></span>

```powershell
Get-Item -Path "HKLM:\Software\MyCompany" | New-ItemProperty -Name NoOfLocations -Value 3
```

<span data-ttu-id="c20df-126">このコマンドが機能するのは、Windows PowerShell のパラメーターバインド機能によって、が返すオブジェクトのパスが `RegistryKey` `Get-Item` の **LiteralPath** パラメーターに関連付けられているため `New-ItemProperty` です。</span><span class="sxs-lookup"><span data-stu-id="c20df-126">This command works because the parameter-binding feature of Windows PowerShell associates the path of the `RegistryKey` object that `Get-Item` returns with the **LiteralPath** parameter of `New-ItemProperty`.</span></span> <span data-ttu-id="c20df-127">詳細については、「 [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c20df-127">For more information, see [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span></span>

### <span data-ttu-id="c20df-128">例 3: Here-String を使用してレジストリに文字列値を作成する</span><span class="sxs-lookup"><span data-stu-id="c20df-128">Example 3: Create a MultiString value in the registry using a Here-String</span></span>

<span data-ttu-id="c20df-129">この例では、次の文字列を使用して、文字列値を作成します。</span><span class="sxs-lookup"><span data-stu-id="c20df-129">This example creates a MultiString value using a Here-String.</span></span>

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

### <span data-ttu-id="c20df-130">例 4: 配列を使用してレジストリに文字列値を作成する</span><span class="sxs-lookup"><span data-stu-id="c20df-130">Example 4: Create a MultiString value in the registry using an array</span></span>

<span data-ttu-id="c20df-131">この例では、値の配列を使用して値を作成する方法を示し `MultiString` ます。</span><span class="sxs-lookup"><span data-stu-id="c20df-131">The example shows how to use an array of values to create the `MultiString` value.</span></span>

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'MultiString' -PropertyType MultiString -Value ('a','b','c')
$newValue.multistring[0]
```

```output
a
```

## <span data-ttu-id="c20df-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c20df-132">PARAMETERS</span></span>

### <span data-ttu-id="c20df-133">-Credential</span><span class="sxs-lookup"><span data-stu-id="c20df-133">-Credential</span></span>

<span data-ttu-id="c20df-134">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-134">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="c20df-135">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="c20df-135">The default is the current user.</span></span>

<span data-ttu-id="c20df-136">「User01」や「Domain01\User01」のようなユーザー名を入力するか、  コマンドレットで生成されるような `Get-Credential` オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="c20df-136">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="c20df-137">ユーザー名を入力すると、パスワードの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c20df-137">If you type a user name, you are prompted for a password.</span></span>

> [!NOTE]
> <span data-ttu-id="c20df-138">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c20df-138">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="c20df-139">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c20df-139">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="c20df-140">-除外</span><span class="sxs-lookup"><span data-stu-id="c20df-140">-Exclude</span></span>

<span data-ttu-id="c20df-141">このコマンドレットによって操作から除外されるプロパティまたはプロパティを、文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-141">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="c20df-142">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="c20df-142">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="c20df-143">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="c20df-143">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="c20df-144">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c20df-144">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c20df-145">-Filter</span><span class="sxs-lookup"><span data-stu-id="c20df-145">-Filter</span></span>

<span data-ttu-id="c20df-146">プロバイダーの形式または言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-146">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="c20df-147">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="c20df-147">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="c20df-148">ワイルドカード文字の使用など、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c20df-148">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span> <span data-ttu-id="c20df-149">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="c20df-149">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c20df-150">-Force</span><span class="sxs-lookup"><span data-stu-id="c20df-150">-Force</span></span>

<span data-ttu-id="c20df-151">ユーザーがアクセスできないオブジェクトのプロパティをコマンドレットに強制的に作成します。</span><span class="sxs-lookup"><span data-stu-id="c20df-151">Forces the cmdlet to create a property on an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="c20df-152">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="c20df-152">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="c20df-153">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c20df-153">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="c20df-154">-Include</span><span class="sxs-lookup"><span data-stu-id="c20df-154">-Include</span></span>

<span data-ttu-id="c20df-155">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-155">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="c20df-156">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="c20df-156">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="c20df-157">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="c20df-157">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="c20df-158">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c20df-158">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c20df-159">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c20df-159">-LiteralPath</span></span>

<span data-ttu-id="c20df-160">プロパティの現在の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-160">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="c20df-161">**Path** パラメーターと異なり、 **LiteralPath** の値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c20df-161">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="c20df-162">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="c20df-162">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="c20df-163">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c20df-163">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="c20df-164">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="c20df-164">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="c20df-165">-Name</span><span class="sxs-lookup"><span data-stu-id="c20df-165">-Name</span></span>

<span data-ttu-id="c20df-166">新しいプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-166">Specifies a name for the new property.</span></span>
<span data-ttu-id="c20df-167">プロパティがレジストリ エントリである場合、このパラメーターはエントリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-167">If the property is a registry entry, this parameter specifies the name of the entry.</span></span>

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

### <span data-ttu-id="c20df-168">-Path</span><span class="sxs-lookup"><span data-stu-id="c20df-168">-Path</span></span>

<span data-ttu-id="c20df-169">項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-169">Specifies the path of the item.</span></span>
<span data-ttu-id="c20df-170">このパラメーターは、このコマンドレットによって新しいプロパティが追加される項目を識別します。</span><span class="sxs-lookup"><span data-stu-id="c20df-170">This parameter identifies the item to which this cmdlet adds the new property.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c20df-171">-PropertyType</span><span class="sxs-lookup"><span data-stu-id="c20df-171">-PropertyType</span></span>

<span data-ttu-id="c20df-172">このコマンドレットによって追加されるプロパティの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-172">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="c20df-173">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c20df-173">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c20df-174">**String** : null で終わる文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-174">**String** : Specifies a null-terminated string.</span></span> <span data-ttu-id="c20df-175">**REG_SZ** と同じです。</span><span class="sxs-lookup"><span data-stu-id="c20df-175">Equivalent to **REG_SZ** .</span></span>
- <span data-ttu-id="c20df-176">**Expandstring** : 値の取得時に展開される環境変数への展開されていない参照を含む、null で終わる文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-176">**ExpandString** : Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="c20df-177">**REG_EXPAND_SZ** と同じです。</span><span class="sxs-lookup"><span data-stu-id="c20df-177">Equivalent to **REG_EXPAND_SZ** .</span></span>
- <span data-ttu-id="c20df-178">**Binary** : 任意の形式のバイナリデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-178">**Binary** : Specifies binary data in any form.</span></span> <span data-ttu-id="c20df-179">**REG_BINARY** と同じです。</span><span class="sxs-lookup"><span data-stu-id="c20df-179">Equivalent to **REG_BINARY** .</span></span>
- <span data-ttu-id="c20df-180">**DWord** :32 ビットのバイナリ数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-180">**DWord** : Specifies a 32-bit binary number.</span></span> <span data-ttu-id="c20df-181">**REG_DWORD** と同じです。</span><span class="sxs-lookup"><span data-stu-id="c20df-181">Equivalent to **REG_DWORD** .</span></span>
- <span data-ttu-id="c20df-182">Strings: 2 つの null 文字で終了する null で終わる文字列の配列を指定 **します。**</span><span class="sxs-lookup"><span data-stu-id="c20df-182">**MultiString** : Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="c20df-183">**REG_MULTI_SZ** と同じです。</span><span class="sxs-lookup"><span data-stu-id="c20df-183">Equivalent to **REG_MULTI_SZ** .</span></span>
- <span data-ttu-id="c20df-184">**Qword** :64 ビットのバイナリ数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-184">**Qword** : Specifies a 64-bit binary number.</span></span> <span data-ttu-id="c20df-185">**REG_QWORD** と同じです。</span><span class="sxs-lookup"><span data-stu-id="c20df-185">Equivalent to **REG_QWORD** .</span></span>
- <span data-ttu-id="c20df-186">**不明** : **REG_RESOURCE_LIST** など、サポートされていないレジストリデータ型を示します。</span><span class="sxs-lookup"><span data-stu-id="c20df-186">**Unknown** : Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST** .</span></span>

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

### <span data-ttu-id="c20df-187">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="c20df-187">-UseTransaction</span></span>

<span data-ttu-id="c20df-188">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c20df-188">Includes the command in the active transaction.</span></span>
<span data-ttu-id="c20df-189">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="c20df-189">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="c20df-190">詳細については、「about_Transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c20df-190">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="c20df-191">-Value</span><span class="sxs-lookup"><span data-stu-id="c20df-191">-Value</span></span>

<span data-ttu-id="c20df-192">プロパティ値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-192">Specifies the property value.</span></span>
<span data-ttu-id="c20df-193">プロパティがレジストリ エントリである場合、このパラメーターはエントリの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c20df-193">If the property is a registry entry, this parameter specifies the value of the entry.</span></span>

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

### <span data-ttu-id="c20df-194">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c20df-194">-Confirm</span></span>

<span data-ttu-id="c20df-195">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c20df-195">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c20df-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c20df-196">-WhatIf</span></span>

<span data-ttu-id="c20df-197">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="c20df-197">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c20df-198">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c20df-198">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c20df-199">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c20df-199">CommonParameters</span></span>

<span data-ttu-id="c20df-200">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="c20df-200">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="c20df-201">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c20df-201">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="c20df-202">入力</span><span class="sxs-lookup"><span data-stu-id="c20df-202">INPUTS</span></span>

### <span data-ttu-id="c20df-203">なし</span><span class="sxs-lookup"><span data-stu-id="c20df-203">None</span></span>

<span data-ttu-id="c20df-204">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="c20df-204">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c20df-205">出力</span><span class="sxs-lookup"><span data-stu-id="c20df-205">OUTPUTS</span></span>

### <span data-ttu-id="c20df-206">システムの管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="c20df-206">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="c20df-207">`New-ItemProperty` 新しいプロパティを含むカスタムオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c20df-207">`New-ItemProperty` returns a custom object that contains the new property.</span></span>

## <span data-ttu-id="c20df-208">注</span><span class="sxs-lookup"><span data-stu-id="c20df-208">NOTES</span></span>

<span data-ttu-id="c20df-209">`New-ItemProperty` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c20df-209">`New-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="c20df-210">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="c20df-210">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="c20df-211">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c20df-211">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="c20df-212">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c20df-212">RELATED LINKS</span></span>

[<span data-ttu-id="c20df-213">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c20df-213">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="c20df-214">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c20df-214">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="c20df-215">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c20df-215">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="c20df-216">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c20df-216">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="c20df-217">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c20df-217">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="c20df-218">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c20df-218">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="c20df-219">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c20df-219">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="c20df-220">about_Providers</span><span class="sxs-lookup"><span data-stu-id="c20df-220">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
