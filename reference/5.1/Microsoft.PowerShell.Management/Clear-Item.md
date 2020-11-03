---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Item
ms.openlocfilehash: a0854fbff06ea51c322bdaf46c81f47f76af978b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215547"
---
# <span data-ttu-id="4086e-103">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="4086e-103">Clear-Item</span></span>

## <span data-ttu-id="4086e-104">概要</span><span class="sxs-lookup"><span data-stu-id="4086e-104">SYNOPSIS</span></span>
<span data-ttu-id="4086e-105">項目の内容を消去しますが、項目は削除しません。</span><span class="sxs-lookup"><span data-stu-id="4086e-105">Clears the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="4086e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4086e-106">SYNTAX</span></span>

### <span data-ttu-id="4086e-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="4086e-107">Path (Default)</span></span>

```
Clear-Item [-Path] <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="4086e-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4086e-108">LiteralPath</span></span>

```
Clear-Item -LiteralPath <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="4086e-109">Description</span><span class="sxs-lookup"><span data-stu-id="4086e-109">DESCRIPTION</span></span>

<span data-ttu-id="4086e-110">コマンドレットでは、 `Clear-Item` 項目の内容を消去しますが、項目は削除されません。</span><span class="sxs-lookup"><span data-stu-id="4086e-110">The `Clear-Item` cmdlet clears the content of an item, but it does not delete the item.</span></span>
<span data-ttu-id="4086e-111">たとえば、 `Clear-Item` コマンドレットで変数の値を削除することはできますが、変数は削除されません。</span><span class="sxs-lookup"><span data-stu-id="4086e-111">For example, the `Clear-Item` cmdlet can delete the value of a variable, but it does not delete the variable.</span></span> <span data-ttu-id="4086e-112">クリアされた項目を表すために使用される値は、各 PowerShell プロバイダーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="4086e-112">The value that used to represent a cleared item is defined by each PowerShell provider.</span></span>
<span data-ttu-id="4086e-113">このコマンドレットはに似 `Clear-Content` ていますが、ファイルではなくエイリアスと変数に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="4086e-113">This cmdlet is similar to `Clear-Content`, but it works on aliases and variables, instead of files.</span></span>

## <span data-ttu-id="4086e-114">例</span><span class="sxs-lookup"><span data-stu-id="4086e-114">EXAMPLES</span></span>

### <span data-ttu-id="4086e-115">例 1: 変数の値をクリアする</span><span class="sxs-lookup"><span data-stu-id="4086e-115">Example 1: Clear the value of a variable</span></span>

<span data-ttu-id="4086e-116">このコマンドは、という名前の変数の値をクリア `TestVar1` します。</span><span class="sxs-lookup"><span data-stu-id="4086e-116">This command clears the value of the variable named `TestVar1`.</span></span>
<span data-ttu-id="4086e-117">変数はそのままで、有効ですが、その値はに設定され `$null` ます。</span><span class="sxs-lookup"><span data-stu-id="4086e-117">The variable remains and is valid, but its value is set to `$null`.</span></span>
<span data-ttu-id="4086e-118">変数名の先頭には、 `Variable:` PowerShell 変数プロバイダーを示すが付きます。</span><span class="sxs-lookup"><span data-stu-id="4086e-118">The variable name is prefixed with `Variable:` to indicate the PowerShell Variable provider.</span></span>

<span data-ttu-id="4086e-119">別のコマンドは、同じ結果を得るために、PowerShell ドライブに切り替えてからコマンドを実行することを示して `Variable:` `Clear-Item` います。</span><span class="sxs-lookup"><span data-stu-id="4086e-119">The alternate commands show that, to get the same result, you can switch to the PowerShell `Variable:` drive and then run the `Clear-Item` command.</span></span>

```powershell
Clear-Item Variable:TestVar1
```

```
Set-Location Variable:
PS Variable:\> Clear-Item TestVar1
```

### <span data-ttu-id="4086e-120">例 2: すべてのレジストリエントリをクリアする</span><span class="sxs-lookup"><span data-stu-id="4086e-120">Example 2: Clear all registry entries</span></span>

<span data-ttu-id="4086e-121">このコマンドを実行すると、"MyKey" サブキーのすべてのレジストリエントリがクリアされますが、目的を確認するように求められた後でのみ削除されます。</span><span class="sxs-lookup"><span data-stu-id="4086e-121">This command clears all registry entries in the "MyKey" subkey, but only after prompting you to confirm your intent.</span></span>
<span data-ttu-id="4086e-122">"MyKey" サブキーを削除したり、他のレジストリキーやエントリに影響を与えたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="4086e-122">It does not delete the "MyKey" subkey or affect any other registry keys or entries.</span></span>
<span data-ttu-id="4086e-123">**Include** パラメーターと **Exclude** パラメーターを使用してレジストリ キーを指定できますが、これらのパラメーターでレジストリ エントリを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="4086e-123">You can use the **Include** and **Exclude** parameters to identify particular registry keys, but you cannot use them to identify registry entries.</span></span>

- <span data-ttu-id="4086e-124">特定のレジストリ エントリを削除するには、`Remove-ItemProperty` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4086e-124">To delete particular registry entries, use the `Remove-ItemProperty` cmdlet.</span></span>
- <span data-ttu-id="4086e-125">レジストリエントリの値を削除するには、コマンドレットを使用し `Clear-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="4086e-125">To delete the value of a registry entry, use the `Clear-ItemProperty` cmdlet.</span></span>

```powershell
Clear-Item HKLM:\Software\MyCompany\MyKey -Confirm
```

## <span data-ttu-id="4086e-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4086e-126">PARAMETERS</span></span>

### <span data-ttu-id="4086e-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="4086e-127">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="4086e-128">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4086e-128">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="4086e-129">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="4086e-129">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="4086e-130">-除外</span><span class="sxs-lookup"><span data-stu-id="4086e-130">-Exclude</span></span>

<span data-ttu-id="4086e-131">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="4086e-131">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="4086e-132">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="4086e-132">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="4086e-133">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="4086e-133">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="4086e-134">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4086e-134">Wildcard characters are permitted.</span></span> <span data-ttu-id="4086e-135">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="4086e-135">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="4086e-136">-Filter</span><span class="sxs-lookup"><span data-stu-id="4086e-136">-Filter</span></span>

<span data-ttu-id="4086e-137">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="4086e-137">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="4086e-138">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="4086e-138">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="4086e-139">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4086e-139">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="4086e-140">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="4086e-140">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="4086e-141">-Force</span><span class="sxs-lookup"><span data-stu-id="4086e-141">-Force</span></span>

<span data-ttu-id="4086e-142">読み取り専用エイリアスなど、変更できない項目がコマンドレットによってクリアされることを示します。</span><span class="sxs-lookup"><span data-stu-id="4086e-142">Indicates that the cmdlet clears items that cannot otherwise be changed, such as read- only aliases.</span></span>
<span data-ttu-id="4086e-143">このコマンドレットでは、定数はクリアできません。</span><span class="sxs-lookup"><span data-stu-id="4086e-143">The cmdlet cannot clear constants.</span></span>
<span data-ttu-id="4086e-144">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="4086e-144">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="4086e-145">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4086e-145">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="4086e-146">**Force** パラメーターが使用されている場合でも、コマンドレットでセキュリティ制限をオーバーライドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4086e-146">The cmdlet cannot override security restrictions, even when the **Force** parameter is used.</span></span>

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

### <span data-ttu-id="4086e-147">-Include</span><span class="sxs-lookup"><span data-stu-id="4086e-147">-Include</span></span>

<span data-ttu-id="4086e-148">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="4086e-148">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="4086e-149">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="4086e-149">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="4086e-150">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="4086e-150">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="4086e-151">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4086e-151">Wildcard characters are permitted.</span></span> <span data-ttu-id="4086e-152">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="4086e-152">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="4086e-153">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4086e-153">-LiteralPath</span></span>

<span data-ttu-id="4086e-154">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="4086e-154">Specifies a path to one or more locations.</span></span> <span data-ttu-id="4086e-155">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4086e-155">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="4086e-156">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="4086e-156">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="4086e-157">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="4086e-157">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="4086e-158">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="4086e-158">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="4086e-159">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4086e-159">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="4086e-160">-Path</span><span class="sxs-lookup"><span data-stu-id="4086e-160">-Path</span></span>

<span data-ttu-id="4086e-161">削除する項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="4086e-161">Specifies the path to the items being cleared.</span></span>
<span data-ttu-id="4086e-162">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4086e-162">Wildcard characters are permitted.</span></span>
<span data-ttu-id="4086e-163">このパラメーターは必須ですが、パラメーター名の **パス** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4086e-163">This parameter is required, but the parameter name **Path** is optional.</span></span>

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

### <span data-ttu-id="4086e-164">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="4086e-164">-UseTransaction</span></span>

<span data-ttu-id="4086e-165">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4086e-165">Includes the command in the active transaction.</span></span>
<span data-ttu-id="4086e-166">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="4086e-166">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="4086e-167">詳細については、「about_Transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4086e-167">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="4086e-168">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4086e-168">-Confirm</span></span>

<span data-ttu-id="4086e-169">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4086e-169">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4086e-170">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4086e-170">-WhatIf</span></span>

<span data-ttu-id="4086e-171">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="4086e-171">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4086e-172">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="4086e-172">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4086e-173">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4086e-173">CommonParameters</span></span>

<span data-ttu-id="4086e-174">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="4086e-174">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="4086e-175">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4086e-175">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="4086e-176">入力</span><span class="sxs-lookup"><span data-stu-id="4086e-176">INPUTS</span></span>

### <span data-ttu-id="4086e-177">System.String</span><span class="sxs-lookup"><span data-stu-id="4086e-177">System.String</span></span>

<span data-ttu-id="4086e-178">パイプを使用してパス文字列をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="4086e-178">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="4086e-179">出力</span><span class="sxs-lookup"><span data-stu-id="4086e-179">OUTPUTS</span></span>

### <span data-ttu-id="4086e-180">なし</span><span class="sxs-lookup"><span data-stu-id="4086e-180">None</span></span>

<span data-ttu-id="4086e-181">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="4086e-181">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="4086e-182">注</span><span class="sxs-lookup"><span data-stu-id="4086e-182">NOTES</span></span>

- <span data-ttu-id="4086e-183">`Clear-Item`コマンドレットは、 **Alias** 、 **Environment** 、 **Function** 、 **Registry** 、 **Variable** プロバイダーなど、いくつかの PowerShell プロバイダーでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4086e-183">The `Clear-Item` cmdlet is supported only by several PowerShell providers, including the **Alias** , **Environment** , **Function** , **Registry** , and **Variable** providers.</span></span> <span data-ttu-id="4086e-184">そのため、を使用して、 `Clear-Item` プロバイダーの名前空間内の項目の内容を削除できます。</span><span class="sxs-lookup"><span data-stu-id="4086e-184">As such, you can use `Clear-Item` to delete the content of items in the provider namespaces.</span></span> <span data-ttu-id="4086e-185">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="4086e-185">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="4086e-186">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4086e-186">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
- <span data-ttu-id="4086e-187">`Clear-Item`PowerShell FileSystem プロバイダーはこのコマンドレットをサポートしていないため、を使用してファイルの内容を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="4086e-187">You cannot use `Clear-Item` to delete the contents of a file, because the PowerShell FileSystem provider does not support this cmdlet.</span></span> <span data-ttu-id="4086e-188">ファイルをクリアするには、を使用し `Clear-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="4086e-188">To clear files, use the `Clear-Content`.</span></span>

## <span data-ttu-id="4086e-189">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4086e-189">RELATED LINKS</span></span>

[<span data-ttu-id="4086e-190">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="4086e-190">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="4086e-191">Get-Item</span><span class="sxs-lookup"><span data-stu-id="4086e-191">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="4086e-192">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="4086e-192">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="4086e-193">Move-Item</span><span class="sxs-lookup"><span data-stu-id="4086e-193">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="4086e-194">New-Item</span><span class="sxs-lookup"><span data-stu-id="4086e-194">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="4086e-195">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="4086e-195">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="4086e-196">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="4086e-196">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="4086e-197">Set-Item</span><span class="sxs-lookup"><span data-stu-id="4086e-197">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="4086e-198">about_Providers</span><span class="sxs-lookup"><span data-stu-id="4086e-198">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)