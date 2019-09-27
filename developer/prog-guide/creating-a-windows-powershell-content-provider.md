---
title: Windows PowerShell コンテンツプロバイダーを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- content providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], content provider
ms.assetid: 3da88ff9-c4c7-4ace-aa24-0a29c8cfa060
caps.latest.revision: 6
ms.openlocfilehash: a897ba29835e6f04ccacf3c4d7d8a1d43cedb91e
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71323210"
---
# <a name="creating-a-windows-powershell-content-provider"></a>Windows PowerShell コンテンツ プロバイダーを作成する

このトピックでは、ユーザーがデータストア内の項目の内容を操作できるようにする Windows PowerShell プロバイダーを作成する方法について説明します。 その結果、項目の内容を操作できるプロバイダーは、Windows PowerShell コンテンツプロバイダーと呼ばれます。

> [!NOTE]
> このプロバイダーのC#ソースファイル (AccessDBSampleProvider06.cs) をダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。 ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)」を参照してください。
>
> ダウンロードしたソースファイルは、  **\<PowerShell Samples >** ディレクトリにあります。
>
> その他の Windows PowerShell プロバイダーの実装の詳細については、「 [Windows Powershell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」を参照してください。

## <a name="define-the-windows-powershell-content-provider-class"></a>Windows PowerShell コンテンツプロバイダークラスを定義する

Windows PowerShell コンテンツプロバイダーは、 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイスをサポートする .net クラスを作成する必要があります。 ここでは、このセクションで説明する項目プロバイダーのクラス定義を示します。

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L32-L33 "AccessDBProviderSample06.cs")]

このクラス定義では、 [system.string 属性に2つのパラメーター](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)が含まれていることに注意してください。 最初のパラメーターは、Windows PowerShell によって使用されるプロバイダーのわかりやすい名前を指定します。 2番目のパラメーターは、コマンドの処理中にプロバイダーが Windows PowerShell ランタイムに公開する Windows PowerShell 固有の機能を指定します。 このプロバイダーには、Windows PowerShell 固有の機能は追加されていません。

## <a name="define-functionality-of-base-class"></a>基本クラスの機能を定義する

「 [Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」で説明されているように、さまざまなプロバイダーの機能を提供する他のいくつかのクラス[から、このクラスを](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)派生させることができます。 そのため、Windows PowerShell コンテンツプロバイダーは、通常、これらのクラスによって提供されるすべての機能を定義します。

セッション固有の初期化情報を追加したり、プロバイダーで使用されるリソースを解放したりするための機能を実装する方法の詳細については、「[基本的な Windows PowerShell プロバイダーの作成](./creating-a-basic-windows-powershell-provider.md)」を参照してください。 ただし、ここで説明するプロバイダーを含むほとんどのプロバイダーは、Windows PowerShell によって提供されるこの機能の既定の実装を使用できます。

データストアにアクセスするには、プロバイダーが[Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)基底クラスのメソッドを実装する必要があります。 これらのメソッドの実装の詳細については、「 [Windows PowerShell ドライブプロバイダーの作成](./creating-a-windows-powershell-drive-provider.md)」を参照してください。

項目の取得、設定、クリアなど、データストアの項目を操作するには、プロバイダー[が、system.object クラスの基本クラス](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)によって提供されるメソッドを実装する必要があります。 これらのメソッドの実装の詳細については、「 [Windows PowerShell 項目プロバイダーの作成](./creating-a-windows-powershell-item-provider.md)」を参照してください。

マルチレイヤーデータストアを操作するには、プロバイダーが[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)基底クラスによって提供されるメソッドを実装する必要があります。 これらのメソッドの実装の詳細については、「 [Windows PowerShell コンテナープロバイダーの作成](./creating-a-windows-powershell-container-provider.md)」を参照してください。

再帰コマンド、入れ子になったコンテナー、および相対パスをサポートするには、プロバイダー[が、system.servicemodel クラスの基底クラス](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)を実装する必要があります。 さらに、この Windows PowerShell コンテンツプロバイダーは、 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイスを、system.............. [navigationshell プロバイダー](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)基底クラスにアタッチできます。では、そのクラスによって提供されるメソッドを実装する必要があります。 詳細については、「これらのメソッドの実装」を参照してください。「[ナビゲーション Windows PowerShell プロバイダーの実装](./creating-a-windows-powershell-navigation-provider.md)」を参照してください。

## <a name="implementing-a-content-reader"></a>コンテンツリーダーの実装

項目からコンテンツを読み取るには、プロバイダーが[Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader)から派生したコンテンツリーダークラスを実装する必要があります。 このプロバイダーのコンテンツリーダーは、データテーブル内の行の内容にアクセスできるようにします。 コンテンツリーダークラスは、指定された行からデータを取得し、そのデータを表すリストを返す**Read**メソッドを定義します。また、コンテンツリーダーを移動する**Seek**メソッド、コンテンツリーダーを閉じる**Close**メソッド、および**Dispose**メソッド。

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L2115-L2241 "AccessDBProviderSample06.cs")]

## <a name="implementing-a-content-writer"></a>コンテンツライターの実装

コンテンツを項目に書き込むには、プロバイダーが[Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter)から派生したコンテンツライタークラスを実装する必要があります。 コンテンツライタークラスは、指定された行のコンテンツ、コンテンツライターを移動する**Seek**メソッド、コンテンツライターを閉じる**Close**メソッド、および**Dispose**メソッドを**記述する書き込み**メソッドを定義します。

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L2250-L2394 "AccessDBProviderSample06.cs")]

## <a name="retrieving-the-content-reader"></a>コンテンツリーダーを取得しています

項目からコンテンツを取得するには、プロバイダーが[Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)を実装して、 `Get-Content`コマンドレットをサポートする必要があります。 このメソッドは、指定されたパスにある項目のコンテンツリーダーを返します。 その後、リーダーオブジェクトを開いてコンテンツを読み取ることができます。

ここでは、このプロバイダーのこのメソッドの[Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)の実装を示していますが、

```csharp
public IContentReader GetContentReader(string path)
{
    string tableName;
    int rowNumber;

    PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

    if (type == PathType.Invalid)
    {
        ThrowTerminatingInvalidPathException(path);
    }
    else if (type == PathType.Row)
    {
        throw new InvalidOperationException("contents can be obtained only for tables");
    }

    return new AccessDBContentReader(path, this);
} // GetContentReader
```

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1829-L1846 "AccessDBProviderSample06.cs")]

#### <a name="things-to-remember-about-implementing-getcontentreader"></a>GetContentReader の実装に関する注意事項

[Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)の実装には、次の条件が適用される場合があります。

- プロバイダークラスを定義すると、Windows PowerShell コンテンツプロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。 このような場合は、 [Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)メソッドを実装することで、メソッドに渡されるパスが指定された機能の要件を満たしていることを確認する必要があります。 これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...

- 既定では、このメソッドをオーバーライドしても、ユーザーに表示されないオブジェクトのリーダーを取得することはできません。この場合、 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティがに`true`設定されている必要があります。 パスが、ユーザーおよびシステムから非表示になっている項目を表している場合は、エラーを書き込む必要があります。 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)をに`false`設定します。

## <a name="attaching-dynamic-parameters-to-the-get-content-cmdlet"></a>Get Content コマンドレットに動的パラメーターをアタッチする

コマンド`Get-Content`レットでは、実行時に動的に指定される追加のパラメーターが必要になる場合があります。 これらの動的なパラメーターを提供するには、Windows PowerShell コンテンツプロバイダーが[Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters)メソッドを実装する必要があります。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の[Parameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。素材. Windows PowerShell ランタイムは、返されたオブジェクトを使用して、コマンドレットにパラメーターを追加します。

この Windows PowerShell コンテナープロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

```csharp
public object GetContentReaderDynamicParameters(string path)
{
    return null;
}
```

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1853-L1856 "AccessDBProviderSample06.cs")]

## <a name="retrieving-the-content-writer"></a>コンテンツライターを取得する

コンテンツを項目に書き込むには、プロバイダーが[Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)を実装して、コマンドレット`Set-Content`と`Add-Content`コマンドレットをサポートする必要があります。 このメソッドは、指定されたパスにある項目のコンテンツライターを返します。

ここでは、このメソッドの[Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)の実装を示して説明します。

```csharp
public IContentWriter GetContentWriter(string path)
{
    string tableName;
    int rowNumber;

    PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

    if (type == PathType.Invalid)
    {
        ThrowTerminatingInvalidPathException(path);
    }
    else if (type == PathType.Row)
    {
        throw new InvalidOperationException("contents can be added only to tables");
    }

    return new AccessDBContentWriter(path, this);
}
```

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1863-L1880 "AccessDBProviderSample06.cs")]

#### <a name="things-to-remember-about-implementing-getcontentwriter"></a>GetContentWriter の実装に関する注意事項

[Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)の実装には、次の条件が当てはまる場合があります:。

- プロバイダークラスを定義すると、Windows PowerShell コンテンツプロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。 このような場合は、 [Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)メソッドを実装することで、メソッドに渡されるパスが指定された機能の要件を満たしていることを確認する必要があります。 これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...

- 既定では、このメソッドのオーバーライドでは、ユーザーに表示されないオブジェクトのライターを取得しないでください。この場合、 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティがに`true`設定されている必要があります。 パスが、ユーザーおよびシステムから非表示になっている項目を表している場合は、エラーを書き込む必要があります。 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)をに`false`設定します。

## <a name="attaching-dynamic-parameters-to-the-add-content-and-set-content-cmdlets"></a>コンテンツの追加とコンテンツの設定コマンドレットへの動的パラメーターのアタッチ

`Add-Content` および`Set-Content`コマンドレットには、ランタイムを追加する追加の動的パラメーターが必要な場合があります。 これらの動的パラメーターを指定するには、Windows PowerShell コンテンツプロバイダーは、これらのパラメーターを処理するために[Icontentcmdletprovider * Getcontentwriterdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters)メソッドを実装する必要があります。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の[Parameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。素材. Windows PowerShell ランタイムは、返されたオブジェクトを使用して、コマンドレットにパラメーターを追加します。

この Windows PowerShell コンテナープロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1887-L1890 "AccessDBProviderSample06.cs")]

## <a name="clearing-content"></a>コンテンツのクリア

コンテンツプロバイダーは、 `Clear-Content`コマンドレットをサポートするために[Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドを実装しています。 このメソッドは、指定されたパスにある項目の内容を削除しますが、項目はそのまま残ります。

次に示すのは、このプロバイダーの[Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドの実装を示しています。

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1775-L1812 "AccessDBProviderSample06.cs")]

#### <a name="things-to-remember-about-implementing-clearcontent"></a>ClearContent の実装に関する注意事項

[Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)の実装には、次の条件が当てはまる場合があります。

- プロバイダークラスを定義すると、Windows PowerShell コンテンツプロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。 このような場合は、 [Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドを実装することで、メソッドに渡されるパスが指定された機能の要件を満たしていることを確認する必要があります。 これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...

- 既定では、このメソッドをオーバーライドしても、ユーザーに表示されないオブジェクトの内容を消去することはできません。ただし、 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティがに`true`設定されている必要があります。 パスが、ユーザーおよびシステムから非表示になっている項目を表している場合は、エラーを書き込む必要があります。 [Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)をに`false`設定します。

- [Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドを実装するには、system.object を呼び出して、戻り値を確認する必要があります。このメソッドの戻り値を確認し[ます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)データストアに変更を加える前。 このメソッドは、コンテンツのクリアなど、データストアに変更が加えられたときの操作の実行を確認するために使用されます。 [System.](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) ................................................................表示する内容を決定します。

  [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)を呼び出すと、が返さ`true`れます。その[ためには](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)、「」という[メソッドを呼び出す必要があります。この場合、System.](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) ........ このメソッドは、ユーザーにメッセージを送信して、操作を続行する必要があるかどうかを確認するフィードバックを許可します。 System.object を呼び出すと、危険性の高いシステム変更を追加で確認できるように[なります。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)

## <a name="attaching-dynamic-parameters-to-the-clear-content-cmdlet"></a>Clear Content コマンドレットへの動的パラメーターのアタッチ

コマンド`Clear-Content`レットには、実行時に追加される追加の動的パラメーターが必要な場合があります。 これらの動的パラメーターを指定するには、Windows PowerShell コンテンツプロバイダーは、これらのパラメーターを処理するために[Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters)メソッドを実装する必要があります。 このメソッドは、指定されたパスにある項目のパラメーターを取得します。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の[Parameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。素材. Windows PowerShell ランタイムは、返されたオブジェクトを使用して、コマンドレットにパラメーターを追加します。

この Windows PowerShell コンテナープロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

```csharp
public object ClearContentDynamicParameters(string path)
{
    return null;
}
```

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1819-L1822 "AccessDBProviderSample06.cs")]

## <a name="code-sample"></a>コードサンプル

完全なサンプルコードについては、「 [AccessDbProviderSample06 のコードサンプル](./accessdbprovidersample06-code-sample.md)」を参照してください。

## <a name="defining-object-types-and-formatting"></a>オブジェクトの種類と書式設定の定義

プロバイダーを作成する場合は、既存のオブジェクトにメンバーを追加したり、新しいオブジェクトを定義したりすることが必要になる場合があります。 この処理が完了したら、オブジェクトのメンバーを識別するために Windows PowerShell で使用できる型ファイルと、オブジェクトの表示方法を定義するフォーマットファイルを作成する必要があります。 詳細については、「[オブジェクトの種類と書式設定の拡張](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)」を参照してください。

## <a name="building-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーの構築

「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法」を](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)参照してください。

## <a name="testing-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーのテスト

Windows powershell プロバイダーが Windows PowerShell に登録されている場合は、コマンドラインでサポートされているコマンドレットを実行してテストできます。 たとえば、サンプルコンテンツプロバイダーをテストします。

コマンドレットを使用し`Path`て、パラメーターで指定されたパスにあるデータベーステーブル内の指定された項目の内容を取得します。 `Get-Content` パラメーター `ReadCount`は、定義されたコンテンツリーダーが読み取る項目の数を指定します (既定値は 1)。 次のコマンドを入力すると、コマンドレットはテーブルから2つの行 (項目) を取得し、その内容を表示します。 次の出力例では、架空の Access データベースが使用されていることに注意してください。

```powershell
Get-Content -Path mydb:\Customers -ReadCount 2
```

```output
ID        : 1
FirstName : Eric
LastName  : Gruber
Email     : ericgruber@fabrikam.com
Title     : President
Company   : Fabrikam
WorkPhone : (425) 555-0100
Address   : 4567 Main Street
City      : Buffalo
State     : NY
Zip       : 98052
Country   : USA
ID        : 2
FirstName : Eva
LastName  : Corets
Email     : evacorets@cohowinery.com
Title     : Sales Representative
Company   : Coho Winery
WorkPhone : (360) 555-0100
Address   : 8910 Main Street
City      : Cabmerlot
State     : WA
Zip       : 98089
Country   : USA
```

## <a name="see-also"></a>関連項目

[Windows PowerShell プロバイダーの作成](./how-to-create-a-windows-powershell-provider.md)

[Windows PowerShell プロバイダーを設計する](./designing-your-windows-powershell-provider.md)

[オブジェクトの種類と書式設定の拡張](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[ナビゲーション Windows PowerShell プロバイダーを実装する](./creating-a-windows-powershell-navigation-provider.md)

[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Windows PowerShell SDK](../windows-powershell-reference.md)

[Windows PowerShell プログラマーズガイド](./windows-powershell-programmer-s-guide.md)
