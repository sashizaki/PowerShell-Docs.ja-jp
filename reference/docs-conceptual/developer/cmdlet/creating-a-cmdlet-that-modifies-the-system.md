---
title: System | を変更するコマンドレットを作成するMicrosoft Docs
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
ms.openlocfilehash: 8a65915b88a04e36e773853b903528a65fe11e99
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365761"
---
# <a name="creating-a-cmdlet-that-modifies-the-system"></a>システムを変更するコマンドレットを作成する

コマンドレットは、Windows PowerShell ランタイムの状態だけでなく、システムの実行状態を変更する必要がある場合があります。 このような場合は、コマンドレットを使用して、変更を行うかどうかを確認する機会をユーザーに許可する必要があります。

確認をサポートするには、コマンドレットで2つの処理を行う必要があります。

- このコマンドレットでは、Supportsを `true`に設定することによっ[て、指定](/dotnet/api/System.Management.Automation.CmdletAttribute)した場合の確認がサポートされることを宣言します。

- コマンドレットの実行中に、次の例に示すように、「」というコマンドレット[を呼び出します](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)。

コマンドレットは、確認をサポートすることで、Windows PowerShell によって提供される `Confirm` および `WhatIf` パラメーターを公開します。また、コマンドレットの開発ガイドラインにも適合します (コマンドレット開発ガイドラインの詳細については、「[コマンドレット開発ガイドライン](./cmdlet-development-guidelines.md)」を参照してください)。

## <a name="changing-the-system"></a>システムの変更

"システムの変更" の動作は、Windows PowerShell の外部でシステムの状態を変更する可能性のあるすべてのコマンドレットを指します。 たとえば、プロセスを停止したり、ユーザーアカウントを有効または無効にしたり、データベーステーブルに行を追加したりすると、システムに対するすべての変更が確認されます。 これに対して、データの読み取りまたは一時的な接続の確立を行う操作は、システムを変更するのではなく、通常は確認を必要としません。 また、`set-variable`など、Windows PowerShell ランタイム内で効果が制限されている操作についても、確認は必要ありません。 永続的な変更を行う可能性のあるコマンドレットは、永続的な変更を行う必要がある場合にのみ、`SupportsShouldProcess` を宣言して呼び出す必要があり[ます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)

> [!NOTE]
> "プロセスの確認" はコマンドレットにのみ適用されます。 コマンドまたはスクリプトが、.NET のメソッドまたはプロパティを直接呼び出すか、Windows PowerShell の外部でアプリケーションを呼び出すことによって、システムの実行状態を変更した場合、この形式の確認は使用できません。

## <a name="the-stopproc-cmdlet"></a>StopProc コマンドレット

このトピックでは、Get Proc コマンドレットを使用して取得したプロセスを停止しようとする Stop Proc コマンドレットについて説明します (「[最初のコマンドレットを作成する](./creating-a-cmdlet-without-parameters.md)」を参照)。

## <a name="defining-the-cmdlet"></a>コマンドレットの定義

コマンドレットの作成の最初の手順では、常にコマンドレットに名前を付け、コマンドレットを実装する .NET クラスを宣言します。 システムを変更するためのコマンドレットを記述しているので、それに応じた名前を付ける必要があります。 このコマンドレットはシステムプロセスを停止するため、ここで選択した動詞名は "Stop" で、 [Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)クラスで定義されます。これは、コマンドレットがプロセスを停止することを示す "Proc" という名詞です。 承認されたコマンドレット動詞の詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。

この Stop Proc コマンドレットのクラス定義を次に示します。

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

この[場合、`SupportsShouldProcess`](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute キーワードが `true` に設定されていることに注意してください。これにより、コマンドレットは、... [...](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) ............................. [...](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) このキーワードが設定されていない場合、ユーザーは `Confirm` パラメーターと `WhatIf` パラメーターを使用できません。

### <a name="extremely-destructive-actions"></a>非常に破壊的操作

操作の中には、アクティブなハードディスクパーティションの再フォーマットなど、非常に破壊的なものがあります。 このような場合は、コマンドレットによって `ConfirmImpact` = `ConfirmImpact.High` が設定さ[れている](/dotnet/api/System.Management.Automation.CmdletAttribute)必要があります。 この設定により、ユーザーが `Confirm` パラメーターを指定していない場合でも、コマンドレットはユーザー確認を要求します。 ただし、コマンドレットの開発者は、ユーザーアカウントの削除など、破壊的な可能性がある操作については、乱用 `ConfirmImpact` 回避する必要があります。 `ConfirmImpact` が " [System. Automation. ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact) **high"** に設定されていることに注意してください。

同様に、一部の操作は破壊的になる可能性はほとんどありませんが、理論的には Windows PowerShell の外部でシステムの実行状態を変更します。 このようなコマンドレットでは、`ConfirmImpact` を[system.string に設定できます。](/dotnet/api/system.management.automation.confirmimpact?view=powershellsdk-1.1.0) これにより、ユーザーが中程度の影響と大きな影響を与える操作のみを確認するように求められた場合に、確認要求がバイパスされます。

## <a name="defining-parameters-for-system-modification"></a>システム変更のパラメーターの定義

このセクションでは、システムの変更をサポートするために必要なコマンドレットなど、コマンドレットのパラメーターの定義方法について説明します。 パラメーターの定義に関する全般的な情報が必要な場合は、「[コマンドライン入力を処理するパラメーターを追加](./adding-parameters-that-process-command-line-input.md)する」を参照してください。

Stop Proc コマンドレットは、`Name`、`Force`、および `PassThru`の3つのパラメーターを定義します。

`Name` パラメーターは、プロセス入力オブジェクトの `Name` プロパティに対応しています。 このサンプルの `Name` パラメーターは必須であることに注意してください。停止する名前付きプロセスがない場合、コマンドレットは失敗します。

`Force` パラメーターを使用すると、ユーザーは、システムの呼び出しをオーバーライドでき[ます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) 実際、`Force` を指定すると、コマンドレットによって `Force` パラメーターが設定されて[いる必要があります](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)。これにより、コマンドレットは、コマンドレットによる呼び出しをスキップし、操作を続行します[。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) これは、[システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)の呼び出しには影響しないことに注意してください。

`PassThru` パラメーターを使用すると、コマンドレットがパイプライン (この場合はプロセスが停止した後) を介して出力オブジェクトを渡すかどうかを指定できます。 このパラメーターは、入力オブジェクトのプロパティではなく、コマンドレット自体に関連付けられていることに注意してください。

Stop Proc コマンドレットのパラメーター宣言を次に示します。

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

## <a name="overriding-an-input-processing-method"></a>入力処理メソッドのオーバーライド

コマンドレットでは、入力処理メソッドをオーバーライドする必要があります。 次のコードは、サンプルの Stop Proc コマンドレットで使用される、system.object[のオーバーライドを](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)示しています。 このメソッドは、要求されたプロセス名ごとに、プロセスが特別なプロセスではないことを確認し、プロセスを停止し、`PassThru` パラメーターが指定されている場合は出力オブジェクトを送信します。

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

## <a name="calling-the-shouldprocess-method"></a>メソッドの呼び出し

コマンドレットの入力処理方法では、変更 (ファイルの削除など) がシステムの実行状態になる前に、操作の実行を確認するために、 [system.string メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出す必要があります。 これにより、Windows PowerShell ランタイムはシェル内で適切な "WhatIf" および "Confirm" 動作を提供できます。

> [!NOTE]
> コマンドレットによって処理される必要があることが示され、[システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)の呼び出しに失敗した場合は、ユーザーがシステムを予期せず変更する可能性があります。

この呼び出しは、変更するリソースの名前をユーザーに送信し[ます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) Windows PowerShell ランタイムは、ユーザーに表示される内容を決定する際に、コマンドライン設定またはユーザー設定変数を考慮しています。

次の例は、サンプルの Stop Proc コマンドレットでの、 [system](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .................................................. [...](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)

```csharp
if (!ShouldProcess(string.Format("{0} ({1})", processName,
                   process.Id)))
{
  continue;
}
```

## <a name="calling-the-shouldcontinue-method"></a>"メソッドの続行" メソッドの呼び出し

システムの呼び出しによって、ユーザーにセカンダリメッセージが送信されるように[なり](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)ます。 この呼び出しは、`Force` パラメーターが `true`に設定されていない場合に `true`[を返す呼び出しの後に行わ](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)れます。 ユーザーは、操作を続行する必要があるかどうかを伝えるフィードバックを提供できます。 コマンドレットでは、system.object を呼び出し[ます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)危険性の高いシステム変更については、追加のチェックとして続行するか、すべてのオプションをユーザーに提供する必要があるかどうかを確認してください。

次の例では、System... コマンドレットの呼び出しを示して[います。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)サンプルの Stop Proc コマンドレット[で、このメソッドの](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)オーバーライドから続行します。

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

## <a name="stopping-input-processing"></a>入力処理の停止

システムの変更を行うコマンドレットの入力処理メソッドでは、入力の処理を停止する方法が提供される必要があります。 この Stop Proc コマンドレットの場合は[、system.](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) [..](/dotnet/api/System.Diagnostics.Process.Kill) ....................................................... `PassThru` パラメーターは `true`に設定されて[いるので](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)も呼び出されて、プロセスオブジェクトがパイプラインに送信されます。この処理が行われます。

## <a name="code-sample"></a>コードサンプル

完全なC#サンプルコードについては、「 [StopProcessSample01 sample](./stopprocesssample01-sample.md)」を参照してください。

## <a name="defining-object-types-and-formatting"></a>オブジェクトの種類と書式設定の定義

Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。 そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。 新しい型を定義する、または既存の型を拡張する方法の詳細については、「[オブジェクトの型と書式設定の拡張](/previous-versions//ms714665(v=vs.85))」を参照してください。

## <a name="building-the-cmdlet"></a>コマンドレットのビルド

コマンドレットを実装した後は、Windows powershell スナップインを使用して Windows PowerShell に登録する必要があります。 コマンドレットの登録の詳細については、「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。

## <a name="testing-the-cmdlet"></a>コマンドレットのテスト

コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行することでテストできます。 ここでは、Stop Proc コマンドレットをテストするいくつかのテストについて説明します。 コマンドラインからコマンドレットを使用する方法の詳細については、「 [Windows PowerShell を使用したはじめに](/powershell/scripting/getting-started/getting-started-with-windows-powershell)」を参照してください。

- 次に示すように、Windows PowerShell を起動し、Stop-Proc コマンドレットを使用して処理を停止します。 コマンドレットでは `Name` パラメーターを必須として指定しているので、コマンドレットではパラメーターに対してクエリを行います。

    ```powershell
    PS> stop-proc
    ```

次の出力が表示されます。

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    Name[0]:
    ```

- 次に、コマンドレットを使用して、"NOTEPAD" という名前のプロセスを停止します。 コマンドレットでは、操作を確認するように求められます。

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

- 以下に示すように Stop-Proc を使用して、"WINLOGON" という名前の重要なプロセスを停止します。 オペレーティングシステムが再起動されるため、この操作の実行についての警告が表示されます。

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

- ここで、警告を受信せずに WINLOGON プロセスを停止してみましょう。 このコマンドの入力では、`Force` パラメーターを使用して警告を上書きすることに注意してください。

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

## <a name="see-also"></a>関連項目

[コマンドライン入力を処理するパラメーターの追加](./adding-parameters-that-process-command-line-input.md)

[オブジェクトの種類と書式設定の拡張](/previous-versions//ms714665(v=vs.85))

[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))

[Windows PowerShell SDK](../windows-powershell-reference.md)

[コマンドレットのサンプル](./cmdlet-samples.md)