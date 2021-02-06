---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Item
ms.openlocfilehash: fb3f95f51578f9dc02d9f68b3c0be5a6531aca17
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602594"
---
# <span data-ttu-id="1afdf-102">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="1afdf-102">Clear-Item</span></span>

## <span data-ttu-id="1afdf-103">概要</span><span class="sxs-lookup"><span data-stu-id="1afdf-103">SYNOPSIS</span></span>
<span data-ttu-id="1afdf-104">項目の内容を消去しますが、項目は削除しません。</span><span class="sxs-lookup"><span data-stu-id="1afdf-104">Clears the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="1afdf-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1afdf-105">SYNTAX</span></span>

### <span data-ttu-id="1afdf-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="1afdf-106">Path (Default)</span></span>

```
Clear-Item [-Path] <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1afdf-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1afdf-107">LiteralPath</span></span>

```
Clear-Item -LiteralPath <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1afdf-108">Description</span><span class="sxs-lookup"><span data-stu-id="1afdf-108">DESCRIPTION</span></span>

<span data-ttu-id="1afdf-109">コマンドレットでは、 `Clear-Item` 項目の内容を消去しますが、項目は削除されません。</span><span class="sxs-lookup"><span data-stu-id="1afdf-109">The `Clear-Item` cmdlet clears the content of an item, but it does not delete the item.</span></span>
<span data-ttu-id="1afdf-110">たとえば、 `Clear-Item` コマンドレットで変数の値を削除することはできますが、変数は削除されません。</span><span class="sxs-lookup"><span data-stu-id="1afdf-110">For example, the `Clear-Item` cmdlet can delete the value of a variable, but it does not delete the variable.</span></span> <span data-ttu-id="1afdf-111">クリアされた項目を表すために使用される値は、各 PowerShell プロバイダーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-111">The value that used to represent a cleared item is defined by each PowerShell provider.</span></span>
<span data-ttu-id="1afdf-112">このコマンドレットはに似 `Clear-Content` ていますが、ファイルではなくエイリアスと変数に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="1afdf-112">This cmdlet is similar to `Clear-Content`, but it works on aliases and variables, instead of files.</span></span>

## <span data-ttu-id="1afdf-113">例</span><span class="sxs-lookup"><span data-stu-id="1afdf-113">EXAMPLES</span></span>

### <span data-ttu-id="1afdf-114">例 1: 変数の値をクリアする</span><span class="sxs-lookup"><span data-stu-id="1afdf-114">Example 1: Clear the value of a variable</span></span>

<span data-ttu-id="1afdf-115">このコマンドは、という名前の変数の値をクリア `TestVar1` します。</span><span class="sxs-lookup"><span data-stu-id="1afdf-115">This command clears the value of the variable named `TestVar1`.</span></span>
<span data-ttu-id="1afdf-116">変数はそのままで、有効ですが、その値はに設定され `$null` ます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-116">The variable remains and is valid, but its value is set to `$null`.</span></span>
<span data-ttu-id="1afdf-117">変数名の先頭には、 `Variable:` PowerShell 変数プロバイダーを示すが付きます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-117">The variable name is prefixed with `Variable:` to indicate the PowerShell Variable provider.</span></span>

<span data-ttu-id="1afdf-118">別のコマンドは、同じ結果を得るために、PowerShell ドライブに切り替えてからコマンドを実行することを示して `Variable:` `Clear-Item` います。</span><span class="sxs-lookup"><span data-stu-id="1afdf-118">The alternate commands show that, to get the same result, you can switch to the PowerShell `Variable:` drive and then run the `Clear-Item` command.</span></span>

```powershell
Clear-Item Variable:TestVar1
```

```
Set-Location Variable:
PS Variable:\> Clear-Item TestVar1
```

### <span data-ttu-id="1afdf-119">例 2: すべてのレジストリエントリをクリアする</span><span class="sxs-lookup"><span data-stu-id="1afdf-119">Example 2: Clear all registry entries</span></span>

<span data-ttu-id="1afdf-120">このコマンドを実行すると、"MyKey" サブキーのすべてのレジストリエントリがクリアされますが、目的を確認するように求められた後でのみ削除されます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-120">This command clears all registry entries in the "MyKey" subkey, but only after prompting you to confirm your intent.</span></span>
<span data-ttu-id="1afdf-121">"MyKey" サブキーを削除したり、他のレジストリキーやエントリに影響を与えたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="1afdf-121">It does not delete the "MyKey" subkey or affect any other registry keys or entries.</span></span>
<span data-ttu-id="1afdf-122">**Include** パラメーターと **Exclude** パラメーターを使用してレジストリ キーを指定できますが、これらのパラメーターでレジストリ エントリを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="1afdf-122">You can use the **Include** and **Exclude** parameters to identify particular registry keys, but you cannot use them to identify registry entries.</span></span>

- <span data-ttu-id="1afdf-123">特定のレジストリ エントリを削除するには、`Remove-ItemProperty` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1afdf-123">To delete particular registry entries, use the `Remove-ItemProperty` cmdlet.</span></span>
- <span data-ttu-id="1afdf-124">レジストリエントリの値を削除するには、を使用し `Clear-ItemProperty cmdlet` ます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-124">To delete the value of a registry entry, use the `Clear-ItemProperty cmdlet`.</span></span>

```powershell
Clear-Item HKLM:\Software\MyCompany\MyKey -Confirm
```

## <span data-ttu-id="1afdf-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1afdf-125">PARAMETERS</span></span>

### <span data-ttu-id="1afdf-126">-Credential</span><span class="sxs-lookup"><span data-stu-id="1afdf-126">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="1afdf-127">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1afdf-127">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="1afdf-128">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="1afdf-128">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="1afdf-129">-除外</span><span class="sxs-lookup"><span data-stu-id="1afdf-129">-Exclude</span></span>

<span data-ttu-id="1afdf-130">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="1afdf-130">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="1afdf-131">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="1afdf-131">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="1afdf-132">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-132">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="1afdf-133">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-133">Wildcard characters are permitted.</span></span> <span data-ttu-id="1afdf-134">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-134">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="1afdf-135">-Filter</span><span class="sxs-lookup"><span data-stu-id="1afdf-135">-Filter</span></span>

<span data-ttu-id="1afdf-136">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="1afdf-136">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="1afdf-137">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="1afdf-137">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="1afdf-138">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1afdf-138">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="1afdf-139">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="1afdf-139">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="1afdf-140">-Force</span><span class="sxs-lookup"><span data-stu-id="1afdf-140">-Force</span></span>

<span data-ttu-id="1afdf-141">読み取り専用エイリアスなど、変更できない項目がコマンドレットによってクリアされることを示します。</span><span class="sxs-lookup"><span data-stu-id="1afdf-141">Indicates that the cmdlet clears items that cannot otherwise be changed, such as read- only aliases.</span></span>
<span data-ttu-id="1afdf-142">このコマンドレットでは、定数はクリアできません。</span><span class="sxs-lookup"><span data-stu-id="1afdf-142">The cmdlet cannot clear constants.</span></span>
<span data-ttu-id="1afdf-143">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="1afdf-143">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="1afdf-144">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1afdf-144">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="1afdf-145">**Force** パラメーターが使用されている場合でも、コマンドレットでセキュリティ制限をオーバーライドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1afdf-145">The cmdlet cannot override security restrictions, even when the **Force** parameter is used.</span></span>

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

### <span data-ttu-id="1afdf-146">-Include</span><span class="sxs-lookup"><span data-stu-id="1afdf-146">-Include</span></span>

<span data-ttu-id="1afdf-147">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="1afdf-147">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="1afdf-148">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="1afdf-148">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="1afdf-149">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-149">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="1afdf-150">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-150">Wildcard characters are permitted.</span></span> <span data-ttu-id="1afdf-151">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-151">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="1afdf-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1afdf-152">-LiteralPath</span></span>

<span data-ttu-id="1afdf-153">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1afdf-153">Specifies a path to one or more locations.</span></span> <span data-ttu-id="1afdf-154">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-154">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="1afdf-155">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="1afdf-155">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="1afdf-156">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-156">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="1afdf-157">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="1afdf-157">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="1afdf-158">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1afdf-158">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="1afdf-159">-Path</span><span class="sxs-lookup"><span data-stu-id="1afdf-159">-Path</span></span>

<span data-ttu-id="1afdf-160">削除する項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1afdf-160">Specifies the path to the items being cleared.</span></span>
<span data-ttu-id="1afdf-161">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-161">Wildcard characters are permitted.</span></span>
<span data-ttu-id="1afdf-162">このパラメーターは必須ですが、パラメーター名の **パス** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="1afdf-162">This parameter is required, but the parameter name **Path** is optional.</span></span>

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

### <span data-ttu-id="1afdf-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1afdf-163">-Confirm</span></span>

<span data-ttu-id="1afdf-164">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1afdf-165">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1afdf-165">-WhatIf</span></span>

<span data-ttu-id="1afdf-166">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="1afdf-166">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="1afdf-167">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="1afdf-167">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1afdf-168">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1afdf-168">CommonParameters</span></span>

<span data-ttu-id="1afdf-169">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-169">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="1afdf-170">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1afdf-170">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="1afdf-171">入力</span><span class="sxs-lookup"><span data-stu-id="1afdf-171">INPUTS</span></span>

### <span data-ttu-id="1afdf-172">System.String</span><span class="sxs-lookup"><span data-stu-id="1afdf-172">System.String</span></span>

<span data-ttu-id="1afdf-173">パイプを使用してパス文字列をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="1afdf-173">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="1afdf-174">出力</span><span class="sxs-lookup"><span data-stu-id="1afdf-174">OUTPUTS</span></span>

### <span data-ttu-id="1afdf-175">なし</span><span class="sxs-lookup"><span data-stu-id="1afdf-175">None</span></span>

<span data-ttu-id="1afdf-176">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="1afdf-176">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="1afdf-177">注</span><span class="sxs-lookup"><span data-stu-id="1afdf-177">NOTES</span></span>

- <span data-ttu-id="1afdf-178">`Clear-Item`コマンドレットは、 **Alias**、 **Environment**、 **Function**、 **Registry**、 **Variable** プロバイダーなど、いくつかの PowerShell プロバイダーでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1afdf-178">The `Clear-Item` cmdlet is supported only by several PowerShell providers, including the **Alias**, **Environment**, **Function**, **Registry**, and **Variable** providers.</span></span> <span data-ttu-id="1afdf-179">そのため、を使用して、 `Clear-Item` プロバイダーの名前空間内の項目の内容を削除できます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-179">As such, you can use `Clear-Item` to delete the content of items in the provider namespaces.</span></span> <span data-ttu-id="1afdf-180">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="1afdf-180">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="1afdf-181">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1afdf-181">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
- <span data-ttu-id="1afdf-182">`Clear-Item`PowerShell FileSystem プロバイダーはこのコマンドレットをサポートしていないため、を使用してファイルの内容を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="1afdf-182">You cannot use `Clear-Item` to delete the contents of a file, because the PowerShell FileSystem provider does not support this cmdlet.</span></span> <span data-ttu-id="1afdf-183">ファイルをクリアするには、を使用し `Clear-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="1afdf-183">To clear files, use the `Clear-Content`.</span></span>

## <span data-ttu-id="1afdf-184">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1afdf-184">RELATED LINKS</span></span>

[<span data-ttu-id="1afdf-185">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="1afdf-185">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="1afdf-186">Get-Item</span><span class="sxs-lookup"><span data-stu-id="1afdf-186">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="1afdf-187">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="1afdf-187">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="1afdf-188">Move-Item</span><span class="sxs-lookup"><span data-stu-id="1afdf-188">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="1afdf-189">New-Item</span><span class="sxs-lookup"><span data-stu-id="1afdf-189">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="1afdf-190">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="1afdf-190">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="1afdf-191">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="1afdf-191">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="1afdf-192">Set-Item</span><span class="sxs-lookup"><span data-stu-id="1afdf-192">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="1afdf-193">about_Providers</span><span class="sxs-lookup"><span data-stu-id="1afdf-193">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

