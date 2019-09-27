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
# <a name="creating-a-windows-powershell-content-provider"></a><span data-ttu-id="9282f-102">Windows PowerShell コンテンツ プロバイダーを作成する</span><span class="sxs-lookup"><span data-stu-id="9282f-102">Creating a Windows PowerShell Content Provider</span></span>

<span data-ttu-id="9282f-103">このトピックでは、ユーザーがデータストア内の項目の内容を操作できるようにする Windows PowerShell プロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9282f-103">This topic describes how to create a Windows PowerShell provider that enables the user to manipulate the contents of the items in a data store.</span></span> <span data-ttu-id="9282f-104">その結果、項目の内容を操作できるプロバイダーは、Windows PowerShell コンテンツプロバイダーと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9282f-104">As a consequence, a provider that can manipulate the contents of items is referred to as a Windows PowerShell content provider.</span></span>

> [!NOTE]
> <span data-ttu-id="9282f-105">このプロバイダーのC#ソースファイル (AccessDBSampleProvider06.cs) をダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="9282f-105">You can download the C# source file (AccessDBSampleProvider06.cs) for this provider using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="9282f-106">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9282f-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="9282f-107">ダウンロードしたソースファイルは、  **\<PowerShell Samples >** ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="9282f-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>
>
> <span data-ttu-id="9282f-108">その他の Windows PowerShell プロバイダーの実装の詳細については、「 [Windows Powershell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9282f-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="define-the-windows-powershell-content-provider-class"></a><span data-ttu-id="9282f-109">Windows PowerShell コンテンツプロバイダークラスを定義する</span><span class="sxs-lookup"><span data-stu-id="9282f-109">Define the Windows PowerShell Content Provider Class</span></span>

<span data-ttu-id="9282f-110">Windows PowerShell コンテンツプロバイダーは、 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイスをサポートする .net クラスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-110">A Windows PowerShell content provider must create a .NET class that supports the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span> <span data-ttu-id="9282f-111">ここでは、このセクションで説明する項目プロバイダーのクラス定義を示します。</span><span class="sxs-lookup"><span data-stu-id="9282f-111">Here is the class definition for the item provider described in this section.</span></span>

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L32-L33 "AccessDBProviderSample06.cs")]

<span data-ttu-id="9282f-112">このクラス定義では、 [system.string 属性に2つのパラメーター](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)が含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9282f-112">Note that in this class definition, the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute includes two parameters.</span></span> <span data-ttu-id="9282f-113">最初のパラメーターは、Windows PowerShell によって使用されるプロバイダーのわかりやすい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9282f-113">The first parameter specifies a user-friendly name for the provider that is used by Windows PowerShell.</span></span> <span data-ttu-id="9282f-114">2番目のパラメーターは、コマンドの処理中にプロバイダーが Windows PowerShell ランタイムに公開する Windows PowerShell 固有の機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="9282f-114">The second parameter specifies the Windows PowerShell specific capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span> <span data-ttu-id="9282f-115">このプロバイダーには、Windows PowerShell 固有の機能は追加されていません。</span><span class="sxs-lookup"><span data-stu-id="9282f-115">For this provider, there are no added Windows PowerShell specific capabilities.</span></span>

## <a name="define-functionality-of-base-class"></a><span data-ttu-id="9282f-116">基本クラスの機能を定義する</span><span class="sxs-lookup"><span data-stu-id="9282f-116">Define Functionality of Base Class</span></span>

<span data-ttu-id="9282f-117">「 [Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」で説明されているように、さまざまなプロバイダーの機能を提供する他のいくつかのクラス[から、このクラスを](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)派生させることができます。</span><span class="sxs-lookup"><span data-stu-id="9282f-117">As described in [Design Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md), the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class derives from several other classes that provided different provider functionality.</span></span> <span data-ttu-id="9282f-118">そのため、Windows PowerShell コンテンツプロバイダーは、通常、これらのクラスによって提供されるすべての機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="9282f-118">A Windows PowerShell content provider, therefore, typically defines all of the functionality provided by those classes.</span></span>

<span data-ttu-id="9282f-119">セッション固有の初期化情報を追加したり、プロバイダーで使用されるリソースを解放したりするための機能を実装する方法の詳細については、「[基本的な Windows PowerShell プロバイダーの作成](./creating-a-basic-windows-powershell-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9282f-119">For more information about how to implement functionality for adding session-specific initialization information and for releasing resources that are used by the provider, see [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span> <span data-ttu-id="9282f-120">ただし、ここで説明するプロバイダーを含むほとんどのプロバイダーは、Windows PowerShell によって提供されるこの機能の既定の実装を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9282f-120">However, most providers, including the provider described here, can use the default implementation of this functionality that is provided by Windows PowerShell.</span></span>

<span data-ttu-id="9282f-121">データストアにアクセスするには、プロバイダーが[Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)基底クラスのメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-121">To access the data store, the provider must implement the methods of the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) base class.</span></span> <span data-ttu-id="9282f-122">これらのメソッドの実装の詳細については、「 [Windows PowerShell ドライブプロバイダーの作成](./creating-a-windows-powershell-drive-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9282f-122">For more information about implementing these methods, see [Creating a Windows PowerShell Drive Provider](./creating-a-windows-powershell-drive-provider.md).</span></span>

<span data-ttu-id="9282f-123">項目の取得、設定、クリアなど、データストアの項目を操作するには、プロバイダー[が、system.object クラスの基本クラス](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)によって提供されるメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-123">To manipulate the items of a data store, such as getting, setting, and clearing items, the provider must implement the methods provided by the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) base class.</span></span> <span data-ttu-id="9282f-124">これらのメソッドの実装の詳細については、「 [Windows PowerShell 項目プロバイダーの作成](./creating-a-windows-powershell-item-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9282f-124">For more information about implementing these methods, see [Creating a Windows PowerShell Item Provider](./creating-a-windows-powershell-item-provider.md).</span></span>

<span data-ttu-id="9282f-125">マルチレイヤーデータストアを操作するには、プロバイダーが[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)基底クラスによって提供されるメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-125">To work on multi-layer data stores, the provider must implement the methods provided by the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) base class.</span></span> <span data-ttu-id="9282f-126">これらのメソッドの実装の詳細については、「 [Windows PowerShell コンテナープロバイダーの作成](./creating-a-windows-powershell-container-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9282f-126">For more information about implementing these methods, see [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>

<span data-ttu-id="9282f-127">再帰コマンド、入れ子になったコンテナー、および相対パスをサポートするには、プロバイダー[が、system.servicemodel クラスの基底クラス](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-127">To support recursive commands, nested containers, and relative paths, the provider must implement the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) base class.</span></span> <span data-ttu-id="9282f-128">さらに、この Windows PowerShell コンテンツプロバイダーは、 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイスを、system.............. [navigationshell プロバイダー](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)基底クラスにアタッチできます。では、そのクラスによって提供されるメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-128">In addition, this Windows PowerShell content provider can attaches [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface to the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) base class, and must therefore implement the methods provided by that class.</span></span> <span data-ttu-id="9282f-129">詳細については、「これらのメソッドの実装」を参照してください。「[ナビゲーション Windows PowerShell プロバイダーの実装](./creating-a-windows-powershell-navigation-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9282f-129">For more information, see implementing those methods, see [Implement a Navigation Windows PowerShell Provider](./creating-a-windows-powershell-navigation-provider.md).</span></span>

## <a name="implementing-a-content-reader"></a><span data-ttu-id="9282f-130">コンテンツリーダーの実装</span><span class="sxs-lookup"><span data-stu-id="9282f-130">Implementing a Content Reader</span></span>

<span data-ttu-id="9282f-131">項目からコンテンツを読み取るには、プロバイダーが[Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader)から派生したコンテンツリーダークラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-131">To read content from an item, a provider must implements a content reader class that derives from [System.Management.Automation.Provider.Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader).</span></span> <span data-ttu-id="9282f-132">このプロバイダーのコンテンツリーダーは、データテーブル内の行の内容にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="9282f-132">The content reader for this provider allows access to the contents of a row in a data table.</span></span> <span data-ttu-id="9282f-133">コンテンツリーダークラスは、指定された行からデータを取得し、そのデータを表すリストを返す**Read**メソッドを定義します。また、コンテンツリーダーを移動する**Seek**メソッド、コンテンツリーダーを閉じる**Close**メソッド、および**Dispose**メソッド。</span><span class="sxs-lookup"><span data-stu-id="9282f-133">The content reader class defines a **Read** method that retrieves the data from the indicated row and returns a list representing that data, a **Seek** method that moves the content reader, a **Close** method that closes the content reader, and a **Dispose** method.</span></span>

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L2115-L2241 "AccessDBProviderSample06.cs")]

## <a name="implementing-a-content-writer"></a><span data-ttu-id="9282f-134">コンテンツライターの実装</span><span class="sxs-lookup"><span data-stu-id="9282f-134">Implementing a Content Writer</span></span>

<span data-ttu-id="9282f-135">コンテンツを項目に書き込むには、プロバイダーが[Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter)から派生したコンテンツライタークラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-135">To write content to an item, a provider must implement a content writer class derives from [System.Management.Automation.Provider.Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter).</span></span> <span data-ttu-id="9282f-136">コンテンツライタークラスは、指定された行のコンテンツ、コンテンツライターを移動する**Seek**メソッド、コンテンツライターを閉じる**Close**メソッド、および**Dispose**メソッドを**記述する書き込み**メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="9282f-136">The content writer class defines a **Write** method that writes the specified row content, a **Seek** method that moves the content writer, a **Close** method that closes the content writer, and a **Dispose** method.</span></span>

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L2250-L2394 "AccessDBProviderSample06.cs")]

## <a name="retrieving-the-content-reader"></a><span data-ttu-id="9282f-137">コンテンツリーダーを取得しています</span><span class="sxs-lookup"><span data-stu-id="9282f-137">Retrieving the Content Reader</span></span>

<span data-ttu-id="9282f-138">項目からコンテンツを取得するには、プロバイダーが[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)を実装して、 `Get-Content`コマンドレットをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-138">To get content from an item, the provider must implement the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) to support the `Get-Content` cmdlet.</span></span> <span data-ttu-id="9282f-139">このメソッドは、指定されたパスにある項目のコンテンツリーダーを返します。</span><span class="sxs-lookup"><span data-stu-id="9282f-139">This method returns the content reader for the item located at the specified path.</span></span> <span data-ttu-id="9282f-140">その後、リーダーオブジェクトを開いてコンテンツを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="9282f-140">The reader object can then be opened to read the content.</span></span>

<span data-ttu-id="9282f-141">ここでは、このプロバイダーのこのメソッドの[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)の実装を示していますが、</span><span class="sxs-lookup"><span data-stu-id="9282f-141">Here is the implementation of [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) for this method for this provider.</span></span>

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

#### <a name="things-to-remember-about-implementing-getcontentreader"></a><span data-ttu-id="9282f-142">GetContentReader の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="9282f-142">Things to Remember About Implementing GetContentReader</span></span>

<span data-ttu-id="9282f-143">[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)の実装には、次の条件が適用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-143">The following conditions may apply to an implementation of [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader):</span></span>

- <span data-ttu-id="9282f-144">プロバイダークラスを定義すると、Windows PowerShell コンテンツプロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。</span><span class="sxs-lookup"><span data-stu-id="9282f-144">When defining the provider class, a Windows PowerShell content provider might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="9282f-145">このような場合は、 [Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)メソッドを実装することで、メソッドに渡されるパスが指定された機能の要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-145">In these cases, the implementation of the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) method must ensure that the path passed to the method meets the requirements of the specified capabilities.</span></span> <span data-ttu-id="9282f-146">これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...</span><span class="sxs-lookup"><span data-stu-id="9282f-146">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) and [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) properties.</span></span>

- <span data-ttu-id="9282f-147">既定では、このメソッドをオーバーライドしても、ユーザーに表示されないオブジェクトのリーダーを取得することはできません。この場合、 [Force \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティがに`true`設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-147">By default, overrides of this method should not retrieve a reader for objects that are hidden from the user unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is set to `true`.</span></span> <span data-ttu-id="9282f-148">パスが、ユーザーおよびシステムから非表示になっている項目を表している場合は、エラーを書き込む必要があります。 [Force \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)をに`false`設定します。</span><span class="sxs-lookup"><span data-stu-id="9282f-148">An error should be written if the path represents an item that is hidden from the user and [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) is set to `false`.</span></span>

## <a name="attaching-dynamic-parameters-to-the-get-content-cmdlet"></a><span data-ttu-id="9282f-149">Get Content コマンドレットに動的パラメーターをアタッチする</span><span class="sxs-lookup"><span data-stu-id="9282f-149">Attaching Dynamic Parameters to the Get-Content Cmdlet</span></span>

<span data-ttu-id="9282f-150">コマンド`Get-Content`レットでは、実行時に動的に指定される追加のパラメーターが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-150">The `Get-Content` cmdlet might require additional parameters that are specified dynamically at runtime.</span></span> <span data-ttu-id="9282f-151">これらの動的なパラメーターを提供するには、Windows PowerShell コンテンツプロバイダーが[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters)メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-151">To provide these dynamic parameters, the Windows PowerShell content provider must implement the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreaderdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) method.</span></span> <span data-ttu-id="9282f-152">このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の[Parameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。素材.</span><span class="sxs-lookup"><span data-stu-id="9282f-152">This method retrieves dynamic parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="9282f-153">Windows PowerShell ランタイムは、返されたオブジェクトを使用して、コマンドレットにパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="9282f-153">The Windows PowerShell runtime uses the returned object to add the parameters to the cmdlet.</span></span>

<span data-ttu-id="9282f-154">この Windows PowerShell コンテナープロバイダーは、このメソッドを実装していません。</span><span class="sxs-lookup"><span data-stu-id="9282f-154">This Windows PowerShell container provider does not implement this method.</span></span> <span data-ttu-id="9282f-155">ただし、次のコードは、このメソッドの既定の実装です。</span><span class="sxs-lookup"><span data-stu-id="9282f-155">However, the following code is the default implementation of this method.</span></span>

```csharp
public object GetContentReaderDynamicParameters(string path)
{
    return null;
}
```

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1853-L1856 "AccessDBProviderSample06.cs")]

## <a name="retrieving-the-content-writer"></a><span data-ttu-id="9282f-156">コンテンツライターを取得する</span><span class="sxs-lookup"><span data-stu-id="9282f-156">Retrieving the Content Writer</span></span>

<span data-ttu-id="9282f-157">コンテンツを項目に書き込むには、プロバイダーが[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)を実装して、コマンドレット`Set-Content`と`Add-Content`コマンドレットをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-157">To write content to an item, the provider must implement the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) to support the `Set-Content` and `Add-Content` cmdlets.</span></span> <span data-ttu-id="9282f-158">このメソッドは、指定されたパスにある項目のコンテンツライターを返します。</span><span class="sxs-lookup"><span data-stu-id="9282f-158">This method returns the content writer for the item located at the specified path.</span></span>

<span data-ttu-id="9282f-159">ここでは、このメソッドの[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)の実装を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="9282f-159">Here is the implementation of [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) for this method.</span></span>

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

#### <a name="things-to-remember-about-implementing-getcontentwriter"></a><span data-ttu-id="9282f-160">GetContentWriter の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="9282f-160">Things to Remember About Implementing GetContentWriter</span></span>

<span data-ttu-id="9282f-161">[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)の実装には、次の条件が当てはまる場合があります:。</span><span class="sxs-lookup"><span data-stu-id="9282f-161">The following conditions may apply to your implementation of [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter):</span></span>

- <span data-ttu-id="9282f-162">プロバイダークラスを定義すると、Windows PowerShell コンテンツプロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。</span><span class="sxs-lookup"><span data-stu-id="9282f-162">When defining the provider class, a Windows PowerShell content provider might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="9282f-163">このような場合は、 [Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)メソッドを実装することで、メソッドに渡されるパスが指定された機能の要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-163">In these cases, the implementation of the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) method must ensure that the path passed to the method meets the requirements of the specified capabilities.</span></span> <span data-ttu-id="9282f-164">これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...</span><span class="sxs-lookup"><span data-stu-id="9282f-164">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) and [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) properties.</span></span>

- <span data-ttu-id="9282f-165">既定では、このメソッドのオーバーライドでは、ユーザーに表示されないオブジェクトのライターを取得しないでください。この場合、 [Force \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティがに`true`設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-165">By default, overrides of this method should not retrieve a writer for objects that are hidden from the user unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is set to `true`.</span></span> <span data-ttu-id="9282f-166">パスが、ユーザーおよびシステムから非表示になっている項目を表している場合は、エラーを書き込む必要があります。 [Force \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)をに`false`設定します。</span><span class="sxs-lookup"><span data-stu-id="9282f-166">An error should be written if the path represents an item that is hidden from the user and [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) is set to `false`.</span></span>

## <a name="attaching-dynamic-parameters-to-the-add-content-and-set-content-cmdlets"></a><span data-ttu-id="9282f-167">コンテンツの追加とコンテンツの設定コマンドレットへの動的パラメーターのアタッチ</span><span class="sxs-lookup"><span data-stu-id="9282f-167">Attaching Dynamic Parameters to the Add-Content and Set-Content Cmdlets</span></span>

<span data-ttu-id="9282f-168">`Add-Content` および`Set-Content`コマンドレットには、ランタイムを追加する追加の動的パラメーターが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-168">The `Add-Content` and `Set-Content` cmdlets might require additional dynamic parameters that are added a runtime.</span></span> <span data-ttu-id="9282f-169">これらの動的パラメーターを指定するには、Windows PowerShell コンテンツプロバイダーは、これらのパラメーターを処理するために[Icontentcmdletprovider \* Getcontentwriterdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters)メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-169">To provide these dynamic parameters, the Windows PowerShell content provider must implement the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriterdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) method to handle these parameters.</span></span> <span data-ttu-id="9282f-170">このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の[Parameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。素材.</span><span class="sxs-lookup"><span data-stu-id="9282f-170">This method retrieves dynamic parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="9282f-171">Windows PowerShell ランタイムは、返されたオブジェクトを使用して、コマンドレットにパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="9282f-171">The Windows PowerShell runtime uses the returned object to add the parameters to the cmdlets.</span></span>

<span data-ttu-id="9282f-172">この Windows PowerShell コンテナープロバイダーは、このメソッドを実装していません。</span><span class="sxs-lookup"><span data-stu-id="9282f-172">This Windows PowerShell container provider does not implement this method.</span></span> <span data-ttu-id="9282f-173">ただし、次のコードは、このメソッドの既定の実装です。</span><span class="sxs-lookup"><span data-stu-id="9282f-173">However, the following code is the default implementation of this method.</span></span>

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1887-L1890 "AccessDBProviderSample06.cs")]

## <a name="clearing-content"></a><span data-ttu-id="9282f-174">コンテンツのクリア</span><span class="sxs-lookup"><span data-stu-id="9282f-174">Clearing Content</span></span>

<span data-ttu-id="9282f-175">コンテンツプロバイダーは、 `Clear-Content`コマンドレットをサポートするために[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドを実装しています。</span><span class="sxs-lookup"><span data-stu-id="9282f-175">Your content provider implements the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method in support of the `Clear-Content` cmdlet.</span></span> <span data-ttu-id="9282f-176">このメソッドは、指定されたパスにある項目の内容を削除しますが、項目はそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="9282f-176">This method removes the contents of the item at the specified path, but leaves the item intact.</span></span>

<span data-ttu-id="9282f-177">次に示すのは、このプロバイダーの[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="9282f-177">Here is the implementation of the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method for this provider.</span></span>

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1775-L1812 "AccessDBProviderSample06.cs")]

#### <a name="things-to-remember-about-implementing-clearcontent"></a><span data-ttu-id="9282f-178">ClearContent の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="9282f-178">Things to Remember About Implementing ClearContent</span></span>

<span data-ttu-id="9282f-179">[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)の実装には、次の条件が当てはまる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-179">The following conditions may apply to an implementation of [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent):</span></span>

- <span data-ttu-id="9282f-180">プロバイダークラスを定義すると、Windows PowerShell コンテンツプロバイダーは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、[システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙体から宣言できます。</span><span class="sxs-lookup"><span data-stu-id="9282f-180">When defining the provider class, a Windows PowerShell content provider might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="9282f-181">このような場合は、 [Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドを実装することで、メソッドに渡されるパスが指定された機能の要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-181">In these cases, the implementation of the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method must ensure that the path passed to the method meets the requirements of the specified capabilities.</span></span> <span data-ttu-id="9282f-182">これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、 ["..](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .............................................. [...](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) ...</span><span class="sxs-lookup"><span data-stu-id="9282f-182">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) and [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) properties.</span></span>

- <span data-ttu-id="9282f-183">既定では、このメソッドをオーバーライドしても、ユーザーに表示されないオブジェクトの内容を消去することはできません。ただし、 [Force \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティがに`true`設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-183">By default, overrides of this method should not clear the contents of objects that are hidden from the user unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is set to `true`.</span></span> <span data-ttu-id="9282f-184">パスが、ユーザーおよびシステムから非表示になっている項目を表している場合は、エラーを書き込む必要があります。 [Force \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)をに`false`設定します。</span><span class="sxs-lookup"><span data-stu-id="9282f-184">An error should be written if the path represents an item that is hidden from the user and [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) is set to `false`.</span></span>

- <span data-ttu-id="9282f-185">[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドを実装するには、system.object を呼び出して、戻り値を確認する必要があります。このメソッドの戻り値を確認し[ます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)データストアに変更を加える前。</span><span class="sxs-lookup"><span data-stu-id="9282f-185">Your implementation of the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method should call [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) and verify its return value before making any changes to the data store.</span></span> <span data-ttu-id="9282f-186">このメソッドは、コンテンツのクリアなど、データストアに変更が加えられたときの操作の実行を確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9282f-186">This method is used to confirm execution of an operation when a change is made to the data store, such as clearing content.</span></span> <span data-ttu-id="9282f-187">[System.](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) ................................................................表示する内容を決定します。</span><span class="sxs-lookup"><span data-stu-id="9282f-187">The [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) method sends the name of the resource to be changed to the user, with the Windows PowerShell runtime handling any command-line settings or preference variables in determining what should be displayed.</span></span>

  <span data-ttu-id="9282f-188">[Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)を呼び出すと、が返さ`true`れます。その[ためには](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)、「」という[メソッドを呼び出す必要があります。この場合、System.](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) ........</span><span class="sxs-lookup"><span data-stu-id="9282f-188">After the call to [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) returns `true`, the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method should call the [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) method.</span></span> <span data-ttu-id="9282f-189">このメソッドは、ユーザーにメッセージを送信して、操作を続行する必要があるかどうかを確認するフィードバックを許可します。</span><span class="sxs-lookup"><span data-stu-id="9282f-189">This method sends a message to the user to allow feedback to verify if the operation should be continued.</span></span> <span data-ttu-id="9282f-190">System.object を呼び出すと、危険性の高いシステム変更を追加で確認できるように[なります。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)</span><span class="sxs-lookup"><span data-stu-id="9282f-190">The call to [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) allows an additional check for potentially dangerous system modifications.</span></span>

## <a name="attaching-dynamic-parameters-to-the-clear-content-cmdlet"></a><span data-ttu-id="9282f-191">Clear Content コマンドレットへの動的パラメーターのアタッチ</span><span class="sxs-lookup"><span data-stu-id="9282f-191">Attaching Dynamic Parameters to the Clear-Content Cmdlet</span></span>

<span data-ttu-id="9282f-192">コマンド`Clear-Content`レットには、実行時に追加される追加の動的パラメーターが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-192">The `Clear-Content` cmdlet might require additional dynamic parameters that are added at runtime.</span></span> <span data-ttu-id="9282f-193">これらの動的パラメーターを指定するには、Windows PowerShell コンテンツプロバイダーは、これらのパラメーターを処理するために[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters)メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-193">To provide these dynamic parameters, the Windows PowerShell content provider must implement the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontentdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) method to handle these parameters.</span></span> <span data-ttu-id="9282f-194">このメソッドは、指定されたパスにある項目のパラメーターを取得します。</span><span class="sxs-lookup"><span data-stu-id="9282f-194">This method retrieves the parameters for the item at the indicated path.</span></span> <span data-ttu-id="9282f-195">このメソッドは、指定されたパスにある項目の動的パラメーターを取得し、コマンドレットクラスまたは system.servicemodel 型の[Parameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)と同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。素材.</span><span class="sxs-lookup"><span data-stu-id="9282f-195">This method retrieves dynamic parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="9282f-196">Windows PowerShell ランタイムは、返されたオブジェクトを使用して、コマンドレットにパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="9282f-196">The Windows PowerShell runtime uses the returned object to add the parameters to the cmdlet.</span></span>

<span data-ttu-id="9282f-197">この Windows PowerShell コンテナープロバイダーは、このメソッドを実装していません。</span><span class="sxs-lookup"><span data-stu-id="9282f-197">This Windows PowerShell container provider does not implement this method.</span></span> <span data-ttu-id="9282f-198">ただし、次のコードは、このメソッドの既定の実装です。</span><span class="sxs-lookup"><span data-stu-id="9282f-198">However, the following code is the default implementation of this method.</span></span>

```csharp
public object ClearContentDynamicParameters(string path)
{
    return null;
}
```

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1819-L1822 "AccessDBProviderSample06.cs")]

## <a name="code-sample"></a><span data-ttu-id="9282f-199">コードサンプル</span><span class="sxs-lookup"><span data-stu-id="9282f-199">Code Sample</span></span>

<span data-ttu-id="9282f-200">完全なサンプルコードについては、「 [AccessDbProviderSample06 のコードサンプル](./accessdbprovidersample06-code-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9282f-200">For complete sample code, see [AccessDbProviderSample06 Code Sample](./accessdbprovidersample06-code-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="9282f-201">オブジェクトの種類と書式設定の定義</span><span class="sxs-lookup"><span data-stu-id="9282f-201">Defining Object Types and Formatting</span></span>

<span data-ttu-id="9282f-202">プロバイダーを作成する場合は、既存のオブジェクトにメンバーを追加したり、新しいオブジェクトを定義したりすることが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-202">When writing a provider, it may be necessary to add members to existing objects or define new objects.</span></span> <span data-ttu-id="9282f-203">この処理が完了したら、オブジェクトのメンバーを識別するために Windows PowerShell で使用できる型ファイルと、オブジェクトの表示方法を定義するフォーマットファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9282f-203">When this is done, you must create a Types file that Windows PowerShell can use to identify the members of the object and a Format file that defines how the object is displayed.</span></span> <span data-ttu-id="9282f-204">詳細については、「[オブジェクトの種類と書式設定の拡張](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9282f-204">For more information, see [Extending Object Types and Formatting](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-windows-powershell-provider"></a><span data-ttu-id="9282f-205">Windows PowerShell プロバイダーの構築</span><span class="sxs-lookup"><span data-stu-id="9282f-205">Building the Windows PowerShell Provider</span></span>

<span data-ttu-id="9282f-206">「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法」を](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)参照してください。</span><span class="sxs-lookup"><span data-stu-id="9282f-206">See [How to Register Cmdlets, Providers, and Host Applications](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-windows-powershell-provider"></a><span data-ttu-id="9282f-207">Windows PowerShell プロバイダーのテスト</span><span class="sxs-lookup"><span data-stu-id="9282f-207">Testing the Windows PowerShell Provider</span></span>

<span data-ttu-id="9282f-208">Windows powershell プロバイダーが Windows PowerShell に登録されている場合は、コマンドラインでサポートされているコマンドレットを実行してテストできます。</span><span class="sxs-lookup"><span data-stu-id="9282f-208">When your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line.</span></span> <span data-ttu-id="9282f-209">たとえば、サンプルコンテンツプロバイダーをテストします。</span><span class="sxs-lookup"><span data-stu-id="9282f-209">For example, test the sample content provider.</span></span>

<span data-ttu-id="9282f-210">コマンドレットを使用し`Path`て、パラメーターで指定されたパスにあるデータベーステーブル内の指定された項目の内容を取得します。 `Get-Content`</span><span class="sxs-lookup"><span data-stu-id="9282f-210">Use the `Get-Content` cmdlet to retrieve the contents of specified item in the database table at the path specified by the `Path` parameter.</span></span> <span data-ttu-id="9282f-211">パラメーター `ReadCount`は、定義されたコンテンツリーダーが読み取る項目の数を指定します (既定値は 1)。</span><span class="sxs-lookup"><span data-stu-id="9282f-211">The `ReadCount` parameter specifies the number of items for the defined content reader to read (default 1).</span></span> <span data-ttu-id="9282f-212">次のコマンドを入力すると、コマンドレットはテーブルから2つの行 (項目) を取得し、その内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="9282f-212">With the following command entry, the cmdlet retrieves two rows (items) from the table and displays their contents.</span></span> <span data-ttu-id="9282f-213">次の出力例では、架空の Access データベースが使用されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9282f-213">Note that the following example output uses a fictitious Access database.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9282f-214">関連項目</span><span class="sxs-lookup"><span data-stu-id="9282f-214">See Also</span></span>

[<span data-ttu-id="9282f-215">Windows PowerShell プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="9282f-215">Creating Windows PowerShell providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="9282f-216">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="9282f-216">Design Your Windows PowerShell provider</span></span>](./designing-your-windows-powershell-provider.md)

[<span data-ttu-id="9282f-217">オブジェクトの種類と書式設定の拡張</span><span class="sxs-lookup"><span data-stu-id="9282f-217">Extending Object Types and Formatting</span></span>](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="9282f-218">ナビゲーション Windows PowerShell プロバイダーを実装する</span><span class="sxs-lookup"><span data-stu-id="9282f-218">Implement a Navigation Windows PowerShell provider</span></span>](./creating-a-windows-powershell-navigation-provider.md)

[<span data-ttu-id="9282f-219">コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法</span><span class="sxs-lookup"><span data-stu-id="9282f-219">How to Register Cmdlets, Providers, and Host Applications</span></span>](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="9282f-220">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="9282f-220">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="9282f-221">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="9282f-221">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)
