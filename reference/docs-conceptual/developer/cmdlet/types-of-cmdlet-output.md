---
title: コマンドレットの出力の種類 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell SDK], output
ms.assetid: 547e6695-e936-4cac-a90b-417d0dab393d
caps.latest.revision: 12
ms.openlocfilehash: de21d9ebfec4f23d3819695df225f7a230864a7b
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561416"
---
# <a name="types-of-cmdlet-output"></a>コマンドレットの出力の種類

PowerShell には、コマンドレットによって出力を生成するために呼び出すことができるメソッドがいくつか用意されています。 これらのメソッドは、特定の操作を使用して、成功データストリームやエラーデータストリームなどの特定のデータストリームに出力を書き込みます。 この記事では、出力の種類と、それらを生成するために使用されるメソッドについて説明します。

## <a name="types-of-output"></a>出力の種類

### <a name="success-output"></a>成功の出力

コマンドレットは、パイプラインの次のコマンドで処理できるオブジェクトを返すことで成功を報告できます。 コマンドレットは、アクションを正常に実行した後、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッドを呼び出します。 [PSHostUserInterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.WriteLine)メソッドまたはメソッドの代わりに、このメソッドを呼び出すことをお勧めします。この[メソッドは、](/dotnet/api/System.Console.WriteLine)

通常はオブジェクトを返さないコマンドレットには、 **PassThru**スイッチパラメーターを指定できます。
コマンドラインで**PassThru**スイッチパラメーターを指定すると、コマンドレットはオブジェクトを返すように求められます。 **PassThru**パラメーターを持つコマンドレットの例については、「[追加-履歴](/powershell/module/Microsoft.PowerShell.Core/Add-History)」を参照してください。

### <a name="error-output"></a>エラー出力

コマンドレットはエラーを報告できます。 終了エラーが発生すると、コマンドレットは例外をスローします。 終了しないエラーが発生すると、コマンドレットは[WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError)メソッドを呼び出して、エラーレコードをエラーデータストリームに送信しています。 エラー報告の詳細については、「[エラーレポートの概念](./error-reporting-concepts.md)」を参照してください。

### <a name="verbose-output"></a>詳細出力

コマンドレットは、使用しているユーザーにとって有用な情報を提供します。また、コマンドレットで[は、このメソッドを](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)呼び出すことによってレコードが正しく処理されます。 メソッドは、アクションの進行状況を示す詳細メッセージを生成します。

既定では、詳細メッセージは表示されません。 これらのメッセージを表示するには、コマンドレットを実行するときに**Verbose**パラメーターを指定します。 **Verbose**は、すべてのコマンドレットで使用できる共通のパラメーターです。

### <a name="progress-output"></a>進行状況の出力

コマンドレットは、ディレクトリを再帰的にコピーするなど、完了までに時間がかかるタスクを実行しているときに、進行状況に関する情報を提供します。 進行状況に関する情報を表示するには、コマンドレットで[system.servicemodel メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress)呼び出します。

### <a name="debug-output"></a>デバッグ出力

コマンドレットは、コマンドレットコードのトラブルシューティングに役立つデバッグメッセージを提供できます。 デバッグ情報を表示するには、コマンドレットに[よって、system.string メソッドが](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)呼び出されます。

既定では、デバッグメッセージは表示されません。 コマンドレットを実行してこれらのメッセージを表示する場合は、 **Debug**パラメーターを指定できます。 **Debug**は、すべてのコマンドレットで使用できる共通パラメーターです。

### <a name="warning-output"></a>警告出力

コマンドレット[では、system.string メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning)呼び出すことで警告メッセージを表示できます。

既定では、警告メッセージが表示されます。 ただし、警告メッセージを構成するには、変数を使用する `$WarningPreference` か、コマンドレットが呼び出されたときに**Verbose**パラメーターと**Debug**パラメーターを使用します。

## <a name="displaying-output"></a>出力の表示

すべての書き込みメソッド呼び出しでは、コンテンツの表示は特定のランタイム変数によって決定されます。 例外として、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッドがあります。 これらの変数を使用すると、適切な書き込み呼び出しをコード内の適切な場所で行うことができ、出力を表示するタイミングやタイミングを気にする必要がなくなります。

## <a name="accessing-the-output-functionality-of-a-host-application"></a>ホストアプリケーションの出力機能へのアクセス

PowerShell ランタイムを使用してホストアプリケーションの出力機能に直接アクセスするようにコマンドレットを設計することもできます。 [System.](/dotnet/api/System.Console) [Windows. フォーム](/dotnet/api/System.Windows.Forms)ではなく、PowerShell によって提供されるホスト api を使用すると、コマンドレットがさまざまなホストで動作することが保証されます。 たとえば、 **powershell**のコンソールホスト、 **powershell_ise**のグラフィカルホスト、powershell リモート処理ホスト、サードパーティのホストなどです。

## <a name="see-also"></a>関連項目

[エラー レポートの概念](./error-reporting-concepts.md)

[コマンドレットの概要](./cmdlet-overview.md)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
