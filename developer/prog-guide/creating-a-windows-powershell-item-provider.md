---
title: Windows PowerShell 項目プロバイダーを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- item providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], item provider
ms.assetid: a5a304ce-fc99-4a5b-a779-de7d85e031fe
caps.latest.revision: 6
ms.openlocfilehash: f2c9e10f0dc392399cf062500b7f28b3d1c07f6e
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055123"
---
# <a name="creating-a-windows-powershell-item-provider"></a>Windows PowerShell アイテム プロバイダーを作成する

このトピックでは、データ ストア内のデータを操作できる Windows PowerShell プロバイダーを作成する方法について説明します。 このトピックでは、ストア内のデータ要素をストアのデータの「項目」として参照されます。 その結果、ストア内のデータを操作できるプロバイダーは、Windows PowerShell 項目プロバイダーとしてに呼ばれます。

> [!NOTE]
> ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と .NET Framework 3.0 ランタイム コンポーネントを使用して、このプロバイダーのソース ファイル (AccessDBSampleProvider03.cs)。 ダウンロードの手順については、[Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)を参照してください。
>
> ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。
>
> その他の Windows PowerShell プロバイダーの実装の詳細については、[Your Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)を参照してください。

このトピックで説明されている Windows PowerShell 項目プロバイダーでは、Access データベースからのデータ項目を取得します。 ここでは、"item"は、Access データベース内のテーブルまたはテーブルの行のいずれかです。

次の一覧には、このトピックのセクションが含まれています。 Windows PowerShell 項目プロバイダーの記述に慣れていない場合に、出現する順序でこれらのセクションが読み取られます。 ただし、Windows PowerShell 項目プロバイダーの作成に習熟する場合は、必要な情報に直接移動します。

- [Windows PowerShell 項目プロバイダー クラスを定義します。](#Defining-the-Windows-PowerShell-Item-Provider-Class)

- [基本機能を定義します。](#Defining-Base-Functionality)

- [パスの有効性の確認](#Checking-for-Path-Validity)

- [項目が存在するかを決定します。](#Determining-if-an-Item-Exists)

- [動的パラメーターをアタッチ、`Test-Path`コマンドレット](#Attaching-Dynamic-Parameters-to-the-Test-Path-Cmdlet)

- [項目の取得](#Retrieving-an-Item)

- [動的パラメーターをアタッチ、`Get-Item`コマンドレット](#Attaching-Dynamic-Parameters-to-the-Get-Item-Cmdlet)

- [項目の設定](#Setting-an-Item)

- [動的パラメーターをアタッチ、`Set-Item`コマンドレット](#Retrieving-Dynamic-Parameters-for-SetItem)

- [項目をクリアします。](#Clearing-an-Item)

- [Clear-item コマンドレットへの動的パラメーター](#Retrieve-Dynamic-Parameters-for-ClearItem)

- [項目の既定のアクションを実行します。](#Performing-a-Default-Action-for-an-Item)

- [InvokeDefaultAction の動的パラメーターを取得します。](#Retrieve-Dynamic-Parameters-for-InvokeDefaultAction)

- [ヘルパー メソッドとクラスを実装します。](#Implementing-Helper-Methods-and-Classes)

- [コード サンプル](#Code-Sample)

- [オブジェクトの種類を定義して、書式設定](#Defining-Object-Types-and-Formatting)

- [Windows PowerShell プロバイダーのビルド](#Building-the-Windows-PowerShell-provider)

- [Windows PowerShell プロバイダーのテスト](#Testing-the-Windows-PowerShell-provider)

## <a name="defining-the-windows-powershell-item-provider-class"></a>Windows PowerShell 項目プロバイダー クラスを定義します。

Windows PowerShell 項目プロバイダーから派生する .NET クラスを定義する必要があります、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)基本クラス。 このセクションで説明されている項目プロバイダーのクラス定義を次に示します。

[!code-csharp[AccessDBProviderSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs#L34-L36 "AccessDBProviderSample03.cs")]

このクラス定義を[System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)属性には、2 つのパラメーターが含まれています。 最初のパラメーターには、Windows PowerShell で使用されるプロバイダーのわかりやすい名前を指定します。 2 番目のパラメーターには、プロバイダーがコマンドの処理中に、Windows PowerShell ランタイムに公開する Windows PowerShell の特定機能を指定します。 このプロバイダーでは、追加した Windows PowerShell の特定の機能はありません。

## <a name="defining-base-functionality"></a>基本機能を定義します。

」の説明に従って[デザイン、Windows PowerShell プロバイダー](./designing-your-windows-powershell-provider.md)、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスは別に提供されるその他のいくつかのクラスから派生プロバイダーの機能です。 Windows PowerShell 項目プロバイダーでは、そのため、する必要があります定義のすべてのクラスが提供する機能。

セッション固有の初期化情報を追加して、プロバイダーによって使用されるリソースを解放するための機能を実装する方法の詳細については、[基本的な Windows PowerShell プロバイダーを作成する](./creating-a-basic-windows-powershell-provider.md)を参照してください。 ただし、ここでは、説明されているプロバイダーを含む、ほとんどのプロバイダーは、この Windows PowerShell によって提供される機能の既定の実装を使用できます。

メソッドを実装する必要があります、Windows PowerShell 項目プロバイダーには、ストア内の項目を操作できる、前に、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)基底クラスにデータ ストアにアクセスします。 このクラスの実装の詳細については、[Windows PowerShell ドライブ プロバイダーを作成する](./creating-a-windows-powershell-drive-provider.md)を参照してください。

## <a name="checking-for-path-validity"></a>パスの有効性の確認

「PSPath 概念」セクションで定義されている、Windows PowerShell ランタイムが、プロバイダーへの Windows PowerShell パスを提供データ項目を探すときに[Windows PowerShell のしくみ](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)します。 Windows PowerShell 項目プロバイダーは、実装することで渡された任意のパスの構文および意味の有効性を確認する必要があります、 [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)メソッド。 このメソッドが戻る`true`パスが、有効な場合と`false`それ以外の場合。 このメソッドの実装が、パスが構文的にのみ、パスにある項目の有無を確認する必要がありますできませんに注意してくださいと意味的に正しくします。

実装をここでは、 [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)このプロバイダーのメソッド。 この実装が統一された 1 つに、パス内のすべての区切り記号を変換する NormalizePath ヘルパー メソッドを呼び出すことに注意してください。

[!code-csharp[AccessDBProviderSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs#L274-L298 "AccessDBProviderSample03.cs")]

## <a name="determining-if-an-item-exists"></a>項目が存在するかを決定します。

パスを確認した後、Windows PowerShell ランタイムはそのパスに存在する場合のデータ項目を決定する必要があります。 この種類のクエリをサポートするために、Windows PowerShell 項目プロバイダーを実装して、 [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)メソッド。 このメソッドが戻る`true`項目が指定されたパスに見つかったと`false`それ以外の場合 (既定)。

実装をここでは、 [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)このプロバイダーのメソッド。 このメソッドでは PathIsDrive、ChunkPath、および GetTable のヘルパー メソッドを呼び出して、プロバイダーを使用して DatabaseTableInfo オブジェクトを定義します。

[!code-csharp[AccessDBProviderSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs#L229-L267 "AccessDBProviderSample03.cs")]

#### <a name="things-to-remember-about-implementing-itemexists"></a>ItemExists の実装に関する注意点

実装に、次の条件が適用[System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists):

- Windows PowerShell 項目プロバイダーがから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言可能性があります、プロバイダー クラスを定義するときに、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これらのケースの実装で、 [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)メソッドは、メソッドに渡されるパスが指定した機能の要件を満たしていることを確認する必要があります。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)と[System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)プロパティ。

- このメソッドの実装は、ユーザーに表示される項目を使用するアイテムへのアクセスの任意の形式を処理する必要があります。 たとえば、ユーザーが (Windows PowerShell によって提供される)、FileSystem プロバイダーが読み取りアクセスは含まれません経由でファイルを書き込みアクセス権を持っている場合、ファイルが存在し、 [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)返します`true`します。 実装は、子項目を列挙できるかどうかに表示する親項目をチェックする必要があります。

## <a name="attaching-dynamic-parameters-to-the-test-path-cmdlet"></a>Test-path コマンドレットへの動的パラメーター

場合によって、`Test-Path`コマンドレットを呼び出す[System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)実行時に動的に指定されている追加のパラメーターが必要です。 これらの動的パラメーターを指定するには、Windows PowerShell 項目プロバイダーを実装する必要がある、 [System.Management.Automation.Provider.Itemcmdletprovider.Itemexistsdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters)メソッド。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムでは、返されたオブジェクトを使用して、パラメーターを追加、`Test-Path`コマンドレット。

この Windows PowerShell 項目プロバイダーでは、このメソッドは実装しません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovideritemexistdynamicparameters](Msh_samplestestcmdlets#testprovideritemexistdynamicparameters)]  -->

## <a name="retrieving-an-item"></a>項目の取得

項目を取得する Windows PowerShell 項目プロバイダーをオーバーライドする必要があります[System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)メソッドからの呼び出しをサポートするために、`Get-Item`コマンドレット。 このメソッドは項目を使用して書き込みます、 [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject)メソッド。

実装をここでは、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)このプロバイダーのメソッド。 このメソッドで GetTable および GetRow ヘルパー メソッドを使用して、Access データベース内のテーブルまたはデータ テーブル内の行のいずれかにある項目を取得することに注意してください。

[!code-csharp[AccessDBProviderSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs#L132-L163 "AccessDBProviderSample03.cs")]

#### <a name="things-to-remember-about-implementing-getitem"></a>GetItem の実装に関する注意点

実装を次の条件が適用[System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem):

- Windows PowerShell 項目プロバイダーがから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言可能性があります、プロバイダー クラスを定義するときに、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これらのケースの実装で[System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)メソッドに渡されたパスがそれらの要件を満たしていることを確認する必要があります。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)と[System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)プロパティ。

- 既定では、このメソッドのオーバーライドを取得しないようには一般に、ユーザーから非表示しない限り、オブジェクト、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティに設定されて`true`します。 たとえば、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) FileSystem プロバイダー チェックのためのメソッド、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティを呼び出そうとその前に[System.Management.Automation.Provider.Cmdletprovider.Writeitemobject*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject)隠しファイルやシステム ファイル。

## <a name="attaching-dynamic-parameters-to-the-get-item-cmdlet"></a>Get-item コマンドレットへの動的パラメーター

場合によって、`Get-Item`コマンドレットが実行時に動的に指定されている追加のパラメーターが必要です。 これらの動的パラメーターを指定するには、Windows PowerShell 項目プロバイダーを実装する必要がある、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)メソッド。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムでは、返されたオブジェクトを使用して、パラメーターを追加、`Get-Item`コマンドレット。

このプロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetitemdynamicparameters](Msh_samplestestcmdlets#testprovidergetitemdynamicparameters)]  -->

## <a name="setting-an-item"></a>項目の設定

項目を設定する、Windows PowerShell 項目プロバイダーをオーバーライドする必要があります、 [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドからの呼び出しをサポートするために、`Set-Item`コマンドレット。 このメソッドは、指定したパスにある項目の値を設定します。

このプロバイダーは上書きを提供していません、 [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッド。 ただし、このメソッドの既定の実装は、次のようにします。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidersetitem](Msh_samplestestcmdlets#testprovidersetitem)]  -->

#### <a name="things-to-remember-about-implementing-setitem"></a>SetItem の実装に関する注意点

実装に、次の条件が適用[System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem):

- Windows PowerShell 項目プロバイダーがから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言可能性があります、プロバイダー クラスを定義するときに、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これらのケースの実装で[System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドに渡されたパスがそれらの要件を満たしていることを確認する必要があります。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)と[System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)プロパティ。

- 既定では、このメソッドのオーバーライドしたりしないでください設定しない限り、ユーザーが非表示オブジェクトを記述、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティに設定されて`true`します。 エラーを送信するか、 [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError)パスが非表示の項目を表す場合、メソッドと[System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)に設定されている`false`します。

- 実装、 [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを呼び出す必要があります[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)をデータ ストアに変更を加える前に、その戻り値を確認します。 このメソッドは、データ ストアに、たとえば、ファイルを削除する変更が行われる操作の実行の確認に使用されます。 [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)メソッドは、任意のコマンドライン設定を考慮して、Windows PowerShell ランタイムで、ユーザーに変更するリソースの名前を送信しますまたは。ユーザー設定変数の内容を表示するかを決定します。

  呼び出し後[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)返します`true`、 [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを呼び出す必要があります、 [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)メソッド。 このメソッドは、ユーザーにフィードバックするかどうかは、操作を続行することを確認できるようにメッセージを送信します。 呼び出し[System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)危険性のあるシステムの変更、追加のチェックを許可します。

## <a name="retrieving-dynamic-parameters-for-setitem"></a>SetItem の動的パラメーターを取得します。

場合によって、`Set-Item`コマンドレットが実行時に動的に指定されている追加のパラメーターが必要です。 これらの動的パラメーターを指定するには、Windows PowerShell 項目プロバイダーを実装する必要がある、 [System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)メソッド。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムでは、返されたオブジェクトを使用して、パラメーターを追加、`Set-Item`コマンドレット。

このプロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidersetitemdynamicparameters](Msh_samplestestcmdlets#testprovidersetitemdynamicparameters)]  -->

## <a name="clearing-an-item"></a>項目をクリアします。

項目をクリアする Windows PowerShell 項目プロバイダーを実装して、 [System.Management.Automation.Provider.Itemcmdletprovider.Clearitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem)メソッドからの呼び出しをサポートするために、`Clear-Item`コマンドレット。 このメソッドは、指定されたパスにあるデータ項目を消去します。

このプロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderclearitem](Msh_samplestestcmdlets#testproviderclearitem)]  -->

#### <a name="things-to-remember-about-implementing-clearitem"></a>ClearItem の実装に関する注意点

実装を次の条件が適用[System.Management.Automation.Provider.Itemcmdletprovider.Clearitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem):

- Windows PowerShell 項目プロバイダーがから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言可能性があります、プロバイダー クラスを定義するときに、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これらのケースの実装で[System.Management.Automation.Provider.Itemcmdletprovider.Clearitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem)メソッドに渡されたパスがそれらの要件を満たしていることを確認する必要があります。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)と[System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)プロパティ。

- 既定では、このメソッドのオーバーライドしたりしないでください設定しない限り、ユーザーが非表示オブジェクトを記述、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティに設定されて`true`します。 エラーを送信するか、 [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError)パスは、ユーザーから非表示のアイテムを表す場合、メソッドと[System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)に設定されている`false`します。

- 実装、 [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを呼び出す必要があります[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)をデータ ストアに変更を加える前に、その戻り値を確認します。 このメソッドは、データ ストアに、たとえば、ファイルを削除する変更が行われる操作の実行の確認に使用されます。 [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)メソッドは、Windows PowerShell ランタイムで、ユーザーに変更して、コマンドライン設定や基本設定を処理するリソースの名前を送信します。何を表示するかを決定するのには変数。

  呼び出し後[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)返します`true`、 [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを呼び出す必要があります、 [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)メソッド。 このメソッドは、ユーザーにフィードバックするかどうかは、操作を続行することを確認できるようにメッセージを送信します。 呼び出し[System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)危険性のあるシステムの変更、追加のチェックを許可します。

## <a name="retrieve-dynamic-parameters-for-clearitem"></a>ClearItem の動的パラメーターを取得します。

場合によって、`Clear-Item`コマンドレットが実行時に動的に指定されている追加のパラメーターが必要です。 これらの動的パラメーターを指定するには、Windows PowerShell 項目プロバイダーを実装する必要がある、 [System.Management.Automation.Provider.Itemcmdletprovider.Clearitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters)メソッド。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムでは、返されたオブジェクトを使用して、パラメーターを追加、`Clear-Item`コマンドレット。

この項目プロバイダーでは、このメソッドは実装しません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderclearitemdynamicparameters](Msh_samplestestcmdlets#testproviderclearitemdynamicparameters)]  -->

## <a name="performing-a-default-action-for-an-item"></a>項目の既定のアクションを実行します。

Windows PowerShell 項目プロバイダーを実装できます、 [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)メソッドからの呼び出しをサポートするために、`Invoke-Item`コマンドレットで、プロバイダーを使用するには指定されたパスにある項目の既定のアクションを実行します。 たとえば、FileSystem プロバイダーは、このメソッドを ShellExecute を呼び出して特定の項目を使用する場合があります。

このプロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinvokedefaultaction](Msh_samplestestcmdlets#testproviderinvokedefaultaction)]  -->

#### <a name="things-to-remember-about-implementing-invokedefaultaction"></a>InvokeDefaultAction の実装に関する注意点

実装を次の条件が適用[System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction):

- Windows PowerShell 項目プロバイダーがから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言可能性があります、プロバイダー クラスを定義するときに、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これらのケースの実装で[System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)メソッドに渡されたパスがそれらの要件を満たしていることを確認する必要があります。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)と[System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)プロパティ。

- 既定では、このメソッドのオーバーライドしたりしないでください設定しない限り、ユーザーに表示されないオブジェクトを書き込む、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティに設定されて`true`します。 エラーを送信するか、 [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError)パスは、ユーザーから非表示のアイテムを表す場合、メソッドと[System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)に設定されている`false`します。

## <a name="retrieve-dynamic-parameters-for-invokedefaultaction"></a>InvokeDefaultAction の動的パラメーターを取得します。

場合によって、`Invoke-Item`コマンドレットが実行時に動的に指定されている追加のパラメーターが必要です。 これらの動的パラメーターを指定するには、Windows PowerShell 項目プロバイダーを実装する必要がある、 [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultactiondynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters)メソッド。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムでは、返されたオブジェクトを使用して、動的パラメーターを追加、`Invoke-Item`コマンドレット。

この項目プロバイダーでは、このメソッドは実装しません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinvokedefaultactiondynamicparameters](Msh_samplestestcmdlets#testproviderinvokedefaultactiondynamicparameters)]  -->

## <a name="implementing-helper-methods-and-classes"></a>ヘルパー メソッドとクラスを実装します。

この項目プロバイダーがいくつかのヘルパー メソッドを実装し、パブリックで使用されるクラスは、Windows PowerShell によって定義されたメソッドをオーバーライドします。 これらのヘルパー メソッドとクラスのコードに表示されます、[コード サンプル](#Code-Sample)セクション。

### <a name="normalizepath-method"></a>NormalizePath メソッド

この項目プロバイダーでは、パスが一貫性のある形式であることを確認する NormalizePath ヘルパー メソッドを実装します。 指定された形式は、円記号を使用して (\\)、区切り記号として。

### <a name="pathisdrive-method"></a>PathIsDrive メソッド

この項目プロバイダーでは、指定されたパスが実際には、ドライブ名であるかどうかを PathIsDrive ヘルパー メソッドを実装します。

### <a name="chunkpath-method"></a>ChunkPath メソッド

この項目プロバイダーでは、プロバイダーは、その個々 の要素を識別できるように、指定されたパスを分割する ChunkPath ヘルパー メソッドを実装します。 パスの要素から成る配列を返します。

### <a name="gettable-method"></a>GetTable メソッド

この項目プロバイダーでは、呼び出しで指定されたテーブルに関する情報を表す DatabaseTableInfo オブジェクトを返す GetTables ヘルパー メソッドを実装します。

### <a name="getrow-method"></a>GetRow メソッド

[System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)この項目プロバイダーのメソッドは、ヘルパー メソッドを呼び出します。 このヘルパー メソッドは、テーブルの指定した行に関する情報を表す DatabaseRowInfo オブジェクトを取得します。

### <a name="databasetableinfo-class"></a>DatabaseTableInfo クラス

この項目プロバイダーでは、データベース内のデータ テーブル内の情報のコレクションを表す DatabaseTableInfo クラスを定義します。 このクラスと似ています、 [System.IO.Directoryinfo](/dotnet/api/System.IO.DirectoryInfo)クラス。

サンプルの項目プロバイダーでは、データベースのテーブルを定義するテーブルの情報オブジェクトのコレクションを返す DatabaseTableInfo.GetTables メソッドを定義します。 このメソッドには、任意のデータベース エラーとして表示されること行 0 個のエントリを含むことを確認する try/catch ブロックが含まれています。

### <a name="databaserowinfo-class"></a>DatabaseRowInfo クラス

この項目プロバイダーでは、データベースのテーブルの行を表す DatabaseRowInfo ヘルパー クラスを定義します。 このクラスと似ています、 [System.IO.FileInfo](/dotnet/api/System.IO.FileInfo)クラス。

サンプル プロバイダーでは、指定されたテーブルの行情報のオブジェクトのコレクションを返す DatabaseRowInfo.GetRows メソッドを定義します。 このメソッドには、例外をトラップする try/catch ブロックが含まれています。 行情報はありませんすべてのエラーが発生します。

## <a name="code-sample"></a>コード サンプル

完全なサンプル コードでは、[AccessDbProviderSample03 コード サンプル](./accessdbprovidersample03-code-sample.md)を参照してください。

## <a name="defining-object-types-and-formatting"></a>オブジェクトの種類を定義して、書式設定

プロバイダーを記述する場合は、既存のオブジェクトにメンバーを追加または新しいオブジェクトを定義する必要があります。 完了したら、Windows PowerShell がオブジェクトのメンバーを識別するために使用できる種類のファイルと、オブジェクトの表示方法を定義するフォーマット ファイルを作成します。 詳細については、[を拡張するオブジェクトの種類と書式](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)を参照してください。

## <a name="building-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーの構築

参照してください[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。

## <a name="testing-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーのテスト

Windows PowerShell を使用したこの Windows PowerShell 項目プロバイダーが登録されると、基本的なテストし、プロバイダーの機能をドライブのみできます。 項目の操作をテストするで説明されているコンテナーの機能も実装する必要があります[コンテナーの Windows PowerShell プロバイダーを実装する](./creating-a-windows-powershell-container-provider.md)します。

## <a name="see-also"></a>参照

[Windows PowerShell SDK](../windows-powershell-reference.md)

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell プロバイダーを作成します。](./how-to-create-a-windows-powershell-provider.md)

[Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)

[オブジェクトの種類を拡張して、書式設定](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Windows PowerShell の動作](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[コンテナーの Windows PowerShell プロバイダーを作成します。](./creating-a-windows-powershell-container-provider.md)

[ドライブの Windows PowerShell プロバイダーを作成します。](./creating-a-windows-powershell-drive-provider.md)

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)