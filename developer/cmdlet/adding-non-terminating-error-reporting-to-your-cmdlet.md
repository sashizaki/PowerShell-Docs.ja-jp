---
title: 未終了エラー レポート、コマンドレットに追加する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2a1531a-a92a-4606-9d54-c5df80d34f33
caps.latest.revision: 8
ms.openlocfilehash: 3741982f81efa04d8fe7ab448fba5f2fdf4b0c01
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068866"
---
# <a name="adding-non-terminating-error-reporting-to-your-cmdlet"></a>終了しないエラーのレポートをコマンドレットに追加する

コマンドレットは、呼び出すことで終了しないエラーを報告できる、 [System.Management.Automation.Cmdlet.WriteError][]メソッドと、引き続き現在の入力オブジェクトまたはそれ以上の受信を操作するオブジェクトをパイプラインします。
このセクションでは、その入力処理メソッドから終了しないエラーを報告するコマンドレットを作成する方法について説明します。

終了しないエラー (だけでなく終了するエラー) のコマンドレットを渡す必要があります、 [System.Management.Automation.ErrorRecord][]エラーを識別するオブジェクト。
各 error レコードには、「エラー識別子」と呼ばれる一意の文字列によって識別されます。
識別子、だけでなく、各エラーのカテゴリがによって定義される定数で指定された、 [System.Management.Automation.ErrorCategory][]列挙体。
ユーザーが設定して、カテゴリに基づいてエラーを表示できます、`$ErrorView`変数を"CategoryView"にします。

エラー レコードの詳細については、次を参照してください。 [Windows PowerShell のエラー レコード](./windows-powershell-error-records.md)します。

## <a name="defining-the-cmdlet"></a>コマンドレットを定義します。

コマンドレットの作成の最初の手順は常に、コマンドレットの名前を付けると、コマンドレットを実装する .NET クラスを宣言します。
このコマンドレットは、ため、ここで選択した動詞名は"Get"プロセスの情報を取得します。
(ほぼあらゆる種類の情報を取得するのに対応しているコマンドレットは、コマンドラインの入力を処理できます)承認されたコマンドレット動詞の詳細については、次を参照してください。[コマンドレット動詞名](approved-verbs-for-windows-powershell-commands.md)します。

この Get-proc コマンドレットの定義を次に示します。
この定義の詳細が記載[最初のコマンドレットを作成](creating-a-cmdlet-without-parameters.md)です。

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-parameters"></a>パラメーターを定義します。

必要に応じて、コマンドレットは、入力を処理するためのパラメーターを定義する必要があります。
この Get-proc コマンドレットを定義、**名前**パラメーター」の説明に従って[プロセス コマンド ライン入力パラメーターを追加する](adding-parameters-that-process-command-line-input.md)します。

パラメーター宣言を次に示します、**名前**この Get-proc コマンドレットのパラメーター。

```csharp
[Parameter(
           Position = 0,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true
)]
[ValidateNotNullOrEmpty]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;
```

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

## <a name="overriding-input-processing-methods"></a>入力処理メソッドをオーバーライドします。

すべてのコマンドレットは、少なくとも 1 つの入力によって提供されるメソッドの処理をオーバーライドする必要があります、 [System.Management.Automation.Cmdlet][]クラス。
これらのメソッドは、後ほど[最初のコマンドレットを作成](creating-a-cmdlet-without-parameters.md)です。

> [!NOTE]
> コマンドレットが処理されない各レコードできるだけ独立しています。

この Get-proc コマンドレットよりも優先、 [System.Management.Automation.Cmdlet.ProcessRecord][]を処理するメソッド、**名前**ユーザーまたはスクリプトによって提供される入力パラメーター。
名前が指定されていない場合、このメソッドは各要求のプロセス名またはすべてのプロセスのプロセスを取得します。
この上書きの詳細が記載[最初のコマンドレットを作成](creating-a-cmdlet-without-parameters.md)です。

### <a name="things-to-remember-when-reporting-errors"></a>エラーを報告する際の注意点

[System.Management.Automation.ErrorRecord][]コマンドレットが根本的に、例外エラーを書き込む必要がある場合に合格するオブジェクトします。
使用して例外を決定する際に、.NET のガイドラインに従います。
基本的に、エラーは、既存の例外と同じである意味場合、コマンドレットを使用またはその例外から派生します。
それ以外の場合、新しい例外またはから直接例外階層を派生する必要がありますが、 [System.Exception][]クラス。

エラーの識別子 (ErrorRecord クラスの FullyQualifiedErrorId プロパティからアクセスする) を作成するときに、次に注意してください。

- 対象となるは、エラーの入手元とは完全修飾識別子を検査する際に、どのようなエラーを確認できるように診断目的で使用して文字列。

- 適切な形式の完全修飾エラー識別子は、ようになります可能性があります。

`CommandNotFoundException,Microsoft.PowerShell.Commands.GetCommandCommand`

前の例では、エラー識別子 (最初のトークン) を指定エラーを確認し、残りの部分では、エラーの出所を示します。

- 複雑なシナリオは、エラーの識別子は検査で解析できるドット区切りトークンを指定できます。
  これにより、エラーの識別子と、エラーの識別子、エラー カテゴリの部分にも分岐します。

コマンドレットは、異なるコード パスを特定のエラー識別子を割り当てる必要があります。
次の情報に注意してエラーの識別子の割り当てのために注意してください。

- エラー識別子は、コマンドレットのライフ サイクル全体で一定する必要があります。
  コマンドレットのバージョン間でのエラー識別子のセマンティクスは変更されません。

- 答えました報告されるエラーに対応するエラーの識別子のテキストを使用します。
  空白や句読点を使用しないでください。

- 再現可能なエラー識別子のみを生成するコマンドレットがあります。
  たとえば、プロセス識別子を含む識別子は生成しません。
  エラー識別子は、同じ問題が発生している他のユーザーに表示される識別子に対応する場合にのみ、ユーザーに役立ちます。

次の条件では、PowerShell によってハンドルされない例外はキャッチしません。

- コマンドレットは、新しいスレッドおよびスレッド ハンドルされない例外をスローすることで実行されているコードを作成する場合、PowerShell は、エラーはキャッチできないと、プロセスが終了します。

- オブジェクトは、そのデストラクターまたは Dispose メソッドでハンドルされない例外を発生させるコードが、PowerShell は、エラーはキャッチできないと、プロセスが終了します。

## <a name="reporting-nonterminating-errors"></a>終了しないエラーの報告

入力処理メソッドのいずれかが終了しないエラーを報告、出力ストリームを使用して、 [System.Management.Automation.Cmdlet.WriteError][]メソッド。

呼び出しを示しますこの Get-proc コマンドレットからのコード例を次に示します[System.Management.Automation.Cmdlet.WriteError][]からのオーバーライドの中で、 [System.Management.Automation.Cmdlet.ProcessRecord][]メソッド。
ここで、呼び出しには、コマンドレットは、指定されたプロセスの識別子のプロセスを見つけられない場合が行われます。

```csharp
protected override void ProcessRecord()
{
  // If no name parameter passed to cmdlet, get all processes.
  if (processNames == null)
  {
    WriteObject(Process.GetProcesses(), true);
  }
    else
    {
      // If a name parameter is passed to cmdlet, get and write
      // the associated processes.
      // Write a nonterminating error for failure to retrieve
      // a process.
      foreach (string name in processNames)
      {
        Process[] processes;

        try
        {
          processes = Process.GetProcessesByName(name);
        }
        catch (InvalidOperationException ex)
        {
          WriteError(new ErrorRecord(
                     ex,
                     "NameNotFound",
                     ErrorCategory.InvalidOperation,
                     name));
          continue;
        }

        WriteObject(processes, true);
      } // foreach (...
    } // else
  }
```

### <a name="things-to-remember-about-writing-nonterminating-errors"></a>終了しないエラーの記述に関する注意点

終了しないエラーでは、このコマンドレットは、各入力オブジェクトの特定のエラー識別子を生成する必要があります。

コマンドレットは頻繁に終了しないエラーによって生成された PowerShell アクションを変更する必要があります。
これを行うこと、`ErrorAction`と`ErrorVariable`パラメーター。
定義する場合、`ErrorAction`パラメーター、コマンドレットは、ユーザー オプションを表示します[System.Management.Automation.ActionPreference][]を設定して、アクションも直接影響、`$ErrorActionPreference`変数。

終了しないエラーを保存、変数を使用して、コマンドレット、`ErrorVariable`パラメーターの設定の影響を受けません`ErrorAction`します。
エラーは、変数名の前にプラス記号 (+) を追加することで、既存のエラー変数に追加できます。

## <a name="code-sample"></a>コード サンプル

完全なC#サンプル コードは、「 [GetProcessSample04 サンプル](./getprocesssample04-sample.md)します。

## <a name="define-object-types-and-formatting"></a>オブジェクトの種類と書式設定を定義します。

PowerShell では、.NET オブジェクトを使用してコマンドレット間で情報を渡します。
その結果、コマンドレットは、独自の型を定義する必要がありますか、コマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。
新しい型を定義するか、既存の型の拡張の詳細については、次を参照してください。[を拡張するオブジェクトの種類と書式](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)します。

## <a name="building-the-cmdlet"></a>コマンドレットを構築

コマンドレットを実装するには、後にする必要がありますに登録する Windows PowerShell Windows PowerShell スナップインを使用します。
コマンドレットの登録の詳細については、次を参照してください。[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。

## <a name="testing-the-cmdlet"></a>テスト コマンドレット

PowerShell を使用した、コマンドレットを登録しているときに、コマンドラインで実行してテストできます。
エラーを報告するかどうかを確認するサンプル Get-proc コマンドレットをテストしてみましょう。

- PowerShell を起動し、Get-proc コマンドレットを使用して"TEST"という名前のプロセスを取得します。

    ```powershell
    PS> get-proc -name test
    ```

次の出力が表示されます。

    ```
    get-proc : Operation is not valid due to the current state of the object.
    At line:1 char:9
    + get-proc  <<<< -name test
    ```

## <a name="see-also"></a>参照

[プロセス パイプラインの入力パラメーターを追加します。](./adding-parameters-that-process-pipeline-input.md)

[コマンドライン入力を処理するパラメーターの追加](./adding-parameters-that-process-command-line-input.md)

[初めてのコマンドレットを作成します。](./creating-a-cmdlet-without-parameters.md)

[オブジェクトの種類を拡張して、書式設定](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Windows PowerShell リファレンス](../windows-powershell-reference.md)

[コマンドレットのサンプル](./cmdlet-samples.md)

[System.Exception]: /dotnet/api/System.Exception
[System.Management.Automation.ActionPreference]: /dotnet/api/System.Management.Automation.ActionPreference
[System.Management.Automation.Cmdlet.ProcessRecord]: /dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord
[System.Management.Automation.Cmdlet.WriteError]: /dotnet/api/System.Management.Automation.Cmdlet.WriteError
[System.Management.Automation.Cmdlet]: /dotnet/api/System.Management.Automation.Cmdlet
[System.Management.Automation.ErrorCategory]: /dotnet/api/System.Management.Automation.ErrorCategory
[System.Management.Automation.ErrorRecord]: /dotnet/api/System.Management.Automation.ErrorRecord
