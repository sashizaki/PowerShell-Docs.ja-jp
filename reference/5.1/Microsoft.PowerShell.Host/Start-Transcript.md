---
external help file: Microsoft.PowerShell.ConsoleHost.dll-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 01/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/start-transcript?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transcript
ms.openlocfilehash: 4f90dd8e3080d393e50fb8f48133c74909ec2b80
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "98860747"
---
# <span data-ttu-id="31db4-103">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="31db4-103">Start-Transcript</span></span>

## <span data-ttu-id="31db4-104">構文</span><span class="sxs-lookup"><span data-stu-id="31db4-104">Synopsis</span></span>
<span data-ttu-id="31db4-105">テキストファイルへの PowerShell セッションのすべてまたは一部のレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="31db4-105">Creates a record of all or part of a PowerShell session to a text file.</span></span>

## <span data-ttu-id="31db4-106">構文</span><span class="sxs-lookup"><span data-stu-id="31db4-106">Syntax</span></span>

### <span data-ttu-id="31db4-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="31db4-107">ByPath (Default)</span></span>

```
Start-Transcript [[-Path] <String>] [-Append] [-Force] [-NoClobber] [-IncludeInvocationHeader] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="31db4-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="31db4-108">ByLiteralPath</span></span>

```
Start-Transcript [[-LiteralPath] <String>] [-Append] [-Force] [-NoClobber] [-IncludeInvocationHeader] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="31db4-109">ByOutputDirectory</span><span class="sxs-lookup"><span data-stu-id="31db4-109">ByOutputDirectory</span></span>

```
Start-Transcript [[-OutputDirectory] <String>] [-Append] [-Force] [-NoClobber] [-IncludeInvocationHeader]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="31db4-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="31db4-110">Description</span></span>

<span data-ttu-id="31db4-111">コマンドレットにより、 `Start-Transcript` PowerShell セッションのすべてまたは一部のレコードがテキストファイルに作成されます。</span><span class="sxs-lookup"><span data-stu-id="31db4-111">The `Start-Transcript` cmdlet creates a record of all or part of a PowerShell session to a text file.</span></span> <span data-ttu-id="31db4-112">トランスクリプトには、ユーザーが入力したすべてのコマンドと、コンソールに表示されたすべての出力が含まれます。</span><span class="sxs-lookup"><span data-stu-id="31db4-112">The transcript includes all command that the user types and all output that appears on the console.</span></span>

<span data-ttu-id="31db4-113">Windows PowerShell 5.0 以降、では、 `Start-Transcript` すべてのトランスクリプトの生成されたファイル名にホスト名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="31db4-113">Starting in Windows PowerShell 5.0, `Start-Transcript` includes the hostname in the generated file name of all transcripts.</span></span> <span data-ttu-id="31db4-114">これは、企業のログ記録が集中管理されている場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="31db4-114">This is especially useful when your enterprise's logging is centralized.</span></span>
<span data-ttu-id="31db4-115">コマンドレットによって作成されるファイルには、 `Start-Transcript` 2 つ以上のトランスクリプトが同時に開始された場合に上書きや重複が発生しないように、名前にランダムな文字が含まれます。</span><span class="sxs-lookup"><span data-stu-id="31db4-115">Files that are created by the `Start-Transcript` cmdlet include random characters in names to prevent potential overwrites or duplication when two or more transcripts are started simultaneously.</span></span>
<span data-ttu-id="31db4-116">これにより、一元化されたファイル共有に保存されているトランスクリプトの不正な検出も防止されます。</span><span class="sxs-lookup"><span data-stu-id="31db4-116">This also prevents unauthorized discovery of transcripts that are stored in a centralized file share.</span></span>

<span data-ttu-id="31db4-117">**Append** パラメーターを使用する場合、ターゲットファイルにバイトオーダーマーク (BOM) がない場合は、 `Start-Transcript` ターゲットファイルのエンコードが既定で設定され `ASCII` ます。</span><span class="sxs-lookup"><span data-stu-id="31db4-117">When using the **Append** parameter, if the target file doesn't have a Byte Order Mark (BOM) `Start-Transcript` defaults to `ASCII` encoding in the target file.</span></span> <span data-ttu-id="31db4-118">この動作によって、トランスクリプトで mulitbyte 文字が不適切にエンコードされることがあります。</span><span class="sxs-lookup"><span data-stu-id="31db4-118">This behavior can result in improper encoding of mulitbyte characters in the transcript.</span></span>

## <span data-ttu-id="31db4-119">使用例</span><span class="sxs-lookup"><span data-stu-id="31db4-119">Examples</span></span>

### <span data-ttu-id="31db4-120">例 1: 既定の設定を使用してトランスクリプトファイルを開始する</span><span class="sxs-lookup"><span data-stu-id="31db4-120">Example 1: Start a transcript file with default settings</span></span>

```powershell
Start-Transcript
```

<span data-ttu-id="31db4-121">このコマンドは、既定のファイルの場所を使用してトランスクリプトを開始します。</span><span class="sxs-lookup"><span data-stu-id="31db4-121">This command starts a transcript in the default file location.</span></span>

### <span data-ttu-id="31db4-122">例 2: 特定の場所でトランスクリプトファイルを開始する</span><span class="sxs-lookup"><span data-stu-id="31db4-122">Example 2: Start a transcript file at a specific location</span></span>

```powershell
Start-Transcript -Path "C:\transcripts\transcript0.txt" -NoClobber
```

<span data-ttu-id="31db4-123">このコマンドは、のファイルでトランスクリプトを開始 `Transcript0.txt` `C:\transcripts` します。</span><span class="sxs-lookup"><span data-stu-id="31db4-123">This command starts a transcript in the `Transcript0.txt` file in `C:\transcripts`.</span></span> <span data-ttu-id="31db4-124">**NoClobber** パラメーターが使用されているため、既存のファイルは上書きされません。</span><span class="sxs-lookup"><span data-stu-id="31db4-124">Since the **NoClobber** parameter is used, the command prevents any existing files from being overwritten.</span></span> <span data-ttu-id="31db4-125">ファイルが `Transcript0.txt` 既に存在する場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="31db4-125">If the `Transcript0.txt` file already exists, the command fails.</span></span>

## <span data-ttu-id="31db4-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="31db4-126">Parameters</span></span>

### <span data-ttu-id="31db4-127">-追加</span><span class="sxs-lookup"><span data-stu-id="31db4-127">-Append</span></span>

<span data-ttu-id="31db4-128">このコマンドレットが、新しいトランスクリプトを既存のファイルの末尾に追加することを示します。</span><span class="sxs-lookup"><span data-stu-id="31db4-128">Indicates that this cmdlet adds the new transcript to the end of an existing file.</span></span> <span data-ttu-id="31db4-129">**Path** パラメーターを使用して、ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="31db4-129">Use the **Path** parameter to specify the file.</span></span>

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

### <span data-ttu-id="31db4-130">-Force</span><span class="sxs-lookup"><span data-stu-id="31db4-130">-Force</span></span>

<span data-ttu-id="31db4-131">コマンドレットがトランスクリプトを既存の読み取り専用ファイルに追加することを許可します。</span><span class="sxs-lookup"><span data-stu-id="31db4-131">Allows the cmdlet to append the transcript to an existing read-only file.</span></span> <span data-ttu-id="31db4-132">読み取り専用ファイルで使用した場合、このコマンドレットはファイルのアクセス許可を読み取り/書き込みに変更します。</span><span class="sxs-lookup"><span data-stu-id="31db4-132">When used on a read-only file, the cmdlet changes the file permission to read-write.</span></span> <span data-ttu-id="31db4-133">このパラメーターが使用されている場合、コマンドレットでセキュリティ制限をオーバーライドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="31db4-133">The cmdlet cannot override security restrictions when this parameter is used.</span></span>

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

### <span data-ttu-id="31db4-134">-IncludeInvocationHeader</span><span class="sxs-lookup"><span data-stu-id="31db4-134">-IncludeInvocationHeader</span></span>

<span data-ttu-id="31db4-135">コマンドの実行時に、このコマンドレットによってタイムスタンプがログに記録されることを示します。</span><span class="sxs-lookup"><span data-stu-id="31db4-135">Indicates that this cmdlet logs the time stamp when commands are run.</span></span>

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

### <span data-ttu-id="31db4-136">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="31db4-136">-LiteralPath</span></span>

<span data-ttu-id="31db4-137">トランスクリプトファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="31db4-137">Specifies a location to the transcript file.</span></span> <span data-ttu-id="31db4-138">**Path** パラメーターと異なり、**LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="31db4-138">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="31db4-139">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="31db4-139">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="31db4-140">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="31db4-140">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="31db4-141">単一引用符は、文字をエスケープシーケンスとして解釈しないことを PowerShell に伝えます。</span><span class="sxs-lookup"><span data-stu-id="31db4-141">Single quotation marks inform PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31db4-142">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="31db4-142">-NoClobber</span></span>

<span data-ttu-id="31db4-143">このコマンドレットが既存のファイルを上書きしないことを示します。</span><span class="sxs-lookup"><span data-stu-id="31db4-143">Indicates that this cmdlet will not overwrite of an existing file.</span></span> <span data-ttu-id="31db4-144">既定では、指定されたパスにトランスクリプトファイルが存在する場合、は `Start-Transcript` 警告なしにファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="31db4-144">By default, if a transcript file exists in the specified path, `Start-Transcript` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="31db4-145">-OutputDirectory</span><span class="sxs-lookup"><span data-stu-id="31db4-145">-OutputDirectory</span></span>

<span data-ttu-id="31db4-146">トランスクリプトを保存する特定のパスとフォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="31db4-146">Specifies a specific path and folder in which to save a transcript.</span></span> <span data-ttu-id="31db4-147">PowerShell では、トランスクリプト名が自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="31db4-147">PowerShell automatically assigns the transcript name.</span></span>

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

### <span data-ttu-id="31db4-148">-Path</span><span class="sxs-lookup"><span data-stu-id="31db4-148">-Path</span></span>

<span data-ttu-id="31db4-149">トランスクリプトファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="31db4-149">Specifies a location to the transcript file.</span></span> <span data-ttu-id="31db4-150">ファイルへのパスを入力 `.txt` します。</span><span class="sxs-lookup"><span data-stu-id="31db4-150">Enter a path to a `.txt` file.</span></span> <span data-ttu-id="31db4-151">ワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="31db4-151">Wildcards are not permitted.</span></span>

<span data-ttu-id="31db4-152">パスを指定しない場合、は `Start-Transcript` グローバル変数の値のパスを使用し `$Transcript` ます。</span><span class="sxs-lookup"><span data-stu-id="31db4-152">If you do not specify a path, `Start-Transcript` uses the path in the value of the `$Transcript` global variable.</span></span> <span data-ttu-id="31db4-153">この変数を作成していない場合は、によって `Start-Transcript` ファイルにトランスクリプトが格納され `$Home\My Documents directory as \PowerShell_transcript.<time-stamp>.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="31db4-153">If you have not created this variable, `Start-Transcript` stores the transcripts in the `$Home\My Documents directory as \PowerShell_transcript.<time-stamp>.txt` files.</span></span>

<span data-ttu-id="31db4-154">パス内のいずれかのディレクトリが存在しない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="31db4-154">If any of the directories in the path do not exist, the command fails.</span></span>

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

### <span data-ttu-id="31db4-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="31db4-155">-Confirm</span></span>

<span data-ttu-id="31db4-156">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="31db4-156">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="31db4-157">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="31db4-157">-WhatIf</span></span>

<span data-ttu-id="31db4-158">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="31db4-158">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="31db4-159">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="31db4-159">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="31db4-160">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="31db4-160">CommonParameters</span></span>

<span data-ttu-id="31db4-161">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="31db4-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="31db4-162">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31db4-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="31db4-163">入力</span><span class="sxs-lookup"><span data-stu-id="31db4-163">Inputs</span></span>

### <span data-ttu-id="31db4-164">なし</span><span class="sxs-lookup"><span data-stu-id="31db4-164">None</span></span>

<span data-ttu-id="31db4-165">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="31db4-165">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="31db4-166">出力</span><span class="sxs-lookup"><span data-stu-id="31db4-166">Outputs</span></span>

### <span data-ttu-id="31db4-167">System.String</span><span class="sxs-lookup"><span data-stu-id="31db4-167">System.String</span></span>

<span data-ttu-id="31db4-168">このコマンドレットは、確認メッセージと出力ファイルへのパスを含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="31db4-168">This cmdlet returns a string that contains a confirmation message and the path to the output file.</span></span>

## <span data-ttu-id="31db4-169">注</span><span class="sxs-lookup"><span data-stu-id="31db4-169">Notes</span></span>

<span data-ttu-id="31db4-170">トランスクリプトを停止するには、コマンドレットを使用し `Stop-Transcript` ます。</span><span class="sxs-lookup"><span data-stu-id="31db4-170">To stop a transcript, use the `Stop-Transcript` cmdlet.</span></span>

<span data-ttu-id="31db4-171">セッション全体を記録するには、 `Start-Transcript` プロファイルにコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="31db4-171">To record an entire session, add the `Start-Transcript` command to your profile.</span></span> <span data-ttu-id="31db4-172">詳細については、「 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31db4-172">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

## <span data-ttu-id="31db4-173">関連リンク</span><span class="sxs-lookup"><span data-stu-id="31db4-173">Related Links</span></span>

[<span data-ttu-id="31db4-174">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="31db4-174">Stop-Transcript</span></span>](Stop-Transcript.md)
