---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Item
ms.openlocfilehash: 030e65f2b78ba91ddd4f6e2626372c1716218a78
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211648"
---
# <span data-ttu-id="7b925-103">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="7b925-103">Invoke-Item</span></span>

## <span data-ttu-id="7b925-104">概要</span><span class="sxs-lookup"><span data-stu-id="7b925-104">SYNOPSIS</span></span>
<span data-ttu-id="7b925-105">指定した項目に対して、既定のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="7b925-105">Performs the default action on the specified item.</span></span>

## <span data-ttu-id="7b925-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7b925-106">SYNTAX</span></span>

### <span data-ttu-id="7b925-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="7b925-107">Path (Default)</span></span>

```
Invoke-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7b925-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7b925-108">LiteralPath</span></span>

```
Invoke-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7b925-109">Description</span><span class="sxs-lookup"><span data-stu-id="7b925-109">DESCRIPTION</span></span>

<span data-ttu-id="7b925-110">`Invoke-Item`コマンドレットは、指定された項目に対して既定のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="7b925-110">The `Invoke-Item` cmdlet performs the default action on the specified item.</span></span>
<span data-ttu-id="7b925-111">たとえば、実行可能ファイルを実行したり、ドキュメント ファイル タイプに関連付けられているアプリケーションでドキュメント ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7b925-111">For example, it runs an executable file or opens a document file in the application associated with the document file type.</span></span>
<span data-ttu-id="7b925-112">既定のアクションは項目の種類によって異なり、データへのアクセスを提供する PowerShell プロバイダーによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="7b925-112">The default action depends on the type of item and is determined by the PowerShell provider that provides access to the data.</span></span>

## <span data-ttu-id="7b925-113">例</span><span class="sxs-lookup"><span data-stu-id="7b925-113">EXAMPLES</span></span>

### <span data-ttu-id="7b925-114">例 1: ファイルを開く</span><span class="sxs-lookup"><span data-stu-id="7b925-114">Example 1: Open a file</span></span>

<span data-ttu-id="7b925-115">このコマンドは Microsoft Office Word でファイル "aliasApr04.doc" を開きます。</span><span class="sxs-lookup"><span data-stu-id="7b925-115">This command opens the file "aliasApr04.doc" in Microsoft Office Word.</span></span>
<span data-ttu-id="7b925-116">この場合、Word で開くことは、".doc" ファイルの既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="7b925-116">In this case, opening in Word is the default action for ".doc" files.</span></span>

```powershell
Invoke-Item "C:\Test\aliasApr04.doc"
```

### <span data-ttu-id="7b925-117">例 2: 特定の種類のすべてのファイルを開く</span><span class="sxs-lookup"><span data-stu-id="7b925-117">Example 2: Open all files of a specific type</span></span>

<span data-ttu-id="7b925-118">このコマンドを実行すると、フォルダー内のすべての Microsoft Office Excel スプレッドシートが開き `C:\Documents and
Settings\Lister\My Documents` ます。</span><span class="sxs-lookup"><span data-stu-id="7b925-118">This command opens all of the Microsoft Office Excel spreadsheets in the `C:\Documents and
Settings\Lister\My Documents` folder.</span></span> <span data-ttu-id="7b925-119">各スプレッドシートは、Excel の新しいインスタンスで開かれます。</span><span class="sxs-lookup"><span data-stu-id="7b925-119">Each spreadsheet is opened in a new instance of Excel.</span></span>
<span data-ttu-id="7b925-120">この場合、Excel で開くことが、ファイルの既定のアクションになり `.xls` ます。</span><span class="sxs-lookup"><span data-stu-id="7b925-120">In this case, opening in Excel is the default action for `.xls` files.</span></span>

```powershell
Invoke-Item "C:\Documents and Settings\Lister\My Documents\*.xls"
```

## <span data-ttu-id="7b925-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7b925-121">PARAMETERS</span></span>

### <span data-ttu-id="7b925-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="7b925-122">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="7b925-123">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7b925-123">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="7b925-124">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b925-124">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="7b925-125">-除外</span><span class="sxs-lookup"><span data-stu-id="7b925-125">-Exclude</span></span>

<span data-ttu-id="7b925-126">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="7b925-126">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="7b925-127">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="7b925-127">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="7b925-128">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="7b925-128">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="7b925-129">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b925-129">Wildcard characters are permitted.</span></span> <span data-ttu-id="7b925-130">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="7b925-130">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="7b925-131">-Filter</span><span class="sxs-lookup"><span data-stu-id="7b925-131">-Filter</span></span>

<span data-ttu-id="7b925-132">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b925-132">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="7b925-133">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="7b925-133">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="7b925-134">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b925-134">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="7b925-135">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="7b925-135">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="7b925-136">-Include</span><span class="sxs-lookup"><span data-stu-id="7b925-136">-Include</span></span>

<span data-ttu-id="7b925-137">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b925-137">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="7b925-138">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="7b925-138">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="7b925-139">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="7b925-139">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="7b925-140">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b925-140">Wildcard characters are permitted.</span></span> <span data-ttu-id="7b925-141">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="7b925-141">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="7b925-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7b925-142">-LiteralPath</span></span>

<span data-ttu-id="7b925-143">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b925-143">Specifies a path to one or more locations.</span></span> <span data-ttu-id="7b925-144">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7b925-144">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="7b925-145">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="7b925-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="7b925-146">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="7b925-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="7b925-147">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="7b925-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="7b925-148">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b925-148">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="7b925-149">-Path</span><span class="sxs-lookup"><span data-stu-id="7b925-149">-Path</span></span>

<span data-ttu-id="7b925-150">選択した項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b925-150">Specifies the path to the selected item.</span></span>
<span data-ttu-id="7b925-151">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b925-151">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="7b925-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7b925-152">-Confirm</span></span>

<span data-ttu-id="7b925-153">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b925-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7b925-154">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7b925-154">-WhatIf</span></span>

<span data-ttu-id="7b925-155">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="7b925-155">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7b925-156">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="7b925-156">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7b925-157">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7b925-157">CommonParameters</span></span>

<span data-ttu-id="7b925-158">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="7b925-158">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="7b925-159">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b925-159">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="7b925-160">入力</span><span class="sxs-lookup"><span data-stu-id="7b925-160">INPUTS</span></span>

### <span data-ttu-id="7b925-161">System.String</span><span class="sxs-lookup"><span data-stu-id="7b925-161">System.String</span></span>

<span data-ttu-id="7b925-162">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="7b925-162">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="7b925-163">出力</span><span class="sxs-lookup"><span data-stu-id="7b925-163">OUTPUTS</span></span>

### <span data-ttu-id="7b925-164">なし</span><span class="sxs-lookup"><span data-stu-id="7b925-164">None</span></span>

<span data-ttu-id="7b925-165">このコマンドは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="7b925-165">The command does not generate any output.</span></span>
<span data-ttu-id="7b925-166">ただし、コマンドによって呼び出される項目によって出力が生成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="7b925-166">However, output might be generated by the item that it invokes.</span></span>

## <span data-ttu-id="7b925-167">注</span><span class="sxs-lookup"><span data-stu-id="7b925-167">NOTES</span></span>

<span data-ttu-id="7b925-168">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="7b925-168">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="7b925-169">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="7b925-169">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="7b925-170">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b925-170">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="7b925-171">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7b925-171">RELATED LINKS</span></span>

[<span data-ttu-id="7b925-172">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="7b925-172">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="7b925-173">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="7b925-173">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="7b925-174">Get-Item</span><span class="sxs-lookup"><span data-stu-id="7b925-174">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="7b925-175">Move-Item</span><span class="sxs-lookup"><span data-stu-id="7b925-175">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="7b925-176">New-Item</span><span class="sxs-lookup"><span data-stu-id="7b925-176">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="7b925-177">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="7b925-177">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="7b925-178">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="7b925-178">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="7b925-179">Set-Item</span><span class="sxs-lookup"><span data-stu-id="7b925-179">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="7b925-180">about_Providers</span><span class="sxs-lookup"><span data-stu-id="7b925-180">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

