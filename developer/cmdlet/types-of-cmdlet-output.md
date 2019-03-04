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
ms.openlocfilehash: 3efa98c7aa22fdaee8042bae99282aea0618ef5f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853928"
---
# <a name="types-of-cmdlet-output"></a>コマンドレットの出力の種類

PowerShell は、出力を生成するためのコマンドレットを呼び出すことができるいくつかのメソッドを提供します。 これらのメソッドは、成功した場合のデータ ストリームやエラーのデータ ストリームなどの特定のデータ ストリームに出力を書き込む、特定の操作を使用します。 この記事では、出力とそれらを生成するために使用するメソッドの型について説明します。

## <a name="types-of-output"></a>出力の種類

### <a name="success-output"></a>成功した場合の出力

コマンドレットは、次のコマンドにパイプラインによって処理できるオブジェクトを返すことによって、成功を報告できます。 このコマンドレットでは、そのアクションが正常に実行、コマンドレットは呼び出し、 [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッド。 代わりに、このメソッドを呼び出すことをお勧め、 [System.Console.WriteLine](/dotnet/api/System.Console.WriteLine)または[System.Management.Automation.Host.PSHostUserInterface.WriteLine](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.WriteLine)メソッド。

行うことができます、 **PassThru**スイッチを通常のオブジェクトを返さないコマンドレットのパラメーター。
ときに、 **PassThru**にスイッチ パラメーターをコマンドラインに指定すると、コマンドレットがオブジェクトを取得する要求。 あるコマンドレットの例については、 **PassThru**パラメーターを参照してください[Add-history](/powershell/module/Microsoft.PowerShell.Core/Add-History)します。

### <a name="error-output"></a>エラー出力

コマンドレットは、エラーを報告できます。 コマンドレットは、終了エラーが発生したときに例外をスローします。 コマンドレットを呼び出す、未終了エラーが発生したときに、 [System.Management.Automation.Provider.CmdletProvider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError)エラー データのストリームにエラー レコードを送信する方法。 エラー報告の詳細については、次を参照してください。[エラー Reporting 概念](./error-reporting-concepts.md)します。

### <a name="verbose-output"></a>詳細出力

コマンドレットできますを提供します。 役に立つ情報、コマンドレットを呼び出してレコードの処理が正しく中に、 [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)メソッド。 メソッドは、アクションは続行される方法を示す詳細なメッセージを生成します。

既定では、詳細メッセージは表示されません。 指定することができます、 **Verbose**パラメーターをこれらのメッセージを表示するコマンドレットを実行するとします。 **詳細な**はすべてのコマンドレットを使用できる一般的なパラメーターです。

### <a name="progress-output"></a>進行状況の出力

コマンドレットは、コマンドレットがディレクトリの再帰的にコピーするなど、完了に長い時間がかかるタスクを実行するときに進行状況に関する情報を提供することができます。 呼び出し、コマンドレットの進行状況に関する情報を表示するのには、 [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress)メソッド。

### <a name="debug-output"></a>デバッグ出力

コマンドレットは、コマンドレット コードのトラブルシューティングに役立つものをデバッグ メッセージを提供できます。 呼び出し、コマンドレットのデバッグ情報を表示するのには、 [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)メソッド。

既定では、デバッグ メッセージは表示されません。 指定することができます、**デバッグ**パラメーターをこれらのメッセージを表示するコマンドレットを実行するとします。 **デバッグ**はすべてのコマンドレットを使用できる一般的なパラメーターです。

### <a name="warning-output"></a>警告の出力

コマンドレットは呼び出すことによって警告メッセージを表示することができます、 [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning)メソッド。

既定では、警告メッセージが表示されます。 ただし、使用して警告メッセージを構成することができます、`$WarningPreference`変数またはを使用して、 **Verbose**と**デバッグ**コマンドレットが呼び出されたときにパラメーター。

## <a name="displaying-output"></a>出力を表示します。

すべての書き込みメソッドの呼び出しには、コンテンツの表示を特定のランタイム変数によって決まります。 例外は、 [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッド。 これらの変数を使用するには、適切なコードで呼び出しの正しい場所を記述して、出力が表示される場合、またはについて心配せずの操作を行うことができます。

## <a name="accessing-the-output-functionality-of-a-host-application"></a>ホスト アプリケーションの出力の機能にアクセスします。

直接 PowerShell ランタイムからホスト アプリケーションの出力機能にアクセスするコマンドレットを設計することもできます。 ホストの代わりに PowerShell で提供される Api を使用して[System.Console](/dotnet/api/System.Console)または[System.Windows.Forms](/dotnet/api/System.Windows.Forms)により、コマンドレットは、さまざまなホストで動作するようになります。 例: **powershell.exe**コンソールのホスト、 **powershell_ise.exe**グラフィカル ホストでは、PowerShell リモート処理ホスト、およびサードパーティのホスト。

## <a name="see-also"></a>関連項目

[エラー報告の概念](./error-reporting-concepts.md)

[コマンドレットの概要](./cmdlet-overview.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)