---
title: コマンドレットへのユーザー メッセージの追加 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WriteWarning
- notifications, writing
- progress notification
- WriteVerbose
- Stop-Proc
- WriteProgress
- WriteDebug
- notifications, debug
- ProgressRecord
- samples, Stop-Proc cmdlet
- notifications, progress
- notifications, warning
- WriteObject
- WriteError
- verbose notification
- ProcessRecord
- notifications, verbose
- debug notification
- cmdlet, writing notifications
- warning
- code sample, user notifications
- user notifications
ms.assetid: 14c13acb-f0b7-4613-bc7d-c361d14da1a2
caps.latest.revision: 8
ms.openlocfilehash: 1e048f6ae94ac226218c18c8f8f7590a4db26226
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67733759"
---
# <a name="adding-user-messages-to-your-cmdlet"></a>コマンドレットにユーザー メッセージを追加する

コマンドレットは、いくつかの種類の Windows PowerShell ランタイムによって、ユーザーに表示できるメッセージを記述できます。 これらのメッセージには、次の種類があります。

- 全般的なユーザー情報を含む詳細メッセージ。

- トラブルシューティングの情報を含むメッセージをデバッグします。

- 警告メッセージを含むことができる操作を実行しようとして、コマンドレットである通知予期しない結果。

- メッセージ量に関する情報が含まれているコマンドレットの作業の進行状況レポートは、時間がかかる操作を実行するときに完了しました。

コマンドレットの書き込みのメッセージの種類のコマンドレットが書き込むことのできるメッセージの数に制限はありません。 処理方法、コマンドレットの入力の中から特定を呼び出すことによって、各メッセージが書き込まれます。

## <a name="defining-the-cmdlet"></a>コマンドレットを定義します。

コマンドレットの作成の最初の手順は常に、コマンドレットの名前を付けると、コマンドレットを実装する .NET クラスを宣言します。 コマンドレットの任意の並べ替えは、入力処理メソッド; からユーザーへの通知を記述できます。そのため、一般に、できる名前をコマンドレットを実行します。 どのようなシステムの変更を示すすべての動詞を使用してこのコマンドレット。 承認されたコマンドレット動詞の詳細については、次を参照してください。[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)します。

停止 Proc コマンドレットが、システムを変更するように設計します。そのため、 [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) .NET クラスの宣言を含める必要があります、`SupportsShouldProcess`キーワードを属性し、に設定する`true`します。

次のコードは、この停止 Proc コマンドレット クラスの定義です。 この定義の詳細については、次を参照してください。[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)します。

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a>システムの変更のパラメーターを定義します。

停止 Proc コマンドレットは、3 つのパラメーターを定義します。 `Name`、 `Force`、および`PassThru`します。 これらのパラメーターの定義の詳細については、次を参照してください。[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)します。

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

コマンドレットは、入力処理メソッドをオーバーライドする必要があります、最もよくなります[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)します。 この停止 Proc コマンドレットよりも優先、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)処理方法を入力します。 停止 Proc コマンドレットのこの実装では、呼び出しは詳細メッセージ、デバッグ メッセージ、警告メッセージを記述する行われます。

> [!NOTE]
> このメソッドを呼び出す方法の詳細については、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッド、を参照してください[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)します。

## <a name="writing-a-verbose-message"></a>詳細なメッセージの書き込み

[System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)が特定のエラー条件に関連付けられていない一般的なユーザー レベルの情報を記述するメソッドを使用します。 システム管理者はその情報を使用して、その他のコマンドの処理を続行します。 さらに、必要に応じて、このメソッドを使用して書き込まれた情報をローカライズする必要があります。

この停止 Proc コマンドレットから次のコードは、2 つの呼び出しを示しています、 [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)メソッドのオーバーライドから、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。

```csharp
message = String.Format("Attempting to stop process \"{0}\".", name);
WriteVerbose(message);
```

```csharp
message = String.Format("Stopped process \"{0}\", pid {1}.",
                        processName, process.Id);

WriteVerbose(message);
```

## <a name="writing-a-debug-message"></a>デバッグ メッセージの書き込み

[System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)コマンドレットの操作のトラブルシューティングに使用できるデバッグ メッセージを記述するメソッドを使用します。 入力処理メソッドから呼び出し。

> [!NOTE]
> Windows PowerShell も定義、`Debug`パラメーターを両方の詳細を表示し、デバッグ情報。 呼び出す必要はありません、コマンドレットは、このパラメーターをサポートする場合[System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)を呼び出すのと同じコードで[System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).

サンプルの停止 Proc コマンドレットからのコードの次の 2 つのセクションへの呼び出しを表示する、 [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)メソッドのオーバーライドから、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。

このデバッグ メッセージが直前に書き込まれる[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)が呼び出されます。

```csharp
message =
          String.Format("Acquired name for pid {0} : \"{1}\"",
                       process.Id, processName);
WriteDebug(message);
```

このデバッグ メッセージが直前に書き込まれる[System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)が呼び出されます。

```csharp
message =
         String.Format("Writing process \"{0}\" to pipeline",
         processName);
WriteDebug(message);
WriteObject(process);
```

いずれかは、Windows PowerShell が自動的にルーティング[System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)トレース インフラストラクチャとコマンドレットの呼び出し。 これにより、コマンドレットの開発に余分な作業を行うことがなく、ホスト アプリケーション、ファイル、またはデバッガーをトレースするメソッドの呼び出しです。 次のコマンド ライン エントリは、トレース操作を実装します。

**PS > トレース式停止インプロセス-proc.log ファイル-停止 proc メモ帳のコマンド**

## <a name="writing-a-warning-message"></a>警告メッセージの書き込み

[System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning)コマンドレットが予期しない結果が、たとえば、読み取り専用ファイルを上書きする可能性がある操作を実行するときに警告を記述するメソッドを使用します。

サンプルの停止 Proc コマンドレットから次のコードに呼び出しを示しています、 [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning)メソッドのオーバーライドから、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。

```csharp
 if (criticalProcess)
 {
   message =
             String.Format("Stopping the critical process \"{0}\".",
                           processName);
   WriteWarning(message);
} // if (criticalProcess...
```

## <a name="writing-a-progress-message"></a>進行状況メッセージの書き込み

[System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress)コマンドレットの操作を完了するに非常に長い時間を取得すると、進行状況メッセージを書き込むために使用します。 呼び出し[System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress)渡します、 [System.Management.Automation.Progressrecord](/dotnet/api/System.Management.Automation.ProgressRecord)レンダリングするまで、ユーザーに、ホスト アプリケーションに送信されるオブジェクト。

> [!NOTE]
> この停止 Proc コマンドレットへの呼び出しを含まない、 [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress)メソッド。

次のコードは、項目をコピーしようとするコマンドレットによって作成された進行状況メッセージの例です。

```csharp
int myId = 0;
string myActivity = "Copy-item: Copying *.* to c:\abc";
string myStatus = "Copying file bar.txt";
ProgressRecord pr = new ProgressRecord(myId, myActivity, myStatus);
WriteProgress(pr);

pr.RecordType = ProgressRecordType.Completed;
WriteProgress(pr);
```

## <a name="code-sample"></a>コード サンプル

完全なC#サンプル コードは、「 [StopProcessSample02 サンプル](./stopprocesssample02-sample.md)します。

## <a name="define-object-types-and-formatting"></a>オブジェクトの種類と書式設定を定義します。

Windows PowerShell は、.NET オブジェクトを使用してコマンドレット間で情報を渡します。 その結果、コマンドレットは、独自の型を定義する必要がありますか、コマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。 新しい型を定義するか、既存の型の拡張の詳細については、次を参照してください。[を拡張するオブジェクトの種類と書式](/previous-versions//ms714665(v=vs.85))します。

## <a name="building-the-cmdlet"></a>コマンドレットを構築

コマンドレットを実装するには、後にする必要があります登録する必要が Windows PowerShell を使用した Windows PowerShell スナップインを使用します。 コマンドレットの登録の詳細については、次を参照してください。[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](/previous-versions//ms714644(v=vs.85))します。

## <a name="testing-the-cmdlet"></a>テスト コマンドレット

コマンドレットは、Windows PowerShell を使用した登録しているときに、コマンドラインで実行してテストできます。 サンプルの停止 Proc コマンドレットをテストしてみましょう。 詳細については、コマンドラインからコマンドレットを使用して、次を参照してください。、 [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)します。

- 次のコマンド ライン エントリは、"NOTEPAD"という名前のプロセスを停止し、詳細の通知を提供し、デバッグ情報を印刷する停止プロシージャを使用します。

    ```powershell
    PS> stop-proc -Name notepad -Verbose -Debug
    ```

次の出力が表示されます。

    ```
    VERBOSE: Attempting to stop process " notepad ".
    DEBUG: Acquired name for pid 5584 : "notepad"

    Confirm
    Continue with this operation?
    [Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"): Y

    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (5584)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    VERBOSE: Stopped process "notepad", pid 5584.
    ```

## <a name="see-also"></a>参照

[システムを変更するコマンドレットを作成します。](./creating-a-cmdlet-that-modifies-the-system.md)

[Windows PowerShell コマンドレットを作成する方法](/powershell/developer/cmdlet/writing-a-windows-powershell-cmdlet)

[オブジェクトの種類を拡張して、書式設定](/previous-versions//ms714665(v=vs.85))

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](/previous-versions//ms714644(v=vs.85))

[Windows PowerShell SDK](../windows-powershell-reference.md)
