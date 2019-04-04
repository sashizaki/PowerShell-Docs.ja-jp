---
title: システムを変更するコマンドレットを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- should process [PowerShell Programmer's Guide]
- should continue [PowerShell Programmer's Guide]
- user feedback [PowerShell Programmer's Guide]
- confirm impact [PowerShell Programmer's Guide]
ms.assetid: 59be4120-1700-4d92-a308-ef4a32ccf11a
caps.latest.revision: 8
ms.openlocfilehash: bbe9f0213754d1cc47e0fd9a7a898bde916c0636
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055140"
---
# <a name="creating-a-cmdlet-that-modifies-the-system"></a>システムを変更するコマンドレットを作成する

場合によってコマンドレットは、Windows PowerShell ランタイムの状態だけでなく、システムの実行中の状態を変更する必要があります。 このような場合は、コマンドレットは、する必要がある、ユーザー、変更するかどうかを確認する機会が。

確認をサポートするには、コマンドレットは、2 つの処理を行う必要があります。

- 宣言を指定する場合は、コマンドレットが確認をサポートしている、 [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute)属性 SupportsShouldProcess キーワードを設定して`true`します。

- 呼び出す[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) (次の例で説明) とコマンドレットの実行中にします。

コマンドレットを公開の確認をサポートすることによって、`Confirm`と`WhatIf`は、Windows PowerShell によって提供され、コマンドレットの開発のガイドラインにも対応するパラメーター (コマンドレットの開発のガイドラインの詳細についてを参照してください[コマンドレットの開発ガイドライン](./cmdlet-development-guidelines.md)。)。

## <a name="changing-the-system"></a>システムを変更します。

「システムの変更」の動作は、Windows PowerShell の外部システムの状態を変更する可能性のあるすべてのコマンドレットを参照します。 たとえば、プロセスを有効にするか、ユーザー アカウントを無効にするまたはデータベース テーブルに行がすべての変更を確認する必要がありますシステムの追加を停止しています。 これに対し、データの読み取り、一時的な接続を確立したりする操作を使用して、システムは変更されず、一般に、確認を要求されません。 アクションが影響を制限する、Windows PowerShell ランタイム内でなどの 確認は必要ありませんも`set-variable`します。 可能性がある永続的な変更を加える可能性がありますいないコマンドレットを宣言する必要があります`SupportsShouldProcess`を呼び出すと[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)永続的な変更を加えるしようとしている場合のみです。

> [!NOTE]
> ShouldProcess 確認は、コマンドレットにのみ適用されます。 コマンドまたはスクリプトは、.NET メソッドまたはプロパティを直接呼び出すことによって、または Windows PowerShell の外部で呼び出し元のアプリケーション、システムの実行中の状態を変更します、この形式の確認できなくなります。

## <a name="the-stopproc-cmdlet"></a>StopProc コマンドレット

このトピックでは Get-proc コマンドレットを使用して取得するプロセスを停止しようとする停止 Proc コマンドレットの説明 (で説明されている[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md))。

このセクションのトピックで、次のとおりです。

- [コマンドレットを定義します。](#Defining-the-Cmdlet)

- [システムの変更のパラメーターを定義します。](#Defining-Parameters-for-System-Modification)

- [入力処理メソッドをオーバーライドします。](#Overriding-an-Input-Processing-Method)

- [ShouldProcess メソッドの呼び出し](#Calling-the-ShouldProcess-Method)

- [ShouldContinue メソッドを呼び出す](#Calling-the-ShouldContinue-Method)

- [入力の処理を停止しています](#Stopping-Input-Processing)

- [コード サンプル](#Code-Sample)

- [オブジェクトの種類を定義して、書式設定](#Defining-Object-Types-and-Formatting)

- [コマンドレットを構築](#Building-the-Cmdlet)

- [テスト コマンドレット](#Testing-the-Cmdlet)

## <a name="defining-the-cmdlet"></a>コマンドレットを定義します。

コマンドレットの作成の最初の手順は常に、コマンドレットの名前を付けると、コマンドレットを実装する .NET クラスを宣言します。 システムを変更するコマンドレットを記述するため、それに応じて名前にする必要があります。 このコマンドレットが停止システム プロセス、ため、ここで選択した動詞名が"Stop"がによって定義された、 [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)クラスの名詞コマンドレットは、プロセスを停止することを示すには、"Proc"とします。 承認されたコマンドレット動詞の詳細については、[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)を参照してください。

この停止 Proc コマンドレットのクラス定義を次に示します。

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

注意してくださいで、 [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute)宣言、`SupportsShouldProcess`属性のキーワードに設定されている`true`に呼び出しを実行するコマンドレットを有効にする[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)します。 このキーワードを設定することがなく、`Confirm`と`WhatIf`パラメーターは、ユーザーには使用できません。

### <a name="extremely-destructive-actions"></a>非常に破壊的な操作

一部の操作は、アクティブなハード ディスク パーティションを再フォーマットなどの非常に破壊的なです。 このような場合は、コマンドレットを設定する必要があります`ConfirmImpact`  =  `ConfirmImpact.High`を宣言するとき、 [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute)属性。 この設定では、ユーザーが指定されていない場合でも要求をユーザーが確認するコマンドレットを強制、`Confirm`パラメーター。 ただし、コマンドレットの開発者が過剰な使用を回避する必要があります`ConfirmImpact`のユーザー アカウントを削除するなど、だけ可能性がある破壊的な操作の場合。 ある`ConfirmImpact`に設定されている[System.Management.Automation.Confirmimpact.High](/dotnet/api/System.Management.Automation.ConfirmImpact.High)します。

同様に、いくつかの操作は、これらは理論的に変更が Windows PowerShell の外部システムの実行中の状態を破壊する可能性がありますではありません。 このようなコマンドレットを設定できます`ConfirmImpact`に[System.Management.Automation.Confirmimpact.Low](/dotnet/api/system.management.automation.confirmimpact?view=powershellsdk-1.1.0)します。 これにより、確認要求が、ユーザーがメディアへの影響と、影響の大きいだけの操作を確認する要求されましたが省略されます。

## <a name="defining-parameters-for-system-modification"></a>システムの変更のパラメーターを定義します。

このセクションでは、サポート システムの変更に必要なものも含め、このコマンドレットのパラメーターを定義する方法について説明します。 参照してください[そのプロセスのコマンドラインの入力パラメーターを追加する](./adding-parameters-that-process-command-line-input.md)パラメーターの定義に関する一般的な情報が必要な場合。

停止 Proc コマンドレットは、3 つのパラメーターを定義します。 `Name`、 `Force`、および`PassThru`します。

`Name`パラメーターに対応、`Name`プロセスの入力オブジェクトのプロパティ。 注意を`Name`を停止する名前付きプロセスがあるない場合、コマンドレットが失敗すると、このサンプルではパラメーターが必須では。

`Force`パラメーターにより、ユーザーへの呼び出しをオーバーライドする[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)します。 実際には、いずれかのコマンドレットを呼び出す[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)する必要がありますが、`Force`パラメーターようにとき`Force`を指定すると、コマンドレットの呼び出しをスキップします[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)操作を続行します。 この影響を及ぼさないようにへの呼び出しに注意してください[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)します。

`PassThru`パラメーターを示すかどうか、コマンドレット オブジェクトを渡します出力、パイプラインを介してこの場合、プロセスが停止したら、ユーザーを使用できます。 このパラメーターが、入力オブジェクトのプロパティに自体の代わりにコマンドレットに関連付けられていることに注意します。

停止 Proc コマンドレットのパラメーター宣言を次に示します。

```csharp
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true
)]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;

/// <summary>
/// Specify the Force parameter that allows the user to override
/// the ShouldContinue call to force the stop operation. This
/// parameter should always be used with caution.
/// </summary>
[Parameter]
public SwitchParameter Force
{
  get { return force; }
  set { force = value; }
}
private bool force;

/// <summary>
/// Specify the PassThru parameter that allows the user to specify
/// that the cmdlet should pass the process object down the pipeline
/// after the process has been stopped.
/// </summary>
[Parameter]
public SwitchParameter PassThru
{
  get { return passThru; }
  set { passThru = value; }
}
private bool passThru;
```

## <a name="overriding-an-input-processing-method"></a>入力処理メソッドをオーバーライドします。

コマンドレットは、入力処理メソッドをオーバーライドする必要があります。 次のコードは、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)上書きサンプル停止 Proc コマンドレットで使用します。 プロセス名を要求された各のこのメソッドにより、こと、プロセスは特殊なプロセスではありません、プロセスを停止しようとする場合に出力オブジェクトを送信、`PassThru`パラメーターを指定します。

```csharp
protected override void ProcessRecord()
{
  foreach (string name in processNames)
  {
    // For every process name passed to the cmdlet, get the associated
    // process(es). For failures, write a non-terminating error
    Process[] processes;

    try
    {
      processes = Process.GetProcessesByName(name);
    }
    catch (InvalidOperationException ioe)
    {
      WriteError(new ErrorRecord(ioe,"Unable to access the target process by name",
                 ErrorCategory.InvalidOperation, name));
      continue;
    }

    // Try to stop the process(es) that have been retrieved for a name
    foreach (Process process in processes)
    {
      string processName;

      try
      {
        processName = process.ProcessName;
      }

      catch (Win32Exception e)
        {
          WriteError(new ErrorRecord(e, "ProcessNameNotFound",
                     ErrorCategory.ReadError, process));
          continue;
        }

        // Call Should Process to confirm the operation first.
        // This is always false if WhatIf is set.
        if (!ShouldProcess(string.Format("{0} ({1})", processName,
                           process.Id)))
        {
          continue;
        }
        // Call ShouldContinue to make sure the user really does want
        // to stop a critical process that could possibly stop the computer.
        bool criticalProcess =
             criticalProcessNames.Contains(processName.ToLower());

        if (criticalProcess &&!force)
        {
          string message = String.Format
                ("The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
                processName);

          // It is possible that ProcessRecord is called multiple times
          // when the Name parameter receives objects as input from the
          // pipeline. So to retain YesToAll and NoToAll input that the
          // user may enter across multiple calls to ProcessRecord, this
          // information is stored as private members of the cmdlet.
          if (!ShouldContinue(message, "Warning!",
                              ref yesToAll,
                              ref noToAll))
          {
            continue;
          }
        } // if (criticalProcess...
        // Stop the named process.
        try
        {
          process.Kill();
        }
        catch (Exception e)
        {
          if ((e is Win32Exception) || (e is SystemException) ||
              (e is InvalidOperationException))
          {
            // This process could not be stopped so write
            // a non-terminating error.
            string message = String.Format("{0} {1} {2}",
                             "Could not stop process \"", processName,
                             "\".");
            WriteError(new ErrorRecord(e, message,
                       ErrorCategory.CloseError, process));
                       continue;
          } // if ((e is...
          else throw;
        } // catch

        // If the PassThru parameter argument is
        // True, pass the terminated process on.
        if (passThru)
        {
          WriteObject(process);
        }
    } // foreach (Process...
  } // foreach (string...
} // ProcessRecord
```

## <a name="calling-the-shouldprocess-method"></a>ShouldProcess メソッドの呼び出し

入力処理、コマンドレットのメソッドを呼び出す必要があります、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッドが実行状態を変更 (たとえば、ファイルの削除) が行われる前に、操作の実行を確認するにはシステムです。 これにより、シェル内で正しい"WhatIf"と「確認」の動作を指定する Windows PowerShell ランタイムです。

> [!NOTE]
> 処理する必要がありに失敗したコマンドレットの状態をサポートしている場合、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)を呼び出すには、ユーザーは、システムを予期せず変更可能性があります。

呼び出し[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)コマンドライン設定やユーザー設定変数を考慮して、Windows PowerShell ランタイムで、ユーザーに変更するリソースの名前を送信します。何をユーザーに表示するかを決定します。

次の例では、呼び出し[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)のオーバーライドから、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)サンプル メソッド停止 Proc コマンドレットを使用します。

```csharp
if (!ShouldProcess(string.Format("{0} ({1})", processName,
                   process.Id)))
{
  continue;
}
```

## <a name="calling-the-shouldcontinue-method"></a>ShouldContinue メソッドを呼び出す

呼び出し、 [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドは、ユーザーにセカンダリのメッセージを送信します。 呼び出しの後にこの呼び出しが行われた[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)返します`true`場合に、`Force`にパラメーターが設定されませんでした`true`します。 ユーザーは、操作を続行するかどうかにフィードバックを提供し、できます。 コマンドレットの呼び出し[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)危険性のあるシステムの変更、ユーザーに [はい] ですべてとなしですべてのオプションを提供する場合、追加のチェックとして。

次の例では、呼び出し[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)のオーバーライドから、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)サンプル メソッド停止 Proc コマンドレットを使用します。

```csharp
if (criticalProcess &&!force)
{
  string message = String.Format
        ("The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
        processName);

  // It is possible that ProcessRecord is called multiple times
  // when the Name parameter receives objects as input from the
  // pipeline. So to retain YesToAll and NoToAll input that the
  // user may enter across multiple calls to ProcessRecord, this
  // information is stored as private members of the cmdlet.
  if (!ShouldContinue(message, "Warning!",
                      ref yesToAll,
                      ref noToAll))
  {
    continue;
  }
} // if (criticalProcess...
```

## <a name="stopping-input-processing"></a>入力の処理を停止しています

入力システムの変更は、コマンドレットのメソッドの処理には、入力の処理を停止する方法を提供する必要があります。 この停止 Proc コマンドレットの呼び出しが行われます、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッドを[System.Diagnostics.Process.Kill*](/dotnet/api/System.Diagnostics.Process.Kill)メソッド。 `PassThru`にパラメーターが設定されている`true`、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)も呼び出して[System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)を送信するにはパイプラインにプロセス オブジェクト。

## <a name="code-sample"></a>コード サンプル

完全なC#サンプル コードは、「 [StopProcessSample01 サンプル](./stopprocesssample01-sample.md)します。

## <a name="defining-object-types-and-formatting"></a>オブジェクトの種類を定義して、書式設定

Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。 その結果、コマンドレットは、独自の型を定義する必要がありますか、コマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。 新しい型を定義するか、既存の型の拡張の詳細については、[を拡張するオブジェクトの種類と書式](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)を参照してください。

## <a name="building-the-cmdlet"></a>コマンドレットを構築

コマンドレットを実装するには、後にする必要があります登録する必要が Windows PowerShell を使用した Windows PowerShell スナップインを使用します。 コマンドレットの登録の詳細については、[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)を参照してください。

## <a name="testing-the-cmdlet"></a>テスト コマンドレット

コマンドレットは、Windows PowerShell を使用した登録しているときに、コマンドラインで実行してテストできます。 ここでは、停止 Proc コマンドレットをテストするいくつかのテストです。 詳細については、コマンドラインからコマンドレットを使用して、、 [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)を参照してください。

- Windows PowerShell を起動し、停止 Proc コマンドレットを使用して、次に示すように処理を停止します。 コマンドレットは、指定されているので、`Name`として必須パラメーターでは、コマンドレットのクエリ パラメーター。

    ```powershell
    PS> stop-proc
    ```

次の出力が表示されます。

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    Name[0]:
    ```

- ここで"NOTEPAD"という名前のプロセスを停止するコマンドレットを使用してみましょう。 コマンドレットでは、アクションの確認が求められます。

    ```powershell
    PS> stop-proc -Name notepad
    ```

次の出力が表示されます。

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (4996)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- "WINLOGON"という名前の重要なプロセスを停止するよう停止プロシージャを使用します。 メッセージが表示され、オペレーティング システムの再起動が発生するために、このアクションを実行する警告を表示します。

    ```powershell
    PS> stop-proc -Name Winlogon
    ```

次の出力が表示されます。

    ```output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    Warning!
    The process " winlogon " is a critical process and should not be stopped. Are you sure you wish to stop the process?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

- 警告を表示せず、WINLOGON プロセスを停止するようになりました試してみましょう。 このコマンドの入力が使用することに注意してください、`Force`パラメーターを警告を無視します。

    ```powershell
    PS> stop-proc -Name winlogon -Force
    ```

次の出力が表示されます。

    ```output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a>参照

[コマンドライン入力を処理するパラメーターの追加](./adding-parameters-that-process-command-line-input.md)

[オブジェクトの種類を拡張して、書式設定](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Windows PowerShell SDK](../windows-powershell-reference.md)

[コマンドレットのサンプル](./cmdlet-samples.md)