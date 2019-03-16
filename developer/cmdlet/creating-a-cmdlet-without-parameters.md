---
title: パラメーターを指定しないでコマンドレットを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell Programmers Guide], creating
- cmdlets [PowerShell Programmers Guide], basic cmdlet
ms.assetid: 54236ef3-82db-45f8-9114-1ecb7ff65d3e
caps.latest.revision: 8
ms.openlocfilehash: c380b28570c955de6f41152fd617f5c1b0f9e4bd
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054698"
---
# <a name="creating-a-cmdlet-without-parameters"></a>パラメーターなしでコマンドレットを作成する

このセクションでは、パラメーターを使用せず、ローカル コンピューターから情報を取得し、パイプラインに情報を書き込みますコマンドレットを作成する方法について説明します。 ここで説明するコマンドレットは、ローカル コンピューターのプロセスに関する情報を取得し、コマンドラインでその情報を表示する Get-proc コマンドレットです。

このセクションのトピックで、次のとおりです。

- [コマンドレットの名前を付ける](#Naming-the-Cmdlet)

- [コマンドレット クラスを定義します。](#Defining-the-Cmdlet-Class)

- [入力処理メソッドをオーバーライドします。](#Overriding-an-Input-Processing-Method)

- [コード サンプル](#Code-Sample)

- [オブジェクトの種類を定義して、書式設定](#Defining-Object-Types-and-Formatting)

- [コマンドレットを構築](#Building-the-Cmdlet)

- [テスト コマンドレット](#Testing-the-Cmdlet)

> [!NOTE]
> コマンドレットを記述する場合、Windows PowerShell® 参照アセンブリがダウンロードされるディスク上に (既定で C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0 など) を認識します。グローバル アセンブリ キャッシュ (GAC) には未インストールします。

## <a name="naming-the-cmdlet"></a>コマンドレットの名前を付ける

コマンドレット名は、コマンドレットは、アクションを示す動詞と名詞コマンドレットが実行される項目を示すで構成されます。 "Get,"で定義されている動詞を使用、このサンプル Get-proc コマンドレットは、プロセス オブジェクトを取得するため、 [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon)列挙、およびプロセスの項目に、コマンドレットが動作するかを示すには、"Proc"という名詞の部分。

When naming cmdlets, do not use any of the following characters: # , () {} [] & - /\ $ ; : " '<> &#124; ? @ ` .

### <a name="choosing-a-noun"></a>名詞を選択します。

固有名詞を選択する必要があります。 短縮バージョン、製品名の付いた名詞の単数形を使用することをお勧めします。 この型の例のコマンドレットの名前は"`Get-SQLServer`"。

### <a name="choosing-a-verb"></a>動詞を選択します。

承認されたコマンドレット動詞名のセットからの動詞を使用する必要があります。 承認されたコマンドレット動詞の詳細については、次を参照してください。[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)します。

## <a name="defining-the-cmdlet-class"></a>コマンドレット クラスを定義します。

コマンドレット名を選択すると、コマンドレットを実装する .NET クラスを定義します。 このサンプル Get-proc コマンドレットのクラス定義を次に示します。

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

クラスの定義の前にあることに注意して、 [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute)属性構文と`[Cmdlet(verb, noun, ...)]`、コマンドレットとしては、このクラスを識別するために使用します。 これは、すべてのコマンドレットの唯一の必須属性でき、これらを正しく呼び出す Windows PowerShell ランタイム。 必要に応じてさらに、クラスを宣言する属性のキーワードを設定することができます。 サンプル GetProcCommand クラスの属性の宣言が Get-proc コマンドレットの名詞と動詞名だけを宣言することに注意します。

> [!NOTE]
> 設定できるキーワードは、Windows PowerShell のすべての属性クラスの属性クラスのプロパティに対応します。

コマンドレットのクラスの名前を付けるときは、クラス名でコマンドレット名を反映することをお勧めします。 これを行うには、"VerbNounCommand"の形式を使用し、動詞と名詞を使用、コマンドレット名を「動詞」と「名詞」を置き換えます。 サンプルの Get-proc コマンドレットがという GetProcCommand から派生するクラスを定義しますが示すように、前のクラス定義で、 [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)基本クラス。

> [!IMPORTANT]
> Windows PowerShell ランタイムに直接アクセスするためのコマンドレットを定義する場合は、.NET クラスの派生元、 [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)基本クラス。 このクラスの詳細については、次を参照してください。[コマンドレットにその定義のパラメーター セットを作成する](./adding-parameter-sets-to-a-cmdlet.md)します。

> [!NOTE]
> コマンドレットのクラスする必要があります明示的にパブリックと指定します。 Public としてマークされていないクラスは、内部には既定でと、Windows PowerShell ランタイムでは検出されません。

Windows PowerShell を使用して、 [Microsoft.PowerShell.Commands](/dotnet/api/Microsoft.PowerShell.Commands)コマンドレット クラスの名前空間。 API 名前空間、xxx.PS.Commands などのコマンドの名前空間に、コマンドレット クラスを配置することをお勧めします。

## <a name="overriding-an-input-processing-method"></a>入力処理メソッドをオーバーライドします。

[System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)クラスは、コマンドレットをオーバーライドする必要がありますが少なくとも 1 つ、3 つの主な入力処理メソッドを提供します。 Windows PowerShell がレコードを処理する方法の詳細については、次を参照してください。 [Windows PowerShell のしくみ](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)します。

Windows PowerShell ランタイムが呼び出すすべての種類の入力では、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)処理を有効にします。 コマンドレットは、前処理またはセットアップを実行する必要がある場合、このメソッドをオーバーライドすることでこれが実行できます。

> [!NOTE]
> Windows PowerShell では、"record"という用語を使用して、コマンドレットが呼び出されたときに指定されたパラメーター値のセットについて説明します。

これをオーバーライドする必要があります、コマンドレットがパイプラインの入力を受け入れる場合、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド、および必要に応じて、 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド。 たとえば、コマンドレットの方が優先両方のメソッドを使用して、すべての入力を収集する場合[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)し、入力に 1 つの要素ではなく、全体として、一度にとして動作し、 `Sort-Object`コマンドレットでは。

これをオーバーライドする必要があります、コマンドレットがパイプラインの入力を受け取らない場合、 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド。 このメソッドは、の代わりに頻繁に使用されるかどうかを注意[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)ときコマンドレットは操作できません。 1 つの要素、時に、並べ替えコマンドレットの場合と同様です。

このサンプル Get-proc コマンドレットは、パイプラインの入力を受け取る必要があります、ため、オーバーライド、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッドの既定の実装を使用して[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)と[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)します。 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override キーワードを使用して、コマンドラインに書き込むし、プロセスを取得します、 [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッド。

```csharp
protected override void ProcessRecord()
{
  // Get the current processes
  Process[] processes = Process.GetProcesses();

  // Write the processes to the pipeline making them available
  // to the next cmdlet. The second parameter of this call tells
  // PowerShell to enumerate the array, and send one process at a
  // time to the pipeline.
  WriteObject(processes, true);
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ Get the current processes.
    Dim processes As Process()
    processes = Process.GetProcesses()

    '/ Write the processes to the pipeline making them available
    '/ to the next cmdlet. The second parameter of this call tells
    '/ PowerShell to enumerate the array, and send one process at a
    '/ time to the pipeline.
    WriteObject(processes, True)

End Sub 'ProcessRecord
```

#### <a name="things-to-remember-about-input-processing"></a>入力の処理に関する注意点

- 入力の既定のソースは、コマンドラインでユーザーによって提供される明示的なオブジェクト (たとえば、文字列) です。 詳細については、次を参照してください。[コマンドライン入力データを処理するコマンドレットを作成する](./adding-parameters-that-process-command-line-input.md)します。

- メソッドの処理の入力では、パイプラインのアップ ストリームのコマンドレットの出力オブジェクトからの入力も受信できます。 詳細については、次を参照してください。[プロセス パイプラインの入力にコマンドレットを作成する](./adding-parameters-that-process-pipeline-input.md)します。 対応するコマンドレットはコマンド ラインの組み合わせから入力を受け取るし、パイプラインのソースします。

- 長い間、またはまったく、ダウン ストリームのコマンドレットを返しません可能性があります。 そのため、入力、コマンドレットでメソッドを処理する必要がありますロックが保持されない呼び出し中に[System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)、特にロックが、スコープがコマンドレットのインスタンスを超えて拡張されます。

> [!IMPORTANT]
> コマンドレットは呼び出さないで[System.Console.Writeline*](/dotnet/api/System.Console.WriteLine)またはそれと同等です。

- コマンドレットはオブジェクト変数が完了したら、クリーンアップする必要がありますの処理 (ファイル ハンドルが開く場合など、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッドと保持で使用するためのハンドルを開く[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord))。 Windows PowerShell ランタイムが常に呼び出していないことに注意してください、 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッドで、オブジェクトのクリーンアップを実行する必要があります。

たとえば、 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)途中、コマンドレットが取り消されたかコマンドレットのすべての部分でエラーが発生した場合は、終了が呼び出されません。 したがって、オブジェクトのクリーンアップが必要なコマンドレットを完全に実装[System.IDisposable](/dotnet/api/System.IDisposable)パターン、ランタイムは、両方を呼び出すことができますができるように、ファイナライザーを含む[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)と[System.IDisposable.Dispose*](/dotnet/api/System.IDisposable.Dispose)処理の最後にします。

## <a name="code-sample"></a>コード サンプル

完全なC#サンプル コードは、「 [GetProcessSample01 サンプル](./getprocesssample01-sample.md)します。

## <a name="defining-object-types-and-formatting"></a>オブジェクトの種類を定義して、書式設定

Windows PowerShell は、.NET オブジェクトを使用してコマンドレット間で情報を渡します。 その結果、コマンドレットは、独自の型を定義する必要がありますか、コマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。 新しい型を定義するか、既存の型の拡張の詳細については、次を参照してください。[を拡張するオブジェクトの種類と書式](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)します。

## <a name="building-the-cmdlet"></a>コマンドレットを構築

コマンドレットを実装するには、後にする必要がありますに登録する Windows PowerShell Windows PowerShell スナップインを使用します。 コマンドレットの登録の詳細については、次を参照してください。[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。

## <a name="testing-the-cmdlet"></a>テスト コマンドレット

コマンドレットは、Windows PowerShell を使用した登録しているときに、コマンドラインで実行してテストできます。 サンプル Get-proc コマンドレットのコードは小さいが、Windows PowerShell ランタイムとこれには、既存の .NET オブジェクトを引き続き使用します。 Get プロシージャが実行できる内容とその出力を使用する方法を理解することをテストしてみましょう。 詳細については、コマンドラインからコマンドレットを使用して、次を参照してください。、 [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)します。

1. Windows PowerShell を起動し、コンピューターで実行されている現在のプロセスを取得します。

    ```powershell
    get-proc
    ```

    次の出力が表示されます。

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    254      7       7664   12048  66     173.75  1200  QCTRAY
    32       2       1372   2628   31       0.04  1860  DLG
    271      6       1216   3688   33       0.03  3816  lg
    27       2       560    1920   24       0.01  1768  TpScrex
    ...
    ```

2. コマンドレットの結果を簡単に操作するには、変数を割り当てます。

    ```powershell
    $p=get-proc
    ```

3. プロセスの数を取得します。

    ```powershell
    $p.length
    ```

    次の出力が表示されます。

    ```output
    63
    ```

4. 特定のプロセスを取得します。

    ```powershell
    $p[6]
    ```

    次の出力が表示されます。

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id    ProcessName
    -------  ------  -----  -----  -----  ------  --    -----------
    1033     3       2400   3336   35     0.53    1588  rundll32
    ```

5. このプロセスの開始時刻を取得します。

    ```powershell
    $p[6].starttime
    ```

    次の出力が表示されます。

    ```output
    Tuesday, July 26, 2005 9:34:15 AM
    ```

    ```powershell
    $p[6].starttime.dayofyear
    ```

    ```output
    207
    ```

6. ハンドル数は 500 より大きいプロセスを取得し、結果を並べ替えます。

    ```powershell
    $p | Where-Object {$_.HandleCount -gt 500 } | Sort-Object HandleCount
    ```

    次の出力が表示されます。

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    568      14      2164   4972   39     5.55    824  svchost
    716       7      2080   5332   28    25.38    468  csrss
    761      21      33060  56608  440  393.56    3300 WINWORD
    791      71      7412   4540   59     3.31    492  winlogon
    ...
    ```

7. 使用して、`Get-Member`コマンドレットをそれぞれのプロセスで使用できるプロパティを一覧表示します。

    ```powershell
    $p | Get-Member -MemberType property
    ```

    ```output
        TypeName: System.Diagnostics.Process
    ```

    次の出力が表示されます。

    ```output
    Name                     MemberType Definition
    ----                     ---------- ----------
    BasePriority             Property   System.Int32 BasePriority {get;}
    Container                Property   System.ComponentModel.IContainer Conta...
    EnableRaisingEvents      Property   System.Boolean EnableRaisingEvents {ge...
    ...
    ```

## <a name="see-also"></a>参照

[コマンドラインの入力を処理するコマンドレットを作成します。](./adding-parameters-that-process-command-line-input.md)

[パイプラインの入力を処理するコマンドレットを作成します。](./adding-parameters-that-process-pipeline-input.md)

[Windows PowerShell コマンドレットを作成する方法](https://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[オブジェクトの種類を拡張して、書式設定](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Windows PowerShell の動作](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Windows PowerShell リファレンス](../windows-powershell-reference.md)

[コマンドレットのサンプル](./cmdlet-samples.md)