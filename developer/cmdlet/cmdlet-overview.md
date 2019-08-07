---
title: コマンドレットの概要 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell SDK]
- cmdlets [PowerShell SDK], described
ms.assetid: 0aa32589-4447-4ead-a5dd-a3be99113140
caps.latest.revision: 21
ms.openlocfilehash: 14200aed2fb94c37c8b8af29650f602945e7ac1c
ms.sourcegitcommit: 58fb23c854f5a8b40ad1f952d3323aeeccac7a24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65229368"
---
# <a name="cmdlet-overview"></a>コマンドレットの概要

コマンドレットは、Windows PowerShell 環境で使用される軽量コマンドです。 Windows PowerShell ランタイムでは、コマンドラインで提供されている自動化スクリプトのコンテキスト内でこれらのコマンドレットを呼び出します。 Windows PowerShell ランタイムも呼び出されたプログラムで Windows PowerShell Api を使用します。

## <a name="cmdlets"></a>コマンドレット

コマンドレットは、アクションの実行し、通常、パイプラインでは、次のコマンドに、Microsoft .NET Framework オブジェクトを返します。 コマンドレットを作成するには、2 つの特殊なコマンドレットの基底クラスのいずれかから派生したコマンドレット クラスを実装する必要があります。 派生クラスである必要があります。

- コマンドレットと派生クラスを識別する属性を宣言します。

- コマンドレットのパラメーターとしてパブリック プロパティを識別する属性で装飾するパブリック プロパティを定義します。

- 1 つ以上の入力処理レコードを処理メソッドをオーバーライドします。

使用して直接クラスを含むアセンブリを読み込むことができます、 [Import-module](/powershell/module/microsoft.powershell.core/import-module)コマンドレット、またはを使用して、アセンブリを読み込むホスト アプリケーションを作成できます、 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) API。 どちらの方法では、コマンドレットの機能にプログラムおよびコマンド ライン アクセスを提供します。

## <a name="cmdlet-terms"></a>コマンドレットの使用条件

次の用語は、Windows PowerShell コマンドレットのドキュメントでよく使用されます。

### <a name="cmdlet-attribute"></a>コマンドレット属性

コマンドレットとコマンドレットのクラスを宣言するために使用する .NET Framework 属性。
PowerShell は、省略可能なその他のいくつかの属性を使用して、コマンドレットの属性が必要です。
この属性の詳細については、次を参照してください。[コマンドレット属性宣言](cmdlet-attribute-declaration.md)します。

### <a name="cmdlet-parameter"></a>コマンドレットのパラメーター

コマンドレットを実行しているアプリケーションにユーザーに使用可能なパラメーターを定義するパブリック プロパティ。
名前付きの位置を指定すると、コマンドレットできる必要があると*切り替える*パラメーター。
スイッチ パラメーターを使用すると、パラメーターが呼び出しで指定された場合にのみ評価されるパラメーターを定義できます。
パラメーターのさまざまな種類の詳細については、次を参照してください。[コマンドレット パラメーター](cmdlet-parameters.md)します。

### <a name="parameter-set"></a>パラメーター セット

特定のアクションを実行するために同じコマンドで使用できるパラメーターのグループ。
コマンドレットは、複数のパラメーター セットを持つことができますが、各パラメーター セットが一意である少なくとも 1 つのパラメーターをいる必要があります。
適切なコマンドレットのデザインでは、一意のパラメーターも必須パラメーターであることを強くお勧めします。
パラメーター セットの詳細については、次を参照してください。[コマンドレット パラメーター設定](cmdlet-parameter-sets.md)します。

### <a name="dynamic-parameter"></a>動的パラメーター

実行時に、コマンドレットに追加されるパラメーター。
通常、動的パラメーターは、別のパラメーターが特定の値に設定されている場合、コマンドレットに追加されます。
動的パラメーターの詳細については、次を参照してください。[コマンドレットの動的パラメーター](cmdlet-dynamic-parameters.md)します。

### <a name="input-processing-method"></a>入力処理メソッド

コマンドが入力として受信するレコードを処理するのに使用できるメソッド。
入力の処理方法があります、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッド、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド、 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド、および[System.Management.Automation.Cmdlet.StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing)メソッド。 コマンドレットを実装するときの少なくとも 1 つをオーバーライドする必要があります、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)、および[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド。
通常、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッドは、コマンドレットが処理されるレコードごとに呼び出されるためにオーバーライドするメソッドです。
これに対し、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッドと[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)を実行するメソッドに 1 回は呼び出されます処理前または処理後のレコード。
これらのメソッドの詳細については、次を参照してください。[入力処理メソッド](cmdlet-input-processing-methods.md)します。

### <a name="shouldprocess-feature"></a>ShouldProcess 機能

PowerShell は、コマンドレットでは、システムに変更を加える前に、ユーザーにフィードバックを求めるコマンドレットを作成することができます。
コマンドレットは、この機能を使用するコマンドレットの属性を宣言すると、コマンドレットを呼び出す必要があります、ShouldProcess 機能をサポートしているを宣言する必要があります、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)入力処理メソッド内のメソッド。
ShouldProcess 機能をサポートする方法の詳細については、次を参照してください。[確認を要求する](requesting-confirmation-from-cmdlets.md)します。

### <a name="transaction"></a>トランザクション

1 つのタスクとして扱われるコマンドの論理グループです。
タスクは、グループ内の任意のコマンドに失敗し、ユーザーが受け入れるか、トランザクション内で実行されるアクションを拒否するかを選択する場合に自動的に失敗します。
トランザクションに参加するにコマンドレットの属性が宣言されている場合は、トランザクションをサポートしているコマンドレットを宣言する必要があります。
トランザクションのサポートは、Windows PowerShell 2.0 で導入されました。
トランザクションの詳細については、次を参照してください。[トランザクションをサポートする方法](how-to-support-transactions.md)します。

## <a name="how-cmdlets-differ-from-commands"></a>コマンドのコマンドレットの違い

コマンドレットは、次の方法で他のコマンド シェル環境でコマンドとは異なります。

- コマンドレットは、.NET Framework クラスのインスタンススタンドアロン実行可能ファイルではありません。

- コマンドレットは、わずか数十個の行のコードから作成できます。

- コマンドレットは、一般的に実行しない独自の解析、エラーのプレゼンテーション、または出力の書式設定します。 解析、エラーのプレゼンテーションと出力の書式設定は、Windows PowerShell ランタイムによって処理されます。

- 入力テキストのストリームではなく、パイプラインからオブジェクトをコマンドレットの処理と、コマンドレットは通常、パイプラインに出力としてオブジェクトを提供します。

- コマンドレットは、一度に 1 つのオブジェクトを処理するためのレコード指向です。

## <a name="cmdlet-base-classes"></a>コマンドレットの基底クラス

Windows PowerShell には、次の 2 つの基本クラスから派生したコマンドレットがサポートしています。

- ほとんどのコマンドレットがから派生する .NET Framework クラスに基づく、 [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)基本クラス。 Windows PowerShell ランタイムに依存関係の最小セットを使用するコマンドレットは、このクラスから派生します。 これは、2 つの利点があります。 最初の利点は、コマンドレット オブジェクトは小さく、Windows PowerShell ランタイムへの変更の影響を受ける可能性が少なくです。 2 つ目の利点は、場合にある場合は、コマンドレットのオブジェクトのインスタンスを直接作成して、Windows PowerShell ランタイムを呼び出すのではなく、直接呼び出すことです。

- 複雑なコマンドレットはから派生する .NET Framework クラスに基づいて、 [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)基本クラス。 このクラスから派生するはるかにアクセス、Windows PowerShell ランタイム。 このアクセスは、コマンドレットを呼び出して、プロバイダーにアクセスして、現在のセッション状態にアクセスするスクリプトをできます。 (現在のセッション状態にアクセスするを取得および設定のセッション変数と基本設定。)ただし、コマンドレット オブジェクトのサイズが増加するこのクラスから派生し、コマンドレットが、Windows PowerShell ランタイムの現在のバージョンより緊密に結合することを意味します。

一般に、Windows PowerShell ランタイムへの拡張が必要でない限り必要がありますから派生した、 [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)クラス。 ただし、Windows PowerShell ランタイムには、コマンドレットを実行するための広範なログ記録機能があります。 派生することによって、別のコマンドレット内から、コマンドレットの実行を防ぐことができます、監査のモデルは、このログに依存する場合、 [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)クラス。

## <a name="input-processing-methods"></a>入力処理メソッド

[System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)クラスは、レコードを処理するために使用する次の仮想メソッドを提供します。 すべての派生コマンドレット クラスには、1 つ以上の最初の 3 つのメソッドをオーバーライドする必要があります。

- [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing):コマンドレットの 1 回限り、処理前の省略可能な機能を提供するために使用します。

- [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord):コマンドレットに対してレコードずつ処理機能を提供するために使用します。 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッドは、任意の数だけ、またはまったくないコマンドレットの入力に応じて呼び出す可能性があります。

- [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing):コマンドレットの 1 回限り、処理後の省略可能な機能を提供するために使用します。

- [System.Management.Automation.Cmdlet.StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing):ユーザーが停止するコマンドレットは、非同期的に (たとえば、ctrl キーを押しながら C キーを押して) によって処理が停止するために使用します。

これらのメソッドの詳細については、[コマンドレットの入力処理メソッド](./cmdlet-input-processing-methods.md)を参照してください。

## <a name="cmdlet-attributes"></a>コマンドレットの属性

Windows PowerShell コマンドレットを管理し、一般的な機能は Windows PowerShell によって提供されると、指定に使用されるいくつかの .NET Framework 属性の定義をコマンドレットで行う必要があります。たとえば、コマンドレットやコマンドレットのパラメーターを指定して、コマンドレットの開発者はコマンドレットのコードでその機能を実装しなくてもいいように、入力の検証を要求としてクラスを指定する属性が使用されます。 属性の詳細については、[Windows PowerShell 属性](./cmdlet-attributes.md) を参照してください。

## <a name="cmdlet-names"></a>コマンドレット名

Windows PowerShell コマンドレットの名前を動詞と名詞を組み合わせた名前のペアを使用します。 たとえば、 `Get-Command` Windows PowerShell に含まれるコマンドレットを使用して、コマンド シェルに登録されているすべてのコマンドレットを取得します。 動詞は、コマンドレットを実行するアクションを識別し、名詞は、リソース、コマンドレットがそのアクションを実行しますを識別します。

.NET Framework のクラスがコマンドレットとして宣言されている場合、これらの名前が指定されます。 .NET Framework クラスをコマンドレットとして宣言する方法の詳細については、[コマンドレット属性宣言](./cmdlet-class-declaration.md)を参照してください。

## <a name="writing-cmdlet-code"></a>コマンドレット コードの記述

このドキュメントでは、コマンドレット コードの記述方法を見つけるための2つの方法を説明します。 詳細な説明のないにコードをご覧になる場合は、[コマンドレット コードの例](./examples-of-cmdlet-code.md) を参照してください。 コードについてさらに説明が必要な場合は、[GetProc チュートリアル](./getproc-tutorial.md)、 [StopProc チュートリアル](./stopproc-tutorial.md)、または[SelectStr チュートリアル](./selectstr-tutorial.md) のトピックを参照してください。

コマンドレットの記述に関するガイドラインの詳細については、[コマンドレット開発ガイドライン](./cmdlet-development-guidelines.md)を参照してください。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの概念](./windows-powershell-cmdlet-concepts.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
