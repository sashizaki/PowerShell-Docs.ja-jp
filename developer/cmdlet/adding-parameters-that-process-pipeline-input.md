---
title: パイプラインの入力を処理するパラメーターの追加 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell Programmer's Guide], pipeline input
- parameters [PowerShell Programmer's Guide], pipeline input
ms.assetid: 09bf70a9-7c76-4ffe-b3f0-a1d5f10a0931
caps.latest.revision: 8
ms.openlocfilehash: bd52dc8aee7975d0899083a5c2f595b17690dc33
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054766"
---
# <a name="adding-parameters-that-process-pipeline-input"></a>パイプライン入力を処理するパラメーターを追加する

コマンドレットの入力の 1 つのソースは、アップ ストリームのコマンドレットから発信されたパイプラインにオブジェクトです。 ここが Get-proc コマンドレットにパラメーターを追加する方法について説明します (で説明されている[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md)) コマンドレットは、パイプライン オブジェクトを処理できるようにします。

この Get-proc コマンドレットを使用して、`Name`パイプライン オブジェクトからの入力を受け付けるパラメーターは、指定された名前に基づいて、ローカル コンピューターからプロセス情報を取得し、コマンドラインでのプロセスに関する情報を表示します。

このセクションのトピックで、次のとおりです。

- [コマンドレット クラスを定義します。](#Defining-the-Cmdlet-Class)

- [パイプラインから入力を定義します。](#Defining-Input-from-the-Pipeline)

- [入力処理メソッドをオーバーライドします。](#Overriding-an-Input-Processing-Method)

- [コード サンプル](#Code-Sample)

- [オブジェクトの種類を定義して、書式設定](#Defining-Object-Types-and-Formatting)

- [コマンドレットを構築](#Building-the-Cmdlet)

- [テスト コマンドレット](#Testing-the-Cmdlet)

## <a name="defining-the-cmdlet-class"></a>コマンドレット クラスを定義します。

コマンドレットの作成の最初の手順は常に、コマンドレットの名前を付けると、コマンドレットを実装する .NET クラスを宣言します。 このコマンドレットは、ため、ここで選択した動詞名は"Get"プロセスの情報を取得します。 (ほぼあらゆる種類の情報を取得するのに対応しているコマンドレットは、コマンドラインの入力を処理できます)承認されたコマンドレット動詞の詳細については、[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)を参照してください。

この Get-proc コマンドレットの定義を次に示します。 この定義の詳細が記載[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md)です。

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-input-from-the-pipeline"></a>パイプラインから入力を定義します。

このセクションでは、コマンドレットのパイプラインからの入力を定義する方法について説明します。 この Get-proc コマンドレットを表すプロパティの定義、`Name`パラメーター」の説明に従って[そのプロセスのコマンドラインの入力パラメーターを追加する](./adding-parameters-that-process-command-line-input.md)します。 (パラメーターの宣言に関する全般情報のトピックを参照してください)。

ただし、コマンドレットは、パイプラインの入力を処理する必要がある、ときに、Windows PowerShell ランタイムによって入力値にバインドされたパラメーターが必要です。 これを行うには、追加する必要があります、`ValueFromPipeline`キーワードを追加または、`ValueFromPipelineByProperty`キーワードを[System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)属性宣言。 指定、`ValueFromPipeline`コマンドレットは、完全な入力オブジェクトにアクセスする場合は、キーワード。 指定、`ValueFromPipelineByProperty`コマンドレットは、オブジェクトのプロパティのみにアクセスする場合。

パラメーター宣言を次に示します、`Name`パイプライン入力を受け付けるこの Get-proc コマンドレットのパラメーター。

[!code-csharp[GetProcessSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs#L35-L44 "GetProcessSample03.cs")]

```vb
<Parameter(Position:=0, ValueFromPipeline:=True, _
ValueFromPipelineByPropertyName:=True), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#GetProc03VBNameParameter](Msh_samplesgetproc03#GetProc03VBNameParameter)]  -->

前の宣言のセット、`ValueFromPipeline`キーワードを`true`Windows PowerShell ランタイムは、オブジェクトが、パラメーターと同じ型である場合に、受信オブジェクトへのパラメーターをバインドはまたは場合に、同じ型に強制的に変換できます。 `ValueFromPipelineByPropertyName`キーワードの設定も`true`、Windows PowerShell ランタイムは、受信オブジェクトを確認できるように、`Name`プロパティ。 受信のオブジェクトは、このようなプロパティを持っている場合、ランタイムはバインド、`Name`パラメーターを`Name`受信オブジェクトのプロパティ。

> [!NOTE]
> 設定、`ValueFromPipeline`キーワード属性パラメーターの設定よりも優先、`ValueFromPipelineByPropertyName`キーワード。

## <a name="overriding-an-input-processing-method"></a>入力処理メソッドをオーバーライドします。

コマンドレットをパイプラインの入力を処理する場合は、その適切な入力処理メソッドをオーバーライドする必要があります。 基本的な入力処理メソッドがで導入された[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md)です。

この Get-proc コマンドレットよりも優先、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)を処理するメソッド、`Name`ユーザーまたはスクリプトによって提供されるパラメーターの入力。 名前が指定されていない場合、このメソッドは各要求のプロセス名またはすべてのプロセスのプロセスを取得します。 わかります[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)への呼び出し[System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29)出力出力を送信するためのメカニズムは、パイプラインにオブジェクトです。 この呼び出しの 2 番目のパラメーター`enumerateCollection`に設定されている`true`、プロセス オブジェクトの配列を列挙し、コマンドラインに、一度に 1 つのプロセスを記述する Windows PowerShell ランタイムに通知します。

```csharp
protected override void ProcessRecord()
{
  // If no process names are passed to the cmdlet, get all processes.
  if (processNames == null)
  {
      // Write the processes to the pipeline making them available
      // to the next cmdlet. The second argument of this call tells
      // PowerShell to enumerate the array, and send one process at a
      // time to the pipeline.
      WriteObject(Process.GetProcesses(), true);
  }
  else
  {
    // If process names are passed to the cmdlet, get and write
    // the associated processes.
    foreach (string name in processNames)
    {
      WriteObject(Process.GetProcessesByName(name), true);
    } // End foreach (string name...).
  }
}
```

```vb
Protected Overrides Sub ProcessRecord()
    Dim processes As Process()

    '/ If no process names are passed to the cmdlet, get all processes.
    If processNames Is Nothing Then
        processes = Process.GetProcesses()
    Else

        '/ If process names are specified, write the processes to the
        '/ pipeline to display them or make them available to the next cmdlet.
        For Each name As String In processNames
            '/ The second parameter of this call tells PowerShell to enumerate the
            '/ array, and send one process at a time to the pipeline.
            WriteObject(Process.GetProcessesByName(name), True)
        Next
    End If

End Sub 'ProcessRecord
```

## <a name="code-sample"></a>コード サンプル

完全なC#サンプル コードは、「 [GetProcessSample03 サンプル](./getprocesssample03-sample.md)します。

## <a name="defining-object-types-and-formatting"></a>オブジェクトの種類を定義して、書式設定

Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。 その結果、コマンドレットは、独自の型を定義する必要がありますか、コマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。 新しい型を定義するか、既存の型の拡張の詳細については、[を拡張するオブジェクトの種類と書式](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)を参照してください。

## <a name="building-the-cmdlet"></a>コマンドレットを構築

Windows PowerShell を使って Windows PowerShell を使用した登録する必要がありますコマンドレットの実装後にスナップインです。 コマンドレットの登録の詳細については、[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)を参照してください。

## <a name="testing-the-cmdlet"></a>テスト コマンドレット

Windows PowerShell コマンドレットが登録されて、コマンドラインで実行してテストします。 たとえば、サンプルのコマンドレットのコードをテストします。 詳細については、コマンドラインからコマンドレットを使用して、、 [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)を参照してください。

- Windows PowerShell プロンプトで、パイプラインを介してプロセス名を取得する次のコマンドを入力します。

    ```powershell
    PS> type ProcessNames | get-proc
    ```

次の出力が表示されます。

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
    -------  ------  -----   ----- -----   ------    --  -----------
        809      21  40856    4448    147    9.50  2288  iexplore
        737      21  26036   16348    144   22.03  3860  iexplore
         39       2   1024     388     30    0.08  3396  notepad
       3927      62  71836   26984    467  195.19  1848  OUTLOOK
    ```

- 次の行を取得しているプロセス オブジェクトを入力してください、 `Name` "IEXPLORE"と呼ばれるプロセスからのプロパティ。 この例では、`Get-Process`コマンドレットが (Windows PowerShell によって提供される)"と、IEXPLORE"プロセスを取得するアップ ストリームのコマンドとして。

    ```powershell
    PS> get-process iexplore | get-proc
    ```

次の出力が表示されます。

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
    -------  ------  -----      ----- -----   ------     -- -----------
        801      21  40720    6544    142    9.52  2288  iexplore
        726      21  25872   16652    138   22.09  3860  iexplore
        801      21  40720    6544    142    9.52  2288  iexplore
        726      21  25872   16652    138   22.09  3860  iexplore
    ```

## <a name="see-also"></a>参照

[コマンドラインの入力を処理するパラメーターの追加](./adding-parameters-that-process-command-line-input.md)

[初めてのコマンドレットを作成します。](./creating-a-cmdlet-without-parameters.md)

[オブジェクトの種類を拡張して、書式設定](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Windows PowerShell リファレンス](../windows-powershell-reference.md)

[コマンドレットのサンプル](./cmdlet-samples.md)
