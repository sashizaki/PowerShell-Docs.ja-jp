---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Item
ms.openlocfilehash: ebb79f16447aef2dd194505d805a34353f710e69
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601003"
---
# <span data-ttu-id="4d8eb-102">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="4d8eb-102">Invoke-Item</span></span>

## <span data-ttu-id="4d8eb-103">概要</span><span class="sxs-lookup"><span data-stu-id="4d8eb-103">SYNOPSIS</span></span>
<span data-ttu-id="4d8eb-104">指定した項目に対して、既定のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-104">Performs the default action on the specified item.</span></span>

## <span data-ttu-id="4d8eb-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4d8eb-105">SYNTAX</span></span>

### <span data-ttu-id="4d8eb-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="4d8eb-106">Path (Default)</span></span>

```
Invoke-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4d8eb-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4d8eb-107">LiteralPath</span></span>

```
Invoke-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4d8eb-108">Description</span><span class="sxs-lookup"><span data-stu-id="4d8eb-108">DESCRIPTION</span></span>

<span data-ttu-id="4d8eb-109">`Invoke-Item`コマンドレットは、指定された項目に対して既定のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-109">The `Invoke-Item` cmdlet performs the default action on the specified item.</span></span>
<span data-ttu-id="4d8eb-110">たとえば、実行可能ファイルを実行したり、ドキュメント ファイル タイプに関連付けられているアプリケーションでドキュメント ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-110">For example, it runs an executable file or opens a document file in the application associated with the document file type.</span></span>
<span data-ttu-id="4d8eb-111">既定のアクションは項目の種類によって異なり、データへのアクセスを提供する PowerShell プロバイダーによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-111">The default action depends on the type of item and is determined by the PowerShell provider that provides access to the data.</span></span>

## <span data-ttu-id="4d8eb-112">例</span><span class="sxs-lookup"><span data-stu-id="4d8eb-112">EXAMPLES</span></span>

### <span data-ttu-id="4d8eb-113">例 1: ファイルを開く</span><span class="sxs-lookup"><span data-stu-id="4d8eb-113">Example 1: Open a file</span></span>

<span data-ttu-id="4d8eb-114">このコマンドは Microsoft Office Word でファイル "aliasApr04.doc" を開きます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-114">This command opens the file "aliasApr04.doc" in Microsoft Office Word.</span></span>
<span data-ttu-id="4d8eb-115">この場合、Word で開くことは、".doc" ファイルの既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-115">In this case, opening in Word is the default action for ".doc" files.</span></span>

```powershell
Invoke-Item "C:\Test\aliasApr04.doc"
```

### <span data-ttu-id="4d8eb-116">例 2: 特定の種類のすべてのファイルを開く</span><span class="sxs-lookup"><span data-stu-id="4d8eb-116">Example 2: Open all files of a specific type</span></span>

<span data-ttu-id="4d8eb-117">このコマンドを実行すると、フォルダー内のすべての Microsoft Office Excel スプレッドシートが開き `C:\Documents and
Settings\Lister\My Documents` ます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-117">This command opens all of the Microsoft Office Excel spreadsheets in the `C:\Documents and
Settings\Lister\My Documents` folder.</span></span> <span data-ttu-id="4d8eb-118">各スプレッドシートは、Excel の新しいインスタンスで開かれます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-118">Each spreadsheet is opened in a new instance of Excel.</span></span>
<span data-ttu-id="4d8eb-119">この場合、Excel で開くことが、ファイルの既定のアクションになり `.xls` ます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-119">In this case, opening in Excel is the default action for `.xls` files.</span></span>

```powershell
Invoke-Item "C:\Documents and Settings\Lister\My Documents\*.xls"
```

## <span data-ttu-id="4d8eb-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4d8eb-120">PARAMETERS</span></span>

### <span data-ttu-id="4d8eb-121">-Credential</span><span class="sxs-lookup"><span data-stu-id="4d8eb-121">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="4d8eb-122">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-122">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="4d8eb-123">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-123">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="4d8eb-124">-除外</span><span class="sxs-lookup"><span data-stu-id="4d8eb-124">-Exclude</span></span>

<span data-ttu-id="4d8eb-125">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-125">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="4d8eb-126">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-126">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="4d8eb-127">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-127">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="4d8eb-128">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-128">Wildcard characters are permitted.</span></span> <span data-ttu-id="4d8eb-129">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-129">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="4d8eb-130">-Filter</span><span class="sxs-lookup"><span data-stu-id="4d8eb-130">-Filter</span></span>

<span data-ttu-id="4d8eb-131">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-131">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="4d8eb-132">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-132">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="4d8eb-133">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-133">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="4d8eb-134">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-134">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="4d8eb-135">-Include</span><span class="sxs-lookup"><span data-stu-id="4d8eb-135">-Include</span></span>

<span data-ttu-id="4d8eb-136">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-136">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="4d8eb-137">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="4d8eb-138">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-138">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="4d8eb-139">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="4d8eb-140">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-140">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="4d8eb-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4d8eb-141">-LiteralPath</span></span>

<span data-ttu-id="4d8eb-142">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-142">Specifies a path to one or more locations.</span></span> <span data-ttu-id="4d8eb-143">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-143">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="4d8eb-144">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-144">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="4d8eb-145">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-145">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="4d8eb-146">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="4d8eb-147">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-147">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="4d8eb-148">-Path</span><span class="sxs-lookup"><span data-stu-id="4d8eb-148">-Path</span></span>

<span data-ttu-id="4d8eb-149">選択した項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-149">Specifies the path to the selected item.</span></span>
<span data-ttu-id="4d8eb-150">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-150">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="4d8eb-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4d8eb-151">-Confirm</span></span>

<span data-ttu-id="4d8eb-152">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4d8eb-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4d8eb-153">-WhatIf</span></span>

<span data-ttu-id="4d8eb-154">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4d8eb-155">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4d8eb-156">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4d8eb-156">CommonParameters</span></span>

<span data-ttu-id="4d8eb-157">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-157">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="4d8eb-158">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-158">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="4d8eb-159">入力</span><span class="sxs-lookup"><span data-stu-id="4d8eb-159">INPUTS</span></span>

### <span data-ttu-id="4d8eb-160">System.String</span><span class="sxs-lookup"><span data-stu-id="4d8eb-160">System.String</span></span>

<span data-ttu-id="4d8eb-161">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-161">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="4d8eb-162">出力</span><span class="sxs-lookup"><span data-stu-id="4d8eb-162">OUTPUTS</span></span>

### <span data-ttu-id="4d8eb-163">なし</span><span class="sxs-lookup"><span data-stu-id="4d8eb-163">None</span></span>

<span data-ttu-id="4d8eb-164">このコマンドは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-164">The command does not generate any output.</span></span>
<span data-ttu-id="4d8eb-165">ただし、コマンドによって呼び出される項目によって出力が生成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-165">However, output might be generated by the item that it invokes.</span></span>

## <span data-ttu-id="4d8eb-166">注</span><span class="sxs-lookup"><span data-stu-id="4d8eb-166">NOTES</span></span>

<span data-ttu-id="4d8eb-167">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-167">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="4d8eb-168">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-168">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="4d8eb-169">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d8eb-169">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="4d8eb-170">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4d8eb-170">RELATED LINKS</span></span>

[<span data-ttu-id="4d8eb-171">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="4d8eb-171">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="4d8eb-172">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="4d8eb-172">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="4d8eb-173">Get-Item</span><span class="sxs-lookup"><span data-stu-id="4d8eb-173">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="4d8eb-174">Move-Item</span><span class="sxs-lookup"><span data-stu-id="4d8eb-174">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="4d8eb-175">New-Item</span><span class="sxs-lookup"><span data-stu-id="4d8eb-175">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="4d8eb-176">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="4d8eb-176">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="4d8eb-177">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="4d8eb-177">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="4d8eb-178">Set-Item</span><span class="sxs-lookup"><span data-stu-id="4d8eb-178">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="4d8eb-179">about_Providers</span><span class="sxs-lookup"><span data-stu-id="4d8eb-179">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

