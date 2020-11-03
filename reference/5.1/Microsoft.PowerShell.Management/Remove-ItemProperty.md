---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ItemProperty
ms.openlocfilehash: 9ae9c0e7c17a6a63da5487cce138ddce129b975b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214547"
---
# <span data-ttu-id="631f0-103">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="631f0-103">Remove-ItemProperty</span></span>

## <span data-ttu-id="631f0-104">概要</span><span class="sxs-lookup"><span data-stu-id="631f0-104">SYNOPSIS</span></span>
<span data-ttu-id="631f0-105">項目からプロパティとその値を削除します。</span><span class="sxs-lookup"><span data-stu-id="631f0-105">Deletes the property and its value from an item.</span></span>

## <span data-ttu-id="631f0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="631f0-106">SYNTAX</span></span>

### <span data-ttu-id="631f0-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="631f0-107">Path (Default)</span></span>

```
Remove-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="631f0-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="631f0-108">LiteralPath</span></span>

```
Remove-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="631f0-109">Description</span><span class="sxs-lookup"><span data-stu-id="631f0-109">DESCRIPTION</span></span>

<span data-ttu-id="631f0-110">`Remove-ItemProperty`コマンドレットは、項目からプロパティとその値を削除します。</span><span class="sxs-lookup"><span data-stu-id="631f0-110">The `Remove-ItemProperty` cmdlet deletes a property and its value from an item.</span></span>
<span data-ttu-id="631f0-111">これを使用して、レジストリ値とその中に格納されているデータを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="631f0-111">You can use it to delete registry values and the data that they store.</span></span>

## <span data-ttu-id="631f0-112">例</span><span class="sxs-lookup"><span data-stu-id="631f0-112">EXAMPLES</span></span>

### <span data-ttu-id="631f0-113">例 1: レジストリ値を削除する</span><span class="sxs-lookup"><span data-stu-id="631f0-113">Example 1: Delete a registry value</span></span>

<span data-ttu-id="631f0-114">このコマンドは、"HKEY_LOCAL_MACHINE\Software" レジストリキーの "Smpproperty" サブキーから "SmpProperty" レジストリ値とそのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="631f0-114">This command deletes the "SmpProperty" registry value, and its data, from the "SmpApplication" subkey of the "HKEY_LOCAL_MACHINE\Software" registry key.</span></span>

<span data-ttu-id="631f0-115">コマンドはファイルシステムドライブ () から発行されるので、 `PS C:\>` ドライブ、 `HKLM:` 、および "Software" キーを含む "SmpApplication" サブキーの完全修飾パスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="631f0-115">Because the command is issued from a file system drive (`PS C:\>`), it includes the fully qualified path of the "SmpApplication" subkey, including the drive, `HKLM:`, and the "Software" key.</span></span>

<span data-ttu-id="631f0-116">この例では、 **Name** パラメーターを使用して、削除するレジストリ値を識別します。</span><span class="sxs-lookup"><span data-stu-id="631f0-116">It uses the **Name** parameter to identify the registry value that is being deleted.</span></span>

```powershell
Remove-ItemProperty -Path "HKLM:\Software\SmpApplication" -Name "SmpProperty"
```

### <span data-ttu-id="631f0-117">例 2: HKCU の場所からレジストリ値を削除する</span><span class="sxs-lookup"><span data-stu-id="631f0-117">Example 2: Delete a registry value from the HKCU location</span></span>

<span data-ttu-id="631f0-118">これらのコマンドは、"HKEY_CURRENT_USER\Software\MyCompany" の "MyApp" サブキーから、"Options" レジストリ値とそのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="631f0-118">These commands delete the "Options" registry value, and its data, from the "MyApp" subkey of "HKEY_CURRENT_USER\Software\MyCompany".</span></span>

<span data-ttu-id="631f0-119">最初のコマンドは、コマンドレットを使用して、 `Set-Location` 現在の場所を **HKEY_CURRENT_USER** ドライブ ( `HKCU:` ) と "Software\MyCompany\MyApp" サブキーに変更します。</span><span class="sxs-lookup"><span data-stu-id="631f0-119">The first command uses the `Set-Location` cmdlet to change the current location to the **HKEY_CURRENT_USER** drive (`HKCU:`) and the "Software\MyCompany\MyApp" subkey.</span></span>

<span data-ttu-id="631f0-120">2番目のコマンドは、を使用して、" `Remove-ItemProperty` MyApp" サブキーから "Options" レジストリ値とそのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="631f0-120">The second command uses `Remove-ItemProperty` to remove the "Options" registry value, and its data, from the "MyApp" subkey.</span></span>
<span data-ttu-id="631f0-121">**パス** が必要であるため、コマンドはドット ('. ') を使用して現在の場所を示します。</span><span class="sxs-lookup"><span data-stu-id="631f0-121">Because **Path** is required, the command uses a dot ('.') to indicate the current location.</span></span>
<span data-ttu-id="631f0-122">**名前** を使用して、削除するレジストリ値を指定します。</span><span class="sxs-lookup"><span data-stu-id="631f0-122">It uses **Name** to specify which registry value to delete.</span></span>
<span data-ttu-id="631f0-123">**Confirm** パラメーターを使用して、値を削除する前にユーザープロンプトを要求します。</span><span class="sxs-lookup"><span data-stu-id="631f0-123">It uses the **Confirm** parameter to request a user prompt before deleting the value.</span></span>

```
PS C:\> Set-Location HKCU:\Software\MyCompany\MyApp
PS HKCU:\Software\MyCompany\MyApp> Remove-ItemProperty -Path . -Name "Options" -Confirm
```

### <span data-ttu-id="631f0-124">例 3: パイプラインを使用してレジストリ値を削除する</span><span class="sxs-lookup"><span data-stu-id="631f0-124">Example 3: Remove a registry value by using the pipeline</span></span>

<span data-ttu-id="631f0-125">このコマンドは、"NoOfEmployees" レジストリ値とそのデータを "HKLM\Software\MyCompany" レジストリキーから削除します。</span><span class="sxs-lookup"><span data-stu-id="631f0-125">This command deletes the "NoOfEmployees" registry value, and its data, from the "HKLM\Software\MyCompany" registry key.</span></span>

<span data-ttu-id="631f0-126">コマンドは、コマンドレットを使用して、 `Get-Item` レジストリキーを表す項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="631f0-126">The command uses the `Get-Item` cmdlet to get an item that represents the registry key.</span></span>
<span data-ttu-id="631f0-127">パイプライン演算子 () を使用して `|` 、オブジェクトをに送信 `Remove-ItemProperty` します。</span><span class="sxs-lookup"><span data-stu-id="631f0-127">It uses a pipeline operator (`|`) to send the object to `Remove-ItemProperty`.</span></span>
<span data-ttu-id="631f0-128">次に、の **name** パラメーターを使用して、 `Remove-ItemProperty` レジストリ値の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="631f0-128">Then, it uses the **Name** parameter of `Remove-ItemProperty` to specify the name of the registry value.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany | Remove-ItemProperty -Name NoOfEmployees
```

## <span data-ttu-id="631f0-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="631f0-129">PARAMETERS</span></span>

### <span data-ttu-id="631f0-130">-Credential</span><span class="sxs-lookup"><span data-stu-id="631f0-130">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="631f0-131">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="631f0-131">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="631f0-132">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="631f0-132">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="631f0-133">-除外</span><span class="sxs-lookup"><span data-stu-id="631f0-133">-Exclude</span></span>

<span data-ttu-id="631f0-134">このコマンドレットで省略される項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="631f0-134">Specifies items that this cmdlet omits.</span></span>
<span data-ttu-id="631f0-135">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="631f0-135">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="631f0-136">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="631f0-136">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="631f0-137">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="631f0-137">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="631f0-138">-Filter</span><span class="sxs-lookup"><span data-stu-id="631f0-138">-Filter</span></span>

<span data-ttu-id="631f0-139">プロバイダーの形式または言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="631f0-139">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="631f0-140">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="631f0-140">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="631f0-141">ワイルドカード文字の使用など、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="631f0-141">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="631f0-142">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="631f0-142">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="631f0-143">-Force</span><span class="sxs-lookup"><span data-stu-id="631f0-143">-Force</span></span>

<span data-ttu-id="631f0-144">ユーザーがアクセスできないオブジェクトのプロパティをコマンドレットに強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="631f0-144">Forces the cmdlet to remove a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="631f0-145">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="631f0-145">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="631f0-146">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="631f0-146">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="631f0-147">-Include</span><span class="sxs-lookup"><span data-stu-id="631f0-147">-Include</span></span>

<span data-ttu-id="631f0-148">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="631f0-148">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="631f0-149">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="631f0-149">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="631f0-150">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="631f0-150">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="631f0-151">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="631f0-151">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="631f0-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="631f0-152">-LiteralPath</span></span>

<span data-ttu-id="631f0-153">プロパティの現在の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="631f0-153">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="631f0-154">**Path** パラメーターと異なり、 **LiteralPath** の値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="631f0-154">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="631f0-155">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="631f0-155">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="631f0-156">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="631f0-156">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="631f0-157">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="631f0-157">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="631f0-158">-Name</span><span class="sxs-lookup"><span data-stu-id="631f0-158">-Name</span></span>

<span data-ttu-id="631f0-159">削除するプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="631f0-159">Specifies the names of the properties to remove.</span></span>
<span data-ttu-id="631f0-160">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="631f0-160">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="631f0-161">-Path</span><span class="sxs-lookup"><span data-stu-id="631f0-161">-Path</span></span>

<span data-ttu-id="631f0-162">プロパティを削除する項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="631f0-162">Specifies the path of the item whose properties are being removed.</span></span>
<span data-ttu-id="631f0-163">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="631f0-163">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="631f0-164">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="631f0-164">-UseTransaction</span></span>

<span data-ttu-id="631f0-165">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="631f0-165">Includes the command in the active transaction.</span></span>
<span data-ttu-id="631f0-166">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="631f0-166">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="631f0-167">詳細については、「about_Transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="631f0-167">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="631f0-168">-Confirm</span><span class="sxs-lookup"><span data-stu-id="631f0-168">-Confirm</span></span>

<span data-ttu-id="631f0-169">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="631f0-169">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="631f0-170">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="631f0-170">-WhatIf</span></span>

<span data-ttu-id="631f0-171">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="631f0-171">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="631f0-172">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="631f0-172">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="631f0-173">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="631f0-173">CommonParameters</span></span>

<span data-ttu-id="631f0-174">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="631f0-174">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="631f0-175">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="631f0-175">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="631f0-176">入力</span><span class="sxs-lookup"><span data-stu-id="631f0-176">INPUTS</span></span>

### <span data-ttu-id="631f0-177">System.String</span><span class="sxs-lookup"><span data-stu-id="631f0-177">System.String</span></span>

<span data-ttu-id="631f0-178">パイプを使用してパスを含む文字列をこのコマンドレットに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="631f0-178">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="631f0-179">出力</span><span class="sxs-lookup"><span data-stu-id="631f0-179">OUTPUTS</span></span>

### <span data-ttu-id="631f0-180">なし</span><span class="sxs-lookup"><span data-stu-id="631f0-180">None</span></span>

<span data-ttu-id="631f0-181">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="631f0-181">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="631f0-182">注</span><span class="sxs-lookup"><span data-stu-id="631f0-182">NOTES</span></span>

<span data-ttu-id="631f0-183">PowerShell レジストリプロバイダーでは、レジストリ値はレジストリキーまたはサブキーのプロパティと見なされます。</span><span class="sxs-lookup"><span data-stu-id="631f0-183">In the PowerShell Registry provider, registry values are considered to be properties of a registry key or subkey.</span></span> <span data-ttu-id="631f0-184">これらの値は、 **get-itemproperty** コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="631f0-184">You can use the **ItemProperty** cmdlets to manage these values.</span></span>

<span data-ttu-id="631f0-185">`Remove-ItemProperty` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="631f0-185">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="631f0-186">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="631f0-186">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="631f0-187">詳細については、「about_Providers」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="631f0-187">For more information, see about_Providers.</span></span>

## <span data-ttu-id="631f0-188">関連リンク</span><span class="sxs-lookup"><span data-stu-id="631f0-188">RELATED LINKS</span></span>

[<span data-ttu-id="631f0-189">Get-Item</span><span class="sxs-lookup"><span data-stu-id="631f0-189">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="631f0-190">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="631f0-190">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="631f0-191">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="631f0-191">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="631f0-192">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="631f0-192">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="631f0-193">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="631f0-193">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="631f0-194">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="631f0-194">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="631f0-195">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="631f0-195">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="631f0-196">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="631f0-196">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="631f0-197">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="631f0-197">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="631f0-198">about_Providers</span><span class="sxs-lookup"><span data-stu-id="631f0-198">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
