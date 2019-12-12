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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365891"
---
# <a name="cmdlet-overview"></a>コマンドレットの概要

コマンドレットは、Windows PowerShell 環境で使用される簡易コマンドです。 Windows PowerShell ランタイムは、コマンドラインで指定されたオートメーションスクリプトのコンテキスト内でこれらのコマンドレットを呼び出します。 Windows PowerShell ランタイムでは、Windows PowerShell Api を使用してプログラムで呼び出すこともできます。

## <a name="cmdlets"></a>コマンドレット

コマンドレットは、アクションを実行し、通常、パイプラインの次のコマンドに Microsoft .NET Framework オブジェクトを返します。 コマンドレットを記述するには、2つの特殊なコマンドレット基本クラスのうちの1つから派生したコマンドレットクラスを実装する必要があります。 派生クラスには次のものが必要です。

- 派生クラスをコマンドレットとして識別する属性を宣言します。

- コマンドレットのパラメーターとしてパブリックプロパティを識別する属性で装飾されたパブリックプロパティを定義します。

- 1つ以上の入力処理メソッドをオーバーライドしてレコードを処理します。

クラスを含むアセンブリは、Initialsessionstate [Import-Module](/powershell/module/microsoft.powershell.core/import-module)コマンドレットを使用して直接読み込むことができます。また、アセンブリを読み込むホストアプリケーションを作成するには、 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) API を使用します。 どちらの方法でも、プログラムおよびコマンドラインからコマンドレットの機能にアクセスできます。

## <a name="cmdlet-terms"></a>コマンドレットの使用条件

Windows PowerShell コマンドレットのドキュメントでは、次の用語が頻繁に使用されます。

### <a name="cmdlet-attribute"></a>コマンドレット属性

コマンドレットとしてコマンドレットクラスを宣言するために使用される .NET Framework 属性。
PowerShell では、省略可能な他のいくつかの属性が使用されますが、コマンドレットの属性は必須です。
この属性の詳細については、「[コマンドレット属性の宣言](cmdlet-attribute-declaration.md)」を参照してください。

### <a name="cmdlet-parameter"></a>コマンドレットのパラメーター

ユーザーが使用できるパラメーター、またはコマンドレットを実行しているアプリケーションに対して使用可能なパラメーターを定義するパブリックプロパティ。
コマンドレットには、必須の、名前付き、位置指定、および*スイッチ*のパラメーターを指定できます。
スイッチパラメーターを使用すると、呼び出しでパラメーターが指定されている場合にのみ評価されるパラメーターを定義できます。
さまざまな種類のパラメーターの詳細については、「[コマンドレットパラメーター](cmdlet-parameters.md)」を参照してください。

### <a name="parameter-set"></a>パラメーターセット

特定のアクションを実行するために同じコマンドで使用できるパラメーターのグループ。
コマンドレットには複数のパラメーターセットを含めることができますが、各パラメーターセットには一意のパラメーターが少なくとも1つ必要です。
適切なコマンドレットの設計では、unique パラメーターも必須パラメーターであることを強く示唆しています。
パラメーターセットの詳細については、「[コマンドレットパラメーターセット](cmdlet-parameter-sets.md)」を参照してください。

### <a name="dynamic-parameter"></a>動的パラメーター

実行時にコマンドレットに追加されるパラメーター。
通常、動的パラメーターは、別のパラメーターが特定の値に設定されている場合に、コマンドレットに追加されます。
動的パラメーターの詳細については、「[コマンドレット動的パラメーター](cmdlet-dynamic-parameters.md)」を参照してください。

### <a name="input-processing-method"></a>入力処理方法

コマンドが入力として受信するレコードを処理するのに使用できるメソッド。
入力処理メソッドには、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) .................................................[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)........................................... コマンドレット[System.Management.Automation.Cmdlet.StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing)。 コマンドレットを実装する場合は、少なくと[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)も1つの system................................................. コマンドレットシステムの....... コマンドレット。
通常、この[メソッドは](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)、コマンドレットが処理するすべてのレコードに対して呼び出されるため、オーバーライドされるメソッドです。
これに対して、レコードの事前処理または後処理を実行するために、1回は呼び出されますが、[このメソッドと](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)は、[このメソッドと](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)共に呼び出されます。
これらのメソッドの詳細については、「[入力処理方法](cmdlet-input-processing-methods.md)」を参照してください。

### <a name="shouldprocess-feature"></a>機能を処理する

PowerShell では、コマンドレットがシステムに変更を加える前に、ユーザーにフィードバックを求めるコマンドレットを作成できます。
この機能を使用するには、コマンドレットでコマンドレットの属性を宣言するときに、コマンドレットで指定する機能がサポートされていることを宣言する必要があり[ます。また](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)、コマンドレット[は、入力](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)処理メソッド内からメソッドを呼び出す必要があります。
入力プロセス機能をサポートする方法の詳細については、「[確認の要求](requesting-confirmation-from-cmdlets.md)」を参照してください。

### <a name="transaction"></a>トランザクション

1つのタスクとして扱われるコマンドの論理グループ。
グループ内のいずれかのコマンドが失敗し、ユーザーがトランザクション内で実行されたアクションを受け入れるか拒否するかを選択できる場合、タスクは自動的に失敗します。
コマンドレットは、トランザクションに参加するには、コマンドレットの属性が宣言されているときにトランザクションをサポートするように宣言する必要があります。
トランザクションのサポートは、Windows PowerShell 2.0 で導入されました。
トランザクションの詳細については、「[トランザクションをサポートする方法](how-to-support-transactions.md)」を参照してください。

## <a name="how-cmdlets-differ-from-commands"></a>コマンドレットの違い

コマンドレットは、次の方法で他のコマンドシェル環境のコマンドとは異なります。

- コマンドレットは .NET Framework クラスのインスタンスです。これらはスタンドアロンの実行可能ファイルではありません。

- コマンドレットは、数十のコード行から作成できます。

- コマンドレットは、通常、独自の解析、エラー表示、または出力書式設定を行いません。 解析、エラー表示、および出力の書式設定は、Windows PowerShell ランタイムによって処理されます。

- コマンドレットは、テキストのストリームからではなく、パイプラインからの入力オブジェクトを処理します。また、コマンドレットは通常、オブジェクトをパイプラインに出力として配信します。

- コマンドレットは、一度に1つのオブジェクトを処理するため、レコード指向です。

## <a name="cmdlet-base-classes"></a>コマンドレットの基本クラス

Windows PowerShell は、次の2つの基本クラスから派生したコマンドレットをサポートしています。

- ほとんどのコマンドレットは、[システム](/dotnet/api/System.Management.Automation.Cmdlet)の .NET Framework 基底クラスから派生したクラスに基づいています。 このクラスから派生させることにより、コマンドレットは、Windows PowerShell ランタイムの最小限の依存関係を使用できます。 これには2つの利点があります。 1つ目の利点は、コマンドレットオブジェクトが小さく、Windows PowerShell ランタイムの変更によって影響を受ける可能性が低いことです。 2つ目の利点は、必要に応じて、コマンドレットオブジェクトのインスタンスを直接作成してから、Windows PowerShell ランタイムを使用して呼び出すのではなく、直接呼び出すことができることです。

- より複雑なコマンドレットは、 [PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)基底クラスから派生した .NET Framework クラスに基づいています。 このクラスから派生させることで、Windows PowerShell ランタイムにはるかに多くのアクセスを提供できます。 このアクセスにより、コマンドレットは、スクリプトを呼び出したり、プロバイダーにアクセスしたり、現在のセッション状態にアクセスしたりすることができます。 (現在のセッション状態にアクセスするには、セッション変数とユーザー設定を取得して設定します)。ただし、このクラスから派生すると、コマンドレットオブジェクトのサイズが大きくなります。また、コマンドレットが現在のバージョンの Windows PowerShell ランタイムと密接に結合されていることを意味します。

一般に、Windows PowerShell ランタイムへの拡張アクセスが必要な場合を除き、[このクラスから](/dotnet/api/System.Management.Automation.Cmdlet)派生させる必要があります。 ただし、Windows PowerShell ランタイムには、コマンドレットを実行するための広範なログ記録機能があります。 監査モデルがこのログに依存している場合は、 [PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)クラスから派生することによって、別のコマンドレット内からコマンドレットを実行できないようにすることができます。

## <a name="input-processing-methods"></a>入力処理メソッド

System.string[クラスは](/dotnet/api/System.Management.Automation.Cmdlet)、レコードを処理するために使用される次の仮想メソッドを提供します。 派生したすべてのコマンドレットクラスは、最初の3つのメソッドをオーバーライドする必要があります。

- [次の](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)ように実行します。コマンドレットに対して、オプションの1回限りの事前処理機能を提供するために使用されます。

- ..............[コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord):コマンドレットのレコードごとの処理機能を提供するために使用されます。 コマンドレットの入力によっては、すべての回数 (またはまったくではない) の呼び出しが必要になる場合があり[ます。](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

- [次の](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)ようにします。コマンドレットに対して、オプションの1回限りの後処理機能を提供するために使用されます。

- ............. [StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing):ユーザーがコマンドレットを非同期に停止したとき (たとえば、CTRL + C キーを押して)、処理を停止するために使用されます。

これらのメソッドの詳細については、「[コマンドレットの入力処理方法](./cmdlet-input-processing-methods.md)」を参照してください。

## <a name="cmdlet-attributes"></a>コマンドレットの属性

Windows PowerShell では、コマンドレットを管理したり、Windows PowerShell によって提供される一般的な機能を指定したり、コマンドレットで必要になる可能性のある、いくつかの .NET Framework 属性を定義しています。 たとえば、属性を使用して、クラスをコマンドレットとして指定したり、コマンドレットのパラメーターを指定したり、コマンドレットの開発者がコマンドレットコードにその機能を実装する必要がないように入力の検証を要求したりします。 属性の詳細については、「 [Windows PowerShell の属性](./cmdlet-attributes.md)」を参照してください。

## <a name="cmdlet-names"></a>コマンドレット名

Windows PowerShell では、動詞と名詞の名前の組み合わせを使用して、コマンドレットに名前を指定します。 たとえば、Windows PowerShell に含まれている `Get-Command` コマンドレットは、コマンドシェルに登録されているすべてのコマンドレットを取得するために使用されます。 動詞はコマンドレットが実行するアクションを識別し、名詞は、コマンドレットがアクションを実行するリソースを識別します。

これらの名前は、.NET Framework クラスがコマンドレットとして宣言されている場合に指定します。 .NET Framework クラスをコマンドレットとして宣言する方法の詳細については、「[コマンドレットの属性宣言](./cmdlet-class-declaration.md)」を参照してください。

## <a name="writing-cmdlet-code"></a>コマンドレットコードの記述

このドキュメントでは、コマンドレットコードの記述方法を確認する2つの方法について説明します。 コードをよく説明する必要がない場合は、[コマンドレットコードの例](./examples-of-cmdlet-code.md)を参照してください。 コードの詳細については、「 [Getproc チュートリアル](./getproc-tutorial.md)」、「 [stopproc チュートリアル](./stopproc-tutorial.md)」、または「 [selectstr チュートリアル](./selectstr-tutorial.md)」のトピックを参照してください。

コマンドレットの記述に関するガイドラインの詳細については、「[コマンドレットの開発ガイドライン](./cmdlet-development-guidelines.md)」を参照してください。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの概念](./windows-powershell-cmdlet-concepts.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
