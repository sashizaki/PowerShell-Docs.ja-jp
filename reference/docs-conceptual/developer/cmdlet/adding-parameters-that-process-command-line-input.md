---
title: コマンドライン入力を処理するパラメーターを追加する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell Programmer's Guide], parameters
- Get-Proc cmdlet [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], command line input
- command line input [PowerShell Programmer's Guide]
- parameters [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], creating
ms.assetid: da0b32f8-7b51-440e-a061-3177b5759e0e
caps.latest.revision: 9
ms.openlocfilehash: b8ade5607595fd4453b2a4d69a6345880e58192b
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870457"
---
# <a name="adding-parameters-that-process-command-line-input"></a>コマンドライン入力を処理するパラメーターを追加する

コマンドレットの1つの入力ソースは、コマンドラインです。 このトピックでは、コマンドレットに渡された明示的なオブジェクトに基づいてローカルコンピューターからの入力を処理できるように、`Get-Proc` コマンドレット ([最初のコマンドレットの作成](./creating-a-cmdlet-without-parameters.md)に関するページで説明) にパラメーターを追加する方法について説明します。 ここで説明する `Get-Proc` コマンドレットは、名前に基づいてプロセスを取得し、コマンドプロンプトでプロセスに関する情報を表示します。

## <a name="defining-the-cmdlet-class"></a>コマンドレットクラスの定義

コマンドレットの作成の最初の手順は、コマンドレットの名前付けと、コマンドレットを実装する .NET Framework クラスの宣言です。 このコマンドレットはプロセス情報を取得するため、ここで選択した動詞名は "Get" です。 (情報を取得できるほとんどすべての種類のコマンドレットは、コマンドライン入力を処理できます)。承認されたコマンドレット動詞の詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。

`Get-Proc` コマンドレットのクラス宣言を次に示します。 この定義の詳細については[、最初のコマンドレットの作成](./creating-a-cmdlet-without-parameters.md)に関する説明をご覧ください。

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="declaring-parameters"></a>パラメーターの宣言

コマンドレットパラメーターを使用すると、ユーザーはコマンドレットに入力を提供できます。 次の例では、`Get-Proc` と `Get-Member` がパイプラインのコマンドレットの名前であり、`MemberType` は `Get-Member` コマンドレットのパラメーターです。 パラメーターには、"property" という引数があります。

**PS > get-proc;`get-member` membertype プロパティ**

コマンドレットのパラメーターを宣言するには、パラメーターを表すプロパティを最初に定義する必要があります。 `Get-Proc` コマンドレットでは、唯一のパラメーターは `Name`です。この例では、取得する .NET Framework process オブジェクトの名前を表します。 このため、コマンドレットクラスは、名前の配列を受け入れる文字列型のプロパティを定義します。

`Get-Proc` コマンドレットの `Name` パラメーターのパラメーター宣言を次に示します。

```csharp
/// <summary>
/// Specify the cmdlet Name parameter.
/// </summary>
  [Parameter(Position = 0)]
  [ValidateNotNullOrEmpty]
  public string[] Name
  {
    get { return processNames; }
    set { processNames = value; }
  }
  private string[] processNames;

  #endregion Parameters
```

```vb
<Parameter(Position:=0), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

このプロパティが `Name` パラメーターであることを Windows PowerShell ランタイムに通知するには、プロパティ定義に[system.string 属性を](/dotnet/api/System.Management.Automation.ParameterAttribute)追加します。 この属性を宣言するための基本構文は `[Parameter()]`です。

> [!NOTE]
> パラメーターは、明示的にパブリックとしてマークする必要があります。 既定でパブリックに設定されていないパラメーターは、Windows PowerShell ランタイムによって検出されません。

このコマンドレットは、`Name` パラメーターに文字列の配列を使用します。 可能であれば、コマンドレットでパラメーターを配列として定義する必要もあります。これにより、コマンドレットでは複数の項目を受け入れることができるためです。

#### <a name="things-to-remember-about-parameter-definitions"></a>パラメーター定義に関する注意事項

- コマンドレットが Windows PowerShell コマンドレットと互換性があることを確認するために、定義済みの Windows PowerShell パラメーター名とデータ型をできるだけ再利用する必要があります。 たとえば、すべてのコマンドレットが定義済みの `Id` パラメーター名を使用してリソースを識別する場合、ユーザーは使用しているコマンドレットに関係なく、パラメーターの意味を簡単に理解できます。 基本的に、パラメーター名は、共通言語ランタイム (CLR) の変数名に使用される規則と同じ規則に従います。 パラメーターの名前付けの詳細については、「[コマンドレットパラメーター名](/previous-versions/ms714468(v=vs.85))」を参照してください。

- Windows PowerShell では、一貫したユーザーエクスペリエンスを提供するために、いくつかのパラメーター名が予約されています。 これらのパラメーター名は使用しないでください。 `WhatIf`、`Confirm`、`Verbose`、`Debug`、`Warn`、`ErrorAction`、`ErrorVariable`、`OutVariable`、`OutBuffer`です。 また、これらのパラメーター名のエイリアスとして、`vb`、`db`、`ea`、`ev`、`ov`、および `ob`が予約されています。

- `Name` は、コマンドレットで使用するために推奨される単純なパラメーター名です。 このようなパラメーター名は、特定のコマンドレットに固有であり、覚えにくい複合名として選択することをお勧めします。

- Windows PowerShell ではパラメーターの大文字と小文字は区別されませんが、既定では、シェルは大文字小文字を保持します。 引数の大文字と小文字の区別は、コマンドレットの操作によって異なります。 引数は、コマンドラインで指定されたパラメーターに渡されます。

- その他のパラメーター宣言の例については、「[コマンドレットパラメーター](./cmdlet-parameters.md)」を参照してください。

## <a name="declaring-parameters-as-positional-or-named"></a>位置指定または名前付きパラメーターの宣言

コマンドレットでは、各パラメーターを位置指定パラメーターまたは名前付きパラメーターのどちらかとして設定する必要があります。 どちらの種類のパラメーターも、1つの引数、コンマで区切られた複数の引数、およびブール値の設定を受け取ります。 ブール型パラメーター (*スイッチ*とも呼ばれます) は、ブール値の設定のみを処理します。 スイッチは、パラメーターの存在を確認するために使用されます。 推奨される既定値は `false`です。

Sample `Get-Proc` コマンドレットは、位置指定パラメーターとして `Name` パラメーターを定義します。
0. これは、ユーザーがコマンドラインに入力した最初の引数が、このパラメーターに自動的に挿入されることを意味します。 ユーザーがコマンドラインからパラメーター名を指定する必要のある名前付きパラメーターを定義する場合は、`Position` キーワードを属性宣言の外に残します。

> [!NOTE]
> パラメーターの名前を指定する必要がない限り、最も使用されているパラメーターを設定して、ユーザーがパラメーター名を入力する必要がないようにすることをお勧めします。

## <a name="declaring-parameters-as-mandatory-or-optional"></a>必須またはオプションとしてのパラメーターの宣言

コマンドレットでは、各パラメーターを省略可能なパラメーターまたは必須パラメーターのいずれかとして設定する必要があります。 Sample `Get-Proc` コマンドレットでは、`Mandatory` キーワードが属性宣言で設定されていないため、`Name` パラメーターはオプションとして定義されます。

## <a name="supporting-parameter-validation"></a>パラメーター検証のサポート

Sample `Get-Proc` コマンドレットは、入力の検証属性[である](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute)system.string を `Name` パラメーターに追加して、入力が `null` も空でもないことを検証できるようにします。 この属性は、Windows PowerShell によって提供されるいくつかの検証属性の1つです。 その他の検証属性の例については、「[パラメーター入力の検証](./validating-parameter-input.md)」を参照してください。

```
[Parameter(Position = 0)]
[ValidateNotNullOrEmpty]
public string[] Name
```

## <a name="overriding-an-input-processing-method"></a>入力処理メソッドのオーバーライド

コマンドレットがコマンドライン入力を処理する場合は、適切な入力処理メソッドをオーバーライドする必要があります。 基本的な入力処理方法は、[最初のコマンドレットを作成するとき](./creating-a-cmdlet-without-parameters.md)に導入されます。

`Get-Proc` コマンドレットは、ユーザーまたはスクリプトによって指定された `Name` パラメーターの入力を処理するために、 [system.servicemodel メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)オーバーライドします。 このメソッドは、要求された各プロセス名のプロセスを取得します。名前が指定されていない場合は、すべてのプロセスを取得します。 [WriteObject% 2csystem.string %29](/dotnet/api/system.management.automation.cmdlet.writeobject?view=powershellsdk-1.1.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)の呼び出しは、出力オブジェクトをパイプラインに送信するための出力機構として使用されていることに注意してください。[processrecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) この呼び出しの2番目のパラメーターである `enumerateCollection`は `true` に設定され、プロセスオブジェクトの出力配列を列挙し、一度に1つのプロセスをコマンドラインに書き込むように Windows PowerShell ランタイムに通知します。

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
    }
  }
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ If no process names are passed to the cmdlet, get all processes.
    If processNames Is Nothing Then
        Dim processes As Process()
        processes = Process.GetProcesses()
    End If

    '/ If process names are specified, write the processes to the
    '/ pipeline to display them or make them available to the next cmdlet.

    For Each name As String In processNames
        '/ The second parameter of this call tells PowerShell to enumerate the
        '/ array, and send one process at a time to the pipeline.
        WriteObject(Process.GetProcessesByName(name), True)
    Next

End Sub 'ProcessRecord
```

## <a name="code-sample"></a>コード サンプル

完全なC#サンプルコードについては、「 [GetProcessSample02 sample](./getprocesssample02-sample.md)」を参照してください。

## <a name="defining-object-types-and-formatting"></a>オブジェクトの種類と書式設定の定義

Windows PowerShell は、.NET Framework オブジェクトを使用してコマンドレット間で情報を渡します。 そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。 新しい型を定義する、または既存の型を拡張する方法の詳細については、「[オブジェクトの型と書式設定の拡張](/previous-versions/ms714665(v=vs.85))」を参照してください。

## <a name="building-the-cmdlet"></a>コマンドレットのビルド

コマンドレットを実装したら、Windows PowerShell スナップインを使用して Windows PowerShell に登録する必要があります。 コマンドレットの登録の詳細については、「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions/ms714644(v=vs.85))」を参照してください。

## <a name="testing-the-cmdlet"></a>コマンドレットのテスト

コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行することでテストできます。 サンプルコマンドレットのコードをテストするには、次の2つの方法があります。 コマンドラインからコマンドレットを使用する方法の詳細については、「 [Windows PowerShell を使用したはじめに](/powershell/scripting/getting-started/getting-started-with-windows-powershell)」を参照してください。

- Windows PowerShell プロンプトで、次のコマンドを使用して、"IEXPLORE.EXE" という名前の Internet Explorer のプロセスを一覧表示します。

  ```powershell
  get-proc -name iexplore
  ```

  次のような出力が表示されます。

  ```Output
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
  -------  ------  -----   -----  -----   ------ --   -----------
      354      11  10036   18992    85   0.67   3284   iexplore
  ```

- Internet Explorer、Outlook、および "IEXPLORE.EXE"、"OUTLOOK"、および "NOTEPAD" という名前のプロセスを一覧表示するには、次のコマンドを使用します。 複数のプロセスがある場合は、すべてのプロセスが表示されます。

  ```powershell
  get-proc -name iexplore, outlook, notepad
  ```

  次のような出力が表示されます。

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
  -------  ------  -----   -----  -----  ------   --   -----------
      732      21  24696    5000    138   2.25  2288   iexplore
      715      19  20556   14116    136   1.78  3860   iexplore
     3917      62  74096   58112    468 191.56  1848   OUTLOOK
       39       2   1024    3280     30   0.09  1444   notepad
       39       2   1024     356     30   0.08  3396   notepad
  ```

## <a name="see-also"></a>関連項目

[パイプライン入力を処理するパラメーターの追加](./adding-parameters-that-process-pipeline-input.md)

[最初のコマンドレットの作成](./creating-a-cmdlet-without-parameters.md)

[オブジェクトの種類と書式設定の拡張](/previous-versions/ms714665(v=vs.85))

[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions/ms714644(v=vs.85))

[Windows PowerShell リファレンス](../windows-powershell-reference.md)

[コマンドレットのサンプル](./cmdlet-samples.md)
