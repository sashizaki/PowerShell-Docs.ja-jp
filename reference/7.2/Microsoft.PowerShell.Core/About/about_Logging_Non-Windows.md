---
description: PowerShell は、エンジン、プロバイダー、およびコマンドレットからの内部操作をログに記録します。
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logging_non-windows?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logging_Non-Windows
ms.openlocfilehash: e74e357d81eddf87ad27d023eb9a8ba2977156e9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600786"
---
# <a name="about-logging-non-windows"></a><span data-ttu-id="cfed6-103">Windows 以外のログ記録について</span><span class="sxs-lookup"><span data-stu-id="cfed6-103">About Logging Non-Windows</span></span>

## <a name="short-description"></a><span data-ttu-id="cfed6-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="cfed6-104">Short description</span></span>
<span data-ttu-id="cfed6-105">PowerShell は、エンジン、プロバイダー、およびコマンドレットからの内部操作をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-105">PowerShell logs internal operations from the engine, providers, and cmdlets.</span></span>

## <a name="long-description"></a><span data-ttu-id="cfed6-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="cfed6-106">Long description</span></span>

<span data-ttu-id="cfed6-107">Powershell は、PowerShell 操作の詳細をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-107">PowerShell logs details of PowerShell operations.</span></span> <span data-ttu-id="cfed6-108">たとえば、PowerShell では、エンジンの起動や停止、プロバイダーの開始と停止などの操作をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-108">For example, PowerShell will log operations such as starting and stopping the engine and starting and stopping providers.</span></span> <span data-ttu-id="cfed6-109">また、PowerShell コマンドに関する詳細もログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-109">It will also log details about PowerShell commands.</span></span>

<span data-ttu-id="cfed6-110">PowerShell ログの場所は、ターゲットプラットフォームに依存します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-110">The location of PowerShell logs is dependent on the target platform.</span></span> <span data-ttu-id="cfed6-111">**Linux** では、PowerShell ログを **syslog** と **rsyslog** に使用できます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-111">On **Linux**, PowerShell logs to **syslog** and **rsyslog.conf** can be used.</span></span> <span data-ttu-id="cfed6-112">詳細については、Linux コンピューターのローカルページを参照してください `man` 。</span><span class="sxs-lookup"><span data-stu-id="cfed6-112">For more information, refer to the Linux computer's local `man` pages.</span></span> <span data-ttu-id="cfed6-113">**MacOS** では、 **os_log** ログ記録システムが使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-113">On **macOS**, the **os_log** logging system is used.</span></span> <span data-ttu-id="cfed6-114">詳細については、 [os_log 開発者向けドキュメント](https://developer.apple.com/documentation/os/os_log)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfed6-114">For more information, see [os_log developer documentation](https://developer.apple.com/documentation/os/os_log).</span></span>

## <a name="viewing-powershell-log-output-on-linux"></a><span data-ttu-id="cfed6-115">Linux での PowerShell ログ出力の表示</span><span class="sxs-lookup"><span data-stu-id="cfed6-115">Viewing PowerShell log output on Linux</span></span>

<span data-ttu-id="cfed6-116">Linux の **syslog** の PowerShell ログと、 **syslog** の内容を表示するためによく使用されるすべてのツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-116">PowerShell logs to **syslog** on Linux and any of the tools commonly used to view **syslog** contents may be used.</span></span>

<span data-ttu-id="cfed6-117">ログエントリの形式は、次のテンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-117">The format of the log entries uses the following template:</span></span>

```
TIMESTAMP MACHINENAME powershell[PID]: (COMMITID:TID:CID)
  [EVENTID:TASK.OPCODE.LEVEL] MESSAGE
```

|<span data-ttu-id="cfed6-118">フィールド</span><span class="sxs-lookup"><span data-stu-id="cfed6-118">Field</span></span>        |<span data-ttu-id="cfed6-119">説明</span><span class="sxs-lookup"><span data-stu-id="cfed6-119">Description</span></span>                                             |
|-------------|--------------------------------------------------------|
|`TIMESTAMP`  |<span data-ttu-id="cfed6-120">ログエントリが生成された日付/時刻。</span><span class="sxs-lookup"><span data-stu-id="cfed6-120">A date/time when the log entry was produced.</span></span>            |
|`MACHINENAME`|<span data-ttu-id="cfed6-121">ログが生成されたシステムの名前。</span><span class="sxs-lookup"><span data-stu-id="cfed6-121">The name of the system where the log was produced.</span></span>      |
|`PID`        |<span data-ttu-id="cfed6-122">ログエントリを作成したプロセスのプロセス ID。</span><span class="sxs-lookup"><span data-stu-id="cfed6-122">The process ID of the process that wrote the log entry.</span></span> |
|`COMMITID`   |<span data-ttu-id="cfed6-123">`git commit`ビルドの生成に使用される ID またはタグ。</span><span class="sxs-lookup"><span data-stu-id="cfed6-123">The `git commit` ID or tag used to produce the build.</span></span>   |
|`TID`        |<span data-ttu-id="cfed6-124">ログエントリを書き込んだスレッドのスレッド ID。</span><span class="sxs-lookup"><span data-stu-id="cfed6-124">The thread ID of the thread that wrote the log entry.</span></span>   |
|`CID`        |<span data-ttu-id="cfed6-125">ログエントリの16進チャネル識別子。</span><span class="sxs-lookup"><span data-stu-id="cfed6-125">The hex channel identifier of the log entry.</span></span>            |
|             |<span data-ttu-id="cfed6-126">10 = 運用、11 = 分析</span><span class="sxs-lookup"><span data-stu-id="cfed6-126">10 = Operational, 11 = Analytic</span></span>                         |
|`EVENTID`    |<span data-ttu-id="cfed6-127">ログエントリのイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="cfed6-127">The event identifier of the log entry.</span></span>                  |
|`TASK`       |<span data-ttu-id="cfed6-128">イベントエントリのタスク識別子</span><span class="sxs-lookup"><span data-stu-id="cfed6-128">The task identifier for the event entry</span></span>                 |
|`OPCODE`     |<span data-ttu-id="cfed6-129">イベントエントリのオペコード</span><span class="sxs-lookup"><span data-stu-id="cfed6-129">The opcode for the event entry</span></span>                          |
|`LEVEL`      |<span data-ttu-id="cfed6-130">イベントエントリのログレベル</span><span class="sxs-lookup"><span data-stu-id="cfed6-130">The log level for the event entry</span></span>                       |
|`MESSAGE`    |<span data-ttu-id="cfed6-131">イベントエントリに関連付けられているメッセージ</span><span class="sxs-lookup"><span data-stu-id="cfed6-131">The message associated with the event entry</span></span>             |

> [!NOTE]
> <span data-ttu-id="cfed6-132">`EVENTID`、 `TASK` 、 `OPCODE` 、および `LEVEL` は、Windows イベントログへのログ記録時に使用される値と同じです。</span><span class="sxs-lookup"><span data-stu-id="cfed6-132">`EVENTID`, `TASK`, `OPCODE`, and `LEVEL` are the same values as used when logging to the Windows event log.</span></span>

### <a name="filtering-powershell-log-entries-using-rsyslog"></a><span data-ttu-id="cfed6-133">Rsyslog を使用して PowerShell ログエントリをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="cfed6-133">Filtering PowerShell log entries using rsyslog</span></span>

<span data-ttu-id="cfed6-134">通常、PowerShell ログエントリは、syslog の既定値に書き込まれ `location/file` ます。 </span><span class="sxs-lookup"><span data-stu-id="cfed6-134">Normally, PowerShell log entries are written to the default `location/file` for **syslog**.</span></span> <span data-ttu-id="cfed6-135">ただし、エントリをカスタムファイルにリダイレクトすることはできます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-135">However, it's possible to redirect the entries to a custom file.</span></span>

1. <span data-ttu-id="cfed6-136">PowerShell ログ構成の conf を作成し、のように 50 (の場合) 未満の数値を指定し `50-default.conf` `40-powershell.conf` ます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-136">Create a conf for PowerShell log configuration and provide a number that's less than 50 (for `50-default.conf`), such as `40-powershell.conf`.</span></span> <span data-ttu-id="cfed6-137">ファイルは、の下に配置する必要があり `/etc/rsyslog.d` ます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-137">The file should be placed under `/etc/rsyslog.d`.</span></span>

1. <span data-ttu-id="cfed6-138">次のエントリをファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-138">Add the following entry to the file:</span></span>

   ```
   :syslogtag, contains, "powershell[" /var/log/powershell.log
   & stop
   ```

1. <span data-ttu-id="cfed6-139">に新しいファイルが含まれていることを確認してください `/etc/rsyslog.conf` 。</span><span class="sxs-lookup"><span data-stu-id="cfed6-139">Make sure `/etc/rsyslog.conf` includes the new file.</span></span> <span data-ttu-id="cfed6-140">多くの場合、次のような一般的なインクルードステートメントがあります。</span><span class="sxs-lookup"><span data-stu-id="cfed6-140">Often, it will have a generic include statement that looks like following configuration:</span></span>

   `$IncludeConfig /etc/rsyslog.d/*.conf`

   <span data-ttu-id="cfed6-141">そうでない場合は、include ステートメントを手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfed6-141">If it doesn't, you'll need to add an include statement manually.</span></span>

1. <span data-ttu-id="cfed6-142">属性と権限が適切に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-142">Make sure attributes and permissions are set appropriately.</span></span>

   ```
   -rw-r--r-- 1 root root   67 Nov 28 12:51 40-powershell.conf
   ```

1. <span data-ttu-id="cfed6-143">所有権を **ルート** に設定します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-143">Set ownership to **root**.</span></span>

   ```
   chown root:root /etc/rsyslog.d/40-powershell.conf
   ```

1. <span data-ttu-id="cfed6-144">アクセス許可の設定: **ルート** に読み取り/書き込みがあり、 **ユーザー** が読み取りました。</span><span class="sxs-lookup"><span data-stu-id="cfed6-144">Set access permissions: **root** has read/write, **users** have read.</span></span>

   ```
   chmod 644 /etc/rsyslog.d/40-powershell.conf
   ```

## <a name="viewing-powershell-log-output-on-macos"></a><span data-ttu-id="cfed6-145">MacOS での PowerShell ログ出力の表示</span><span class="sxs-lookup"><span data-stu-id="cfed6-145">Viewing PowerShell log output on macOS</span></span>

<span data-ttu-id="cfed6-146">MacOS で PowerShell ログ出力を表示する最も簡単な方法は、 **コンソール** アプリケーションを使用することです。</span><span class="sxs-lookup"><span data-stu-id="cfed6-146">The easiest method for viewing PowerShell log output on macOS is using the **Console** application.</span></span>

1. <span data-ttu-id="cfed6-147">**コンソール** アプリケーションを検索して起動します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-147">Search for the **Console** application and launch it.</span></span>
1. <span data-ttu-id="cfed6-148">[ **デバイス**] でコンピューター名を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-148">Select the Machine name under **Devices**.</span></span>
1. <span data-ttu-id="cfed6-149">**検索** フィールドに、 `pwsh` PowerShell のメインバイナリとして「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-149">In the **Search** field, enter `pwsh` for the PowerShell main binary.</span></span>
1. <span data-ttu-id="cfed6-150">検索フィルターをからに変更し `Any` `Process` ます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-150">Change the search filter from `Any` to `Process`.</span></span>
1. <span data-ttu-id="cfed6-151">操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-151">Perform the operations.</span></span>
1. <span data-ttu-id="cfed6-152">必要に応じて、後で使用するために検索を保存します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-152">Optionally, save the search for future use.</span></span>

<span data-ttu-id="cfed6-153">**コンソール** で PowerShell の特定のプロセスインスタンスをフィルター処理するには、変数に `$pid` プロセス ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cfed6-153">To filter on a specific process instance of PowerShell in the **Console**, the variable `$pid` contains the process ID.</span></span>

1. <span data-ttu-id="cfed6-154">**検索** フィールドに **PID** (プロセス ID) を入力します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-154">Enter the **pid** (Process ID) in the **Search** field.</span></span>
1. <span data-ttu-id="cfed6-155">検索フィルターをに変更し `PID` ます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-155">Change the search filter to `PID`.</span></span>
1. <span data-ttu-id="cfed6-156">操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-156">Perform the operations.</span></span>

### <a name="viewing-powershell-log-output-from-a-command-line"></a><span data-ttu-id="cfed6-157">コマンドラインからの PowerShell ログ出力の表示</span><span class="sxs-lookup"><span data-stu-id="cfed6-157">Viewing PowerShell log output from a command line</span></span>

<span data-ttu-id="cfed6-158">コマンドは、 `log` コマンドラインから PowerShell ログエントリを表示するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-158">The `log` command can be used to view PowerShell log entries from the command line.</span></span>

```
sudo log stream --predicate 'process == "pwsh"' --info
```

### <a name="persisting-powershell-log-output"></a><span data-ttu-id="cfed6-159">PowerShell ログ出力の保持</span><span class="sxs-lookup"><span data-stu-id="cfed6-159">Persisting PowerShell log output</span></span>

<span data-ttu-id="cfed6-160">既定では、PowerShell は macOS の既定のメモリのみのログ記録を使用します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-160">By default, PowerShell uses the default memory-only logging on macOS.</span></span> <span data-ttu-id="cfed6-161">この動作を変更して、コマンドを使用して永続化を有効にすることができ `log config` ます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-161">This behavior can be changed to enable persistence using the `log config` command.</span></span>

<span data-ttu-id="cfed6-162">次のスクリプトは、情報レベルのログ記録と永続化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="cfed6-162">The following script enables info level logging and persistence:</span></span>

```
log config --subsystem com.microsoft.powershell --mode=persist:info,level:info
```

<span data-ttu-id="cfed6-163">次のコマンドは、PowerShell のログ記録を既定の状態に戻します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-163">The following command reverts PowerShell logging to the default state:</span></span>

```
log config --subsystem com.microsoft.powershell --mode=persist:default,level:default
```

<span data-ttu-id="cfed6-164">永続化を有効にした後、コマンドを使用して `log show` ログ項目をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-164">After persistence is enabled, the `log show` command can be used to export log items.</span></span> <span data-ttu-id="cfed6-165">このコマンドは、最後の N 個の項目、特定の時刻からの項目、または特定の期間内の項目をエクスポートするためのオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-165">The command provides options for exporting the last N items, items since a given time, or items within a given time span.</span></span>

<span data-ttu-id="cfed6-166">たとえば、次のコマンドは、から項目をエクスポートし `9am on April 5 of 2018` ます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-166">For example, the following command exports items since `9am on April 5 of 2018`:</span></span>

```
log show --info --start "2018-04-05 09:00:00" --predicate "process = 'pwsh'"
```

<span data-ttu-id="cfed6-167">のヘルプを表示するには、を `log` 実行して `log show --help` 追加の詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-167">You can get help for `log` by running `log show --help` for additional details.</span></span>

> [!TIP]
> <span data-ttu-id="cfed6-168">PowerShell プロンプトまたはスクリプトから任意のログコマンドを実行するときは、述語文字列全体を二重引用符で囲み、内の単一引用符を使用します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-168">When executing any of the log commands from a PowerShell prompt or script, use double quotes around the entire predicate string and single quotes within.</span></span> <span data-ttu-id="cfed6-169">これにより、述語文字列内で二重引用符文字をエスケープする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="cfed6-169">This avoids the need to escape double quote characters within the predicate string.</span></span>

<span data-ttu-id="cfed6-170">また、イベントログを中央のイベントログコレクターや [SIEM][] アグリゲーターなどのより安全な場所に保存することも検討してください。</span><span class="sxs-lookup"><span data-stu-id="cfed6-170">You may also want to consider saving the event logs to a more secure location such as a central event log collector, or [SIEM][] aggregator.</span></span> <span data-ttu-id="cfed6-171">Azure で SIEM を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-171">You can set up SIEM in Azure.</span></span> <span data-ttu-id="cfed6-172">詳細については、「 [GENERIC SIEM integration](/cloud-app-security/siem)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfed6-172">For more information, see [Generic SIEM integration](/cloud-app-security/siem).</span></span>

## <a name="configuring-logging-on-a-non-windows-system"></a><span data-ttu-id="cfed6-173">Windows 以外のシステムでのログ記録の構成</span><span class="sxs-lookup"><span data-stu-id="cfed6-173">Configuring logging on a non-Windows system</span></span>

<span data-ttu-id="cfed6-174">Windows では、ETW トレースリスナーを作成するか、イベントビューアーを使用して分析ログを有効にすることで、ログが構成されます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-174">On Windows, logging is configured by creating ETW trace listeners or by using the Event Viewer to enable Analytic logging.</span></span> <span data-ttu-id="cfed6-175">Linux と macOS では、ログはファイルを使用して構成され `powershell.config.json` ます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-175">On Linux and macOS, logging is configured using the file `powershell.config.json`.</span></span> <span data-ttu-id="cfed6-176">このセクションの残りの部分では、Windows 以外のシステムでの PowerShell ログの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-176">The rest of this section will discuss configuring PowerShell logging on a non-Windows system.</span></span>

<span data-ttu-id="cfed6-177">既定では、PowerShell によって、操作チャネルへの情報ログが有効になります。</span><span class="sxs-lookup"><span data-stu-id="cfed6-177">By default, PowerShell enables informational logging to the operational channel.</span></span> <span data-ttu-id="cfed6-178">これは、PowerShell によって生成されるログ出力のうち、操作可能としてマークされているものの、情報がログ記録されるログ (トレース) レベルが高いことを意味します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-178">What this means is any log output produced by PowerShell that is marked as operational and has a log (trace) level greater than informational will be logged.</span></span> <span data-ttu-id="cfed6-179">診断によっては、詳細ログ出力や分析ログ出力の有効化など、追加のログ出力が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cfed6-179">Occasionally, diagnoses may require additional log output, such as verbose log output or enabling analytic log output.</span></span>

<span data-ttu-id="cfed6-180">ファイル `powershell.config.json` は、PowerShell ディレクトリに存在する **JSON** 形式のファイルです `$PSHOME` 。</span><span class="sxs-lookup"><span data-stu-id="cfed6-180">The file `powershell.config.json` is a **JSON** formatted file residing in the PowerShell `$PSHOME` directory.</span></span> <span data-ttu-id="cfed6-181">PowerShell の各インストールは、このファイルの独自のコピーを使用します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-181">Each installation of PowerShell uses its own copy of this file.</span></span> <span data-ttu-id="cfed6-182">通常の操作では、このファイルは変更されません。</span><span class="sxs-lookup"><span data-stu-id="cfed6-182">For normal operation, this file is left unchanged.</span></span> <span data-ttu-id="cfed6-183">これは便利な場合がありますが、ファイル内の一部の設定を変更して診断や同じシステム上の複数の PowerShell バージョンを区別したり、同じバージョンの複数のコピーを区別したりすることもでき `LogIdentity` ます (以下の表を参照)。</span><span class="sxs-lookup"><span data-stu-id="cfed6-183">Although it can be useful, to change some of the settings in the file, for diagnosis or for distinguishing between multiple PowerShell versions on the same system or even multiple copies of the same version (See `LogIdentity` in the table below).</span></span>

<span data-ttu-id="cfed6-184">構成の例を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-184">The following code is an example configuration:</span></span>

```json
{
  "Microsoft.PowerShell:ExecutionPolicy": "RemoteSigned",
  "PowerShellPolicies": {
    "ScriptExecution": {
      "ExecutionPolicy": "RemoteSigned",
      "EnableScripts": true
    },
    "ScriptBlockLogging": {
      "EnableScriptBlockInvocationLogging": true,
      "EnableScriptBlockLogging": true
    },
    "ModuleLogging": {
      "EnableModuleLogging": false,
      "ModuleNames": [
        "PSReadline",
        "PowerShellGet"
      ]
    },
    "ProtectedEventLogging": {
      "EnableProtectedEventLogging": false,
      "EncryptionCertificate": [
        "Joe"
      ]
    },
    "Transcription": {
      "EnableTranscripting": true,
      "EnableInvocationHeader": true,
      "OutputDirectory": "F:\\tmp\\new"
    },
    "UpdatableHelp": {
      "DefaultSourcePath": "f:\\temp"
    },
    "ConsoleSessionConfiguration": {
      "EnableConsoleSessionConfiguration": false,
      "ConsoleSessionConfigurationName": "name"
    }
  },
  "LogLevel": "verbose"
}
```

<span data-ttu-id="cfed6-185">次の表に、PowerShell ログを構成するためのプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-185">The properties for configuring PowerShell logging are listed in the following table.</span></span> <span data-ttu-id="cfed6-186">などのアスタリスクでマーク `Operational*` された値は、ファイルに値が指定されていない場合の既定値を示します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-186">Values marked with an asterisk, such as `Operational*`, indicate the default value when no value is provided in the file.</span></span>

|<span data-ttu-id="cfed6-187">プロパティ</span><span class="sxs-lookup"><span data-stu-id="cfed6-187">Property</span></span>   |<span data-ttu-id="cfed6-188">値</span><span class="sxs-lookup"><span data-stu-id="cfed6-188">Values</span></span>        |<span data-ttu-id="cfed6-189">説明</span><span class="sxs-lookup"><span data-stu-id="cfed6-189">Description</span></span>                                  |
|-----------|--------------|---------------------------------------------|
|`LogIdentity`|<span data-ttu-id="cfed6-190">(文字列名)</span><span class="sxs-lookup"><span data-stu-id="cfed6-190">(string name)</span></span> |<span data-ttu-id="cfed6-191">ログ記録時に使用する名前。</span><span class="sxs-lookup"><span data-stu-id="cfed6-191">The name to use when logging.</span></span> <span data-ttu-id="cfed6-192">既定では、</span><span class="sxs-lookup"><span data-stu-id="cfed6-192">By default,</span></span>  |
|           |<span data-ttu-id="cfed6-193">powershell</span><span class="sxs-lookup"><span data-stu-id="cfed6-193">powershell\*</span></span>   |<span data-ttu-id="cfed6-194">powershell は id です。</span><span class="sxs-lookup"><span data-stu-id="cfed6-194">powershell is the identity.</span></span> <span data-ttu-id="cfed6-195">この値は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cfed6-195">This value can be</span></span>|
|           |              |<span data-ttu-id="cfed6-196">2つの間の違いを示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-196">used to tell the difference between two</span></span>      |
|           |              |<span data-ttu-id="cfed6-197">PowerShell インストールのインスタンス (</span><span class="sxs-lookup"><span data-stu-id="cfed6-197">instances of a PowerShell installation, such</span></span> |
|           |              |<span data-ttu-id="cfed6-198">リリースおよびベータ版として。</span><span class="sxs-lookup"><span data-stu-id="cfed6-198">as a release and beta version.</span></span> <span data-ttu-id="cfed6-199">この値は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cfed6-199">This value is</span></span> |
|           |              |<span data-ttu-id="cfed6-200">ログ出力をにリダイレクトするためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-200">also used to redirect log output to a</span></span>        |
|           |              |<span data-ttu-id="cfed6-201">Linux 上の個別のファイル。</span><span class="sxs-lookup"><span data-stu-id="cfed6-201">separate file on Linux.</span></span> <span data-ttu-id="cfed6-202">「」の説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfed6-202">See the discussion of</span></span>|
|           |              |<span data-ttu-id="cfed6-203">上記の **rsyslog** 。</span><span class="sxs-lookup"><span data-stu-id="cfed6-203">**rsyslog** above.</span></span>                           |
|`LogChannels`|<span data-ttu-id="cfed6-204">操作</span><span class="sxs-lookup"><span data-stu-id="cfed6-204">Operational\*</span></span>  |<span data-ttu-id="cfed6-205">有効にするチャネル。</span><span class="sxs-lookup"><span data-stu-id="cfed6-205">The channels to enable.</span></span> <span data-ttu-id="cfed6-206">値を分離する</span><span class="sxs-lookup"><span data-stu-id="cfed6-206">Separate the values</span></span>|
|           |<span data-ttu-id="cfed6-207">分析</span><span class="sxs-lookup"><span data-stu-id="cfed6-207">Analytic</span></span>      |<span data-ttu-id="cfed6-208">複数指定する場合は、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="cfed6-208">with a comma when specifying more than one.</span></span>  |
|`LogLevel`   |<span data-ttu-id="cfed6-209">Always</span><span class="sxs-lookup"><span data-stu-id="cfed6-209">Always</span></span>        |<span data-ttu-id="cfed6-210">1つの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-210">Specify a single value.</span></span> <span data-ttu-id="cfed6-211">この値により、</span><span class="sxs-lookup"><span data-stu-id="cfed6-211">The value enables</span></span>  |
|           |<span data-ttu-id="cfed6-212">Critical</span><span class="sxs-lookup"><span data-stu-id="cfed6-212">Critical</span></span>      |<span data-ttu-id="cfed6-213">それより上のすべての値と</span><span class="sxs-lookup"><span data-stu-id="cfed6-213">itself and all values above it in the</span></span>        |
|           |<span data-ttu-id="cfed6-214">エラー</span><span class="sxs-lookup"><span data-stu-id="cfed6-214">Error</span></span>         |<span data-ttu-id="cfed6-215">左に一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="cfed6-215">list to the left.</span></span>                            |
|           |<span data-ttu-id="cfed6-216">警告</span><span class="sxs-lookup"><span data-stu-id="cfed6-216">Warning</span></span>       |                                             |
|           |<span data-ttu-id="cfed6-217">専用</span><span class="sxs-lookup"><span data-stu-id="cfed6-217">Informational\*</span></span>|                                             |
|           |<span data-ttu-id="cfed6-218">"詳細"</span><span class="sxs-lookup"><span data-stu-id="cfed6-218">Verbose</span></span>       |                                             |
|           |<span data-ttu-id="cfed6-219">デバッグ</span><span class="sxs-lookup"><span data-stu-id="cfed6-219">Debug</span></span>         |                                             |
|`LogKeywords`|<span data-ttu-id="cfed6-220">Runspace</span><span class="sxs-lookup"><span data-stu-id="cfed6-220">Runspace</span></span>      |<span data-ttu-id="cfed6-221">キーワードを使用すると、ログ記録を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-221">Keywords provide the ability to limit logging</span></span>|
|           |<span data-ttu-id="cfed6-222">パイプライン</span><span class="sxs-lookup"><span data-stu-id="cfed6-222">Pipeline</span></span>      |<span data-ttu-id="cfed6-223">PowerShell 内の特定のコンポーネントに対して。</span><span class="sxs-lookup"><span data-stu-id="cfed6-223">to specific components within PowerShell.</span></span> <span data-ttu-id="cfed6-224">By</span><span class="sxs-lookup"><span data-stu-id="cfed6-224">By</span></span> |
|           |<span data-ttu-id="cfed6-225">プロトコル</span><span class="sxs-lookup"><span data-stu-id="cfed6-225">Protocol</span></span>      |<span data-ttu-id="cfed6-226">既定では、すべてのキーワードが有効になり、変更されます。</span><span class="sxs-lookup"><span data-stu-id="cfed6-226">default, all keywords are enabled and change</span></span> |
|           |<span data-ttu-id="cfed6-227">トランスポート</span><span class="sxs-lookup"><span data-stu-id="cfed6-227">Transport</span></span>     |<span data-ttu-id="cfed6-228">この値は非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="cfed6-228">this value is only useful for very</span></span>           |
|           |<span data-ttu-id="cfed6-229">Host</span><span class="sxs-lookup"><span data-stu-id="cfed6-229">Host</span></span>          |<span data-ttu-id="cfed6-230">特別なトラブルシューティング。</span><span class="sxs-lookup"><span data-stu-id="cfed6-230">specialized troubleshooting.</span></span>                |
|           |<span data-ttu-id="cfed6-231">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="cfed6-231">Cmdlets</span></span>       |                                             |
|           |<span data-ttu-id="cfed6-232">シリアライザー</span><span class="sxs-lookup"><span data-stu-id="cfed6-232">Serializer</span></span>    |                                             |
|           |<span data-ttu-id="cfed6-233">セッション</span><span class="sxs-lookup"><span data-stu-id="cfed6-233">Session</span></span>       |                                             |
|           |<span data-ttu-id="cfed6-234">ManagedPlugin</span><span class="sxs-lookup"><span data-stu-id="cfed6-234">ManagedPlugin</span></span> |                                             |

## <a name="see-also"></a><span data-ttu-id="cfed6-235">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfed6-235">See also</span></span>

<span data-ttu-id="cfed6-236">Linux の **syslog** と **rsyslog** の情報については、linux コンピューターのローカルページを参照してください `man` 。</span><span class="sxs-lookup"><span data-stu-id="cfed6-236">For Linux **syslog** and **rsyslog.conf** information, refer to the Linux computer's local `man` pages.</span></span>

<span data-ttu-id="cfed6-237">MacOS の **os_log** 情報については、 [os_log 開発者向けドキュメント](https://developer.apple.com/documentation/os/os_log)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfed6-237">For macOS **os_log** information, see [os_log developer documentation](https://developer.apple.com/documentation/os/os_log).</span></span>

[<span data-ttu-id="cfed6-238">about_Logging_Windows</span><span class="sxs-lookup"><span data-stu-id="cfed6-238">about_Logging_Windows</span></span>](about_Logging_Windows.md)

[<span data-ttu-id="cfed6-239">汎用 SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="cfed6-239">Generic SIEM integration</span></span>](/cloud-app-security/siem)

<!-- link references -->
[SIEM]: https://wikipedia.org/wiki/Security_information_and_event_management
