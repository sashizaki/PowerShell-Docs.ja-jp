---
title: コマンドライン入力を処理するパラメーターの追加 |Microsoft Docs
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
ms.openlocfilehash: fb113086ce89e4becff9bcaf3232905fde2bf610
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055922"
---
# <a name="adding-parameters-that-process-command-line-input"></a>コマンドライン入力を処理するパラメーターを追加する

コマンドレットの入力の 1 つのソースは、コマンド ラインです。 このトピックでは、パラメーターを追加する方法を説明します、 **Get-proc**コマンドレット (に記載されている[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md)) コマンドレットは、明示的に基づき、ローカル コンピューターからの入力を処理できるようにオブジェクトは、コマンドレットに渡されます。 **Get-proc**説明されているコマンドレットは、ここで、その名前に基づいてプロセスを取得し、コマンド プロンプトで、プロセスに関する情報を表示します。

次のセクションでは、このトピックでは。

- [コマンドレット クラスを定義します。](#Defining-the-Cmdlet-Class)

- [パラメーターの宣言](#Declaring-Parameters)

- [パラメーターの検証のサポート](#Supporting-Parameter-Validation)

- [入力処理メソッドをオーバーライドします。](#Overriding-an-Input-Processing-Method)

- [コード サンプル](#Code-Sample)

- [オブジェクトの種類を定義して、書式設定](#Defining-Object-Types-and-Formatting)

- [コマンドレットを構築](#Building-the-Cmdlet)

- [テスト コマンドレット](#Testing-the-Cmdlet)

## <a name="defining-the-cmdlet-class"></a>コマンドレット クラスを定義します。

コマンドレットの作成の最初の手順では、コマンドレットの名前付けと、コマンドレットを実装する .NET Framework クラスの宣言です。 このコマンドレットは、ため、ここで選択した動詞名が"Get"にプロセスの情報を取得します (ほぼあらゆる種類の情報を取得するのに対応しているコマンドレットは、コマンドラインの入力を処理できます)承認されたコマンドレット動詞の詳細については、[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)を参照してください。

クラス宣言を次に示します、 **Get-proc**コマンドレット。 この定義に関する詳細情報が記載[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md)です。

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

コマンドレット パラメーターには、コマンドレットへの入力を提供するユーザーが可能になります。 次の例では、 **Get-proc**と`Get-Member`パイプラインのコマンドレットの名前と`MemberType`パラメーターです、`Get-Member`コマンドレット。 パラメーターが、引数「プロパティです」

**PS > get proc です。`get-member` -membertype プロパティ**

コマンドレットのパラメーターを宣言するには、最初にパラメーターを表すプロパティを定義する必要があります。 **Get-proc**コマンドレット、唯一のパラメーターは`Name`をここで取得する .NET Framework のプロセス オブジェクトの名前を表します。 そのため、コマンドレット クラスでは、名前の配列を受け入れるように文字列型のプロパティを定義します。

パラメーター宣言を次に示します、`Name`のパラメーター、 **Get-proc**コマンドレット。

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

このプロパティである Windows PowerShell ランタイムを通知するために、`Name`パラメーター、 [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)属性は、プロパティ定義に追加します。 この属性を宣言するための基本構文は`[Parameter()]`します。

> [!NOTE]
> パラメーターをする必要があります明示的にパブリックと指定します。 内部にパブリックの既定としてマークされていないと、Windows PowerShell ランタイムでは検出できないパラメーター。

このコマンドレットは、文字列の配列を使用して、`Name`パラメーター。 可能であれば、コマンドレットする必要がありますもパラメーターを定義、配列としてため、これにより、1 つ以上の項目をそのまま使用するコマンドレット。

#### <a name="things-to-remember-about-parameter-definitions"></a>パラメーターの定義に関する注意点

- 定義済み Windows PowerShell パラメーター名とデータ型は、コマンドレットが Windows PowerShell コマンドレットと互換性があることを確認することを可能な限り再利用する必要があります。 たとえば、すべてのコマンドレットを使用して、定義済み`Id`ユーザーは、リソースを簡単に識別するためにパラメーター名は、どのようなコマンドレットを使用しているに関係なく、パラメーターの意味を理解します。 基本的に、パラメーター名には、共通言語ランタイム (CLR) 内の変数名に使用されるものと同じ規則に従ってください。 パラメーターの名前付けの詳細については、[コマンドレットのパラメーター名](https://msdn.microsoft.com/en-us/c4500737-0a05-4d01-911b-394424c65bfb)を参照してください。

- Windows PowerShell では、一貫性のあるユーザー エクスペリエンスを提供するいくつかのパラメーター名を予約します。 これらのパラメーター名を使用しない: `WhatIf`、 `Confirm`、 `Verbose`、 `Debug`、 `Warn`、 `ErrorAction`、 `ErrorVariable`、 `OutVariable`、および`OutBuffer`します。 さらに、これらのパラメーター名の次のエイリアスは予約されています: `vb`、 `db`、 `ea`、 `ev`、 `ov`、および`ob`します。

- `Name` コマンドレットで使用するための推奨、単純で一般的なパラメーターの名前です。 次のようにより、特定のコマンドレットに一意で覚えにくい複雑な名前のパラメーター名を選択することをお勧めします。

- パラメーターは、シェルが大文字小文字を保持する既定では、Windows PowerShell では大文字です。 引数の大文字小文字の区別は、コマンドレットの操作に依存します。 引数は、コマンドラインで指定されたパラメーターに渡されます。

- その他のパラメーター宣言の例については、[コマンドレット パラメーター](./cmdlet-parameters.md)を参照してください。

## <a name="declaring-parameters-as-positional-or-named"></a>位置指定または名前付きパラメーターの宣言

コマンドレットをする必要があります各パラメーターとして設定か位置指定か名前付きパラメーター。 パラメーターの両方の種類は、1 つの引数、コンマ、およびブール値の設定で区切られた複数の引数を受け取ります。 呼ばれる、ブール型パラメーター、*切り替える*、ブール型設定のみを処理します。 パラメーターの存在を検出するスイッチを使用します。 推奨される既定値は`false`します。

サンプル**Get-proc**コマンドレットを定義、`Name`位置 0 の位置指定パラメーターとしてパラメーター。 これは、コマンドラインで、ユーザーが入力した最初の引数がこのパラメーターに自動的に挿入されていることを意味します。 名前付きパラメーターを定義する場合は、ユーザーが指定する必要があります、コマンドラインからパラメーター名のままに、`Position`属性の宣言からキーワード。

> [!NOTE]
> パラメーターを指定する必要があります、されない限り、ユーザーは、パラメーター名を入力する必要があるないように、最も使用頻度のパラメーターを位置指定して行うことをお勧めします。

## <a name="declaring-parameters-as-mandatory-or-optional"></a>必須または省略可能パラメーターを宣言します。

コマンドレットは、省略可能または必須のパラメーターとして各パラメーターを設定する必要があります。 サンプルの**Get-proc**コマンドレット、`Name`ために、オプションとしてパラメーターが定義されている、`Mandatory`属性宣言でキーワードが設定されていません。

## <a name="supporting-parameter-validation"></a>パラメーターの検証のサポート

サンプル**Get-proc**コマンドレットは、入力の検証属性を追加します[System.Management.Automation.Validatenotnulloremptyattribute](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute)を、`Name`検証を有効にするパラメーターを、。入力がどちらも`null`も空でも。 この属性では、Windows PowerShell によって提供されるいくつかの検証属性の 1 つです。 その他の検証属性の例については、[パラメーター入力の検証](./validating-parameter-input.md)を参照してください。

```
[Parameter(Position = 0)]
[ValidateNotNullOrEmpty]
public string[] Name
```

## <a name="overriding-an-input-processing-method"></a>入力処理メソッドをオーバーライドします。

コマンドレットは、コマンドライン入力を処理するためには、適切な入力処理メソッドをオーバーライドにする必要があります。 基本的な入力処理メソッドがで導入された[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md)です。

**Get-proc**コマンドレットよりも優先、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)を処理するメソッド、`Name`ユーザーまたはスクリプトによって提供されるパラメーターの入力。 このメソッドは、名前が指定されていない場合、各要求プロセス名またはプロセスのすべてのプロセスを取得します。 ある[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)への呼び出し[System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/system.management.automation.cmdlet.writeobject?view=powershellsdk-1.1.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)出力出力を送信するためのメカニズムは、パイプラインにオブジェクトです。 この呼び出しの 2 番目のパラメーター`enumerateCollection`に設定されている`true`プロセス オブジェクトの出力配列を列挙し、コマンドラインに、一度に 1 つのプロセスを記述する Windows PowerShell ランタイムに通知します。

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

完全なC#サンプル コードは、「 [GetProcessSample02 サンプル](./getprocesssample02-sample.md)します。

## <a name="defining-object-types-and-formatting"></a>オブジェクトの種類を定義して、書式設定

Windows PowerShell は、.NET Framework オブジェクトを使用してコマンドレット間で情報を渡します。 そのため、コマンドレットは、独自の型を定義する必要があります。 またはコマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。 新しい型を定義するか、既存の型の拡張の詳細については、[を拡張するオブジェクトの種類と書式](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)を参照してください。

## <a name="building-the-cmdlet"></a>コマンドレットを構築

コマンドレットを実装した後は、Windows PowerShell スナップインを使用して Windows PowerShell を使用した登録する必要があります。 コマンドレットの登録の詳細については、[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)を参照してください。

## <a name="testing-the-cmdlet"></a>テスト コマンドレット

コマンドレットが Windows PowerShell に登録されたときに、コマンドラインで実行してテストできます。 サンプル コマンドレットのコードをテストする 2 つの方法を示します。 詳細については、コマンドラインからコマンドレットを使用して、[Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)を参照してください。

- Windows PowerShell プロンプトで次のコマンドを使用、Internet Explorer プロセスは、"IEXPLORE"という名前の一覧を表示するには

    ```powershell
    PS> get-proc -name iexplore
    ```

次の出力が表示されます。

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
    -------  ------  -----   -----  -----   ------ --   -----------
        354      11  10036   18992    85   0.67   3284   iexplore
    ```

- Internet Explorer、Outlook、およびメモ帳のプロセスの"と、IEXPLORE"という名前を一覧表示するには、"OUTLOOK"と「メモ帳」は、次のコマンドを使用します。 複数のプロセスがある場合は、それらのすべてが表示されます。

    ```powershell
    PS> get-proc -name iexplore, outlook, notepad
    ```

次の出力が表示されます。

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
    -------  ------  -----   -----  -----  ------   --    -----------
        732      21  24696    5000    138   2.25  2288   iexplore
        715      19  20556   14116    136   1.78  3860   iexplore
       3917      62  74096   58112    468 191.56  1848   OUTLOOK
         39       2   1024    3280     30   0.09  1444   notepad
         39       2   1024     356     30   0.08  3396   notepad
    ```

## <a name="see-also"></a>参照

[プロセス パイプラインの入力パラメーターを追加します。](./adding-parameters-that-process-pipeline-input.md)

[初めてのコマンドレットを作成します。](./creating-a-cmdlet-without-parameters.md)

[オブジェクトの種類を拡張して、書式設定](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Windows PowerShell リファレンス](../windows-powershell-reference.md)

[コマンドレットのサンプル](./cmdlet-samples.md)
