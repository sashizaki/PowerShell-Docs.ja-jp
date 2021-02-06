---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ItemProperty
ms.openlocfilehash: 18383dc2b1e018e56864e412dfe75eca2b578a08
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600117"
---
# <span data-ttu-id="220b9-102">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="220b9-102">Set-ItemProperty</span></span>

## <span data-ttu-id="220b9-103">概要</span><span class="sxs-lookup"><span data-stu-id="220b9-103">SYNOPSIS</span></span>
<span data-ttu-id="220b9-104">項目のプロパティの値を作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="220b9-104">Creates or changes the value of a property of an item.</span></span>

## <span data-ttu-id="220b9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="220b9-105">SYNTAX</span></span>

### <span data-ttu-id="220b9-106">propertyValuePathSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="220b9-106">propertyValuePathSet (Default)</span></span>

```
Set-ItemProperty [-Path] <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### <span data-ttu-id="220b9-107">propertyPSObjectPathSet</span><span class="sxs-lookup"><span data-stu-id="220b9-107">propertyPSObjectPathSet</span></span>

```
Set-ItemProperty [-Path] <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### <span data-ttu-id="220b9-108">Propertyvaluelろ Alpathset</span><span class="sxs-lookup"><span data-stu-id="220b9-108">propertyValueLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### <span data-ttu-id="220b9-109">propertyPSObjectLiteralPathSet</span><span class="sxs-lookup"><span data-stu-id="220b9-109">propertyPSObjectLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

## <span data-ttu-id="220b9-110">Description</span><span class="sxs-lookup"><span data-stu-id="220b9-110">DESCRIPTION</span></span>

<span data-ttu-id="220b9-111">コマンドレットにより、 `Set-ItemProperty` 指定した項目のプロパティの値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="220b9-111">The `Set-ItemProperty` cmdlet changes the value of the property of the specified item.</span></span>
<span data-ttu-id="220b9-112">コマンドレットを使用して、項目のプロパティを作成または変更できます。</span><span class="sxs-lookup"><span data-stu-id="220b9-112">You can use the cmdlet to establish or change the properties of items.</span></span>
<span data-ttu-id="220b9-113">たとえば、を使用して、 `Set-ItemProperty` ファイルオブジェクトの **IsReadOnly** プロパティの値をに設定でき `$True` ます。</span><span class="sxs-lookup"><span data-stu-id="220b9-113">For example, you can use `Set-ItemProperty` to set the value of the **IsReadOnly** property of a file object to `$True`.</span></span>

<span data-ttu-id="220b9-114">また、を使用し `Set-ItemProperty` て、レジストリ値とデータを作成および変更します。</span><span class="sxs-lookup"><span data-stu-id="220b9-114">You also use `Set-ItemProperty` to create and change registry values and data.</span></span>
<span data-ttu-id="220b9-115">たとえば、新しいレジストリ エントリをキーに追加し、その値を設定または変更できます。</span><span class="sxs-lookup"><span data-stu-id="220b9-115">For example, you can add a new registry entry to a key and establish or change its value.</span></span>

## <span data-ttu-id="220b9-116">例</span><span class="sxs-lookup"><span data-stu-id="220b9-116">EXAMPLES</span></span>

### <span data-ttu-id="220b9-117">例 1: ファイルのプロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="220b9-117">Example 1: Set a property of a file</span></span>

<span data-ttu-id="220b9-118">このコマンドは、"final.doc" ファイルの **IsReadOnly** プロパティの値を "true" に設定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-118">This command sets the value of the **IsReadOnly** property of the "final.doc" file to "true".</span></span>
<span data-ttu-id="220b9-119">**パス** を使用して、**ファイルを指定し、プロパティ** の名前を指定し、 **value** パラメーターを使用して新しい値を指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-119">It uses **Path** to specify the file, **Name** to specify the name of the property, and the **Value** parameter to specify the new value.</span></span>

<span data-ttu-id="220b9-120">ファイルは **IsReadOnly** オブジェクトであり、そのプロパティの1つにすぎ **ません。**</span><span class="sxs-lookup"><span data-stu-id="220b9-120">The file is a **System.IO.FileInfo** object and **IsReadOnly** is just one of its properties.</span></span>
<span data-ttu-id="220b9-121">すべてのプロパティを表示するには、「」と入力 `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType
Property` します。</span><span class="sxs-lookup"><span data-stu-id="220b9-121">To see all of the properties, type `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType
Property`.</span></span>

<span data-ttu-id="220b9-122">`$true`自動変数は、値 "TRUE" を表します。</span><span class="sxs-lookup"><span data-stu-id="220b9-122">The `$true` automatic variable represents a value of "TRUE".</span></span>
<span data-ttu-id="220b9-123">詳細については、「 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="220b9-123">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
Set-ItemProperty -Path C:\GroupFiles\final.doc -Name IsReadOnly -Value $true
```

### <span data-ttu-id="220b9-124">例 2: レジストリエントリと値を作成する</span><span class="sxs-lookup"><span data-stu-id="220b9-124">Example 2: Create a registry entry and value</span></span>

<span data-ttu-id="220b9-125">この例では、を使用し `Set-ItemProperty` て新しいレジストリエントリを作成し、エントリに値を割り当てる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="220b9-125">This example shows how to use `Set-ItemProperty` to create a new registry entry and to assign a value to the entry.</span></span> <span data-ttu-id="220b9-126">キーの "ContosoCompany" キーに "NoOfEmployees" エントリを作成 `HKLM\Software` し、その値を823に設定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-126">It creates the "NoOfEmployees" entry in the "ContosoCompany" key in `HKLM\Software` key and sets its value to 823.</span></span>

<span data-ttu-id="220b9-127">レジストリエントリはレジストリキーのプロパティ (項目) と見なされるため、を使用して `Set-ItemProperty` レジストリエントリを作成し、値を設定して変更します。</span><span class="sxs-lookup"><span data-stu-id="220b9-127">Because registry entries are considered to be properties of the registry keys, which are items, you use `Set-ItemProperty` to create registry entries, and to establish and change their values.</span></span>

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 823
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```Output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 823
```

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 824
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```Output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 824
```

<span data-ttu-id="220b9-128">最初のコマンドは、レジストリエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="220b9-128">The first command creates the registry entry.</span></span>
<span data-ttu-id="220b9-129">**パス** を使用して、ドライブのパス `HKLM:` と "Software\MyCompany" キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-129">It uses **Path** to specify the path of the `HKLM:` drive and the "Software\MyCompany" key.</span></span>
<span data-ttu-id="220b9-130">このコマンドでは、 **名前** を使用してエントリ名と値を指定し、 **値** を指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-130">The command uses **Name** to specify the entry name and **Value** to specify a value.</span></span>

<span data-ttu-id="220b9-131">2番目のコマンドは、 `Get-ItemProperty` コマンドレットを使用して、新しいレジストリエントリを確認します。</span><span class="sxs-lookup"><span data-stu-id="220b9-131">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>
<span data-ttu-id="220b9-132">またはコマンドレットを使用した場合、エントリは、 `Get-Item` `Get-ChildItem` 項目や子項目ではなく、キーのプロパティであるため、表示されません。</span><span class="sxs-lookup"><span data-stu-id="220b9-132">If you use the `Get-Item` or `Get-ChildItem` cmdlets, the entries do not appear because they are properties of a key, not items or child items.</span></span>

<span data-ttu-id="220b9-133">3番目のコマンドは、 **Noofemployees** エントリの値を824に変更します。</span><span class="sxs-lookup"><span data-stu-id="220b9-133">The third command changes the value of the **NoOfEmployees** entry to 824.</span></span>

<span data-ttu-id="220b9-134">また、 `New-ItemProperty` コマンドレットを使用してレジストリエントリとその値を作成し、を使用して値を変更することもでき `Set-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="220b9-134">You can also use the `New-ItemProperty` cmdlet to create the registry entry and its value and then use `Set-ItemProperty` to change the value.</span></span>

<span data-ttu-id="220b9-135">ドライブの詳細については `HKLM:` 、「」と入力 `Get-Help Get-PSDrive` してください。</span><span class="sxs-lookup"><span data-stu-id="220b9-135">For more information about the `HKLM:` drive, type `Get-Help Get-PSDrive`.</span></span>
<span data-ttu-id="220b9-136">PowerShell を使用してレジストリを管理する方法の詳細については、「」と入力 `Get-Help Registry` してください。</span><span class="sxs-lookup"><span data-stu-id="220b9-136">For more information about how to use PowerShell to manage the registry, type `Get-Help Registry`.</span></span>

### <span data-ttu-id="220b9-137">例 3: パイプラインを使用して項目を変更する</span><span class="sxs-lookup"><span data-stu-id="220b9-137">Example 3: Modify an item by using the pipeline</span></span>

<span data-ttu-id="220b9-138">これらのコマンドは、パイプライン演算子 () を使用してに項目を送信する方法を示して `|` `Set-ItemProperty` います。</span><span class="sxs-lookup"><span data-stu-id="220b9-138">These commands show how to use a pipeline operator (`|`) to send an item to `Set-ItemProperty`.</span></span>

<span data-ttu-id="220b9-139">コマンドの最初の部分では、を使用して、 `Get-ChildItem` "Weekly.txt" ファイルを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="220b9-139">The first part of the command uses `Get-ChildItem` to get an object that represents the "Weekly.txt" file.</span></span> <span data-ttu-id="220b9-140">このコマンドは、パイプライン演算子を使用して、ファイルオブジェクトをに送信し `Set-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="220b9-140">The command uses a pipeline operator to send the file object to `Set-ItemProperty`.</span></span>
<span data-ttu-id="220b9-141">この `Set-ItemProperty` コマンドは、 **Name** パラメーターと **value** パラメーターを使用して、プロパティとその新しい値を指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-141">The `Set-ItemProperty` command uses the **Name** and **Value** parameters to specify the property and its new value.</span></span>

<span data-ttu-id="220b9-142">このコマンドは、 **InputObject** パラメーターを使用して、が取得するオブジェクトを指定することと同じです `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="220b9-142">This command is equivalent to using the **InputObject** parameter to specify the object that `Get-ChildItem` gets.</span></span>

```powershell
Get-ChildItem weekly.txt | Set-ItemProperty -Name IsReadOnly -Value $True
```

## <span data-ttu-id="220b9-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="220b9-143">PARAMETERS</span></span>

### <span data-ttu-id="220b9-144">-Credential</span><span class="sxs-lookup"><span data-stu-id="220b9-144">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="220b9-145">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="220b9-145">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="220b9-146">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="220b9-146">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="220b9-147">-除外</span><span class="sxs-lookup"><span data-stu-id="220b9-147">-Exclude</span></span>

<span data-ttu-id="220b9-148">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-148">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="220b9-149">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="220b9-149">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="220b9-150">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="220b9-150">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="220b9-151">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="220b9-151">Wildcard characters are permitted.</span></span> <span data-ttu-id="220b9-152">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="220b9-152">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="220b9-153">-Filter</span><span class="sxs-lookup"><span data-stu-id="220b9-153">-Filter</span></span>

<span data-ttu-id="220b9-154">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-154">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="220b9-155">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="220b9-155">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="220b9-156">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="220b9-156">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="220b9-157">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="220b9-157">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="220b9-158">-Force</span><span class="sxs-lookup"><span data-stu-id="220b9-158">-Force</span></span>

<span data-ttu-id="220b9-159">ユーザーがアクセスできない項目のプロパティをコマンドレットに強制的に設定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-159">Forces the cmdlet to set a property on items that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="220b9-160">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="220b9-160">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="220b9-161">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="220b9-161">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="220b9-162">-Include</span><span class="sxs-lookup"><span data-stu-id="220b9-162">-Include</span></span>

<span data-ttu-id="220b9-163">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-163">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="220b9-164">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="220b9-164">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="220b9-165">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="220b9-165">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="220b9-166">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="220b9-166">Wildcard characters are permitted.</span></span> <span data-ttu-id="220b9-167">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="220b9-167">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="220b9-168">-InputObject</span><span class="sxs-lookup"><span data-stu-id="220b9-168">-InputObject</span></span>

<span data-ttu-id="220b9-169">このコマンドレットによって変更されるプロパティを持つオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-169">Specifies the object that has the properties that this cmdlet changes.</span></span>
<span data-ttu-id="220b9-170">オブジェクトが格納されている変数、またはオブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="220b9-170">Enter a variable that contains the object or a command that gets the object.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: propertyPSObjectPathSet, propertyPSObjectLiteralPathSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="220b9-171">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="220b9-171">-LiteralPath</span></span>

<span data-ttu-id="220b9-172">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-172">Specifies a path to one or more locations.</span></span> <span data-ttu-id="220b9-173">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="220b9-173">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="220b9-174">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="220b9-174">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="220b9-175">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="220b9-175">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="220b9-176">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="220b9-176">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="220b9-177">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="220b9-177">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyValueLiteralPathSet, propertyPSObjectLiteralPathSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="220b9-178">-Name</span><span class="sxs-lookup"><span data-stu-id="220b9-178">-Name</span></span>

<span data-ttu-id="220b9-179">プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-179">Specifies the name of the property.</span></span>

```yaml
Type: System.String
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="220b9-180">-PassThru</span><span class="sxs-lookup"><span data-stu-id="220b9-180">-PassThru</span></span>

<span data-ttu-id="220b9-181">項目プロパティを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="220b9-181">Returns an object that represents the item property.</span></span>
<span data-ttu-id="220b9-182">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="220b9-182">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="220b9-183">-Path</span><span class="sxs-lookup"><span data-stu-id="220b9-183">-Path</span></span>

<span data-ttu-id="220b9-184">変更するプロパティを持つ項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-184">Specifies the path of the items with the property to modify.</span></span>
<span data-ttu-id="220b9-185">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="220b9-185">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyValuePathSet, propertyPSObjectPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="220b9-186">-Type</span><span class="sxs-lookup"><span data-stu-id="220b9-186">-Type</span></span>

<span data-ttu-id="220b9-187">**Type** は、レジストリプロバイダーによってコマンドレットに追加される動的パラメーターです `Set-ItemProperty` 。</span><span class="sxs-lookup"><span data-stu-id="220b9-187">**Type** is a dynamic parameter that the Registry provider adds to the `Set-ItemProperty` cmdlet.</span></span>
<span data-ttu-id="220b9-188">このパラメーターは、レジストリドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="220b9-188">This parameter only works in the registry drives.</span></span>

<span data-ttu-id="220b9-189">このコマンドレットによって追加されるプロパティの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-189">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="220b9-190">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="220b9-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="220b9-191">**String**: null で終わる文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-191">**String**: Specifies a null-terminated string.</span></span> <span data-ttu-id="220b9-192">**REG_SZ** と同じです。</span><span class="sxs-lookup"><span data-stu-id="220b9-192">Equivalent to **REG_SZ**.</span></span>
- <span data-ttu-id="220b9-193">**Expandstring**: 値の取得時に展開される環境変数への展開されていない参照を含む、null で終わる文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-193">**ExpandString**: Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="220b9-194">**REG_EXPAND_SZ** と同じです。</span><span class="sxs-lookup"><span data-stu-id="220b9-194">Equivalent to **REG_EXPAND_SZ**.</span></span>
- <span data-ttu-id="220b9-195">**Binary**: 任意の形式のバイナリデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-195">**Binary**: Specifies binary data in any form.</span></span> <span data-ttu-id="220b9-196">**REG_BINARY** と同じです。</span><span class="sxs-lookup"><span data-stu-id="220b9-196">Equivalent to **REG_BINARY**.</span></span>
- <span data-ttu-id="220b9-197">**DWord**:32 ビットのバイナリ数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-197">**DWord**: Specifies a 32-bit binary number.</span></span> <span data-ttu-id="220b9-198">**REG_DWORD** と同じです。</span><span class="sxs-lookup"><span data-stu-id="220b9-198">Equivalent to **REG_DWORD**.</span></span>
- <span data-ttu-id="220b9-199">Strings: 2 つの null 文字で終了する null で終わる文字列の配列を指定 **します。**</span><span class="sxs-lookup"><span data-stu-id="220b9-199">**MultiString**: Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="220b9-200">**REG_MULTI_SZ** と同じです。</span><span class="sxs-lookup"><span data-stu-id="220b9-200">Equivalent to **REG_MULTI_SZ**.</span></span>
- <span data-ttu-id="220b9-201">**Qword**:64 ビットのバイナリ数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-201">**Qword**: Specifies a 64-bit binary number.</span></span> <span data-ttu-id="220b9-202">**REG_QWORD** と同じです。</span><span class="sxs-lookup"><span data-stu-id="220b9-202">Equivalent to **REG_QWORD**.</span></span>
- <span data-ttu-id="220b9-203">**不明**: **REG_RESOURCE_LIST** など、サポートされていないレジストリデータ型を示します。</span><span class="sxs-lookup"><span data-stu-id="220b9-203">**Unknown**: Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST**.</span></span>

```yaml
Type: Microsoft.Win32.RegistryValueKind
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="220b9-204">-Value</span><span class="sxs-lookup"><span data-stu-id="220b9-204">-Value</span></span>

<span data-ttu-id="220b9-205">プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="220b9-205">Specifies the value of the property.</span></span>

```yaml
Type: System.Object
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="220b9-206">-Confirm</span><span class="sxs-lookup"><span data-stu-id="220b9-206">-Confirm</span></span>

<span data-ttu-id="220b9-207">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="220b9-207">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="220b9-208">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="220b9-208">-WhatIf</span></span>

<span data-ttu-id="220b9-209">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="220b9-209">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="220b9-210">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="220b9-210">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="220b9-211">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="220b9-211">CommonParameters</span></span>

<span data-ttu-id="220b9-212">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="220b9-212">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="220b9-213">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="220b9-213">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="220b9-214">入力</span><span class="sxs-lookup"><span data-stu-id="220b9-214">INPUTS</span></span>

### <span data-ttu-id="220b9-215">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="220b9-215">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="220b9-216">パイプを使用してオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="220b9-216">You can pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="220b9-217">出力</span><span class="sxs-lookup"><span data-stu-id="220b9-217">OUTPUTS</span></span>

### <span data-ttu-id="220b9-218">なし、システム管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="220b9-218">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="220b9-219">このコマンドレットは、 **PassThru** パラメーターを指定した場合に、変更された項目を表す **pscustomobject** とその新しいプロパティ値を生成します。</span><span class="sxs-lookup"><span data-stu-id="220b9-219">This cmdlet generates a **PSCustomObject** object that represents the item that was changed and its new property value, if you specify the **PassThru** parameter.</span></span>
<span data-ttu-id="220b9-220">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="220b9-220">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="220b9-221">注</span><span class="sxs-lookup"><span data-stu-id="220b9-221">NOTES</span></span>

<span data-ttu-id="220b9-222">`Set-ItemProperty` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="220b9-222">`Set-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="220b9-223">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="220b9-223">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="220b9-224">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="220b9-224">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="220b9-225">関連リンク</span><span class="sxs-lookup"><span data-stu-id="220b9-225">RELATED LINKS</span></span>

[<span data-ttu-id="220b9-226">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="220b9-226">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="220b9-227">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="220b9-227">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="220b9-228">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="220b9-228">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="220b9-229">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="220b9-229">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="220b9-230">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="220b9-230">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="220b9-231">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="220b9-231">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="220b9-232">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="220b9-232">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="220b9-233">about_Providers</span><span class="sxs-lookup"><span data-stu-id="220b9-233">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

