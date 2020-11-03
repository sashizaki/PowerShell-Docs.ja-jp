---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-itemproperty?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ItemProperty
ms.openlocfilehash: b9a2386b41ec4d64200283a5cd3b802d254b5475
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217283"
---
# <span data-ttu-id="432bd-103">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="432bd-103">Set-ItemProperty</span></span>

## <span data-ttu-id="432bd-104">概要</span><span class="sxs-lookup"><span data-stu-id="432bd-104">SYNOPSIS</span></span>
<span data-ttu-id="432bd-105">項目のプロパティの値を作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="432bd-105">Creates or changes the value of a property of an item.</span></span>

## <span data-ttu-id="432bd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="432bd-106">SYNTAX</span></span>

### <span data-ttu-id="432bd-107">propertyValuePathSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="432bd-107">propertyValuePathSet (Default)</span></span>

```
Set-ItemProperty [-Path] <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### <span data-ttu-id="432bd-108">propertyPSObjectPathSet</span><span class="sxs-lookup"><span data-stu-id="432bd-108">propertyPSObjectPathSet</span></span>

```
Set-ItemProperty [-Path] <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### <span data-ttu-id="432bd-109">Propertyvaluelろ Alpathset</span><span class="sxs-lookup"><span data-stu-id="432bd-109">propertyValueLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### <span data-ttu-id="432bd-110">propertyPSObjectLiteralPathSet</span><span class="sxs-lookup"><span data-stu-id="432bd-110">propertyPSObjectLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

## <span data-ttu-id="432bd-111">Description</span><span class="sxs-lookup"><span data-stu-id="432bd-111">DESCRIPTION</span></span>

<span data-ttu-id="432bd-112">コマンドレットにより、 `Set-ItemProperty` 指定した項目のプロパティの値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="432bd-112">The `Set-ItemProperty` cmdlet changes the value of the property of the specified item.</span></span>
<span data-ttu-id="432bd-113">コマンドレットを使用して、項目のプロパティを作成または変更できます。</span><span class="sxs-lookup"><span data-stu-id="432bd-113">You can use the cmdlet to establish or change the properties of items.</span></span>
<span data-ttu-id="432bd-114">たとえば、を使用して、 `Set-ItemProperty` ファイルオブジェクトの **IsReadOnly** プロパティの値をに設定でき `$True` ます。</span><span class="sxs-lookup"><span data-stu-id="432bd-114">For example, you can use `Set-ItemProperty` to set the value of the **IsReadOnly** property of a file object to `$True`.</span></span>

<span data-ttu-id="432bd-115">また、を使用し `Set-ItemProperty` て、レジストリ値とデータを作成および変更します。</span><span class="sxs-lookup"><span data-stu-id="432bd-115">You also use `Set-ItemProperty` to create and change registry values and data.</span></span>
<span data-ttu-id="432bd-116">たとえば、新しいレジストリ エントリをキーに追加し、その値を設定または変更できます。</span><span class="sxs-lookup"><span data-stu-id="432bd-116">For example, you can add a new registry entry to a key and establish or change its value.</span></span>

## <span data-ttu-id="432bd-117">例</span><span class="sxs-lookup"><span data-stu-id="432bd-117">EXAMPLES</span></span>

### <span data-ttu-id="432bd-118">例 1: ファイルのプロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="432bd-118">Example 1: Set a property of a file</span></span>

<span data-ttu-id="432bd-119">このコマンドは、"final.doc" ファイルの **IsReadOnly** プロパティの値を "true" に設定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-119">This command sets the value of the **IsReadOnly** property of the "final.doc" file to "true".</span></span>
<span data-ttu-id="432bd-120">**パス** を使用して、 **ファイルを指定し、プロパティ** の名前を指定し、 **value** パラメーターを使用して新しい値を指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-120">It uses **Path** to specify the file, **Name** to specify the name of the property, and the **Value** parameter to specify the new value.</span></span>

<span data-ttu-id="432bd-121">ファイルは **IsReadOnly** オブジェクトであり、そのプロパティの1つにすぎ **ません。**</span><span class="sxs-lookup"><span data-stu-id="432bd-121">The file is a **System.IO.FileInfo** object and **IsReadOnly** is just one of its properties.</span></span>
<span data-ttu-id="432bd-122">すべてのプロパティを表示するには、「」と入力 `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType
Property` します。</span><span class="sxs-lookup"><span data-stu-id="432bd-122">To see all of the properties, type `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType
Property`.</span></span>

<span data-ttu-id="432bd-123">`$true`自動変数は、値 "TRUE" を表します。</span><span class="sxs-lookup"><span data-stu-id="432bd-123">The `$true` automatic variable represents a value of "TRUE".</span></span>
<span data-ttu-id="432bd-124">詳細については、「 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="432bd-124">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
Set-ItemProperty -Path C:\GroupFiles\final.doc -Name IsReadOnly -Value $true
```

### <span data-ttu-id="432bd-125">例 2: レジストリエントリと値を作成する</span><span class="sxs-lookup"><span data-stu-id="432bd-125">Example 2: Create a registry entry and value</span></span>

<span data-ttu-id="432bd-126">この例では、を使用し `Set-ItemProperty` て新しいレジストリエントリを作成し、エントリに値を割り当てる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="432bd-126">This example shows how to use `Set-ItemProperty` to create a new registry entry and to assign a value to the entry.</span></span> <span data-ttu-id="432bd-127">キーの "ContosoCompany" キーに "NoOfEmployees" エントリを作成 `HKLM\Software` し、その値を823に設定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-127">It creates the "NoOfEmployees" entry in the "ContosoCompany" key in `HKLM\Software` key and sets its value to 823.</span></span>

<span data-ttu-id="432bd-128">レジストリエントリはレジストリキーのプロパティ (項目) と見なされるため、を使用して `Set-ItemProperty` レジストリエントリを作成し、値を設定して変更します。</span><span class="sxs-lookup"><span data-stu-id="432bd-128">Because registry entries are considered to be properties of the registry keys, which are items, you use `Set-ItemProperty` to create registry entries, and to establish and change their values.</span></span>

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

<span data-ttu-id="432bd-129">最初のコマンドは、レジストリエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="432bd-129">The first command creates the registry entry.</span></span>
<span data-ttu-id="432bd-130">**パス** を使用して、ドライブのパス `HKLM:` と "Software\MyCompany" キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-130">It uses **Path** to specify the path of the `HKLM:` drive and the "Software\MyCompany" key.</span></span>
<span data-ttu-id="432bd-131">このコマンドでは、 **名前** を使用してエントリ名と値を指定し、 **値** を指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-131">The command uses **Name** to specify the entry name and **Value** to specify a value.</span></span>

<span data-ttu-id="432bd-132">2番目のコマンドは、 `Get-ItemProperty` コマンドレットを使用して、新しいレジストリエントリを確認します。</span><span class="sxs-lookup"><span data-stu-id="432bd-132">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>
<span data-ttu-id="432bd-133">またはコマンドレットを使用した場合、エントリは、 `Get-Item` `Get-ChildItem` 項目や子項目ではなく、キーのプロパティであるため、表示されません。</span><span class="sxs-lookup"><span data-stu-id="432bd-133">If you use the `Get-Item` or `Get-ChildItem` cmdlets, the entries do not appear because they are properties of a key, not items or child items.</span></span>

<span data-ttu-id="432bd-134">3番目のコマンドは、 **Noofemployees** エントリの値を824に変更します。</span><span class="sxs-lookup"><span data-stu-id="432bd-134">The third command changes the value of the **NoOfEmployees** entry to 824.</span></span>

<span data-ttu-id="432bd-135">また、 `New-ItemProperty` コマンドレットを使用してレジストリエントリとその値を作成し、を使用して値を変更することもでき `Set-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="432bd-135">You can also use the `New-ItemProperty` cmdlet to create the registry entry and its value and then use `Set-ItemProperty` to change the value.</span></span>

<span data-ttu-id="432bd-136">ドライブの詳細については `HKLM:` 、「」と入力 `Get-Help Get-PSDrive` してください。</span><span class="sxs-lookup"><span data-stu-id="432bd-136">For more information about the `HKLM:` drive, type `Get-Help Get-PSDrive`.</span></span>
<span data-ttu-id="432bd-137">PowerShell を使用してレジストリを管理する方法の詳細については、「」と入力 `Get-Help Registry` してください。</span><span class="sxs-lookup"><span data-stu-id="432bd-137">For more information about how to use PowerShell to manage the registry, type `Get-Help Registry`.</span></span>

### <span data-ttu-id="432bd-138">例 3: パイプラインを使用して項目を変更する</span><span class="sxs-lookup"><span data-stu-id="432bd-138">Example 3: Modify an item by using the pipeline</span></span>

<span data-ttu-id="432bd-139">これらのコマンドは、パイプライン演算子 () を使用してに項目を送信する方法を示して `|` `Set-ItemProperty` います。</span><span class="sxs-lookup"><span data-stu-id="432bd-139">These commands show how to use a pipeline operator (`|`) to send an item to `Set-ItemProperty`.</span></span>

<span data-ttu-id="432bd-140">コマンドの最初の部分では、を使用して、 `Get-ChildItem` "Weekly.txt" ファイルを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="432bd-140">The first part of the command uses `Get-ChildItem` to get an object that represents the "Weekly.txt" file.</span></span> <span data-ttu-id="432bd-141">このコマンドは、パイプライン演算子を使用して、ファイルオブジェクトをに送信し `Set-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="432bd-141">The command uses a pipeline operator to send the file object to `Set-ItemProperty`.</span></span>
<span data-ttu-id="432bd-142">この `Set-ItemProperty` コマンドは、 **Name** パラメーターと **value** パラメーターを使用して、プロパティとその新しい値を指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-142">The `Set-ItemProperty` command uses the **Name** and **Value** parameters to specify the property and its new value.</span></span>

<span data-ttu-id="432bd-143">このコマンドは、 **InputObject** パラメーターを使用して、が取得するオブジェクトを指定することと同じです `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="432bd-143">This command is equivalent to using the **InputObject** parameter to specify the object that `Get-ChildItem` gets.</span></span>

```powershell
Get-ChildItem weekly.txt | Set-ItemProperty -Name IsReadOnly -Value $True
```

## <span data-ttu-id="432bd-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="432bd-144">PARAMETERS</span></span>

### <span data-ttu-id="432bd-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="432bd-145">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="432bd-146">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="432bd-146">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="432bd-147">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="432bd-147">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="432bd-148">-除外</span><span class="sxs-lookup"><span data-stu-id="432bd-148">-Exclude</span></span>

<span data-ttu-id="432bd-149">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-149">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="432bd-150">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="432bd-150">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="432bd-151">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="432bd-151">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="432bd-152">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="432bd-152">Wildcard characters are permitted.</span></span> <span data-ttu-id="432bd-153">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="432bd-153">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="432bd-154">-Filter</span><span class="sxs-lookup"><span data-stu-id="432bd-154">-Filter</span></span>

<span data-ttu-id="432bd-155">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-155">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="432bd-156">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="432bd-156">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="432bd-157">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="432bd-157">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="432bd-158">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="432bd-158">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="432bd-159">-Force</span><span class="sxs-lookup"><span data-stu-id="432bd-159">-Force</span></span>

<span data-ttu-id="432bd-160">ユーザーがアクセスできない項目のプロパティをコマンドレットに強制的に設定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-160">Forces the cmdlet to set a property on items that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="432bd-161">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="432bd-161">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="432bd-162">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="432bd-162">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="432bd-163">-Include</span><span class="sxs-lookup"><span data-stu-id="432bd-163">-Include</span></span>

<span data-ttu-id="432bd-164">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-164">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="432bd-165">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="432bd-165">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="432bd-166">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="432bd-166">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="432bd-167">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="432bd-167">Wildcard characters are permitted.</span></span> <span data-ttu-id="432bd-168">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="432bd-168">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="432bd-169">-InputObject</span><span class="sxs-lookup"><span data-stu-id="432bd-169">-InputObject</span></span>

<span data-ttu-id="432bd-170">このコマンドレットによって変更されるプロパティを持つオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-170">Specifies the object that has the properties that this cmdlet changes.</span></span>
<span data-ttu-id="432bd-171">オブジェクトが格納されている変数、またはオブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="432bd-171">Enter a variable that contains the object or a command that gets the object.</span></span>

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

### <span data-ttu-id="432bd-172">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="432bd-172">-LiteralPath</span></span>

<span data-ttu-id="432bd-173">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-173">Specifies a path to one or more locations.</span></span> <span data-ttu-id="432bd-174">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="432bd-174">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="432bd-175">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="432bd-175">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="432bd-176">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="432bd-176">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="432bd-177">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="432bd-177">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="432bd-178">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="432bd-178">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyPSObjectLiteralPathSet, propertyValueLiteralPathSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="432bd-179">-Name</span><span class="sxs-lookup"><span data-stu-id="432bd-179">-Name</span></span>

<span data-ttu-id="432bd-180">プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-180">Specifies the name of the property.</span></span>

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

### <span data-ttu-id="432bd-181">-PassThru</span><span class="sxs-lookup"><span data-stu-id="432bd-181">-PassThru</span></span>

<span data-ttu-id="432bd-182">項目プロパティを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="432bd-182">Returns an object that represents the item property.</span></span>
<span data-ttu-id="432bd-183">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="432bd-183">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="432bd-184">-Path</span><span class="sxs-lookup"><span data-stu-id="432bd-184">-Path</span></span>

<span data-ttu-id="432bd-185">変更するプロパティを持つ項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-185">Specifies the path of the items with the property to modify.</span></span>
<span data-ttu-id="432bd-186">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="432bd-186">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="432bd-187">-Type</span><span class="sxs-lookup"><span data-stu-id="432bd-187">-Type</span></span>

<span data-ttu-id="432bd-188">**Type** は、レジストリプロバイダーによってコマンドレットに追加される動的パラメーターです `Set-ItemProperty` 。</span><span class="sxs-lookup"><span data-stu-id="432bd-188">**Type** is a dynamic parameter that the Registry provider adds to the `Set-ItemProperty` cmdlet.</span></span>
<span data-ttu-id="432bd-189">このパラメーターは、レジストリドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="432bd-189">This parameter only works in the registry drives.</span></span>

<span data-ttu-id="432bd-190">このコマンドレットによって追加されるプロパティの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-190">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="432bd-191">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="432bd-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="432bd-192">**String** : null で終わる文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-192">**String** : Specifies a null-terminated string.</span></span> <span data-ttu-id="432bd-193">**REG_SZ** と同じです。</span><span class="sxs-lookup"><span data-stu-id="432bd-193">Equivalent to **REG_SZ**.</span></span>
- <span data-ttu-id="432bd-194">**Expandstring** : 値の取得時に展開される環境変数への展開されていない参照を含む、null で終わる文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-194">**ExpandString** : Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="432bd-195">**REG_EXPAND_SZ** と同じです。</span><span class="sxs-lookup"><span data-stu-id="432bd-195">Equivalent to **REG_EXPAND_SZ**.</span></span>
- <span data-ttu-id="432bd-196">**Binary** : 任意の形式のバイナリデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-196">**Binary** : Specifies binary data in any form.</span></span> <span data-ttu-id="432bd-197">**REG_BINARY** と同じです。</span><span class="sxs-lookup"><span data-stu-id="432bd-197">Equivalent to **REG_BINARY**.</span></span>
- <span data-ttu-id="432bd-198">**DWord** :32 ビットのバイナリ数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-198">**DWord** : Specifies a 32-bit binary number.</span></span> <span data-ttu-id="432bd-199">**REG_DWORD** と同じです。</span><span class="sxs-lookup"><span data-stu-id="432bd-199">Equivalent to **REG_DWORD**.</span></span>
- <span data-ttu-id="432bd-200">Strings: 2 つの null 文字で終了する null で終わる文字列の配列を指定 **します。**</span><span class="sxs-lookup"><span data-stu-id="432bd-200">**MultiString** : Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="432bd-201">**REG_MULTI_SZ** と同じです。</span><span class="sxs-lookup"><span data-stu-id="432bd-201">Equivalent to **REG_MULTI_SZ**.</span></span>
- <span data-ttu-id="432bd-202">**Qword** :64 ビットのバイナリ数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-202">**Qword** : Specifies a 64-bit binary number.</span></span> <span data-ttu-id="432bd-203">**REG_QWORD** と同じです。</span><span class="sxs-lookup"><span data-stu-id="432bd-203">Equivalent to **REG_QWORD**.</span></span>
- <span data-ttu-id="432bd-204">**不明** : **REG_RESOURCE_LIST** など、サポートされていないレジストリデータ型を示します。</span><span class="sxs-lookup"><span data-stu-id="432bd-204">**Unknown** : Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST**.</span></span>

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

### <span data-ttu-id="432bd-205">-Value</span><span class="sxs-lookup"><span data-stu-id="432bd-205">-Value</span></span>

<span data-ttu-id="432bd-206">プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="432bd-206">Specifies the value of the property.</span></span>

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

### <span data-ttu-id="432bd-207">-Confirm</span><span class="sxs-lookup"><span data-stu-id="432bd-207">-Confirm</span></span>

<span data-ttu-id="432bd-208">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="432bd-208">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="432bd-209">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="432bd-209">-WhatIf</span></span>

<span data-ttu-id="432bd-210">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="432bd-210">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="432bd-211">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="432bd-211">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="432bd-212">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="432bd-212">CommonParameters</span></span>

<span data-ttu-id="432bd-213">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="432bd-213">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="432bd-214">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="432bd-214">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="432bd-215">入力</span><span class="sxs-lookup"><span data-stu-id="432bd-215">INPUTS</span></span>

### <span data-ttu-id="432bd-216">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="432bd-216">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="432bd-217">パイプを使用してオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="432bd-217">You can pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="432bd-218">出力</span><span class="sxs-lookup"><span data-stu-id="432bd-218">OUTPUTS</span></span>

### <span data-ttu-id="432bd-219">なし、システム管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="432bd-219">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="432bd-220">このコマンドレットは、 **PassThru** パラメーターを指定した場合に、変更された項目を表す **pscustomobject** とその新しいプロパティ値を生成します。</span><span class="sxs-lookup"><span data-stu-id="432bd-220">This cmdlet generates a **PSCustomObject** object that represents the item that was changed and its new property value, if you specify the **PassThru** parameter.</span></span>
<span data-ttu-id="432bd-221">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="432bd-221">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="432bd-222">注</span><span class="sxs-lookup"><span data-stu-id="432bd-222">NOTES</span></span>

<span data-ttu-id="432bd-223">`Set-ItemProperty` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="432bd-223">`Set-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="432bd-224">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="432bd-224">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="432bd-225">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="432bd-225">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="432bd-226">関連リンク</span><span class="sxs-lookup"><span data-stu-id="432bd-226">RELATED LINKS</span></span>

[<span data-ttu-id="432bd-227">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="432bd-227">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="432bd-228">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="432bd-228">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="432bd-229">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="432bd-229">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="432bd-230">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="432bd-230">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="432bd-231">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="432bd-231">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="432bd-232">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="432bd-232">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="432bd-233">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="432bd-233">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="432bd-234">about_Providers</span><span class="sxs-lookup"><span data-stu-id="432bd-234">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
