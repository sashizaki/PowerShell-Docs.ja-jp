---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ItemProperty
ms.openlocfilehash: 969cb181758dc1ac40b9d8fca2c22fa97f87c693
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214456"
---
# <span data-ttu-id="fb89e-103">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="fb89e-103">Set-ItemProperty</span></span>

## <span data-ttu-id="fb89e-104">概要</span><span class="sxs-lookup"><span data-stu-id="fb89e-104">SYNOPSIS</span></span>
<span data-ttu-id="fb89e-105">項目のプロパティの値を作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-105">Creates or changes the value of a property of an item.</span></span>

## <span data-ttu-id="fb89e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fb89e-106">SYNTAX</span></span>

### <span data-ttu-id="fb89e-107">propertyValuePathSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="fb89e-107">propertyValuePathSet (Default)</span></span>

```
Set-ItemProperty [-Path] <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="fb89e-108">propertyPSObjectPathSet</span><span class="sxs-lookup"><span data-stu-id="fb89e-108">propertyPSObjectPathSet</span></span>

```
Set-ItemProperty [-Path] <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="fb89e-109">Propertyvaluelろ Alpathset</span><span class="sxs-lookup"><span data-stu-id="fb89e-109">propertyValueLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="fb89e-110">propertyPSObjectLiteralPathSet</span><span class="sxs-lookup"><span data-stu-id="fb89e-110">propertyPSObjectLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="fb89e-111">Description</span><span class="sxs-lookup"><span data-stu-id="fb89e-111">DESCRIPTION</span></span>

<span data-ttu-id="fb89e-112">コマンドレットにより、 `Set-ItemProperty` 指定した項目のプロパティの値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="fb89e-112">The `Set-ItemProperty` cmdlet changes the value of the property of the specified item.</span></span> <span data-ttu-id="fb89e-113">コマンドレットを使用して、項目のプロパティを作成または変更できます。</span><span class="sxs-lookup"><span data-stu-id="fb89e-113">You can use the cmdlet to establish or change the properties of items.</span></span> <span data-ttu-id="fb89e-114">たとえば、を使用して、 `Set-ItemProperty` ファイルオブジェクトの **IsReadOnly** プロパティの値をに設定でき `$True` ます。</span><span class="sxs-lookup"><span data-stu-id="fb89e-114">For example, you can use `Set-ItemProperty` to set the value of the **IsReadOnly** property of a file object to `$True`.</span></span>

<span data-ttu-id="fb89e-115">また、を使用し `Set-ItemProperty` て、レジストリ値とデータを作成および変更します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-115">You also use `Set-ItemProperty` to create and change registry values and data.</span></span>
<span data-ttu-id="fb89e-116">たとえば、新しいレジストリ エントリをキーに追加し、その値を設定または変更できます。</span><span class="sxs-lookup"><span data-stu-id="fb89e-116">For example, you can add a new registry entry to a key and establish or change its value.</span></span>

## <span data-ttu-id="fb89e-117">例</span><span class="sxs-lookup"><span data-stu-id="fb89e-117">EXAMPLES</span></span>

### <span data-ttu-id="fb89e-118">例 1: ファイルのプロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="fb89e-118">Example 1: Set a property of a file</span></span>

<span data-ttu-id="fb89e-119">このコマンドは、"final.doc" ファイルの **IsReadOnly** プロパティの値を "true" に設定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-119">This command sets the value of the **IsReadOnly** property of the "final.doc" file to "true".</span></span> <span data-ttu-id="fb89e-120">**パス** を使用してファイルを指定し、 **名前** にプロパティの名前を指定し、 **値** pazrameter を使用して新しい値を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-120">It uses **Path** to specify the file, **Name** to specify the name of the property, and the **Value** pazrameter to specify the new value.</span></span>

<span data-ttu-id="fb89e-121">ファイルは **IsReadOnly** オブジェクトであり、そのプロパティの1つにすぎ **ません。**</span><span class="sxs-lookup"><span data-stu-id="fb89e-121">The file is a **System.IO.FileInfo** object and **IsReadOnly** is just one of its properties.</span></span>
<span data-ttu-id="fb89e-122">すべてのプロパティを表示するには、「」と入力 `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType Property` します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-122">To see all of the properties, type `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType Property`.</span></span>

<span data-ttu-id="fb89e-123">`$true`自動変数は、値 "TRUE" を表します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-123">The `$true` automatic variable represents a value of "TRUE".</span></span>
<span data-ttu-id="fb89e-124">詳細については、「 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb89e-124">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
Set-ItemProperty -Path C:\GroupFiles\final.doc -Name IsReadOnly -Value $true
```

### <span data-ttu-id="fb89e-125">例 2: レジストリエントリと値を作成する</span><span class="sxs-lookup"><span data-stu-id="fb89e-125">Example 2: Create a registry entry and value</span></span>

<span data-ttu-id="fb89e-126">この例では、を使用し `Set-ItemProperty` て新しいレジストリエントリを作成し、エントリに値を割り当てる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-126">This example shows how to use `Set-ItemProperty` to create a new registry entry and to assign a value to the entry.</span></span> <span data-ttu-id="fb89e-127">"、Hklm\software" キーの "ContosoCompany" キーに "NoOfEmployees" エントリを作成し、その値を823に設定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-127">It creates the "NoOfEmployees" entry in the "ContosoCompany" key in "HKLM\Software" key and sets its value to 823.</span></span>

<span data-ttu-id="fb89e-128">レジストリエントリはレジストリキーのプロパティ (項目) と見なされるため、を使用して `Set-ItemProperty` レジストリエントリを作成し、値を設定して変更します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-128">Because registry entries are considered to be properties of the registry keys, which are items, you use `Set-ItemProperty` to create registry entries, and to establish and change their values.</span></span>

<span data-ttu-id="fb89e-129">最初のコマンドは、レジストリエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-129">The first command creates the registry entry.</span></span>
<span data-ttu-id="fb89e-130">**パス** を使用して、ドライブのパス `HKLM:` と "Software\MyCompany" キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-130">It uses **Path** to specify the path of the `HKLM:` drive and the "Software\MyCompany" key.</span></span>
<span data-ttu-id="fb89e-131">このコマンドでは、 **名前** を使用してエントリ名と値を指定し、 **値** を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-131">The command uses **Name** to specify the entry name and **Value** to specify a value.</span></span>

<span data-ttu-id="fb89e-132">2番目のコマンドは、 `Get-ItemProperty` コマンドレットを使用して、新しいレジストリエントリを確認します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-132">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span> <span data-ttu-id="fb89e-133">またはコマンドレットを使用した場合、エントリは、 `Get-Item` `Get-ChildItem` 項目や子項目ではなく、キーのプロパティであるため、表示されません。</span><span class="sxs-lookup"><span data-stu-id="fb89e-133">If you use the `Get-Item` or `Get-ChildItem` cmdlets, the entries do not appear because they are properties of a key, not items or child items.</span></span>

<span data-ttu-id="fb89e-134">3番目のコマンドは、 **Noofemployees** エントリの値を824に変更します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-134">The third command changes the value of the **NoOfEmployees** entry to 824.</span></span>

<span data-ttu-id="fb89e-135">また、 `New-ItemProperty` コマンドレットを使用してレジストリエントリとその値を作成し、を使用して値を変更することもでき `Set-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="fb89e-135">You can also use the `New-ItemProperty` cmdlet to create the registry entry and its value and then use `Set-ItemProperty` to change the value.</span></span>

<span data-ttu-id="fb89e-136">ドライブの詳細については `HKLM:` 、「」と入力 `Get-Help Get-PSDrive` してください。</span><span class="sxs-lookup"><span data-stu-id="fb89e-136">For more information about the `HKLM:` drive, type `Get-Help Get-PSDrive`.</span></span>
<span data-ttu-id="fb89e-137">PowerShell を使用してレジストリを管理する方法の詳細については、「」と入力 `Get-Help Registry` してください。</span><span class="sxs-lookup"><span data-stu-id="fb89e-137">For more information about how to use PowerShell to manage the registry, type `Get-Help Registry`.</span></span>

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 823
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```output
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

```output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 824
```

### <span data-ttu-id="fb89e-138">例 3: パイプラインを使用して項目を変更する</span><span class="sxs-lookup"><span data-stu-id="fb89e-138">Example 3: Modify an item by using the pipeline</span></span>

<span data-ttu-id="fb89e-139">これらのコマンドは、パイプライン演算子 () を使用してに項目を送信する方法を示して `|` `Set-ItemProperty` います。</span><span class="sxs-lookup"><span data-stu-id="fb89e-139">These commands show how to use a pipeline operator (`|`) to send an item to `Set-ItemProperty`.</span></span>

<span data-ttu-id="fb89e-140">コマンドの最初の部分では、を使用して、 `Get-ChildItem` "Weekly.txt" ファイルを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-140">The first part of the command uses `Get-ChildItem` to get an object that represents the "Weekly.txt" file.</span></span>
<span data-ttu-id="fb89e-141">このコマンドは、パイプライン演算子を使用して、ファイルオブジェクトをに送信し `Set-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="fb89e-141">The command uses a pipeline operator to send the file object to `Set-ItemProperty`.</span></span>
<span data-ttu-id="fb89e-142">この `Set-ItemProperty` コマンドは、 **Name** パラメーターと **value** パラメーターを使用して、プロパティとその新しい値を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-142">The `Set-ItemProperty` command uses the **Name** and **Value** parameters to specify the property and its new value.</span></span>

<span data-ttu-id="fb89e-143">このコマンドは、 **InputObject** パラメーターを使用して、が取得するオブジェクトを指定することと同じです `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="fb89e-143">This command is equivalent to using the **InputObject** parameter to specify the object that `Get-ChildItem` gets.</span></span>

```powershell
Get-ChildItem weekly.txt | Set-ItemProperty -Name IsReadOnly -Value $True
```

## <span data-ttu-id="fb89e-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fb89e-144">PARAMETERS</span></span>

### <span data-ttu-id="fb89e-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="fb89e-145">-Credential</span></span>

<span data-ttu-id="fb89e-146">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-146">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="fb89e-147">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="fb89e-147">The default is the current user.</span></span>

<span data-ttu-id="fb89e-148">「User01」や「Domain01\User01」のようなユーザー名を入力するか、  コマンドレットで生成されるような `Get-Credential` オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-148">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="fb89e-149">ユーザー名を入力すると、パスワードの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb89e-149">If you type a user name, you are prompted for a password.</span></span>

> [!NOTE]
> <span data-ttu-id="fb89e-150">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fb89e-150">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="fb89e-151">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-151">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="fb89e-152">-除外</span><span class="sxs-lookup"><span data-stu-id="fb89e-152">-Exclude</span></span>

<span data-ttu-id="fb89e-153">コマンドレットが動作しない項目を指定し、他の項目もすべて含めます。</span><span class="sxs-lookup"><span data-stu-id="fb89e-153">Specifies those items upon which the cmdlet does not act, and includes all others.</span></span>
<span data-ttu-id="fb89e-154">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-154">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="fb89e-155">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-155">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="fb89e-156">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fb89e-156">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="fb89e-157">-Filter</span><span class="sxs-lookup"><span data-stu-id="fb89e-157">-Filter</span></span>

<span data-ttu-id="fb89e-158">プロバイダーの形式または言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-158">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="fb89e-159">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-159">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="fb89e-160">ワイルドカード文字の使用など、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="fb89e-160">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="fb89e-161">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="fb89e-161">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="fb89e-162">-Force</span><span class="sxs-lookup"><span data-stu-id="fb89e-162">-Force</span></span>

<span data-ttu-id="fb89e-163">ユーザーがアクセスできない項目のプロパティをコマンドレットに強制的に設定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-163">Forces the cmdlet to set a property on items that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="fb89e-164">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="fb89e-164">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="fb89e-165">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb89e-165">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="fb89e-166">-Include</span><span class="sxs-lookup"><span data-stu-id="fb89e-166">-Include</span></span>

<span data-ttu-id="fb89e-167">コマンドレットが処理する項目だけを指定します。この場合、他の項目はすべて除外されます。</span><span class="sxs-lookup"><span data-stu-id="fb89e-167">Specifies only those items upon which the cmdlet acts, which excludes all others.</span></span>
<span data-ttu-id="fb89e-168">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-168">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="fb89e-169">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-169">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="fb89e-170">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fb89e-170">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="fb89e-171">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fb89e-171">-InputObject</span></span>

<span data-ttu-id="fb89e-172">このコマンドレットによって変更されるプロパティを持つオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-172">Specifies the object that has the properties that this cmdlet changes.</span></span>
<span data-ttu-id="fb89e-173">オブジェクトが格納されている変数、またはオブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-173">Enter a variable that contains the object or a command that gets the object.</span></span>

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

### <span data-ttu-id="fb89e-174">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="fb89e-174">-LiteralPath</span></span>

<span data-ttu-id="fb89e-175">項目プロパティのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-175">Specifies a path of the item property.</span></span>
<span data-ttu-id="fb89e-176">**Path** パラメーターと異なり、 **LiteralPath** の値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb89e-176">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="fb89e-177">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="fb89e-177">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="fb89e-178">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="fb89e-178">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="fb89e-179">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="fb89e-179">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyValueLiteralPathSet, propertyPSObjectLiteralPathSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fb89e-180">-Name</span><span class="sxs-lookup"><span data-stu-id="fb89e-180">-Name</span></span>

<span data-ttu-id="fb89e-181">プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-181">Specifies the name of the property.</span></span>

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

### <span data-ttu-id="fb89e-182">-PassThru</span><span class="sxs-lookup"><span data-stu-id="fb89e-182">-PassThru</span></span>

<span data-ttu-id="fb89e-183">項目プロパティを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-183">Returns an object that represents the item property.</span></span>
<span data-ttu-id="fb89e-184">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="fb89e-184">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="fb89e-185">-Path</span><span class="sxs-lookup"><span data-stu-id="fb89e-185">-Path</span></span>

<span data-ttu-id="fb89e-186">変更するプロパティを持つ項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-186">Specifies the path of the items with the property to modify.</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyValuePathSet, propertyPSObjectPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fb89e-187">-Type</span><span class="sxs-lookup"><span data-stu-id="fb89e-187">-Type</span></span>

<span data-ttu-id="fb89e-188">**Type** は、レジストリプロバイダーによってコマンドレットに追加される動的パラメーターです `Set-ItemProperty` 。</span><span class="sxs-lookup"><span data-stu-id="fb89e-188">**Type** is a dynamic parameter that the Registry provider adds to the `Set-ItemProperty` cmdlet.</span></span>
<span data-ttu-id="fb89e-189">このパラメーターは、レジストリドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-189">This parameter only works in the registry drives.</span></span>

<span data-ttu-id="fb89e-190">このコマンドレットによって追加されるプロパティの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-190">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="fb89e-191">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fb89e-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fb89e-192">**String** : null で終わる文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-192">**String** : Specifies a null-terminated string.</span></span> <span data-ttu-id="fb89e-193">**REG_SZ** と同じです。</span><span class="sxs-lookup"><span data-stu-id="fb89e-193">Equivalent to **REG_SZ** .</span></span>
- <span data-ttu-id="fb89e-194">**Expandstring** : 値の取得時に展開される環境変数への展開されていない参照を含む、null で終わる文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-194">**ExpandString** : Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="fb89e-195">**REG_EXPAND_SZ** と同じです。</span><span class="sxs-lookup"><span data-stu-id="fb89e-195">Equivalent to **REG_EXPAND_SZ** .</span></span>
- <span data-ttu-id="fb89e-196">**Binary** : 任意の形式のバイナリデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-196">**Binary** : Specifies binary data in any form.</span></span> <span data-ttu-id="fb89e-197">**REG_BINARY** と同じです。</span><span class="sxs-lookup"><span data-stu-id="fb89e-197">Equivalent to **REG_BINARY** .</span></span>
- <span data-ttu-id="fb89e-198">**DWord** :32 ビットのバイナリ数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-198">**DWord** : Specifies a 32-bit binary number.</span></span> <span data-ttu-id="fb89e-199">**REG_DWORD** と同じです。</span><span class="sxs-lookup"><span data-stu-id="fb89e-199">Equivalent to **REG_DWORD** .</span></span>
- <span data-ttu-id="fb89e-200">Strings: 2 つの null 文字で終了する null で終わる文字列の配列を指定 **します。**</span><span class="sxs-lookup"><span data-stu-id="fb89e-200">**MultiString** : Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="fb89e-201">**REG_MULTI_SZ** と同じです。</span><span class="sxs-lookup"><span data-stu-id="fb89e-201">Equivalent to **REG_MULTI_SZ** .</span></span>
- <span data-ttu-id="fb89e-202">**Qword** :64 ビットのバイナリ数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-202">**Qword** : Specifies a 64-bit binary number.</span></span> <span data-ttu-id="fb89e-203">**REG_QWORD** と同じです。</span><span class="sxs-lookup"><span data-stu-id="fb89e-203">Equivalent to **REG_QWORD** .</span></span>
- <span data-ttu-id="fb89e-204">**不明** : **REG_RESOURCE_LIST** など、サポートされていないレジストリデータ型を示します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-204">**Unknown** : Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST** .</span></span>

```yaml
Type: RegistryValueKind
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fb89e-205">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="fb89e-205">-UseTransaction</span></span>

<span data-ttu-id="fb89e-206">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fb89e-206">Includes the command in the active transaction.</span></span>
<span data-ttu-id="fb89e-207">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="fb89e-207">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="fb89e-208">詳細については、「[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb89e-208">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fb89e-209">-Value</span><span class="sxs-lookup"><span data-stu-id="fb89e-209">-Value</span></span>

<span data-ttu-id="fb89e-210">プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-210">Specifies the value of the property.</span></span>

```yaml
Type: Object
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fb89e-211">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fb89e-211">-Confirm</span></span>

<span data-ttu-id="fb89e-212">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb89e-212">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fb89e-213">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fb89e-213">-WhatIf</span></span>

<span data-ttu-id="fb89e-214">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-214">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="fb89e-215">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="fb89e-215">The cmdlet is not run.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fb89e-216">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb89e-216">CommonParameters</span></span>

<span data-ttu-id="fb89e-217">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="fb89e-217">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="fb89e-218">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb89e-218">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="fb89e-219">入力</span><span class="sxs-lookup"><span data-stu-id="fb89e-219">INPUTS</span></span>

### <span data-ttu-id="fb89e-220">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="fb89e-220">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="fb89e-221">パイプを使用してオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-221">You can pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="fb89e-222">出力</span><span class="sxs-lookup"><span data-stu-id="fb89e-222">OUTPUTS</span></span>

### <span data-ttu-id="fb89e-223">なし、システム管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="fb89e-223">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="fb89e-224">このコマンドレットは、 **PassThru** パラメーターを指定した場合に、変更された項目を表す **pscustomobject** とその新しいプロパティ値を生成します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-224">This cmdlet generates a **PSCustomObject** object that represents the item that was changed and its new property value, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="fb89e-225">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="fb89e-225">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="fb89e-226">注</span><span class="sxs-lookup"><span data-stu-id="fb89e-226">NOTES</span></span>

<span data-ttu-id="fb89e-227">`Set-ItemProperty` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="fb89e-227">`Set-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="fb89e-228">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="fb89e-228">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="fb89e-229">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb89e-229">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="fb89e-230">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fb89e-230">RELATED LINKS</span></span>

[<span data-ttu-id="fb89e-231">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="fb89e-231">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="fb89e-232">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="fb89e-232">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="fb89e-233">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="fb89e-233">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="fb89e-234">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="fb89e-234">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="fb89e-235">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="fb89e-235">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="fb89e-236">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="fb89e-236">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="fb89e-237">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="fb89e-237">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)
