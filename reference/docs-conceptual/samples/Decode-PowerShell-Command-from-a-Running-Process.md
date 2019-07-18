---
ms.date: 11/13/2018
keywords: PowerShell, コマンドレット
title: 実行中のプロセスからの PowerShell コマンドをデコードする
author: randomnote1
ms.openlocfilehash: a6c01d8edf67aba6c47350a97cc0ceec4801ad29
ms.sourcegitcommit: bc42c9166857147a1ecf9924b718d4a48eb901e3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2019
ms.locfileid: "66470971"
---
# <a name="decode-a-powershell-command-from-a-running-process"></a>実行中のプロセスからの PowerShell コマンドをデコードする

実行している PowerShell プロセスで大量のリソースが使用されることがあります。
このプロセスは、[タスク スケジューラ][] ジョブまたは [SQL Server エージェント][] ジョブのコンテキストで実行されている可能性があります。 複数の PowerShell プロセスが実行されている場合、どのプロセスで問題が発生しているのかわかりにくいことがあります。 この記事では、PowerShell プロセスで現在実行中のスクリプト ブロックをデコードする方法を示します。

## <a name="create-a-long-running-process"></a>実行時間の長いプロセスを作成する

このシナリオを示すため、新しい PowerShell ウィンドウを開き、次のコードを実行します。 10 分間にわたって 1 分ごとに数値を出力する PowerShell コマンドが実行されます。

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

## <a name="view-the-process"></a>プロセスを表示する

PowerShell で実行されているコマンドの本体は、[Win32_Process][] クラスの **CommandLine** プロパティに格納されています。 コマンドがエンコードされたコマンドである場合、**CommandLine** プロパティには文字列 "EncodedCommand" が含まれています。 この情報を使用して、次のプロセスにより、エンコードされたコマンドを難読化解除できます。

管理者として PowerShell を開始します。 PowerShell を管理者として実行することが重要です。そうしないと、実行中のプロセスのクエリを実行しても結果は返されません。

次のコマンドを実行し、エンコードされたコマンドを含むすべての PowerShell プロセスを取得します。

```powershell
$powerShellProcesses = Get-CimInstance -ClassName Win32_Process -Filter 'CommandLine LIKE "%EncodedCommand%"'
```

次のコマンドでは、プロセス ID とエンコードされたコマンドを含むカスタム PowerShell オブジェクトが作成されます。

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

これで、エンコードされたコマンドをデコードできるようになります。 次のスニペットは、コマンドの詳細オブジェクトを反復処理して、エンコードされたコマンドをデコードし、詳しい調査のためのデコードされたコマンドをオブジェクトに追加します。

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

デコードされたコマンド プロパティを選択することで、デコードされたコマンドを確認できるようになります。

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
