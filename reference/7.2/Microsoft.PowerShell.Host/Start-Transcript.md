---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 01/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/start-transcript?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transcript
ms.openlocfilehash: d0987c77e3c2bb8cee08e67610cd6fe4fedc36e4
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "99602406"
---
# <span data-ttu-id="58063-102">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="58063-102">Start-Transcript</span></span>

## <span data-ttu-id="58063-103">構文</span><span class="sxs-lookup"><span data-stu-id="58063-103">Synopsis</span></span>
<span data-ttu-id="58063-104">テキストファイルへの PowerShell セッションのすべてまたは一部のレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="58063-104">Creates a record of all or part of a PowerShell session to a text file.</span></span>

## <span data-ttu-id="58063-105">構文</span><span class="sxs-lookup"><span data-stu-id="58063-105">Syntax</span></span>

### <span data-ttu-id="58063-106">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="58063-106">ByPath (Default)</span></span>

```
Start-Transcript [[-Path] <String>] [-Append] [-Force] [-NoClobber] [-IncludeInvocationHeader]
 [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="58063-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="58063-107">ByLiteralPath</span></span>

```
Start-Transcript [[-LiteralPath] <String>] [-Append] [-Force] [-NoClobber]
 [-IncludeInvocationHeader] [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="58063-108">ByOutputDirectory</span><span class="sxs-lookup"><span data-stu-id="58063-108">ByOutputDirectory</span></span>

```
Start-Transcript [[-OutputDirectory] <String>] [-Append] [-Force] [-NoClobber]
 [-IncludeInvocationHeader] [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="58063-109">説明</span><span class="sxs-lookup"><span data-stu-id="58063-109">Description</span></span>

<span data-ttu-id="58063-110">コマンドレットにより、 `Start-Transcript` PowerShell セッションのすべてまたは一部のレコードがテキストファイルに作成されます。</span><span class="sxs-lookup"><span data-stu-id="58063-110">The `Start-Transcript` cmdlet creates a record of all or part of a PowerShell session to a text file.</span></span> <span data-ttu-id="58063-111">トランスクリプトには、ユーザーが入力したすべてのコマンドと、コンソールに表示されたすべての出力が含まれます。</span><span class="sxs-lookup"><span data-stu-id="58063-111">The transcript includes all command that the user types and all output that appears on the console.</span></span>

<span data-ttu-id="58063-112">Windows PowerShell 5.0 以降、では、 `Start-Transcript` すべてのトランスクリプトの生成されたファイル名にホスト名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="58063-112">Starting in Windows PowerShell 5.0, `Start-Transcript` includes the hostname in the generated file name of all transcripts.</span></span> <span data-ttu-id="58063-113">これは、企業のログ記録が集中管理されている場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="58063-113">This is especially useful when your enterprise's logging is centralized.</span></span>
<span data-ttu-id="58063-114">コマンドレットによって作成されるファイルには、 `Start-Transcript` 2 つ以上のトランスクリプトが同時に開始された場合に上書きや重複が発生しないように、名前にランダムな文字が含まれます。</span><span class="sxs-lookup"><span data-stu-id="58063-114">Files that are created by the `Start-Transcript` cmdlet include random characters in names to prevent potential overwrites or duplication when two or more transcripts are started simultaneously.</span></span>
<span data-ttu-id="58063-115">これにより、一元化されたファイル共有に保存されているトランスクリプトの不正な検出も防止されます。</span><span class="sxs-lookup"><span data-stu-id="58063-115">This also prevents unauthorized discovery of transcripts that are stored in a centralized file share.</span></span>

<span data-ttu-id="58063-116">ターゲットファイルにバイトオーダーマーク (BOM) がない場合、では、 `Start-Transcript` ターゲットファイルのエンコードが既定で設定され `Utf8NoBom` ます。</span><span class="sxs-lookup"><span data-stu-id="58063-116">If the target file doesn't have a Byte Order Mark (BOM), `Start-Transcript` defaults to `Utf8NoBom` encoding in the target file.</span></span>

## <span data-ttu-id="58063-117">例</span><span class="sxs-lookup"><span data-stu-id="58063-117">Examples</span></span>

### <span data-ttu-id="58063-118">例 1: 既定の設定を使用してトランスクリプトファイルを開始する</span><span class="sxs-lookup"><span data-stu-id="58063-118">Example 1: Start a transcript file with default settings</span></span>

```powershell
Start-Transcript
```

<span data-ttu-id="58063-119">このコマンドは、既定のファイルの場所を使用してトランスクリプトを開始します。</span><span class="sxs-lookup"><span data-stu-id="58063-119">This command starts a transcript in the default file location.</span></span>

### <span data-ttu-id="58063-120">例 2: 特定の場所でトランスクリプトファイルを開始する</span><span class="sxs-lookup"><span data-stu-id="58063-120">Example 2: Start a transcript file at a specific location</span></span>

```powershell
Start-Transcript -Path "C:\transcripts\transcript0.txt" -NoClobber
```

<span data-ttu-id="58063-121">このコマンドは、のファイルでトランスクリプトを開始 `Transcript0.txt` `C:\transcripts` します。</span><span class="sxs-lookup"><span data-stu-id="58063-121">This command starts a transcript in the `Transcript0.txt` file in `C:\transcripts`.</span></span> <span data-ttu-id="58063-122">**NoClobber** パラメーターが使用されているため、既存のファイルは上書きされません。</span><span class="sxs-lookup"><span data-stu-id="58063-122">Since the **NoClobber** parameter is used, the command prevents any existing files from being overwritten.</span></span> <span data-ttu-id="58063-123">ファイルが `Transcript0.txt` 既に存在する場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="58063-123">If the `Transcript0.txt` file already exists, the command fails.</span></span>

## <span data-ttu-id="58063-124">パラメーター</span><span class="sxs-lookup"><span data-stu-id="58063-124">Parameters</span></span>

### <span data-ttu-id="58063-125">-追加</span><span class="sxs-lookup"><span data-stu-id="58063-125">-Append</span></span>

<span data-ttu-id="58063-126">このコマンドレットが、新しいトランスクリプトを既存のファイルの末尾に追加することを示します。</span><span class="sxs-lookup"><span data-stu-id="58063-126">Indicates that this cmdlet adds the new transcript to the end of an existing file.</span></span> <span data-ttu-id="58063-127">**Path** パラメーターを使用して、ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="58063-127">Use the **Path** parameter to specify the file.</span></span>

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

### <span data-ttu-id="58063-128">-Force</span><span class="sxs-lookup"><span data-stu-id="58063-128">-Force</span></span>

<span data-ttu-id="58063-129">コマンドレットがトランスクリプトを既存の読み取り専用ファイルに追加することを許可します。</span><span class="sxs-lookup"><span data-stu-id="58063-129">Allows the cmdlet to append the transcript to an existing read-only file.</span></span> <span data-ttu-id="58063-130">読み取り専用ファイルで使用した場合、このコマンドレットはファイルのアクセス許可を読み取り/書き込みに変更します。</span><span class="sxs-lookup"><span data-stu-id="58063-130">When used on a read-only file, the cmdlet changes the file permission to read-write.</span></span> <span data-ttu-id="58063-131">このパラメーターが使用されている場合、コマンドレットでセキュリティ制限をオーバーライドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="58063-131">The cmdlet cannot override security restrictions when this parameter is used.</span></span>

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

### <span data-ttu-id="58063-132">-IncludeInvocationHeader</span><span class="sxs-lookup"><span data-stu-id="58063-132">-IncludeInvocationHeader</span></span>

<span data-ttu-id="58063-133">コマンドの実行時に、このコマンドレットによってタイムスタンプがログに記録されることを示します。</span><span class="sxs-lookup"><span data-stu-id="58063-133">Indicates that this cmdlet logs the time stamp when commands are run.</span></span>

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

### <span data-ttu-id="58063-134">-UseMinimalHeader</span><span class="sxs-lookup"><span data-stu-id="58063-134">-UseMinimalHeader</span></span>

<span data-ttu-id="58063-135">既定では、詳細ヘッダーではなく、短いヘッダーをトランスクリプトに追加します。</span><span class="sxs-lookup"><span data-stu-id="58063-135">Prepend a short header to the transcript, instead of the detailed header included by default.</span></span> <span data-ttu-id="58063-136">このパラメーターは、PowerShell 6.2 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="58063-136">This parameter was added in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="58063-137">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="58063-137">-LiteralPath</span></span>

<span data-ttu-id="58063-138">トランスクリプトファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="58063-138">Specifies a location to the transcript file.</span></span> <span data-ttu-id="58063-139">**Path** パラメーターと異なり、**LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="58063-139">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="58063-140">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="58063-140">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="58063-141">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="58063-141">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="58063-142">単一引用符は、文字をエスケープシーケンスとして解釈しないことを PowerShell に伝えます。</span><span class="sxs-lookup"><span data-stu-id="58063-142">Single quotation marks inform PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58063-143">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="58063-143">-NoClobber</span></span>

<span data-ttu-id="58063-144">このコマンドレットが既存のファイルを上書きしないことを示します。</span><span class="sxs-lookup"><span data-stu-id="58063-144">Indicates that this cmdlet will not overwrite of an existing file.</span></span> <span data-ttu-id="58063-145">既定では、指定されたパスにトランスクリプトファイルが存在する場合、は `Start-Transcript` 警告なしにファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="58063-145">By default, if a transcript file exists in the specified path, `Start-Transcript` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58063-146">-OutputDirectory</span><span class="sxs-lookup"><span data-stu-id="58063-146">-OutputDirectory</span></span>

<span data-ttu-id="58063-147">トランスクリプトを保存する特定のパスとフォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="58063-147">Specifies a specific path and folder in which to save a transcript.</span></span> <span data-ttu-id="58063-148">PowerShell では、トランスクリプト名が自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="58063-148">PowerShell automatically assigns the transcript name.</span></span>

```yaml
Type: System.String
Parameter Sets: ByOutputDirectory
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58063-149">-Path</span><span class="sxs-lookup"><span data-stu-id="58063-149">-Path</span></span>

<span data-ttu-id="58063-150">トランスクリプトファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="58063-150">Specifies a location to the transcript file.</span></span> <span data-ttu-id="58063-151">ファイルへのパスを入力 `.txt` します。</span><span class="sxs-lookup"><span data-stu-id="58063-151">Enter a path to a `.txt` file.</span></span> <span data-ttu-id="58063-152">ワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="58063-152">Wildcards are not permitted.</span></span>

<span data-ttu-id="58063-153">パスを指定しない場合、は `Start-Transcript` グローバル変数の値のパスを使用し `$Transcript` ます。</span><span class="sxs-lookup"><span data-stu-id="58063-153">If you do not specify a path, `Start-Transcript` uses the path in the value of the `$Transcript` global variable.</span></span> <span data-ttu-id="58063-154">この変数を作成していない場合は、によって `Start-Transcript` ファイルにトランスクリプトが格納され `$Home\My Documents directory as \PowerShell_transcript.<time-stamp>.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="58063-154">If you have not created this variable, `Start-Transcript` stores the transcripts in the `$Home\My Documents directory as \PowerShell_transcript.<time-stamp>.txt` files.</span></span>

<span data-ttu-id="58063-155">パス内のいずれかのディレクトリが存在しない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="58063-155">If any of the directories in the path do not exist, the command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58063-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="58063-156">-Confirm</span></span>

<span data-ttu-id="58063-157">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="58063-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="58063-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="58063-158">-WhatIf</span></span>

<span data-ttu-id="58063-159">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="58063-159">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="58063-160">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="58063-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="58063-161">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="58063-161">CommonParameters</span></span>

<span data-ttu-id="58063-162">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="58063-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="58063-163">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58063-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="58063-164">入力</span><span class="sxs-lookup"><span data-stu-id="58063-164">Inputs</span></span>

### <span data-ttu-id="58063-165">なし</span><span class="sxs-lookup"><span data-stu-id="58063-165">None</span></span>

<span data-ttu-id="58063-166">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="58063-166">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="58063-167">出力</span><span class="sxs-lookup"><span data-stu-id="58063-167">Outputs</span></span>

### <span data-ttu-id="58063-168">System.String</span><span class="sxs-lookup"><span data-stu-id="58063-168">System.String</span></span>

<span data-ttu-id="58063-169">このコマンドレットは、確認メッセージと出力ファイルへのパスを含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="58063-169">This cmdlet returns a string that contains a confirmation message and the path to the output file.</span></span>

## <span data-ttu-id="58063-170">メモ</span><span class="sxs-lookup"><span data-stu-id="58063-170">Notes</span></span>

<span data-ttu-id="58063-171">トランスクリプトを停止するには、コマンドレットを使用し `Stop-Transcript` ます。</span><span class="sxs-lookup"><span data-stu-id="58063-171">To stop a transcript, use the `Stop-Transcript` cmdlet.</span></span>

<span data-ttu-id="58063-172">セッション全体を記録するには、 `Start-Transcript` プロファイルにコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="58063-172">To record an entire session, add the `Start-Transcript` command to your profile.</span></span> <span data-ttu-id="58063-173">詳細については、「 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58063-173">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

## <span data-ttu-id="58063-174">関連リンク</span><span class="sxs-lookup"><span data-stu-id="58063-174">Related Links</span></span>

[<span data-ttu-id="58063-175">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="58063-175">Stop-Transcript</span></span>](Stop-Transcript.md)
