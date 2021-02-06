---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ItemProperty
ms.openlocfilehash: 92a14e4bd165efd4721e3802cade827744c9c056
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600114"
---
# <span data-ttu-id="a9264-102">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a9264-102">Move-ItemProperty</span></span>

## <span data-ttu-id="a9264-103">構文</span><span class="sxs-lookup"><span data-stu-id="a9264-103">Synopsis</span></span>
<span data-ttu-id="a9264-104">プロパティをある場所から別の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="a9264-104">Moves a property from one location to another.</span></span>

## <span data-ttu-id="a9264-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a9264-105">SYNTAX</span></span>

### <span data-ttu-id="a9264-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="a9264-106">Path (Default)</span></span>

```
Move-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a9264-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a9264-107">LiteralPath</span></span>

```
Move-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a9264-108">説明</span><span class="sxs-lookup"><span data-stu-id="a9264-108">Description</span></span>

<span data-ttu-id="a9264-109">コマンドレットは、項目 `Move-ItemProperty` のプロパティをある項目から別の項目に移動します。</span><span class="sxs-lookup"><span data-stu-id="a9264-109">The `Move-ItemProperty` cmdlet moves a property of an item from one item to another item.</span></span>
<span data-ttu-id="a9264-110">たとえば、あるレジストリキーから別のレジストリキーにレジストリエントリを移動できます。</span><span class="sxs-lookup"><span data-stu-id="a9264-110">For instance, it can move a registry entry from one registry key to another registry key.</span></span>
<span data-ttu-id="a9264-111">項目のプロパティを移動すると、そのプロパティが新しい場所に追加され、元の場所から削除されます。</span><span class="sxs-lookup"><span data-stu-id="a9264-111">When you move an item property, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="a9264-112">例</span><span class="sxs-lookup"><span data-stu-id="a9264-112">EXAMPLES</span></span>

### <span data-ttu-id="a9264-113">例 1: レジストリ値とそのデータを別のキーに移動する</span><span class="sxs-lookup"><span data-stu-id="a9264-113">Example 1: Move a registry value and its data to another key</span></span>

<span data-ttu-id="a9264-114">このコマンドは、Version レジストリ値とそのデータを、"MyApp" サブキーからレジストリキーの NewApp サブキーに移動し `HKLM\Software\MyCompany` ます。</span><span class="sxs-lookup"><span data-stu-id="a9264-114">This command moves the Version registry value, and its data, from the "MyApp" subkey to the NewApp subkey of the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Move-ItemProperty "HKLM:\Software\MyCompany\MyApp" -Name "Version" -Destination "HKLM:\Software\MyCompany\NewApp"
```

## <span data-ttu-id="a9264-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a9264-115">PARAMETERS</span></span>

### <span data-ttu-id="a9264-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="a9264-116">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="a9264-117">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a9264-117">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="a9264-118">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="a9264-118">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="a9264-119">-Destination</span><span class="sxs-lookup"><span data-stu-id="a9264-119">-Destination</span></span>

<span data-ttu-id="a9264-120">移動先のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9264-120">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="a9264-121">-除外</span><span class="sxs-lookup"><span data-stu-id="a9264-121">-Exclude</span></span>

<span data-ttu-id="a9264-122">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="a9264-122">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="a9264-123">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="a9264-123">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a9264-124">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="a9264-124">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="a9264-125">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9264-125">Wildcard characters are permitted.</span></span> <span data-ttu-id="a9264-126">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="a9264-126">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="a9264-127">-Filter</span><span class="sxs-lookup"><span data-stu-id="a9264-127">-Filter</span></span>

<span data-ttu-id="a9264-128">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9264-128">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="a9264-129">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="a9264-129">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="a9264-130">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9264-130">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="a9264-131">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="a9264-131">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="a9264-132">-Force</span><span class="sxs-lookup"><span data-stu-id="a9264-132">-Force</span></span>

<span data-ttu-id="a9264-133">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a9264-133">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="a9264-134">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="a9264-134">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="a9264-135">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9264-135">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="a9264-136">-Include</span><span class="sxs-lookup"><span data-stu-id="a9264-136">-Include</span></span>

<span data-ttu-id="a9264-137">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9264-137">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="a9264-138">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="a9264-138">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a9264-139">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="a9264-139">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="a9264-140">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9264-140">Wildcard characters are permitted.</span></span> <span data-ttu-id="a9264-141">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="a9264-141">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="a9264-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a9264-142">-LiteralPath</span></span>

<span data-ttu-id="a9264-143">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9264-143">Specifies a path to one or more locations.</span></span> <span data-ttu-id="a9264-144">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a9264-144">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="a9264-145">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="a9264-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="a9264-146">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="a9264-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="a9264-147">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="a9264-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="a9264-148">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9264-148">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="a9264-149">-Name</span><span class="sxs-lookup"><span data-stu-id="a9264-149">-Name</span></span>

<span data-ttu-id="a9264-150">移動対象のプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9264-150">Specifies the name of the property to be moved.</span></span>

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

### <span data-ttu-id="a9264-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a9264-151">-PassThru</span></span>

<span data-ttu-id="a9264-152">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a9264-152">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="a9264-153">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="a9264-153">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="a9264-154">-Path</span><span class="sxs-lookup"><span data-stu-id="a9264-154">-Path</span></span>

<span data-ttu-id="a9264-155">プロパティの現在の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9264-155">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="a9264-156">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9264-156">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a9264-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a9264-157">-Confirm</span></span>

<span data-ttu-id="a9264-158">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9264-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a9264-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a9264-159">-WhatIf</span></span>

<span data-ttu-id="a9264-160">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="a9264-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a9264-161">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a9264-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a9264-162">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a9264-162">CommonParameters</span></span>

<span data-ttu-id="a9264-163">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="a9264-163">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="a9264-164">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9264-164">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a9264-165">入力</span><span class="sxs-lookup"><span data-stu-id="a9264-165">INPUTS</span></span>

### <span data-ttu-id="a9264-166">System.String</span><span class="sxs-lookup"><span data-stu-id="a9264-166">System.String</span></span>

<span data-ttu-id="a9264-167">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="a9264-167">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="a9264-168">出力</span><span class="sxs-lookup"><span data-stu-id="a9264-168">OUTPUTS</span></span>

### <span data-ttu-id="a9264-169">なしまたはシステムの管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="a9264-169">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="a9264-170">**PassThru** パラメーターを使用すると、このコマンドレットは移動した項目プロパティを表す **pscustomobject** 生成します。</span><span class="sxs-lookup"><span data-stu-id="a9264-170">When you use the **PassThru** parameter, this cmdlet generates a **PSCustomObject** representing the moved item property.</span></span> <span data-ttu-id="a9264-171">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="a9264-171">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a9264-172">注</span><span class="sxs-lookup"><span data-stu-id="a9264-172">NOTES</span></span>

<span data-ttu-id="a9264-173">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="a9264-173">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="a9264-174">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="a9264-174">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="a9264-175">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9264-175">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="a9264-176">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a9264-176">RELATED LINKS</span></span>

[<span data-ttu-id="a9264-177">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a9264-177">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="a9264-178">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a9264-178">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="a9264-179">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a9264-179">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="a9264-180">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a9264-180">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="a9264-181">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a9264-181">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="a9264-182">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a9264-182">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="a9264-183">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a9264-183">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="a9264-184">about_Providers</span><span class="sxs-lookup"><span data-stu-id="a9264-184">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

