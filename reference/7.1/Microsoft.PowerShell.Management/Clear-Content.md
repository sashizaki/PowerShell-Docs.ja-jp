---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-content?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Content
ms.openlocfilehash: 89ac365524658612dd878cf8c2c462a40a278487
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692748"
---
# <span data-ttu-id="c7c87-102">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="c7c87-102">Clear-Content</span></span>

## <span data-ttu-id="c7c87-103">概要</span><span class="sxs-lookup"><span data-stu-id="c7c87-103">SYNOPSIS</span></span>
<span data-ttu-id="c7c87-104">項目の内容を削除します。項目自体は削除しません。</span><span class="sxs-lookup"><span data-stu-id="c7c87-104">Deletes the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="c7c87-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c7c87-105">SYNTAX</span></span>

### <span data-ttu-id="c7c87-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="c7c87-106">Path (Default)</span></span>

```
Clear-Content [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

### <span data-ttu-id="c7c87-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c7c87-107">LiteralPath</span></span>

```
Clear-Content -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

## <span data-ttu-id="c7c87-108">Description</span><span class="sxs-lookup"><span data-stu-id="c7c87-108">DESCRIPTION</span></span>

<span data-ttu-id="c7c87-109">コマンドレットは、ファイルからテキストを削除するなど `Clear-Content` 、項目の内容を削除しますが、項目は削除しません。</span><span class="sxs-lookup"><span data-stu-id="c7c87-109">The `Clear-Content` cmdlet deletes the contents of an item, such as deleting the text from a file, but it does not delete the item.</span></span>
<span data-ttu-id="c7c87-110">その結果、項目は残りますが、空になります。</span><span class="sxs-lookup"><span data-stu-id="c7c87-110">As a result, the item exists, but it is empty.</span></span>
<span data-ttu-id="c7c87-111">は `Clear-Content` に似てい `Clear-Item` ますが、値を持つ項目ではなく、内容を持つ項目に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-111">The `Clear-Content` is similar to `Clear-Item`, but it works on items with contents, instead of items with values.</span></span>

## <span data-ttu-id="c7c87-112">例</span><span class="sxs-lookup"><span data-stu-id="c7c87-112">EXAMPLES</span></span>

### <span data-ttu-id="c7c87-113">例 1: ディレクトリからすべてのコンテンツを削除する</span><span class="sxs-lookup"><span data-stu-id="c7c87-113">Example 1: Delete all content from a directory</span></span>

```powershell
Clear-Content "..\SmpUsers\*\init.txt"
```

<span data-ttu-id="c7c87-114">このコマンドを実行すると、SmpUsers ディレクトリのすべてのサブディレクトリにある init.txt ファイルからすべての内容が削除されます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-114">This command deletes all of the content from the "init.txt" files in all subdirectories of the SmpUsers directory.</span></span>
<span data-ttu-id="c7c87-115">ファイル自体は削除されず、空になります。</span><span class="sxs-lookup"><span data-stu-id="c7c87-115">The files are not deleted, but they are empty.</span></span>

### <span data-ttu-id="c7c87-116">例 2: ワイルドカードを使用してすべてのファイルの内容を削除する</span><span class="sxs-lookup"><span data-stu-id="c7c87-116">Example 2: Delete content of all files with a wildcard</span></span>

```powershell
Clear-Content -Path "*" -Filter "*.log" -Force
```

<span data-ttu-id="c7c87-117">このコマンドを実行すると、読み取り専用属性が指定されているファイルを含め、現在のディレクトリ内で、拡張子が ".log" であるすべてのファイルから内容が削除されます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-117">This command deletes the contents of all files in the current directory with the ".log" file name extension, including files with the read-only attribute.</span></span> <span data-ttu-id="c7c87-118">パスのアスタリスク () は、 \* 現在のディレクトリ内のすべての項目を表します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-118">The asterisk (\*) in the path represents all items in the current directory.</span></span> <span data-ttu-id="c7c87-119">**Force** パラメーターを指定すると、読み取り専用ファイルに対してコマンドが有効になります。</span><span class="sxs-lookup"><span data-stu-id="c7c87-119">The **Force** parameter makes the command effective on read-only files.</span></span> <span data-ttu-id="c7c87-120">フィルターを使用して、パスに .log を指定する代わりに、.log ファイル名拡張子を持つファイルにコマンドを制限すると、 \* 操作が高速になります。</span><span class="sxs-lookup"><span data-stu-id="c7c87-120">Using a filter to restrict the command to files with the .log file name extension instead of specifying \*.log in the path makes the operation faster.</span></span>

### <span data-ttu-id="c7c87-121">例 3: ストリームからすべてのデータをクリアする</span><span class="sxs-lookup"><span data-stu-id="c7c87-121">Example 3: Clear all data from a stream</span></span>

<span data-ttu-id="c7c87-122">この例では、 `Clear-Content` ストリームをそのまま残したまま、コマンドレットが代替データストリームからコンテンツをクリアする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-122">This example shows how the `Clear-Content` cmdlet clears the content from an alternate data stream while leaving the stream intact.</span></span>

<span data-ttu-id="c7c87-123">最初のコマンドは、コマンドレットを使用して、 `Get-Content` `Zone.Identifier` インターネットからダウンロードされた Copy-Script.ps1 ファイル内のストリームの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-123">The first command uses the `Get-Content` cmdlet to get the content of the `Zone.Identifier` stream in the Copy-Script.ps1 file, which was downloaded from the Internet.</span></span>

<span data-ttu-id="c7c87-124">2番目のコマンドは、 `Clear-Content` コマンドレットを使用してコンテンツをクリアします。</span><span class="sxs-lookup"><span data-stu-id="c7c87-124">The second command uses the `Clear-Content` cmdlet to clear the content.</span></span>

<span data-ttu-id="c7c87-125">3 番目のコマンドは、最初のコマンドを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-125">The third command repeats the first command.</span></span> <span data-ttu-id="c7c87-126">コンテンツがクリアされていることを確認しますが、ストリームは残ります。</span><span class="sxs-lookup"><span data-stu-id="c7c87-126">It verifies that the content is cleared, but the stream remains.</span></span> <span data-ttu-id="c7c87-127">ストリームが削除された場合、コマンドはエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-127">If the stream were deleted, the command would generate an error.</span></span>

<span data-ttu-id="c7c87-128">このようなメソッドを使用して、代替データストリームの内容を消去できます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-128">You can use a method like this one to clear the content of an alternate data stream.</span></span> <span data-ttu-id="c7c87-129">ただし、インターネットからダウンロードされるファイルをブロックするセキュリティ チェックをなくす方法としては推奨されません。</span><span class="sxs-lookup"><span data-stu-id="c7c87-129">However, it is not the recommended way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="c7c87-130">ダウンロードしたファイルが安全であることを確認した場合は、コマンドレットを使用し `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-130">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

```
PS C:\> Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

[ZoneTransfer]
ZoneId=3

PS C:\>Clear-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

PS C:\>Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
PS C:\>
```

## <span data-ttu-id="c7c87-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c7c87-131">PARAMETERS</span></span>

### <span data-ttu-id="c7c87-132">-ストリーム</span><span class="sxs-lookup"><span data-stu-id="c7c87-132">-Stream</span></span>

> [!NOTE]
> <span data-ttu-id="c7c87-133">このパラメーターは Windows でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-133">This Parameter is only available on Windows.</span></span>

<span data-ttu-id="c7c87-134">コンテンツの代替データストリームを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-134">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="c7c87-135">ストリームが存在しない場合は、このコマンドレットによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-135">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="c7c87-136">ワイルドカード文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c7c87-136">Wildcard characters are not supported.</span></span>

<span data-ttu-id="c7c87-137">**Stream** は、FileSystem プロバイダーによってに追加される動的パラメーターです `Clear-Content` 。</span><span class="sxs-lookup"><span data-stu-id="c7c87-137">**Stream** is a dynamic parameter that the FileSystem provider adds to `Clear-Content`.</span></span> <span data-ttu-id="c7c87-138">このパラメーターはファイルシステムドライブでのみ機能し、ファイルとディレクトリの両方で代替データストリームの内容をクリアします。</span><span class="sxs-lookup"><span data-stu-id="c7c87-138">This parameter works only in file system drives, and will clear the content of alternative data streams on both files and directories.</span></span>

<span data-ttu-id="c7c87-139">コマンドレットを使用し `Clear-Content` て、のような、amy オルタネートデータストリームの内容を変更でき `Zone.Identifier` ます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-139">You can use the `Clear-Content` cmdlet to change the content of amy alternate data stream, such as `Zone.Identifier`.</span></span> <span data-ttu-id="c7c87-140">ただし、インターネットからダウンロードされたファイルをブロックするセキュリティチェックを省略する方法としては、この方法をお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="c7c87-140">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="c7c87-141">ダウンロードしたファイルが安全であることを確認した場合は、コマンドレットを使用し `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-141">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="c7c87-142">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c7c87-142">This parameter was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="c7c87-143">PowerShell 7.2 の場合、で `Clear-Content` は、ディレクトリおよびファイルから代替データストリームの内容を消去できます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-143">As of PowerShell 7.2, `Clear-Content` can clear the content of alternative data streams from directories as well as files.</span></span>

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

### <span data-ttu-id="c7c87-144">-Credential</span><span class="sxs-lookup"><span data-stu-id="c7c87-144">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="c7c87-145">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c7c87-145">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="c7c87-146">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、Invoke コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-146">To impersonate another user, or elevate your credentials when running this cmdlet, use Invoke-Command.</span></span>

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

### <span data-ttu-id="c7c87-147">-除外</span><span class="sxs-lookup"><span data-stu-id="c7c87-147">-Exclude</span></span>

<span data-ttu-id="c7c87-148">文字列配列として、このコマンドレットによってコンテンツへのパスから省略される文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-148">Specifies, as a string array, strings that this cmdlet omits from the path to the content.</span></span> <span data-ttu-id="c7c87-149">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-149">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c7c87-150">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-150">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="c7c87-151">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-151">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="c7c87-152">-Filter</span><span class="sxs-lookup"><span data-stu-id="c7c87-152">-Filter</span></span>

<span data-ttu-id="c7c87-153">プロバイダーの形式や言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-153">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="c7c87-154">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-154">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c7c87-155">ワイルドカードを使用できるかどうかなど、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c7c87-155">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="c7c87-156">フィルターは他のパラメーターよりも効率的です。これは、オブジェクトを取得した後に PowerShell がオブジェクトをフィルター処理するのではなく、オブジェクトを取得するときにプロバイダーが適用するためです。</span><span class="sxs-lookup"><span data-stu-id="c7c87-156">Filters are more efficient than other parameters, because the provider applies them when retrieving the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="c7c87-157">-Force</span><span class="sxs-lookup"><span data-stu-id="c7c87-157">-Force</span></span>

<span data-ttu-id="c7c87-158">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-158">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="c7c87-159">-Include</span><span class="sxs-lookup"><span data-stu-id="c7c87-159">-Include</span></span>

<span data-ttu-id="c7c87-160">このコマンドレットによってクリアされるコンテンツを文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-160">Specifies, as a string array, content that this cmdlet clears.</span></span> <span data-ttu-id="c7c87-161">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-161">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c7c87-162">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-162">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="c7c87-163">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-163">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="c7c87-164">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c7c87-164">-LiteralPath</span></span>

<span data-ttu-id="c7c87-165">内容を削除する項目へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-165">Specifies the paths to the items from which content is deleted.</span></span> <span data-ttu-id="c7c87-166">**Path** パラメーターと異なり、**LiteralPath** の値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-166">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="c7c87-167">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="c7c87-167">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="c7c87-168">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-168">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="c7c87-169">単一引用符は、どの文字もエスケープシーケンスとして解釈されないように PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-169">Single quotation marks tell having PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="c7c87-170">-Path</span><span class="sxs-lookup"><span data-stu-id="c7c87-170">-Path</span></span>

<span data-ttu-id="c7c87-171">内容を削除する項目へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-171">Specifies the paths to the items from which content is deleted.</span></span> <span data-ttu-id="c7c87-172">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-172">Wildcards are permitted.</span></span> <span data-ttu-id="c7c87-173">コンテナーのパスではなく、項目のパスを指定してください。</span><span class="sxs-lookup"><span data-stu-id="c7c87-173">The paths must be paths to items, not to containers.</span></span> <span data-ttu-id="c7c87-174">たとえば、ディレクトリのパスではなく、1 つ以上のファイルのパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7c87-174">For example, you must specify a path to one or more files, not a path to a directory.</span></span> <span data-ttu-id="c7c87-175">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-175">Wildcards are permitted.</span></span> <span data-ttu-id="c7c87-176">このパラメーターは必須ですが、パラメーター名 (Path) は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c7c87-176">This parameter is required, but the parameter name ("Path") is optional.</span></span>

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

### <span data-ttu-id="c7c87-177">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c7c87-177">-Confirm</span></span>

<span data-ttu-id="c7c87-178">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-178">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c7c87-179">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c7c87-179">-WhatIf</span></span>

<span data-ttu-id="c7c87-180">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-180">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="c7c87-181">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c7c87-181">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c7c87-182">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c7c87-182">CommonParameters</span></span>

<span data-ttu-id="c7c87-183">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c7c87-183">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c7c87-184">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7c87-184">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c7c87-185">入力</span><span class="sxs-lookup"><span data-stu-id="c7c87-185">INPUTS</span></span>

### <span data-ttu-id="c7c87-186">なし</span><span class="sxs-lookup"><span data-stu-id="c7c87-186">None</span></span>

<span data-ttu-id="c7c87-187">パイプを使用してオブジェクトをにパイプすることはできません `Clear-Content` 。</span><span class="sxs-lookup"><span data-stu-id="c7c87-187">You cannot pipe objects to `Clear-Content`.</span></span>

## <span data-ttu-id="c7c87-188">出力</span><span class="sxs-lookup"><span data-stu-id="c7c87-188">OUTPUTS</span></span>

### <span data-ttu-id="c7c87-189">なし</span><span class="sxs-lookup"><span data-stu-id="c7c87-189">None</span></span>

<span data-ttu-id="c7c87-190">このコマンドレットはオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="c7c87-190">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="c7c87-191">注</span><span class="sxs-lookup"><span data-stu-id="c7c87-191">NOTES</span></span>

<span data-ttu-id="c7c87-192">は `Clear-Content` 、PowerShell FileSystem プロバイダーや、コンテンツを操作するその他のプロバイダーで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-192">You can use `Clear-Content` with the PowerShell FileSystem provider and with other providers that manipulate content.</span></span> <span data-ttu-id="c7c87-193">PowerShell 証明書またはレジストリプロバイダーによって管理されている項目など、コンテンツと見なされない項目をクリアするには、を使用し `Clear-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="c7c87-193">To clear items that are not considered to be content, such as items managed by the PowerShell Certificate or Registry providers, use `Clear-Item`.</span></span>

<span data-ttu-id="c7c87-194">`Clear-Content`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c7c87-194">The `Clear-Content` cmdlet is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="c7c87-195">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="c7c87-195">To list the providers available in your session, type `Get-PsProvider`.</span></span>
<span data-ttu-id="c7c87-196">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7c87-196">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="c7c87-197">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c7c87-197">RELATED LINKS</span></span>

[<span data-ttu-id="c7c87-198">Add-Content</span><span class="sxs-lookup"><span data-stu-id="c7c87-198">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="c7c87-199">Get-Content</span><span class="sxs-lookup"><span data-stu-id="c7c87-199">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="c7c87-200">Get-Item</span><span class="sxs-lookup"><span data-stu-id="c7c87-200">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="c7c87-201">Set-Content</span><span class="sxs-lookup"><span data-stu-id="c7c87-201">Set-Content</span></span>](Set-Content.md)

[<span data-ttu-id="c7c87-202">about_Providers</span><span class="sxs-lookup"><span data-stu-id="c7c87-202">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

