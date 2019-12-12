---
title: パイプライン入力を処理するパラメーターを追加する |Microsoft Docs
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
ms.openlocfilehash: 9ecb73a4138a5853fa5fb378874da2d81c5dbdba
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364601"
---
# <a name="adding-parameters-that-process-pipeline-input"></a>パイプライン入力を処理するパラメーターを追加する

コマンドレットの1つの入力ソースは、上流のコマンドレットで発生したパイプライン上のオブジェクトです。 このセクションでは、コマンドレットがパイプラインオブジェクトを処理できるように、Get Proc コマンドレット ([最初のコマンドレットの作成](./creating-a-cmdlet-without-parameters.md)に関するページで説明) にパラメーターを追加する方法について説明します。

この Get Proc コマンドレットは、パイプラインオブジェクトからの入力を受け入れ、指定された名前に基づいてローカルコンピューターからプロセス情報を取得し、コマンドラインでプロセスに関する情報を表示する `Name` パラメーターを使用します。

## <a name="defining-the-cmdlet-class"></a>コマンドレットクラスの定義

コマンドレットの作成の最初の手順では、常にコマンドレットに名前を付け、コマンドレットを実装する .NET クラスを宣言します。 このコマンドレットはプロセス情報を取得するため、ここで選択した動詞名は "Get" です。 (情報を取得できるほとんどすべての種類のコマンドレットは、コマンドライン入力を処理できます)。承認されたコマンドレット動詞の詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。

この Get Proc コマンドレットの定義を次に示します。 この定義の詳細につい[ては、最初のコマンドレットの作成](./creating-a-cmdlet-without-parameters.md)に関する説明をご確認ください。

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-input-from-the-pipeline"></a>パイプラインからの入力の定義

このセクションでは、コマンドレットのパイプラインからの入力を定義する方法について説明します。 この Get Proc コマンドレットは、「[コマンドライン入力を処理するパラメーターの追加](./adding-parameters-that-process-command-line-input.md)」で説明されているように、`Name` パラメーターを表すプロパティを定義します。 (パラメーターの宣言に関する一般的な情報については、「」を参照してください)。

ただし、コマンドレットでパイプラインの入力を処理する必要がある場合は、Windows PowerShell ランタイムによって入力値にバインドされたパラメーターを持つ必要があります。 これを行うには、`ValueFromPipeline` キーワードを追加するか、または `ValueFromPipelineByProperty` キーワードを[system.object 属性宣言](/dotnet/api/System.Management.Automation.ParameterAttribute)に追加する必要があります。 コマンドレットが入力オブジェクト全体にアクセスする場合は、`ValueFromPipeline` キーワードを指定します。 コマンドレットがオブジェクトのプロパティのみにアクセスする場合は、`ValueFromPipelineByProperty` を指定します。

パイプライン入力を受け入れるこの Get Proc コマンドレットの `Name` パラメーターのパラメーター宣言を次に示します。

[!code-csharp[GetProcessSample03.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs#L35-L44 "GetProcessSample03.cs")]

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

前の宣言では、`ValueFromPipeline` キーワードを `true` に設定しています。これにより、オブジェクトがパラメーターと同じ型である場合、または同じ型に強制的に変換できる場合は、Windows PowerShell ランタイムがパラメーターを受信オブジェクトにバインドします。 `ValueFromPipelineByPropertyName` キーワードも `true` に設定されます。これにより、Windows PowerShell ランタイムは `Name` プロパティの受信オブジェクトを確認します。 受信オブジェクトにこのようなプロパティがある場合、ランタイムは、受信オブジェクトの `Name` プロパティに `Name` パラメーターをバインドします。

> [!NOTE]
> パラメーターの `ValueFromPipeline` attribute キーワードの設定は、`ValueFromPipelineByPropertyName` キーワードの設定よりも優先されます。

## <a name="overriding-an-input-processing-method"></a>入力処理メソッドのオーバーライド

コマンドレットがパイプライン入力を処理する場合は、適切な入力処理メソッドをオーバーライドする必要があります。 基本的な入力処理方法は、[最初のコマンドレットを作成するとき](./creating-a-cmdlet-without-parameters.md)に導入されます。

この Get Proc コマンドレットは、ユーザーまたはスクリプトによって指定された `Name` パラメーターの入力を処理するために、 [system.servicemodel メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)オーバーライドします。 このメソッドは、要求された各プロセス名のプロセスを取得します。名前が指定されていない場合は、すべてのプロセスを取得します。 [WriteObject (system.object, system.string)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)の呼び出しが、出力オブジェクトをパイプラインに送信するための出力機構として使用されていることに注意し[てください。](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) この呼び出しの2番目のパラメーターである `enumerateCollection`は `true` に設定され、プロセスオブジェクトの配列を列挙し、一度に1つのプロセスをコマンドラインに書き込むように Windows PowerShell ランタイムに指示します。

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

完全なC#サンプルコードについては、「 [GetProcessSample03 sample](./getprocesssample03-sample.md)」を参照してください。

## <a name="defining-object-types-and-formatting"></a>オブジェクトの種類と書式設定の定義

Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。 そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。 新しい型を定義する、または既存の型を拡張する方法の詳細については、「[オブジェクトの型と書式設定の拡張](/previous-versions//ms714665(v=vs.85))」を参照してください。

## <a name="building-the-cmdlet"></a>コマンドレットのビルド

コマンドレットを実装した後は、Windows powershell スナップインを使用して Windows PowerShell に登録する必要があります。 コマンドレットの登録の詳細については、「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。

## <a name="testing-the-cmdlet"></a>コマンドレットのテスト

コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行してテストします。 たとえば、サンプルコマンドレットのコードをテストします。 コマンドラインからコマンドレットを使用する方法の詳細については、「 [Windows PowerShell を使用したはじめに](/powershell/scripting/getting-started/getting-started-with-windows-powershell)」を参照してください。

- Windows PowerShell プロンプトで、次のコマンドを入力して、パイプラインを介してプロセス名を取得します。

    ```powershell
    PS> type ProcessNames | get-proc
    ```

次のような出力が表示されます。

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
    -------  ------  -----   ----- -----   ------    --  -----------
        809      21  40856    4448    147    9.50  2288  iexplore
        737      21  26036   16348    144   22.03  3860  iexplore
         39       2   1024     388     30    0.08  3396  notepad
       3927      62  71836   26984    467  195.19  1848  OUTLOOK
    ```

- 次の行を入力して、"IEXPLORE.EXE" というプロセスから `Name` プロパティを持つプロセスオブジェクトを取得します。 この例では、(Windows PowerShell によって提供される) `Get-Process` コマンドレットを上流のコマンドとして使用して、"IEXPLORE.EXE" プロセスを取得します。

    ```powershell
    PS> get-process iexplore | get-proc
    ```

次のような出力が表示されます。

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
    -------  ------  -----      ----- -----   ------     -- -----------
        801      21  40720    6544    142    9.52  2288  iexplore
        726      21  25872   16652    138   22.09  3860  iexplore
        801      21  40720    6544    142    9.52  2288  iexplore
        726      21  25872   16652    138   22.09  3860  iexplore
    ```

## <a name="see-also"></a>参照

[コマンドライン入力を処理するパラメーターの追加](./adding-parameters-that-process-command-line-input.md)

[最初のコマンドレットの作成](./creating-a-cmdlet-without-parameters.md)

[オブジェクトの種類と書式設定の拡張](/previous-versions//ms714665(v=vs.85))

[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))

[Windows PowerShell リファレンス](../windows-powershell-reference.md)

[コマンドレットのサンプル](./cmdlet-samples.md)
