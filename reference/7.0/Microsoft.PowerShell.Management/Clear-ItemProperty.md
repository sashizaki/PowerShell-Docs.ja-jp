---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-itemproperty?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-ItemProperty
ms.openlocfilehash: f112b2bda543b50e0077df6778fc4eacfb3add9c
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211120"
---
# <span data-ttu-id="229a3-103">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="229a3-103">Clear-ItemProperty</span></span>

## <span data-ttu-id="229a3-104">概要</span><span class="sxs-lookup"><span data-stu-id="229a3-104">SYNOPSIS</span></span>
<span data-ttu-id="229a3-105">プロパティの値をクリアしますが、プロパティは削除しません。</span><span class="sxs-lookup"><span data-stu-id="229a3-105">Clears the value of a property but does not delete the property.</span></span>

## <span data-ttu-id="229a3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="229a3-106">SYNTAX</span></span>

### <span data-ttu-id="229a3-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="229a3-107">Path (Default)</span></span>

```
Clear-ItemProperty [-Path] <String[]> [-Name] <String> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="229a3-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="229a3-108">LiteralPath</span></span>

```
Clear-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="229a3-109">Description</span><span class="sxs-lookup"><span data-stu-id="229a3-109">DESCRIPTION</span></span>

<span data-ttu-id="229a3-110">`Clear-ItemProperty`コマンドレットはプロパティの値をクリアしますが、プロパティは削除しません。</span><span class="sxs-lookup"><span data-stu-id="229a3-110">The `Clear-ItemProperty` cmdlet clears the value of a property, but it does not delete the property.</span></span>
<span data-ttu-id="229a3-111">このコマンドレットを使用して、レジストリ値からデータを削除できます。</span><span class="sxs-lookup"><span data-stu-id="229a3-111">You can use this cmdlet to delete the data from a registry value.</span></span>

## <span data-ttu-id="229a3-112">例</span><span class="sxs-lookup"><span data-stu-id="229a3-112">EXAMPLES</span></span>

### <span data-ttu-id="229a3-113">例 1: レジストリキーの値をクリアする</span><span class="sxs-lookup"><span data-stu-id="229a3-113">Example 1: Clear the value of registry key</span></span>

<span data-ttu-id="229a3-114">このコマンドを実行すると、の "MyApp" サブキーの "Options" レジストリ値のデータが消去され `HKEY_LOCAL_MACHINE\Software\MyCompany` ます。</span><span class="sxs-lookup"><span data-stu-id="229a3-114">This command clears the data in the "Options" registry value in the "MyApp" subkey of `HKEY_LOCAL_MACHINE\Software\MyCompany`.</span></span>

```powershell
Clear-ItemProperty -Path "HKLM:\Software\MyCompany\MyApp" -Name "Options"
```

## <span data-ttu-id="229a3-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="229a3-115">PARAMETERS</span></span>

### <span data-ttu-id="229a3-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="229a3-116">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="229a3-117">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="229a3-117">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="229a3-118">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="229a3-118">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="229a3-119">-除外</span><span class="sxs-lookup"><span data-stu-id="229a3-119">-Exclude</span></span>

<span data-ttu-id="229a3-120">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="229a3-120">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="229a3-121">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="229a3-121">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="229a3-122">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="229a3-122">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="229a3-123">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="229a3-123">Wildcard characters are permitted.</span></span> <span data-ttu-id="229a3-124">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="229a3-124">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="229a3-125">-Filter</span><span class="sxs-lookup"><span data-stu-id="229a3-125">-Filter</span></span>

<span data-ttu-id="229a3-126">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="229a3-126">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="229a3-127">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="229a3-127">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="229a3-128">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="229a3-128">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="229a3-129">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="229a3-129">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="229a3-130">-Force</span><span class="sxs-lookup"><span data-stu-id="229a3-130">-Force</span></span>

<span data-ttu-id="229a3-131">このコマンドレットは、ユーザーがアクセスできない項目からプロパティを削除することを示します。</span><span class="sxs-lookup"><span data-stu-id="229a3-131">Indicates that this cmdlet deletes properties from items that cannot otherwise be accessed by the user.</span></span> <span data-ttu-id="229a3-132">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="229a3-132">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="229a3-133">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="229a3-133">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="229a3-134">-Include</span><span class="sxs-lookup"><span data-stu-id="229a3-134">-Include</span></span>

<span data-ttu-id="229a3-135">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="229a3-135">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="229a3-136">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="229a3-136">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="229a3-137">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="229a3-137">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="229a3-138">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="229a3-138">Wildcard characters are permitted.</span></span> <span data-ttu-id="229a3-139">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="229a3-139">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="229a3-140">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="229a3-140">-LiteralPath</span></span>

<span data-ttu-id="229a3-141">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="229a3-141">Specifies a path to one or more locations.</span></span> <span data-ttu-id="229a3-142">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="229a3-142">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="229a3-143">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="229a3-143">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="229a3-144">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="229a3-144">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="229a3-145">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="229a3-145">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="229a3-146">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="229a3-146">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="229a3-147">-Name</span><span class="sxs-lookup"><span data-stu-id="229a3-147">-Name</span></span>

<span data-ttu-id="229a3-148">レジストリ値の名前など、クリアするプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="229a3-148">Specifies the name of the property to be cleared, such as the name of a registry value.</span></span>
<span data-ttu-id="229a3-149">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="229a3-149">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="229a3-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="229a3-150">-PassThru</span></span>

<span data-ttu-id="229a3-151">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="229a3-151">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="229a3-152">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="229a3-152">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="229a3-153">-Path</span><span class="sxs-lookup"><span data-stu-id="229a3-153">-Path</span></span>

<span data-ttu-id="229a3-154">クリアするプロパティのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="229a3-154">Specifies the path to the property being cleared.</span></span>
<span data-ttu-id="229a3-155">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="229a3-155">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="229a3-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="229a3-156">-Confirm</span></span>

<span data-ttu-id="229a3-157">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="229a3-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="229a3-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="229a3-158">-WhatIf</span></span>

<span data-ttu-id="229a3-159">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="229a3-159">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="229a3-160">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="229a3-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="229a3-161">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="229a3-161">CommonParameters</span></span>

<span data-ttu-id="229a3-162">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="229a3-162">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="229a3-163">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="229a3-163">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="229a3-164">入力</span><span class="sxs-lookup"><span data-stu-id="229a3-164">INPUTS</span></span>

### <span data-ttu-id="229a3-165">System.String</span><span class="sxs-lookup"><span data-stu-id="229a3-165">System.String</span></span>

<span data-ttu-id="229a3-166">パイプを使用してパス文字列をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="229a3-166">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="229a3-167">出力</span><span class="sxs-lookup"><span data-stu-id="229a3-167">OUTPUTS</span></span>

### <span data-ttu-id="229a3-168">なしまたはシステムの管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="229a3-168">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="229a3-169">**PassThru** パラメーターを使用すると、消去された `Clear-ItemProperty` 項目プロパティを表す **pscustomobject** オブジェクトがによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="229a3-169">When you use the **PassThru** parameter, `Clear-ItemProperty` generates a **PSCustomObject** object that represents the cleared item property.</span></span> <span data-ttu-id="229a3-170">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="229a3-170">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="229a3-171">注</span><span class="sxs-lookup"><span data-stu-id="229a3-171">NOTES</span></span>

- <span data-ttu-id="229a3-172">を使用すると、 `Clear-ItemProperty` レジストリ値の値を削除せずにデータを削除できます。</span><span class="sxs-lookup"><span data-stu-id="229a3-172">You can use `Clear-ItemProperty` to delete the data in registry values without deleting the value.</span></span>
  <span data-ttu-id="229a3-173">値のデータ型がバイナリ値または DWORD の場合、データをクリアすると値がゼロに設定されます。</span><span class="sxs-lookup"><span data-stu-id="229a3-173">If the data type of the value is Binary or DWORD, clearing the data sets the value to zero.</span></span>
  <span data-ttu-id="229a3-174">それ以外の型の場合は、値が空になります。</span><span class="sxs-lookup"><span data-stu-id="229a3-174">Otherwise, the value is empty.</span></span>
- <span data-ttu-id="229a3-175">`Clear-ItemProperty`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="229a3-175">The `Clear-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="229a3-176">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="229a3-176">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="229a3-177">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="229a3-177">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="229a3-178">関連リンク</span><span class="sxs-lookup"><span data-stu-id="229a3-178">RELATED LINKS</span></span>

[<span data-ttu-id="229a3-179">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="229a3-179">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="229a3-180">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="229a3-180">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="229a3-181">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="229a3-181">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="229a3-182">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="229a3-182">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="229a3-183">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="229a3-183">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="229a3-184">about_Providers</span><span class="sxs-lookup"><span data-stu-id="229a3-184">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
