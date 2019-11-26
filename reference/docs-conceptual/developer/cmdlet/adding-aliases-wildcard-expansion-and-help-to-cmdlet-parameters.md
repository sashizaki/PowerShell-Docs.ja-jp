---
title: エイリアス、ワイルドカードの展開、およびコマンドレットパラメーターへのヘルプの追加Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 931ccace-c565-4a98-8dcc-df00f86394b1
caps.latest.revision: 8
ms.openlocfilehash: d210a852a90d94df2ab360dd86f0b83a396330e3
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74415648"
---
# <a name="adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters"></a>エイリアス、ワイルドカード展開、ヘルプをコマンドレット パラメーターに追加する

ここでは、Stop-Proc コマンドレットのパラメーターにエイリアス、ワイルドカード拡張、およびヘルプメッセージを追加する方法について説明します (「[システムを変更するコマンドレットの作成](./creating-a-cmdlet-that-modifies-the-system.md)」で説明)。

この Stop Proc コマンドレットは、Get Proc コマンドレットを使用して取得されたプロセスを停止しようとします (「[最初のコマンドレットを作成する](./creating-a-cmdlet-without-parameters.md)」を参照)。

## <a name="defining-the-cmdlet"></a>コマンドレットの定義

コマンドレットの作成の最初の手順では、常にコマンドレットに名前を付け、コマンドレットを実装する .NET クラスを宣言します。 システムを変更するためのコマンドレットを記述しているので、それに応じた名前を付ける必要があります。 このコマンドレットはシステムプロセスを停止するため、プロセスを示すために "Proc" という名詞を使用して、 [Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)クラスで定義された動詞 "Stop" を使用します。 承認されたコマンドレット動詞の詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。

次のコードは、この Stop Proc コマンドレットのクラス定義です。

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a>システム変更のパラメーターの定義

コマンドレットでは、システムの変更とユーザーフィードバックをサポートするパラメーターを定義する必要があります。 コマンドレットでは、`Name` パラメーターまたはそれと同等のものを定義して、コマンドレットが何らかの種類の識別子でシステムを変更できるようにする必要があります。 さらに、コマンドレットでは、`Force` パラメーターと `PassThru` パラメーターを定義する必要があります。 これらのパラメーターの詳細については、「[システムを変更するコマンドレットを作成](./creating-a-cmdlet-that-modifies-the-system.md)する」を参照してください。

## <a name="defining-a-parameter-alias"></a>パラメーターの別名の定義

パラメーターエイリアスは、コマンドレットパラメーターの代替名または適切に定義された1文字または2文字の短い名前にすることができます。 どちらの場合も、エイリアスを使用する目的は、コマンドラインからのユーザーエントリを簡略化することです。 Windows PowerShell では、宣言構文 [Alias ()] を使用する、system.string[属性のパラメーター](/dotnet/api/System.Management.Automation.AliasAttribute)エイリアスがサポートされています。

次のコードは、`Name` パラメーターにエイリアスを追加する方法を示しています。

```csharp
/// <summary>
/// Specify the mandatory Name parameter used to identify the
/// processes to be stopped.
/// </summary>
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true,
           HelpMessage = "The name of one or more processes to stop. Wildcards are permitted."
)]
[Alias("ProcessName")]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;
```

Windows PowerShell ランタイムでは、 [alias 属性を](/dotnet/api/System.Management.Automation.AliasAttribute)使用するだけでなく、別名が指定されていない場合でも、部分的な名前の一致が実行されます。 たとえば、コマンドレットに `FileName` パラメーターがあり、それが `F`で始まる唯一のパラメーターである場合、ユーザーは `Filename`、`Filenam`、`File`、`Fi`、`F` を入力しても、エントリを `FileName` パラメーターとして認識できます。

## <a name="creating-help-for-parameters"></a>パラメーターのヘルプの作成

Windows PowerShell では、コマンドレットパラメーターのヘルプを作成できます。 この操作は、システムの変更やユーザーフィードバックに使用される任意のパラメーターに対して行います。 ヘルプをサポートする各パラメーターに対して、`HelpMessage` attribute キーワード[を、この](/dotnet/api/System.Management.Automation.ParameterAttribute)属性宣言で設定できます。 このキーワードは、パラメーターを使用する際の参考としてユーザーに表示するテキストを定義します。 また、`HelpMessageBaseName` キーワードを設定して、メッセージに使用するリソースの基本名を指定することもできます。 このキーワードを設定する場合は、`HelpMessageResourceId` キーワードを設定してリソース識別子を指定する必要もあります。

この Stop Proc コマンドレットの次のコードは、`Name` パラメーターの `HelpMessage` attribute キーワードを定義します。

```csharp
/// <summary>
/// Specify the mandatory Name parameter used to identify the
/// processes to be stopped.
/// </summary>
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true,
           HelpMessage = "The name of one or more processes to stop. Wildcards are permitted."
)]
```

## <a name="overriding-an-input-processing-method"></a>入力処理メソッドのオーバーライド

コマンドレットでは、入力処理メソッドをオーバーライドする必要があります。これは、ほとんどの場合、このコマンド[レット](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)を使用します。 システムを変更する場合、コマンドレットは、変更を加える前にユーザーがフィードバックを提供できるようにするために、コマンドレットに[よってメソッド](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)を呼び出す必要があり[ます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) これらの方法の詳細については、「[システムを変更するコマンドレットを作成](./creating-a-cmdlet-that-modifies-the-system.md)する」を参照してください。

## <a name="supporting-wildcard-expansion"></a>ワイルドカード拡張のサポート

複数のオブジェクトを選択できるようにするには、コマンドレットで[Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern)クラスと[Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions)クラスを使用して、パラメーター入力のワイルドカード拡張サポートを提供します。 ワイルドカードパターンの例としては、lsa *、\*.txt、および [a-c]\*があります。 パターンに文字どおりに使用する必要がある文字が含まれている場合は、二重引用符文字 (') をエスケープ文字として使用します。

ファイル名とパス名のワイルドカードによる展開は、複数のオブジェクトを選択する必要がある場合に、コマンドレットでパス入力のサポートを許可する一般的なシナリオの例です。 通常、ファイルシステムには、現在のフォルダーに存在するすべてのファイルが表示されます。

カスタマイズされたワイルドカードパターン一致の実装が必要になることはほとんどありません。 この場合、コマンドレットは、完全な POSIX 1003.2、3.13 のワイルドカードの展開、または次の簡略化されたサブセットのいずれかをサポートする必要があります。

- **疑問符 (?)。** 指定した位置にある任意の文字と一致します。

- **アスタリスク (\*)。** 指定した位置から始まる0個以上の文字と一致します。

- **角かっこ ([) を開きます。** 文字または文字の範囲を含めることができるパターン角かっこ式を導入します。 範囲が必要な場合は、範囲を示すためにハイフン (-) が使用されます。

- **閉じかっこ (])。** パターン角かっこ表現を終了します。

- **バッククォートエスケープ文字 (')。** 次の文字を文字どおりに取得する必要があることを示します。 プログラムによって指定するのではなく、コマンドラインからバッククォート文字を指定する場合は、バッククォートのエスケープ文字を2回指定する必要があることに注意してください。

> [!NOTE]
> ワイルドカードパターンの詳細については、「[コマンドレットパラメーターでのワイルドカードのサポート](./supporting-wildcard-characters-in-cmdlet-parameters.md)」を参照してください。

次のコードは、ワイルドカードオプションを設定し、このコマンドレットの `Name` パラメーターの解決に使用するワイルドカードパターンを定義する方法を示しています。

```csharp
WildcardOptions options = WildcardOptions.IgnoreCase |
                          WildcardOptions.Compiled;
WildcardPattern wildcard = new WildcardPattern(name,options);
```

次のコードは、プロセス名が定義されたワイルドカードパターンに一致するかどうかをテストする方法を示しています。 この場合、プロセス名がパターンと一致しない場合、コマンドレットは次のプロセス名を取得し続けます。

```csharp
if (!wildcard.IsMatch(processName))
{
  continue;
}
```

## <a name="code-sample"></a>コードサンプル

完全なC#サンプルコードについては、「 [StopProcessSample03 sample](./stopprocesssample03-sample.md)」を参照してください。

## <a name="define-object-types-and-formatting"></a>オブジェクトの種類と書式を定義する

Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。 そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。 新しい型を定義する、または既存の型を拡張する方法の詳細については、「[オブジェクトの型と書式設定の拡張](/previous-versions//ms714665(v=vs.85))」を参照してください。

## <a name="building-the-cmdlet"></a>コマンドレットのビルド

コマンドレットを実装した後は、Windows powershell スナップインを使用して Windows PowerShell に登録する必要があります。 コマンドレットの登録の詳細については、「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。

## <a name="testing-the-cmdlet"></a>コマンドレットのテスト

コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行することでテストできます。 Stop-Proc コマンドレットのサンプルをテストしてみましょう。 コマンドラインからコマンドレットを使用する方法の詳細については、「 [Windows PowerShell を使用したはじめに](/powershell/scripting/getting-started/getting-started-with-windows-powershell)」を参照してください。

- Windows PowerShell を起動し、`Name` パラメーターの ProcessName エイリアスを使用してプロセスを停止するには、Stop Proc を使用します。

    ```powershell
    PS> stop-proc -ProcessName notepad
    ```

次の出力が表示されます。

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (3496)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- コマンドラインで次のエントリを作成します。 Name パラメーターは必須であるため、入力を求められます。 「!?」と入力します。 パラメーターに関連付けられたヘルプテキストを表示します。

    ```powershell
    PS> stop-proc
    ```

次の出力が表示されます。

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    (Type !? for Help.)
    Name[0]: !?
    The name of one or more processes to stop. Wildcards are permitted.
    Name[0]: notepad
    ```

- ここで、次のエントリを作成して、ワイルドカードパターン "* note\*" に一致するすべてのプロセスを停止します。 パターンに一致する各プロセスを停止する前に、メッセージが表示されます。

    ```powershell
    PS> stop-proc -Name *note*
    ```

次の出力が表示されます。

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (1112)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

次の出力が表示されます。

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTEM (3712)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

次の出力が表示されます。

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTE (3592)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a>関連項目

[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)

[Windows PowerShell コマンドレットを作成する方法](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

[オブジェクトの種類と書式設定の拡張](/previous-versions//ms714665(v=vs.85))

[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))

[コマンドレットパラメーターでのワイルドカードのサポート](./supporting-wildcard-characters-in-cmdlet-parameters.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
