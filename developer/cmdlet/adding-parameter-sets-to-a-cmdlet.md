---
title: コマンドレットにパラメーターを追加すると設定 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parameter sets [PowerShell Programmer's Guide]
ms.assetid: a6131db4-fd6e-45f1-bd47-17e7174afd56
caps.latest.revision: 8
ms.openlocfilehash: f0bff11618c18bf53b9c2a185445795a17306fa3
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054987"
---
# <a name="adding-parameter-sets-to-a-cmdlet"></a>コマンドレットにパラメーター セットを追加する

このセクションは、停止 Proc コマンドレットにパラメーターの設定を追加する方法を説明します (で説明されている[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md))。 このプログラマー ガイドで説明されているその他の停止 Proc コマンドレットと同様に、このコマンドレットは Get-proc コマンドレットを使用して取得されるプロセスの停止を試みます (で説明されている[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md))。

このセクションのトピックで、次のとおりです。

- [パラメーターのセットについて知っておくべきこと](#Adding-Parameter-Sets-to-a-Cmdlet)

- [コマンドレット クラスを宣言します。](#Declaring-the-Cmdlet-Class)

- [コマンドレットのパラメーターを宣言します。](#Declaring-the-Parameters-of-the-Cmdlet)

- [入力処理メソッドをオーバーライドします。](#Overriding-an-Input-Processing-Method)

- [コード サンプル](#Declaring-the-Parameters-of-the-Cmdlet)

- [オブジェクトの種類を定義して、書式設定](#Defining-Object-Types-and-Formatting)

- [コマンドレットを構築](#Building-the-Cmdlet)

- [テスト コマンドレット](#Testing-the-Cmdlet)

## <a name="things-to-know-about-parameter-sets"></a>パラメーターのセットについて知っておくべきこと

Windows PowerShell では、同時に動作するパラメーターのグループとして設定パラメーターを定義します。 コマンドレットのパラメーターをグループ化には、ユーザーがどのような一連のパラメーターを指定に基づいて、その機能を変更できる 1 つのコマンドレットを作成できます。

さまざまな機能を定義する 2 つのパラメーター セットを使用するコマンドレットの例は、`Get-EventLog`コマンドレットは Windows PowerShell によって提供されます。 このコマンドレットは、ユーザーを指定すると、さまざまな情報を返します、`List`または`LogName`パラメーター。 場合、`LogName`パラメーターを指定すると、コマンドレットは、特定のイベント ログで、イベントに関する情報を返します。 場合、`List`パラメーターを指定すると、コマンドレットは、ログに関する情報をファイル自体 (イベントが含まれている情報以外) を返します。 ここで、`List`と`LogName`パラメーターが 2 つの個別のパラメーター セットを識別します。

パラメーターのセットに関して記憶して 2 つの重要な点は、Windows PowerShell ランタイムは、1 つだけのパラメーターが特定の入力セットを使用して、各パラメーター セットが少なくとも 1 つのパラメーターを持つ必要があるをそのパラメーターのセットの一意。

この停止 Proc コマンドレットが次の 3 つのパラメーター セットを使用するにはその最後のポイントを示すためには、: `ProcessName`、 `ProcessId`、および`InputObject`します。 それぞれのパラメーター セットは、他のパラメーター セットではない 1 つのパラメーターがあります。 パラメーター セットは、他のパラメーターを共有でしたが、コマンドレットは、固有のパラメーターを使用して`ProcessName`、 `ProcessId`、および`InputObject`Windows PowerShell ランタイムが使用されるパラメーターのセットを識別するためにします。

## <a name="declaring-the-cmdlet-class"></a>コマンドレット クラスを宣言します。

コマンドレットの作成の最初の手順は常に、コマンドレットの名前を付けると、コマンドレットを実装する .NET クラスを宣言します。 このコマンドレットでは、"Stop"ライフ サイクルの動詞はコマンドレットは、システム プロセスを停止するために使用されます。 "Proc"名詞形式の名前は、コマンドレットは、プロセスで機能するために使用されます。 次の宣言では、コマンドレット クラスの名前、コマンドレットの動詞と名詞の名前が反映されることに注意してください。

> [!NOTE]
> 承認されたコマンドレット動詞名の詳細については、次を参照してください。[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)します。

次のコードは、このコマンドレットで停止 Proc クラス定義です。

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        DefaultParameterSetName = "ProcessId",
        SupportsShouldProcess = true)]
public class StopProcCommand : PSCmdlet
```

```vb
<Cmdlet(VerbsLifecycle.Stop, "Proc", DefaultParameterSetName:="ProcessId", _
SupportsShouldProcess:=True)> _
Public Class StopProcCommand
    Inherits PSCmdlet
```

## <a name="declaring-the-parameters-of-the-cmdlet"></a>コマンドレットのパラメーターを宣言します。

このコマンドレットは、コマンドレットが (これらのパラメーターは、パラメーター セットも定義) への入力として必要な 3 つのパラメーターを定義と同様に、`Force`コマンドレットが何を管理するパラメーターと`PassThru`コマンドレットに送信するかどうかを決定するパラメーター、オブジェクトをパイプラインを通じてに出力します。 既定では、このコマンドレットは、パイプラインを通じてオブジェクトを通過しません。 これらの最後の 2 つのパラメーターの詳細については、次を参照してください。[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)します。

### <a name="declaring-the-name-parameter"></a>Name パラメーターを宣言します。

この入力パラメーターは、停止するプロセスの名前を指定できます。 なお、`ParameterSetName`属性のキーワード、 [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)属性を指定します、`ProcessName`パラメーターは、このパラメーターに設定します。

[!code-csharp[StopProcessSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs#L44-L58 "StopProcessSample04.cs")]

```vb
<Parameter(Position:=0, ParameterSetName:="ProcessName", _
Mandatory:=True, _
ValueFromPipeline:=True, ValueFromPipelineByPropertyName:=True, _
HelpMessage:="The name of one or more processes to stop. " & _
    "Wildcards are permitted."), [Alias]("ProcessName")> _
Public Property Name() As String()
    Get
        Return processNames
    End Get
    Set(ByVal value As String())
        processNames = value
    End Set
End Property

Private processNames() As String
```

このパラメーターにエイリアス"ProcessName"が与えられているにも注意してください。

### <a name="declaring-the-id-parameter"></a>Id パラメーターを宣言します。

この入力パラメーターは、停止するプロセスの識別子を指定できます。 なお、`ParameterSetName`属性のキーワード、 [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)属性を指定します、`ProcessId`パラメーターのセット。

```csharp
[Parameter(
           ParameterSetName = "ProcessId",
           Mandatory = true,
           ValueFromPipelineByPropertyName = true,
           ValueFromPipeline = true
)]
[Alias("ProcessId")]
public int[] Id
{
  get { return processIds; }
  set { processIds = value; }
}
private int[] processIds;
```

```vb
<Parameter(ParameterSetName:="ProcessId", _
Mandatory:=True, _
ValueFromPipelineByPropertyName:=True, _
ValueFromPipeline:=True), [Alias]("ProcessId")> _
Public Property Id() As Integer()
    Get
        Return processIds
    End Get
    Set(ByVal value As Integer())
        processIds = value
    End Set
End Property
Private processIds() As Integer
```

このパラメーターにエイリアス"ProcessId"が与えられているにも注意してください。

### <a name="declaring-the-inputobject-parameter"></a>InputObject パラメーターを宣言します。

この入力パラメーターは、停止するプロセスに関する情報を格納している入力オブジェクトを指定できます。 なお、`ParameterSetName`属性のキーワード、 [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)属性を指定します、`InputObject`パラメーターは、このパラメーターに設定します。

```csharp
[Parameter(
           ParameterSetName = "InputObject",
           Mandatory = true,
           ValueFromPipeline = true)]
public Process[] InputObject
{
  get { return inputObject; }
  set { inputObject = value; }
}
private Process[] inputObject;
```

```vb
<Parameter(ParameterSetName:="InputObject", _
Mandatory:=True, ValueFromPipeline:=True)> _
Public Property InputObject() As Process()
    Get
        Return myInputObject
    End Get
    Set(ByVal value As Process())
        myInputObject = value
    End Set
End Property
Private myInputObject() As Process
```

このパラメーターにエイリアスがないことにも注意してください。

### <a name="declaring-parameters-in-multiple-parameter-sets"></a>複数のパラメーター セット内のパラメーターを宣言します。

パラメーターのセットごとに一意のパラメーターは必要ありませんが、パラメーターが 1 つ以上のパラメーターのセットに属することができます。 このような場合は、共有パラメーターを与える、 [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)にそのパラメーターを設定それぞれが属する属性の宣言。 パラメーターがすべてのパラメーター セットの場合は、するパラメーターの属性を 1 回宣言する必要があるのみとパラメーター セット名を指定する必要はありません。

## <a name="overriding-an-input-processing-method"></a>入力処理メソッドをオーバーライドします。

すべてのコマンドレットは、入力処理メソッドをオーバーライドする必要があります、これは最も頻繁になります、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。 このコマンドレットで、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)コマンドレットは、任意の数のプロセスを処理できるように、メソッドはオーバーライドされます。 どのパラメーター セットで、ユーザー ベースのさまざまなメソッドの呼び出しが指定されている Select ステートメントが含まれています。

```csharp
protected override void ProcessRecord()
{
  switch (ParameterSetName)
  {
    case "ProcessName":
         ProcessByName();
         break;

    case "ProcessId":
         ProcessById();
         break;

    case "InputObject":
         foreach (Process process in inputObject)
         {
           SafeStopProcess(process);
         }
         break;

    default:
         throw new ArgumentException("Bad ParameterSet Name");
  } // switch (ParameterSetName...
} // ProcessRecord
```

```vb
Protected Overrides Sub ProcessRecord()
    Select Case ParameterSetName
        Case "ProcessName"
            ProcessByName()

        Case "ProcessId"
            ProcessById()

        Case "InputObject"
            Dim process As Process
            For Each process In myInputObject
                SafeStopProcess(process)
            Next process

        Case Else
            Throw New ArgumentException("Bad ParameterSet Name")
    End Select

End Sub 'ProcessRecord ' ProcessRecord
```

Select ステートメントによって呼び出されるヘルパー メソッドが、ここで説明できませんが、次のセクションで完全なコード サンプルでは、その実装を確認できます。

## <a name="code-sample"></a>コード サンプル

完全なC#サンプル コードは、「 [StopProcessSample04 サンプル](./stopprocesssample04-sample.md)します。

## <a name="defining-object-types-and-formatting"></a>オブジェクトの種類を定義して、書式設定

Windows PowerShell は、.NET オブジェクトを使用してコマンドレット間で情報を渡します。 その結果、コマンドレットは、独自の型を定義する必要がありますか、コマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。 新しい型を定義するか、既存の型の拡張の詳細については、次を参照してください。[を拡張するオブジェクトの種類と書式](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)します。

## <a name="building-the-cmdlet"></a>コマンドレットを構築

コマンドレットを実装するには、後にする必要がありますに登録する Windows PowerShell Windows PowerShell スナップインを使用します。 コマンドレットの登録の詳細については、次を参照してください。[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。

## <a name="testing-the-cmdlet"></a>テスト コマンドレット

Windows PowerShell コマンドレットが登録されて、コマンドラインで実行してテストします。 示すいくつかのテストをここでは、どのように`ProcessId`と`InputObject`パラメーターは、テストのプロセスを停止するには、そのパラメーター セットを使用できます。

- Windows PowerShell が起動、実行停止 Proc コマンドレットと、 `ProcessId` id に基づいてプロセスを停止するパラメーターを設定します。 この場合、コマンドレットを使用して、`ProcessId`プロセスを停止するパラメーターを設定します。

    ```
    PS> stop-proc -Id 444
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (444)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- Windows PowerShell が起動、実行停止 Proc コマンドレットと、`InputObject`で取得したメモ帳オブジェクトのプロセスを停止するパラメーターの設定、`Get-Process`コマンド。

    ```
    PS> get-process notepad | stop-proc
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (444)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a>参照

[システムを変更するコマンドレットを作成します。](./creating-a-cmdlet-that-modifies-the-system.md)

[Windows PowerShell コマンドレットを作成する方法](http://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[オブジェクトの種類を拡張して、書式設定](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Windows PowerShell SDK](../windows-powershell-reference.md)
