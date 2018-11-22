---
ms.date: 11/13/2018
keywords: PowerShell, コマンドレット
title: 実行中のプロセスからの PowerShell コマンドをデコードする
author: randomnote1
ms.openlocfilehash: a0602070a8c5b60ce0bb09e227690f48d970a868
ms.sourcegitcommit: 91786b03704fbd2d185f674df0bc67faddfb6288
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2018
ms.locfileid: "51619204"
---
# <a name="decode-a-powershell-command-from-a-running-process"></a><span data-ttu-id="99617-103">実行中のプロセスからの PowerShell コマンドをデコードする</span><span class="sxs-lookup"><span data-stu-id="99617-103">Decode a PowerShell command from a running process</span></span>

<span data-ttu-id="99617-104">実行しているプロセスが大量のリソースを占有して PowerShell があります。</span><span class="sxs-lookup"><span data-stu-id="99617-104">At times, you may have a PowerShell process running that is taking up a large amount of resources.</span></span>
<span data-ttu-id="99617-105">このプロセスのコンテキストで実行でき、[タスク スケジューラ][]ジョブまたは[SQL Server エージェント][]ジョブ。</span><span class="sxs-lookup"><span data-stu-id="99617-105">This process could be running in the context of a [Task Scheduler][] job or a [SQL Server Agent][] job.</span></span> <span data-ttu-id="99617-106">実行されている複数の PowerShell プロセスがある場合は、どのプロセスが、問題を表しますがわかりにくいができます。</span><span class="sxs-lookup"><span data-stu-id="99617-106">Where there are multiple PowerShell processes running, it can be difficult to know which process represents the problem.</span></span> <span data-ttu-id="99617-107">この記事では、PowerShell プロセスで現在実行中のスクリプト ブロックをデコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="99617-107">This article shows how to decode a script block that a PowerShell process is currently running.</span></span>

## <a name="create-a-long-running-process"></a><span data-ttu-id="99617-108">実行時間の長いプロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="99617-108">Create a long running process</span></span>

<span data-ttu-id="99617-109">このシナリオを示すためには、新しい PowerShell ウィンドウを開き、次のコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="99617-109">To demonstrate this scenario, open a new PowerShell window and run the following code.</span></span> <span data-ttu-id="99617-110">10 分の 1 分間隔の数値を出力するための PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="99617-110">It executes a PowerShell command that outputs a number every minute for 10 minutes.</span></span>

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

## <a name="view-the-process"></a><span data-ttu-id="99617-111">プロセスを表示します。</span><span class="sxs-lookup"><span data-stu-id="99617-111">View the process</span></span>

<span data-ttu-id="99617-112">PowerShell が実行されているコマンドの本文が格納されている、 **CommandLine**のプロパティ、 [Win32_Process][]クラス。</span><span class="sxs-lookup"><span data-stu-id="99617-112">The body of the command which PowerShell is executing is stored in the **CommandLine** property of the [Win32_Process][] class.</span></span> <span data-ttu-id="99617-113">コマンドの場合、[コマンドでエンコードされた][]、 **CommandLine**プロパティに文字列"EncodedCommand"が含まれています。</span><span class="sxs-lookup"><span data-stu-id="99617-113">If the command is an [encoded command][], the **CommandLine** property contains the string "EncodedCommand".</span></span> <span data-ttu-id="99617-114">この情報を使用してエンコードされたコマンドは、次のプロセスを使用して難読化解除できます。</span><span class="sxs-lookup"><span data-stu-id="99617-114">Using this information, the encoded command can be de-obfuscated via the following process.</span></span>

<span data-ttu-id="99617-115">管理者として PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="99617-115">Start PowerShell as Administrator.</span></span> <span data-ttu-id="99617-116">PowerShell を管理者として実行されている重要なは、それ以外の場合の結果は返されません、実行中のプロセスを照会するときに。</span><span class="sxs-lookup"><span data-stu-id="99617-116">It is vital that PowerShell is running as administrator, otherwise no results are returned when querying the running processes.</span></span>

<span data-ttu-id="99617-117">すべてのエンコード済みのコマンドが PowerShell プロセスを取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="99617-117">Execute the following command to get all of the PowerShell processes that have an encoded command:</span></span>

```powershell
$powerShellProcesses = Get-CimInstance -ClassName Win32_Process -Filter 'CommandLine LIKE "%EncodedCommand%"'
```

<span data-ttu-id="99617-118">次のコマンドは、プロセス ID とエンコードされたコマンドを含むカスタム PowerShell オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="99617-118">The following command creates a custom PowerShell object that contains the process ID and the encoded command.</span></span>

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

<span data-ttu-id="99617-119">今すぐでエンコードされたコマンドをデコードできます。</span><span class="sxs-lookup"><span data-stu-id="99617-119">Now the encoded command can be decoded.</span></span> <span data-ttu-id="99617-120">次のスニペットは、コマンドの詳細オブジェクトを反復処理し、エンコード済みのコマンドをデコードし、詳しい調査のためのオブジェクトに、デコードされたコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="99617-120">The following snippet iterates over the command details object, decodes the encoded command, and adds the decoded command back to the object for further investigation.</span></span>

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

<span data-ttu-id="99617-121">デコードされたコマンドは、デコードされた command プロパティを選択してここで確認できます。</span><span class="sxs-lookup"><span data-stu-id="99617-121">The decoded command can now be reviewed by selecting the decoded command property.</span></span>

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
[コマンドでエンコードされた]: /powershell/scripting/core-powershell/console/powershell.exe-command-line-help#-encodedcommand-
[encoded command]: /powershell/scripting/core-powershell/console/powershell.exe-command-line-help#-encodedcommand-
