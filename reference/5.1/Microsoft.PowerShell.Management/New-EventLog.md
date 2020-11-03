---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-EventLog
ms.openlocfilehash: 61fafc0670a24fd6ca057e4cf0c7179d90446b07
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214619"
---
# <span data-ttu-id="9662c-103">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="9662c-103">New-EventLog</span></span>

## <span data-ttu-id="9662c-104">概要</span><span class="sxs-lookup"><span data-stu-id="9662c-104">SYNOPSIS</span></span>
<span data-ttu-id="9662c-105">新しいイベント ログおよび新しいイベント ソースをローカル コンピューターまたはリモート コンピューター上に作成します。</span><span class="sxs-lookup"><span data-stu-id="9662c-105">Creates a new event log and a new event source on a local or remote computer.</span></span>

## <span data-ttu-id="9662c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9662c-106">SYNTAX</span></span>

```
New-EventLog [-LogName] <string> [-Source] <string[]> [[-ComputerName] <string[]>]
  [-CategoryResourceFile <string>] [-MessageResourceFile <string>] [-ParameterResourceFile <string>]
  [<CommonParameters>]
```

## <span data-ttu-id="9662c-107">Description</span><span class="sxs-lookup"><span data-stu-id="9662c-107">DESCRIPTION</span></span>

<span data-ttu-id="9662c-108">このコマンドレットは、新しい従来のイベント ログをローカル コンピューターまたはリモート コンピューター上に作成します。</span><span class="sxs-lookup"><span data-stu-id="9662c-108">This cmdlet creates a new classic event log on a local or remote computer.</span></span> <span data-ttu-id="9662c-109">また、イベント ソースを登録して、新しいログまたは既存のログに書き込みを行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="9662c-109">It can also register an event source that writes to the new log or to an existing log.</span></span>

<span data-ttu-id="9662c-110">EventLog という名詞を含むコマンドレット (Event ログ コマンドレット) は、従来のイベント ログでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="9662c-110">The cmdlets that contain the EventLog noun (the Event log cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="9662c-111">Windows Vista 以降のバージョンの windows で windows イベントログテクノロジを使用するログからイベントを取得するには、を使用し `Get-WinEvent` ます。</span><span class="sxs-lookup"><span data-stu-id="9662c-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of Windows, use `Get-WinEvent`.</span></span>

## <span data-ttu-id="9662c-112">例</span><span class="sxs-lookup"><span data-stu-id="9662c-112">EXAMPLES</span></span>

### <span data-ttu-id="9662c-113">例 1-新しいイベントログを作成する</span><span class="sxs-lookup"><span data-stu-id="9662c-113">Example 1 - create a new event log</span></span>

<span data-ttu-id="9662c-114">このコマンドは、TestLog イベント ログをローカル コンピューター上に作成し、ログの新しいソースを登録します。</span><span class="sxs-lookup"><span data-stu-id="9662c-114">This command creates the TestLog event log on the local computer and registers a new source for it.</span></span>

```powershell
New-EventLog -source TestApp -LogName TestLog -MessageResourceFile C:\Test\TestApp.dll
```

### <span data-ttu-id="9662c-115">例 2-既存のログに新しいイベントソースを追加する</span><span class="sxs-lookup"><span data-stu-id="9662c-115">Example 2 - add a new event source to an existing log</span></span>

<span data-ttu-id="9662c-116">このコマンドは、新しいイベント ソース NewTestApp を Server01 リモート コンピューター上の Application ログに追加します。</span><span class="sxs-lookup"><span data-stu-id="9662c-116">This command adds a new event source, NewTestApp, to the Application log on the Server01 remote computer.</span></span>

```powershell
$file = "C:\Program Files\TestApps\NewTestApp.dll"
New-EventLog -ComputerName Server01 -Source NewTestApp -LogName Application -MessageResourceFile $file -CategoryResourceFile $file
```

<span data-ttu-id="9662c-117">このコマンドを実行するには、Server01 コンピューター上に NewTestApp.dll ファイルが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9662c-117">The command requires that the NewTestApp.dll file is located on the Server01 computer.</span></span>

## <span data-ttu-id="9662c-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9662c-118">PARAMETERS</span></span>

### <span data-ttu-id="9662c-119">-CategoryResourceFile</span><span class="sxs-lookup"><span data-stu-id="9662c-119">-CategoryResourceFile</span></span>

<span data-ttu-id="9662c-120">ソース イベントのカテゴリ文字列が含まれているファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9662c-120">Specifies the path to the file that contains category strings for the source events.</span></span> <span data-ttu-id="9662c-121">このファイルはカテゴリ メッセージ ファイルとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9662c-121">This file is also known as the Category Message File.</span></span>

<span data-ttu-id="9662c-122">ファイルは、イベント ログを作成するコンピューター上に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9662c-122">The file must be present on the computer on which the event log is being created.</span></span> <span data-ttu-id="9662c-123">このパラメーターでは、ファイルの作成または移動が行われません。</span><span class="sxs-lookup"><span data-stu-id="9662c-123">This parameter does not create or move files.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9662c-124">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="9662c-124">-ComputerName</span></span>

<span data-ttu-id="9662c-125">指定されたコンピューター上に新しいイベント ログを作成します。</span><span class="sxs-lookup"><span data-stu-id="9662c-125">Creates the new event logs on the specified computers.</span></span> <span data-ttu-id="9662c-126">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="9662c-126">The default is the local computer.</span></span>

<span data-ttu-id="9662c-127">リモートコンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="9662c-127">The NetBIOS name, IP address, or fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="9662c-128">ローカル コンピューターを指定するには、コンピューター名、ドット (.)、または「localhost」を入力します。</span><span class="sxs-lookup"><span data-stu-id="9662c-128">To specify the local computer, type the computer name, a dot (.), or "localhost".</span></span>

<span data-ttu-id="9662c-129">このパラメーターは、PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="9662c-129">This parameter does not rely on PowerShell remoting.</span></span> <span data-ttu-id="9662c-130">**ComputerName** `Get-EventLog` コンピューターがリモートコマンドを実行するように構成されていない場合でも、の ComputerName パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9662c-130">You can use the **ComputerName** parameter of `Get-EventLog` even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 3
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9662c-131">-LogName</span><span class="sxs-lookup"><span data-stu-id="9662c-131">-LogName</span></span>

<span data-ttu-id="9662c-132">イベント ログの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9662c-132">Specifies the name of the event log.</span></span>

<span data-ttu-id="9662c-133">ログが存在しない場合、は `New-EventLog` ログを作成し、新しいイベントログの **Log** および **logdisplayname** プロパティにこの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="9662c-133">If the log does not exist, `New-EventLog` creates the log and uses this value for the **Log** and **LogDisplayName** properties of the new event log.</span></span> <span data-ttu-id="9662c-134">ログが存在する場合は、 `New-EventLog` イベントログの新しいソースを登録します。</span><span class="sxs-lookup"><span data-stu-id="9662c-134">If the log exists, `New-EventLog` registers a new source for the event log.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9662c-135">-MessageResourceFile</span><span class="sxs-lookup"><span data-stu-id="9662c-135">-MessageResourceFile</span></span>

<span data-ttu-id="9662c-136">ソース イベントのメッセージ書式設定文字列が含まれているファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9662c-136">Specifies the path to the file that contains message formatting strings for the source events.</span></span>
<span data-ttu-id="9662c-137">このファイルはイベント メッセージ ファイルとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9662c-137">This file is also known as the Event Message File.</span></span>

<span data-ttu-id="9662c-138">ファイルは、イベント ログを作成するコンピューター上に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9662c-138">The file must be present on the computer on which the event log is being created.</span></span>
<span data-ttu-id="9662c-139">このパラメーターでは、ファイルの作成または移動が行われません。</span><span class="sxs-lookup"><span data-stu-id="9662c-139">This parameter does not create or move files.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9662c-140">-ParameterResourceFile</span><span class="sxs-lookup"><span data-stu-id="9662c-140">-ParameterResourceFile</span></span>

<span data-ttu-id="9662c-141">イベントの説明でパラメーターに置き換えて使用する文字列が含まれているファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9662c-141">Specifies the path to the file that contains strings used for parameter substitutions in event descriptions.</span></span> <span data-ttu-id="9662c-142">このファイルはパラメーター メッセージ ファイルとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9662c-142">This file is also known as the Parameter Message File.</span></span>

<span data-ttu-id="9662c-143">ファイルは、イベント ログを作成するコンピューター上に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9662c-143">The file must be present on the computer on which the event log is being created.</span></span>
<span data-ttu-id="9662c-144">このパラメーターでは、ファイルの作成または移動が行われません。</span><span class="sxs-lookup"><span data-stu-id="9662c-144">This parameter does not create or move files.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9662c-145">-Source</span><span class="sxs-lookup"><span data-stu-id="9662c-145">-Source</span></span>

<span data-ttu-id="9662c-146">イベント ログに書き込むアプリケーション プログラムのようなイベント ログ ソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9662c-146">Specifies the names of the event log sources, such as application programs that write to the event log.</span></span> <span data-ttu-id="9662c-147">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="9662c-147">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9662c-148">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9662c-148">CommonParameters</span></span>

<span data-ttu-id="9662c-149">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9662c-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9662c-150">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9662c-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9662c-151">入力</span><span class="sxs-lookup"><span data-stu-id="9662c-151">INPUTS</span></span>

### <span data-ttu-id="9662c-152">なし</span><span class="sxs-lookup"><span data-stu-id="9662c-152">None</span></span>

<span data-ttu-id="9662c-153">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="9662c-153">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="9662c-154">出力</span><span class="sxs-lookup"><span data-stu-id="9662c-154">OUTPUTS</span></span>

### <span data-ttu-id="9662c-155">EventLogEntry</span><span class="sxs-lookup"><span data-stu-id="9662c-155">System.Diagnostics.EventLogEntry</span></span>

## <span data-ttu-id="9662c-156">注</span><span class="sxs-lookup"><span data-stu-id="9662c-156">NOTES</span></span>

<span data-ttu-id="9662c-157">Windows Vista 以降のバージョンの Windows でを使用するには `New-EventLog` 、[管理者として実行] オプションを使用して PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="9662c-157">To use `New-EventLog` on Windows Vista and later versions of Windows, open PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="9662c-158">Windows Vista、Windows XP Professional、または Windows Server 2003 でイベント ソースを作成するには、コンピューターの Administrators グループのメンバーであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="9662c-158">To create an event source in Windows Vista, Windows XP Professional, or Windows Server 2003, you must be a member of the Administrators group on the computer.</span></span>

<span data-ttu-id="9662c-159">新しいイベント ログと新しいイベント ソースを作成する場合、新しいログには新しいソースが登録されますが、最初のエントリが書き込まれるまでログは作成されません。</span><span class="sxs-lookup"><span data-stu-id="9662c-159">When you create a new event log and a new event source, the system registers the new source for the new log, but the log is not created until the first entry is written to it.</span></span>

<span data-ttu-id="9662c-160">オペレーティング システムではイベント ログはファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="9662c-160">The operating system stores event logs as files.</span></span>

<span data-ttu-id="9662c-161">新しいイベントログを作成すると、関連付けられているファイルは、 `$env:SystemRoot\System32\Config` 指定したコンピューターのディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="9662c-161">When you create a new event log, the associated file is stored in the `$env:SystemRoot\System32\Config` directory on the specified computer.</span></span>

<span data-ttu-id="9662c-162">ファイル名は、 **Log** プロパティの最初の8文字で、ファイル名拡張子は .evt です。</span><span class="sxs-lookup"><span data-stu-id="9662c-162">The file name is the first eight characters of the **Log** property with an .evt file name extension.</span></span>

## <span data-ttu-id="9662c-163">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9662c-163">RELATED LINKS</span></span>

[<span data-ttu-id="9662c-164">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="9662c-164">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="9662c-165">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="9662c-165">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="9662c-166">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="9662c-166">Get-WinEvent</span></span>](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[<span data-ttu-id="9662c-167">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="9662c-167">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="9662c-168">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="9662c-168">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="9662c-169">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="9662c-169">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="9662c-170">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="9662c-170">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="9662c-171">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="9662c-171">Write-EventLog</span></span>](Write-EventLog.md)
