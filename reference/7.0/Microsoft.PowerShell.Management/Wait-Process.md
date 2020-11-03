---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/wait-process?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Process
ms.openlocfilehash: 07986e4c7e8ead25e99ffc67ff8f9ffa2241af9b
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209739"
---
# <span data-ttu-id="b5acd-103">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="b5acd-103">Wait-Process</span></span>

## <span data-ttu-id="b5acd-104">概要</span><span class="sxs-lookup"><span data-stu-id="b5acd-104">SYNOPSIS</span></span>
<span data-ttu-id="b5acd-105">プロセスが停止するまで、次の入力を受け取るのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="b5acd-105">Waits for the processes to be stopped before accepting more input.</span></span>

## <span data-ttu-id="b5acd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b5acd-106">SYNTAX</span></span>

### <span data-ttu-id="b5acd-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="b5acd-107">Name (Default)</span></span>

```
Wait-Process [-Name] <String[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="b5acd-108">Id</span><span class="sxs-lookup"><span data-stu-id="b5acd-108">Id</span></span>

```
Wait-Process [-Id] <Int32[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="b5acd-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="b5acd-109">InputObject</span></span>

```
Wait-Process [[-Timeout] <Int32>] -InputObject <Process[]> [<CommonParameters>]
```

## <span data-ttu-id="b5acd-110">Description</span><span class="sxs-lookup"><span data-stu-id="b5acd-110">DESCRIPTION</span></span>

<span data-ttu-id="b5acd-111">**Wait Process** コマンドレットは、実行中の1つ以上のプロセスが、入力を受け入れる前に停止するのを待機します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-111">The **Wait-Process** cmdlet waits for one or more running processes to be stopped before accepting input.</span></span>
<span data-ttu-id="b5acd-112">PowerShell コンソールでは、このコマンドレットにより、プロセスが停止するまでコマンドプロンプトが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="b5acd-112">In the PowerShell console, this cmdlet suppresses the command prompt until the processes are stopped.</span></span>
<span data-ttu-id="b5acd-113">プロセスは、プロセス名またはプロセス ID (PID) を使用して指定することも、プロセスオブジェクトを **待機プロセス** にパイプすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b5acd-113">You can specify a process by process name or process ID (PID), or pipe a process object to **Wait-Process** .</span></span>

<span data-ttu-id="b5acd-114">**待機プロセス** は、ローカルコンピューター上で実行されているプロセスでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-114">**Wait-Process** works only on processes running on the local computer.</span></span>

## <span data-ttu-id="b5acd-115">例</span><span class="sxs-lookup"><span data-stu-id="b5acd-115">EXAMPLES</span></span>

### <span data-ttu-id="b5acd-116">例 1: プロセスを停止して待機する</span><span class="sxs-lookup"><span data-stu-id="b5acd-116">Example 1: Stop a process and wait</span></span>

```
PS C:\> $nid = (Get-Process notepad).id
PS C:\> Stop-Process -Id $nid
PS C:\> Wait-Process -Id $nid
```

<span data-ttu-id="b5acd-117">この例では、メモ帳のプロセスを停止し、プロセスが停止するまで待機してから、次のコマンドに進みます。</span><span class="sxs-lookup"><span data-stu-id="b5acd-117">This example stops the Notepad process and then waits for the process to be stopped before it continues with the next command.</span></span>

<span data-ttu-id="b5acd-118">最初のコマンドは、 **Get process** コマンドレットを使用して、メモ帳のプロセスの ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-118">The first command uses the **Get-Process** cmdlet to get the ID of the Notepad process.</span></span>
<span data-ttu-id="b5acd-119">ID は $nid 変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="b5acd-119">It stores the ID in the $nid variable.</span></span>

<span data-ttu-id="b5acd-120">2番目のコマンドは、Stop-Process コマンドレットを使用して、$nid に格納されている ID を使用してプロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-120">The second command uses the Stop-Process cmdlet to stop the process with the ID stored in $nid.</span></span>

<span data-ttu-id="b5acd-121">3番目のコマンドは、 **待機プロセス** を使用して、Notepad プロセスが停止するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-121">The third command uses **Wait-Process** to wait until the Notepad process is stopped.</span></span>
<span data-ttu-id="b5acd-122">プロセスを識別するために、 **待機プロセス** の *Id* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-122">It uses the *Id* parameter of **Wait-Process** to identify the process.</span></span>

### <span data-ttu-id="b5acd-123">例 2: プロセスを指定する</span><span class="sxs-lookup"><span data-stu-id="b5acd-123">Example 2: Specifying a process</span></span>

```
PS C:\> $p = Get-Process notepad
PS C:\> Wait-Process -Id $p.id
PS C:\> Wait-Process -Name "notepad"
PS C:\> Wait-Process -InputObject $p
```

<span data-ttu-id="b5acd-124">これらのコマンドは、プロセスを **待機** するプロセスを指定する3つの異なる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b5acd-124">These commands show three different methods of specifying a process to **Wait-Process** .</span></span>
<span data-ttu-id="b5acd-125">最初のコマンドは、メモ帳のプロセスを取得し、$p 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-125">The first command gets the Notepad process and stores it in the $p variable.</span></span>

<span data-ttu-id="b5acd-126">2番目のコマンドは *Id* パラメーターを使用し、3番目のコマンドは *Name* パラメーターを使用し、4番目のコマンドは *InputObject* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-126">The second command uses the *Id* parameter, the third command uses the *Name* parameter, and the fourth command uses the *InputObject* parameter.</span></span>

<span data-ttu-id="b5acd-127">これらのコマンドの結果はすべて同じであり、置き換えて使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b5acd-127">These commands have the same results and can be used interchangeably.</span></span>

### <span data-ttu-id="b5acd-128">例 3: 指定した時間だけプロセスを待機する</span><span class="sxs-lookup"><span data-stu-id="b5acd-128">Example 3: Wait for processes for a specified time</span></span>

```
PS C:\> Wait-Process -Name outlook, winword -Timeout 30
```

<span data-ttu-id="b5acd-129">このコマンドは、Outlook と Winword の各プロセスが停止するまで 30 秒間待ちます。</span><span class="sxs-lookup"><span data-stu-id="b5acd-129">This command waits 30 seconds for the Outlook and Winword processes to stop.</span></span>
<span data-ttu-id="b5acd-130">プロセスがいずれも停止しない場合、コマンドレットによって未終了エラーが表示され、コマンド プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5acd-130">If both processes are not stopped, the cmdlet displays a non-terminating error and the command prompt.</span></span>

## <span data-ttu-id="b5acd-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b5acd-131">PARAMETERS</span></span>

### <span data-ttu-id="b5acd-132">-Id</span><span class="sxs-lookup"><span data-stu-id="b5acd-132">-Id</span></span>

<span data-ttu-id="b5acd-133">プロセスのプロセス ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-133">Specifies the process IDs of the processes.</span></span>
<span data-ttu-id="b5acd-134">複数の ID を指定するには、ID をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="b5acd-134">To specify multiple IDs, use commas to separate the IDs.</span></span>
<span data-ttu-id="b5acd-135">プロセスの PID を検索するには、「」と入力 `Get-Process` します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-135">To find the PID of a process, type `Get-Process`.</span></span>

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

### <span data-ttu-id="b5acd-136">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b5acd-136">-InputObject</span></span>

<span data-ttu-id="b5acd-137">プロセス オブジェクトを送信して、プロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-137">Specifies the processes by submitting process objects.</span></span>
<span data-ttu-id="b5acd-138">プロセスオブジェクトが格納されている変数を入力するか、Get-Process コマンドレットなどのプロセスオブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-138">Enter a variable that contains the process objects, or type a command or expression that gets the process objects, such as the Get-Process cmdlet.</span></span>

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

### <span data-ttu-id="b5acd-139">-Name</span><span class="sxs-lookup"><span data-stu-id="b5acd-139">-Name</span></span>

<span data-ttu-id="b5acd-140">プロセスのプロセス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-140">Specifies the process names of the processes.</span></span>
<span data-ttu-id="b5acd-141">複数の名前を指定するには、名前をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="b5acd-141">To specify multiple names, use commas to separate the names.</span></span>
<span data-ttu-id="b5acd-142">ワイルドカード文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b5acd-142">Wildcard characters are not supported.</span></span>

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

### <span data-ttu-id="b5acd-143">-タイムアウト</span><span class="sxs-lookup"><span data-stu-id="b5acd-143">-Timeout</span></span>

<span data-ttu-id="b5acd-144">このコマンドレットが、指定されたプロセスを停止するまで待機する最大時間を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-144">Specifies the maximum time, in seconds, that this cmdlet waits for the specified processes to stop.</span></span>
<span data-ttu-id="b5acd-145">この時間が経過すると、まだ実行中のプロセスの一覧を示す未終了エラーが表示され、待機動作が終了します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-145">When this interval expires, the command displays a non-terminating error that lists the processes that are still running, and ends the wait.</span></span>
<span data-ttu-id="b5acd-146">既定では、タイムアウトはありません。</span><span class="sxs-lookup"><span data-stu-id="b5acd-146">By default, there is no time-out.</span></span>

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

### <span data-ttu-id="b5acd-147">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b5acd-147">CommonParameters</span></span>

<span data-ttu-id="b5acd-148">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b5acd-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b5acd-149">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5acd-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b5acd-150">入力</span><span class="sxs-lookup"><span data-stu-id="b5acd-150">INPUTS</span></span>

### <span data-ttu-id="b5acd-151">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="b5acd-151">System.Diagnostics.Process</span></span>

<span data-ttu-id="b5acd-152">パイプを使用してプロセスオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-152">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="b5acd-153">出力</span><span class="sxs-lookup"><span data-stu-id="b5acd-153">OUTPUTS</span></span>

### <span data-ttu-id="b5acd-154">なし</span><span class="sxs-lookup"><span data-stu-id="b5acd-154">None</span></span>

<span data-ttu-id="b5acd-155">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="b5acd-155">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b5acd-156">注</span><span class="sxs-lookup"><span data-stu-id="b5acd-156">NOTES</span></span>

* <span data-ttu-id="b5acd-157">このコマンドレットは、system.servicemodel クラスの **Waitforexit** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5acd-157">This cmdlet uses the **WaitForExit** method of the System.Diagnostics.Process class.</span></span> <span data-ttu-id="b5acd-158">このメソッドの詳細については、「Microsoft .NET Framework SDK」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5acd-158">For more information about this method, see the Microsoft .NET Framework SDK.</span></span>

*

## <span data-ttu-id="b5acd-159">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b5acd-159">RELATED LINKS</span></span>

[<span data-ttu-id="b5acd-160">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="b5acd-160">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="b5acd-161">Get-Process</span><span class="sxs-lookup"><span data-stu-id="b5acd-161">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="b5acd-162">Start-Process</span><span class="sxs-lookup"><span data-stu-id="b5acd-162">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="b5acd-163">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="b5acd-163">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="b5acd-164">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="b5acd-164">Wait-Process</span></span>](Wait-Process.md)
