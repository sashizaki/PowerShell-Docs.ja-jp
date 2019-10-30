---
title: Windows PowerShell プロパティプロバイダーを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- property providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], property provider
ms.assetid: a6adca44-b94b-4103-9970-a9b414355e60
caps.latest.revision: 5
ms.openlocfilehash: c36b93a5b4d3e7ef92d7f5b16381a8def2dd5466
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360481"
---
# <a name="creating-a-windows-powershell-property-provider"></a>Windows PowerShell プロパティ プロバイダーを作成する

このトピックでは、ユーザーがデータストア内の項目のプロパティを操作できるようにするプロバイダーを作成する方法について説明します。 その結果、この種類のプロバイダーは、Windows PowerShell プロパティプロバイダーと呼ばれます。 たとえば、Windows PowerShell によって提供されるレジストリプロバイダーは、レジストリキーの値をレジストリキー項目のプロパティとして処理します。 この種類のプロバイダーは、 [Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider)インターフェイスを .net クラスの実装に追加する必要があります。

> [!NOTE]
> Windows PowerShell には、Windows PowerShell プロバイダーの開発に使用できるテンプレートファイルが用意されています。 TemplateProvider.cs ファイルは、Microsoft Windows Software Development Kit for Windows Vista および .NET Framework 3.0 ランタイムコンポーネントで使用できます。 ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)」を参照してください。
>
> ダウンロードしたテンプレートは、 **\<PowerShell Samples >** ディレクトリにあります。 このファイルのコピーを作成し、新しい Windows PowerShell プロバイダーを作成するためにコピーを使用して、不要な機能を削除する必要があります。
>
> その他の Windows PowerShell プロバイダーの実装の詳細については、「 [Windows Powershell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」を参照してください。

> [!CAUTION]
> プロパティプロバイダーのメソッドは、System........................ [Writepropertyobject *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WritePropertyObject)メソッドを使用してオブジェクトを書き込む必要があります。

## <a name="defining-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーの定義

プロパティプロバイダーは、 [Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider)インターフェイスをサポートする .net クラスを作成する必要があります。 Windows PowerShell によって提供される TemplateProvider.cs ファイルの既定のクラス宣言を次に示します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyproviderclassdeclaration](Msh_samplestestcmdlets#testcmdletspropertyproviderclassdeclaration)]  -->

## <a name="defining-base-functionality"></a>基本機能の定義

[System.Management.Automation.Provider.Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider)インターフェイスは、Drivecmdletprovider クラスを除き、どのプロバイダーの基底クラスにもアタッチできます。このインターフェイスには、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスが含まれています。 使用する基本クラスに必要な基本機能を追加します。 基本クラスの詳細については、「 [Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」を参照してください。

## <a name="retrieving-properties"></a>取得 (プロパティを)

プロパティを取得するには、プロバイダーが[Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)メソッドを実装して、`Get-ItemProperty` コマンドレットからの呼び出しをサポートする必要があります。 このメソッドは、指定されたプロバイダー内部パス (完全修飾) にある項目のプロパティを取得します。

@No__t_0 パラメーターは、取得するプロパティを示します。 このパラメーターが `null` または空の場合、メソッドはすべてのプロパティを取得する必要があります。 さらに、 [Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)は、取得されたプロパティのプロパティバッグを表す、 [system.servicemodel オブジェクトの](/dotnet/api/System.Management.Automation.PSObject)インスタンスを書き込んでいることを意味しています。 メソッドは何も返しません。

[Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)の実装では、選択リストの各要素に対して、プロパティ名のワイルドカード展開がサポートされていることをお勧めします。 これを行うには、 [Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern)クラスを使用して、ワイルドカードのパターンマッチングを実行します。

Windows PowerShell によって提供される TemplateProvider.cs ファイルからの[Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)の既定の実装を次に示します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidergetproperty](Msh_samplestestcmdlets#testcmdletspropertyprovidergetproperty)]  -->

#### <a name="things-to-remember-about-implementing-getproperty"></a>GetProperty の実装に関する注意事項

[Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)の実装には、次の条件が当てはまる場合があります。

- プロバイダークラスを定義すると、Windows PowerShell プロパティプロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。 このような場合、 [Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)メソッドの実装では、メソッドに渡されるパスが、指定された機能の要件を満たしていることを確認する必要があります。 これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...

- 既定では、このメソッドのオーバーライドでは、ユーザーに表示されないオブジェクトのリーダーを取得しないでください。この場合、 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティが `true` に設定されている必要があります。 パスが、ユーザーおよびシステムから非表示になっている項目を表している場合は、エラーを書き込む必要があります。 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)を `false` に設定します。

## <a name="attaching-dynamic-parameters-to-the-get-itemproperty-cmdlet"></a>Get-itemproperty コマンドレットへの動的パラメーターのアタッチ

@No__t_0 コマンドレットでは、実行時に動的に指定される追加のパラメーターが必要になる場合があります。 これらの動的パラメーターを指定するには、Windows PowerShell プロパティプロバイダーで[Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters)メソッドを実装する必要があります。 @No__t_0 パラメーターは、完全修飾プロバイダーの内部パスを示します。一方、`providerSpecificPickList` パラメーターは、コマンドラインで入力されたプロバイダー固有のプロパティを指定します。 プロパティがコマンドレットにパイプされている場合、このパラメーターは `null` または空になることがあります。 この場合、このメソッドは、コマンドレットクラスまたは system.servicemodel 型の[Parameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクトと同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。 Windows PowerShell ランタイムは、返されたオブジェクトを使用して、コマンドレットにパラメーターを追加します。

ここでは、Windows PowerShell によって提供される TemplateProvider.cs ファイルからの[Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters)の既定の実装を示します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidergetpropertydynamicparameters](Msh_samplestestcmdlets#testcmdletspropertyprovidergetpropertydynamicparameters)]  -->

## <a name="setting-properties"></a>設定のプロパティ

プロパティを設定するには、Windows PowerShell プロパティプロバイダーが[Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)メソッドを実装して、`Set-ItemProperty` コマンドレットからの呼び出しをサポートする必要があります。 このメソッドは、指定されたパスにある項目の1つ以上のプロパティを設定し、必要に応じて、指定されたプロパティを上書きします。 また、 [Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)は、更新されたプロパティのプロパティバッグを表す、system.servicemodel[オブジェクトの](/dotnet/api/System.Management.Automation.PSObject)インスタンスも書き込みます。このオブジェクトは、更新されたプロパティのプロパティバッグを表します。

ここでは、Windows PowerShell によって提供される TemplateProvider.cs ファイルからの[Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)の既定の実装を示します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidersetproperty](Msh_samplestestcmdlets#testcmdletspropertyprovidersetproperty)]  -->

#### <a name="things-to-remember-about-implementing-set-itemproperty"></a>Get-itemproperty の実装に関する注意事項

[Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)の実装には、次の条件が当てはまる場合があります。

- プロバイダークラスを定義すると、Windows PowerShell プロパティプロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。 このような場合は、 [Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)メソッドを実装することで、メソッドに渡されるパスが指定された機能の要件を満たしていることを確認する必要があります。 これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...

- 既定では、このメソッドのオーバーライドでは、ユーザーに表示されないオブジェクトのリーダーを取得しないでください。この場合、 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティが `true` に設定されている必要があります。 パスが、ユーザーおよびシステムから非表示になっている項目を表している場合は、エラーを書き込む必要があります。 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)を `false` に設定します。

- [Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)メソッドを実装する場合は、system.object を呼び出し、戻り値を確認する必要があります。このメソッドの戻り値を確認し[ます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)データストアに変更を加える前。 このメソッドは、ファイル名の変更など、システム状態が変更されたときの操作の実行を確認するために使用されます。 Windows PowerShell ランタイムを使用して、変更するリソースの名前をユーザー[に送信し](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)ます。また、コマンドライン設定またはユーザー設定変数を処理するかどうかを指定します。が表示されます。

  @No__t_1[が返され](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)た後に、危険性の高いシステム変更を行うことができる場合は、の[ようになります。Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)メソッド[は、system.servicemodel メソッドを呼び](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)出す必要があります。このメソッドは、...................... このメソッドは、ユーザーに確認メッセージを送信して、操作を続行する必要があることを示す追加のフィードバックを許可します。

## <a name="attaching-dynamic-parameters-for-the-set-itemproperty-cmdlet"></a>Get-itemproperty コマンドレットの動的パラメーターのアタッチ

@No__t_0 コマンドレットでは、実行時に動的に指定される追加のパラメーターが必要になる場合があります。 これらの動的パラメーターを指定するには、Windows PowerShell プロパティプロバイダーで[Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters)メソッドを実装する必要があります。 このメソッドは、コマンドレットクラスや[system.string オブジェクトと](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。 動的パラメーターを追加する必要がない場合は、`null` 値を返すことができます。

ここでは、Windows PowerShell によって提供される TemplateProvider.cs ファイルからの[Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters)の既定の実装を示します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidersetpropertydynamicparameters](Msh_samplestestcmdlets#testcmdletspropertyprovidersetpropertydynamicparameters)]  -->

## <a name="clearing-properties"></a>プロパティのクリア

プロパティをクリアするには、Windows PowerShell プロパティプロバイダーが[Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)メソッドを実装して、`Clear-ItemProperty` コマンドレットからの呼び出しをサポートする必要があります。 このメソッドは、指定されたパスにある項目の1つ以上のプロパティを設定します。

Windows PowerShell によって提供される TemplateProvider.cs ファイルの[Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)の既定の実装を次に示します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyproviderclearproperty](Msh_samplestestcmdlets#testcmdletspropertyproviderclearproperty)]  -->

#### <a name="thing-to-remember-about-implementing-clearproperty"></a>ClearProperty の実装について覚えておくべきこと

[Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)の実装には、次の条件が当てはまる場合があります。

- プロバイダークラスを定義すると、Windows PowerShell プロパティプロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。 このような場合、 [Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)メソッドを実装するには、メソッドに渡されるパスが、指定された機能の要件を満たしていることを確認する必要があります。 これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...

- 既定では、このメソッドのオーバーライドでは、ユーザーに表示されないオブジェクトのリーダーを取得しないでください。この場合、 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティが `true` に設定されている必要があります。 パスが、ユーザーおよびシステムから非表示になっている項目を表している場合は、エラーを書き込む必要があります。 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)を `false` に設定します。

- [Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)メソッドを実装するには、system.object を呼び出して、戻り値を確認する必要があります。このメソッドの戻り値を確認し[ます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)データストアに変更を加える前。 このメソッドは、コンテンツのクリアなど、システム状態が変更される前に操作の実行を確認するために使用されます。 Windows PowerShell ランタイムでは、変更するリソースの名前をユーザーに送信します。 Windows PowerShell ランタイムでは、コマンドライン設定またはユーザー設定変数を考慮に[入れます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)表示される内容。

  @No__t_1[が返され](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)た後に、危険性の高いシステム変更を行うことができる場合は、の[ようになります。Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)メソッド[は、system.servicemodel メソッドを呼び](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)出す必要があります。このメソッドは、"..................... このメソッドは、ユーザーに確認メッセージを送信して、危険な可能性のある操作を続行する必要があることを示す追加のフィードバックを許可します。

## <a name="attaching-dynamic-parameters-to-the-clear-itemproperty-cmdlet"></a>動的パラメーターを Get-itemproperty コマンドレットにアタッチする

@No__t_0 コマンドレットでは、実行時に動的に指定される追加のパラメーターが必要になる場合があります。 これらの動的パラメーターを指定するには、Windows PowerShell プロパティプロバイダーで[Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters)メソッドを実装する必要があります。 このメソッドは、コマンドレットクラスや[system.string オブジェクトと](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。 動的パラメーターを追加する必要がない場合は、`null` 値を返すことができます。

ここでは、Windows PowerShell によって提供される TemplateProvider.cs ファイルからの[Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters)の既定の実装を示します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyproviderclearpropertydynamicparameters](Msh_samplestestcmdlets#testcmdletspropertyproviderclearpropertydynamicparameters)]  -->

## <a name="building-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーの構築

「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法」を](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)参照してください。

## <a name="see-also"></a>関連項目

[Windows PowerShell プロバイダー](./designing-your-windows-powershell-provider.md)

[Windows PowerShell プロバイダーを設計する](./designing-your-windows-powershell-provider.md)

[オブジェクトの種類と書式設定の拡張](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)