---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ItemProperty
ms.openlocfilehash: 870d8e9797ff2cfce14034706f704c0e1c954fc2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602414"
---
# <span data-ttu-id="bea7a-102">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bea7a-102">Remove-ItemProperty</span></span>

## <span data-ttu-id="bea7a-103">概要</span><span class="sxs-lookup"><span data-stu-id="bea7a-103">SYNOPSIS</span></span>
<span data-ttu-id="bea7a-104">項目からプロパティとその値を削除します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-104">Deletes the property and its value from an item.</span></span>

## <span data-ttu-id="bea7a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bea7a-105">SYNTAX</span></span>

### <span data-ttu-id="bea7a-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="bea7a-106">Path (Default)</span></span>

```
Remove-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bea7a-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="bea7a-107">LiteralPath</span></span>

```
Remove-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="bea7a-108">Description</span><span class="sxs-lookup"><span data-stu-id="bea7a-108">DESCRIPTION</span></span>

<span data-ttu-id="bea7a-109">`Remove-ItemProperty`コマンドレットは、項目からプロパティとその値を削除します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-109">The `Remove-ItemProperty` cmdlet deletes a property and its value from an item.</span></span>
<span data-ttu-id="bea7a-110">これを使用して、レジストリ値とその中に格納されているデータを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-110">You can use it to delete registry values and the data that they store.</span></span>

## <span data-ttu-id="bea7a-111">例</span><span class="sxs-lookup"><span data-stu-id="bea7a-111">EXAMPLES</span></span>

### <span data-ttu-id="bea7a-112">例 1: レジストリ値を削除する</span><span class="sxs-lookup"><span data-stu-id="bea7a-112">Example 1: Delete a registry value</span></span>

<span data-ttu-id="bea7a-113">このコマンドは、レジストリキーの "Smpproperty" サブキーから、"SmpProperty" レジストリ値とそのデータを削除し `HKEY_LOCAL_MACHINE\Software` ます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-113">This command deletes the "SmpProperty" registry value, and its data, from the "SmpApplication" subkey of the `HKEY_LOCAL_MACHINE\Software` registry key.</span></span>

```powershell
Remove-ItemProperty -Path "HKLM:\Software\SmpApplication" -Name "SmpProperty"
```

<span data-ttu-id="bea7a-114">コマンドはファイルシステムドライブ () から発行されるので、 `PS C:\>` ドライブ、 `HKLM:` 、および "Software" キーを含む "SmpApplication" サブキーの完全修飾パスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-114">Because the command is issued from a file system drive (`PS C:\>`), it includes the fully qualified path of the "SmpApplication" subkey, including the drive, `HKLM:`, and the "Software" key.</span></span>

### <span data-ttu-id="bea7a-115">例 2: HKCU の場所からレジストリ値を削除する</span><span class="sxs-lookup"><span data-stu-id="bea7a-115">Example 2: Delete a registry value from the HKCU location</span></span>

<span data-ttu-id="bea7a-116">これらのコマンドは、"HKEY_CURRENT_USER\Software\MyCompany" の "MyApp" サブキーから、"Options" レジストリ値とそのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-116">These commands delete the "Options" registry value, and its data, from the "MyApp" subkey of "HKEY_CURRENT_USER\Software\MyCompany".</span></span>

```
PS C:\> Set-Location HKCU:\Software\MyCompany\MyApp
PS HKCU:\Software\MyCompany\MyApp> Remove-ItemProperty -Path . -Name "Options" -Confirm
```

<span data-ttu-id="bea7a-117">最初のコマンドは、コマンドレットを使用して、 `Set-Location` 現在の場所を **HKEY_CURRENT_USER** ドライブ ( `HKCU:` ) とサブキーに変更し `Software\MyCompany\MyApp` ます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-117">The first command uses the `Set-Location` cmdlet to change the current location to the **HKEY_CURRENT_USER** drive (`HKCU:`) and the `Software\MyCompany\MyApp` subkey.</span></span>

<span data-ttu-id="bea7a-118">2番目のコマンドは、を使用して、" `Remove-ItemProperty` MyApp" サブキーから "Options" レジストリ値とそのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-118">The second command uses `Remove-ItemProperty` to remove the "Options" registry value, and its data, from the "MyApp" subkey.</span></span> <span data-ttu-id="bea7a-119">**パス** が必要であるため、コマンドはドット () を使用し `.` て現在の場所を示します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-119">Because **Path** is required, the command uses a dot (`.`) to indicate the current location.</span></span> <span data-ttu-id="bea7a-120">**Confirm** パラメーターは、値を削除する前にユーザープロンプトを要求します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-120">The **Confirm** parameter requests a user prompt before deleting the value.</span></span>

### <span data-ttu-id="bea7a-121">例 3: パイプラインを使用してレジストリ値を削除する</span><span class="sxs-lookup"><span data-stu-id="bea7a-121">Example 3: Remove a registry value by using the pipeline</span></span>

<span data-ttu-id="bea7a-122">このコマンドは、レジストリキーから "NoOfEmployees" レジストリ値とそのデータを削除し `HKLM\Software\MyCompany` ます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-122">This command deletes the "NoOfEmployees" registry value, and its data, from the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany | Remove-ItemProperty -Name NoOfEmployees
```

<span data-ttu-id="bea7a-123">コマンドは、コマンドレットを使用して、 `Get-Item` レジストリキーを表す項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-123">The command uses the `Get-Item` cmdlet to get an item that represents the registry key.</span></span>
<span data-ttu-id="bea7a-124">パイプライン演算子 () を使用して `|` 、オブジェクトをに送信 `Remove-ItemProperty` します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-124">It uses a pipeline operator (`|`) to send the object to `Remove-ItemProperty`.</span></span>
<span data-ttu-id="bea7a-125">次に、の **name** パラメーターを使用して、 `Remove-ItemProperty` レジストリ値の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-125">Then, it uses the **Name** parameter of `Remove-ItemProperty` to specify the name of the registry value.</span></span>

## <span data-ttu-id="bea7a-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bea7a-126">PARAMETERS</span></span>

### <span data-ttu-id="bea7a-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="bea7a-127">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="bea7a-128">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bea7a-128">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="bea7a-129">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-129">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="bea7a-130">-除外</span><span class="sxs-lookup"><span data-stu-id="bea7a-130">-Exclude</span></span>

<span data-ttu-id="bea7a-131">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-131">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="bea7a-132">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-132">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="bea7a-133">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-133">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="bea7a-134">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-134">Wildcard characters are permitted.</span></span> <span data-ttu-id="bea7a-135">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-135">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="bea7a-136">-Filter</span><span class="sxs-lookup"><span data-stu-id="bea7a-136">-Filter</span></span>

<span data-ttu-id="bea7a-137">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-137">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="bea7a-138">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="bea7a-138">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="bea7a-139">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bea7a-139">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="bea7a-140">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="bea7a-140">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="bea7a-141">-Force</span><span class="sxs-lookup"><span data-stu-id="bea7a-141">-Force</span></span>

<span data-ttu-id="bea7a-142">ユーザーがアクセスできないオブジェクトのプロパティをコマンドレットに強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-142">Forces the cmdlet to remove a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="bea7a-143">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="bea7a-143">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="bea7a-144">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bea7a-144">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="bea7a-145">-Include</span><span class="sxs-lookup"><span data-stu-id="bea7a-145">-Include</span></span>

<span data-ttu-id="bea7a-146">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-146">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="bea7a-147">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-147">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="bea7a-148">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-148">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="bea7a-149">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-149">Wildcard characters are permitted.</span></span> <span data-ttu-id="bea7a-150">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-150">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="bea7a-151">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="bea7a-151">-LiteralPath</span></span>

<span data-ttu-id="bea7a-152">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-152">Specifies a path to one or more locations.</span></span> <span data-ttu-id="bea7a-153">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-153">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="bea7a-154">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="bea7a-154">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="bea7a-155">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-155">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="bea7a-156">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="bea7a-156">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="bea7a-157">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bea7a-157">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="bea7a-158">-Name</span><span class="sxs-lookup"><span data-stu-id="bea7a-158">-Name</span></span>

<span data-ttu-id="bea7a-159">削除するプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-159">Specifies the names of the properties to remove.</span></span>
<span data-ttu-id="bea7a-160">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-160">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="bea7a-161">-Path</span><span class="sxs-lookup"><span data-stu-id="bea7a-161">-Path</span></span>

<span data-ttu-id="bea7a-162">プロパティを削除する項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-162">Specifies the path of the item whose properties are being removed.</span></span>
<span data-ttu-id="bea7a-163">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-163">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="bea7a-164">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bea7a-164">-Confirm</span></span>

<span data-ttu-id="bea7a-165">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-165">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bea7a-166">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bea7a-166">-WhatIf</span></span>

<span data-ttu-id="bea7a-167">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-167">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="bea7a-168">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="bea7a-168">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bea7a-169">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="bea7a-169">CommonParameters</span></span>

<span data-ttu-id="bea7a-170">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-170">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="bea7a-171">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bea7a-171">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="bea7a-172">入力</span><span class="sxs-lookup"><span data-stu-id="bea7a-172">INPUTS</span></span>

### <span data-ttu-id="bea7a-173">System.String</span><span class="sxs-lookup"><span data-stu-id="bea7a-173">System.String</span></span>

<span data-ttu-id="bea7a-174">パイプを使用してパスを含む文字列をこのコマンドレットに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-174">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="bea7a-175">出力</span><span class="sxs-lookup"><span data-stu-id="bea7a-175">OUTPUTS</span></span>

### <span data-ttu-id="bea7a-176">なし</span><span class="sxs-lookup"><span data-stu-id="bea7a-176">None</span></span>

<span data-ttu-id="bea7a-177">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="bea7a-177">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="bea7a-178">注</span><span class="sxs-lookup"><span data-stu-id="bea7a-178">NOTES</span></span>

- <span data-ttu-id="bea7a-179">PowerShell レジストリプロバイダーでは、レジストリ値はレジストリキーまたはサブキーのプロパティと見なされます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-179">In the PowerShell Registry provider, registry values are considered to be properties of a registry key or subkey.</span></span> <span data-ttu-id="bea7a-180">これらの値は、 **get-itemproperty** コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="bea7a-180">You can use the **ItemProperty** cmdlets to manage these values.</span></span>
- <span data-ttu-id="bea7a-181">`Remove-ItemProperty` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="bea7a-181">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="bea7a-182">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-182">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="bea7a-183">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bea7a-183">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="bea7a-184">関連リンク</span><span class="sxs-lookup"><span data-stu-id="bea7a-184">RELATED LINKS</span></span>

[<span data-ttu-id="bea7a-185">Get-Item</span><span class="sxs-lookup"><span data-stu-id="bea7a-185">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="bea7a-186">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bea7a-186">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="bea7a-187">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bea7a-187">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="bea7a-188">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bea7a-188">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="bea7a-189">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bea7a-189">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="bea7a-190">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bea7a-190">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="bea7a-191">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="bea7a-191">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="bea7a-192">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bea7a-192">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="bea7a-193">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bea7a-193">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="bea7a-194">Set-Location</span><span class="sxs-lookup"><span data-stu-id="bea7a-194">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="bea7a-195">about_Providers</span><span class="sxs-lookup"><span data-stu-id="bea7a-195">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

