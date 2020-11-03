---
external help file: PSDiagnostics-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/start-trace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Trace
ms.openlocfilehash: b0fd03a62be21736a5d30e8ed4760dba300258ce
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212179"
---
# <span data-ttu-id="e2cd6-103">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="e2cd6-103">Start-Trace</span></span>

## <span data-ttu-id="e2cd6-104">概要</span><span class="sxs-lookup"><span data-stu-id="e2cd6-104">SYNOPSIS</span></span>
<span data-ttu-id="e2cd6-105">イベントトレースログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-105">Start an Event Trace logging session.</span></span>

## <span data-ttu-id="e2cd6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e2cd6-106">SYNTAX</span></span>

```
Start-Trace [-SessionName] <String> [[-OutputFilePath] <String>] [[-ProviderFilePath] <String>]
 [-ETS] [-Format <String>] [-MinBuffers <Int32>] [-MaxBuffers <Int32>]
 [-BufferSizeInKB <Int32>] [-MaxLogFileSizeInMB <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="e2cd6-107">Description</span><span class="sxs-lookup"><span data-stu-id="e2cd6-107">DESCRIPTION</span></span>
<span data-ttu-id="e2cd6-108">このコマンドレットは、Windows イベントトレースログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-108">This cmdlet starts a Windows Event Trace logging session.</span></span>

<span data-ttu-id="e2cd6-109">このコマンドレットは、次のコマンドレットによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-109">This cmdlet is used by the following cmdlets:</span></span>

- `Enable-PSWSManCombinedTrace`
- `Enable-WSManTrace`

<span data-ttu-id="e2cd6-110">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="e2cd6-111">例</span><span class="sxs-lookup"><span data-stu-id="e2cd6-111">EXAMPLES</span></span>

### <span data-ttu-id="e2cd6-112">例 1: WSMan トレースログセッションを開始する</span><span class="sxs-lookup"><span data-stu-id="e2cd6-112">Example 1: Start a WSMan Trace logging session</span></span>

```powershell
Start-Trace -SessionName 'wsmlog' -ETS -OutputFilePath "$env:windir\system32\wsmtraces.log" -Format 'bincirc' -MinBuffers 16 -MaxBuffers 256 -BufferSizeInKb 64 -MaxLogFileSizeInMB 256 -ProviderFilePath "$env:windir\system32\wsmtraceproviders.txt"
```

## <span data-ttu-id="e2cd6-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e2cd6-113">PARAMETERS</span></span>

### <span data-ttu-id="e2cd6-114">-BufferSizeInKB</span><span class="sxs-lookup"><span data-stu-id="e2cd6-114">-BufferSizeInKB</span></span>
<span data-ttu-id="e2cd6-115">イベントトレースセッションのバッファーサイズ (KB)。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-115">Event Trace Session buffer size in kilobytes (KB).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e2cd6-116">-/</span><span class="sxs-lookup"><span data-stu-id="e2cd6-116">-ETS</span></span>
<span data-ttu-id="e2cd6-117">イベントを保存またはスケジュールせずに直接イベントトレースセッションに送信します。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-117">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="e2cd6-118">-形式</span><span class="sxs-lookup"><span data-stu-id="e2cd6-118">-Format</span></span>
<span data-ttu-id="e2cd6-119">データコレクターのログの形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-119">Specifies the log format for the data collector.</span></span> <span data-ttu-id="e2cd6-120">SQL database 形式の場合は、コマンドラインで値を指定して **Outputfilepath** オプションを使用する必要があり `dsn!log` ます。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-120">For SQL database format, you must use the **OutputFilePath** option in the command line with the `dsn!log` value.</span></span> <span data-ttu-id="e2cd6-121">既定値は binary (bin) です。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-121">The default is binary (bin).</span></span> <span data-ttu-id="e2cd6-122">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-122">The possible values are:</span></span>

- <span data-ttu-id="e2cd6-123">ビン-バイナリ</span><span class="sxs-lookup"><span data-stu-id="e2cd6-123">bin - binary</span></span>
- <span data-ttu-id="e2cd6-124">ビン circ-バイナリと循環ログ</span><span class="sxs-lookup"><span data-stu-id="e2cd6-124">bincirc - binary with circular logging</span></span>
- <span data-ttu-id="e2cd6-125">csv-コンマ区切り値</span><span class="sxs-lookup"><span data-stu-id="e2cd6-125">csv - Comma-separated values</span></span>
- <span data-ttu-id="e2cd6-126">tsv-タブ区切り値</span><span class="sxs-lookup"><span data-stu-id="e2cd6-126">tsv - Tab-separated values</span></span>
- <span data-ttu-id="e2cd6-127">sql-SQL データベース</span><span class="sxs-lookup"><span data-stu-id="e2cd6-127">sql - SQL database</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:
Accepted values: bin, bincirc, csv, tsv, sql

Required: False
Position: Named
Default value: bin
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e2cd6-128">-MaxBuffers</span><span class="sxs-lookup"><span data-stu-id="e2cd6-128">-MaxBuffers</span></span>
<span data-ttu-id="e2cd6-129">イベントトレースセッションバッファーの最大数を設定します。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-129">Sets the maximum number of Event Trace Session buffers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 256
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e2cd6-130">-MaxLogFileSizeInMB</span><span class="sxs-lookup"><span data-stu-id="e2cd6-130">-MaxLogFileSizeInMB</span></span>
<span data-ttu-id="e2cd6-131">SQL ログのログファイルの最大サイズ (MB) またはレコード数を設定します。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-131">Sets the maximum log file size in megabytes (MB) or number of records for SQL logs.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0 (no limit)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e2cd6-132">-MinBuffers</span><span class="sxs-lookup"><span data-stu-id="e2cd6-132">-MinBuffers</span></span>
<span data-ttu-id="e2cd6-133">イベントトレースセッションバッファーの最小数を設定します。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-133">Sets the minimum number of Event Trace Session buffers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e2cd6-134">-OutputFilePath</span><span class="sxs-lookup"><span data-stu-id="e2cd6-134">-OutputFilePath</span></span>
<span data-ttu-id="e2cd6-135">出力ログファイルのパス、または SQL データベースの DSN とログセット名。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-135">Path of the output log file or the DSN and log set name in a SQL database.</span></span> <span data-ttu-id="e2cd6-136">既定のパスは、`$env:systemdrive\PerfLogs\Admin` です。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-136">The default path is `$env:systemdrive\PerfLogs\Admin`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: $env:systemdrive\PerfLogs\Admin
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e2cd6-137">-ProviderFilePath</span><span class="sxs-lookup"><span data-stu-id="e2cd6-137">-ProviderFilePath</span></span>
<span data-ttu-id="e2cd6-138">有効にする複数のイベントトレースプロバイダーを一覧表示するファイルです。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-138">File listing multiple Event Trace providers to enable.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e2cd6-139">-セッション名</span><span class="sxs-lookup"><span data-stu-id="e2cd6-139">-SessionName</span></span>
<span data-ttu-id="e2cd6-140">イベントトレースセッションの名前。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-140">The name of the Event Trace session.</span></span> <span data-ttu-id="e2cd6-141">トレースセッションを停止するには、セッション名を把握している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-141">To stop a trace session you must know the session name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e2cd6-142">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e2cd6-142">CommonParameters</span></span>

<span data-ttu-id="e2cd6-143">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e2cd6-144">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2cd6-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e2cd6-145">入力</span><span class="sxs-lookup"><span data-stu-id="e2cd6-145">INPUTS</span></span>

### <span data-ttu-id="e2cd6-146">なし</span><span class="sxs-lookup"><span data-stu-id="e2cd6-146">None</span></span>

## <span data-ttu-id="e2cd6-147">出力</span><span class="sxs-lookup"><span data-stu-id="e2cd6-147">OUTPUTS</span></span>

### <span data-ttu-id="e2cd6-148">なし</span><span class="sxs-lookup"><span data-stu-id="e2cd6-148">None</span></span>

## <span data-ttu-id="e2cd6-149">注</span><span class="sxs-lookup"><span data-stu-id="e2cd6-149">NOTES</span></span>

## <span data-ttu-id="e2cd6-150">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e2cd6-150">RELATED LINKS</span></span>

[<span data-ttu-id="e2cd6-151">イベントのトレース</span><span class="sxs-lookup"><span data-stu-id="e2cd6-151">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="e2cd6-152">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="e2cd6-152">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="e2cd6-153">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="e2cd6-153">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="e2cd6-154">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="e2cd6-154">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="e2cd6-155">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="e2cd6-155">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="e2cd6-156">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="e2cd6-156">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
