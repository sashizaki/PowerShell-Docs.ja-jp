---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/start-trace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Trace
ms.openlocfilehash: b1c6a596f3dc35028b928c3a6b5459a805bc2512
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600796"
---
# <span data-ttu-id="6abfa-102">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="6abfa-102">Start-Trace</span></span>

## <span data-ttu-id="6abfa-103">概要</span><span class="sxs-lookup"><span data-stu-id="6abfa-103">SYNOPSIS</span></span>
<span data-ttu-id="6abfa-104">イベントトレースログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="6abfa-104">Start an Event Trace logging session.</span></span>

## <span data-ttu-id="6abfa-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6abfa-105">SYNTAX</span></span>

```
Start-Trace [-SessionName] <String> [[-OutputFilePath] <String>] [[-ProviderFilePath] <String>]
 [-ETS] [-Format <String>] [-MinBuffers <Int32>] [-MaxBuffers <Int32>]
 [-BufferSizeInKB <Int32>] [-MaxLogFileSizeInMB <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="6abfa-106">Description</span><span class="sxs-lookup"><span data-stu-id="6abfa-106">DESCRIPTION</span></span>
<span data-ttu-id="6abfa-107">このコマンドレットは、Windows イベントトレースログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="6abfa-107">This cmdlet starts a Windows Event Trace logging session.</span></span>

<span data-ttu-id="6abfa-108">このコマンドレットは、次のコマンドレットによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="6abfa-108">This cmdlet is used by the following cmdlets:</span></span>

- `Enable-PSWSManCombinedTrace`
- `Enable-WSManTrace`

<span data-ttu-id="6abfa-109">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6abfa-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="6abfa-110">例</span><span class="sxs-lookup"><span data-stu-id="6abfa-110">EXAMPLES</span></span>

### <span data-ttu-id="6abfa-111">例 1: WSMan トレースログセッションを開始する</span><span class="sxs-lookup"><span data-stu-id="6abfa-111">Example 1: Start a WSMan Trace logging session</span></span>

```powershell
Start-Trace -SessionName 'wsmlog' -ETS -OutputFilePath "$env:windir\system32\wsmtraces.log" -Format 'bincirc' -MinBuffers 16 -MaxBuffers 256 -BufferSizeInKb 64 -MaxLogFileSizeInMB 256 -ProviderFilePath "$env:windir\system32\wsmtraceproviders.txt"
```

## <span data-ttu-id="6abfa-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6abfa-112">PARAMETERS</span></span>

### <span data-ttu-id="6abfa-113">-BufferSizeInKB</span><span class="sxs-lookup"><span data-stu-id="6abfa-113">-BufferSizeInKB</span></span>
<span data-ttu-id="6abfa-114">イベントトレースセッションのバッファーサイズ (KB)。</span><span class="sxs-lookup"><span data-stu-id="6abfa-114">Event Trace Session buffer size in kilobytes (KB).</span></span>

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

### <span data-ttu-id="6abfa-115">-/</span><span class="sxs-lookup"><span data-stu-id="6abfa-115">-ETS</span></span>
<span data-ttu-id="6abfa-116">イベントを保存またはスケジュールせずに直接イベントトレースセッションに送信します。</span><span class="sxs-lookup"><span data-stu-id="6abfa-116">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="6abfa-117">-形式</span><span class="sxs-lookup"><span data-stu-id="6abfa-117">-Format</span></span>
<span data-ttu-id="6abfa-118">データコレクターのログの形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="6abfa-118">Specifies the log format for the data collector.</span></span> <span data-ttu-id="6abfa-119">SQL database 形式の場合は、コマンドラインで値を指定して **Outputfilepath** オプションを使用する必要があり `dsn!log` ます。</span><span class="sxs-lookup"><span data-stu-id="6abfa-119">For SQL database format, you must use the **OutputFilePath** option in the command line with the `dsn!log` value.</span></span> <span data-ttu-id="6abfa-120">既定値は binary (bin) です。</span><span class="sxs-lookup"><span data-stu-id="6abfa-120">The default is binary (bin).</span></span> <span data-ttu-id="6abfa-121">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6abfa-121">The possible values are:</span></span>

- <span data-ttu-id="6abfa-122">ビン-バイナリ</span><span class="sxs-lookup"><span data-stu-id="6abfa-122">bin - binary</span></span>
- <span data-ttu-id="6abfa-123">ビン circ-バイナリと循環ログ</span><span class="sxs-lookup"><span data-stu-id="6abfa-123">bincirc - binary with circular logging</span></span>
- <span data-ttu-id="6abfa-124">csv-コンマ区切り値</span><span class="sxs-lookup"><span data-stu-id="6abfa-124">csv - Comma-separated values</span></span>
- <span data-ttu-id="6abfa-125">tsv-タブ区切り値</span><span class="sxs-lookup"><span data-stu-id="6abfa-125">tsv - Tab-separated values</span></span>
- <span data-ttu-id="6abfa-126">sql-SQL データベース</span><span class="sxs-lookup"><span data-stu-id="6abfa-126">sql - SQL database</span></span>

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

### <span data-ttu-id="6abfa-127">-MaxBuffers</span><span class="sxs-lookup"><span data-stu-id="6abfa-127">-MaxBuffers</span></span>
<span data-ttu-id="6abfa-128">イベントトレースセッションバッファーの最大数を設定します。</span><span class="sxs-lookup"><span data-stu-id="6abfa-128">Sets the maximum number of Event Trace Session buffers.</span></span>

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

### <span data-ttu-id="6abfa-129">-MaxLogFileSizeInMB</span><span class="sxs-lookup"><span data-stu-id="6abfa-129">-MaxLogFileSizeInMB</span></span>
<span data-ttu-id="6abfa-130">SQL ログのログファイルの最大サイズ (MB) またはレコード数を設定します。</span><span class="sxs-lookup"><span data-stu-id="6abfa-130">Sets the maximum log file size in megabytes (MB) or number of records for SQL logs.</span></span>

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

### <span data-ttu-id="6abfa-131">-MinBuffers</span><span class="sxs-lookup"><span data-stu-id="6abfa-131">-MinBuffers</span></span>
<span data-ttu-id="6abfa-132">イベントトレースセッションバッファーの最小数を設定します。</span><span class="sxs-lookup"><span data-stu-id="6abfa-132">Sets the minimum number of Event Trace Session buffers.</span></span>

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

### <span data-ttu-id="6abfa-133">-OutputFilePath</span><span class="sxs-lookup"><span data-stu-id="6abfa-133">-OutputFilePath</span></span>
<span data-ttu-id="6abfa-134">出力ログファイルのパス、または SQL データベースの DSN とログセット名。</span><span class="sxs-lookup"><span data-stu-id="6abfa-134">Path of the output log file or the DSN and log set name in a SQL database.</span></span> <span data-ttu-id="6abfa-135">既定のパスは、`$env:systemdrive\PerfLogs\Admin` です。</span><span class="sxs-lookup"><span data-stu-id="6abfa-135">The default path is `$env:systemdrive\PerfLogs\Admin`.</span></span>

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

### <span data-ttu-id="6abfa-136">-ProviderFilePath</span><span class="sxs-lookup"><span data-stu-id="6abfa-136">-ProviderFilePath</span></span>
<span data-ttu-id="6abfa-137">有効にする複数のイベントトレースプロバイダーを一覧表示するファイルです。</span><span class="sxs-lookup"><span data-stu-id="6abfa-137">File listing multiple Event Trace providers to enable.</span></span>

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

### <span data-ttu-id="6abfa-138">-セッション名</span><span class="sxs-lookup"><span data-stu-id="6abfa-138">-SessionName</span></span>
<span data-ttu-id="6abfa-139">イベントトレースセッションの名前。</span><span class="sxs-lookup"><span data-stu-id="6abfa-139">The name of the Event Trace session.</span></span> <span data-ttu-id="6abfa-140">トレースセッションを停止するには、セッション名を把握している必要があります。</span><span class="sxs-lookup"><span data-stu-id="6abfa-140">To stop a trace session you must know the session name.</span></span>

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

### <span data-ttu-id="6abfa-141">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6abfa-141">CommonParameters</span></span>

<span data-ttu-id="6abfa-142">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6abfa-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6abfa-143">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abfa-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6abfa-144">入力</span><span class="sxs-lookup"><span data-stu-id="6abfa-144">INPUTS</span></span>

### <span data-ttu-id="6abfa-145">なし</span><span class="sxs-lookup"><span data-stu-id="6abfa-145">None</span></span>

## <span data-ttu-id="6abfa-146">出力</span><span class="sxs-lookup"><span data-stu-id="6abfa-146">OUTPUTS</span></span>

### <span data-ttu-id="6abfa-147">なし</span><span class="sxs-lookup"><span data-stu-id="6abfa-147">None</span></span>

## <span data-ttu-id="6abfa-148">注</span><span class="sxs-lookup"><span data-stu-id="6abfa-148">NOTES</span></span>

## <span data-ttu-id="6abfa-149">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6abfa-149">RELATED LINKS</span></span>

[<span data-ttu-id="6abfa-150">イベントのトレース</span><span class="sxs-lookup"><span data-stu-id="6abfa-150">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="6abfa-151">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="6abfa-151">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="6abfa-152">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="6abfa-152">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="6abfa-153">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="6abfa-153">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="6abfa-154">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="6abfa-154">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="6abfa-155">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="6abfa-155">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

