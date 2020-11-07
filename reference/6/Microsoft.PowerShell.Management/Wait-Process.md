---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/wait-process?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Process
ms.openlocfilehash: 88eec3461a267a03bfe3a91735ece7269aa601c2
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345036"
---
# <span data-ttu-id="1c9ab-103">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="1c9ab-103">Wait-Process</span></span>

## <span data-ttu-id="1c9ab-104">概要</span><span class="sxs-lookup"><span data-stu-id="1c9ab-104">SYNOPSIS</span></span>
<span data-ttu-id="1c9ab-105">プロセスが停止するまで、次の入力を受け取るのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-105">Waits for the processes to be stopped before accepting more input.</span></span>

## <span data-ttu-id="1c9ab-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1c9ab-106">SYNTAX</span></span>

### <span data-ttu-id="1c9ab-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="1c9ab-107">Name (Default)</span></span>

```
Wait-Process [-Name] <String[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="1c9ab-108">Id</span><span class="sxs-lookup"><span data-stu-id="1c9ab-108">Id</span></span>

```
Wait-Process [-Id] <Int32[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="1c9ab-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="1c9ab-109">InputObject</span></span>

```
Wait-Process [[-Timeout] <Int32>] -InputObject <Process[]> [<CommonParameters>]
```

## <span data-ttu-id="1c9ab-110">Description</span><span class="sxs-lookup"><span data-stu-id="1c9ab-110">DESCRIPTION</span></span>

<span data-ttu-id="1c9ab-111">`Wait-Process`コマンドレットは、実行中の1つ以上のプロセスが、入力を受け入れる前に停止するのを待機します。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-111">The `Wait-Process` cmdlet waits for one or more running processes to be stopped before accepting input.</span></span> <span data-ttu-id="1c9ab-112">PowerShell コンソールでは、このコマンドレットにより、プロセスが停止するまでコマンドプロンプトが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-112">In the PowerShell console, this cmdlet suppresses the command prompt until the processes are stopped.</span></span> <span data-ttu-id="1c9ab-113">プロセスは、プロセス名またはプロセス ID (PID) で指定することも、パイプを使用してに処理することもでき `Wait-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-113">You can specify a process by process name or process ID (PID), or pipe a process object to `Wait-Process`.</span></span>

<span data-ttu-id="1c9ab-114">`Wait-Process` ローカルコンピューター上で実行されているプロセスでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-114">`Wait-Process` works only on processes running on the local computer.</span></span>

## <span data-ttu-id="1c9ab-115">例</span><span class="sxs-lookup"><span data-stu-id="1c9ab-115">EXAMPLES</span></span>

### <span data-ttu-id="1c9ab-116">例 1: プロセスを停止して待機する</span><span class="sxs-lookup"><span data-stu-id="1c9ab-116">Example 1: Stop a process and wait</span></span>

```
PS C:\> $nid = (Get-Process notepad).id
PS C:\> Stop-Process -Id $nid
PS C:\> Wait-Process -Id $nid
```

<span data-ttu-id="1c9ab-117">この例では、メモ帳のプロセスを停止し、プロセスが停止するまで待機してから、次のコマンドに進みます。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-117">This example stops the Notepad process and then waits for the process to be stopped before it continues with the next command.</span></span>

<span data-ttu-id="1c9ab-118">最初のコマンドは、 `Get-Process` コマンドレットを使用して、メモ帳のプロセスの ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-118">The first command uses the `Get-Process` cmdlet to get the ID of the Notepad process.</span></span> <span data-ttu-id="1c9ab-119">ID は変数に格納され `$nid` ます。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-119">It stores the ID in the `$nid` variable.</span></span>

<span data-ttu-id="1c9ab-120">2番目のコマンドは、コマンドレットを使用して、 `Stop-Process` に格納されている ID を使用してプロセスを停止し `$nid` ます。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-120">The second command uses the `Stop-Process` cmdlet to stop the process with the ID stored in `$nid`.</span></span>

<span data-ttu-id="1c9ab-121">3番目のコマンドは、を使用して `Wait-Process` 、Notepad プロセスが停止するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-121">The third command uses `Wait-Process` to wait until the Notepad process is stopped.</span></span> <span data-ttu-id="1c9ab-122">の **Id** パラメーターを使用して `Wait-Process` プロセスを識別します。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-122">It uses the **Id** parameter of `Wait-Process` to identify the process.</span></span>

### <span data-ttu-id="1c9ab-123">例 2: プロセスを指定する</span><span class="sxs-lookup"><span data-stu-id="1c9ab-123">Example 2: Specifying a process</span></span>

```
PS C:\> $p = Get-Process notepad
PS C:\> Wait-Process -Id $p.id
PS C:\> Wait-Process -Name "notepad"
PS C:\> Wait-Process -InputObject $p
```

<span data-ttu-id="1c9ab-124">これらのコマンドは、にプロセスを指定する3つの異なる方法を示して `Wait-Process` います。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-124">These commands show three different methods of specifying a process to `Wait-Process`.</span></span> <span data-ttu-id="1c9ab-125">最初のコマンドは、メモ帳のプロセスを取得し、変数に格納し `$p` ます。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-125">The first command gets the Notepad process and stores it in the `$p` variable.</span></span>

<span data-ttu-id="1c9ab-126">2番目のコマンドは **Id** パラメーターを使用し、3番目のコマンドは **Name** パラメーターを使用し、4番目のコマンドは **InputObject** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-126">The second command uses the **Id** parameter, the third command uses the **Name** parameter, and the fourth command uses the **InputObject** parameter.</span></span>

<span data-ttu-id="1c9ab-127">これらのコマンドの結果はすべて同じであり、置き換えて使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-127">These commands have the same results and can be used interchangeably.</span></span>

### <span data-ttu-id="1c9ab-128">例 3: 指定した時間だけプロセスを待機する</span><span class="sxs-lookup"><span data-stu-id="1c9ab-128">Example 3: Wait for processes for a specified time</span></span>

```
PS C:\> Wait-Process -Name outlook, winword -Timeout 30
```

<span data-ttu-id="1c9ab-129">このコマンドは、Outlook と Winword の各プロセスが停止するまで 30 秒間待ちます。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-129">This command waits 30 seconds for the Outlook and Winword processes to stop.</span></span> <span data-ttu-id="1c9ab-130">プロセスがいずれも停止しない場合、コマンドレットによって未終了エラーが表示され、コマンド プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-130">If both processes are not stopped, the cmdlet displays a non-terminating error and the command prompt.</span></span>

## <span data-ttu-id="1c9ab-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1c9ab-131">PARAMETERS</span></span>

### <span data-ttu-id="1c9ab-132">-Id</span><span class="sxs-lookup"><span data-stu-id="1c9ab-132">-Id</span></span>

<span data-ttu-id="1c9ab-133">プロセスのプロセス ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-133">Specifies the process IDs of the processes.</span></span> <span data-ttu-id="1c9ab-134">複数の ID を指定するには、ID をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-134">To specify multiple IDs, use commas to separate the IDs.</span></span>
<span data-ttu-id="1c9ab-135">プロセスの PID を検索するには、「」と入力 `Get-Process` します。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-135">To find the PID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases: PID, ProcessId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1c9ab-136">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1c9ab-136">-InputObject</span></span>

<span data-ttu-id="1c9ab-137">プロセス オブジェクトを送信して、プロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-137">Specifies the processes by submitting process objects.</span></span> <span data-ttu-id="1c9ab-138">プロセスオブジェクトが格納されている変数を入力するか、コマンドレットなどのプロセスオブジェクトを取得するコマンドまたは式を入力し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-138">Enter a variable that contains the process objects, or type a command or expression that gets the process objects, such as the `Get-Process` cmdlet.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1c9ab-139">-Name</span><span class="sxs-lookup"><span data-stu-id="1c9ab-139">-Name</span></span>

<span data-ttu-id="1c9ab-140">プロセスのプロセス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-140">Specifies the process names of the processes.</span></span> <span data-ttu-id="1c9ab-141">複数の名前を指定するには、名前をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-141">To specify multiple names, use commas to separate the names.</span></span> <span data-ttu-id="1c9ab-142">ワイルドカード文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-142">Wildcard characters are not supported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1c9ab-143">-タイムアウト</span><span class="sxs-lookup"><span data-stu-id="1c9ab-143">-Timeout</span></span>

<span data-ttu-id="1c9ab-144">このコマンドレットが、指定されたプロセスを停止するまで待機する最大時間を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-144">Specifies the maximum time, in seconds, that this cmdlet waits for the specified processes to stop.</span></span>
<span data-ttu-id="1c9ab-145">この時間が経過すると、まだ実行中のプロセスの一覧を示す未終了エラーが表示され、待機動作が終了します。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-145">When this interval expires, the command displays a non-terminating error that lists the processes that are still running, and ends the wait.</span></span> <span data-ttu-id="1c9ab-146">既定では、タイムアウトはありません。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-146">By default, there is no time-out.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1c9ab-147">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1c9ab-147">CommonParameters</span></span>

<span data-ttu-id="1c9ab-148">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1c9ab-149">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1c9ab-150">入力</span><span class="sxs-lookup"><span data-stu-id="1c9ab-150">INPUTS</span></span>

### <span data-ttu-id="1c9ab-151">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="1c9ab-151">System.Diagnostics.Process</span></span>

<span data-ttu-id="1c9ab-152">パイプを使用してプロセスオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-152">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="1c9ab-153">出力</span><span class="sxs-lookup"><span data-stu-id="1c9ab-153">OUTPUTS</span></span>

### <span data-ttu-id="1c9ab-154">なし</span><span class="sxs-lookup"><span data-stu-id="1c9ab-154">None</span></span>

<span data-ttu-id="1c9ab-155">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-155">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="1c9ab-156">注</span><span class="sxs-lookup"><span data-stu-id="1c9ab-156">NOTES</span></span>

<span data-ttu-id="1c9ab-157">コマンドレットは、Windows プラットフォームでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-157">The cmdlet is only supported on Windows platforms.</span></span>

<span data-ttu-id="1c9ab-158">このコマンドレットは、 **system.servicemodel クラスの** **waitforexit** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c9ab-158">This cmdlet uses the **WaitForExit** method of the **System.Diagnostics.Process** class.</span></span>

## <span data-ttu-id="1c9ab-159">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1c9ab-159">RELATED LINKS</span></span>

[<span data-ttu-id="1c9ab-160">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="1c9ab-160">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="1c9ab-161">Get-Process</span><span class="sxs-lookup"><span data-stu-id="1c9ab-161">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="1c9ab-162">Start-Process</span><span class="sxs-lookup"><span data-stu-id="1c9ab-162">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="1c9ab-163">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="1c9ab-163">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="1c9ab-164">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="1c9ab-164">Wait-Process</span></span>](Wait-Process.md)
