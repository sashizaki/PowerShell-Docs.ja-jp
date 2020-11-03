---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-itemproperty?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-ItemProperty
ms.openlocfilehash: d9403a2572926101a7ccab8992013b60e4fb77f4
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210864"
---
# <span data-ttu-id="73d10-103">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73d10-103">Rename-ItemProperty</span></span>

## <span data-ttu-id="73d10-104">概要</span><span class="sxs-lookup"><span data-stu-id="73d10-104">SYNOPSIS</span></span>
<span data-ttu-id="73d10-105">項目のプロパティの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="73d10-105">Renames a property of an item.</span></span>

## <span data-ttu-id="73d10-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="73d10-106">SYNTAX</span></span>

### <span data-ttu-id="73d10-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="73d10-107">Path (Default)</span></span>

```
Rename-ItemProperty [-Path] <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="73d10-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="73d10-108">LiteralPath</span></span>

```
Rename-ItemProperty -LiteralPath <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="73d10-109">Description</span><span class="sxs-lookup"><span data-stu-id="73d10-109">DESCRIPTION</span></span>

<span data-ttu-id="73d10-110">`Rename-ItemProperty`コマンドレットは、指定された項目のプロパティの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="73d10-110">The `Rename-ItemProperty` cmdlet changes the name of a specified item property.</span></span>
<span data-ttu-id="73d10-111">プロパティの値は変更されません。</span><span class="sxs-lookup"><span data-stu-id="73d10-111">The value of the property is not changed.</span></span>
<span data-ttu-id="73d10-112">たとえば、を使用して、 `Rename-ItemProperty` レジストリエントリの名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="73d10-112">For example, you can use `Rename-ItemProperty` to change the name of a registry entry.</span></span>

## <span data-ttu-id="73d10-113">例</span><span class="sxs-lookup"><span data-stu-id="73d10-113">EXAMPLES</span></span>

### <span data-ttu-id="73d10-114">例 1: レジストリエントリの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="73d10-114">Example 1: Rename a registry entry</span></span>

<span data-ttu-id="73d10-115">このコマンドを実行すると、キーに含まれている構成レジストリエントリの名前が `HKEY_LOCAL_MACHINE\Software\SmpApplication` "oldconfig" に変更されます。</span><span class="sxs-lookup"><span data-stu-id="73d10-115">This command renames the config registry entry that is contained in the `HKEY_LOCAL_MACHINE\Software\SmpApplication` key to "oldconfig".</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\Software\SmpApplication -Name config -NewName oldconfig
```

## <span data-ttu-id="73d10-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="73d10-116">PARAMETERS</span></span>

### <span data-ttu-id="73d10-117">-Credential</span><span class="sxs-lookup"><span data-stu-id="73d10-117">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="73d10-118">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="73d10-118">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="73d10-119">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="73d10-119">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="73d10-120">-除外</span><span class="sxs-lookup"><span data-stu-id="73d10-120">-Exclude</span></span>

<span data-ttu-id="73d10-121">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="73d10-121">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="73d10-122">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="73d10-122">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="73d10-123">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="73d10-123">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="73d10-124">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="73d10-124">Wildcard characters are permitted.</span></span> <span data-ttu-id="73d10-125">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="73d10-125">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="73d10-126">-Filter</span><span class="sxs-lookup"><span data-stu-id="73d10-126">-Filter</span></span>

<span data-ttu-id="73d10-127">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="73d10-127">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="73d10-128">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="73d10-128">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="73d10-129">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73d10-129">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="73d10-130">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="73d10-130">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="73d10-131">-Force</span><span class="sxs-lookup"><span data-stu-id="73d10-131">-Force</span></span>

<span data-ttu-id="73d10-132">このコマンドレットによって、ユーザーがアクセスできないオブジェクトのプロパティの名前を強制的に変更します。</span><span class="sxs-lookup"><span data-stu-id="73d10-132">Forces the cmdlet to rename a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="73d10-133">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="73d10-133">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="73d10-134">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73d10-134">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="73d10-135">-Include</span><span class="sxs-lookup"><span data-stu-id="73d10-135">-Include</span></span>

<span data-ttu-id="73d10-136">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="73d10-136">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="73d10-137">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="73d10-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="73d10-138">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="73d10-138">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="73d10-139">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="73d10-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="73d10-140">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="73d10-140">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="73d10-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="73d10-141">-LiteralPath</span></span>

<span data-ttu-id="73d10-142">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="73d10-142">Specifies a path to one or more locations.</span></span> <span data-ttu-id="73d10-143">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="73d10-143">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="73d10-144">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="73d10-144">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="73d10-145">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="73d10-145">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="73d10-146">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="73d10-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="73d10-147">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73d10-147">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="73d10-148">-Name</span><span class="sxs-lookup"><span data-stu-id="73d10-148">-Name</span></span>

<span data-ttu-id="73d10-149">名前を変更するプロパティの現在の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="73d10-149">Specifies the current name of the property to rename.</span></span>

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

### <span data-ttu-id="73d10-150">-NewName</span><span class="sxs-lookup"><span data-stu-id="73d10-150">-NewName</span></span>

<span data-ttu-id="73d10-151">プロパティの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="73d10-151">Specifies the new name for the property.</span></span>

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

### <span data-ttu-id="73d10-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="73d10-152">-PassThru</span></span>

<span data-ttu-id="73d10-153">項目プロパティを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="73d10-153">Returns an object that represents the item property.</span></span>
<span data-ttu-id="73d10-154">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="73d10-154">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="73d10-155">-Path</span><span class="sxs-lookup"><span data-stu-id="73d10-155">-Path</span></span>

<span data-ttu-id="73d10-156">名前を変更する項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="73d10-156">Specifies the path of the item to rename.</span></span>
<span data-ttu-id="73d10-157">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="73d10-157">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="73d10-158">-Confirm</span><span class="sxs-lookup"><span data-stu-id="73d10-158">-Confirm</span></span>

<span data-ttu-id="73d10-159">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="73d10-159">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="73d10-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="73d10-160">-WhatIf</span></span>

<span data-ttu-id="73d10-161">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="73d10-161">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="73d10-162">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="73d10-162">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="73d10-163">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="73d10-163">CommonParameters</span></span>

<span data-ttu-id="73d10-164">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="73d10-164">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="73d10-165">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73d10-165">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="73d10-166">入力</span><span class="sxs-lookup"><span data-stu-id="73d10-166">INPUTS</span></span>

### <span data-ttu-id="73d10-167">System.String</span><span class="sxs-lookup"><span data-stu-id="73d10-167">System.String</span></span>

<span data-ttu-id="73d10-168">パイプを使用してパスを含む文字列をこのコマンドレットに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="73d10-168">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="73d10-169">出力</span><span class="sxs-lookup"><span data-stu-id="73d10-169">OUTPUTS</span></span>

### <span data-ttu-id="73d10-170">なし、システム管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="73d10-170">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="73d10-171">このコマンドレットは、 **PassThru** パラメーターを指定した場合、名前が変更された item プロパティを表す **pscustomobject** 生成します。</span><span class="sxs-lookup"><span data-stu-id="73d10-171">This cmdlet generates a **PSCustomObject** that represents the renamed item property, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="73d10-172">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="73d10-172">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="73d10-173">注</span><span class="sxs-lookup"><span data-stu-id="73d10-173">NOTES</span></span>

<span data-ttu-id="73d10-174">`Remove-ItemProperty` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="73d10-174">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="73d10-175">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="73d10-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="73d10-176">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73d10-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="73d10-177">関連リンク</span><span class="sxs-lookup"><span data-stu-id="73d10-177">RELATED LINKS</span></span>

[<span data-ttu-id="73d10-178">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73d10-178">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="73d10-179">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73d10-179">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="73d10-180">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73d10-180">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="73d10-181">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73d10-181">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="73d10-182">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73d10-182">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="73d10-183">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73d10-183">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="73d10-184">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="73d10-184">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="73d10-185">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73d10-185">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="73d10-186">about_Providers</span><span class="sxs-lookup"><span data-stu-id="73d10-186">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
