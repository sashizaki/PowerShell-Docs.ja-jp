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
ms.openlocfilehash: a2d0f2b435b4b56ac491804f3af695641449e17a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360501"
---
# <a name="creating-a-windows-powershell-item-provider"></a>Windows PowerShell アイテム プロバイダーを作成する

このトピックでは、データストア内のデータを操作できる Windows PowerShell プロバイダーを作成する方法について説明します。 このトピックでは、ストア内のデータの要素を、データストアの "項目" と呼びます。 その結果、ストア内のデータを操作できるプロバイダーは、Windows PowerShell 項目プロバイダーと呼ばれます。

> [!NOTE]
> このプロバイダーのC#ソースファイル (AccessDBSampleProvider03.cs) をダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。 ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)」を参照してください。
>
> ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。
>
> その他の Windows PowerShell プロバイダーの実装の詳細については、「 [Windows Powershell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」を参照してください。

このトピックで説明する Windows PowerShell 項目プロバイダーは、Access データベースからデータの項目を取得します。 この場合、"item" は Access データベースのテーブルまたはテーブル内の行のいずれかです。

## <a name="defining-the-windows-powershell-item-provider-class"></a>Windows PowerShell 項目プロバイダークラスの定義

Windows PowerShell 項目プロバイダーでは、.NET クラスを定義する必要があります。このクラス[の基底クラス](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)から派生します。 このセクションで説明する項目プロバイダーのクラス定義を次に示します。

[!code-csharp[AccessDBProviderSample03.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs#L34-L36 "AccessDBProviderSample03.cs")]

このクラス定義では、 [system.string 属性に2つのパラメーター](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)が含まれていることに注意してください。 最初のパラメーターは、Windows PowerShell によって使用されるプロバイダーのわかりやすい名前を指定します。 2番目のパラメーターは、コマンドの処理中にプロバイダーが Windows PowerShell ランタイムに公開する Windows PowerShell 固有の機能を指定します。 このプロバイダーには、Windows PowerShell 固有の機能は追加されていません。

## <a name="defining-base-functionality"></a>基本機能の定義

「 [Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」で説明されているように、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスは、さまざまなプロバイダー機能を提供する他のいくつかのクラスから派生します。 そのため、Windows PowerShell 項目プロバイダーは、これらのクラスによって提供されるすべての機能を定義する必要があります。

セッション固有の初期化情報を追加したり、プロバイダーで使用されるリソースを解放したりするための機能を実装する方法の詳細については、「[基本的な Windows PowerShell プロバイダーの作成](./creating-a-basic-windows-powershell-provider.md)」を参照してください。 ただし、ここで説明するプロバイダーを含むほとんどのプロバイダーは、Windows PowerShell によって提供されるこの機能の既定の実装を使用できます。

Windows PowerShell 項目プロバイダーがストア内の項目を操作できるようにするには、データストアにアクセスするために、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)基底クラスのメソッドを実装する必要があります。 このクラスの実装の詳細については、「 [Windows PowerShell ドライブプロバイダーの作成](./creating-a-windows-powershell-drive-provider.md)」を参照してください。

## <a name="checking-for-path-validity"></a>パスの有効性を確認しています

Windows powershell ランタイムは、データの項目を検索するときに、windows powershell の[動作につい](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)ての「Pspath の概念」セクションで定義されているように、プロバイダーへの windows powershell パスを提供します。 Windows PowerShell 項目プロバイダーは、指定されたパスの構文とセマンティックの有効性を検証する必要があります。そのためには、 [System.](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) .................. を実装します。 このメソッドは、パスが有効な場合は `true` を返し、それ以外の場合は `false` を返します。 このメソッドの実装では、パスに項目が存在するかどうかを検証しないことに注意してください。ただし、パスの構文的で意味が正しいことだけを確認してください。

ここでは、このプロバイダーのシステムの管理を実装しています。このプロバイダーの[Isvalidpath *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)メソッド。 この実装では、NormalizePath ヘルパーメソッドを呼び出して、パス内のすべての区切り記号を一様なものに変換することに注意してください。

[!code-csharp[AccessDBProviderSample03.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs#L274-L298 "AccessDBProviderSample03.cs")]

## <a name="determining-if-an-item-exists"></a>項目が存在するかどうかを判断する

パスを確認した後、Windows PowerShell ランタイムは、データの項目がそのパスに存在するかどうかを判断する必要があります。 この種類のクエリをサポートするために、Windows PowerShell 項目プロバイダーは、[システムの管理](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)を実装しています。 このメソッドは、指定したパスに項目が見つかった `true` を返します。それ以外の場合は `false` (既定)。

次に示すのは、このプロバイダーの system.servicemodel.................... [Itemexists *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)メソッドの実装です。 このメソッドは PathIsDrive、ChunkPath、および GetTable helper メソッドを呼び出し、プロバイダーによって定義されたオブジェクトを使用します。

[!code-csharp[AccessDBProviderSample03.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs#L229-L267 "AccessDBProviderSample03.cs")]

#### <a name="things-to-remember-about-implementing-itemexists"></a>ItemExists の実装に関する注意事項

次の条件は、システムの実装に適用される場合があります。 [Itemexists *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists):

- プロバイダークラスを定義すると、Windows PowerShell 項目プロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。 このような場合、[システム](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)の実装では、メソッドに渡されるパスが指定された機能の要件を満たしていることを確認する必要があります。 これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...

- このメソッドの実装では、項目がユーザーに表示される可能性のある項目への任意の形式のアクセスを処理する必要があります。 たとえば、ユーザーがファイルシステムプロバイダー (Windows PowerShell によって提供される) を介してファイルに対する書き込みアクセス権を持っていても、 [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)読み取りアクセス権を持っていない場合、ファイルはまだ存在しています`true`。 子項目を列挙できるかどうかを確認するために、の実装で親項目を確認することが必要になる場合があります。

## <a name="attaching-dynamic-parameters-to-the-test-path-cmdlet"></a>テストパスコマンドレットへの動的パラメーターのアタッチ

場合によっては、`Test-Path` コマンドレットを実行すると、実行時に動的に指定される追加のパラメーターが必要になることが[あります。](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) これらの動的パラメーターを指定するには、Windows PowerShell 項目プロバイダーで、system.servicemodel.............................- [Dynamicsdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters)メソッドを実装します。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の Parameterdictionary と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。 [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムは、返されたオブジェクトを使用して、`Test-Path` コマンドレットにパラメーターを追加します。

この Windows PowerShell 項目プロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovideritemexistdynamicparameters](Msh_samplestestcmdlets#testprovideritemexistdynamicparameters)]  -->

## <a name="retrieving-an-item"></a>項目を取得する

項目を取得するには、Windows PowerShell 項目プロバイダーが、`Get-Item` コマンドレットからの呼び出しをサポートするように、system.string [* Getitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)メソッドをオーバーライドする必要があります。 このメソッドは、[システム](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject)の.............................. を使用して項目を書き込みます。

次に示すのは、このプロバイダーに対する system.servicemodel......................... [...](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)を実装したものです。 このメソッドは、GetTable と GetRow のヘルパーメソッドを使用して、Access データベース内のテーブルまたはデータテーブル内の行のいずれかの項目を取得します。

[!code-csharp[AccessDBProviderSample03.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs#L132-L163 "AccessDBProviderSample03.cs")]

#### <a name="things-to-remember-about-implementing-getitem"></a>GetItem の実装に関する注意事項

次の条件は、[システム](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)の実装に適用される可能性があります。

- プロバイダークラスを定義すると、Windows PowerShell 項目プロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。 このような場合は、メソッドに渡されるパスが要件を満たしているかどうかを確認する必要[があります。](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...

- 既定では、このメソッドをオーバーライドしても、通常はユーザーに表示されないオブジェクトを取得しないでください。この場合、 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティが `true` に設定されている必要があります。 たとえば、FileSystem プロバイダーの場合、 [system.](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) .................................................... [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) ..........。隠しファイルまたはシステム[ファイルの場合は、.](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) .........

## <a name="attaching-dynamic-parameters-to-the-get-item-cmdlet"></a>動的パラメーターの Get Item コマンドレットへのアタッチ

@No__t_0 コマンドレットでは、実行時に動的に指定される追加のパラメーターが必要になる場合があります。 これらの動的パラメーターを指定するには、Windows PowerShell 項目プロバイダーで[Getitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)メソッドを実装する必要があります。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の Parameterdictionary と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。 [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムは、返されたオブジェクトを使用して、`Get-Item` コマンドレットにパラメーターを追加します。

このプロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetitemdynamicparameters](Msh_samplestestcmdlets#testprovidergetitemdynamicparameters)]  -->

## <a name="setting-an-item"></a>項目を設定する

項目を設定するには、Windows PowerShell 項目プロバイダーで[Setitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドをオーバーライドして、`Set-Item` コマンドレットからの呼び出しをサポートする必要があります。 このメソッドは、指定されたパスにある項目の値を設定します。

このプロバイダーでは、 [Setitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドのオーバーライドは提供されていませんが、 ただし、このメソッドの既定の実装は次のとおりです。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidersetitem](Msh_samplestestcmdlets#testprovidersetitem)]  -->

#### <a name="things-to-remember-about-implementing-setitem"></a>SetItem の実装に関する注意事項

[Setitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)の実装には、次の条件が当てはまる場合があります:。

- プロバイダークラスを定義すると、Windows PowerShell 項目プロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。 このような場合は、 [Setitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)の実装によって、メソッドに渡されるパスが要件を満たしていることを確認する必要があります。 これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...

- 既定では、このメソッドのオーバーライドでは、ユーザーに表示されないオブジェクトを設定または作成する必要はありません。この場合、 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティが `true` に設定されている必要があります。 パスが非表示の項目と[WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) * を表している場合、このメソッドにはエラーを送信する必要があります。 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)は、`false` に設定されています。

- [Setitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを実装する場合は、前に「」を呼び出してから、その戻り値を確認してから、作成する必要があり[ます](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)が、データストアに対する変更。 このメソッドは、ファイルの削除など、データストアに変更が加えられたときの操作の実行を確認するために使用されます。 [System.](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) .......................................................表示する内容を決定します。

  Setitem を呼び出すと、が[`true` 返されます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)その後、 [*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドは、を呼び出す必要があります。この場合、このメソッドは、 [System.](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) ........ このメソッドは、ユーザーにメッセージを送信して、操作を続行する必要があるかどうかを確認するフィードバックを許可します。 System.object を呼び出すと、危険性の高いシステム変更を追加で確認できるように[なります。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)

## <a name="retrieving-dynamic-parameters-for-setitem"></a>SetItem の動的パラメーターの取得

@No__t_0 コマンドレットでは、実行時に動的に指定される追加のパラメーターが必要になる場合があります。 これらの動的パラメーターを指定するには、Windows PowerShell 項目プロバイダーで[Setitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)メソッドを実装する必要があります。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の Parameterdictionary と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。 [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムは、返されたオブジェクトを使用して、`Set-Item` コマンドレットにパラメーターを追加します。

このプロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidersetitemdynamicparameters](Msh_samplestestcmdlets#testprovidersetitemdynamicparameters)]  -->

## <a name="clearing-an-item"></a>項目のクリア

項目をクリアするには、Windows PowerShell 項目プロバイダーが、`Clear-Item` コマンドレットからの呼び出しをサポートするために、system.object を実装します。 [Clearitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem)メソッド。 このメソッドは、指定されたパスのデータ項目を消去します。

このプロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderclearitem](Msh_samplestestcmdlets#testproviderclearitem)]  -->

#### <a name="things-to-remember-about-implementing-clearitem"></a>ClearItem の実装に関する注意事項

次の条件は、システムの実装に適用される場合があります。 [clearitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem):

- プロバイダークラスを定義すると、Windows PowerShell 項目プロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。 このような場合、[システム](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem)の実装では、メソッドに渡されるパスが要件を満たしていることを確認する必要があります。 これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...

- 既定では、このメソッドのオーバーライドでは、ユーザーに表示されないオブジェクトを設定または作成する必要はありません。この場合、 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティが `true` に設定されている必要があります。 パスがユーザーと[WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError)の非表示になっている項目を表している場合は、このメソッドにエラーを送信する必要があります。 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)を使用して、* です。を `false` に設定します。

- [Setitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを実装する場合は、前に「」を呼び出してから、その戻り値を確認してから、作成する必要があり[ます](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)が、データストアに対する変更。 このメソッドは、ファイルの削除など、データストアに変更が加えられたときの操作の実行を確認するために使用されます。 [System.](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) .......................................................表示する内容を決定します。

  Setitem を呼び出すと、が[`true` 返されます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)その後、 [*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドは、を呼び出す必要があります。この場合、このメソッドは、 [System.](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) ........ このメソッドは、ユーザーにメッセージを送信して、操作を続行する必要があるかどうかを確認するフィードバックを許可します。 System.object を呼び出すと、危険性の高いシステム変更を追加で確認できるように[なります。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)

## <a name="retrieve-dynamic-parameters-for-clearitem"></a>ClearItem の動的パラメーターの取得

@No__t_0 コマンドレットでは、実行時に動的に指定される追加のパラメーターが必要になる場合があります。 これらの動的パラメーターを指定するには、Windows PowerShell 項目プロバイダーで、システムを実装する必要があります。 [Clearitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters)メソッド。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の Parameterdictionary と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。 [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムは、返されたオブジェクトを使用して、`Clear-Item` コマンドレットにパラメーターを追加します。

この項目プロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderclearitemdynamicparameters](Msh_samplestestcmdlets#testproviderclearitemdynamicparameters)]  -->

## <a name="performing-a-default-action-for-an-item"></a>項目の既定のアクションを実行する

Windows PowerShell 項目プロバイダーは、 [Invokedefaultaction *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)メソッドを実装して、プロバイダーがの既定のアクションを実行できるようにする、`Invoke-Item` コマンドレットからの呼び出しをサポートすることができます。指定されたパスにある項目。 たとえば、FileSystem プロバイダーは、このメソッドを使用して、特定の項目に対して ShellExecute を呼び出す場合があります。

このプロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinvokedefaultaction](Msh_samplestestcmdlets#testproviderinvokedefaultaction)]  -->

#### <a name="things-to-remember-about-implementing-invokedefaultaction"></a>InvokeDefaultAction の実装に関する注意事項

[Invokedefaultaction *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)の実装には、次の条件が適用される場合があります。

- プロバイダークラスを定義すると、Windows PowerShell 項目プロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。 このような場合は、 [Invokedefaultaction *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)の実装によって、メソッドに渡されるパスが要件を満たしていることを確認する必要があります。 これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...

- 既定では、このメソッドのオーバーライドでは、system.string [*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティが `true` に設定されていない限り、ユーザーに対して非表示のオブジェクトを設定または記述することはできません。 パスがユーザーと[WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError)の非表示になっている項目を表している場合は、このメソッドにエラーを送信する必要があります。 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)を使用して、* です。を `false` に設定します。

## <a name="retrieve-dynamic-parameters-for-invokedefaultaction"></a>InvokeDefaultAction の動的パラメーターの取得

@No__t_0 コマンドレットでは、実行時に動的に指定される追加のパラメーターが必要になる場合があります。 これらの動的パラメーターを指定するには、Windows PowerShell 項目プロバイダーでは、system.string [*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters)メソッドを実装する必要があります。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の Parameterdictionary と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。 [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムは、返されたオブジェクトを使用して、`Invoke-Item` コマンドレットに動的パラメーターを追加します。

この項目プロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinvokedefaultactiondynamicparameters](Msh_samplestestcmdlets#testproviderinvokedefaultactiondynamicparameters)]  -->

## <a name="implementing-helper-methods-and-classes"></a>ヘルパーメソッドとクラスの実装

この項目プロバイダーは、Windows PowerShell で定義されているパブリックオーバーライドメソッドによって使用されるいくつかのヘルパーメソッドとクラスを実装します。 これらのヘルパーメソッドとクラスのコードについては、「[コードサンプル](#code-sample)」セクションを参照してください。

### <a name="normalizepath-method"></a>NormalizePath メソッド

この項目プロバイダーは、パスが一貫した形式であることを保証するために、NormalizePath ヘルパーメソッドを実装します。 指定された形式では、区切り記号として円記号 (\\) を使用します。

### <a name="pathisdrive-method"></a>PathIsDrive メソッド

この項目プロバイダーは、PathIsDrive ヘルパーメソッドを実装して、指定されたパスが実際にドライブ名であるかどうかを判断します。

### <a name="chunkpath-method"></a>ChunkPath メソッド

この項目プロバイダーは、プロバイダーが個々の要素を識別できるように、指定されたパスを分割する ChunkPath ヘルパーメソッドを実装します。 パス要素で構成される配列を返します。

### <a name="gettable-method"></a>GetTable メソッド

この項目プロバイダーは、呼び出しで指定されたテーブルに関する情報を表すデータオブジェクトを返す、GetTables ヘルパーメソッドを実装します。

### <a name="getrow-method"></a>GetRow メソッド

この項目プロバイダーの system.servicemodel............... この[メソッドは、](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) GetRows ヘルパーメソッドを呼び出します。 このヘルパーメソッドは、テーブル内の指定された行に関する情報を表す DatabaseRowInfo オブジェクトを取得します。

### <a name="databasetableinfo-class"></a>"クラス"

この項目プロバイダーは、データベース内のデータテーブル内の情報のコレクションを表すデータセットを定義します。 このクラスは、 [Directoryinfo](/dotnet/api/System.IO.DirectoryInfo)クラスに似ています。

サンプル項目プロバイダーは、データベース内のテーブルを定義するテーブル情報オブジェクトのコレクションを返す、データセットメソッドを定義します。 このメソッドには try/catch ブロックが含まれており、すべてのデータベースエラーがエントリが0の行として表示されるようになっています。

### <a name="databaserowinfo-class"></a>DatabaseRowInfo クラス

このアイテムプロバイダーは、データベースのテーブルの行を表す DatabaseRowInfo helper クラスを定義します。 このクラス[は、system.servicemodel](/dotnet/api/System.IO.FileInfo)クラスに似ています。

サンプルプロバイダーは、指定されたテーブルの行情報オブジェクトのコレクションを返す DatabaseRowInfo メソッドを定義します。 このメソッドには、例外をトラップするための try/catch ブロックが含まれています。 エラーが発生すると、行情報は生成されません。

## <a name="code-sample"></a>コードサンプル

完全なサンプルコードについては、「 [AccessDbProviderSample03 のコードサンプル](./accessdbprovidersample03-code-sample.md)」を参照してください。

## <a name="defining-object-types-and-formatting"></a>オブジェクトの種類と書式設定の定義

プロバイダーを作成する場合は、既存のオブジェクトにメンバーを追加したり、新しいオブジェクトを定義したりすることが必要になる場合があります。 完了したら、Windows PowerShell がオブジェクトのメンバーを識別するために使用できる型ファイルと、オブジェクトの表示方法を定義するフォーマットファイルを作成します。 の詳細については、「[オブジェクトの種類と書式設定の拡張](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)」を参照してください。

## <a name="building-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーの構築

「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法」を](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)参照してください。

## <a name="testing-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーのテスト

この Windows PowerShell 項目プロバイダーが Windows PowerShell に登録されている場合、プロバイダーの基本およびドライブの機能のみをテストできます。 項目の操作をテストするには、「[コンテナーの Windows PowerShell プロバイダーの実装](./creating-a-windows-powershell-container-provider.md)」で説明されているコンテナー機能も実装する必要があります。

## <a name="see-also"></a>関連項目

[Windows PowerShell SDK](../windows-powershell-reference.md)

[Windows PowerShell プログラマーズガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell プロバイダーの作成](./how-to-create-a-windows-powershell-provider.md)

[Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)

[オブジェクトの種類と書式設定の拡張](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Windows PowerShell の動作](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[コンテナーの Windows PowerShell プロバイダーの作成](./creating-a-windows-powershell-container-provider.md)

[ドライブ Windows PowerShell プロバイダーの作成](./creating-a-windows-powershell-drive-provider.md)

[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)
