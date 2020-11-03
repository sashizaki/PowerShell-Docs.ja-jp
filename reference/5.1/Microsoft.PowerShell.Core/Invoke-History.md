---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-history?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-History
ms.openlocfilehash: 613b460678186380b518a0bc04abc426c1038a84
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211984"
---
# <span data-ttu-id="2eb56-103">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="2eb56-103">Invoke-History</span></span>

## <span data-ttu-id="2eb56-104">概要</span><span class="sxs-lookup"><span data-stu-id="2eb56-104">SYNOPSIS</span></span>
<span data-ttu-id="2eb56-105">セッションの履歴からコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-105">Runs commands from the session history.</span></span>

## <span data-ttu-id="2eb56-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2eb56-106">SYNTAX</span></span>

```
Invoke-History [[-Id] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2eb56-107">Description</span><span class="sxs-lookup"><span data-stu-id="2eb56-107">DESCRIPTION</span></span>

<span data-ttu-id="2eb56-108">コマンド `Invoke-History` レットは、セッションの履歴からコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-108">The `Invoke-History` cmdlet runs commands from the session history.</span></span> <span data-ttu-id="2eb56-109">コマンドを表すオブジェクトを Get-History からに渡すことも `Invoke-History` 、 **Id** 番号を使用して現在の履歴内のコマンドを特定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2eb56-109">You can pass objects representing the commands from Get-History to `Invoke-History`, or you can identify commands in the current history by using their **Id** number.</span></span> <span data-ttu-id="2eb56-110">コマンドの識別番号を調べるには、コマンドレットを使用し `Get-History` ます。</span><span class="sxs-lookup"><span data-stu-id="2eb56-110">To find the identification number of a command, use the `Get-History` cmdlet.</span></span>

<span data-ttu-id="2eb56-111">セッション履歴は、 **Psreadline** モジュールによって保持されている履歴とは別に管理されます。</span><span class="sxs-lookup"><span data-stu-id="2eb56-111">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="2eb56-112">どちらの履歴も、 **Psreadline** が読み込まれたセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2eb56-112">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="2eb56-113">このコマンドレットは、セッション履歴でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-113">This cmdlet only works with the session history.</span></span> <span data-ttu-id="2eb56-114">詳細については、「」、「 [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eb56-114">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="2eb56-115">例</span><span class="sxs-lookup"><span data-stu-id="2eb56-115">EXAMPLES</span></span>

### <span data-ttu-id="2eb56-116">例 1: 履歴で最新のコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="2eb56-116">Example 1: Run the most recent command in the history</span></span>

<span data-ttu-id="2eb56-117">この例では、セッション履歴の最後のコマンド、または最新のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-117">This example runs the last, or most recent, command in the session history.</span></span> <span data-ttu-id="2eb56-118">このコマンドは `r` 、のエイリアスであるとして省略でき `Invoke-History` ます。</span><span class="sxs-lookup"><span data-stu-id="2eb56-118">You can abbreviate this command as `r`, the alias for `Invoke-History`.</span></span>

```powershell
Invoke-History
```

### <span data-ttu-id="2eb56-119">例 2: 指定した ID を持つコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="2eb56-119">Example 2: Run the command that has a specified ID</span></span>

<span data-ttu-id="2eb56-120">この例では、 **Id** 132 のセッション履歴でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-120">This example runs the command in the session history with **Id** 132.</span></span> <span data-ttu-id="2eb56-121">**Id** パラメーターの名前は省略可能であるため、このコマンドは `Invoke-History 132` 、、 `ihy 132` 、またはのように省略できます `r 132` 。</span><span class="sxs-lookup"><span data-stu-id="2eb56-121">Because the name of the **Id** parameter is optional, you can abbreviate this command as the following: `Invoke-History 132`, `ihy 132`, or `r 132`.</span></span>

```powershell
Invoke-History -Id 132
```

### <span data-ttu-id="2eb56-122">例 3: コマンドテキストを使用して最新のコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="2eb56-122">Example 3: Run the most recent command by using the command text</span></span>

<span data-ttu-id="2eb56-123">この例では、セッション履歴の最新のコマンドを実行し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="2eb56-123">This example runs the most recent `Get-Process` command in the session history.</span></span> <span data-ttu-id="2eb56-124">**Id** パラメーターに文字を入力すると、は、 `Invoke-History` 最後のコマンドで始まるパターンに一致する最初のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-124">When you type characters for the **Id** parameter, `Invoke-History` runs the first command that it finds that matches the pattern, starting with the most recent commands.</span></span>

```powershell
Invoke-History -Id get-pr
```

> [!NOTE]
> <span data-ttu-id="2eb56-125">パターンマッチングでは大文字と小文字が区別されませんが、パターンは行の先頭と一致します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-125">Pattern matching is case-insensitive, but the pattern matches the beginning of the line.</span></span>

### <span data-ttu-id="2eb56-126">例 4: 履歴から一連のコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="2eb56-126">Example 4: Run a sequence of commands from the history</span></span>

<span data-ttu-id="2eb56-127">この例では、16 ~ 24 のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-127">This example runs commands 16 through 24.</span></span> <span data-ttu-id="2eb56-128">**Id** 値は1つしか表示できないため、コマンドは、コマンドレットを使用して、 `ForEach-Object` `Invoke-History` 各 **id** 値に対してコマンドを1回実行します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-128">Because you can list only one **Id** value, the command uses the `ForEach-Object` cmdlet to run the `Invoke-History` command one time for each **Id** value.</span></span>

```powershell
16..24 | ForEach {Invoke-History -Id $_ }
```

### <span data-ttu-id="2eb56-129">例 5</span><span class="sxs-lookup"><span data-stu-id="2eb56-129">Example 5</span></span>

<span data-ttu-id="2eb56-130">この例では、コマンド 255 (249 ~ 255) で終わる、履歴内の7つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-130">This example runs the seven commands in the history that end with command 255 (249 through 255).</span></span> <span data-ttu-id="2eb56-131">`Get-History`コマンドレットを使用して、コマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-131">It uses the `Get-History` cmdlet to retrieve the commands.</span></span> <span data-ttu-id="2eb56-132">**Id** 値は1つしか表示できないため、コマンドは、コマンドレットを使用して、 `ForEach-Object` `Invoke-History` 各 **id** 値に対してコマンドを1回実行します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-132">Because you can list only one **Id** value, the command uses the `ForEach-Object` cmdlet to run the `Invoke-History` command once for each **Id** value.</span></span>

```powershell
Get-History -Id 255 -Count 7 | ForEach {Invoke-History -Id $_.Id}
```

## <span data-ttu-id="2eb56-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2eb56-133">PARAMETERS</span></span>

### <span data-ttu-id="2eb56-134">-Id</span><span class="sxs-lookup"><span data-stu-id="2eb56-134">-Id</span></span>

<span data-ttu-id="2eb56-135">履歴内のコマンドの **Id** を指定します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-135">Specifies the **Id** of a command in the history.</span></span> <span data-ttu-id="2eb56-136">コマンドの **Id** 番号、またはコマンドの最初のいくつかの文字を入力できます。</span><span class="sxs-lookup"><span data-stu-id="2eb56-136">You can type the **Id** number of the command or the first few characters of the command.</span></span>

<span data-ttu-id="2eb56-137">文字を入力すると、は `Invoke-History` 最新のコマンドと最初に一致します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-137">If you type characters, `Invoke-History` matches the most recent commands first.</span></span> <span data-ttu-id="2eb56-138">このパラメーターを省略すると、 `Invoke-History` は最後のコマンド、または最新のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-138">If you omit this parameter, `Invoke-History` runs the last, or most recent, command.</span></span> <span data-ttu-id="2eb56-139">コマンドの **Id** 番号を検索するには、コマンドレットを使用し `Get-History` ます。</span><span class="sxs-lookup"><span data-stu-id="2eb56-139">To find the **Id** number of a command, use the `Get-History` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2eb56-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2eb56-140">-Confirm</span></span>

<span data-ttu-id="2eb56-141">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2eb56-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2eb56-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2eb56-142">-WhatIf</span></span>

<span data-ttu-id="2eb56-143">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2eb56-144">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2eb56-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2eb56-145">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2eb56-145">CommonParameters</span></span>

<span data-ttu-id="2eb56-146">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2eb56-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2eb56-147">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eb56-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2eb56-148">入力</span><span class="sxs-lookup"><span data-stu-id="2eb56-148">INPUTS</span></span>

### <span data-ttu-id="2eb56-149">System.String</span><span class="sxs-lookup"><span data-stu-id="2eb56-149">System.String</span></span>

<span data-ttu-id="2eb56-150">このコマンドレットには、履歴 **Id** をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="2eb56-150">You can pipe a history **Id** to this cmdlet.</span></span>

## <span data-ttu-id="2eb56-151">出力</span><span class="sxs-lookup"><span data-stu-id="2eb56-151">OUTPUTS</span></span>

### <span data-ttu-id="2eb56-152">なし</span><span class="sxs-lookup"><span data-stu-id="2eb56-152">None</span></span>

<span data-ttu-id="2eb56-153">このコマンドレットは出力を生成しませんが、実行するコマンドによって出力が生成される場合があり `Invoke-History` ます。</span><span class="sxs-lookup"><span data-stu-id="2eb56-153">This cmdlet does not generate any output, but output might be generated by the commands that `Invoke-History` runs.</span></span>

## <span data-ttu-id="2eb56-154">注</span><span class="sxs-lookup"><span data-stu-id="2eb56-154">NOTES</span></span>

<span data-ttu-id="2eb56-155">セッション履歴は、セッション中に入力したコマンドの一覧です。</span><span class="sxs-lookup"><span data-stu-id="2eb56-155">The session history is a list of the commands entered during the session.</span></span> <span data-ttu-id="2eb56-156">セッション履歴は、実行の順序、状態、コマンドの開始時刻と終了時刻を表します。</span><span class="sxs-lookup"><span data-stu-id="2eb56-156">The session history represents the order of execution, the status, and the start and end times of the command.</span></span> <span data-ttu-id="2eb56-157">各コマンドを入力すると、PowerShell によってそのコマンドが履歴に追加され、再利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2eb56-157">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="2eb56-158">セッションの履歴の詳細については、「 [about_History](About/about_History.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eb56-158">For more information about the session history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="2eb56-159">また、組み込みのエイリアスであるとを参照することもでき `Invoke-History` `r` `ihy` ます。</span><span class="sxs-lookup"><span data-stu-id="2eb56-159">You can also refer to `Invoke-History` by its built-in aliases, `r` and `ihy`.</span></span> <span data-ttu-id="2eb56-160">詳細については、「 [about_Aliases](About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eb56-160">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>

## <span data-ttu-id="2eb56-161">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2eb56-161">RELATED LINKS</span></span>

[<span data-ttu-id="2eb56-162">Add-History</span><span class="sxs-lookup"><span data-stu-id="2eb56-162">Add-History</span></span>](Add-History.md)

[<span data-ttu-id="2eb56-163">Clear-History</span><span class="sxs-lookup"><span data-stu-id="2eb56-163">Clear-History</span></span>](Clear-History.md)

[<span data-ttu-id="2eb56-164">Get-History</span><span class="sxs-lookup"><span data-stu-id="2eb56-164">Get-History</span></span>](Get-History.md)
