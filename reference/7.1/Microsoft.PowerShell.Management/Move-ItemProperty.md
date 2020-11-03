---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-itemproperty?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ItemProperty
ms.openlocfilehash: e3c1d1641c6f4b30b17c9f0f6703cd063663f25b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211600"
---
# <span data-ttu-id="3cb82-103">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3cb82-103">Move-ItemProperty</span></span>

## <span data-ttu-id="3cb82-104">構文</span><span class="sxs-lookup"><span data-stu-id="3cb82-104">Synopsis</span></span>
<span data-ttu-id="3cb82-105">プロパティをある場所から別の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-105">Moves a property from one location to another.</span></span>

## <span data-ttu-id="3cb82-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3cb82-106">SYNTAX</span></span>

### <span data-ttu-id="3cb82-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="3cb82-107">Path (Default)</span></span>

```
Move-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3cb82-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3cb82-108">LiteralPath</span></span>

```
Move-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3cb82-109">説明</span><span class="sxs-lookup"><span data-stu-id="3cb82-109">Description</span></span>

<span data-ttu-id="3cb82-110">コマンドレットは、項目 `Move-ItemProperty` のプロパティをある項目から別の項目に移動します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-110">The `Move-ItemProperty` cmdlet moves a property of an item from one item to another item.</span></span>
<span data-ttu-id="3cb82-111">たとえば、あるレジストリキーから別のレジストリキーにレジストリエントリを移動できます。</span><span class="sxs-lookup"><span data-stu-id="3cb82-111">For instance, it can move a registry entry from one registry key to another registry key.</span></span>
<span data-ttu-id="3cb82-112">項目のプロパティを移動すると、そのプロパティが新しい場所に追加され、元の場所から削除されます。</span><span class="sxs-lookup"><span data-stu-id="3cb82-112">When you move an item property, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="3cb82-113">例</span><span class="sxs-lookup"><span data-stu-id="3cb82-113">EXAMPLES</span></span>

### <span data-ttu-id="3cb82-114">例 1: レジストリ値とそのデータを別のキーに移動する</span><span class="sxs-lookup"><span data-stu-id="3cb82-114">Example 1: Move a registry value and its data to another key</span></span>

<span data-ttu-id="3cb82-115">このコマンドは、Version レジストリ値とそのデータを、"MyApp" サブキーからレジストリキーの NewApp サブキーに移動し `HKLM\Software\MyCompany` ます。</span><span class="sxs-lookup"><span data-stu-id="3cb82-115">This command moves the Version registry value, and its data, from the "MyApp" subkey to the NewApp subkey of the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Move-ItemProperty "HKLM:\Software\MyCompany\MyApp" -Name "Version" -Destination "HKLM:\Software\MyCompany\NewApp"
```

## <span data-ttu-id="3cb82-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3cb82-116">PARAMETERS</span></span>

### <span data-ttu-id="3cb82-117">-Credential</span><span class="sxs-lookup"><span data-stu-id="3cb82-117">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="3cb82-118">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3cb82-118">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="3cb82-119">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-119">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="3cb82-120">-Destination</span><span class="sxs-lookup"><span data-stu-id="3cb82-120">-Destination</span></span>

<span data-ttu-id="3cb82-121">移動先のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-121">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="3cb82-122">-除外</span><span class="sxs-lookup"><span data-stu-id="3cb82-122">-Exclude</span></span>

<span data-ttu-id="3cb82-123">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-123">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="3cb82-124">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-124">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="3cb82-125">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="3cb82-125">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="3cb82-126">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cb82-126">Wildcard characters are permitted.</span></span> <span data-ttu-id="3cb82-127">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="3cb82-127">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="3cb82-128">-Filter</span><span class="sxs-lookup"><span data-stu-id="3cb82-128">-Filter</span></span>

<span data-ttu-id="3cb82-129">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-129">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="3cb82-130">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="3cb82-130">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="3cb82-131">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cb82-131">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="3cb82-132">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="3cb82-132">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="3cb82-133">-Force</span><span class="sxs-lookup"><span data-stu-id="3cb82-133">-Force</span></span>

<span data-ttu-id="3cb82-134">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-134">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="3cb82-135">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="3cb82-135">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="3cb82-136">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cb82-136">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="3cb82-137">-Include</span><span class="sxs-lookup"><span data-stu-id="3cb82-137">-Include</span></span>

<span data-ttu-id="3cb82-138">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-138">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="3cb82-139">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-139">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="3cb82-140">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="3cb82-140">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="3cb82-141">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cb82-141">Wildcard characters are permitted.</span></span> <span data-ttu-id="3cb82-142">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="3cb82-142">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="3cb82-143">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3cb82-143">-LiteralPath</span></span>

<span data-ttu-id="3cb82-144">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-144">Specifies a path to one or more locations.</span></span> <span data-ttu-id="3cb82-145">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3cb82-145">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="3cb82-146">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="3cb82-146">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="3cb82-147">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="3cb82-147">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="3cb82-148">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="3cb82-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="3cb82-149">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cb82-149">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="3cb82-150">-Name</span><span class="sxs-lookup"><span data-stu-id="3cb82-150">-Name</span></span>

<span data-ttu-id="3cb82-151">移動対象のプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-151">Specifies the name of the property to be moved.</span></span>

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

### <span data-ttu-id="3cb82-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="3cb82-152">-PassThru</span></span>

<span data-ttu-id="3cb82-153">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-153">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="3cb82-154">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="3cb82-154">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="3cb82-155">-Path</span><span class="sxs-lookup"><span data-stu-id="3cb82-155">-Path</span></span>

<span data-ttu-id="3cb82-156">プロパティの現在の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-156">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="3cb82-157">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cb82-157">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="3cb82-158">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3cb82-158">-Confirm</span></span>

<span data-ttu-id="3cb82-159">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3cb82-159">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3cb82-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3cb82-160">-WhatIf</span></span>

<span data-ttu-id="3cb82-161">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-161">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="3cb82-162">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="3cb82-162">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3cb82-163">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="3cb82-163">CommonParameters</span></span>

<span data-ttu-id="3cb82-164">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="3cb82-164">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="3cb82-165">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cb82-165">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="3cb82-166">入力</span><span class="sxs-lookup"><span data-stu-id="3cb82-166">INPUTS</span></span>

### <span data-ttu-id="3cb82-167">System.String</span><span class="sxs-lookup"><span data-stu-id="3cb82-167">System.String</span></span>

<span data-ttu-id="3cb82-168">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="3cb82-168">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="3cb82-169">出力</span><span class="sxs-lookup"><span data-stu-id="3cb82-169">OUTPUTS</span></span>

### <span data-ttu-id="3cb82-170">なしまたはシステムの管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="3cb82-170">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="3cb82-171">**PassThru** パラメーターを使用すると、このコマンドレットは移動した項目プロパティを表す **pscustomobject** 生成します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-171">When you use the **PassThru** parameter, this cmdlet generates a **PSCustomObject** representing the moved item property.</span></span> <span data-ttu-id="3cb82-172">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="3cb82-172">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3cb82-173">注</span><span class="sxs-lookup"><span data-stu-id="3cb82-173">NOTES</span></span>

<span data-ttu-id="3cb82-174">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="3cb82-174">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="3cb82-175">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="3cb82-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="3cb82-176">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cb82-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="3cb82-177">関連リンク</span><span class="sxs-lookup"><span data-stu-id="3cb82-177">RELATED LINKS</span></span>

[<span data-ttu-id="3cb82-178">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3cb82-178">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="3cb82-179">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3cb82-179">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="3cb82-180">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3cb82-180">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="3cb82-181">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3cb82-181">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="3cb82-182">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3cb82-182">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="3cb82-183">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3cb82-183">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="3cb82-184">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3cb82-184">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="3cb82-185">about_Providers</span><span class="sxs-lookup"><span data-stu-id="3cb82-185">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

