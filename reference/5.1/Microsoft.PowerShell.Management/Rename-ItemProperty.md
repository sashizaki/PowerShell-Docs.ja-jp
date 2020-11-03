---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-ItemProperty
ms.openlocfilehash: 5cbd228f78da3bf7fa70a001391bc98f63085a73
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214531"
---
# <span data-ttu-id="d2b53-103">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d2b53-103">Rename-ItemProperty</span></span>

## <span data-ttu-id="d2b53-104">概要</span><span class="sxs-lookup"><span data-stu-id="d2b53-104">SYNOPSIS</span></span>
<span data-ttu-id="d2b53-105">項目のプロパティの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-105">Renames a property of an item.</span></span>

## <span data-ttu-id="d2b53-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d2b53-106">SYNTAX</span></span>

### <span data-ttu-id="d2b53-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="d2b53-107">Path (Default)</span></span>

```
Rename-ItemProperty [-Path] <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="d2b53-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d2b53-108">LiteralPath</span></span>

```
Rename-ItemProperty -LiteralPath <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="d2b53-109">Description</span><span class="sxs-lookup"><span data-stu-id="d2b53-109">DESCRIPTION</span></span>

<span data-ttu-id="d2b53-110">`Rename-ItemProperty`コマンドレットは、指定された項目のプロパティの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-110">The `Rename-ItemProperty` cmdlet changes the name of a specified item property.</span></span>
<span data-ttu-id="d2b53-111">プロパティの値は変更されません。</span><span class="sxs-lookup"><span data-stu-id="d2b53-111">The value of the property is not changed.</span></span>
<span data-ttu-id="d2b53-112">たとえば、を使用して、 `Rename-ItemProperty` レジストリエントリの名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d2b53-112">For example, you can use `Rename-ItemProperty` to change the name of a registry entry.</span></span>

## <span data-ttu-id="d2b53-113">例</span><span class="sxs-lookup"><span data-stu-id="d2b53-113">EXAMPLES</span></span>

### <span data-ttu-id="d2b53-114">例 1: レジストリエントリの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="d2b53-114">Example 1: Rename a registry entry</span></span>

<span data-ttu-id="d2b53-115">このコマンドは、"HKEY_LOCAL_MACHINE\Software\SmpApplication" キーに含まれている構成レジストリエントリの名前を "oldconfig" に変更します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-115">This command renames the config registry entry that is contained in the "HKEY_LOCAL_MACHINE\Software\SmpApplication" key to "oldconfig".</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\Software\SmpApplication -Name config -NewName oldconfig
```

## <span data-ttu-id="d2b53-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d2b53-116">PARAMETERS</span></span>

### <span data-ttu-id="d2b53-117">-Credential</span><span class="sxs-lookup"><span data-stu-id="d2b53-117">-Credential</span></span>

<span data-ttu-id="d2b53-118">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-118">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="d2b53-119">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="d2b53-119">The default is the current user.</span></span>

<span data-ttu-id="d2b53-120">「User01」や「Domain01\User01」のようなユーザー名を入力するか、  コマンドレットで生成されるような `Get-Credential` オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-120">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="d2b53-121">ユーザー名を入力すると、パスワードの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2b53-121">If you type a user name, you are prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="d2b53-122">このパラメーターは、Windows PowerShell でインストールされるプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d2b53-122">This parameter is not supported by any providers installed with Windows PowerShell.</span></span>

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

### <span data-ttu-id="d2b53-123">-除外</span><span class="sxs-lookup"><span data-stu-id="d2b53-123">-Exclude</span></span>

<span data-ttu-id="d2b53-124">このコマンドレットで省略される項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-124">Specifies items that this cmdlet omits.</span></span>
<span data-ttu-id="d2b53-125">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-125">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="d2b53-126">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-126">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="d2b53-127">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d2b53-127">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="d2b53-128">-Filter</span><span class="sxs-lookup"><span data-stu-id="d2b53-128">-Filter</span></span>

<span data-ttu-id="d2b53-129">プロバイダーの形式または言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-129">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="d2b53-130">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-130">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="d2b53-131">ワイルドカード文字の使用など、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d2b53-131">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="d2b53-132">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="d2b53-132">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="d2b53-133">-Force</span><span class="sxs-lookup"><span data-stu-id="d2b53-133">-Force</span></span>

<span data-ttu-id="d2b53-134">このコマンドレットによって、ユーザーがアクセスできないオブジェクトのプロパティの名前を強制的に変更します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-134">Forces the cmdlet to rename a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="d2b53-135">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="d2b53-135">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="d2b53-136">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2b53-136">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="d2b53-137">-Include</span><span class="sxs-lookup"><span data-stu-id="d2b53-137">-Include</span></span>

<span data-ttu-id="d2b53-138">コマンドレットが動作する項目だけを指定します。他の項目は除外されます。</span><span class="sxs-lookup"><span data-stu-id="d2b53-138">Specifies only those items upon which the cmdlet acts, excluding all others.</span></span>
<span data-ttu-id="d2b53-139">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-139">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="d2b53-140">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-140">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="d2b53-141">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d2b53-141">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="d2b53-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d2b53-142">-LiteralPath</span></span>

<span data-ttu-id="d2b53-143">項目プロパティのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-143">Specifies a path of the item property.</span></span>
<span data-ttu-id="d2b53-144">**Path** パラメーターと異なり、 **LiteralPath** の値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d2b53-144">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="d2b53-145">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="d2b53-145">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="d2b53-146">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="d2b53-146">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="d2b53-147">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="d2b53-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d2b53-148">-Name</span><span class="sxs-lookup"><span data-stu-id="d2b53-148">-Name</span></span>

<span data-ttu-id="d2b53-149">名前を変更するプロパティの現在の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-149">Specifies the current name of the property to rename.</span></span>

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

### <span data-ttu-id="d2b53-150">-NewName</span><span class="sxs-lookup"><span data-stu-id="d2b53-150">-NewName</span></span>

<span data-ttu-id="d2b53-151">プロパティの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-151">Specifies the new name for the property.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d2b53-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d2b53-152">-PassThru</span></span>

<span data-ttu-id="d2b53-153">項目プロパティを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-153">Returns an object that represents the item property.</span></span>
<span data-ttu-id="d2b53-154">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="d2b53-154">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="d2b53-155">-Path</span><span class="sxs-lookup"><span data-stu-id="d2b53-155">-Path</span></span>

<span data-ttu-id="d2b53-156">名前を変更する項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-156">Specifies the path of the item to rename.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="d2b53-157">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="d2b53-157">-UseTransaction</span></span>

<span data-ttu-id="d2b53-158">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d2b53-158">Includes the command in the active transaction.</span></span>
<span data-ttu-id="d2b53-159">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="d2b53-159">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="d2b53-160">詳細については、「[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2b53-160">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="d2b53-161">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d2b53-161">-Confirm</span></span>

<span data-ttu-id="d2b53-162">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2b53-162">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d2b53-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d2b53-163">-WhatIf</span></span>

<span data-ttu-id="d2b53-164">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-164">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d2b53-165">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="d2b53-165">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d2b53-166">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d2b53-166">CommonParameters</span></span>

<span data-ttu-id="d2b53-167">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="d2b53-167">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="d2b53-168">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2b53-168">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d2b53-169">入力</span><span class="sxs-lookup"><span data-stu-id="d2b53-169">INPUTS</span></span>

### <span data-ttu-id="d2b53-170">System.String</span><span class="sxs-lookup"><span data-stu-id="d2b53-170">System.String</span></span>

<span data-ttu-id="d2b53-171">パイプを使用してパスを含む文字列をこのコマンドレットに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="d2b53-171">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="d2b53-172">出力</span><span class="sxs-lookup"><span data-stu-id="d2b53-172">OUTPUTS</span></span>

### <span data-ttu-id="d2b53-173">なし、システム管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="d2b53-173">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="d2b53-174">このコマンドレットは、 *PassThru* パラメーターを指定した場合、名前が変更された item プロパティを表す **pscustomobject** 生成します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-174">This cmdlet generates a **PSCustomObject** that represents the renamed item property, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="d2b53-175">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="d2b53-175">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d2b53-176">注</span><span class="sxs-lookup"><span data-stu-id="d2b53-176">NOTES</span></span>

<span data-ttu-id="d2b53-177">`Remove-ItemProperty` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="d2b53-177">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="d2b53-178">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="d2b53-178">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="d2b53-179">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2b53-179">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="d2b53-180">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d2b53-180">RELATED LINKS</span></span>

[<span data-ttu-id="d2b53-181">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d2b53-181">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="d2b53-182">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d2b53-182">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="d2b53-183">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d2b53-183">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="d2b53-184">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d2b53-184">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="d2b53-185">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d2b53-185">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="d2b53-186">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d2b53-186">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="d2b53-187">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="d2b53-187">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="d2b53-188">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d2b53-188">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="d2b53-189">about_Providers</span><span class="sxs-lookup"><span data-stu-id="d2b53-189">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)