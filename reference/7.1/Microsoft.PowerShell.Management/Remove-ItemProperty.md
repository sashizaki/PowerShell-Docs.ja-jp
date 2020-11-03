---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-itemproperty?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ItemProperty
ms.openlocfilehash: 335f1f5b3e40eaf39cee7213b7bb02dbfa69ee3c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211536"
---
# <span data-ttu-id="51cc8-103">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="51cc8-103">Remove-ItemProperty</span></span>

## <span data-ttu-id="51cc8-104">概要</span><span class="sxs-lookup"><span data-stu-id="51cc8-104">SYNOPSIS</span></span>
<span data-ttu-id="51cc8-105">項目からプロパティとその値を削除します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-105">Deletes the property and its value from an item.</span></span>

## <span data-ttu-id="51cc8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="51cc8-106">SYNTAX</span></span>

### <span data-ttu-id="51cc8-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="51cc8-107">Path (Default)</span></span>

```
Remove-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="51cc8-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="51cc8-108">LiteralPath</span></span>

```
Remove-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="51cc8-109">Description</span><span class="sxs-lookup"><span data-stu-id="51cc8-109">DESCRIPTION</span></span>

<span data-ttu-id="51cc8-110">`Remove-ItemProperty`コマンドレットは、項目からプロパティとその値を削除します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-110">The `Remove-ItemProperty` cmdlet deletes a property and its value from an item.</span></span>
<span data-ttu-id="51cc8-111">これを使用して、レジストリ値とその中に格納されているデータを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-111">You can use it to delete registry values and the data that they store.</span></span>

## <span data-ttu-id="51cc8-112">例</span><span class="sxs-lookup"><span data-stu-id="51cc8-112">EXAMPLES</span></span>

### <span data-ttu-id="51cc8-113">例 1: レジストリ値を削除する</span><span class="sxs-lookup"><span data-stu-id="51cc8-113">Example 1: Delete a registry value</span></span>

<span data-ttu-id="51cc8-114">このコマンドは、レジストリキーの "Smpproperty" サブキーから、"SmpProperty" レジストリ値とそのデータを削除し `HKEY_LOCAL_MACHINE\Software` ます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-114">This command deletes the "SmpProperty" registry value, and its data, from the "SmpApplication" subkey of the `HKEY_LOCAL_MACHINE\Software` registry key.</span></span>

```powershell
Remove-ItemProperty -Path "HKLM:\Software\SmpApplication" -Name "SmpProperty"
```

<span data-ttu-id="51cc8-115">コマンドはファイルシステムドライブ () から発行されるので、 `PS C:\>` ドライブ、 `HKLM:` 、および "Software" キーを含む "SmpApplication" サブキーの完全修飾パスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-115">Because the command is issued from a file system drive (`PS C:\>`), it includes the fully qualified path of the "SmpApplication" subkey, including the drive, `HKLM:`, and the "Software" key.</span></span>

### <span data-ttu-id="51cc8-116">例 2: HKCU の場所からレジストリ値を削除する</span><span class="sxs-lookup"><span data-stu-id="51cc8-116">Example 2: Delete a registry value from the HKCU location</span></span>

<span data-ttu-id="51cc8-117">これらのコマンドは、"HKEY_CURRENT_USER\Software\MyCompany" の "MyApp" サブキーから、"Options" レジストリ値とそのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-117">These commands delete the "Options" registry value, and its data, from the "MyApp" subkey of "HKEY_CURRENT_USER\Software\MyCompany".</span></span>

```
PS C:\> Set-Location HKCU:\Software\MyCompany\MyApp
PS HKCU:\Software\MyCompany\MyApp> Remove-ItemProperty -Path . -Name "Options" -Confirm
```

<span data-ttu-id="51cc8-118">最初のコマンドは、コマンドレットを使用して、 `Set-Location` 現在の場所を **HKEY_CURRENT_USER** ドライブ ( `HKCU:` ) とサブキーに変更し `Software\MyCompany\MyApp` ます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-118">The first command uses the `Set-Location` cmdlet to change the current location to the **HKEY_CURRENT_USER** drive (`HKCU:`) and the `Software\MyCompany\MyApp` subkey.</span></span>

<span data-ttu-id="51cc8-119">2番目のコマンドは、を使用して、" `Remove-ItemProperty` MyApp" サブキーから "Options" レジストリ値とそのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-119">The second command uses `Remove-ItemProperty` to remove the "Options" registry value, and its data, from the "MyApp" subkey.</span></span> <span data-ttu-id="51cc8-120">**パス** が必要であるため、コマンドはドット () を使用し `.` て現在の場所を示します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-120">Because **Path** is required, the command uses a dot (`.`) to indicate the current location.</span></span> <span data-ttu-id="51cc8-121">**Confirm** パラメーターは、値を削除する前にユーザープロンプトを要求します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-121">The **Confirm** parameter requests a user prompt before deleting the value.</span></span>

### <span data-ttu-id="51cc8-122">例 3: パイプラインを使用してレジストリ値を削除する</span><span class="sxs-lookup"><span data-stu-id="51cc8-122">Example 3: Remove a registry value by using the pipeline</span></span>

<span data-ttu-id="51cc8-123">このコマンドは、レジストリキーから "NoOfEmployees" レジストリ値とそのデータを削除し `HKLM\Software\MyCompany` ます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-123">This command deletes the "NoOfEmployees" registry value, and its data, from the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany | Remove-ItemProperty -Name NoOfEmployees
```

<span data-ttu-id="51cc8-124">コマンドは、コマンドレットを使用して、 `Get-Item` レジストリキーを表す項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-124">The command uses the `Get-Item` cmdlet to get an item that represents the registry key.</span></span>
<span data-ttu-id="51cc8-125">パイプライン演算子 () を使用して `|` 、オブジェクトをに送信 `Remove-ItemProperty` します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-125">It uses a pipeline operator (`|`) to send the object to `Remove-ItemProperty`.</span></span>
<span data-ttu-id="51cc8-126">次に、の **name** パラメーターを使用して、 `Remove-ItemProperty` レジストリ値の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-126">Then, it uses the **Name** parameter of `Remove-ItemProperty` to specify the name of the registry value.</span></span>

## <span data-ttu-id="51cc8-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="51cc8-127">PARAMETERS</span></span>

### <span data-ttu-id="51cc8-128">-Credential</span><span class="sxs-lookup"><span data-stu-id="51cc8-128">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="51cc8-129">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="51cc8-129">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="51cc8-130">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-130">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="51cc8-131">-除外</span><span class="sxs-lookup"><span data-stu-id="51cc8-131">-Exclude</span></span>

<span data-ttu-id="51cc8-132">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-132">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="51cc8-133">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-133">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="51cc8-134">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-134">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="51cc8-135">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-135">Wildcard characters are permitted.</span></span> <span data-ttu-id="51cc8-136">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-136">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="51cc8-137">-Filter</span><span class="sxs-lookup"><span data-stu-id="51cc8-137">-Filter</span></span>

<span data-ttu-id="51cc8-138">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-138">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="51cc8-139">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="51cc8-139">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="51cc8-140">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51cc8-140">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="51cc8-141">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="51cc8-141">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="51cc8-142">-Force</span><span class="sxs-lookup"><span data-stu-id="51cc8-142">-Force</span></span>

<span data-ttu-id="51cc8-143">ユーザーがアクセスできないオブジェクトのプロパティをコマンドレットに強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-143">Forces the cmdlet to remove a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="51cc8-144">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="51cc8-144">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="51cc8-145">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51cc8-145">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="51cc8-146">-Include</span><span class="sxs-lookup"><span data-stu-id="51cc8-146">-Include</span></span>

<span data-ttu-id="51cc8-147">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-147">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="51cc8-148">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-148">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="51cc8-149">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-149">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="51cc8-150">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-150">Wildcard characters are permitted.</span></span> <span data-ttu-id="51cc8-151">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-151">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="51cc8-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="51cc8-152">-LiteralPath</span></span>

<span data-ttu-id="51cc8-153">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-153">Specifies a path to one or more locations.</span></span> <span data-ttu-id="51cc8-154">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-154">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="51cc8-155">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="51cc8-155">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="51cc8-156">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-156">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="51cc8-157">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="51cc8-157">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="51cc8-158">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51cc8-158">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="51cc8-159">-Name</span><span class="sxs-lookup"><span data-stu-id="51cc8-159">-Name</span></span>

<span data-ttu-id="51cc8-160">削除するプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-160">Specifies the names of the properties to remove.</span></span>
<span data-ttu-id="51cc8-161">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-161">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="51cc8-162">-Path</span><span class="sxs-lookup"><span data-stu-id="51cc8-162">-Path</span></span>

<span data-ttu-id="51cc8-163">プロパティを削除する項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-163">Specifies the path of the item whose properties are being removed.</span></span>
<span data-ttu-id="51cc8-164">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-164">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="51cc8-165">-Confirm</span><span class="sxs-lookup"><span data-stu-id="51cc8-165">-Confirm</span></span>

<span data-ttu-id="51cc8-166">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-166">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="51cc8-167">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="51cc8-167">-WhatIf</span></span>

<span data-ttu-id="51cc8-168">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-168">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="51cc8-169">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="51cc8-169">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="51cc8-170">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="51cc8-170">CommonParameters</span></span>

<span data-ttu-id="51cc8-171">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-171">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="51cc8-172">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51cc8-172">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="51cc8-173">入力</span><span class="sxs-lookup"><span data-stu-id="51cc8-173">INPUTS</span></span>

### <span data-ttu-id="51cc8-174">System.String</span><span class="sxs-lookup"><span data-stu-id="51cc8-174">System.String</span></span>

<span data-ttu-id="51cc8-175">パイプを使用してパスを含む文字列をこのコマンドレットに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-175">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="51cc8-176">出力</span><span class="sxs-lookup"><span data-stu-id="51cc8-176">OUTPUTS</span></span>

### <span data-ttu-id="51cc8-177">なし</span><span class="sxs-lookup"><span data-stu-id="51cc8-177">None</span></span>

<span data-ttu-id="51cc8-178">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="51cc8-178">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="51cc8-179">注</span><span class="sxs-lookup"><span data-stu-id="51cc8-179">NOTES</span></span>

- <span data-ttu-id="51cc8-180">PowerShell レジストリプロバイダーでは、レジストリ値はレジストリキーまたはサブキーのプロパティと見なされます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-180">In the PowerShell Registry provider, registry values are considered to be properties of a registry key or subkey.</span></span> <span data-ttu-id="51cc8-181">これらの値は、 **get-itemproperty** コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="51cc8-181">You can use the **ItemProperty** cmdlets to manage these values.</span></span>
- <span data-ttu-id="51cc8-182">`Remove-ItemProperty` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="51cc8-182">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="51cc8-183">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="51cc8-183">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="51cc8-184">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51cc8-184">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="51cc8-185">関連リンク</span><span class="sxs-lookup"><span data-stu-id="51cc8-185">RELATED LINKS</span></span>

[<span data-ttu-id="51cc8-186">Get-Item</span><span class="sxs-lookup"><span data-stu-id="51cc8-186">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="51cc8-187">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="51cc8-187">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="51cc8-188">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="51cc8-188">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="51cc8-189">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="51cc8-189">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="51cc8-190">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="51cc8-190">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="51cc8-191">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="51cc8-191">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="51cc8-192">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="51cc8-192">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="51cc8-193">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="51cc8-193">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="51cc8-194">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="51cc8-194">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="51cc8-195">Set-Location</span><span class="sxs-lookup"><span data-stu-id="51cc8-195">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="51cc8-196">about_Providers</span><span class="sxs-lookup"><span data-stu-id="51cc8-196">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

