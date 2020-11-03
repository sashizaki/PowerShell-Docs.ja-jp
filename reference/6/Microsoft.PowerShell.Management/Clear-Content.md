---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-content?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Content
ms.openlocfilehash: 2d7575718391052fedea978b6957e5caec0eafdc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212563"
---
# <span data-ttu-id="de587-103">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="de587-103">Clear-Content</span></span>

## <span data-ttu-id="de587-104">概要</span><span class="sxs-lookup"><span data-stu-id="de587-104">SYNOPSIS</span></span>
<span data-ttu-id="de587-105">項目の内容を削除します。項目自体は削除しません。</span><span class="sxs-lookup"><span data-stu-id="de587-105">Deletes the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="de587-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="de587-106">SYNTAX</span></span>

### <span data-ttu-id="de587-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="de587-107">Path (Default)</span></span>

```
Clear-Content [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

### <span data-ttu-id="de587-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="de587-108">LiteralPath</span></span>

```
Clear-Content -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

## <span data-ttu-id="de587-109">Description</span><span class="sxs-lookup"><span data-stu-id="de587-109">DESCRIPTION</span></span>

<span data-ttu-id="de587-110">コマンドレットは、ファイルからテキストを削除するなど `Clear-Content` 、項目の内容を削除しますが、項目は削除しません。</span><span class="sxs-lookup"><span data-stu-id="de587-110">The `Clear-Content` cmdlet deletes the contents of an item, such as deleting the text from a file, but it does not delete the item.</span></span>
<span data-ttu-id="de587-111">その結果、項目は残りますが、空になります。</span><span class="sxs-lookup"><span data-stu-id="de587-111">As a result, the item exists, but it is empty.</span></span>
<span data-ttu-id="de587-112">は `Clear-Content` に似てい `Clear-Item` ますが、値を持つ項目ではなく、内容を持つ項目に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="de587-112">The `Clear-Content` is similar to `Clear-Item`, but it works on items with contents, instead of items with values.</span></span>

## <span data-ttu-id="de587-113">例</span><span class="sxs-lookup"><span data-stu-id="de587-113">EXAMPLES</span></span>

### <span data-ttu-id="de587-114">例 1: ディレクトリからすべてのコンテンツを削除する</span><span class="sxs-lookup"><span data-stu-id="de587-114">Example 1: Delete all content from a directory</span></span>

```powershell
Clear-Content "..\SmpUsers\*\init.txt"
```

<span data-ttu-id="de587-115">このコマンドを実行すると、SmpUsers ディレクトリのすべてのサブディレクトリにある init.txt ファイルからすべての内容が削除されます。</span><span class="sxs-lookup"><span data-stu-id="de587-115">This command deletes all of the content from the "init.txt" files in all subdirectories of the SmpUsers directory.</span></span>
<span data-ttu-id="de587-116">ファイル自体は削除されず、空になります。</span><span class="sxs-lookup"><span data-stu-id="de587-116">The files are not deleted, but they are empty.</span></span>

### <span data-ttu-id="de587-117">例 2: ワイルドカードを使用してすべてのファイルの内容を削除する</span><span class="sxs-lookup"><span data-stu-id="de587-117">Example 2: Delete content of all files with a wildcard</span></span>

```powershell
Clear-Content -Path "*" -Filter "*.log" -Force
```

<span data-ttu-id="de587-118">このコマンドを実行すると、読み取り専用属性が指定されているファイルを含め、現在のディレクトリ内で、拡張子が ".log" であるすべてのファイルから内容が削除されます。</span><span class="sxs-lookup"><span data-stu-id="de587-118">This command deletes the contents of all files in the current directory with the ".log" file name extension, including files with the read-only attribute.</span></span>
<span data-ttu-id="de587-119">パスのアスタリスク () は、 \* 現在のディレクトリ内のすべての項目を表します。</span><span class="sxs-lookup"><span data-stu-id="de587-119">The asterisk (\*) in the path represents all items in the current directory.</span></span>
<span data-ttu-id="de587-120">**Force** パラメーターを指定すると、読み取り専用ファイルに対してコマンドが有効になります。</span><span class="sxs-lookup"><span data-stu-id="de587-120">The **Force** parameter makes the command effective on read-only files.</span></span>
<span data-ttu-id="de587-121">フィルターを使用して、パスに .log を指定する代わりに、.log ファイル名拡張子を持つファイルにコマンドを制限すると、 \* 操作が高速になります。</span><span class="sxs-lookup"><span data-stu-id="de587-121">Using a filter to restrict the command to files with the .log file name extension instead of specifying \*.log in the path makes the operation faster.</span></span>

### <span data-ttu-id="de587-122">例 3: ストリームからすべてのデータをクリアする</span><span class="sxs-lookup"><span data-stu-id="de587-122">Example 3: Clear all data from a stream</span></span>

<span data-ttu-id="de587-123">この例では、 `Clear-Content` ストリームをそのまま残したまま、コマンドレットが代替データストリームからコンテンツをクリアする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="de587-123">This example shows how the `Clear-Content` cmdlet clears the content from an alternate data stream while leaving the stream intact.</span></span>

<span data-ttu-id="de587-124">最初のコマンドは、コマンドレットを使用して、 `Get-Content` インターネットからダウンロードされた Copy-Script.ps1 ファイル内のゾーン識別子ストリームの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="de587-124">The first command uses the `Get-Content` cmdlet to get the content of the Zone.Identifier stream in the Copy-Script.ps1 file, which was downloaded from the Internet.</span></span>

<span data-ttu-id="de587-125">2番目のコマンドは、 `Clear-Content` コマンドレットを使用してコンテンツをクリアします。</span><span class="sxs-lookup"><span data-stu-id="de587-125">The second command uses the `Clear-Content` cmdlet to clear the content.</span></span>

<span data-ttu-id="de587-126">3 番目のコマンドは、最初のコマンドを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="de587-126">The third command repeats the first command.</span></span> <span data-ttu-id="de587-127">コンテンツがクリアされていることを確認しますが、ストリームは残ります。</span><span class="sxs-lookup"><span data-stu-id="de587-127">It verifies that the content is cleared, but the stream remains.</span></span> <span data-ttu-id="de587-128">ストリームが削除された場合、コマンドはエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="de587-128">If the stream were deleted, the command would generate an error.</span></span>

<span data-ttu-id="de587-129">このようなメソッドを使用して、代替データストリームの内容を消去できます。</span><span class="sxs-lookup"><span data-stu-id="de587-129">You can use a method like this one to clear the content of an alternate data stream.</span></span> <span data-ttu-id="de587-130">ただし、インターネットからダウンロードされるファイルをブロックするセキュリティ チェックをなくす方法としては推奨されません。</span><span class="sxs-lookup"><span data-stu-id="de587-130">However, it is not the recommended way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="de587-131">ダウンロードしたファイルが安全であることを確認した場合は、コマンドレットを使用し `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="de587-131">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

```
PS C:\> Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

[ZoneTransfer]
ZoneId=3

PS C:\>Clear-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

PS C:\>Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
PS C:\>
```

## <span data-ttu-id="de587-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="de587-132">PARAMETERS</span></span>

### <span data-ttu-id="de587-133">-ストリーム</span><span class="sxs-lookup"><span data-stu-id="de587-133">-Stream</span></span>

<span data-ttu-id="de587-134">コンテンツの代替データストリームを指定します。</span><span class="sxs-lookup"><span data-stu-id="de587-134">Specifies an alternative data stream for content.</span></span>
<span data-ttu-id="de587-135">ストリームが存在しない場合は、このコマンドレットによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="de587-135">If the stream does not exist, this cmdlet creates it.</span></span>
<span data-ttu-id="de587-136">ワイルドカード文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="de587-136">Wildcard characters are not supported.</span></span>

<span data-ttu-id="de587-137">Stream は、FileSystem プロバイダーによってに追加される動的パラメーターです `Clear-Content` 。</span><span class="sxs-lookup"><span data-stu-id="de587-137">Stream is a dynamic parameter that the FileSystem provider adds to `Clear-Content`.</span></span>
<span data-ttu-id="de587-138">このパラメーターはファイル システム ドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="de587-138">This parameter works only in file system drives.</span></span>

<span data-ttu-id="de587-139">コマンドレットを使用して、 `Clear-Content` ゾーンの内容を変更できます。識別子代替データストリーム。</span><span class="sxs-lookup"><span data-stu-id="de587-139">You can use the `Clear-Content` cmdlet to change the content of the Zone.Identifier alternate data stream.</span></span>
<span data-ttu-id="de587-140">ただし、インターネットからダウンロードされたファイルをブロックするセキュリティチェックを省略する方法としては、この方法をお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="de587-140">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span>
<span data-ttu-id="de587-141">ダウンロードしたファイルが安全であることを確認した場合は、コマンドレットを使用し `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="de587-141">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de587-142">-Credential</span><span class="sxs-lookup"><span data-stu-id="de587-142">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="de587-143">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="de587-143">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="de587-144">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、Invoke コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="de587-144">To impersonate another user, or elevate your credentials when running this cmdlet, use Invoke-Command.</span></span>

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

### <span data-ttu-id="de587-145">-除外</span><span class="sxs-lookup"><span data-stu-id="de587-145">-Exclude</span></span>

<span data-ttu-id="de587-146">文字列配列として、このコマンドレットによってコンテンツへのパスから省略される文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="de587-146">Specifies, as a string array, strings that this cmdlet omits from the path to the content.</span></span>
<span data-ttu-id="de587-147">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="de587-147">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="de587-148">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="de587-148">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="de587-149">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="de587-149">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="de587-150">-Filter</span><span class="sxs-lookup"><span data-stu-id="de587-150">-Filter</span></span>

<span data-ttu-id="de587-151">プロバイダーの形式や言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="de587-151">Specifies a filter in the provider's format or language.</span></span>
<span data-ttu-id="de587-152">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="de587-152">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="de587-153">ワイルドカードを使用できるかどうかなど、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="de587-153">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span>
<span data-ttu-id="de587-154">フィルターは他のパラメーターよりも効率的です。これは、オブジェクトを取得した後に PowerShell がオブジェクトをフィルター処理するのではなく、オブジェクトを取得するときにプロバイダーが適用するためです。</span><span class="sxs-lookup"><span data-stu-id="de587-154">Filters are more efficient than other parameters, because the provider applies them when retrieving the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="de587-155">-Force</span><span class="sxs-lookup"><span data-stu-id="de587-155">-Force</span></span>

<span data-ttu-id="de587-156">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="de587-156">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="de587-157">-Include</span><span class="sxs-lookup"><span data-stu-id="de587-157">-Include</span></span>

<span data-ttu-id="de587-158">このコマンドレットによってクリアされるコンテンツを文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="de587-158">Specifies, as a string array, content that this cmdlet clears.</span></span>
<span data-ttu-id="de587-159">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="de587-159">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="de587-160">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="de587-160">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="de587-161">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="de587-161">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="de587-162">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="de587-162">-LiteralPath</span></span>

<span data-ttu-id="de587-163">内容を削除する項目へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="de587-163">Specifies the paths to the items from which content is deleted.</span></span>
<span data-ttu-id="de587-164">**Path** パラメーターと異なり、 **LiteralPath** の値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="de587-164">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="de587-165">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="de587-165">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="de587-166">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="de587-166">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="de587-167">単一引用符は、どの文字もエスケープシーケンスとして解釈されないように PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="de587-167">Single quotation marks tell having PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="de587-168">-Path</span><span class="sxs-lookup"><span data-stu-id="de587-168">-Path</span></span>

<span data-ttu-id="de587-169">内容を削除する項目へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="de587-169">Specifies the paths to the items from which content is deleted.</span></span>
<span data-ttu-id="de587-170">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="de587-170">Wildcards are permitted.</span></span>
<span data-ttu-id="de587-171">コンテナーのパスではなく、項目のパスを指定してください。</span><span class="sxs-lookup"><span data-stu-id="de587-171">The paths must be paths to items, not to containers.</span></span>
<span data-ttu-id="de587-172">たとえば、ディレクトリのパスではなく、1 つ以上のファイルのパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de587-172">For example, you must specify a path to one or more files, not a path to a directory.</span></span>
<span data-ttu-id="de587-173">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="de587-173">Wildcards are permitted.</span></span>
<span data-ttu-id="de587-174">このパラメーターは必須ですが、パラメーター名 (Path) は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="de587-174">This parameter is required, but the parameter name ("Path") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="de587-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="de587-175">-Confirm</span></span>

<span data-ttu-id="de587-176">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="de587-176">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de587-177">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="de587-177">-WhatIf</span></span>

<span data-ttu-id="de587-178">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="de587-178">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="de587-179">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="de587-179">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="de587-180">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="de587-180">CommonParameters</span></span>

<span data-ttu-id="de587-181">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="de587-181">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="de587-182">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de587-182">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="de587-183">入力</span><span class="sxs-lookup"><span data-stu-id="de587-183">INPUTS</span></span>

### <span data-ttu-id="de587-184">なし</span><span class="sxs-lookup"><span data-stu-id="de587-184">None</span></span>

<span data-ttu-id="de587-185">パイプを使用してオブジェクトをにパイプすることはできません `Clear-Content` 。</span><span class="sxs-lookup"><span data-stu-id="de587-185">You cannot pipe objects to `Clear-Content`.</span></span>

## <span data-ttu-id="de587-186">出力</span><span class="sxs-lookup"><span data-stu-id="de587-186">OUTPUTS</span></span>

### <span data-ttu-id="de587-187">なし</span><span class="sxs-lookup"><span data-stu-id="de587-187">None</span></span>

<span data-ttu-id="de587-188">このコマンドレットはオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="de587-188">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="de587-189">注</span><span class="sxs-lookup"><span data-stu-id="de587-189">NOTES</span></span>

<span data-ttu-id="de587-190">は `Clear-Content` 、PowerShell FileSystem プロバイダーや、コンテンツを操作するその他のプロバイダーで使用できます。</span><span class="sxs-lookup"><span data-stu-id="de587-190">You can use `Clear-Content` with the PowerShell FileSystem provider and with other providers that manipulate content.</span></span>
<span data-ttu-id="de587-191">PowerShell 証明書またはレジストリプロバイダーによって管理されている項目など、コンテンツと見なされない項目をクリアするには、を使用し `Clear-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="de587-191">To clear items that are not considered to be content, such as items managed by the PowerShell Certificate or Registry providers, use `Clear-Item`.</span></span>

<span data-ttu-id="de587-192">`Clear-Content`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="de587-192">The `Clear-Content` cmdlet is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="de587-193">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="de587-193">To list the providers available in your session, type `Get-PsProvider`.</span></span>
<span data-ttu-id="de587-194">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de587-194">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="de587-195">関連リンク</span><span class="sxs-lookup"><span data-stu-id="de587-195">RELATED LINKS</span></span>

[<span data-ttu-id="de587-196">Add-Content</span><span class="sxs-lookup"><span data-stu-id="de587-196">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="de587-197">Get-Content</span><span class="sxs-lookup"><span data-stu-id="de587-197">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="de587-198">Get-Item</span><span class="sxs-lookup"><span data-stu-id="de587-198">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="de587-199">Set-Content</span><span class="sxs-lookup"><span data-stu-id="de587-199">Set-Content</span></span>](Set-Content.md)

[<span data-ttu-id="de587-200">about_Providers</span><span class="sxs-lookup"><span data-stu-id="de587-200">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
