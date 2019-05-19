---
title: ワイルドカードの展開のエイリアスを追加し、コマンドレットのパラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 931ccace-c565-4a98-8dcc-df00f86394b1
caps.latest.revision: 8
ms.openlocfilehash: 946b71e4480a47ac6ccd6930be445d7efb4fb62d
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65854906"
---
# <a name="adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters"></a>エイリアス、ワイルドカード展開、ヘルプをコマンドレット パラメーターに追加する

エイリアス、ワイルドカードの展開を追加する方法について説明およびヘルプ メッセージの停止 Proc コマンドレットのパラメーター (で説明されている[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md))。

この停止 Proc コマンドレットは Get-proc コマンドレットを使用して取得するプロセスを停止しようとしました。 (で説明されている[最初のコマンドレットを、作成](./creating-a-cmdlet-without-parameters.md))。

## <a name="defining-the-cmdlet"></a>コマンドレットを定義します。

コマンドレットの作成の最初の手順は常に、コマンドレットの名前を付けると、コマンドレットを実装する .NET クラスを宣言します。 システムを変更するコマンドレットを記述するため、それに応じて名前にする必要があります。 このコマンドレットは、システム プロセスを停止、ために、"Stop"で定義されている、動詞を使用、 [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)クラスの名詞をプロセスを示すために"Proc"とします。 承認されたコマンドレット動詞の詳細については、次を参照してください。[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)します。

次のコードは、このコマンドレットで停止 Proc クラス定義です。

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a>システムの変更のパラメーターを定義します。

コマンドレットは、そのサポート システムの変更やユーザー フィードバック パラメーターを定義する必要があります。 コマンドレットを定義する必要があります、`Name`パラメーターまたはそれと同等、コマンドレットは、システムに何らかの識別子を変更できるようにします。 また、コマンドレットを定義する必要があります、`Force`と`PassThru`パラメーター。 これらのパラメーターの詳細については、次を参照してください。[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)します。

## <a name="defining-a-parameter-alias"></a>パラメーター エイリアスを定義します。

パラメーター エイリアスには代替名またはコマンドレット パラメーターの適切に定義された 1 文字または 2 文字短い名前を使用できます。 どちらの場合も、エイリアスを使用する目的は、コマンドラインからのユーザー入力を簡略化します。 Windows PowerShell からのパラメーターのエイリアスをサポートしている、 [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute)属性には、宣言の構文 [Alias()] を使用します。

次のコードにエイリアスを追加する方法を示しています、`Name`パラメーター。

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

使用するだけでなく、 [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute)属性、Windows PowerShell ランタイムによって実行される部分的な名前が一致する別名が指定されていない場合でもです。 たとえば、次のコマンドレットがある、`FileName`パラメーターとは、唯一のパラメーターで始まる`F`、ユーザーが入力`Filename`、 `Filenam`、 `File`、 `Fi`、または`F`も認識し、エントリとして、`FileName`パラメーター。

## <a name="creating-help-for-parameters"></a>パラメーターのヘルプの作成

Windows PowerShell コマンドレットのパラメーターのヘルプを作成することができます。 このシステムの変更とユーザーのフィードバックに使用される任意のパラメーターに対して行います。 ヘルプをサポートするには、各パラメーターの設定することができます、`HelpMessage`属性内のキーワード、 [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)属性宣言。 このキーワードは、パラメーターを使用してで支援をユーザーに表示するテキストを定義します。 設定することも、`HelpMessageBaseName`メッセージで使用するリソースのベース名を識別するためにキーワード。 設定する必要があるこのキーワードを設定した場合、`HelpMessageResourceId`リソース識別子を指定するキーワード。

この停止 Proc コマンドレットから次のコードを定義、`HelpMessage`属性のキーワード、`Name`パラメーター。

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

## <a name="overriding-an-input-processing-method"></a>入力処理メソッドをオーバーライドします。

コマンドレットは、入力処理メソッドをオーバーライドする必要があります、これは最も頻繁になります[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)します。 コマンドレットを呼び出す必要があります、システムを変更するときに、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)ユーザーを許可する方法変更が行われる前に、フィードバックを提供します。 これらのメソッドの詳細については、次を参照してください。[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)します。

## <a name="supporting-wildcard-expansion"></a>ワイルドカードの展開をサポートしています。

複数のオブジェクトの選択を許可する、コマンドレットを使用できます、 [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern)と[System.Management.Automation.Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions)クラスを提供するには入力パラメーターのワイルドカードの拡張サポート。 ワイルドカードのパターンの例は、lsa * \*.txt、および [c]、\*します。 パターンには、そのまま使用する文字が含まれている場合は、エスケープ文字として逆引用符 (') を使用します。

ファイルとパス名のワイルドカードの展開では、コマンドレットは、複数のオブジェクトの選択が必要な場合は、パスの入力のサポートを許可する必要のある一般的なシナリオの例を示します。 一般的なケースが、ユーザーが、現在のフォルダー内に存在するすべてのファイルを表示するが、ファイル システムです。

まれに、カスタマイズされたワイルドカードのパターン一致の実装を必要があります。 この場合、コマンドレットでは、いずれかの完全な POSIX 1003.2、ワイルドカードの展開の 3.13 仕様または、次の簡略化されたサブセットをサポートする必要があります。

- **疑問符 (?)。** 指定した位置に任意の文字と一致します。

- **アスタリスク (\*)。** 指定した場所から始まる 0 個以上の文字と一致します。

- **角かっこ ([) を開きます。** 文字または文字の範囲に格納できるパターンの角かっこ表現が導入されています。 範囲が必要な場合は、ハイフン (-) が、範囲を示すために使用されます。

- **終了の角かっこ (]) です。** パターンの角かっこ表現を終了します。

- **バックアップ-引用符のエスケープ文字 (')。** 次の文字がそのまま使用することを示します。 (プログラムで指定) ではなくコマンドラインから逆引用符を指定するときに、背面引用符のエスケープ文字が指定することは 2 回あります。

> [!NOTE]
> ワイルドカードのパターンの詳細については、次を参照してください。[コマンドレットのパラメーターにワイルドカードをサポートしている](./supporting-wildcard-characters-in-cmdlet-parameters.md)します。

次のコードは、ワイルドカードのオプションを設定し、解決するために使用するワイルドカード パターンを定義する方法を示しています、`Name`このコマンドレットのパラメーター。

```csharp
WildcardOptions options = WildcardOptions.IgnoreCase |
                          WildcardOptions.Compiled;
WildcardPattern wildcard = new WildcardPattern(name,options);
```

次のコードでは、プロセス名が定義されているワイルドカードのパターンと一致するかどうかをテストする方法を示します。 、ここでは、プロセス名にパターンが一致しない場合、コマンドレットに続くこと、次のプロセス名を取得することを確認します。

```csharp
if (!wildcard.IsMatch(processName))
{
  continue;
}
```

## <a name="code-sample"></a>コード サンプル

完全なC#サンプル コードは、「 [StopProcessSample03 サンプル](./stopprocesssample03-sample.md)します。

## <a name="define-object-types-and-formatting"></a>オブジェクトの種類と書式設定を定義します。

Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。 その結果、コマンドレットは、独自の型を定義する必要がありますか、コマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。 新しい型を定義するか、既存の型の拡張の詳細については、次を参照してください。[を拡張するオブジェクトの種類と書式](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)します。

## <a name="building-the-cmdlet"></a>コマンドレットを構築

コマンドレットを実装するには、後にする必要があります登録する必要が Windows PowerShell を使用した Windows PowerShell スナップインを使用します。 コマンドレットの登録の詳細については、次を参照してください。[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。

## <a name="testing-the-cmdlet"></a>テスト コマンドレット

コマンドレットは、Windows PowerShell を使用した登録しているときに、コマンドラインで実行してテストできます。 サンプルの停止 Proc コマンドレットをテストしてみましょう。 詳細については、コマンドラインからコマンドレットを使用して、次を参照してください。、 [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)します。

- Windows PowerShell を起動し、ProcessName エイリアスを使用してプロセスを停止する停止プロシージャを使用して、`Name`パラメーター。

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

- コマンドラインでは、次のエントリを作成します。 Name パラメーターは必須であるために、そのように求められます。 入力"!?" パラメーターに関連付けられているヘルプ テキストが表示されます。

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

- 今すぐワイルドカード パターンに一致するすべてのプロセスを停止する次のエントリを作成する"* 注\*"。 各パターンに一致するプロセスを停止する前に求められます。

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

## <a name="see-also"></a>参照

[システムを変更するコマンドレットを作成します。](./creating-a-cmdlet-that-modifies-the-system.md)

[Windows PowerShell コマンドレットを作成する方法](https://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[オブジェクトの種類を拡張して、書式設定](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[コマンドレットのパラメーターでのワイルドカードのサポート](./supporting-wildcard-characters-in-cmdlet-parameters.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
