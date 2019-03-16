---
title: Windows PowerShell コンテナー プロバイダーを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- providers [PowerShell Programmer's Guide], container provider
- container providers [PowerShell Programmer's Guide]
ms.assetid: a7926647-0d18-45b2-967e-b31f92004bc4
caps.latest.revision: 5
ms.openlocfilehash: 33effed9a96cf1b9ee5f1a50b60a1937526db9d1
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055021"
---
# <a name="creating-a-windows-powershell-container-provider"></a>Windows PowerShell コンテナー プロバイダーを作成する

このトピックでは、複数レイヤーのデータ ストアで動作する Windows PowerShell プロバイダーを作成する方法について説明します。 この種類のデータ ストアでのストアの最上位レベルには、ルート項目が含まれています。 と後続の各レベルは子項目のノードと呼ばれます。 これらの子ノードで作業するユーザーを許可すると、ユーザーから操作できる階層的に、データ ストア。

複数レベルのデータ ストアで動作するプロバイダーは、Windows PowerShell コンテナー プロバイダーと呼ばれます。 ただし、内の項目を含む 1 つのコンテナー (入れ子になったコンテナーがありません) がある場合にのみ、Windows PowerShell コンテナー プロバイダーを使用できることもあります。 入れ子になったコンテナーがある場合は、Windows PowerShell ナビゲーション プロバイダーを実装する必要があります。 Windows PowerShell ナビゲーション プロバイダーの実装の詳細については、次を参照してください。 [Windows PowerShell ナビゲーション プロバイダーを作成する](./creating-a-windows-powershell-navigation-provider.md)します。

> [!NOTE]
> ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と .NET Framework 3.0 ランタイム コンポーネントを使用して、このプロバイダーのソース ファイル (AccessDBSampleProvider04.cs)。 ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。
>
> ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。
>
> その他の Windows PowerShell プロバイダーの実装の詳細については、次を参照してください。 [Your Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)します。

ここで説明する Windows PowerShell コンテナー プロバイダーでは、テーブルと、コンテナーの項目として定義されているデータベースの行の 1 つのコンテナーとして、データベースを定義します。

> [!CAUTION]
> 注意この設計が、名前の ID を持つフィールドを持つデータベースを想定していると、フィールドの型がなければなりません。

このトピックのセクションの一覧を示します。 Windows PowerShell コンテナー プロバイダーの記述に慣れていない場合は、出現する順序では、この情報をお読みください。 ただし、Windows PowerShell コンテナー プロバイダーの作成に習熟する場合は、直接」に進んでください必要な情報。

- [Windows PowerShell コンテナー プロバイダー クラスを定義します。](#Defining-a-Windows-PowerShell-Container-Provider-Class)

- [基本機能を定義します。](#defining-base-functionality)

- [子項目を取得します。](#Retrieving-Child-Items)

- [動的パラメーターをアタッチ、`Get-ChildItem`コマンドレット](#Attaching-Dynamic-Parameters-to-the-Get-ChildItem-Cmdlet)

- [子項目の名前を取得します。](#Retrieving-Child-Item-Names)

- [動的パラメーターをアタッチ、`Get-ChildItem`コマンドレット (名)](#Attaching-Dynamic-Parameters-to-the-Get-ChildItem-Cmdlet-(Name))

- [項目の名前を変更します。](#Renaming-Items)

- [動的パラメーターをアタッチ、`Rename-Item`コマンドレット](#Attaching-Dynamic-Parameters-to-the-Rename-Item-Cmdlet)

- [新しい項目の作成](#Creating-New-Items)

- [動的パラメーターをアタッチ、`New-Item`コマンドレット](#Attaching-Dynamic-Parameters-to-the-New-Item-Cmdlet)

- [項目を削除します。](#Removing-Items)

- [動的パラメーターをアタッチ、`Remove-Item`コマンドレット](#Attaching-Dynamic-Parameters-to-the-Remove-Item-Cmdlet)

- [子項目のクエリを実行します。](#Querying-for-Child-Items)

- [コピー項目](#Copying-Items)

- [動的パラメーターをアタッチ、`Copy-Item`コマンドレット](#Attaching-Dynamic-Parameters-to-the-Copy-Item-Cmdlet)

- [コード サンプル](#Code-Sample)

- [Windows PowerShell プロバイダーのビルド](#Building-the-Windows-PowerShell-Provider)

- [Windows PowerShell プロバイダーのテスト](#Testing-the-Windows-PowerShell-Provider)

## <a name="defining-a-windows-powershell-container-provider-class"></a>Windows PowerShell コンテナー プロバイダー クラスを定義します。

Windows PowerShell コンテナー プロバイダーがから派生する .NET クラスを定義する必要があります、 [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)基本クラス。 このセクションで説明されている Windows PowerShell コンテナー プロバイダーのクラス定義を次に示します。

```csharp
   [CmdletProvider("AccessDB", ProviderCapabilities.None)]
   public class AccessDBProvider : ContainerCmdletProvider
```

[!code-csharp[AccessDBProviderSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L34-L35 "AccessDBProviderSample04.cs")]

このクラスの定義に注意してください、 [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)属性には、2 つのパラメーターが含まれています。 最初のパラメーターには、Windows PowerShell で使用されるプロバイダーのわかりやすい名前を指定します。 2 番目のパラメーターには、プロバイダーがコマンドの処理中に、Windows PowerShell ランタイムに公開する Windows PowerShell の特定機能を指定します。 このプロバイダーに追加される Windows PowerShell の特定の機能はありません。

## <a name="defining-base-functionality"></a>基本機能を定義します。

」の説明に従って[Your Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)、 [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスが提供されるその他のいくつかのクラスから派生別のプロバイダー機能。 そのため、Windows PowerShell コンテナー プロバイダーは、これらのクラスによって提供される機能のすべてを定義する必要があります。

セッション固有の初期化情報を追加して、プロバイダーによって使用されているリソースを解放するための機能を実装するを参照してください。[基本的な Windows PowerShell プロバイダーを作成する](./creating-a-basic-windows-powershell-provider.md)します。 ただし、ほとんどのプロバイダー (ここで説明されているプロバイダーを含む) は、この Windows PowerShell によって提供される機能の既定の実装を使用できます。

データ ストアへのアクセスを取得するには、プロバイダーがのメソッドを実装する必要があります、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)基本クラス。 これらのメソッドの実装の詳細については、次を参照してください。 [Windows PowerShell ドライブ プロバイダーの作成](./creating-a-windows-powershell-drive-provider.md)です。

プロバイダーの取得、設定、および消去の項目などのデータ ストアの項目を操作するによって提供されるメソッドを実装する必要があります、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)基本クラス。 これらのメソッドの実装の詳細については、次を参照してください。 [Windows PowerShell 項目プロバイダーを作成する](./creating-a-windows-powershell-item-provider.md)します。

## <a name="retrieving-child-items"></a>子項目を取得します。

子項目を取得する、Windows PowerShell コンテナー プロバイダーがオーバーライドする必要があります、 [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドからの呼び出しをサポートするために、`Get-ChildItem`コマンドレット。 このメソッドは、子項目をデータ ストアから取得し、それらをパイプラインにオブジェクトとして書き込みます。 場合、`recurse`コマンドレットのパラメーターを指定すると、メソッドにはどのようなレベルに関係なくすべての子を取得します。 場合、`recurse`パラメーターが指定されていない、メソッドは、子の 1 つのレベルのみを取得します。

実装をここでは、 [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)このプロバイダーのメソッド。 パスが、Access データベースに示しパスには、データ テーブルが示されている場合、そのテーブルの行から子項目を取得ときに、このメソッドがすべてのデータベース テーブル内の子項目を取得することを確認します。

```csharp
protected override void GetChildItems(string path, bool recurse)
{
    // If path represented is a drive then the children in the path are
    // tables. Hence all tables in the drive represented will have to be
    // returned
    if (PathIsDrive(path))
    {
        foreach (DatabaseTableInfo table in GetTables())
        {
            WriteItemObject(table, path, true);

            // if the specified item exists and recurse has been set then
            // all child items within it have to be obtained as well
            if (ItemExists(path) && recurse)
            {
                GetChildItems(path + pathSeparator + table.Name, recurse);
            }
        } // foreach (DatabaseTableInfo...
    } // if (PathIsDrive...
    else
    {
        // Get the table name, row number and type of path from the
        // path specified
        string tableName;
        int rowNumber;

        PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

        if (type == PathType.Table)
        {
            // Obtain all the rows within the table
            foreach (DatabaseRowInfo row in GetRows(tableName))
            {
                WriteItemObject(row, path + pathSeparator + row.RowNumber,
                        false);
            } // foreach (DatabaseRowInfo...
        }
        else if (type == PathType.Row)
        {
            // In this case the user has directly specified a row, hence
            // just give that particular row
            DatabaseRowInfo row = GetRow(tableName, rowNumber);
            WriteItemObject(row, path + pathSeparator + row.RowNumber,
                        false);
        }
        else
        {
            // In this case, the path specified is not valid
            ThrowTerminatingInvalidPathException(path);
        }
    } // else
} // GetChildItems
```

[!code-csharp[AccessDBProviderSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L311-L362 "AccessDBProviderSample04.cs")]

#### <a name="things-to-remember-about-implementing-getchilditems"></a>GetChildItems の実装に関する注意点

実装に、次の条件が適用[System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems):

- Windows PowerShell コンテナー プロバイダーがから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言可能性があります、プロバイダー クラスを定義するときに、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これらのケースの実装で、 [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドは、メソッドに渡されるパスが指定した要件を満たしていることを確認する必要があります機能。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)と[System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)プロパティ。

- このメソッドの実装する必要があります考慮に入れて任意の形式のアクセスをユーザーに表示される項目を使用する項目にします。 たとえば、ユーザーが (Windows PowerShell によって提供される)、FileSystem プロバイダーが読み取りアクセスは含まれません経由でファイルを書き込みアクセス権を持っている場合、ファイルが存在し、 [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)返します`true`します。 実装では、子を列挙できるかどうかに表示する親項目のチェックを必要があります。

- 複数の項目を作成するとき、 [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドは時間がかかることができます。 使用して項目を作成するには、プロバイダーを設計することができます、 [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject)一度に 1 つのメソッド。 この手法を使用すると、ストリーム内のユーザーに項目が表示されます。

- 実装[System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)循環リンクは、およびなどがある場合は、無限再帰を回避するため責任を負います。 そうした状態を反映するように適切な終了例外をスローする必要があります。

## <a name="attaching-dynamic-parameters-to-the-get-childitem-cmdlet"></a>Get-childitem コマンドレットに動的パラメーターを追加

場合によって、`Get-ChildItem`コマンドレットを呼び出す[System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)実行時に動的に指定されている追加のパラメーターが必要です。 これらの動的パラメーターを提供する、Windows PowerShell コンテナー プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Containercmdletprovider.Getchilditemsdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters)メソッド。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムでは、返されたオブジェクトを使用して、パラメーターを追加、`Get-ChildItem`コマンドレット。

この Windows PowerShell コンテナー プロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchilditemsdynamicparameters](Msh_samplestestcmdlets#testprovidergetchilditemsdynamicparameters)]  -->

## <a name="retrieving-child-item-names"></a>子項目の名前を取得します。

子項目の名前を取得する、Windows PowerShell コンテナー プロバイダーがオーバーライドする必要があります、 [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) からの呼び出しをサポートするためにメソッド`Get-ChildItem`コマンドレットとその`Name`パラメーターを指定します。 場合、このメソッドは指定されたパスまたは子項目の名前をすべてのコンテナーの子項目の名前を取得、`returnAllContainers`コマンドレットのパラメーターを指定します。 子の名前は、パスのリーフ部分です。 たとえば、パス c:\windows\system32\abc.dll の子の名前は「月」は。 ディレクトリ c:\windows\system32 の子の名前は、"system32"です。

実装をここでは、 [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)このプロバイダーのメソッド。 パスが、テーブルを示している場合を示します、Access データベース (ドライブ) と行番号の指定したパスの場合、メソッドはテーブル名を取得します。 注意してください。

```csharp
protected override void GetChildNames(string path,
                            ReturnContainers returnContainers)
{
    // If the path represented is a drive, then the child items are
    // tables. get the names of all the tables in the drive.
    if (PathIsDrive(path))
    {
        foreach (DatabaseTableInfo table in GetTables())
        {
            WriteItemObject(table.Name, path, true);
        } // foreach (DatabaseTableInfo...
    } // if (PathIsDrive...
    else
    {
        // Get type, table name and row number from path specified
        string tableName;
        int rowNumber;

        PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

        if (type == PathType.Table)
        {
            // Get all the rows in the table and then write out the
            // row numbers.
            foreach (DatabaseRowInfo row in GetRows(tableName))
            {
                WriteItemObject(row.RowNumber, path, false);
            } // foreach (DatabaseRowInfo...
        }
        else if (type == PathType.Row)
        {
            // In this case the user has directly specified a row, hence
            // just give that particular row
            DatabaseRowInfo row = GetRow(tableName, rowNumber);

            WriteItemObject(row.RowNumber, path, false);
        }
        else
        {
            ThrowTerminatingInvalidPathException(path);
        }
    } // else
} // GetChildNames
```

[!code-csharp[AccessDBProviderSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L369-L411 "AccessDBProviderSample04.cs")]

#### <a name="things-to-remember-about-implementing-getchildnames"></a>GetChildNames の実装に関する注意点

実装に、次の条件が適用[System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems):

- Windows PowerShell コンテナー プロバイダーがから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言可能性があります、プロバイダー クラスを定義するときに、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これらのケースの実装で、 [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドは、メソッドに渡されるパスが指定した要件を満たしていることを確認する必要があります機能。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)と[System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)プロパティ。

  > [!NOTE]
  > このルールの例外が発生したときに、`returnAllContainers`コマンドレットのパラメーターを指定します。 ここでは、メソッドする必要がありますを取得、コンテナーの子の名前は任意の値に一致しない場合でも、 [System.Management.Automation.Provider.Cmdletprovider.Filter*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Filter)、 [System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)、または[System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)プロパティ。

- 既定では、このメソッドのオーバーライドを取得しないが一般的に、ユーザーから非表示しない限り、オブジェクトの名前、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティを指定します。 指定されたパスには、コンテナーが示されている場合、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティは必要ありません。

- 実装[System.Management.Automation.Provider.Containercmdletprovider.Getchildnames*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)循環リンクは、およびなどがある場合は、無限再帰を回避するため責任を負います。 そうした状態を反映するように適切な終了例外をスローする必要があります。

## <a name="attaching-dynamic-parameters-to-the-get-childitem-cmdlet-name"></a>Get-childitem コマンドレット (名) に動的パラメーターを追加

場合によって、`Get-ChildItem`コマンドレット (で、`Name`パラメーター) 実行時に動的に指定されている追加のパラメーターが必要です。 これらの動的パラメーターを提供する、Windows PowerShell コンテナー プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Containercmdletprovider.Getchildnamesdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)メソッド。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムでは、返されたオブジェクトを使用して、パラメーターを追加、`Get-ChildItem`コマンドレット。

このプロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchildnamesdynamicparameters](Msh_samplestestcmdlets#testprovidergetchildnamesdynamicparameters)]  -->

## <a name="renaming-items"></a>項目の名前を変更します。

項目の名前を変更する Windows PowerShell コンテナー プロバイダーがオーバーライドする必要があります、 [System.Management.Automation.Provider.Containercmdletprovider.Renameitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)メソッドからの呼び出しをサポートするために、`Rename-Item`コマンドレット。 このメソッドは、指定された新しい名前を指定したパスにある項目の名前を変更します。 親項目 (コンテナー) に対して相対的に新しい名前が常にあります。

このプロバイダーをオーバーライドしない、 [System.Management.Automation.Provider.Containercmdletprovider.Renameitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)メソッド。 ただし、既定の実装は、次のようにします。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderrenameitem](Msh_samplestestcmdlets#testproviderrenameitem)]  -->

#### <a name="things-to-remember-about-implementing-renameitem"></a>RenameItem の実装に関する注意点

実装に、次の条件が適用[System.Management.Automation.Provider.Containercmdletprovider.Renameitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem):

- Windows PowerShell コンテナー プロバイダーがから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言可能性があります、プロバイダー クラスを定義するときに、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これらのケースの実装で、 [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドは、メソッドに渡されるパスが指定した要件を満たしていることを確認する必要があります機能。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)と[System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)プロパティ。

- [System.Management.Automation.Provider.Containercmdletprovider.Renameitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)だけ、項目の名前を変更して、移動操作ではなく、メソッドが対象としています。 場合、メソッドの実装でエラーを書き込む必要があります、`newName`パラメーターは、パスの区切り記号が含まれていますか、それ以外の場合、親の位置を変更する項目が発生する可能性があります。

- 既定では、このメソッドのオーバーライドする必要がありますいないオブジェクト名を変更しない限り、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティを指定します。 指定されたパスには、コンテナーが示されている場合、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティは必要ありません。

- 実装、 [System.Management.Automation.Provider.Containercmdletprovider.Renameitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)メソッドを呼び出す必要があります[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)データ ストアに変更を加える前に、戻り値を確認します。 このメソッドは、変更が行われるとシステムの状態にたとえば、ファイルの名前を変更する操作の実行の確認に使用されます。 [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)コマンドライン設定や ユーザー設定変数を考慮して、Windows PowerShell ランタイムで、ユーザーに変更するリソースの名前を送信します。何を表示するかを決定します。

  呼び出し後[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)返します`true`、 [System.Management.Automation.Provider.Containercmdletprovider.Renameitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)メソッドを呼び出す必要があります、 [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)メソッド。 このメソッドは、かどうかは、操作を続行したいその他のフィードバックを許可するユーザーに確認メッセージのメッセージを送信します。 プロバイダーを呼び出す必要があります[System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)危険性のあるシステムの変更、追加のチェックとして。

## <a name="attaching-dynamic-parameters-to-the-rename-item-cmdlet"></a>Rename-item コマンドレットへの動的パラメーター

場合によって、`Rename-Item`コマンドレットが実行時に動的に指定されている追加のパラメーターが必要です。 これらの動的パラメーターを提供する Windows PowerShell コンテナー プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters)メソッド。 このメソッドは、指定されたパスにある項目のパラメーターを取得し、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムでは、返されたオブジェクトを使用して、パラメーターを追加、`Rename-Item`コマンドレット。

このコンテナーのプロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderrenameitemdynamicparameters](Msh_samplestestcmdlets#testproviderrenameitemdynamicparameters)]  -->

## <a name="creating-new-items"></a>新しい項目の作成

新しい項目を作成するコンテナー プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドからの呼び出しをサポートするために、`New-Item`コマンドレット。 このメソッドは、指定されたパスにあるデータ項目を作成します。 `type`コマンドレットのパラメーターに新しい項目のプロバイダーによって定義された型が含まれています。 たとえば、FileSystem プロバイダーを使用して、`type`パラメーター値は"file"または"directory"です。 `newItemValue`コマンドレットのパラメーターを新しい項目のプロバイダー固有の値を指定します。

実装をここでは、 [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)このプロバイダーのメソッド。

```csharp
protected override void NewItem( string path, string type,
                                 object newItemValue )
{
    // Create the new item here after
    // performing necessary validations
    //
    // WriteItemObject(newItemValue, path, false);

    // Example
    //
    // if (ShouldProcess(path, "new item"))
    // {
    //      // Create a new item and then call WriteObject
    //      WriteObject(newItemValue, path, false);
    // }

} // NewItem
```

[!code-csharp[AccessDBProviderSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L939-L955 "AccessDBProviderSample04.cs")]

#### <a name="things-to-remember-about-implementing-newitem"></a>NewItem の実装に関する注意点

実装に、次の条件が適用[System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem):

- [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドに渡された文字列の大文字と小文字を実行する必要があります、`type`パラメーター。 あいまいな少なく一致ことも可能です。 たとえば、種類"file"と"directory"は、あいまいさを解消する最初の文字だけが必要です。 場合、`type`パラメーターは、プロバイダーを作成できない型を示します、 [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドは、ArgumentException メッセージを書き込む必要があります型を示す、プロバイダーを作成できます。

- `newItemValue`パラメーターの実装、 [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)最低限の文字列をそのまま使用する方法はお勧めします。 によって取得されるオブジェクトの型を受け入れる必要がありますもこと、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)メソッドと同じパスにします。 [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドが使用できる、 [System.Management.Automation.Languageprimitives.Convertto*](/dotnet/api/System.Management.Automation.LanguagePrimitives.ConvertTo)型に変換するメソッド目的の型。

- 実装、 [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドを呼び出す必要があります[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)データ ストアに変更を加える前に、戻り値を確認します。 呼び出し後[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)は true を返し、 [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドを呼び出す必要があります、 [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)危険性のあるシステムの変更の追加の確認としてのメソッド。

## <a name="attaching-dynamic-parameters-to-the-new-item-cmdlet"></a>New-item コマンドレットへの動的パラメーター

場合によって、`New-Item`コマンドレットが実行時に動的に指定されている追加のパラメーターが必要です。 これらの動的パラメーターを提供するコンテナーのプロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Containercmdletprovider.Newitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters)メソッド。 このメソッドは、指定されたパスにある項目のパラメーターを取得し、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムでは、返されたオブジェクトを使用して、パラメーターを追加、`New-Item`コマンドレット。

このプロバイダーは、このメソッドを実装していません。 ただし、次のコードは、このメソッドの既定の実装です。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewitemdynamicparameters](Msh_samplestestcmdlets#testprovidernewitemdynamicparameters)]  -->

## <a name="removing-items"></a>項目を削除します。

項目を削除するには、Windows PowerShell プロバイダーをオーバーライドする必要があります、 [System.Management.Automation.Provider.Containercmdletprovider.Removeitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)メソッドからの呼び出しをサポートするために、`Remove-Item`コマンドレット。 このメソッドは、指定されたパスにデータ ストアから項目を削除します。 場合、`recurse`のパラメーター、`Remove-Item`コマンドレットに設定されている`true`メソッドは、そのレベルに関係なくすべての子項目を削除します。 パラメーターに設定されている場合`false`メソッドは、指定されたパスに 1 つの項目のみを削除します。

このプロバイダーは、項目の削除をサポートしていません。 ただし、次のコードは、既定の実装の[System.Management.Automation.Provider.Containercmdletprovider.Removeitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderremoveitem](Msh_samplestestcmdlets#testproviderremoveitem)]  -->

#### <a name="things-to-remember-about-implementing-removeitem"></a>RemoveItem の実装に関する注意点

実装に、次の条件が適用[System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem):

- Windows PowerShell コンテナー プロバイダーがから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言可能性があります、プロバイダー クラスを定義するときに、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これらのケースの実装で、 [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドは、メソッドに渡されるパスが指定した要件を満たしていることを確認する必要があります機能。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)と[System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)プロパティ。

- 既定では、このメソッドのオーバーライドする必要がありますオブジェクトは削除しない限り、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティが true にします。 指定されたパスには、コンテナーが示されている場合、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティは必要ありません。

- 実装[System.Management.Automation.Provider.Containercmdletprovider.Removeitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)循環リンクは、およびなどがある場合は、無限再帰を回避するため責任を負います。 そうした状態を反映するように適切な終了例外をスローする必要があります。

- 実装、 [System.Management.Automation.Provider.Containercmdletprovider.Removeitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)メソッドを呼び出す必要があります[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)データ ストアに変更を加える前に、戻り値を確認します。 呼び出し後[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)返します`true`、 [System.Management.Automation.Provider.Containercmdletprovider.Removeitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)メソッドを呼び出す必要があります、 [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)危険性のあるシステムの変更の追加の確認としてのメソッド。

## <a name="attaching-dynamic-parameters-to-the-remove-item-cmdlet"></a>Remove-item コマンドレットに動的パラメーターを追加

場合によって、`Remove-Item`コマンドレットが実行時に動的に指定されている追加のパラメーターが必要です。 これらの動的パラメーターを提供するコンテナーのプロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)これらのパラメーターを処理するメソッド。 このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムでは、返されたオブジェクトを使用して、パラメーターを追加、`Remove-Item`コマンドレット。

このコンテナーのプロバイダーは、このメソッドを実装していません。 ただし、次のコードは、既定の実装の[System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderremoveitemdynamicparameters](Msh_samplestestcmdlets#testproviderremoveitemdynamicparameters)]  -->

## <a name="querying-for-child-items"></a>子項目のクエリを実行します。

子項目が、指定されたパスに存在するかを確認するを確認する、Windows PowerShell コンテナー プロバイダーがオーバーライドする必要があります、 [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems)メソッド。 このメソッドが戻る`true`アイテムに子、および`false`それ以外の場合。 Null または空のパスのメソッドが子にするデータ ストア内のすべての項目を考慮し、返します`true`します。

ここでは、オーバーライド、 [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems)メソッド。 メソッドを返すかどうか ChunkPath のヘルパー メソッドによって作成された複数の 2 つのパス部分がある、`false`データベース コンテナーのみとテーブル コンテナーが定義されているため、します。 このヘルパー メソッドの詳細については、ChunkPath メソッドについては説明を参照してください[Windows PowerShell 項目プロバイダーを作成する](./creating-a-windows-powershell-item-provider.md)します。

```csharp
protected override bool HasChildItems( string path )
{
    return false;
} // HasChildItems
```

[!code-csharp[AccessDBProviderSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L1094-L1097 "AccessDBProviderSample04.cs")]

#### <a name="things-to-remember-about-implementing-haschilditems"></a>HasChildItems の実装に関する注意点

実装に、次の条件が適用[System.Management.Automation.Provider.Containercmdletprovider.Haschilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems):

- コンテナー プロバイダーが興味深いマウント ポイントの実装を含むルートを公開している場合、 [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) が返されます`true`を null または空の文字列が渡された場合に、パスにします。

## <a name="copying-items"></a>項目のコピー

項目をコピーするコンテナー プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)メソッドからの呼び出しをサポートするために、`Copy-Item`コマンドレット。 このメソッドによって示される位置からのデータ項目のコピー、`path`で示された場所にコマンドレットのパラメーター、`copyPath`パラメーター。 場合、`recurse`パラメーターを指定すると、メソッドは、すべてのサブコンテナーをコピーします。 パラメーターが指定されていない場合、メソッドは項目の 1 つのレベルのみをコピーします。

このプロバイダーは、このメソッドを実装していません。 ただし、次のコードは、既定の実装の[System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidercopyitem](Msh_samplestestcmdlets#testprovidercopyitem)]  -->

#### <a name="things-to-remember-about-implementing-copyitem"></a>CopyItem の実装に関する注意点

実装に、次の条件が適用[System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem):

- Windows PowerShell コンテナー プロバイダーがから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言可能性があります、プロバイダー クラスを定義するときに、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これらのケースの実装で、 [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドは、メソッドに渡されるパスが指定した要件を満たしていることを確認する必要があります機能。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)と[System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)プロパティ。

- 既定では、このメソッドのオーバーライドはないオブジェクトにコピーの既存のオブジェクトしない限り、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティに設定されて`true`します。 たとえば、FileSystem プロバイダーはコピーしません c:\temp\abc.txt c:\abc.txt の既存のファイルにしない限り、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティに設定されて`true`します。 パスが指定されている場合、`copyPath`パラメーターが存在し、コンテナーを示します、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティは必要ありません。 この場合、 [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)によって示される項目をコピーする必要があります、`path`でコンテナーにパラメーターが示される、`copyPath`子としてパラメーター。

- 実装[System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)循環リンクは、およびなどがある場合は、無限再帰を回避するため責任を負います。 そうした状態を反映するように適切な終了例外をスローする必要があります。

- 実装、 [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)メソッドを呼び出す必要があります[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)データ ストアに変更を加える前に、戻り値を確認します。 呼び出し後[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)は true を返し、 [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)メソッドを呼び出す必要があります、 [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)危険性のあるシステムの変更の追加の確認としてのメソッド。 これらのメソッドを呼び出す方法の詳細については、次を参照してください。[項目の名前を変更](#Renaming-Items)します。

## <a name="attaching-dynamic-parameters-to-the-copy-item-cmdlet"></a>Copy-item コマンドレットへの動的パラメーター

場合によって、`Copy-Item`コマンドレットが実行時に動的に指定されている追加のパラメーターが必要です。 これらの動的パラメーターを提供する、Windows PowerShell コンテナー プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)これらを処理するメソッドパラメーター。 このメソッドは、指定されたパスにある項目のパラメーターを取得し、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムでは、返されたオブジェクトを使用して、パラメーターを追加、`Copy-Item`コマンドレット。

このプロバイダーは、このメソッドを実装していません。 ただし、次のコードは、既定の実装の[System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidercopyitemdynamicparameters](Msh_samplestestcmdlets#testprovidercopyitemdynamicparameters)]  -->

## <a name="code-sample"></a>コード サンプル

完全なサンプル コードでは、次を参照してください。 [AccessDbProviderSample04 コード サンプル](./accessdbprovidersample04-code-sample.md)します。

## <a name="building-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーのビルド

参照してください[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。

## <a name="testing-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーのテスト

Windows PowerShell を使用した、Windows PowerShell プロバイダーを登録しているときに、コマンドラインでサポートされているコマンドレットを実行してテストできます。 次の出力例は架空の Access データベースに注意します。

1. 実行、`Get-ChildItem`コマンドレットは、Access データベースの Customers テーブルから子項目の一覧を取得します。

   ```powershell
   Get-ChildItem mydb:customers
   ```

   次の出力が表示されます。

   ```output
   PSPath        : AccessDB::customers
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : True
   Data          : System.Data.DataRow
   Name          : Customers
   RowCount      : 91
   Columns       :
   ```

2. 実行、`Get-ChildItem`コマンドレットを再度テーブルのデータを取得します。

   ```powershell
   (Get-ChildItem mydb:customers).data
   ```

   次の出力が表示されます。

   ```output
   TABLE_CAT   : c:\PS\northwind
   TABLE_SCHEM :
   TABLE_NAME  : Customers
   TABLE_TYPE  : TABLE
   REMARKS     :
   ```

3. 使用して、`Get-Item`データ テーブルの行 0 にある項目を取得するコマンドレットです。

   ```powershell
   Get-Item mydb:\customers\0
   ```

   次の出力が表示されます。

   ```output
   PSPath        : AccessDB::customers\0
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : False
   Data          : System.Data.DataRow
   RowNumber     : 0
   ```

4. 再利用`Get-Item`行 0 内の項目のデータを取得します。

   ```powershell
   (Get-Item mydb:\customers\0).data
   ```

   次の出力が表示されます。

   ```output
   CustomerID   : 1234
   CompanyName  : Fabrikam
   ContactName  : Eric Gruber
   ContactTitle : President
   Address      : 4567 Main Street
   City         : Buffalo
   Region       : NY
   PostalCode   : 98052
   Country      : USA
   Phone        : (425) 555-0100
   Fax          : (425) 555-0101
   ```

5. 使用して、`New-Item`コマンドレットを既存のテーブルに行を追加します。 `Path`パラメーターは、行への完全パスを指定し、行番号を指定する必要がありますが、テーブルの行の既存の番号より大きくなります。 `Type`パラメーターを追加する項目の種類を指定するには、「行」を示します。 最後に、`Value`パラメーターの行の列の値のコンマ区切りの一覧を指定します。

   ```powershell
   New-Item -Path mydb:\Customers\3 -ItemType "row" -Value "3,CustomerFirstName,CustomerLastName,CustomerEmailAddress,CustomerTitle,CustomerCompany,CustomerPhone, CustomerAddress,CustomerCity,CustomerState,CustomerZip,CustomerCountry"
   ```

6. 次のように、新しい項目の操作の正確性を確認します。

   ```none
   PS mydb:\> cd Customers
   PS mydb:\Customers> (Get-Item 3).data
   ```

   次の出力が表示されます。

   ```output
   ID        : 3
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
   ```

## <a name="see-also"></a>参照

[Windows PowerShell プロバイダーを作成します。](./how-to-create-a-windows-powershell-provider.md)

[Windows PowerShell プロバイダーのデザイン](./designing-your-windows-powershell-provider.md)

[項目の Windows PowerShell プロバイダーを実装します。](./creating-a-windows-powershell-item-provider.md)

[ナビゲーションの Windows PowerShell プロバイダーを実装します。](./creating-a-windows-powershell-navigation-provider.md)

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Windows PowerShell SDK](../windows-powershell-reference.md)

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)