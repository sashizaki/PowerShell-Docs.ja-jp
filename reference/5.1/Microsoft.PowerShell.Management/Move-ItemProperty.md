---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ItemProperty
ms.openlocfilehash: 4cf883964e1ff86487bf5abca8789af62b274c8a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214624"
---
# <span data-ttu-id="3f497-103">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3f497-103">Move-ItemProperty</span></span>

## <span data-ttu-id="3f497-104">構文</span><span class="sxs-lookup"><span data-stu-id="3f497-104">Synopsis</span></span>
<span data-ttu-id="3f497-105">プロパティをある場所から別の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="3f497-105">Moves a property from one location to another.</span></span>

## <span data-ttu-id="3f497-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3f497-106">SYNTAX</span></span>

### <span data-ttu-id="3f497-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="3f497-107">Path (Default)</span></span>

```
Move-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="3f497-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3f497-108">LiteralPath</span></span>

```
Move-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="3f497-109">説明</span><span class="sxs-lookup"><span data-stu-id="3f497-109">Description</span></span>

<span data-ttu-id="3f497-110">コマンドレットは、項目 `Move-ItemProperty` のプロパティをある項目から別の項目に移動します。</span><span class="sxs-lookup"><span data-stu-id="3f497-110">The `Move-ItemProperty` cmdlet moves a property of an item from one item to another item.</span></span>
<span data-ttu-id="3f497-111">たとえば、あるレジストリキーから別のレジストリキーにレジストリエントリを移動できます。</span><span class="sxs-lookup"><span data-stu-id="3f497-111">For instance, it can move a registry entry from one registry key to another registry key.</span></span>
<span data-ttu-id="3f497-112">項目のプロパティを移動すると、そのプロパティが新しい場所に追加され、元の場所から削除されます。</span><span class="sxs-lookup"><span data-stu-id="3f497-112">When you move an item property, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="3f497-113">例</span><span class="sxs-lookup"><span data-stu-id="3f497-113">EXAMPLES</span></span>

### <span data-ttu-id="3f497-114">例 1: レジストリ値とそのデータを別のキーに移動する</span><span class="sxs-lookup"><span data-stu-id="3f497-114">Example 1: Move a registry value and its data to another key</span></span>

<span data-ttu-id="3f497-115">このコマンドは、Version レジストリ値とそのデータを、"MyApp" サブキーからレジストリキーの NewApp サブキーに移動し `HKLM\Software\MyCompany` ます。</span><span class="sxs-lookup"><span data-stu-id="3f497-115">This command moves the Version registry value, and its data, from the "MyApp" subkey to the NewApp subkey of the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Move-ItemProperty "HKLM:\Software\MyCompany\MyApp" -Name "Version" -Destination "HKLM:\Software\MyCompany\NewApp"
```

## <span data-ttu-id="3f497-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3f497-116">PARAMETERS</span></span>

### <span data-ttu-id="3f497-117">-Credential</span><span class="sxs-lookup"><span data-stu-id="3f497-117">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="3f497-118">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3f497-118">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="3f497-119">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f497-119">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="3f497-120">-Destination</span><span class="sxs-lookup"><span data-stu-id="3f497-120">-Destination</span></span>

<span data-ttu-id="3f497-121">移動先のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f497-121">Specifies the path to the destination location.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3f497-122">-除外</span><span class="sxs-lookup"><span data-stu-id="3f497-122">-Exclude</span></span>

<span data-ttu-id="3f497-123">このコマンドレットによって操作から除外されるプロパティまたはプロパティを、文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="3f497-123">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="3f497-124">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="3f497-124">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="3f497-125">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="3f497-125">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="3f497-126">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f497-126">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="3f497-127">-Filter</span><span class="sxs-lookup"><span data-stu-id="3f497-127">-Filter</span></span>

<span data-ttu-id="3f497-128">プロバイダーの形式または言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f497-128">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="3f497-129">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="3f497-129">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="3f497-130">ワイルドカード文字の使用など、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3f497-130">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="3f497-131">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="3f497-131">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="3f497-132">-Force</span><span class="sxs-lookup"><span data-stu-id="3f497-132">-Force</span></span>

<span data-ttu-id="3f497-133">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3f497-133">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="3f497-134">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="3f497-134">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="3f497-135">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f497-135">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="3f497-136">-Include</span><span class="sxs-lookup"><span data-stu-id="3f497-136">-Include</span></span>

<span data-ttu-id="3f497-137">このコマンドレットによって操作に含まれるプロパティまたはプロパティを、文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="3f497-137">Specifies, as a string array, a property or property that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="3f497-138">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="3f497-138">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="3f497-139">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="3f497-139">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="3f497-140">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f497-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="3f497-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3f497-141">-LiteralPath</span></span>

<span data-ttu-id="3f497-142">プロパティの現在の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f497-142">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="3f497-143">**Path** パラメーターと異なり、 **LiteralPath** の値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f497-143">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="3f497-144">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="3f497-144">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="3f497-145">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="3f497-145">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="3f497-146">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="3f497-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="3f497-147">-Name</span><span class="sxs-lookup"><span data-stu-id="3f497-147">-Name</span></span>

<span data-ttu-id="3f497-148">移動対象のプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f497-148">Specifies the name of the property to be moved.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3f497-149">-PassThru</span><span class="sxs-lookup"><span data-stu-id="3f497-149">-PassThru</span></span>

<span data-ttu-id="3f497-150">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="3f497-150">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="3f497-151">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="3f497-151">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="3f497-152">-Path</span><span class="sxs-lookup"><span data-stu-id="3f497-152">-Path</span></span>

<span data-ttu-id="3f497-153">プロパティの現在の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f497-153">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="3f497-154">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f497-154">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="3f497-155">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="3f497-155">-UseTransaction</span></span>

<span data-ttu-id="3f497-156">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3f497-156">Includes the command in the active transaction.</span></span>
<span data-ttu-id="3f497-157">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="3f497-157">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="3f497-158">詳細については、「about_Transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f497-158">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="3f497-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3f497-159">-Confirm</span></span>

<span data-ttu-id="3f497-160">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f497-160">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3f497-161">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3f497-161">-WhatIf</span></span>

<span data-ttu-id="3f497-162">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="3f497-162">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="3f497-163">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="3f497-163">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3f497-164">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f497-164">CommonParameters</span></span>

<span data-ttu-id="3f497-165">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="3f497-165">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="3f497-166">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f497-166">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="3f497-167">入力</span><span class="sxs-lookup"><span data-stu-id="3f497-167">INPUTS</span></span>

### <span data-ttu-id="3f497-168">System.String</span><span class="sxs-lookup"><span data-stu-id="3f497-168">System.String</span></span>

<span data-ttu-id="3f497-169">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="3f497-169">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="3f497-170">出力</span><span class="sxs-lookup"><span data-stu-id="3f497-170">OUTPUTS</span></span>

### <span data-ttu-id="3f497-171">なしまたはシステムの管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="3f497-171">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="3f497-172">**PassThru** パラメーターを使用すると、このコマンドレットは移動した項目プロパティを表す **pscustomobject** 生成します。</span><span class="sxs-lookup"><span data-stu-id="3f497-172">When you use the **PassThru** parameter, this cmdlet generates a **PSCustomObject** representing the moved item property.</span></span>
<span data-ttu-id="3f497-173">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="3f497-173">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3f497-174">注</span><span class="sxs-lookup"><span data-stu-id="3f497-174">NOTES</span></span>

<span data-ttu-id="3f497-175">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="3f497-175">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="3f497-176">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="3f497-176">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="3f497-177">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f497-177">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="3f497-178">関連リンク</span><span class="sxs-lookup"><span data-stu-id="3f497-178">RELATED LINKS</span></span>

[<span data-ttu-id="3f497-179">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3f497-179">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="3f497-180">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3f497-180">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="3f497-181">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3f497-181">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="3f497-182">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3f497-182">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="3f497-183">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3f497-183">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="3f497-184">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3f497-184">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="3f497-185">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3f497-185">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="3f497-186">about_Providers</span><span class="sxs-lookup"><span data-stu-id="3f497-186">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
