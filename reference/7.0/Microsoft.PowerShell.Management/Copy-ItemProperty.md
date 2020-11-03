---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-itemproperty?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-ItemProperty
ms.openlocfilehash: 9fddb6003627162094b89f738071e977cae77e99
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209672"
---
# <span data-ttu-id="9f680-103">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9f680-103">Copy-ItemProperty</span></span>

## <span data-ttu-id="9f680-104">概要</span><span class="sxs-lookup"><span data-stu-id="9f680-104">SYNOPSIS</span></span>
<span data-ttu-id="9f680-105">プロパティとその値を、指定された場所から別の場所へコピーします。</span><span class="sxs-lookup"><span data-stu-id="9f680-105">Copies a property and value from a specified location to another location.</span></span>

## <span data-ttu-id="9f680-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9f680-106">SYNTAX</span></span>

### <span data-ttu-id="9f680-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="9f680-107">Path (Default)</span></span>

```
Copy-ItemProperty [-Path] <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9f680-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9f680-108">LiteralPath</span></span>

```
Copy-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9f680-109">Description</span><span class="sxs-lookup"><span data-stu-id="9f680-109">DESCRIPTION</span></span>

<span data-ttu-id="9f680-110">`Copy-ItemProperty`コマンドレットは、プロパティと値を指定した場所から別の場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9f680-110">The `Copy-ItemProperty` cmdlet copies a property and value from a specified location to another location.</span></span>
<span data-ttu-id="9f680-111">たとえば、このコマンドレットを使用すると、1つのレジストリキーから別のレジストリキーに1つ以上のレジストリエントリをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="9f680-111">For instance, you can use this cmdlet to copy one or more registry entries from one registry key to another registry key.</span></span>

## <span data-ttu-id="9f680-112">例</span><span class="sxs-lookup"><span data-stu-id="9f680-112">EXAMPLES</span></span>

### <span data-ttu-id="9f680-113">例 1: レジストリキーから別のレジストリキーにプロパティをコピーする</span><span class="sxs-lookup"><span data-stu-id="9f680-113">Example 1: Copy a property from a registry key to another registry key</span></span>

<span data-ttu-id="9f680-114">このコマンドは、"T.myproperty" という名前のプロパティを "MyApplication" レジストリキーから "MyApplicationRev2" レジストリキーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9f680-114">This command copies the property named "MyProperty" from the "MyApplication" registry key to the "MyApplicationRev2" registry key.</span></span>

```powershell
Copy-ItemProperty -Path "MyApplication" -Destination "HKLM:\Software\MyApplicationRev2" -Name "MyProperty"
```

## <span data-ttu-id="9f680-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9f680-115">PARAMETERS</span></span>

### <span data-ttu-id="9f680-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="9f680-116">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="9f680-117">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9f680-117">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="9f680-118">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="9f680-118">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="9f680-119">-Destination</span><span class="sxs-lookup"><span data-stu-id="9f680-119">-Destination</span></span>

<span data-ttu-id="9f680-120">移動先のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f680-120">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="9f680-121">-除外</span><span class="sxs-lookup"><span data-stu-id="9f680-121">-Exclude</span></span>

<span data-ttu-id="9f680-122">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="9f680-122">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="9f680-123">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="9f680-123">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="9f680-124">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="9f680-124">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="9f680-125">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f680-125">Wildcard characters are permitted.</span></span> <span data-ttu-id="9f680-126">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="9f680-126">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="9f680-127">-Filter</span><span class="sxs-lookup"><span data-stu-id="9f680-127">-Filter</span></span>

<span data-ttu-id="9f680-128">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f680-128">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="9f680-129">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="9f680-129">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="9f680-130">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f680-130">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="9f680-131">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="9f680-131">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="9f680-132">-Force</span><span class="sxs-lookup"><span data-stu-id="9f680-132">-Force</span></span>

<span data-ttu-id="9f680-133">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9f680-133">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="9f680-134">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="9f680-134">Implementation varies from provider to provider.</span></span>

<span data-ttu-id="9f680-135">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f680-135">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="9f680-136">-Include</span><span class="sxs-lookup"><span data-stu-id="9f680-136">-Include</span></span>

<span data-ttu-id="9f680-137">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="9f680-137">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="9f680-138">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="9f680-138">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="9f680-139">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="9f680-139">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="9f680-140">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f680-140">Wildcard characters are permitted.</span></span> <span data-ttu-id="9f680-141">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="9f680-141">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="9f680-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9f680-142">-LiteralPath</span></span>

<span data-ttu-id="9f680-143">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f680-143">Specifies a path to one or more locations.</span></span> <span data-ttu-id="9f680-144">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f680-144">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="9f680-145">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="9f680-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="9f680-146">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="9f680-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="9f680-147">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="9f680-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="9f680-148">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f680-148">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="9f680-149">-Name</span><span class="sxs-lookup"><span data-stu-id="9f680-149">-Name</span></span>

<span data-ttu-id="9f680-150">コピーするプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9f680-150">Specifies the name of the property to be copied.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9f680-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="9f680-151">-PassThru</span></span>

<span data-ttu-id="9f680-152">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="9f680-152">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="9f680-153">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="9f680-153">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="9f680-154">-Path</span><span class="sxs-lookup"><span data-stu-id="9f680-154">-Path</span></span>

<span data-ttu-id="9f680-155">文字列配列として、コピーするプロパティへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f680-155">Specifies, as a string array, the path to the property to be copied.</span></span>
<span data-ttu-id="9f680-156">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f680-156">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="9f680-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9f680-157">-Confirm</span></span>

<span data-ttu-id="9f680-158">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f680-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9f680-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9f680-159">-WhatIf</span></span>

<span data-ttu-id="9f680-160">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="9f680-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="9f680-161">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="9f680-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9f680-162">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9f680-162">CommonParameters</span></span>

<span data-ttu-id="9f680-163">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="9f680-163">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="9f680-164">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f680-164">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9f680-165">入力</span><span class="sxs-lookup"><span data-stu-id="9f680-165">INPUTS</span></span>

### <span data-ttu-id="9f680-166">System.String</span><span class="sxs-lookup"><span data-stu-id="9f680-166">System.String</span></span>

<span data-ttu-id="9f680-167">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="9f680-167">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="9f680-168">出力</span><span class="sxs-lookup"><span data-stu-id="9f680-168">OUTPUTS</span></span>

### <span data-ttu-id="9f680-169">なしまたはシステムの管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="9f680-169">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="9f680-170">**Passthru** パラメーターを使用すると、このコマンドレットは、コピーされた項目プロパティを表す **pscustomobject** 生成します。</span><span class="sxs-lookup"><span data-stu-id="9f680-170">When you use the **Passthru** parameter, this cmdlet generates a **PsCustomObject** representing the copied item property.</span></span> <span data-ttu-id="9f680-171">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="9f680-171">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9f680-172">注</span><span class="sxs-lookup"><span data-stu-id="9f680-172">NOTES</span></span>

<span data-ttu-id="9f680-173">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="9f680-173">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="9f680-174">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="9f680-174">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="9f680-175">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f680-175">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="9f680-176">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9f680-176">RELATED LINKS</span></span>

[<span data-ttu-id="9f680-177">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9f680-177">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="9f680-178">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9f680-178">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="9f680-179">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9f680-179">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="9f680-180">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9f680-180">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="9f680-181">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9f680-181">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="9f680-182">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9f680-182">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="9f680-183">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="9f680-183">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="9f680-184">about_Providers</span><span class="sxs-lookup"><span data-stu-id="9f680-184">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
