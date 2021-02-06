---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-ItemProperty
ms.openlocfilehash: d6dd6d21d7c0022e8ca1ea7dbd8e1cab8a680de6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604953"
---
# <span data-ttu-id="5d620-102">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5d620-102">Copy-ItemProperty</span></span>

## <span data-ttu-id="5d620-103">概要</span><span class="sxs-lookup"><span data-stu-id="5d620-103">SYNOPSIS</span></span>
<span data-ttu-id="5d620-104">プロパティとその値を、指定された場所から別の場所へコピーします。</span><span class="sxs-lookup"><span data-stu-id="5d620-104">Copies a property and value from a specified location to another location.</span></span>

## <span data-ttu-id="5d620-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5d620-105">SYNTAX</span></span>

### <span data-ttu-id="5d620-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="5d620-106">Path (Default)</span></span>

```
Copy-ItemProperty [-Path] <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5d620-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="5d620-107">LiteralPath</span></span>

```
Copy-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5d620-108">Description</span><span class="sxs-lookup"><span data-stu-id="5d620-108">DESCRIPTION</span></span>

<span data-ttu-id="5d620-109">`Copy-ItemProperty`コマンドレットは、プロパティと値を指定した場所から別の場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="5d620-109">The `Copy-ItemProperty` cmdlet copies a property and value from a specified location to another location.</span></span>
<span data-ttu-id="5d620-110">たとえば、このコマンドレットを使用すると、1つのレジストリキーから別のレジストリキーに1つ以上のレジストリエントリをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="5d620-110">For instance, you can use this cmdlet to copy one or more registry entries from one registry key to another registry key.</span></span>

## <span data-ttu-id="5d620-111">例</span><span class="sxs-lookup"><span data-stu-id="5d620-111">EXAMPLES</span></span>

### <span data-ttu-id="5d620-112">例 1: レジストリキーから別のレジストリキーにプロパティをコピーする</span><span class="sxs-lookup"><span data-stu-id="5d620-112">Example 1: Copy a property from a registry key to another registry key</span></span>

<span data-ttu-id="5d620-113">このコマンドは、"T.myproperty" という名前のプロパティを "MyApplication" レジストリキーから "MyApplicationRev2" レジストリキーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="5d620-113">This command copies the property named "MyProperty" from the "MyApplication" registry key to the "MyApplicationRev2" registry key.</span></span>

```powershell
Copy-ItemProperty -Path "MyApplication" -Destination "HKLM:\Software\MyApplicationRev2" -Name "MyProperty"
```

## <span data-ttu-id="5d620-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5d620-114">PARAMETERS</span></span>

### <span data-ttu-id="5d620-115">-Credential</span><span class="sxs-lookup"><span data-stu-id="5d620-115">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="5d620-116">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5d620-116">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="5d620-117">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d620-117">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="5d620-118">-Destination</span><span class="sxs-lookup"><span data-stu-id="5d620-118">-Destination</span></span>

<span data-ttu-id="5d620-119">移動先のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d620-119">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="5d620-120">-除外</span><span class="sxs-lookup"><span data-stu-id="5d620-120">-Exclude</span></span>

<span data-ttu-id="5d620-121">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="5d620-121">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="5d620-122">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="5d620-122">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="5d620-123">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="5d620-123">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="5d620-124">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d620-124">Wildcard characters are permitted.</span></span> <span data-ttu-id="5d620-125">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="5d620-125">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="5d620-126">-Filter</span><span class="sxs-lookup"><span data-stu-id="5d620-126">-Filter</span></span>

<span data-ttu-id="5d620-127">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d620-127">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="5d620-128">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="5d620-128">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="5d620-129">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d620-129">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="5d620-130">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="5d620-130">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="5d620-131">-Force</span><span class="sxs-lookup"><span data-stu-id="5d620-131">-Force</span></span>

<span data-ttu-id="5d620-132">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5d620-132">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="5d620-133">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="5d620-133">Implementation varies from provider to provider.</span></span>

<span data-ttu-id="5d620-134">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d620-134">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="5d620-135">-Include</span><span class="sxs-lookup"><span data-stu-id="5d620-135">-Include</span></span>

<span data-ttu-id="5d620-136">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d620-136">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="5d620-137">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="5d620-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="5d620-138">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="5d620-138">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="5d620-139">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d620-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="5d620-140">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="5d620-140">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="5d620-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="5d620-141">-LiteralPath</span></span>

<span data-ttu-id="5d620-142">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d620-142">Specifies a path to one or more locations.</span></span> <span data-ttu-id="5d620-143">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d620-143">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="5d620-144">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="5d620-144">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="5d620-145">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="5d620-145">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="5d620-146">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="5d620-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="5d620-147">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d620-147">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="5d620-148">-Name</span><span class="sxs-lookup"><span data-stu-id="5d620-148">-Name</span></span>

<span data-ttu-id="5d620-149">コピーするプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d620-149">Specifies the name of the property to be copied.</span></span>

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

### <span data-ttu-id="5d620-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5d620-150">-PassThru</span></span>

<span data-ttu-id="5d620-151">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="5d620-151">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="5d620-152">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="5d620-152">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="5d620-153">-Path</span><span class="sxs-lookup"><span data-stu-id="5d620-153">-Path</span></span>

<span data-ttu-id="5d620-154">文字列配列として、コピーするプロパティへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d620-154">Specifies, as a string array, the path to the property to be copied.</span></span>
<span data-ttu-id="5d620-155">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d620-155">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="5d620-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5d620-156">-Confirm</span></span>

<span data-ttu-id="5d620-157">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d620-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5d620-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5d620-158">-WhatIf</span></span>

<span data-ttu-id="5d620-159">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="5d620-159">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="5d620-160">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="5d620-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5d620-161">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5d620-161">CommonParameters</span></span>

<span data-ttu-id="5d620-162">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="5d620-162">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="5d620-163">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d620-163">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="5d620-164">入力</span><span class="sxs-lookup"><span data-stu-id="5d620-164">INPUTS</span></span>

### <span data-ttu-id="5d620-165">System.String</span><span class="sxs-lookup"><span data-stu-id="5d620-165">System.String</span></span>

<span data-ttu-id="5d620-166">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="5d620-166">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="5d620-167">出力</span><span class="sxs-lookup"><span data-stu-id="5d620-167">OUTPUTS</span></span>

### <span data-ttu-id="5d620-168">なしまたはシステムの管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="5d620-168">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="5d620-169">**Passthru** パラメーターを使用すると、このコマンドレットは、コピーされた項目プロパティを表す **pscustomobject** 生成します。</span><span class="sxs-lookup"><span data-stu-id="5d620-169">When you use the **Passthru** parameter, this cmdlet generates a **PsCustomObject** representing the copied item property.</span></span> <span data-ttu-id="5d620-170">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="5d620-170">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5d620-171">注</span><span class="sxs-lookup"><span data-stu-id="5d620-171">NOTES</span></span>

<span data-ttu-id="5d620-172">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="5d620-172">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="5d620-173">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="5d620-173">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="5d620-174">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d620-174">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="5d620-175">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5d620-175">RELATED LINKS</span></span>

[<span data-ttu-id="5d620-176">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5d620-176">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="5d620-177">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5d620-177">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="5d620-178">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5d620-178">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="5d620-179">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5d620-179">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="5d620-180">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5d620-180">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="5d620-181">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5d620-181">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="5d620-182">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="5d620-182">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="5d620-183">about_Providers</span><span class="sxs-lookup"><span data-stu-id="5d620-183">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

