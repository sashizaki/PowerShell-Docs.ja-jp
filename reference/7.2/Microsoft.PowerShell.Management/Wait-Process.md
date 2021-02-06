---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/wait-process?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Process
ms.openlocfilehash: c469a4e9cf17b03a33bc8b9ff9b06aa95773fc02
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601405"
---
# <span data-ttu-id="da38f-102">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="da38f-102">Wait-Process</span></span>

## <span data-ttu-id="da38f-103">概要</span><span class="sxs-lookup"><span data-stu-id="da38f-103">SYNOPSIS</span></span>
<span data-ttu-id="da38f-104">プロセスが停止するまで、次の入力を受け取るのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="da38f-104">Waits for the processes to be stopped before accepting more input.</span></span>

## <span data-ttu-id="da38f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="da38f-105">SYNTAX</span></span>

### <span data-ttu-id="da38f-106">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="da38f-106">Name (Default)</span></span>

```
Wait-Process [-Name] <String[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="da38f-107">Id</span><span class="sxs-lookup"><span data-stu-id="da38f-107">Id</span></span>

```
Wait-Process [-Id] <Int32[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="da38f-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="da38f-108">InputObject</span></span>

```
Wait-Process [[-Timeout] <Int32>] -InputObject <Process[]> [<CommonParameters>]
```

## <span data-ttu-id="da38f-109">Description</span><span class="sxs-lookup"><span data-stu-id="da38f-109">DESCRIPTION</span></span>

<span data-ttu-id="da38f-110">**Wait Process** コマンドレットは、実行中の1つ以上のプロセスが、入力を受け入れる前に停止するのを待機します。</span><span class="sxs-lookup"><span data-stu-id="da38f-110">The **Wait-Process** cmdlet waits for one or more running processes to be stopped before accepting input.</span></span>
<span data-ttu-id="da38f-111">PowerShell コンソールでは、このコマンドレットにより、プロセスが停止するまでコマンドプロンプトが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="da38f-111">In the PowerShell console, this cmdlet suppresses the command prompt until the processes are stopped.</span></span>
<span data-ttu-id="da38f-112">プロセスは、プロセス名またはプロセス ID (PID) を使用して指定することも、プロセスオブジェクトを **待機プロセス** にパイプすることもできます。</span><span class="sxs-lookup"><span data-stu-id="da38f-112">You can specify a process by process name or process ID (PID), or pipe a process object to **Wait-Process**.</span></span>

<span data-ttu-id="da38f-113">**待機プロセス** は、ローカルコンピューター上で実行されているプロセスでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="da38f-113">**Wait-Process** works only on processes running on the local computer.</span></span>

## <span data-ttu-id="da38f-114">例</span><span class="sxs-lookup"><span data-stu-id="da38f-114">EXAMPLES</span></span>

### <span data-ttu-id="da38f-115">例 1: プロセスを停止して待機する</span><span class="sxs-lookup"><span data-stu-id="da38f-115">Example 1: Stop a process and wait</span></span>

```
PS C:\> $nid = (Get-Process notepad).id
PS C:\> Stop-Process -Id $nid
PS C:\> Wait-Process -Id $nid
```

<span data-ttu-id="da38f-116">この例では、メモ帳のプロセスを停止し、プロセスが停止するまで待機してから、次のコマンドに進みます。</span><span class="sxs-lookup"><span data-stu-id="da38f-116">This example stops the Notepad process and then waits for the process to be stopped before it continues with the next command.</span></span>

<span data-ttu-id="da38f-117">最初のコマンドは、 **Get process** コマンドレットを使用して、メモ帳のプロセスの ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="da38f-117">The first command uses the **Get-Process** cmdlet to get the ID of the Notepad process.</span></span>
<span data-ttu-id="da38f-118">ID は $nid 変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="da38f-118">It stores the ID in the $nid variable.</span></span>

<span data-ttu-id="da38f-119">2番目のコマンドは、Stop-Process コマンドレットを使用して、$nid に格納されている ID を使用してプロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="da38f-119">The second command uses the Stop-Process cmdlet to stop the process with the ID stored in $nid.</span></span>

<span data-ttu-id="da38f-120">3番目のコマンドは、 **待機プロセス** を使用して、Notepad プロセスが停止するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="da38f-120">The third command uses **Wait-Process** to wait until the Notepad process is stopped.</span></span>
<span data-ttu-id="da38f-121">プロセスを識別するために、**待機プロセス** の *Id* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="da38f-121">It uses the *Id* parameter of **Wait-Process** to identify the process.</span></span>

### <span data-ttu-id="da38f-122">例 2: プロセスを指定する</span><span class="sxs-lookup"><span data-stu-id="da38f-122">Example 2: Specifying a process</span></span>

```
PS C:\> $p = Get-Process notepad
PS C:\> Wait-Process -Id $p.id
PS C:\> Wait-Process -Name "notepad"
PS C:\> Wait-Process -InputObject $p
```

<span data-ttu-id="da38f-123">これらのコマンドは、プロセスを **待機** するプロセスを指定する3つの異なる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="da38f-123">These commands show three different methods of specifying a process to **Wait-Process**.</span></span>
<span data-ttu-id="da38f-124">最初のコマンドは、メモ帳のプロセスを取得し、$p 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="da38f-124">The first command gets the Notepad process and stores it in the $p variable.</span></span>

<span data-ttu-id="da38f-125">2番目のコマンドは *Id* パラメーターを使用し、3番目のコマンドは *Name* パラメーターを使用し、4番目のコマンドは *InputObject* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="da38f-125">The second command uses the *Id* parameter, the third command uses the *Name* parameter, and the fourth command uses the *InputObject* parameter.</span></span>

<span data-ttu-id="da38f-126">これらのコマンドの結果はすべて同じであり、置き換えて使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="da38f-126">These commands have the same results and can be used interchangeably.</span></span>

### <span data-ttu-id="da38f-127">例 3: 指定した時間だけプロセスを待機する</span><span class="sxs-lookup"><span data-stu-id="da38f-127">Example 3: Wait for processes for a specified time</span></span>

```
PS C:\> Wait-Process -Name outlook, winword -Timeout 30
```

<span data-ttu-id="da38f-128">このコマンドは、Outlook と Winword の各プロセスが停止するまで 30 秒間待ちます。</span><span class="sxs-lookup"><span data-stu-id="da38f-128">This command waits 30 seconds for the Outlook and Winword processes to stop.</span></span>
<span data-ttu-id="da38f-129">プロセスがいずれも停止しない場合、コマンドレットによって未終了エラーが表示され、コマンド プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da38f-129">If both processes are not stopped, the cmdlet displays a non-terminating error and the command prompt.</span></span>

## <span data-ttu-id="da38f-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="da38f-130">PARAMETERS</span></span>

### <span data-ttu-id="da38f-131">-Id</span><span class="sxs-lookup"><span data-stu-id="da38f-131">-Id</span></span>

<span data-ttu-id="da38f-132">プロセスのプロセス ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="da38f-132">Specifies the process IDs of the processes.</span></span>
<span data-ttu-id="da38f-133">複数の ID を指定するには、ID をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="da38f-133">To specify multiple IDs, use commas to separate the IDs.</span></span>
<span data-ttu-id="da38f-134">プロセスの PID を検索するには、「」と入力 `Get-Process` します。</span><span class="sxs-lookup"><span data-stu-id="da38f-134">To find the PID of a process, type `Get-Process`.</span></span>

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

### <span data-ttu-id="da38f-135">-InputObject</span><span class="sxs-lookup"><span data-stu-id="da38f-135">-InputObject</span></span>

<span data-ttu-id="da38f-136">プロセス オブジェクトを送信して、プロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="da38f-136">Specifies the processes by submitting process objects.</span></span>
<span data-ttu-id="da38f-137">プロセスオブジェクトが格納されている変数を入力するか、Get-Process コマンドレットなどのプロセスオブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="da38f-137">Enter a variable that contains the process objects, or type a command or expression that gets the process objects, such as the Get-Process cmdlet.</span></span>

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

### <span data-ttu-id="da38f-138">-Name</span><span class="sxs-lookup"><span data-stu-id="da38f-138">-Name</span></span>

<span data-ttu-id="da38f-139">プロセスのプロセス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="da38f-139">Specifies the process names of the processes.</span></span>
<span data-ttu-id="da38f-140">複数の名前を指定するには、名前をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="da38f-140">To specify multiple names, use commas to separate the names.</span></span>
<span data-ttu-id="da38f-141">ワイルドカード文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="da38f-141">Wildcard characters are not supported.</span></span>

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

### <span data-ttu-id="da38f-142">-タイムアウト</span><span class="sxs-lookup"><span data-stu-id="da38f-142">-Timeout</span></span>

<span data-ttu-id="da38f-143">このコマンドレットが、指定されたプロセスを停止するまで待機する最大時間を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="da38f-143">Specifies the maximum time, in seconds, that this cmdlet waits for the specified processes to stop.</span></span>
<span data-ttu-id="da38f-144">この時間が経過すると、まだ実行中のプロセスの一覧を示す未終了エラーが表示され、待機動作が終了します。</span><span class="sxs-lookup"><span data-stu-id="da38f-144">When this interval expires, the command displays a non-terminating error that lists the processes that are still running, and ends the wait.</span></span>
<span data-ttu-id="da38f-145">既定では、タイムアウトはありません。</span><span class="sxs-lookup"><span data-stu-id="da38f-145">By default, there is no time-out.</span></span>

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

### <span data-ttu-id="da38f-146">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="da38f-146">CommonParameters</span></span>

<span data-ttu-id="da38f-147">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="da38f-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="da38f-148">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da38f-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="da38f-149">入力</span><span class="sxs-lookup"><span data-stu-id="da38f-149">INPUTS</span></span>

### <span data-ttu-id="da38f-150">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="da38f-150">System.Diagnostics.Process</span></span>

<span data-ttu-id="da38f-151">パイプを使用してプロセスオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="da38f-151">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="da38f-152">出力</span><span class="sxs-lookup"><span data-stu-id="da38f-152">OUTPUTS</span></span>

### <span data-ttu-id="da38f-153">なし</span><span class="sxs-lookup"><span data-stu-id="da38f-153">None</span></span>

<span data-ttu-id="da38f-154">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="da38f-154">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="da38f-155">注</span><span class="sxs-lookup"><span data-stu-id="da38f-155">NOTES</span></span>

<span data-ttu-id="da38f-156">コマンドレットは、Windows プラットフォームでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="da38f-156">The cmdlet is only supported on Windows platforms.</span></span>

<span data-ttu-id="da38f-157">このコマンドレットは、 **system.servicemodel クラスの** **waitforexit** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="da38f-157">This cmdlet uses the **WaitForExit** method of the **System.Diagnostics.Process** class.</span></span>

## <span data-ttu-id="da38f-158">関連リンク</span><span class="sxs-lookup"><span data-stu-id="da38f-158">RELATED LINKS</span></span>

[<span data-ttu-id="da38f-159">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="da38f-159">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="da38f-160">Get-Process</span><span class="sxs-lookup"><span data-stu-id="da38f-160">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="da38f-161">Start-Process</span><span class="sxs-lookup"><span data-stu-id="da38f-161">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="da38f-162">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="da38f-162">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="da38f-163">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="da38f-163">Wait-Process</span></span>](Wait-Process.md)
