---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Item
ms.openlocfilehash: 6aac74b9b084996377b97997ab78972cb28b0959
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215384"
---
# <span data-ttu-id="a3e27-103">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="a3e27-103">Invoke-Item</span></span>

## <span data-ttu-id="a3e27-104">概要</span><span class="sxs-lookup"><span data-stu-id="a3e27-104">SYNOPSIS</span></span>
<span data-ttu-id="a3e27-105">指定した項目に対して、既定のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="a3e27-105">Performs the default action on the specified item.</span></span>

## <span data-ttu-id="a3e27-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a3e27-106">SYNTAX</span></span>

### <span data-ttu-id="a3e27-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="a3e27-107">Path (Default)</span></span>

```
Invoke-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="a3e27-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a3e27-108">LiteralPath</span></span>

```
Invoke-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="a3e27-109">Description</span><span class="sxs-lookup"><span data-stu-id="a3e27-109">DESCRIPTION</span></span>

<span data-ttu-id="a3e27-110">`Invoke-Item`コマンドレットは、指定された項目に対して既定のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="a3e27-110">The `Invoke-Item` cmdlet performs the default action on the specified item.</span></span>
<span data-ttu-id="a3e27-111">たとえば、実行可能ファイルを実行したり、ドキュメント ファイル タイプに関連付けられているアプリケーションでドキュメント ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a3e27-111">For example, it runs an executable file or opens a document file in the application associated with the document file type.</span></span>
<span data-ttu-id="a3e27-112">既定のアクションは項目の種類によって異なり、データへのアクセスを提供する PowerShell プロバイダーによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="a3e27-112">The default action depends on the type of item and is determined by the PowerShell provider that provides access to the data.</span></span>

## <span data-ttu-id="a3e27-113">例</span><span class="sxs-lookup"><span data-stu-id="a3e27-113">EXAMPLES</span></span>

### <span data-ttu-id="a3e27-114">例 1: ファイルを開く</span><span class="sxs-lookup"><span data-stu-id="a3e27-114">Example 1: Open a file</span></span>

<span data-ttu-id="a3e27-115">このコマンドは Microsoft Office Word でファイル "aliasApr04.doc" を開きます。</span><span class="sxs-lookup"><span data-stu-id="a3e27-115">This command opens the file "aliasApr04.doc" in Microsoft Office Word.</span></span>
<span data-ttu-id="a3e27-116">この場合、Word で開くことは、".doc" ファイルの既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="a3e27-116">In this case, opening in Word is the default action for ".doc" files.</span></span>

```powershell
Invoke-Item "C:\Test\aliasApr04.doc"
```

### <span data-ttu-id="a3e27-117">例 2: 特定の種類のすべてのファイルを開く</span><span class="sxs-lookup"><span data-stu-id="a3e27-117">Example 2: Open all files of a specific type</span></span>

<span data-ttu-id="a3e27-118">このコマンドは、"C:\documents and and Settings\Lister\My Documents" フォルダー内のすべての Microsoft Office Excel スプレッドシートを開きます。</span><span class="sxs-lookup"><span data-stu-id="a3e27-118">This command opens all of the Microsoft Office Excel spreadsheets in the "C:\Documents and Settings\Lister\My Documents" folder.</span></span>
<span data-ttu-id="a3e27-119">各スプレッドシートは、Excel の新しいインスタンスで開かれます。</span><span class="sxs-lookup"><span data-stu-id="a3e27-119">Each spreadsheet is opened in a new instance of Excel.</span></span>
<span data-ttu-id="a3e27-120">この場合、Excel で開くことは、".xls" ファイルの既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="a3e27-120">In this case, opening in Excel is the default action for ".xls" files.</span></span>

```powershell
Invoke-Item "C:\Documents and Settings\Lister\My Documents\*.xls"
```

## <span data-ttu-id="a3e27-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a3e27-121">PARAMETERS</span></span>

### <span data-ttu-id="a3e27-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="a3e27-122">-Credential</span></span>

<span data-ttu-id="a3e27-123">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="a3e27-123">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="a3e27-124">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="a3e27-124">The default is the current user.</span></span>

<span data-ttu-id="a3e27-125">「User01」や「Domain01\User01」のようなユーザー名を入力するか、  コマンドレットで生成されるような `Get-Credential` オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3e27-125">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="a3e27-126">ユーザー名を入力すると、パスワードの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3e27-126">If you type a user name, you are prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="a3e27-127">このパラメーターは、Windows PowerShell でインストールされるプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a3e27-127">This parameter is not supported by any providers installed with Windows PowerShell.</span></span>

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

### <span data-ttu-id="a3e27-128">-除外</span><span class="sxs-lookup"><span data-stu-id="a3e27-128">-Exclude</span></span>

<span data-ttu-id="a3e27-129">このコマンドレットによって操作から除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="a3e27-129">Specifies, as a string array, an item or items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="a3e27-130">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="a3e27-130">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="a3e27-131">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3e27-131">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="a3e27-132">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a3e27-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a3e27-133">-Filter</span><span class="sxs-lookup"><span data-stu-id="a3e27-133">-Filter</span></span>

<span data-ttu-id="a3e27-134">プロバイダーの形式または言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="a3e27-134">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="a3e27-135">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="a3e27-135">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="a3e27-136">ワイルドカード文字の使用など、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="a3e27-136">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="a3e27-137">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="a3e27-137">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="a3e27-138">-Include</span><span class="sxs-lookup"><span data-stu-id="a3e27-138">-Include</span></span>

<span data-ttu-id="a3e27-139">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="a3e27-139">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="a3e27-140">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="a3e27-140">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="a3e27-141">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3e27-141">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="a3e27-142">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a3e27-142">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a3e27-143">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a3e27-143">-LiteralPath</span></span>

<span data-ttu-id="a3e27-144">項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a3e27-144">Specifies a path to the item.</span></span>
<span data-ttu-id="a3e27-145">**Path** パラメーターと異なり、 **LiteralPath** の値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3e27-145">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="a3e27-146">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="a3e27-146">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="a3e27-147">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="a3e27-147">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="a3e27-148">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="a3e27-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="a3e27-149">-Path</span><span class="sxs-lookup"><span data-stu-id="a3e27-149">-Path</span></span>

<span data-ttu-id="a3e27-150">選択した項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a3e27-150">Specifies the path to the selected item.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a3e27-151">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="a3e27-151">-UseTransaction</span></span>

<span data-ttu-id="a3e27-152">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3e27-152">Includes the command in the active transaction.</span></span>
<span data-ttu-id="a3e27-153">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="a3e27-153">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="a3e27-154">詳細については、「about_transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3e27-154">For more information, see about_transactions.</span></span>

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

### <span data-ttu-id="a3e27-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a3e27-155">-Confirm</span></span>
<span data-ttu-id="a3e27-156">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3e27-156">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a3e27-157">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a3e27-157">-WhatIf</span></span>

<span data-ttu-id="a3e27-158">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="a3e27-158">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a3e27-159">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a3e27-159">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a3e27-160">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a3e27-160">CommonParameters</span></span>

<span data-ttu-id="a3e27-161">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="a3e27-161">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="a3e27-162">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3e27-162">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a3e27-163">入力</span><span class="sxs-lookup"><span data-stu-id="a3e27-163">INPUTS</span></span>

### <span data-ttu-id="a3e27-164">System.String</span><span class="sxs-lookup"><span data-stu-id="a3e27-164">System.String</span></span>

<span data-ttu-id="a3e27-165">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="a3e27-165">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="a3e27-166">出力</span><span class="sxs-lookup"><span data-stu-id="a3e27-166">OUTPUTS</span></span>

### <span data-ttu-id="a3e27-167">なし</span><span class="sxs-lookup"><span data-stu-id="a3e27-167">None</span></span>

<span data-ttu-id="a3e27-168">このコマンドは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="a3e27-168">The command does not generate any output.</span></span>
<span data-ttu-id="a3e27-169">ただし、コマンドによって呼び出される項目によって出力が生成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3e27-169">However, output might be generated by the item that it invokes.</span></span>

## <span data-ttu-id="a3e27-170">注</span><span class="sxs-lookup"><span data-stu-id="a3e27-170">NOTES</span></span>

<span data-ttu-id="a3e27-171">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="a3e27-171">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="a3e27-172">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="a3e27-172">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="a3e27-173">詳細については、「about_Providers」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3e27-173">For more information, see about_Providers.</span></span>

## <span data-ttu-id="a3e27-174">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a3e27-174">RELATED LINKS</span></span>

[<span data-ttu-id="a3e27-175">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="a3e27-175">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="a3e27-176">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="a3e27-176">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="a3e27-177">Get-Item</span><span class="sxs-lookup"><span data-stu-id="a3e27-177">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="a3e27-178">Move-Item</span><span class="sxs-lookup"><span data-stu-id="a3e27-178">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="a3e27-179">New-Item</span><span class="sxs-lookup"><span data-stu-id="a3e27-179">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="a3e27-180">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="a3e27-180">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="a3e27-181">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="a3e27-181">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="a3e27-182">Set-Item</span><span class="sxs-lookup"><span data-stu-id="a3e27-182">Set-Item</span></span>](Set-Item.md)
