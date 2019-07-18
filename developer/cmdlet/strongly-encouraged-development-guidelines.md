---
title: 開発のガイドラインを強く推奨 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d68a8f3-fba0-44c5-97b9-9fc191d269a5
caps.latest.revision: 13
ms.openlocfilehash: 0906d0d37c66b8c1538a0b2e9e0f1ff2fba12ac0
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067367"
---
# <a name="strongly-encouraged-development-guidelines"></a>強くお勧めする開発ガイドライン

このセクションには、コマンドレットを記述するときに従う必要のあるガイドラインについて説明します。 コマンドレットとコマンドレット コードの記述に関するガイドラインを設計するためのガイドラインに区切られます。 次のガイドラインは、すべてのシナリオは適用されないことがあります。 ただしは適用し、次のガイドラインに従わない場合、コマンドレットを使用するときに、ユーザーはパフォーマンスを低下させるがあります。

## <a name="design-guidelines"></a>デザイン ガイドライン

- [特定の名詞を使用して、コマンドレット名 (SD01)](./strongly-encouraged-development-guidelines.md#use-a-specific-noun-for-a-cmdlet-name-sd01)

- [パスカル ケースを使用して、コマンドレット名 (SD02)](./strongly-encouraged-development-guidelines.md#use-pascal-case-for-cmdlet-names-sd02)

- [パラメーターのデザインのガイドライン (SD03)](./strongly-encouraged-development-guidelines.md#parameter-design-guidelines-sd03)

- [(SD04) のユーザーにフィードバックを提供します。](./strongly-encouraged-development-guidelines.md#provide-feedback-to-the-user-sd04)

- [コマンドレットのヘルプ ファイル (SD05) の作成します。](./strongly-encouraged-development-guidelines.md#create-a-cmdlet-help-file-sd05)

## <a name="code-guidelines"></a>コードのガイドライン

- [パラメーター (SC01)](./strongly-encouraged-development-guidelines.md#coding-parameters-sc01)

- [適切に定義されたパイプラインの入力 (SC02) のサポートします。](./strongly-encouraged-development-guidelines.md#support-well-defined-pipeline-input-sc02)

- [パイプライン (SC03) に 1 つのレコードを書き込む](./strongly-encouraged-development-guidelines.md#write-single-records-to-the-pipeline-sc03)

- [コマンドレットを大文字と小文字が区別 (SC04)](./strongly-encouraged-development-guidelines.md#make-cmdlets-case-insensitive-and-case-preserving-sc04)

## <a name="design-guidelines"></a>デザイン ガイドライン

間、コマンドレットとその他のコマンドレットを使用して一貫性のあるユーザー エクスペリエンスを実現するためのコマンドレットを設計するときに、次のガイドラインに従ってください。 自分の状況に適用されるデザインのガイドラインを検索するときに必ずのようなガイドラインについては、コードのガイドラインを確認してください。

### <a name="use-a-specific-noun-for-a-cmdlet-name-sd01"></a>特定の名詞を使用して、コマンドレット名 (SD01)

名詞コマンドレットの名前付けで使用される、ユーザーは、コマンドレットを検出できるように、非常に限定する必要があります。 製品名の短縮バージョンでは、"server"などの一般的な名詞をプレフィックスします。 たとえば、名詞は、Microsoft SQL Server のインスタンスを実行しているサーバーが参照されている場合は、"SQLServer"などの名詞を使用します。 承認された動詞の簡単なリストと特定の名詞の組み合わせをすばやく検出し、コマンドレット名の間で重複を回避しながら機能が予想されるユーザーを有効にします。

ユーザー エクスペリエンスを強化するために、コマンドレット名の選択した名詞は単数形にあります。 たとえば、名前を使用して`Get-Process`の代わりに**Get プロセス**します。 コマンドレットは、1 つ以上の項目に対して操作を実行する可能性が高い場合でも、すべてのコマンドレット名にはこの規則に従うことをお勧めします。

### <a name="use-pascal-case-for-cmdlet-names-sd02"></a>パスカル ケースを使用して、コマンドレット名 (SD02)

パラメーター名をパスカル ケースを使用します。 つまり、動詞と名詞で使用されるすべての用語の最初の文字を大文字にします。 たとえば、"`Clear-ItemProperty`"。

### <a name="parameter-design-guidelines-sd03"></a>パラメーターのデザインのガイドライン (SD03)

コマンドレットがパラメーターで、操作する必要があります、データを受信する必要があるし、操作の特性を決定するために使用される情報を示すパラメーターです。 たとえば、コマンドレットがあります、 `Name` 、パイプラインと、コマンドレットからデータを受信するパラメーターがあります、`Force`その操作を実行するコマンドレットを強制できることを指定するパラメーター。 コマンドレットを定義するパラメーターの数に制限はありません。

#### <a name="use-standard-parameter-names"></a>標準的なパラメーター名を使用します。

コマンドレットは、標準的なパラメーター名を使用して、ユーザーは、特定のパラメーターの意味簡単に確認できるようにする必要があります。 特定の名前が必要な場合、標準的なパラメーター名を使用およびをエイリアスとしてより特定の名前を指定します。 たとえば、`Get-Service`コマンドレットは汎用的な名前のパラメーター (`Name`) と具体的なエイリアス (`ServiceName`)。 パラメーターを指定する両方の用語を使用できます。

パラメーター名とそのデータ型の詳細については、次を参照してください。[コマンドレットのパラメーター名と機能のガイドライン](./standard-cmdlet-parameter-names-and-types.md)します。

#### <a name="use-singular-parameter-names"></a>単一のパラメーター名を使用します。

パラメーターの値は、1 つの要素の複数形の名前を使用しないでください。 これを配列を受け取るパラメーターが含まれていますか、一覧、ユーザーを提供する配列またはリスト要素が 1 つだけなので。

複数形のパラメーター名は、パラメーターの値が、複数要素の値では常に場合にのみ使用する必要があります。 このような場合、コマンドレットは複数の要素を指定すると、そのコマンドレットは、複数の要素が指定されていない場合に、ユーザーの警告を表示する必要がありますを確認してください。

#### <a name="use-pascal-case-for-parameter-names"></a>パスカル ケースを使用して、パラメーター名

パラメーター名をパスカル ケースを使用します。 つまり、名前の最初の文字を含む、パラメーター名の各単語の最初の文字を大文字にします。 たとえば、パラメーター名`ErrorAction`正しい大文字と小文字を使用します。 次のパラメーター名は、大文字と小文字を使用します。

- `errorAction`

- `erroraction`

#### <a name="parameters-that-take-a-list-of-options"></a>オプションの一覧を取得するパラメーター

一連のオプションから選択できる値を持つパラメーターを作成する 2 つの方法はあります。

- 列挙型を定義する (または既存の列挙型を使用して) 有効な値を指定します。 次に、列挙型を使用して、その型のパラメーターを作成します。

- 追加、 **ValidateSet**パラメーター宣言に属性します。 この属性の詳細については、次を参照してください。 [ValidateSet 属性宣言](./validateset-attribute-declaration.md)します。

#### <a name="use-standard-types-for-parameters"></a>標準の型パラメーターを使用します。

他のコマンドレットで一貫性を確保するには、するがずっと可能なパラメーターの基本データ型を使用します。 別のパラメーターを使用する種類の詳細については、次を参照してください。[標準コマンドレットのパラメーター名と型](./standard-cmdlet-parameter-names-and-types.md)します。 このトピックでは、名前と、「アクティビティのパラメーター」などの標準パラメーターのグループの .NET Framework 型を記述するいくつかのトピックへのリンクを提供します。

#### <a name="use-strongly-typed-net-framework-types"></a>厳密に型指定された .NET Framework 型を使用します。

パラメーターより優れたパラメーターの検証を提供する .NET Framework の型として定義する必要があります。 たとえば、値のセットから 1 つの値に制限されているパラメーターは、列挙型として定義する必要があります。 Uniform Resource Identifier (URI) の値をサポートするために、パラメーターとしての定義、 [System.Uri](/dotnet/api/System.Uri)型。 以外のすべての自由形式テキストのプロパティの基本的な文字列パラメーターを回避します。

#### <a name="use-consistent-parameter-types"></a>一貫性のあるパラメーターの型を使用して、

複数のコマンドレットによって、同じパラメーターを使用する場合は、常に同じパラメーターの型を使用します。  たとえば場合、`Process`パラメーターは、 [System.Int16](/dotnet/api/System.Int16)コマンドレットの 1 つの入力を加えないでください、`Process`別のコマンドレットのパラメーターを[System.Uint16](/dotnet/api/System.UInt16)型。

#### <a name="parameters-that-take-true-and-false"></a>パラメーターを受け取る True と False

場合のみ、パラメーターを受け取り`true`と`false`、パラメーターを型として定義[System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)します。 スイッチ パラメーターとして扱われます`true`コマンドで指定されている場合。 Windows PowerShell がするパラメーターの値を考慮する場合は、コマンドでは、パラメーターが含まれていない、`false`します。 ブール型のパラメーターを定義してください。

パラメーターは、3 つの値を区別する必要がある場合: $true、$false、および「未指定」は、null 許容型のパラメーターを定義し、\<bool >。  サードの必要性、「未指定」値には通常、コマンドレットがオブジェクトのブール型プロパティを変更とが発生します。 ここでは「未指定」ことを意味しないプロパティの現在の値を変更します。

#### <a name="support-arrays-for-parameters"></a>パラメーターの配列をサポートします。

多くの場合、ユーザーは、複数の引数に対して同じ操作を実行する必要があります。 コマンドレットは、これらのユーザーのユーザーは、Windows PowerShell 変数としてパラメーターに引数を渡すことができますので、入力パラメーターとして配列を受け入れる必要があります。 たとえば、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットは、取得するプロセスの名前を識別する文字列の配列を使用します。

#### <a name="support-the-passthru-parameter"></a>PassThru パラメーターをサポートします。

既定では、多くのコマンドレットを変更する、システムなど、 [Stop-process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process)コマンドレットがオブジェクトの"sinks"として機能し、結果は返されません。 これらのコマンドレットを実装する必要があります、`PassThru`させるオブジェクトを取得するコマンドレットのパラメーター。 ときに、`PassThru`パラメーターを指定すると、コマンドレットの呼び出しを使用してオブジェクトを返します、 [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッド。 たとえば、次のコマンドは、Calc プロセスが停止し、パイプラインに結果のプロセスを渡します。

```powershell
Stop-Process calc -passthru
```

ほとんどの場合、追加、セット、および新規のコマンドレットをサポートする必要があります、`PassThru`パラメーター。

#### <a name="support-parameter-sets"></a>パラメーター セットをサポートします。

コマンドレットは、1 つの目的を実現するものです。 ただし、操作または操作の対象を記述するは、複数の方法は頻繁に。 たとえばの名前、識別子またはプロセス オブジェクト、プロセスが特定されます。 コマンドレットは、ターゲットの適切な表現は、すべてをサポートする必要があります。 通常、コマンドレットは、(パラメーターのセットと呼ばれます) で同時に動作するパラメーターのセットを指定することによってこの要件を満たします。 1 つのパラメーターは、パラメーター セットの任意の数に属することができます。 パラメーター セットの詳細については、次を参照してください。[コマンドレット パラメーター設定](./cmdlet-parameter-sets.md)します。

パラメーター セットを指定する場合は、ValueFromPipeline セットの 1 つだけのパラメーターを設定します。 宣言する方法について、**パラメーター**属性は、「 [ParameterAttribute 宣言](./parameter-attribute-declaration.md)します。

既定のパラメーター セットが定義されているパラメーターのセットを使用している場合、**コマンドレット**属性。 既定のパラメーター セットは、対話型の Windows PowerShell セッションで使用される最も可能性の高いパラメーターを含める必要があります。 宣言する方法について、**コマンドレット**属性は、「 [CmdletAttribute 宣言](./cmdlet-attribute-declaration.md)します。

### <a name="provide-feedback-to-the-user-sd04"></a>(SD04) のユーザーにフィードバックを提供します。

このセクションのガイドラインを使用して、ユーザーにフィードバックを提供します。 このフィードバックによりより管理の決定を行うユーザーをシステムで発生している内容に注意してください。

Windows PowerShell ランタイムにより、ユーザーへの各呼び出しからの出力を処理する方法を指定する、`Write`ユーザー設定変数を設定することによって。 ユーザーは、情報と、システムがさらにアクションを実行する前に、ユーザーを照会する必要があるかどうかを決定する変数を表示するかどうかを決定する変数を含む、いくつかのユーザー設定変数を設定できます。

#### <a name="support-the-writewarning-writeverbose-and-writedebug-methods"></a>WriteWarning、WriteVerbose、WriteDebug メソッドをサポートします。

コマンドレットを呼び出す必要があります、 [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning)メソッドが、意図しない結果があります。 操作を実行しようとしています。 たとえば、コマンドレットは、コマンドレットが読み取り専用ファイルを上書きする場合は、このメソッドを呼び出す必要があります。

コマンドレットを呼び出す必要があります、 [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)メソッド、ユーザーは、コマンドレットの実行内容についていくつかの詳細を必要とする場合。 たとえば、コマンドレットは、コマンドレットの作成者と、コマンドレットの実行内容の詳細が必要となるシナリオがあることを考えている場合、この情報を呼び出す必要があります。

コマンドレットを呼び出す必要があります、 [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)メソッドと、developer、または製品のサポート エンジニアがコマンドレットの操作が破損している内容を理解する必要があります。 必要でないコマンドレットを呼び出す、 [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)メソッドを呼び出すのと同じコードで、 [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)メソッド`Debug`パラメーター情報の両方のセットを表示します。

#### <a name="support-writeprogress-for-operations-that-take-a-long-time"></a>WriteProgress を長い時間がかかる操作のサポートします。

コマンドレットの操作を受け取ると完了に長時間をバック グラウンドで実行できませんに定期的な呼び出しを使用したレポートの進行状況をサポートする必要があります、 [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress)メソッド。

#### <a name="use-the-host-interfaces"></a>ホスト インターフェイスを使用して、

場合によっては、コマンドレットをする必要がありますと直接通信の代わりにユーザーを使用して、さまざまな書き込みまたはメソッドでサポートされている必要があります、 [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)クラス。 この場合、コマンドレットがから派生する必要があります、 [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)クラスを使用して、 [System.Management.Automation.PSCmdlet.Host*](/dotnet/api/System.Management.Automation.PSCmdlet.Host)プロパティ。 このプロパティは、通信の種類、PromptForChoice、プロンプト、および WriteLine/ReadLine 型などのさまざまなレベルをサポートします。 一番の特定のレベルもあり、個々 のキーを読み書きするバッファーを処理する方法。

コマンドレットは具体的にはグラフィカル ユーザー インターフェイス (GUI) を生成するように設計、しない限りを使用して、ホストを回避する必要がありますされませんが、 [System.Management.Automation.PSCmdlet.Host*](/dotnet/api/System.Management.Automation.PSCmdlet.Host)プロパティ。 GUI を生成するように設計されたコマンドレットの例は、 [Out-gridview](/powershell/module/Microsoft.PowerShell.Utility/Out-GridView)コマンドレット。

> [!NOTE]
> コマンドレットを使用する必要があります、 [System.Console](/dotnet/api/System.Console) API。

### <a name="create-a-cmdlet-help-file-sd05"></a>コマンドレットのヘルプ ファイル (SD05) の作成します。

各コマンドレット アセンブリのコマンドレットに関する情報を含む Help.xml ファイルを作成します。 この情報には、コマンドレット、コマンドレットのパラメーターの説明については、コマンドレットの使用、その他の例の説明が含まれています。

## <a name="code-guidelines"></a>コードのガイドライン

間、コマンドレットとその他のコマンドレットを使用して一貫性のあるユーザー エクスペリエンスを実現するためのコマンドレットをコーディングする際、次のガイドラインに従ってください。 自分の状況に適用されるコードのガイドラインを検索するときに必ずのようなガイドラインについては、デザイン ガイドラインを確認してください。

### <a name="coding-parameters-sc01"></a>パラメーター (SC01)

コマンドレット クラスのパブリック プロパティを宣言することで、パラメーターを定義、**パラメーター**属性。 パラメーターは、コマンドレットの派生の .NET Framework クラスの静的メンバーではありません。 宣言する方法について、**パラメーター**属性は、「[パラメーター属性宣言](./parameter-attribute-declaration.md)します。

#### <a name="support-windows-powershell-paths"></a>Windows PowerShell パスをサポートします。

Windows PowerShell パスは、名前空間へのアクセスを正規化するための機構です。 コマンドレットでパラメーターに、Windows PowerShell パスを割り当てた場合、ユーザーは、"drive"、特定のパスへのショートカットとして機能するカスタムを定義できます。 ユーザーがこのようなドライブを指定した場合、レジストリ内のデータなどの格納されたデータが一貫した方法で使用できます。

型のパラメーターを定義する必要があります、コマンドレットは、ファイルまたはデータ ソースを指定するユーザーを許可している場合[System.String](/dotnet/api/System.String)します。 1 つ以上のドライブがサポートされている場合、型が配列でなければなりません。 パラメーターの名前にする必要があります`Path`、エイリアスを持つ`PSPath`します。 さらに、`Path`パラメーターは、ワイルドカード文字をサポートする必要があります。 場合のワイルドカード文字は必要ありませんのサポート、定義、`LiteralPath`パラメーター。

コマンドレットは、読み取りまたは書き込みをデータにファイルがある場合は、コマンドレットは、Windows PowerShell パスの入力を受け入れる必要があります、コマンドレットを使用する必要があります、 [System.Management.Automation.Sessionstate.Path](/dotnet/api/System.Management.Automation.SessionState.Path) Windows を変換するプロパティPowerShell パスにファイル システムが認識するパス。 特定のメカニズムには、次のメソッドが含まれます。

- [System.Management.Automation.PSCmdlet.GetResolvedProviderPathFromPSPath](/dotnet/api/System.Management.Automation.PSCmdlet.GetResolvedProviderPathFromPSPath)

- [System.Management.Automation.PSCmdlet.GetUnresolvedProviderPathFromPSPath](/dotnet/api/System.Management.Automation.PSCmdlet.GetUnresolvedProviderPathFromPSPath)

- [System.Management.Automation.PathIntrinsics.GetResolvedProviderPathFromPSPath](/dotnet/api/System.Management.Automation.PathIntrinsics.GetResolvedProviderPathFromPSPath)

- [System.Management.Automation.PathIntrinsics.GetUnresolvedProviderPathFromPSPath](/dotnet/api/System.Management.Automation.PathIntrinsics.GetUnresolvedProviderPathFromPSPath)

データを読み取りまたは書き込みが、コマンドレットは一連のファイルをコマンドレットではなく文字列プロバイダー コンテンツ情報を使用する必要があります (`Content`メンバー) 読み取りし、書き込みにします。 この情報を得た、 [System.Management.Automation.Provider.CmdletProvider.InvokeProvider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.InvokeProvider)プロパティ。 これらのメカニズムは、データの書き込みと読み取りに参加する他のデータ ストアを許可します。

#### <a name="support-wildcard-characters"></a>ワイルドカード文字をサポートします。

コマンドレットでは、可能であればワイルドカード文字をサポートする必要があります。 ワイルドカード文字のサポートは、(特にパラメーターは、オブジェクトのセットから 1 つのオブジェクトを識別する文字列を受け取ります) 場合、コマンドレットの多くの場所で発生します。 サンプルではたとえば、**停止 Proc**からコマンドレット、 [StopProc チュートリアル](./stopproc-tutorial.md)定義、`Name`プロセス名を表す文字列を処理するパラメーター。 このパラメーターは、ワイルドカード文字をサポートするため、ユーザーが停止するプロセスを簡単に指定できます。

ワイルドカードのサポートの文字は使用可能なコマンドレットの操作には、通常は配列が生成されます。 場合によっては、ユーザーは一度に 1 つの項目のみを使用する場合がありますので、配列をサポートするために意味は行いません。 たとえば、 [Set-location](/powershell/module/Microsoft.PowerShell.Management/Set-Location)コマンドレットは、ユーザーが 1 つの場所のみを設定するために、配列をサポートする必要はありません。 このインスタンスでは、コマンドレットには、ワイルドカード文字を引き続きサポートされますが解像度を強制的に 1 つの場所にします。

ワイルドカード文字のパターンの詳細については、次を参照してください。[コマンドレットのパラメーターにワイルドカード文字をサポートしている](./supporting-wildcard-characters-in-cmdlet-parameters.md)します。

#### <a name="defining-objects"></a>オブジェクトを定義します。

このセクションには、コマンドレットと、既存のオブジェクトを拡張するためのオブジェクトを定義するためのガイドラインが含まれています。

##### <a name="define-standard-members"></a>標準のメンバーを定義します。

カスタムの Types.ps1xml ファイル (Windows PowerShell の Types.ps1xml ファイルのテンプレートとして使用) でオブジェクトの種類を拡張する標準のメンバーを定義します。 標準のメンバーは、PSStandardMembers という名前のノードによって定義されます。 これらの定義は、他のコマンドレットと一貫した方法で、オブジェクトを使用する Windows PowerShell ランタイムを許可します。

##### <a name="define-objectmembers-to-be-used-as-parameters"></a>パラメーターとして使用する ObjectMembers を定義します。

コマンドレットのオブジェクトを設計する場合は、そのメンバーがそれを使用するコマンドレットのパラメーターに直接マップするを確認します。 このマッピングにより、パイプラインに簡単に送信して、別に 1 つのコマンドレットから渡されるオブジェクトです。

コマンドレットによって返される既存の .NET Framework オブジェクトに、スクリプトの開発者やユーザーに必要ないくつかの重要なまたは便利なメンバーと頻繁がありません。 これらの欠落しているメンバーを表示して、オブジェクトをパイプラインに正しく渡すことができるように、適切なメンバー名を作成するために特に重要ですできます。 これらの必要なメンバーを文書化するカスタムの Types.ps1xml ファイルを作成します。 このファイルを作成するときに、次の名前付け規則お勧めします。 *< Your_Product_Name >* します。Types.ps1xml します。

たとえば、追加する、`Mode`スクリプト プロパティを[System.IO.FileInfo](/dotnet/api/System.IO.FileInfo)ファイルの属性をより明確に表示する型。 さらに、追加でした、`Count`エイリアス プロパティを[System.Array](/dotnet/api/System.Array)一貫性のあるが、プロパティ名の使用を許可する型 (の代わりに`Length`)。

##### <a name="implement-the-icomparable-interface"></a>IComparable インターフェイスを実装します。

実装を[System.IComparable](/dotnet/api/System.IComparable)出力オブジェクトのすべてのインターフェイス。 これにより、出力オブジェクトを簡単にさまざまな並べ替えと分析のコマンドレットにパイプ処理できます。

##### <a name="update-display-information"></a>表示情報を更新します。

オブジェクトの表示が期待どおりの結果を提供していない場合は、カスタムを作成 *\<YourProductName >* します。そのオブジェクトの Format.ps1xml ファイルです。

### <a name="support-well-defined-pipeline-input-sc02"></a>適切に定義されたパイプラインの入力 (SC02) のサポートします。

#### <a name="implement-for-the-middle-of-a-pipeline"></a>パイプラインの中間の実装

パイプラインの中央から呼び出されますと仮定すると、コマンドレットを実装する (つまり、他のコマンドレットは、入力を生成またはその出力を使用)。 たとえばと思うかもしれませんが、`Get-Process`コマンドレットは、データが生成されるため、パイプラインの最初のコマンドレットとしてのみ使用されます。 ただし、このコマンドレットは、パイプラインの中間に設計されている、ためこのコマンドレットを使用できます上記のコマンドレットまたはデータを取得するプロセスを指定するには、次のようにパイプラインします。

#### <a name="support-input-from-the-pipeline"></a>パイプラインからの入力をサポート

各パラメーターでは、コマンドレットのセット、パイプラインから入力をサポートしている少なくとも 1 つのパラメーターが含まれます。 パイプラインの入力のサポートは、データまたは結果をコマンドレットに直接渡すと、適切なパラメーター セットに送信するためのオブジェクトを取得できます。

場合、パラメーターはパイプラインから入力を受け入れる、**パラメーター**属性が含まれています、 `ValueFromPipeline` 、キーワード、`ValueFromPipelineByPropertyName`キーワード属性、または両方のキーワードで宣言します。 サポートを設定、パラメーターでパラメーターがないかどうか、`ValueFromPipeline`または`ValueFromPipelineByPropertyName`パイプラインの入力は無視されるため、キーワード、コマンドレットを別のコマンドレットの後に配置明確ことはできません。

#### <a name="support-the-processrecord-method"></a>ProcessRecord メソッドをサポートします。

コマンドレットを実装する必要があります、先頭のコマンドレットは、パイプライン内のすべてのレコードを受け入れるように、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。 Windows PowerShell メソッドを呼び出しますこの複数回、1 回、コマンドレットに送信されるすべてのレコード。

### <a name="write-single-records-to-the-pipeline-sc03"></a>パイプライン (SC03) に 1 つのレコードを書き込む

コマンドレットがオブジェクトを書き込む必要があります、コマンドレットには、オブジェクトが返される、ときに生成されるとすぐにします。 結合した配列にバッファーに格納するためにそのコマンドレットに保持しないようにします。 オブジェクトを入力として受け取るコマンドレットは、処理、表示、または処理および遅延なしの出力オブジェクトを表示することになります。 出力を生成するコマンドレットはオブジェクト 1 つずつ呼び出す必要があります、 [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッド。 (たとえば、基になる API では、出力オブジェクトの配列を返します) ために、バッチ処理で出力オブジェクトを生成するコマンドレットを呼び出す必要があります、 [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) 2 番目のパラメーターを持つメソッドの設定`true`します。

### <a name="make-cmdlets-case-insensitive-and-case-preserving-sc04"></a>コマンドレットを大文字と小文字が区別 (SC04)

既定では、Windows PowerShell 自体は大文字にします。 ただし、多くの既存のシステムで処理しているため Windows PowerShell は容易にするための操作と互換性の大文字と小文字を保持します。 つまり、文字は、大文字で指定した場合は、Windows PowerShell では、大文字。 うまく動作するためのシステムでは、コマンドレットはこの規則に従う必要があります。 可能であれば、大文字小文字を区別でが動作する必要があります。 コマンドレットまたはコマンドの後半に、パイプラインで発生するは、元の大文字を保存し、する必要があります。 ただし、します。

## <a name="see-also"></a>参照

[必要な開発のガイドライン](./required-development-guidelines.md)

[アドバイザリ開発のガイドライン](./advisory-development-guidelines.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
