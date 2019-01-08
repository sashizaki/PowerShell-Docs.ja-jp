---
ms.date: 11/13/2018
keywords: PowerShell, コマンドレット
title: 実行中のプロセスからの PowerShell コマンドをデコードする
author: randomnote1
ms.openlocfilehash: a0602070a8c5b60ce0bb09e227690f48d970a868
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402294"
---
# <a name="decode-a-powershell-command-from-a-running-process"></a>実行中のプロセスからの PowerShell コマンドをデコードする

実行しているプロセスが大量のリソースを占有して PowerShell があります。
このプロセスのコンテキストで実行でき、[タスク スケジューラ][]ジョブまたは[SQL Server エージェント][]ジョブ。 実行されている複数の PowerShell プロセスがある場合は、どのプロセスが、問題を表しますがわかりにくいができます。 この記事では、PowerShell プロセスで現在実行中のスクリプト ブロックをデコードする方法を示します。

## <a name="create-a-long-running-process"></a>実行時間の長いプロセスを作成します。

このシナリオを示すためには、新しい PowerShell ウィンドウを開き、次のコードを実行します。 10 分の 1 分間隔の数値を出力するための PowerShell コマンドを実行します。

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

## <a name="view-the-process"></a>プロセスを表示します。

PowerShell が実行されているコマンドの本文が格納されている、 **CommandLine**のプロパティ、 [Win32_Process][]クラス。 コマンドの場合、[コマンドでエンコードされた][]、 **CommandLine**プロパティに文字列"EncodedCommand"が含まれています。 この情報を使用してエンコードされたコマンドは、次のプロセスを使用して難読化解除できます。

管理者として PowerShell を起動します。 PowerShell を管理者として実行されている重要なは、それ以外の場合の結果は返されません、実行中のプロセスを照会するときに。

すべてのエンコード済みのコマンドが PowerShell プロセスを取得するには、次のコマンドを実行します。

```powershell
$powerShellProcesses = Get-CimInstance -ClassName Win32_Process -Filter 'CommandLine LIKE "%EncodedCommand%"'
```

次のコマンドは、プロセス ID とエンコードされたコマンドを含むカスタム PowerShell オブジェクトを作成します。

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

今すぐでエンコードされたコマンドをデコードできます。 次のスニペットは、コマンドの詳細オブジェクトを反復処理し、エンコード済みのコマンドをデコードし、詳しい調査のためのオブジェクトに、デコードされたコマンドを追加します。

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

デコードされたコマンドは、デコードされた command プロパティを選択してここで確認できます。

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
[SQL Server エージェント]: /sql/ssms/agent/sql-server-agent
[Win32_Process]: /windows/desktop/CIMWin32Prov/win32-process
[コマンドでエンコードされた]: /powershell/scripting/core-powershell/console/powershell.exe-command-line-help#-encodedcommand-
