---
title: Windows PowerShell コンテンツ プロバイダーを作成する |Microsoft Docs
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
ms.openlocfilehash: 6e5d79487539d4f58922e2686f1fdba08797f305
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855308"
---
# <a name="creating-a-windows-powershell-content-provider"></a>Windows PowerShell コンテンツ プロバイダーを作成する

このトピックでは、データ ストア内の項目の内容を操作するユーザーを有効にする Windows PowerShell プロバイダーを作成する方法について説明します。 その結果、項目の内容を操作できるプロバイダーは Windows PowerShell コンテンツ プロバイダーとしてに呼ばれます。

> [!NOTE]
> ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と .NET Framework 3.0 ランタイム コンポーネントを使用して、このプロバイダーのソース ファイル (AccessDBSampleProvider06.cs)。 ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。
> ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と .NET Framework 3.0 ランタイム コンポーネントを使用して、このプロバイダーのソース ファイル (AccessDBSampleProvider06.cs)。 ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。
>
> ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。
>
> その他の Windows PowerShell プロバイダーの実装の詳細については、次を参照してください。 [Your Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)します。

次の一覧には、このトピックのセクションが含まれています。 Windows PowerShell コンテンツ プロバイダーの作成に慣れていない場合は、出現する順序でこれらのセクションを参照します。 ただし、Windows PowerShell コンテンツ プロバイダーの作成に習熟する場合は、必要な情報に直接移動します。

- [Windows PowerShell コンテンツ プロバイダー クラスを定義します。](#Define-the-Windows-PowerShell-Content-Provider-Class)

- [基本機能を定義します。](#Define-Functionality-of-Base-Class)

- [コンテンツのリーダーの実装](#Implementing-a-Content-Reader)

- [コンテンツのライターの実装](#Implementing-a-Content-Writer)

- [コンテンツのリーダーを取得します。](#Retrieving-the-Content-Reader)

- [動的パラメーターをアタッチ、`Get-Content`コマンドレット](#Attaching-Dynamic-Parameters-to-the-Get-Content-Cmdlet)

- [コンテンツのライターを取得します。](#Retrieving-the-Content-Writer)

- [動的パラメーター、Add_Content をアタッチし、`Set-Content`コマンドレット](#Attaching-Dynamic-Parameters-to-the-Add-Content-and-Set-Content-Cmdlets)

- [コンテンツをクリアします。](#Clearing-Content)

- [動的パラメーターをアタッチ、`Clear-Content`コマンドレット](#Attaching-Dynamic-Parameters-to-the-Clear-Content-Cmdlet)

- [コード サンプル](#Code-Sample)

- [オブジェクトの種類を定義して、書式設定]()

- [Windows PowerShell プロバイダーの構築](#Building-the-Windows-PowerShell-Provider)

- [Windows PowerShell プロバイダーのテスト](#Testing-the-Windows-PowerShell-Provider)

## <a name="define-the-windows-powershell-content-provider-class"></a>Windows PowerShell コンテンツ プロバイダー クラスを定義します。

Windows PowerShell コンテンツ プロバイダーがサポートする .NET クラスを作成する必要があります、 [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイス。 このセクションで説明されている項目プロバイダーのクラス定義を次に示します。

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L32-L33 "AccessDBProviderSample06.cs")]

このクラス定義を[System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)属性には、2 つのパラメーターが含まれています。 最初のパラメーターには、Windows PowerShell で使用されるプロバイダーのわかりやすい名前を指定します。 2 番目のパラメーターには、プロバイダーがコマンドの処理中に、Windows PowerShell ランタイムに公開する Windows PowerShell の特定機能を指定します。 このプロバイダーでは、追加した Windows PowerShell の特定の機能はありません。

## <a name="define-functionality-of-base-class"></a>基底クラスの機能を定義します。

」の説明に従って[デザイン、Windows PowerShell プロバイダー](./designing-your-windows-powershell-provider.md)、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスが提供されるその他のいくつかのクラスから派生別のプロバイダー機能。 Windows PowerShell コンテンツ プロバイダーでは、そのため、通常定義のすべてのこれらのクラスによって提供される機能します。

セッション固有の初期化情報を追加して、プロバイダーによって使用されているリソースを解放するための機能を実装する方法の詳細については、次を参照してください。[基本的な Windows PowerShell プロバイダーを作成する](./creating-a-basic-windows-powershell-provider.md)します。 ただし、ここでは、説明されているプロバイダーを含む、ほとんどのプロバイダーは、この Windows PowerShell によって提供される機能の既定の実装を使用できます。

データ ストアにアクセスするには、プロバイダーがのメソッドを実装する必要があります、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)基本クラス。 これらのメソッドの実装の詳細については、次を参照してください。 [Windows PowerShell ドライブ プロバイダーを作成する](./creating-a-windows-powershell-drive-provider.md)します。

プロバイダーの取得、設定、および消去の項目などのデータ ストアの項目を操作するによって提供されるメソッドを実装する必要があります、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)基本クラス。 これらのメソッドの実装の詳細については、次を参照してください。 [Windows PowerShell 項目プロバイダーを作成する](./creating-a-windows-powershell-item-provider.md)します。

プロバイダーを複数レイヤーのデータ ストアを操作するによって提供されるメソッドを実装する必要があります、 [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)基本クラス。 これらのメソッドの実装の詳細については、次を参照してください。 [Windows PowerShell コンテナー プロバイダーを作成する](./creating-a-windows-powershell-container-provider.md)します。

再帰的なコマンド、入れ子になったコンテナーは、相対パスをサポートするプロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)基本クラス。 この Windows PowerShell コンテンツ プロバイダーの接続はさらに、 [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)へのインターフェイス、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)基本クラス、および、したがって、そのクラスによって提供されるメソッドを実装する必要があります。 詳細については、これらのメソッドの実装を参照してくださいを参照してください[ナビゲーションの Windows PowerShell プロバイダーを実装する](./creating-a-windows-powershell-navigation-provider.md)します。

## <a name="implementing-a-content-reader"></a>コンテンツのリーダーの実装

項目からコンテンツを読み取る、プロバイダーがから派生したコンテンツのリーダー クラスを実装する必要があります[System.Management.Automation.Provider.Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader)します。 このプロバイダーのコンテンツのリーダーは、データ テーブルの行の内容にアクセスを許可します。 コンテンツのリーダー クラスを定義、**読み取り**メソッドを指定された行からデータを取得し、そのデータを表すリストを返します、**シーク**コンテンツのリーダーを移動する方法、 **閉じる**メソッドをコンテンツのリーダーを閉じると、 **Dispose**メソッド。

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L2115-L2241 "AccessDBProviderSample06.cs")]

## <a name="implementing-a-content-writer"></a>コンテンツのライターの実装

コンテンツは、項目を書き込む、プロバイダーが、コンテンツを実装する必要がありますライター クラスから派生[System.Management.Automation.Provider.Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter)します。 コンテンツ ライター クラスを定義、**書き込み**指定した行の内容を書き込むメソッドを**シーク**コンテンツのライターを移動する方法、**閉じる**を閉じる方法、コンテンツのライター、 **Dispose**メソッド。

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L2250-L2394 "AccessDBProviderSample06.cs")]

## <a name="retrieving-the-content-reader"></a>コンテンツのリーダーを取得します。

項目からコンテンツを取得するプロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)サポートするために、`Get-Content`コマンドレット。 このメソッドは、指定されたパスにある項目のコンテンツのリーダーを返します。 リーダー オブジェクトは、コンテンツの読み取り開くことができます。

実装を次に示します[System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)このプロバイダーは、このメソッドにします。

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

#### <a name="things-to-remember-about-implementing-getcontentreader"></a>GetContentReader の実装に関する注意点

実装を次の条件が適用[System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader):

- Windows PowerShell コンテンツ プロバイダーがから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言可能性があります、プロバイダー クラスを定義するときに、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これらのケースの実装で、 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)メソッドがメソッドに渡されたパスが指定した要件を満たしていることを確認する必要があります機能。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)と[System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)プロパティ。

- 既定では、このメソッドのオーバーライドを取得しないようにしない限り、ユーザーが非表示オブジェクト用のリーダー、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティに設定されて`true`します。 パスが、ユーザーが非表示の項目を表すかどうかエラーを記述する必要がありますと[System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)に設定されている`false`します。

## <a name="attaching-dynamic-parameters-to-the-get-content-cmdlet"></a>動的パラメーター、Get-content コマンドレットをアタッチ

`Get-Content`コマンドレットは、実行時に動的に指定されている追加のパラメーターを必要があります。 これらの動的パラメーターを提供する Windows PowerShell コンテンツ プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreaderdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters)メソッド。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムでは、返されたオブジェクトを使用して、パラメーターをコマンドレットに追加します。

この Windows PowerShell コンテナー プロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

```csharp
public object GetContentReaderDynamicParameters(string path)
{
    return null;
}
```

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1853-L1856 "AccessDBProviderSample06.cs")]

## <a name="retrieving-the-content-writer"></a>コンテンツのライターを取得します。

コンテンツは、項目を書き込む、プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)サポートするために、`Set-Content`と`Add-Content`コマンドレット。 このメソッドは、指定されたパスにある項目のコンテンツのライターを返します。

実装を次に示します[System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)このメソッドにします。

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

#### <a name="things-to-remember-about-implementing-getcontentwriter"></a>GetContentWriter の実装に関する注意点

実装に、次の条件が適用[System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter):

- Windows PowerShell コンテンツ プロバイダーがから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言可能性があります、プロバイダー クラスを定義するときに、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これらのケースの実装で、 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)メソッドがメソッドに渡されたパスが指定した要件を満たしていることを確認する必要があります機能。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)と[System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)プロパティ。

- 既定では、このメソッドのオーバーライドを取得しないように、しない限り、ユーザーが非表示オブジェクトのライター、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティに設定されて`true`します。 パスが、ユーザーが非表示の項目を表すかどうかエラーを記述する必要がありますと[System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)に設定されている`false`します。

## <a name="attaching-dynamic-parameters-to-the-add-content-and-set-content-cmdlets"></a>動的パラメーター、Add-content、Set-content コマンドレットをアタッチ

`Add-Content`と`Set-Content`コマンドレットは、ランタイムに追加される追加の動的パラメーターを必要があります。 これらの動的パラメーターを提供する Windows PowerShell コンテンツ プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriterdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters)これらを処理するメソッドパラメーター。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムでは、返されたオブジェクトを使用して、パラメーターをコマンドレットに追加します。

この Windows PowerShell コンテナー プロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1887-L1890 "AccessDBProviderSample06.cs")]

## <a name="clearing-content"></a>コンテンツをクリアします。

コンテンツ プロバイダーの実装、 [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドのサポート、`Clear-Content`コマンドレット。 このメソッドは、指定したパスにある項目の内容を削除しますが、項目をそのまま残されます。

実装をここでは、 [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)このプロバイダーのメソッド。

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1775-L1812 "AccessDBProviderSample06.cs")]

#### <a name="things-to-remember-about-implementing-clearcontent"></a>ClearContent の実装に関する注意点

実装を次の条件が適用[System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent):

- Windows PowerShell コンテンツ プロバイダーがから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言可能性があります、プロバイダー クラスを定義するときに、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これらのケースの実装で、 [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドがメソッドに渡されたパスが指定した要件を満たしていることを確認する必要があります機能。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)と[System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)プロパティ。

- 既定では、このメソッドのオーバーライドする必要がありますいないをオフにしない限り、ユーザーが非表示オブジェクトの内容、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティに設定されて`true`します。 パスが、ユーザーが非表示の項目を表すかどうかエラーを記述する必要がありますと[System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)に設定されている`false`します。

- 実装、 [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドを呼び出す必要があります[System.Management.Automation.Provider.Cmdletprovider.Shouldprocess*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)をデータ ストアに変更を加える前に、その戻り値を確認します。 このメソッドは、コンテンツをクリアするなど、データ ストアに変更が行われる操作の実行の確認に使用されます。 [System.Management.Automation.Provider.Cmdletprovider.Shouldprocess*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)メソッドは、任意のコマンドライン設定や基本設定処理の Windows PowerShell ランタイムと、ユーザーに変更するリソースの名前を送信します。何を表示するかを決定するのには変数。

  呼び出し後[System.Management.Automation.Provider.Cmdletprovider.Shouldprocess*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)返します`true`、 [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドを呼び出す必要があります、 [System.Management.Automation.Provider.Cmdletprovider.Shouldcontinue*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)メソッド。 このメソッドは、ユーザーにフィードバックするかどうかは、操作を続行することを確認できるようにメッセージを送信します。 呼び出し[System.Management.Automation.Provider.Cmdletprovider.Shouldcontinue*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)危険性のあるシステムの変更、追加のチェックを許可します。

## <a name="attaching-dynamic-parameters-to-the-clear-content-cmdlet"></a>Clear-content コマンドレットへの動的パラメーター

`Clear-Content`コマンドレットは、実行時に追加される追加の動的パラメーターを必要があります。 これらの動的パラメーターを提供する Windows PowerShell コンテンツ プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontentdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters)これらを処理するメソッドパラメーター。 このメソッドは、指定されたパスにある項目のパラメーターを取得します。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムでは、返されたオブジェクトを使用して、パラメーターをコマンドレットに追加します。

この Windows PowerShell コンテナー プロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

```csharp
public object ClearContentDynamicParameters(string path)
{
    return null;
}
```

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1819-L1822 "AccessDBProviderSample06.cs")]

## <a name="code-sample"></a>コード サンプル

完全なサンプル コードでは、次を参照してください。 [AccessDbProviderSample06 コード サンプル](./accessdbprovidersample06-code-sample.md)します。

## <a name="defining-object-types-and-formatting"></a>オブジェクトの種類を定義して、書式設定

プロバイダーを記述する場合は、既存のオブジェクトにメンバーを追加または新しいオブジェクトを定義する必要があります。 これが完了したら、Windows PowerShell がオブジェクトのメンバーを識別するために使用できる種類のファイルと、オブジェクトの表示方法を定義するフォーマット ファイルを作成する必要があります。 詳細については、次を参照してください。[を拡張するオブジェクトの種類と書式](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)します。
プロバイダーを記述する場合は、既存のオブジェクトにメンバーを追加または新しいオブジェクトを定義する必要があります。 これが完了したら、Windows PowerShell がオブジェクトのメンバーを識別するために使用できる種類のファイルと、オブジェクトの表示方法を定義するフォーマット ファイルを作成する必要があります。 詳細については、次を参照してください。[を拡張するオブジェクトの種類と書式](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)します。

## <a name="building-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーのビルド

参照してください[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。
参照してください[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。

## <a name="testing-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーのテスト

Windows PowerShell を使用した、Windows PowerShell プロバイダーを登録しているときに、コマンドラインでサポートされているコマンドレットを実行してテストできます。 たとえば、サンプルのコンテンツ プロバイダーをテストします。

使用して、`Get-Content`によって指定されたパスにデータベース テーブル内の指定項目の内容を取得するコマンドレット、`Path`パラメーター。 `ReadCount`パラメーター (既定値は 1) の読み取りに定義されているコンテンツのリーダーの項目の数を指定します。 次のコマンドのエントリは、このコマンドレットは、テーブルから 2 つの行 (アイテム) を取得し、その内容を表示します。 次の出力例は架空の Access データベースに注意してください。

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

## <a name="see-also"></a>参照

[Windows PowerShell プロバイダーを作成します。](./how-to-create-a-windows-powershell-provider.md)

[デザイン、Windows PowerShell プロバイダー](./designing-your-windows-powershell-provider.md)

[オブジェクトの種類を拡張して、書式設定](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[オブジェクトの種類を拡張して、書式設定](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[ナビゲーションの Windows PowerShell プロバイダーを実装します。](./creating-a-windows-powershell-navigation-provider.md)

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Windows PowerShell SDK](../windows-powershell-reference.md)

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)
