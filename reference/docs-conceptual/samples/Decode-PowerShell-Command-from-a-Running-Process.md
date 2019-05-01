---
ms.date: 11/13/2018
keywords: PowerShell, コマンドレット
title: 実行中のプロセスからの PowerShell コマンドをデコードする
author: randomnote1
ms.openlocfilehash: a0602070a8c5b60ce0bb09e227690f48d970a868
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086240"
---
# <a name="decode-a-powershell-command-from-a-running-process"></a><span data-ttu-id="f4f14-103">実行中のプロセスからの PowerShell コマンドをデコードする</span><span class="sxs-lookup"><span data-stu-id="f4f14-103">Decode a PowerShell command from a running process</span></span>

<span data-ttu-id="f4f14-104">実行している PowerShell プロセスで大量のリソースが使用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f4f14-104">At times, you may have a PowerShell process running that is taking up a large amount of resources.</span></span>
<span data-ttu-id="f4f14-105">このプロセスは、[タスク スケジューラ][] ジョブまたは [SQL Server エージェント][] ジョブのコンテキストで実行されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f4f14-105">This process could be running in the context of a [Task Scheduler][] job or a [SQL Server Agent][] job.</span></span> <span data-ttu-id="f4f14-106">複数の PowerShell プロセスが実行されている場合、どのプロセスで問題が発生しているのかわかりにくいことがあります。</span><span class="sxs-lookup"><span data-stu-id="f4f14-106">Where there are multiple PowerShell processes running, it can be difficult to know which process represents the problem.</span></span> <span data-ttu-id="f4f14-107">この記事では、PowerShell プロセスで現在実行中のスクリプト ブロックをデコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f4f14-107">This article shows how to decode a script block that a PowerShell process is currently running.</span></span>

## <a name="create-a-long-running-process"></a><span data-ttu-id="f4f14-108">実行時間の長いプロセスを作成する</span><span class="sxs-lookup"><span data-stu-id="f4f14-108">Create a long running process</span></span>

<span data-ttu-id="f4f14-109">このシナリオを示すため、新しい PowerShell ウィンドウを開き、次のコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="f4f14-109">To demonstrate this scenario, open a new PowerShell window and run the following code.</span></span> <span data-ttu-id="f4f14-110">10 分間にわたって 1 分ごとに数値を出力する PowerShell コマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f4f14-110">It executes a PowerShell command that outputs a number every minute for 10 minutes.</span></span>

```powershell
powershell.exe -Command {
    $i = 1
    while ( $i -le 10 )
    {
        Write-Output -InputObject $i
        Start-Sleep -Seconds 60
        $i++
    }
}
```

## <a name="view-the-process"></a><span data-ttu-id="f4f14-111">プロセスを表示する</span><span class="sxs-lookup"><span data-stu-id="f4f14-111">View the process</span></span>

<span data-ttu-id="f4f14-112">PowerShell で実行されているコマンドの本体は、[Win32_Process][] クラスの **CommandLine** プロパティに格納されています。</span><span class="sxs-lookup"><span data-stu-id="f4f14-112">The body of the command which PowerShell is executing is stored in the **CommandLine** property of the [Win32_Process][] class.</span></span> <span data-ttu-id="f4f14-113">コマンドが[エンコードされたコマンド][]の場合、**CommandLine** プロパティには文字列 "EncodedCommand" が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4f14-113">If the command is an [encoded command][], the **CommandLine** property contains the string "EncodedCommand".</span></span> <span data-ttu-id="f4f14-114">この情報を使用して、次のプロセスにより、エンコードされたコマンドを難読化解除できます。</span><span class="sxs-lookup"><span data-stu-id="f4f14-114">Using this information, the encoded command can be de-obfuscated via the following process.</span></span>

<span data-ttu-id="f4f14-115">管理者として PowerShell を開始します。</span><span class="sxs-lookup"><span data-stu-id="f4f14-115">Start PowerShell as Administrator.</span></span> <span data-ttu-id="f4f14-116">PowerShell を管理者として実行することが重要です。そうしないと、実行中のプロセスのクエリを実行しても結果は返されません。</span><span class="sxs-lookup"><span data-stu-id="f4f14-116">It is vital that PowerShell is running as administrator, otherwise no results are returned when querying the running processes.</span></span>

<span data-ttu-id="f4f14-117">次のコマンドを実行し、エンコードされたコマンドを含むすべての PowerShell プロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="f4f14-117">Execute the following command to get all of the PowerShell processes that have an encoded command:</span></span>

```powershell
$powerShellProcesses = Get-CimInstance -ClassName Win32_Process -Filter 'CommandLine LIKE "%EncodedCommand%"'
```

<span data-ttu-id="f4f14-118">次のコマンドでは、プロセス ID とエンコードされたコマンドを含むカスタム PowerShell オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f4f14-118">The following command creates a custom PowerShell object that contains the process ID and the encoded command.</span></span>

```powershell
$commandDetails = $powerShellProcesses | Select-Object -Property ProcessId,
@{
    name       = 'EncodedCommand'
    expression = {
        if ( $_.CommandLine -match 'encodedCommand (.*) -inputFormat' )
        {
            return $matches[1]
        }
    }
}
```

<span data-ttu-id="f4f14-119">これで、エンコードされたコマンドをデコードできるようになります。</span><span class="sxs-lookup"><span data-stu-id="f4f14-119">Now the encoded command can be decoded.</span></span> <span data-ttu-id="f4f14-120">次のスニペットは、コマンドの詳細オブジェクトを反復処理して、エンコードされたコマンドをデコードし、詳しい調査のためのデコードされたコマンドをオブジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="f4f14-120">The following snippet iterates over the command details object, decodes the encoded command, and adds the decoded command back to the object for further investigation.</span></span>

```powershell
$commandDetails | ForEach-Object -Process {
    # Get the current process
    $currentProcess = $_

    # Convert the Base 64 string to a Byte Array
    $commandBytes = [System.Convert]::FromBase64String($currentProcess.EncodedCommand)

    # Convert the Byte Array to a string
    $decodedCommand = [System.Text.Encoding]::Unicode.GetString($commandBytes)

    # Add the decoded command back to the object
    $commandDetails |
        Where-Object -FilterScript { $_.ProcessId -eq $_.ProcessId } |
        Add-Member -MemberType NoteProperty -Name DecodedCommand -Value $decodedCommand
}
$commandDetails[0]
```

<span data-ttu-id="f4f14-121">デコードされたコマンド プロパティを選択することで、デコードされたコマンドを確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f4f14-121">The decoded command can now be reviewed by selecting the decoded command property.</span></span>

```output
ProcessId      : 8752
EncodedCommand : IAAKAAoACgAgAAoAIAAgACAAIAAkAGkAIAA9ACAAMQAgAAoACgAKACAACgAgACAAIAAgAHcAaABpAGwAZQAgACgAIAAkAGkAIAAtAG
                 wAZQAgADEAMAAgACkAIAAKAAoACgAgAAoAIAAgACAAIAB7ACAACgAKAAoAIAAKACAAIAAgACAAIAAgACAAIABXAHIAaQB0AGUALQBP
                 AHUAdABwAHUAdAAgAC0ASQBuAHAAdQB0AE8AYgBqAGUAYwB0ACAAJABpACAACgAKAAoAIAAKACAAIAAgACAAIAAgACAAIABTAHQAYQ
                 ByAHQALQBTAGwAZQBlAHAAIAAtAFMAZQBjAG8AbgBkAHMAIAA2ADAAIAAKAAoACgAgAAoAIAAgACAAIAAgACAAIAAgACQAaQArACsA
                 IAAKAAoACgAgAAoAIAAgACAAIAB9ACAACgAKAAoAIAAKAA==
DecodedCommand :
                     $i = 1

                     while ( $i -le 10 )

                     {

                         Write-Output -InputObject $i

                         Start-Sleep -Seconds 60

                         $i++

                     }
```

[タスク スケジューラ]: /windows/desktop/TaskSchd/task-scheduler-start-page
[Task Scheduler]: /windows/desktop/TaskSchd/task-scheduler-start-page
[SQL Server エージェント]: /sql/ssms/agent/sql-server-agent
[SQL Server Agent]: /sql/ssms/agent/sql-server-agent
[Win32_Process]: /windows/desktop/CIMWin32Prov/win32-process
[エンコードされたコマンド]: /powershell/scripting/core-powershell/console/powershell.exe-command-line-help#-encodedcommand-
[encoded command]: /powershell/scripting/core-powershell/console/powershell.exe-command-line-help#-encodedcommand-
