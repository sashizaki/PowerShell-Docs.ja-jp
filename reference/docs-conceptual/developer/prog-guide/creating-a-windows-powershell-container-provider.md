---
title: Windows PowerShell コンテナープロバイダーを作成する |Microsoft Docs
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
ms.openlocfilehash: 0822e01d1191b019318fd0ea06dadea1a87a299e
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366851"
---
# <a name="creating-a-windows-powershell-container-provider"></a><span data-ttu-id="c25de-102">Windows PowerShell コンテナー プロバイダーを作成する</span><span class="sxs-lookup"><span data-stu-id="c25de-102">Creating a Windows PowerShell Container Provider</span></span>

<span data-ttu-id="c25de-103">このトピックでは、マルチレイヤーデータストアで動作する Windows PowerShell プロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c25de-103">This topic describes how to create a Windows PowerShell provider that can work on multi-layer data stores.</span></span> <span data-ttu-id="c25de-104">この種類のデータストアの場合、ストアの最上位レベルにはルート項目が含まれ、それ以降の各レベルは子項目のノードと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c25de-104">For this type of data store, the top level of the store contains the root items and each subsequent level is referred to as a node of child items.</span></span> <span data-ttu-id="c25de-105">ユーザーがこれらの子ノードを操作できるようにすることで、ユーザーはデータストアを介して階層的に対話できます。</span><span class="sxs-lookup"><span data-stu-id="c25de-105">By allowing the user to work on these child nodes, a user can interact hierarchically through the data store.</span></span>

<span data-ttu-id="c25de-106">複数レベルのデータストアで使用できるプロバイダーは、Windows PowerShell コンテナープロバイダーと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c25de-106">Providers that can work on multi-level data stores are referred to as Windows PowerShell container providers.</span></span> <span data-ttu-id="c25de-107">ただし、Windows PowerShell コンテナープロバイダーは、1つのコンテナー (入れ子になったコンテナーを含まない) に項目がある場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c25de-107">However, be aware that a Windows PowerShell container provider can be used only when there is one container (no nested containers) with items in it.</span></span> <span data-ttu-id="c25de-108">入れ子になったコンテナーがある場合は、Windows PowerShell ナビゲーションプロバイダーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-108">If there are nested containers, then you must implement a Windows PowerShell navigation provider.</span></span> <span data-ttu-id="c25de-109">Windows PowerShell ナビゲーションプロバイダーの実装の詳細については、「 [Windows Powershell ナビゲーションプロバイダーの作成](./creating-a-windows-powershell-navigation-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c25de-109">For more information about implementing Windows PowerShell navigation provider, see [Creating a Windows PowerShell Navigation Provider](./creating-a-windows-powershell-navigation-provider.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c25de-110">このプロバイダーのC#ソースファイル (AccessDBSampleProvider04.cs) をダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="c25de-110">You can download the C# source file (AccessDBSampleProvider04.cs) for this provider using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="c25de-111">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c25de-111">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="c25de-112">ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="c25de-112">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>
>
> <span data-ttu-id="c25de-113">その他の Windows PowerShell プロバイダーの実装の詳細については、「 [Windows Powershell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c25de-113">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

<span data-ttu-id="c25de-114">ここで説明する Windows PowerShell コンテナープロバイダーは、データベースを1つのコンテナーとして定義します。データベースのテーブルと行は、コンテナーの項目として定義されています。</span><span class="sxs-lookup"><span data-stu-id="c25de-114">The Windows PowerShell container provider described here defines the database as its single container, with the tables and rows of the database defined as items of the container.</span></span>

> [!CAUTION]
> <span data-ttu-id="c25de-115">この設計では、名前が ID のフィールドを持つデータベースと、フィールドの型が LongInteger であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c25de-115">Be aware that this design assumes a database that has a field with the name ID, and that the type of the field is LongInteger.</span></span>

## <a name="defining-a-windows-powershell-container-provider-class"></a><span data-ttu-id="c25de-116">Windows PowerShell コンテナープロバイダークラスの定義</span><span class="sxs-lookup"><span data-stu-id="c25de-116">Defining a Windows PowerShell Container Provider Class</span></span>

<span data-ttu-id="c25de-117">Windows PowerShell コンテナープロバイダーは、 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)基底クラスから派生する .net クラスを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-117">A Windows PowerShell container provider must define a .NET class that derives from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) base class.</span></span> <span data-ttu-id="c25de-118">ここでは、このセクションで説明する Windows PowerShell コンテナープロバイダーのクラス定義を示します。</span><span class="sxs-lookup"><span data-stu-id="c25de-118">Here is the class definition for the Windows PowerShell container provider described in this section.</span></span>

```csharp
   [CmdletProvider("AccessDB", ProviderCapabilities.None)]
   public class AccessDBProvider : ContainerCmdletProvider
```

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L34-L35 "AccessDBProviderSample04.cs")]

<span data-ttu-id="c25de-119">このクラス定義では、このクラス[の属性](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)に2つのパラメーターが含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c25de-119">Notice that in this class definition, the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute includes two parameters.</span></span> <span data-ttu-id="c25de-120">最初のパラメーターは、Windows PowerShell によって使用されるプロバイダーのわかりやすい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c25de-120">The first parameter specifies a user-friendly name for the provider that is used by Windows PowerShell.</span></span> <span data-ttu-id="c25de-121">2番目のパラメーターは、コマンドの処理中にプロバイダーが Windows PowerShell ランタイムに公開する Windows PowerShell 固有の機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="c25de-121">The second parameter specifies the Windows PowerShell specific capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span> <span data-ttu-id="c25de-122">このプロバイダーには、Windows PowerShell 固有の機能は追加されていません。</span><span class="sxs-lookup"><span data-stu-id="c25de-122">For this provider, there are no Windows PowerShell specific capabilities that are added.</span></span>

## <a name="defining-base-functionality"></a><span data-ttu-id="c25de-123">基本機能の定義</span><span class="sxs-lookup"><span data-stu-id="c25de-123">Defining Base Functionality</span></span>

<span data-ttu-id="c25de-124">「 [Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」で説明したように、 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスは、さまざまなプロバイダー機能を提供する他のいくつかのクラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="c25de-124">As described in [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md), the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class derives from several other classes that provided different provider functionality.</span></span> <span data-ttu-id="c25de-125">そのため、Windows PowerShell コンテナープロバイダーは、これらのクラスによって提供されるすべての機能を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-125">A Windows PowerShell container provider, therefore, needs to define all of the functionality provided by those classes.</span></span>

<span data-ttu-id="c25de-126">セッション固有の初期化情報を追加し、プロバイダーによって使用されるリソースを解放するための機能を実装するには、「[基本的な Windows PowerShell プロバイダーの作成](./creating-a-basic-windows-powershell-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c25de-126">To implement functionality for adding session-specific initialization information and for releasing resources that are used by the provider, see [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span> <span data-ttu-id="c25de-127">ただし、ほとんどのプロバイダー (ここで説明するプロバイダーを含む) は、Windows PowerShell によって提供されるこの機能の既定の実装を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c25de-127">However, most providers (including the provider described here) can use the default implementation of this functionality that is provided by Windows PowerShell.</span></span>

<span data-ttu-id="c25de-128">データストアへのアクセスを取得するには、プロバイダーが[Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)基底クラスのメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-128">To get access to the data store, the provider must implement the methods of the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) base class.</span></span> <span data-ttu-id="c25de-129">これらのメソッドの実装の詳細については、「 [Windows PowerShell ドライブプロバイダーの作成](./creating-a-windows-powershell-drive-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c25de-129">For more information about implementing these methods, see [Creating an Windows PowerShell Drive Provider](./creating-a-windows-powershell-drive-provider.md).</span></span>

<span data-ttu-id="c25de-130">項目の取得、設定、クリアなど、データストアの項目を操作するには、プロバイダー[が、system.object クラスの基本クラス](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)によって提供されるメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-130">To manipulate the items of a data store, such as getting, setting, and clearing items, the provider must implement the methods provided by the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) base class.</span></span> <span data-ttu-id="c25de-131">これらのメソッドの実装の詳細については、「 [Windows PowerShell 項目プロバイダーの作成](./creating-a-windows-powershell-item-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c25de-131">For more information about implementing these methods, see [Creating an Windows PowerShell Item Provider](./creating-a-windows-powershell-item-provider.md).</span></span>

## <a name="retrieving-child-items"></a><span data-ttu-id="c25de-132">取得 (子項目を)</span><span class="sxs-lookup"><span data-stu-id="c25de-132">Retrieving Child Items</span></span>

<span data-ttu-id="c25de-133">子項目を取得するには、Windows PowerShell コンテナープロバイダーは、Containercmdletprovider コマンドレット `Get-ChildItem` からの呼び出しをサポートするように[Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-133">To retrieve a child item, the Windows PowerShell container provider must override the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method to support calls from the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="c25de-134">このメソッドは、データストアから子項目を取得し、それらをオブジェクトとしてパイプラインに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="c25de-134">This method retrieves child items from the data store and writes them to the pipeline as objects.</span></span> <span data-ttu-id="c25de-135">コマンドレットの `recurse` パラメーターが指定されている場合、メソッドは、どのレベルにあるかに関係なく、すべての子を取得します。</span><span class="sxs-lookup"><span data-stu-id="c25de-135">If the `recurse` parameter of the cmdlet is specified, the method retrieves all children regardless of what level they are at.</span></span> <span data-ttu-id="c25de-136">@No__t_0 パラメーターが指定されていない場合、メソッドは子の1つのレベルのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="c25de-136">If the `recurse` parameter is not specified, the method retrieves only a single level of children.</span></span>

<span data-ttu-id="c25de-137">ここでは、このプロバイダーの[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="c25de-137">Here is the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method for this provider.</span></span> <span data-ttu-id="c25de-138">このメソッドは、パスが Access データベースを示す場合はすべてのデータベーステーブル内の子項目を取得し、パスがデータテーブルを示す場合はそのテーブルの行から子項目を取得することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c25de-138">Notice that this method retrieves the child items in all database tables when the path indicates the Access database, and retrieves the child items from the rows of that table if the path indicates a data table.</span></span>

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

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L311-L362 "AccessDBProviderSample04.cs")]

#### <a name="things-to-remember-about-implementing-getchilditems"></a><span data-ttu-id="c25de-139">GetChildItems の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="c25de-139">Things to Remember About Implementing GetChildItems</span></span>

<span data-ttu-id="c25de-140">[Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)の実装には、次の条件が当てはまる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-140">The following conditions may apply to your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems):</span></span>

- <span data-ttu-id="c25de-141">プロバイダークラスを定義すると、Windows PowerShell コンテナープロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。</span><span class="sxs-lookup"><span data-stu-id="c25de-141">When defining the provider class, a Windows PowerShell container provider might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="c25de-142">このような場合は、 [Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドの実装で、メソッドに渡されるパスが指定された機能の要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-142">In these cases, the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method needs to ensure that the path passed to the method meets the requirements of the specified capabilities.</span></span> <span data-ttu-id="c25de-143">これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...</span><span class="sxs-lookup"><span data-stu-id="c25de-143">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) and [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) properties.</span></span>

- <span data-ttu-id="c25de-144">このメソッドの実装では、項目がユーザーに表示される可能性のある項目へのアクセス形式を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-144">The implementation of this method should take into account any form of access to the item that might make the item visible to the user.</span></span> <span data-ttu-id="c25de-145">たとえば、ユーザーがファイルシステムプロバイダー (Windows PowerShell によって提供される) を介してファイルに対する書き込みアクセス権を持っていても、 [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)読み取りアクセス権を持っていない場合、ファイルはまだ存在しています`true`。</span><span class="sxs-lookup"><span data-stu-id="c25de-145">For example, if a user has write access to a file through the FileSystem provider (supplied by Windows PowerShell), but not read access, the file still exists and [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) returns `true`.</span></span> <span data-ttu-id="c25de-146">実装では、子を列挙できるかどうかを確認するために、親項目のチェックが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-146">Your implementation might require the checking of a parent item to see if the child can be enumerated.</span></span>

- <span data-ttu-id="c25de-147">複数の項目を書き込む場合、 [Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドには時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="c25de-147">When writing multiple items, the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method can take some time.</span></span> <span data-ttu-id="c25de-148">プロバイダーを設計して、1回に1つずつ、[システム](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject)を使用して項目を書き込むようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c25de-148">You can design your provider to write the items using the [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) method one at a time.</span></span> <span data-ttu-id="c25de-149">この手法を使用すると、ストリーム内のユーザーに項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c25de-149">Using this technique will present the items to the user in a stream.</span></span>

- <span data-ttu-id="c25de-150">[Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)の実装は、循環リンクがある場合に無限再帰を防ぐことを担当します。また、同様の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="c25de-150">Your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) is responsible for preventing infinite recursion when there are circular links, and the like.</span></span> <span data-ttu-id="c25de-151">このような状態を反映するには、適切な終了例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-151">An appropriate terminating exception should be thrown to reflect such a condition.</span></span>

## <a name="attaching-dynamic-parameters-to-the-get-childitem-cmdlet"></a><span data-ttu-id="c25de-152">Get-childitem コマンドレットへの動的パラメーターのアタッチ</span><span class="sxs-lookup"><span data-stu-id="c25de-152">Attaching Dynamic Parameters to the Get-ChildItem Cmdlet</span></span>

<span data-ttu-id="c25de-153">Containercmdletprovider を呼び出す`Get-ChildItem`コマンドレット[System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)には、実行時に動的に指定される追加のパラメーターが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-153">Sometimes the `Get-ChildItem` cmdlet that calls [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) requires additional parameters that are specified dynamically at runtime.</span></span> <span data-ttu-id="c25de-154">これらの動的パラメーターを指定するには、Windows PowerShell コンテナープロバイダーが[Containercmdletprovider. Getchilditemsdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters)メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-154">To provide these dynamic parameters, the Windows PowerShell container provider must implement the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditemsdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) method.</span></span> <span data-ttu-id="c25de-155">このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の[Parameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。素材.</span><span class="sxs-lookup"><span data-stu-id="c25de-155">This method retrieves dynamic parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="c25de-156">Windows PowerShell ランタイムは、返されたオブジェクトを使用して、`Get-ChildItem` コマンドレットにパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="c25de-156">The Windows PowerShell runtime uses the returned object to add the parameters to the `Get-ChildItem` cmdlet.</span></span>

<span data-ttu-id="c25de-157">この Windows PowerShell コンテナープロバイダーは、このメソッドを実装していません。</span><span class="sxs-lookup"><span data-stu-id="c25de-157">This Windows PowerShell container provider does not implement this method.</span></span> <span data-ttu-id="c25de-158">ただし、次のコードは、このメソッドの既定の実装です。</span><span class="sxs-lookup"><span data-stu-id="c25de-158">However, the following code is the default implementation of this method.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchilditemsdynamicparameters](Msh_samplestestcmdlets#testprovidergetchilditemsdynamicparameters)]  -->

## <a name="retrieving-child-item-names"></a><span data-ttu-id="c25de-159">取得 (子項目名を)</span><span class="sxs-lookup"><span data-stu-id="c25de-159">Retrieving Child Item Names</span></span>

<span data-ttu-id="c25de-160">子項目の名前を取得するには、`Get-ChildItem` コマンドレットからの呼び出しをサポートするために、Windows PowerShell コンテナープロバイダーで[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)メソッドをオーバーライドする必要があり `Name`パラメーターが指定されています。</span><span class="sxs-lookup"><span data-stu-id="c25de-160">To retrieve the names of child items, the Windows PowerShell container provider must override the [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) method to support calls from the `Get-ChildItem` cmdlet when its `Name` parameter is specified.</span></span> <span data-ttu-id="c25de-161">このメソッドは、コマンドレットの `returnAllContainers` パラメーターが指定されている場合、すべてのコンテナーについて、指定されたパスまたは子項目の名前の子項目の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="c25de-161">This method retrieves the names of the child items for the specified path or child item names for all containers if the `returnAllContainers` parameter of the cmdlet is specified.</span></span> <span data-ttu-id="c25de-162">子の名前は、パスのリーフ部分です。</span><span class="sxs-lookup"><span data-stu-id="c25de-162">A child name is the leaf portion of a path.</span></span> <span data-ttu-id="c25de-163">たとえば、パス c:\windows\system32\abc.dll の子名は "abc .dll" です。</span><span class="sxs-lookup"><span data-stu-id="c25de-163">For example, the child name for the path c:\windows\system32\abc.dll is "abc.dll".</span></span> <span data-ttu-id="c25de-164">ディレクトリ c:\windows\system32 の子名は "system32" です。</span><span class="sxs-lookup"><span data-stu-id="c25de-164">The child name for the directory c:\windows\system32 is "system32".</span></span>

<span data-ttu-id="c25de-165">次に示すのは、このプロバイダーの[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)メソッドの実装について説明します。</span><span class="sxs-lookup"><span data-stu-id="c25de-165">Here is the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) method for this provider.</span></span> <span data-ttu-id="c25de-166">パスがテーブルを示す場合、メソッドはテーブル名を取得することに注意してください。指定されたパスが Access データベース (ドライブ) と行番号を示す場合は、</span><span class="sxs-lookup"><span data-stu-id="c25de-166">Notice that the method retrieves table names if the specified path indicates the Access database (drive) and row numbers if the path indicates a table.</span></span>

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

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L369-L411 "AccessDBProviderSample04.cs")]

#### <a name="things-to-remember-about-implementing-getchildnames"></a><span data-ttu-id="c25de-167">GetChildNames の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="c25de-167">Things to Remember About Implementing GetChildNames</span></span>

<span data-ttu-id="c25de-168">[Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)の実装には、次の条件が当てはまる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-168">The following conditions may apply to your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems):</span></span>

- <span data-ttu-id="c25de-169">プロバイダークラスを定義すると、Windows PowerShell コンテナープロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。</span><span class="sxs-lookup"><span data-stu-id="c25de-169">When defining the provider class, a Windows PowerShell container provider might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="c25de-170">このような場合は、 [Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドの実装で、メソッドに渡されるパスが指定された機能の要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-170">In these cases, the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method needs to ensure that the path passed to the method meets the requirements of the specified capabilities.</span></span> <span data-ttu-id="c25de-171">これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...</span><span class="sxs-lookup"><span data-stu-id="c25de-171">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) and [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) properties.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c25de-172">この規則の例外は、コマンドレットの `returnAllContainers` パラメーターが指定されている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="c25de-172">An exception to this rule occurs when the `returnAllContainers` parameter of the cmdlet is specified.</span></span> <span data-ttu-id="c25de-173">この場合、メソッドは、コンテナーの子名が、[システム](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Filter)[の値と一致しない場合でも、その子名を取得する必要があります。システム.](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include).............................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) ...............</span><span class="sxs-lookup"><span data-stu-id="c25de-173">In this case, the method should retrieve any child name for a container, even if it does not match the values of the [System.Management.Automation.Provider.Cmdletprovider.Filter\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Filter), [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include), or [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) properties.</span></span>

- <span data-ttu-id="c25de-174">既定では、このメソッドをオーバーライドしても、通常はユーザーに表示されないオブジェクトの名前を取得することはできません。ただし、この場合、 [Force \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-174">By default, overrides of this method should not retrieve names of objects that are generally hidden from the user unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is specified.</span></span> <span data-ttu-id="c25de-175">指定されたパスがコンテナーを示している場合、[このプロパティは必須ではあり](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)ません。</span><span class="sxs-lookup"><span data-stu-id="c25de-175">If the specified path indicates a container, the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is not required.</span></span>

- <span data-ttu-id="c25de-176">[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)を実装すると、循環リンクがあるときに無限再帰を防ぐことができます。また、のようになります。</span><span class="sxs-lookup"><span data-stu-id="c25de-176">Your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) is responsible for preventing infinite recursion when there are circular links, and the like.</span></span> <span data-ttu-id="c25de-177">このような状態を反映するには、適切な終了例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-177">An appropriate terminating exception should be thrown to reflect such a condition.</span></span>

## <a name="attaching-dynamic-parameters-to-the-get-childitem-cmdlet-name"></a><span data-ttu-id="c25de-178">動的パラメーターを Get-childitem コマンドレット (Name) にアタッチする</span><span class="sxs-lookup"><span data-stu-id="c25de-178">Attaching Dynamic Parameters to the Get-ChildItem Cmdlet (Name)</span></span>

<span data-ttu-id="c25de-179">@No__t_0 コマンドレット (`Name` パラメーターを使用) には、実行時に動的に指定される追加のパラメーターが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-179">Sometimes the `Get-ChildItem` cmdlet (with the `Name` parameter) requires additional parameters that are specified dynamically at runtime.</span></span> <span data-ttu-id="c25de-180">これらの動的パラメーターを指定するには、Windows PowerShell コンテナープロバイダーが[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)を実装する必要があります。このメソッドは、</span><span class="sxs-lookup"><span data-stu-id="c25de-180">To provide these dynamic parameters, the Windows PowerShell container provider must implement the [System.Management.Automation.Provider.Containercmdletprovider.Getchildnamesdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) method.</span></span> <span data-ttu-id="c25de-181">このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の Parameterdictionary と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。 [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c25de-181">This method retrieves the dynamic parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="c25de-182">Windows PowerShell ランタイムは、返されたオブジェクトを使用して、`Get-ChildItem` コマンドレットにパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="c25de-182">The Windows PowerShell runtime uses the returned object to add the parameters to the `Get-ChildItem` cmdlet.</span></span>

<span data-ttu-id="c25de-183">このプロバイダーは、このメソッドを実装していません。</span><span class="sxs-lookup"><span data-stu-id="c25de-183">This provider does not implement this method.</span></span> <span data-ttu-id="c25de-184">ただし、次のコードは、このメソッドの既定の実装です。</span><span class="sxs-lookup"><span data-stu-id="c25de-184">However, the following code is the default implementation of this method.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchildnamesdynamicparameters](Msh_samplestestcmdlets#testprovidergetchildnamesdynamicparameters)]  -->

## <a name="renaming-items"></a><span data-ttu-id="c25de-185">項目の名前変更</span><span class="sxs-lookup"><span data-stu-id="c25de-185">Renaming Items</span></span>

<span data-ttu-id="c25de-186">項目の名前を変更するには、Windows PowerShell コンテナープロバイダーで[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)メソッドをオーバーライドして、`Rename-Item` コマンドレットからの呼び出しをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-186">To rename an item, a Windows PowerShell container provider must override the [System.Management.Automation.Provider.Containercmdletprovider.Renameitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) method to support calls from the `Rename-Item` cmdlet.</span></span> <span data-ttu-id="c25de-187">このメソッドは、指定されたパスにある項目の名前を、指定された新しい名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="c25de-187">This method changes the name of the item at the specified path to the new name provided.</span></span> <span data-ttu-id="c25de-188">新しい名前は、常に親項目 (コンテナー) に対する相対パスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-188">The new name must always be relative to the parent item (container).</span></span>

<span data-ttu-id="c25de-189">このプロバイダーでは、 [Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)メソッドがオーバーライドされていません。</span><span class="sxs-lookup"><span data-stu-id="c25de-189">This provider does not override the [System.Management.Automation.Provider.Containercmdletprovider.Renameitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) method.</span></span> <span data-ttu-id="c25de-190">ただし、既定の実装は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c25de-190">However, the following is the default implementation.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderrenameitem](Msh_samplestestcmdlets#testproviderrenameitem)]  -->

#### <a name="things-to-remember-about-implementing-renameitem"></a><span data-ttu-id="c25de-191">RenameItem の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="c25de-191">Things to Remember About Implementing RenameItem</span></span>

<span data-ttu-id="c25de-192">Containercmdletprovider の実装には、次の条件が当てはまる場合があります[\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem):</span><span class="sxs-lookup"><span data-stu-id="c25de-192">The following conditions may apply to your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Renameitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem):</span></span>

- <span data-ttu-id="c25de-193">プロバイダークラスを定義すると、Windows PowerShell コンテナープロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。</span><span class="sxs-lookup"><span data-stu-id="c25de-193">When defining the provider class, a Windows PowerShell container provider might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="c25de-194">このような場合は、 [Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドの実装で、メソッドに渡されるパスが指定された機能の要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-194">In these cases, the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method needs to ensure that the path passed to the method meets the requirements of the specified capabilities.</span></span> <span data-ttu-id="c25de-195">これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...</span><span class="sxs-lookup"><span data-stu-id="c25de-195">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) and [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) properties.</span></span>

- <span data-ttu-id="c25de-196">[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)メソッドは、項目の名前の変更のみを目的としています。移動操作では変更できません。</span><span class="sxs-lookup"><span data-stu-id="c25de-196">The [System.Management.Automation.Provider.Containercmdletprovider.Renameitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) method is intended for the modification of the name of an item only, and not for move operations.</span></span> <span data-ttu-id="c25de-197">メソッドの実装では、`newName` パラメーターにパスの区切り記号が含まれている場合、または項目が親の場所を変更する場合に、エラーを書き込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-197">Your implementation of the method should write an error if the `newName` parameter contains path separators, or might otherwise cause the item to change its parent location.</span></span>

- <span data-ttu-id="c25de-198">既定では、このメソッドのオーバーライドでは、system.string [\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティが指定されていない限り、オブジェクトの名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c25de-198">By default, overrides of this method should not rename objects unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is specified.</span></span> <span data-ttu-id="c25de-199">指定されたパスがコンテナーを示している場合、[このプロパティは必須ではあり](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)ません。</span><span class="sxs-lookup"><span data-stu-id="c25de-199">If the specified path indicates a container, the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is not required.</span></span>

- <span data-ttu-id="c25de-200">[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)メソッドの実装では、前に system.object を呼び出し、戻り値を確認する必要があります。これを行うには、前の手順を実行し[ます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)データストアに変更を加える。</span><span class="sxs-lookup"><span data-stu-id="c25de-200">Your implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Renameitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) method should call [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) and check its return value before making any changes to the data store.</span></span> <span data-ttu-id="c25de-201">このメソッドは、ファイル名の変更など、システム状態が変更されたときの操作の実行を確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c25de-201">This method is used to confirm execution of an operation when a change is made to system state, for example, renaming files.</span></span> <span data-ttu-id="c25de-202">Windows PowerShell ランタイムでは、変更するリソースの名前をユーザーに送信します。 Windows PowerShell ランタイムでは、コマンドライン設定またはユーザー設定変数を考慮に[入れます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)表示される内容。</span><span class="sxs-lookup"><span data-stu-id="c25de-202">[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) sends the name of the resource to be changed to the user, with the Windows PowerShell runtime taking into account any command line settings or preference variables in determining what should be displayed.</span></span>

  <span data-ttu-id="c25de-203">Containercmdletprovider を呼び出すと、が[`true` 返されます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)その後、 [\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)メソッドはを呼び出す必要があります。この場合、このメソッドは、 [System.](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) ........</span><span class="sxs-lookup"><span data-stu-id="c25de-203">After the call to [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) returns `true`, the [System.Management.Automation.Provider.Containercmdletprovider.Renameitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) method should call the [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) method.</span></span> <span data-ttu-id="c25de-204">このメソッドは、操作を続行する必要があるかどうかを確認するための追加のフィードバックを許可するために、メッセージを確認メッセージとしてユーザーに送信します。</span><span class="sxs-lookup"><span data-stu-id="c25de-204">This method sends a message a confirmation message to the user to allow additional feedback to say if the operation should be continued.</span></span> <span data-ttu-id="c25de-205">プロバイダーは、system.servicemodel プロバイダーを呼び出す必要があり[ます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)危険性の高いシステム変更については、追加のチェックとして続行してください。</span><span class="sxs-lookup"><span data-stu-id="c25de-205">A provider should call [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) as an additional check for potentially dangerous system modifications.</span></span>

## <a name="attaching-dynamic-parameters-to-the-rename-item-cmdlet"></a><span data-ttu-id="c25de-206">名前の変更コマンドレットに動的パラメーターをアタッチする</span><span class="sxs-lookup"><span data-stu-id="c25de-206">Attaching Dynamic Parameters to the Rename-Item Cmdlet</span></span>

<span data-ttu-id="c25de-207">@No__t_0 コマンドレットでは、実行時に動的に指定される追加のパラメーターが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-207">Sometimes the `Rename-Item` cmdlet requires additional parameters that are specified dynamically at runtime.</span></span> <span data-ttu-id="c25de-208">これらの動的パラメーターを指定するには、Windows PowerShell コンテナープロバイダーで[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters)メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-208">To provide these dynamic parameters, Windows PowerShell container provider must implement the [System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) method.</span></span> <span data-ttu-id="c25de-209">このメソッドは、指定されたパスにある項目のパラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の[Parameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。素材.</span><span class="sxs-lookup"><span data-stu-id="c25de-209">This method retrieves the parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="c25de-210">Windows PowerShell ランタイムは、返されたオブジェクトを使用して、`Rename-Item` コマンドレットにパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="c25de-210">The Windows PowerShell runtime uses the returned object to add the parameters to the `Rename-Item` cmdlet.</span></span>

<span data-ttu-id="c25de-211">このコンテナープロバイダーは、このメソッドを実装していません。</span><span class="sxs-lookup"><span data-stu-id="c25de-211">This container provider does not implement this method.</span></span> <span data-ttu-id="c25de-212">ただし、次のコードは、このメソッドの既定の実装です。</span><span class="sxs-lookup"><span data-stu-id="c25de-212">However, the following code is the default implementation of this method.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderrenameitemdynamicparameters](Msh_samplestestcmdlets#testproviderrenameitemdynamicparameters)]  -->

## <a name="creating-new-items"></a><span data-ttu-id="c25de-213">新しい項目の作成</span><span class="sxs-lookup"><span data-stu-id="c25de-213">Creating New Items</span></span>

<span data-ttu-id="c25de-214">新しい項目を作成するには、Containercmdletprovider コマンドレット `New-Item` からの呼び出しをサポートするために、コンテナープロバイダーが[Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-214">To create new items, a container provider must implement the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method to support calls from the `New-Item` cmdlet.</span></span> <span data-ttu-id="c25de-215">このメソッドは、指定されたパスにあるデータ項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="c25de-215">This method creates a data item located at the specified path.</span></span> <span data-ttu-id="c25de-216">コマンドレットの `type` パラメーターには、新しい項目のプロバイダー定義型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c25de-216">The `type` parameter of the cmdlet contains the provider-defined type for the new item.</span></span> <span data-ttu-id="c25de-217">たとえば、FileSystem プロバイダーは、値が "file" または "directory" の `type` パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c25de-217">For example, the FileSystem provider uses a `type` parameter with a value of "file" or "directory".</span></span> <span data-ttu-id="c25de-218">コマンドレットの `newItemValue` パラメーターでは、新しい項目のプロバイダー固有の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c25de-218">The `newItemValue` parameter of the cmdlet specifies a provider-specific value for the new item.</span></span>

<span data-ttu-id="c25de-219">ここでは、このプロバイダーの[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="c25de-219">Here is the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method for this provider.</span></span>

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

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L939-L955 "AccessDBProviderSample04.cs")]

#### <a name="things-to-remember-about-implementing-newitem"></a><span data-ttu-id="c25de-220">NewItem の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="c25de-220">Things to Remember About Implementing NewItem</span></span>

<span data-ttu-id="c25de-221">[Containercmdletprovider. Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)の実装には、次の条件が当てはまる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-221">The following conditions may apply to your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem):</span></span>

- <span data-ttu-id="c25de-222">[Containercmdletprovider. Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドでは、`type` パラメーターで渡された文字列の大文字と小文字を区別しない比較を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-222">The [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method should perform a case-insensitive comparison of the string passed in the `type` parameter.</span></span> <span data-ttu-id="c25de-223">また、あいまい一致が少なくとも許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-223">It should also allow for least ambiguous matches.</span></span> <span data-ttu-id="c25de-224">たとえば、"file" と "directory" 型の場合、最初の文字のみを明確にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-224">For example, for the types "file" and "directory", only the first letter is required to disambiguate.</span></span> <span data-ttu-id="c25de-225">@No__t_0 パラメーターが、プロバイダーが作成できない型を示している場合、 [Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドは、プロバイダーが可能な型を示すメッセージを含む ArgumentException を書き込む必要があります。生成.</span><span class="sxs-lookup"><span data-stu-id="c25de-225">If the `type` parameter indicates a type your provider cannot create, the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method should write an ArgumentException with a message indicating the types the provider can create.</span></span>

- <span data-ttu-id="c25de-226">@No__t_0 パラメーターの場合は、 [Containercmdletprovider. Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドの実装で、少なくとも文字列を受け入れることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c25de-226">For the `newItemValue` parameter, the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method is recommended to accept strings at a minimum.</span></span> <span data-ttu-id="c25de-227">また、同じパスに対し[て、system.servicemodel](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) ........... によって取得されたオブジェクトの型も受け入れます。</span><span class="sxs-lookup"><span data-stu-id="c25de-227">It should also accept the type of object that is retrieved by the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) method for the same path.</span></span> <span data-ttu-id="c25de-228">[Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドは、convertto-html \* メソッドを使用して、型を目的の型に変換できます。 [\*](/dotnet/api/System.Management.Automation.LanguagePrimitives.ConvertTo)メソッドを使用して Containercmdletprovider します。</span><span class="sxs-lookup"><span data-stu-id="c25de-228">The [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method can use the [System.Management.Automation.Languageprimitives.Convertto\*](/dotnet/api/System.Management.Automation.LanguagePrimitives.ConvertTo) method to convert types to the desired type.</span></span>

- <span data-ttu-id="c25de-229">[Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドの実装では、Containercmdletprovider を呼び出す必要があり[ます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)その場合は、前にその戻り値を確認してください。前にデータストアに変更を加える。</span><span class="sxs-lookup"><span data-stu-id="c25de-229">Your implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method should call [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) and check its return value before making any changes to the data store.</span></span> <span data-ttu-id="c25de-230">Containercmdletprovider の[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)呼び出しによって true が返された後、Newitem \* メソッドはを呼び出す[System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) 必要があります。この場合、\* メソッドは[System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)System.object は、危険性の高いシステム変更について追加のチェックとしてメソッドを続行します。</span><span class="sxs-lookup"><span data-stu-id="c25de-230">After the call to [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) returns true, the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method should call the [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) method as an additional check for potentially dangerous system modifications.</span></span>

## <a name="attaching-dynamic-parameters-to-the-new-item-cmdlet"></a><span data-ttu-id="c25de-231">動的パラメーターを新しい項目のコマンドレットにアタッチする</span><span class="sxs-lookup"><span data-stu-id="c25de-231">Attaching Dynamic Parameters to the New-Item Cmdlet</span></span>

<span data-ttu-id="c25de-232">@No__t_0 コマンドレットでは、実行時に動的に指定される追加のパラメーターが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-232">Sometimes the `New-Item` cmdlet requires additional parameters that are specified dynamically at runtime.</span></span> <span data-ttu-id="c25de-233">これらの動的パラメーターを指定するには、コンテナープロバイダーが[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters)メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-233">To provide these dynamic parameters, the container provider must implement the [System.Management.Automation.Provider.Containercmdletprovider.Newitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) method.</span></span> <span data-ttu-id="c25de-234">このメソッドは、指定されたパスにある項目のパラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の[Parameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。素材.</span><span class="sxs-lookup"><span data-stu-id="c25de-234">This method retrieves the parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="c25de-235">Windows PowerShell ランタイムは、返されたオブジェクトを使用して、`New-Item` コマンドレットにパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="c25de-235">The Windows PowerShell runtime uses the returned object to add the parameters to the `New-Item` cmdlet.</span></span>

<span data-ttu-id="c25de-236">このプロバイダーは、このメソッドを実装していません。</span><span class="sxs-lookup"><span data-stu-id="c25de-236">This provider does not implement this method.</span></span> <span data-ttu-id="c25de-237">ただし、次のコードは、このメソッドの既定の実装です。</span><span class="sxs-lookup"><span data-stu-id="c25de-237">However, the following code is the default implementation of this method.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewitemdynamicparameters](Msh_samplestestcmdlets#testprovidernewitemdynamicparameters)]  -->

## <a name="removing-items"></a><span data-ttu-id="c25de-238">項目の削除</span><span class="sxs-lookup"><span data-stu-id="c25de-238">Removing Items</span></span>

<span data-ttu-id="c25de-239">項目を削除するには、Windows PowerShell プロバイダーで[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)メソッドをオーバーライドして、`Remove-Item` コマンドレットからの呼び出しをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-239">To remove items, the Windows PowerShell provider must override the [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) method to support calls from the `Remove-Item` cmdlet.</span></span> <span data-ttu-id="c25de-240">このメソッドは、指定されたパスにあるデータストアから項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="c25de-240">This method deletes an item from the data store at the specified path.</span></span> <span data-ttu-id="c25de-241">@No__t_1 コマンドレットの `recurse` パラメーターが `true` に設定されている場合、メソッドは、そのレベルに関係なく、すべての子項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="c25de-241">If the `recurse` parameter of the `Remove-Item` cmdlet is set to `true`, the method removes all child items regardless of their level.</span></span> <span data-ttu-id="c25de-242">パラメーターが `false` に設定されている場合、メソッドは、指定されたパスの1つの項目のみを削除します。</span><span class="sxs-lookup"><span data-stu-id="c25de-242">If the parameter is set to `false`, the method removes only a single item at the specified path.</span></span>

<span data-ttu-id="c25de-243">このプロバイダーは項目の削除をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c25de-243">This provider does not support item removal.</span></span> <span data-ttu-id="c25de-244">ただし、次のコードは、 [Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)という既定の実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="c25de-244">However, the following code is the default implementation of [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem).</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderremoveitem](Msh_samplestestcmdlets#testproviderremoveitem)]  -->

#### <a name="things-to-remember-about-implementing-removeitem"></a><span data-ttu-id="c25de-245">RemoveItem の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="c25de-245">Things to Remember About Implementing RemoveItem</span></span>

<span data-ttu-id="c25de-246">[Containercmdletprovider. Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)の実装には、次の条件が当てはまる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-246">The following conditions may apply to your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem):</span></span>

- <span data-ttu-id="c25de-247">プロバイダークラスを定義すると、Windows PowerShell コンテナープロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。</span><span class="sxs-lookup"><span data-stu-id="c25de-247">When defining the provider class, a Windows PowerShell container provider might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="c25de-248">このような場合は、 [Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドの実装で、メソッドに渡されるパスが指定された機能の要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-248">In these cases, the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method needs to ensure that the path passed to the method meets the requirements of the specified capabilities.</span></span> <span data-ttu-id="c25de-249">これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...</span><span class="sxs-lookup"><span data-stu-id="c25de-249">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) and [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) properties.</span></span>

- <span data-ttu-id="c25de-250">既定では、このメソッドのオーバーライドでは、system.object [\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティが true に設定されていない限り、オブジェクトを削除しません。</span><span class="sxs-lookup"><span data-stu-id="c25de-250">By default, overrides of this method should not remove objects unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is set to true.</span></span> <span data-ttu-id="c25de-251">指定されたパスがコンテナーを示している場合、[このプロパティは必須ではあり](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)ません。</span><span class="sxs-lookup"><span data-stu-id="c25de-251">If the specified path indicates a container, the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is not required.</span></span>

- <span data-ttu-id="c25de-252">[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)の実装によって、循環リンクがある場合の無限の再帰を防ぐことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="c25de-252">Your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) is responsible for preventing infinite recursion when there are circular links, and the like.</span></span> <span data-ttu-id="c25de-253">このような状態を反映するには、適切な終了例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-253">An appropriate terminating exception should be thrown to reflect such a condition.</span></span>

- <span data-ttu-id="c25de-254">[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)メソッドの実装では、前に system.object を呼び出し、戻り値を確認する必要があります。これを行うには、前の手順を実行し[ます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)データストアに変更を加える。</span><span class="sxs-lookup"><span data-stu-id="c25de-254">Your implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) method should call [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) and check its return value before making any changes to the data store.</span></span> <span data-ttu-id="c25de-255">Containercmdletprovider を呼び出すと、が[`true` 返されます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)その後、 [\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)メソッドはを呼び出す必要があります。この場合は、を呼び出し[ます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)System.object は、危険性の高いシステム変更について追加のチェックとしてメソッドを続行します。</span><span class="sxs-lookup"><span data-stu-id="c25de-255">After the call to [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) returns `true`, the [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) method should call the [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) method as an additional check for potentially dangerous system modifications.</span></span>

## <a name="attaching-dynamic-parameters-to-the-remove-item-cmdlet"></a><span data-ttu-id="c25de-256">動的パラメーターを削除コマンドレットにアタッチする</span><span class="sxs-lookup"><span data-stu-id="c25de-256">Attaching Dynamic Parameters to the Remove-Item Cmdlet</span></span>

<span data-ttu-id="c25de-257">@No__t_0 コマンドレットでは、実行時に動的に指定される追加のパラメーターが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-257">Sometimes the `Remove-Item` cmdlet requires additional parameters that are specified dynamically at runtime.</span></span> <span data-ttu-id="c25de-258">これらの動的パラメーターを指定するには、コンテナープロバイダーが[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)メソッドを実装してこれらのパラメーターを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-258">To provide these dynamic parameters, the container provider must implement the [System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) method to handle these parameters.</span></span> <span data-ttu-id="c25de-259">このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の Parameterdictionary と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。 [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c25de-259">This method retrieves the dynamic parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="c25de-260">Windows PowerShell ランタイムは、返されたオブジェクトを使用して、`Remove-Item` コマンドレットにパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="c25de-260">The Windows PowerShell runtime uses the returned object to add the parameters to the `Remove-Item` cmdlet.</span></span>

<span data-ttu-id="c25de-261">このコンテナープロバイダーは、このメソッドを実装していません。</span><span class="sxs-lookup"><span data-stu-id="c25de-261">This container provider does not implement this method.</span></span> <span data-ttu-id="c25de-262">ただし、次のコードは、 [Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)の既定の実装であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="c25de-262">However, the following code is the default implementation of [System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters).</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderremoveitemdynamicparameters](Msh_samplestestcmdlets#testproviderremoveitemdynamicparameters)]  -->

## <a name="querying-for-child-items"></a><span data-ttu-id="c25de-263">子項目のクエリ</span><span class="sxs-lookup"><span data-stu-id="c25de-263">Querying for Child Items</span></span>

<span data-ttu-id="c25de-264">指定されたパスに子項目が存在するかどうかを確認するには、Windows PowerShell コンテナープロバイダーが[Haschilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems)メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-264">To check to see if child items exist at the specified path, the Windows PowerShell container provider must override the [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) method.</span></span> <span data-ttu-id="c25de-265">このメソッドは、項目に子がある場合は `true` を返し、それ以外の場合は `false` を返します。</span><span class="sxs-lookup"><span data-stu-id="c25de-265">This method returns `true` if the item has children, and `false` otherwise.</span></span> <span data-ttu-id="c25de-266">Null または空のパスの場合、メソッドはデータストア内のすべての項目を子と見なし、`true` を返します。</span><span class="sxs-lookup"><span data-stu-id="c25de-266">For a null or empty path, the method considers any items in the data store to be children and returns `true`.</span></span>

<span data-ttu-id="c25de-267">Containercmdletprovider のオーバーライドを次に示します。 [Haschilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems)メソッドします。</span><span class="sxs-lookup"><span data-stu-id="c25de-267">Here is the override for the [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) method.</span></span> <span data-ttu-id="c25de-268">チャンクパスヘルパーメソッドによって作成されたパス部分が3つ以上ある場合、このメソッドは `false` を返します。これは、データベースコンテナーとテーブルコンテナーのみが定義されているためです。</span><span class="sxs-lookup"><span data-stu-id="c25de-268">If there are more than two path parts created by the ChunkPath helper method, the method returns `false`, since only a database container and a table container are defined.</span></span> <span data-ttu-id="c25de-269">このヘルパーメソッドの詳細については、「 [Windows PowerShell 項目プロバイダーの作成](./creating-a-windows-powershell-item-provider.md)」で説明されている「chunkpath メソッド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c25de-269">For more information about this helper method, see the ChunkPath method is discussed in [Creating a Windows PowerShell Item Provider](./creating-a-windows-powershell-item-provider.md).</span></span>

```csharp
protected override bool HasChildItems( string path )
{
    return false;
} // HasChildItems
```

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L1094-L1097 "AccessDBProviderSample04.cs")]

#### <a name="things-to-remember-about-implementing-haschilditems"></a><span data-ttu-id="c25de-270">HasChildItems の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="c25de-270">Things to Remember About Implementing HasChildItems</span></span>

<span data-ttu-id="c25de-271">[Containercmdletprovider. Haschilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems)の実装には、次の条件が当てはまる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-271">The following conditions may apply to your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems):</span></span>

- <span data-ttu-id="c25de-272">コンテナープロバイダーが興味深いマウントポイントを含むルートを公開する場合、 [Containercmdletprovider Haschilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems)メソッドの実装は、null または空の場合に `true` を返す必要があります。パスの文字列が渡されます。</span><span class="sxs-lookup"><span data-stu-id="c25de-272">If the container provider exposes a root that contains interesting mount points, the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) method should return `true` when a null or an empty string is passed in for the path.</span></span>

## <a name="copying-items"></a><span data-ttu-id="c25de-273">項目のコピー</span><span class="sxs-lookup"><span data-stu-id="c25de-273">Copying Items</span></span>

<span data-ttu-id="c25de-274">項目をコピーするには、コンテナープロバイダーが[ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)メソッドを実装して、`Copy-Item` コマンドレットからの呼び出しをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-274">To copy items, the container provider must implement the [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) method to support calls from the `Copy-Item` cmdlet.</span></span> <span data-ttu-id="c25de-275">このメソッドは、コマンドレットの `path` パラメーターで示されている場所から、`copyPath` パラメーターで示されている場所にデータ項目をコピーします。</span><span class="sxs-lookup"><span data-stu-id="c25de-275">This method copies a data item from the location indicated by the `path` parameter of the cmdlet to the location indicated by the `copyPath` parameter.</span></span> <span data-ttu-id="c25de-276">@No__t_0 パラメーターが指定されている場合、メソッドはすべてのサブコンテナーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="c25de-276">If the `recurse` parameter is specified, the method copies all sub-containers.</span></span> <span data-ttu-id="c25de-277">パラメーターが指定されていない場合、メソッドは項目の1つのレベルのみをコピーします。</span><span class="sxs-lookup"><span data-stu-id="c25de-277">If the parameter is not specified, the method copies only a single level of items.</span></span>

<span data-ttu-id="c25de-278">このプロバイダーは、このメソッドを実装していません。</span><span class="sxs-lookup"><span data-stu-id="c25de-278">This provider does not implement this method.</span></span> <span data-ttu-id="c25de-279">ただし、次のコードは、 [ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)を既定で実装しているものです。</span><span class="sxs-lookup"><span data-stu-id="c25de-279">However, the following code is the default implementation of [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem).</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidercopyitem](Msh_samplestestcmdlets#testprovidercopyitem)]  -->

#### <a name="things-to-remember-about-implementing-copyitem"></a><span data-ttu-id="c25de-280">CopyItem の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="c25de-280">Things to Remember About Implementing CopyItem</span></span>

<span data-ttu-id="c25de-281">[ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)の実装には、次の条件が当てはまる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-281">The following conditions may apply to your implementation of [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem):</span></span>

- <span data-ttu-id="c25de-282">プロバイダークラスを定義すると、Windows PowerShell コンテナープロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。</span><span class="sxs-lookup"><span data-stu-id="c25de-282">When defining the provider class, a Windows PowerShell container provider might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="c25de-283">このような場合は、 [Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドの実装で、メソッドに渡されるパスが指定された機能の要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-283">In these cases, the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method needs to ensure that the path passed to the method meets the requirements of the specified capabilities.</span></span> <span data-ttu-id="c25de-284">これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...</span><span class="sxs-lookup"><span data-stu-id="c25de-284">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) and [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) properties.</span></span>

- <span data-ttu-id="c25de-285">既定では、このメソッドのオーバーライドでは、system.object [\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティが `true` に設定されていない限り、既存のオブジェクトにオブジェクトをコピーしません。</span><span class="sxs-lookup"><span data-stu-id="c25de-285">By default, overrides of this method should not copy objects over existing objects unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is set to `true`.</span></span> <span data-ttu-id="c25de-286">たとえば、c:\temp\abc.txt [\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティが `true` に設定されていない場合、FileSystem プロバイダーは既存の c:\abc.txt ファイルに対してをコピーしません。</span><span class="sxs-lookup"><span data-stu-id="c25de-286">For example, the FileSystem provider will not copy c:\temp\abc.txt over an existing c:\abc.txt file unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is set to `true`.</span></span> <span data-ttu-id="c25de-287">@No__t_0 パラメーターで指定されたパスが存在し、コンテナーを示している場合は、" [System.](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) ...................................</span><span class="sxs-lookup"><span data-stu-id="c25de-287">If the path specified in the `copyPath` parameter exists and indicates a container, the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is not required.</span></span> <span data-ttu-id="c25de-288">この場合、 [ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)は、`path` パラメーターで示される項目を、`copyPath` パラメーターで指定されたコンテナーに子としてコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-288">In this case, [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) should copy the item indicated by the `path` parameter to the container indicated by the `copyPath` parameter as a child.</span></span>

- <span data-ttu-id="c25de-289">[ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)の実装は、循環リンクがある場合に無限再帰を防ぐことを担当します。また、同様の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="c25de-289">Your implementation of [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) is responsible for preventing infinite recursion when there are circular links, and the like.</span></span> <span data-ttu-id="c25de-290">このような状態を反映するには、適切な終了例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-290">An appropriate terminating exception should be thrown to reflect such a condition.</span></span>

- <span data-ttu-id="c25de-291">[ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)メソッドの実装では、前に system.object を呼び出し、戻り値を確認する必要があります。これを行うには、前の手順を実行し[ます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)データストアに変更を加える。</span><span class="sxs-lookup"><span data-stu-id="c25de-291">Your implementation of the [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) method should call [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) and check its return value before making any changes to the data store.</span></span> <span data-ttu-id="c25de-292">ContainerCmdletProvider の呼び出しによって true[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)が返された後に、このメソッドはを呼び出す必要[System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)があります。この場合、このメソッドは、 [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)System.object は、危険性の高いシステム変更について追加のチェックとしてメソッドを続行します。</span><span class="sxs-lookup"><span data-stu-id="c25de-292">After the call to [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) returns true, the [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) method should call the [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) method as an additional check for potentially dangerous system modifications.</span></span> <span data-ttu-id="c25de-293">これらのメソッドの呼び出しの詳細については、「[項目名の変更](#renaming-items)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c25de-293">For more information about calling these methods, see [Rename Items](#renaming-items).</span></span>

## <a name="attaching-dynamic-parameters-to-the-copy-item-cmdlet"></a><span data-ttu-id="c25de-294">コピー項目のコマンドレットに動的パラメーターをアタッチする</span><span class="sxs-lookup"><span data-stu-id="c25de-294">Attaching Dynamic Parameters to the Copy-Item Cmdlet</span></span>

<span data-ttu-id="c25de-295">@No__t_0 コマンドレットでは、実行時に動的に指定される追加のパラメーターが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-295">Sometimes the `Copy-Item` cmdlet requires additional parameters that are specified dynamically at runtime.</span></span> <span data-ttu-id="c25de-296">これらの動的パラメーターを指定するには、Windows PowerShell コンテナープロバイダーで[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)メソッドを実装してこれらのパラメーターを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-296">To provide these dynamic parameters, the Windows PowerShell container provider must implement the [System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) method to handle these parameters.</span></span> <span data-ttu-id="c25de-297">このメソッドは、指定されたパスにある項目のパラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の[Parameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。素材.</span><span class="sxs-lookup"><span data-stu-id="c25de-297">This method retrieves the parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="c25de-298">Windows PowerShell ランタイムは、返されたオブジェクトを使用して、`Copy-Item` コマンドレットにパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="c25de-298">The Windows PowerShell runtime uses the returned object to add the parameters to the `Copy-Item` cmdlet.</span></span>

<span data-ttu-id="c25de-299">このプロバイダーは、このメソッドを実装していません。</span><span class="sxs-lookup"><span data-stu-id="c25de-299">This provider does not implement this method.</span></span> <span data-ttu-id="c25de-300">ただし、次のコードは、 [Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)の既定の実装であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="c25de-300">However, the following code is the default implementation of [System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters).</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidercopyitemdynamicparameters](Msh_samplestestcmdlets#testprovidercopyitemdynamicparameters)]  -->

## <a name="code-sample"></a><span data-ttu-id="c25de-301">コードサンプル</span><span class="sxs-lookup"><span data-stu-id="c25de-301">Code Sample</span></span>

<span data-ttu-id="c25de-302">完全なサンプルコードについては、「 [AccessDbProviderSample04 のコードサンプル](./accessdbprovidersample04-code-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c25de-302">For complete sample code, see [AccessDbProviderSample04 Code Sample](./accessdbprovidersample04-code-sample.md).</span></span>

## <a name="building-the-windows-powershell-provider"></a><span data-ttu-id="c25de-303">Windows PowerShell プロバイダーの構築</span><span class="sxs-lookup"><span data-stu-id="c25de-303">Building the Windows PowerShell Provider</span></span>

<span data-ttu-id="c25de-304">「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法」を](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)参照してください。</span><span class="sxs-lookup"><span data-stu-id="c25de-304">See [How to Register Cmdlets, Providers, and Host Applications](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-windows-powershell-provider"></a><span data-ttu-id="c25de-305">Windows PowerShell プロバイダーのテスト</span><span class="sxs-lookup"><span data-stu-id="c25de-305">Testing the Windows PowerShell Provider</span></span>

<span data-ttu-id="c25de-306">Windows powershell プロバイダーが Windows PowerShell に登録されている場合は、コマンドラインでサポートされているコマンドレットを実行してテストできます。</span><span class="sxs-lookup"><span data-stu-id="c25de-306">When your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line.</span></span> <span data-ttu-id="c25de-307">次の出力例では、架空の Access データベースが使用されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c25de-307">Be aware that the following example output uses a fictitious Access database.</span></span>

1. <span data-ttu-id="c25de-308">@No__t_0 コマンドレットを実行して、Access データベースの Customers テーブルから子項目の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="c25de-308">Run the `Get-ChildItem` cmdlet to retrieve the list of child items from a Customers table in the Access database.</span></span>

   ```powershell
   Get-ChildItem mydb:customers
   ```

   <span data-ttu-id="c25de-309">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c25de-309">The following output appears.</span></span>

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

2. <span data-ttu-id="c25de-310">@No__t_0 コマンドレットをもう一度実行して、テーブルのデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="c25de-310">Run the `Get-ChildItem` cmdlet again to retrieve the data of a table.</span></span>

   ```powershell
   (Get-ChildItem mydb:customers).data
   ```

   <span data-ttu-id="c25de-311">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c25de-311">The following output appears.</span></span>

   ```output
   TABLE_CAT   : c:\PS\northwind
   TABLE_SCHEM :
   TABLE_NAME  : Customers
   TABLE_TYPE  : TABLE
   REMARKS     :
   ```

3. <span data-ttu-id="c25de-312">ここで、`Get-Item` コマンドレットを使用して、データテーブル内の行0の項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="c25de-312">Now use the `Get-Item` cmdlet to retrieve the items at row 0 in the data table.</span></span>

   ```powershell
   Get-Item mydb:\customers\0
   ```

   <span data-ttu-id="c25de-313">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c25de-313">The following output appears.</span></span>

   ```output
   PSPath        : AccessDB::customers\0
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : False
   Data          : System.Data.DataRow
   RowNumber     : 0
   ```

4. <span data-ttu-id="c25de-314">@No__t_0 を再利用して、行0の項目のデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="c25de-314">Reuse `Get-Item` to retrieve the data for the items in row 0.</span></span>

   ```powershell
   (Get-Item mydb:\customers\0).data
   ```

   <span data-ttu-id="c25de-315">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c25de-315">The following output appears.</span></span>

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

5. <span data-ttu-id="c25de-316">次に、`New-Item` コマンドレットを使用して、既存のテーブルに行を追加します。</span><span class="sxs-lookup"><span data-stu-id="c25de-316">Now use the `New-Item` cmdlet to add a row to an existing table.</span></span> <span data-ttu-id="c25de-317">@No__t_0 パラメーターは、行への完全パスを指定し、テーブル内の既存の行数よりも大きい行番号を示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c25de-317">The `Path` parameter specifies the full path to the row, and must indicate a row number that is greater than the existing number of rows in the table.</span></span> <span data-ttu-id="c25de-318">@No__t_0 パラメーターは、追加する項目の型を指定する "row" を示します。</span><span class="sxs-lookup"><span data-stu-id="c25de-318">The `Type` parameter indicates "row" to specify that type of item to add.</span></span> <span data-ttu-id="c25de-319">最後に、`Value` パラメーターは、行の列値のコンマ区切りリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="c25de-319">Finally, the `Value` parameter specifies a comma-delimited list of column values for the row.</span></span>

   ```powershell
   New-Item -Path mydb:\Customers\3 -ItemType "row" -Value "3,CustomerFirstName,CustomerLastName,CustomerEmailAddress,CustomerTitle,CustomerCompany,CustomerPhone, CustomerAddress,CustomerCity,CustomerState,CustomerZip,CustomerCountry"
   ```

6. <span data-ttu-id="c25de-320">次のように、新しい項目の操作が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c25de-320">Verify the correctness of the new item operation as follows.</span></span>

   ```none
   PS mydb:\> cd Customers
   PS mydb:\Customers> (Get-Item 3).data
   ```

   <span data-ttu-id="c25de-321">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c25de-321">The following output appears.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c25de-322">関連項目</span><span class="sxs-lookup"><span data-stu-id="c25de-322">See Also</span></span>

[<span data-ttu-id="c25de-323">Windows PowerShell プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="c25de-323">Creating Windows PowerShell Providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="c25de-324">Windows PowerShell プロバイダーの設計</span><span class="sxs-lookup"><span data-stu-id="c25de-324">Designing Your Windows PowerShell Provider</span></span>](./designing-your-windows-powershell-provider.md)

[<span data-ttu-id="c25de-325">項目を実装する Windows PowerShell プロバイダー</span><span class="sxs-lookup"><span data-stu-id="c25de-325">Implementing an Item Windows PowerShell Provider</span></span>](./creating-a-windows-powershell-item-provider.md)

[<span data-ttu-id="c25de-326">ナビゲーション Windows PowerShell プロバイダーの実装</span><span class="sxs-lookup"><span data-stu-id="c25de-326">Implementing a Navigation Windows PowerShell Provider</span></span>](./creating-a-windows-powershell-navigation-provider.md)

[<span data-ttu-id="c25de-327">コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法</span><span class="sxs-lookup"><span data-stu-id="c25de-327">How to Register Cmdlets, Providers, and Host Applications</span></span>](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="c25de-328">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="c25de-328">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="c25de-329">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="c25de-329">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)
