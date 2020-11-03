---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-item?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Item
ms.openlocfilehash: 9cfbe55c25540d71d3287f6da456891fa48c05d6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212560"
---
# <span data-ttu-id="f35f5-103">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="f35f5-103">Clear-Item</span></span>

## <span data-ttu-id="f35f5-104">概要</span><span class="sxs-lookup"><span data-stu-id="f35f5-104">SYNOPSIS</span></span>
<span data-ttu-id="f35f5-105">項目の内容を消去しますが、項目は削除しません。</span><span class="sxs-lookup"><span data-stu-id="f35f5-105">Clears the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="f35f5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f35f5-106">SYNTAX</span></span>

### <span data-ttu-id="f35f5-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="f35f5-107">Path (Default)</span></span>

```
Clear-Item [-Path] <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f35f5-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f35f5-108">LiteralPath</span></span>

```
Clear-Item -LiteralPath <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f35f5-109">Description</span><span class="sxs-lookup"><span data-stu-id="f35f5-109">DESCRIPTION</span></span>

<span data-ttu-id="f35f5-110">コマンドレットでは、 `Clear-Item` 項目の内容を消去しますが、項目は削除されません。</span><span class="sxs-lookup"><span data-stu-id="f35f5-110">The `Clear-Item` cmdlet clears the content of an item, but it does not delete the item.</span></span>
<span data-ttu-id="f35f5-111">たとえば、 `Clear-Item` コマンドレットで変数の値を削除することはできますが、変数は削除されません。</span><span class="sxs-lookup"><span data-stu-id="f35f5-111">For example, the `Clear-Item` cmdlet can delete the value of a variable, but it does not delete the variable.</span></span> <span data-ttu-id="f35f5-112">クリアされた項目を表すために使用される値は、各 PowerShell プロバイダーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-112">The value that used to represent a cleared item is defined by each PowerShell provider.</span></span>
<span data-ttu-id="f35f5-113">このコマンドレットはに似 `Clear-Content` ていますが、ファイルではなくエイリアスと変数に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="f35f5-113">This cmdlet is similar to `Clear-Content`, but it works on aliases and variables, instead of files.</span></span>

## <span data-ttu-id="f35f5-114">例</span><span class="sxs-lookup"><span data-stu-id="f35f5-114">EXAMPLES</span></span>

### <span data-ttu-id="f35f5-115">例 1: 変数の値をクリアする</span><span class="sxs-lookup"><span data-stu-id="f35f5-115">Example 1: Clear the value of a variable</span></span>

<span data-ttu-id="f35f5-116">このコマンドは、という名前の変数の値をクリア `TestVar1` します。</span><span class="sxs-lookup"><span data-stu-id="f35f5-116">This command clears the value of the variable named `TestVar1`.</span></span>
<span data-ttu-id="f35f5-117">変数はそのままで、有効ですが、その値はに設定され `$null` ます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-117">The variable remains and is valid, but its value is set to `$null`.</span></span>
<span data-ttu-id="f35f5-118">変数名の先頭には、 `Variable:` PowerShell 変数プロバイダーを示すが付きます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-118">The variable name is prefixed with `Variable:` to indicate the PowerShell Variable provider.</span></span>

<span data-ttu-id="f35f5-119">別のコマンドは、同じ結果を得るために、PowerShell ドライブに切り替えてからコマンドを実行することを示して `Variable:` `Clear-Item` います。</span><span class="sxs-lookup"><span data-stu-id="f35f5-119">The alternate commands show that, to get the same result, you can switch to the PowerShell `Variable:` drive and then run the `Clear-Item` command.</span></span>

```powershell
Clear-Item Variable:TestVar1
```

```
Set-Location Variable:
PS Variable:\> Clear-Item TestVar1
```

### <span data-ttu-id="f35f5-120">例 2: すべてのレジストリエントリをクリアする</span><span class="sxs-lookup"><span data-stu-id="f35f5-120">Example 2: Clear all registry entries</span></span>

<span data-ttu-id="f35f5-121">このコマンドを実行すると、"MyKey" サブキーのすべてのレジストリエントリがクリアされますが、目的を確認するように求められた後でのみ削除されます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-121">This command clears all registry entries in the "MyKey" subkey, but only after prompting you to confirm your intent.</span></span>
<span data-ttu-id="f35f5-122">"MyKey" サブキーを削除したり、他のレジストリキーやエントリに影響を与えたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="f35f5-122">It does not delete the "MyKey" subkey or affect any other registry keys or entries.</span></span>
<span data-ttu-id="f35f5-123">**Include** パラメーターと **Exclude** パラメーターを使用してレジストリ キーを指定できますが、これらのパラメーターでレジストリ エントリを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f35f5-123">You can use the **Include** and **Exclude** parameters to identify particular registry keys, but you cannot use them to identify registry entries.</span></span>

- <span data-ttu-id="f35f5-124">特定のレジストリ エントリを削除するには、`Remove-ItemProperty` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f35f5-124">To delete particular registry entries, use the `Remove-ItemProperty` cmdlet.</span></span>
- <span data-ttu-id="f35f5-125">レジストリエントリの値を削除するには、を使用し `Clear-ItemProperty cmdlet` ます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-125">To delete the value of a registry entry, use the `Clear-ItemProperty cmdlet`.</span></span>

```powershell
Clear-Item HKLM:\Software\MyCompany\MyKey -Confirm
```

## <span data-ttu-id="f35f5-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f35f5-126">PARAMETERS</span></span>

### <span data-ttu-id="f35f5-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="f35f5-127">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="f35f5-128">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f35f5-128">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="f35f5-129">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="f35f5-129">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="f35f5-130">-除外</span><span class="sxs-lookup"><span data-stu-id="f35f5-130">-Exclude</span></span>

<span data-ttu-id="f35f5-131">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="f35f5-131">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="f35f5-132">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="f35f5-132">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="f35f5-133">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-133">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="f35f5-134">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-134">Wildcard characters are permitted.</span></span> <span data-ttu-id="f35f5-135">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-135">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="f35f5-136">-Filter</span><span class="sxs-lookup"><span data-stu-id="f35f5-136">-Filter</span></span>

<span data-ttu-id="f35f5-137">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="f35f5-137">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="f35f5-138">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="f35f5-138">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="f35f5-139">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f35f5-139">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="f35f5-140">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="f35f5-140">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="f35f5-141">-Force</span><span class="sxs-lookup"><span data-stu-id="f35f5-141">-Force</span></span>

<span data-ttu-id="f35f5-142">読み取り専用エイリアスなど、変更できない項目がコマンドレットによってクリアされることを示します。</span><span class="sxs-lookup"><span data-stu-id="f35f5-142">Indicates that the cmdlet clears items that cannot otherwise be changed, such as read- only aliases.</span></span>
<span data-ttu-id="f35f5-143">このコマンドレットでは、定数はクリアできません。</span><span class="sxs-lookup"><span data-stu-id="f35f5-143">The cmdlet cannot clear constants.</span></span>
<span data-ttu-id="f35f5-144">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="f35f5-144">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="f35f5-145">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f35f5-145">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="f35f5-146">**Force** パラメーターが使用されている場合でも、コマンドレットでセキュリティ制限をオーバーライドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f35f5-146">The cmdlet cannot override security restrictions, even when the **Force** parameter is used.</span></span>

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

### <span data-ttu-id="f35f5-147">-Include</span><span class="sxs-lookup"><span data-stu-id="f35f5-147">-Include</span></span>

<span data-ttu-id="f35f5-148">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="f35f5-148">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="f35f5-149">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="f35f5-149">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="f35f5-150">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-150">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="f35f5-151">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-151">Wildcard characters are permitted.</span></span> <span data-ttu-id="f35f5-152">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-152">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="f35f5-153">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f35f5-153">-LiteralPath</span></span>

<span data-ttu-id="f35f5-154">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f35f5-154">Specifies a path to one or more locations.</span></span> <span data-ttu-id="f35f5-155">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-155">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="f35f5-156">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="f35f5-156">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="f35f5-157">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-157">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="f35f5-158">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="f35f5-158">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="f35f5-159">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f35f5-159">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="f35f5-160">-Path</span><span class="sxs-lookup"><span data-stu-id="f35f5-160">-Path</span></span>

<span data-ttu-id="f35f5-161">削除する項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f35f5-161">Specifies the path to the items being cleared.</span></span>
<span data-ttu-id="f35f5-162">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-162">Wildcard characters are permitted.</span></span>
<span data-ttu-id="f35f5-163">このパラメーターは必須ですが、パラメーター名の **パス** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="f35f5-163">This parameter is required, but the parameter name **Path** is optional.</span></span>

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

### <span data-ttu-id="f35f5-164">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f35f5-164">-Confirm</span></span>

<span data-ttu-id="f35f5-165">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-165">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f35f5-166">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f35f5-166">-WhatIf</span></span>

<span data-ttu-id="f35f5-167">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="f35f5-167">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f35f5-168">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f35f5-168">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f35f5-169">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f35f5-169">CommonParameters</span></span>

<span data-ttu-id="f35f5-170">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-170">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="f35f5-171">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f35f5-171">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="f35f5-172">入力</span><span class="sxs-lookup"><span data-stu-id="f35f5-172">INPUTS</span></span>

### <span data-ttu-id="f35f5-173">System.String</span><span class="sxs-lookup"><span data-stu-id="f35f5-173">System.String</span></span>

<span data-ttu-id="f35f5-174">パイプを使用してパス文字列をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="f35f5-174">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="f35f5-175">出力</span><span class="sxs-lookup"><span data-stu-id="f35f5-175">OUTPUTS</span></span>

### <span data-ttu-id="f35f5-176">なし</span><span class="sxs-lookup"><span data-stu-id="f35f5-176">None</span></span>

<span data-ttu-id="f35f5-177">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="f35f5-177">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f35f5-178">注</span><span class="sxs-lookup"><span data-stu-id="f35f5-178">NOTES</span></span>

- <span data-ttu-id="f35f5-179">`Clear-Item`コマンドレットは、 **Alias** 、 **Environment** 、 **Function** 、 **Registry** 、 **Variable** プロバイダーなど、いくつかの PowerShell プロバイダーでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f35f5-179">The `Clear-Item` cmdlet is supported only by several PowerShell providers, including the **Alias** , **Environment** , **Function** , **Registry** , and **Variable** providers.</span></span> <span data-ttu-id="f35f5-180">そのため、を使用して、 `Clear-Item` プロバイダーの名前空間内の項目の内容を削除できます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-180">As such, you can use `Clear-Item` to delete the content of items in the provider namespaces.</span></span> <span data-ttu-id="f35f5-181">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="f35f5-181">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="f35f5-182">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f35f5-182">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
- <span data-ttu-id="f35f5-183">`Clear-Item`PowerShell FileSystem プロバイダーはこのコマンドレットをサポートしていないため、を使用してファイルの内容を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="f35f5-183">You cannot use `Clear-Item` to delete the contents of a file, because the PowerShell FileSystem provider does not support this cmdlet.</span></span> <span data-ttu-id="f35f5-184">ファイルをクリアするには、を使用し `Clear-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="f35f5-184">To clear files, use the `Clear-Content`.</span></span>

## <span data-ttu-id="f35f5-185">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f35f5-185">RELATED LINKS</span></span>

[<span data-ttu-id="f35f5-186">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="f35f5-186">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="f35f5-187">Get-Item</span><span class="sxs-lookup"><span data-stu-id="f35f5-187">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="f35f5-188">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="f35f5-188">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="f35f5-189">Move-Item</span><span class="sxs-lookup"><span data-stu-id="f35f5-189">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="f35f5-190">New-Item</span><span class="sxs-lookup"><span data-stu-id="f35f5-190">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="f35f5-191">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="f35f5-191">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="f35f5-192">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="f35f5-192">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="f35f5-193">Set-Item</span><span class="sxs-lookup"><span data-stu-id="f35f5-193">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="f35f5-194">about_Providers</span><span class="sxs-lookup"><span data-stu-id="f35f5-194">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
