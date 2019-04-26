---
title: Windows PowerShell ナビゲーション プロバイダーを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- navigation providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], navigation provider
ms.assetid: 8bd3224d-ca6f-4640-9464-cb4d9f4e13b1
caps.latest.revision: 5
ms.openlocfilehash: 40454f880b57d5b3a8a8ded21c8c97aebba027fe
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081854"
---
# <a name="creating-a-windows-powershell-navigation-provider"></a><span data-ttu-id="3d3e6-102">Windows PowerShell ナビゲーション プロバイダーを作成する</span><span class="sxs-lookup"><span data-stu-id="3d3e6-102">Creating a Windows PowerShell Navigation Provider</span></span>

<span data-ttu-id="3d3e6-103">このトピックでは、データ ストアを移動できる Windows PowerShell ナビゲーション プロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-103">This topic describes how to create a Windows PowerShell navigation provider that can navigate the data store.</span></span> <span data-ttu-id="3d3e6-104">この種類のプロバイダーには、再帰的なコマンド、入れ子になったコンテナー、および相対パスがサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-104">This type of provider supports recursive commands, nested containers, and relative paths.</span></span>

> [!NOTE]
> <span data-ttu-id="3d3e6-105">ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と .NET Framework 3.0 ランタイム コンポーネントを使用して、このプロバイダーのソース ファイル (AccessDBSampleProvider05.cs)。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-105">You can download the C# source file (AccessDBSampleProvider05.cs) for this provider using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="3d3e6-106">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="3d3e6-107">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>
>
> <span data-ttu-id="3d3e6-108">その他の Windows PowerShell プロバイダーの実装の詳細については、次を参照してください。 [Your Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

<span data-ttu-id="3d3e6-109">ここで説明されているプロバイダーでは、ドライブとして Access データベースのユーザーのハンドルが有効に、ユーザーがデータベース内のデータ テーブルに移動できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-109">The provider described here enables the user handle an Access database as a drive so that the user can navigate to the data tables in the database.</span></span> <span data-ttu-id="3d3e6-110">独自のナビゲーション プロバイダーを作成するときに、ナビゲーションのために必要なドライブ修飾パス、相対パスの正規化、データ ストアと子の名前を取得し、アイテムの親パスを取得し、テストするメソッドのアイテムを移動するメソッドを実装できます。アイテムを識別するために、コンテナーです。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-110">When creating your own navigation provider, you can implement methods that can make drive-qualified paths required for navigation, normalize relative paths, move items of the data store, as well as methods that get child names, get the parent path of an item, and test to identify if an item is a container.</span></span>

> [!CAUTION]
> <span data-ttu-id="3d3e6-111">注意この設計が、名前の ID を持つフィールドを持つデータベースを想定していると、フィールドの型がなければなりません。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-111">Be aware that this design assumes a database that has a field with the name ID, and that the type of the field is LongInteger.</span></span>

<span data-ttu-id="3d3e6-112">次の一覧には、このトピックのセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-112">The following list includes sections in this topic.</span></span> <span data-ttu-id="3d3e6-113">Windows PowerShell ナビゲーション プロバイダーの記述に慣れていない場合は、出現する順序では、この情報を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-113">If you are unfamiliar with writing a Windows PowerShell navigation provider, read this information in the order that it appears.</span></span> <span data-ttu-id="3d3e6-114">ただし、Windows PowerShell ナビゲーション プロバイダーの作成に習熟する場合は、直接」に進んでください必要な情報。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-114">However, if you are familiar with writing a Windows PowerShell navigation provider, please go directly to the information that you need.</span></span>

- [<span data-ttu-id="3d3e6-115">PS ナビゲーション プロバイダー クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-115">Defining a PS Navigation Provider Class</span></span>](#Define-the-Windows-PowerShell-provider)

- [<span data-ttu-id="3d3e6-116">基本機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-116">Defining Base Functionality</span></span>](#Defining-Base-Functionality)

- [<span data-ttu-id="3d3e6-117">PS パスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-117">Creating a PS Path</span></span>](#Creating-a-Windows-PowerShell-Path)

- [<span data-ttu-id="3d3e6-118">親パスを取得します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-118">Retrieving the Parent Path</span></span>](#Retrieving-the-Parent-Path)

- [<span data-ttu-id="3d3e6-119">子のパス名を取得します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-119">Retrieving the Child Path Name</span></span>](#Retrieve-the-Child-Path-Name)

- [<span data-ttu-id="3d3e6-120">項目がコンテナーであるを決定します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-120">Determining if an Item is a Container</span></span>](#Determining-if-an-Item-is-a-Container)

- [<span data-ttu-id="3d3e6-121">アイテムを移動します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-121">Moving an Item</span></span>](#Moving-an-Item)

- [<span data-ttu-id="3d3e6-122">動的パラメーターをアタッチ、`Move-Item`コマンドレット</span><span class="sxs-lookup"><span data-stu-id="3d3e6-122">Attaching Dynamic Parameters to the `Move-Item` Cmdlet</span></span>](#Attaching-Dynamic-Parameters-to-the-Move-Item-Cmdlet)

- [<span data-ttu-id="3d3e6-123">相対パスの正規化</span><span class="sxs-lookup"><span data-stu-id="3d3e6-123">Normalizing a Relative Path</span></span>](#Normalizing-a-Relative-Path)

- [<span data-ttu-id="3d3e6-124">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="3d3e6-124">Code Sample</span></span>](#Code-Sample)

- [<span data-ttu-id="3d3e6-125">オブジェクトの種類を定義して、書式設定</span><span class="sxs-lookup"><span data-stu-id="3d3e6-125">Defining Object Types and Formatting</span></span>](#Defining-Object-Types-and-Formatting)

- [<span data-ttu-id="3d3e6-126">Windows PowerShell プロバイダーのビルド</span><span class="sxs-lookup"><span data-stu-id="3d3e6-126">Building the Windows PowerShell Provider</span></span>](#Building-the-Windows-PowerShell-provider)

- [<span data-ttu-id="3d3e6-127">Windows PowerShell プロバイダーのテスト</span><span class="sxs-lookup"><span data-stu-id="3d3e6-127">Testing the Windows PowerShell Provider</span></span>](#Testing-the-Windows-PowerShell-provider)

## <a name="define-the-windows-powershell-provider"></a><span data-ttu-id="3d3e6-128">Windows PowerShell プロバイダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-128">Define the Windows PowerShell provider</span></span>

<span data-ttu-id="3d3e6-129">Windows PowerShell ナビゲーション プロバイダーから派生する .NET クラスを作成する必要があります、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)基本クラス。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-129">A Windows PowerShell navigation provider must create a .NET class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) base class.</span></span> <span data-ttu-id="3d3e6-130">このセクションで説明されているナビゲーション プロバイダーのクラス定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-130">Here is the class definition for the navigation provider described in this section.</span></span>

[!code-csharp[AccessDBProviderSample05.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs#L31-L32 "AccessDBProviderSample05.cs")]

<span data-ttu-id="3d3e6-131">なお、このプロバイダーで、 [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)属性には、2 つのパラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-131">Note that in this provider, the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute includes two parameters.</span></span> <span data-ttu-id="3d3e6-132">最初のパラメーターには、Windows PowerShell で使用されるプロバイダーのわかりやすい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-132">The first parameter specifies a user-friendly name for the provider that is used by Windows PowerShell.</span></span> <span data-ttu-id="3d3e6-133">2 番目のパラメーターには、プロバイダーがコマンドの処理中に、Windows PowerShell ランタイムに公開する Windows PowerShell の特定機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-133">The second parameter specifies the Windows PowerShell specific capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span> <span data-ttu-id="3d3e6-134">このプロバイダーに追加される Windows PowerShell の特定の機能はありません。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-134">For this provider, there are no Windows PowerShell specific capabilities that are added.</span></span>

## <a name="defining-base-functionality"></a><span data-ttu-id="3d3e6-135">基本機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-135">Defining Base Functionality</span></span>

<span data-ttu-id="3d3e6-136">」の説明に従って[デザイン、PS プロバイダー](./designing-your-windows-powershell-provider.md)、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)基底クラスが別のプロバイダーが提供されるその他のいくつかのクラスから派生機能。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-136">As described in [Design Your PS Provider](./designing-your-windows-powershell-provider.md), the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) base class derives from several other classes that provided different provider functionality.</span></span> <span data-ttu-id="3d3e6-137">Windows PowerShell ナビゲーション プロバイダーでは、そのため、する必要があります定義のすべてのクラスが提供する機能。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-137">A Windows PowerShell navigation provider, therefore, must define all of the functionality provided by those classes.</span></span>

<span data-ttu-id="3d3e6-138">セッション固有の初期化情報を追加して、プロバイダーによって使用されているリソースを解放するための機能を実装するを参照してください。[基本的な PS プロバイダーを作成する](./creating-a-basic-windows-powershell-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-138">To implement functionality for adding session-specific initialization information and for releasing resources that are used by the provider, see [Creating a Basic PS Provider](./creating-a-basic-windows-powershell-provider.md).</span></span> <span data-ttu-id="3d3e6-139">ただし、ほとんどのプロバイダー (ここで説明されているプロバイダーを含む) は、Windows PowerShell によって提供されるこの機能の既定の実装を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-139">However, most providers (including the provider described here) can use the default implementation of this functionality provided by Windows PowerShell.</span></span>

<span data-ttu-id="3d3e6-140">を使用、Windows PowerShell ドライブをデータ ストアへのアクセスを取得するには、のメソッドを実装する必要があります、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)基本クラス。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-140">To get access to the data store through a Windows PowerShell drive, you must implement the methods of the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) base class.</span></span> <span data-ttu-id="3d3e6-141">これらのメソッドの実装の詳細については、次を参照してください。 [Windows PowerShell ドライブ プロバイダーを作成する](./creating-a-windows-powershell-drive-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-141">For more information about implementing these methods, see [Creating a Windows PowerShell Drive Provider](./creating-a-windows-powershell-drive-provider.md).</span></span>

<span data-ttu-id="3d3e6-142">プロバイダーの取得、設定、および消去の項目などのデータ ストアの項目を操作するによって提供されるメソッドを実装する必要があります、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)基本クラス。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-142">To manipulate the items of a data store, such as getting, setting, and clearing items, the provider must implement the methods provided by the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) base class.</span></span> <span data-ttu-id="3d3e6-143">これらのメソッドの実装の詳細については、次を参照してください。 [Windows PowerShell 項目プロバイダーを作成する](./creating-a-windows-powershell-item-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-143">For more information about implementing these methods, see [Creating an Windows PowerShell Item Provider](./creating-a-windows-powershell-item-provider.md).</span></span>

<span data-ttu-id="3d3e6-144">子項目、または、データ ストアとして作成、コピー、名前の変更、およびアイテムを削除するメソッドの名前を取得するには、によって提供されるメソッドを実装する必要があります、 [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)基本クラス。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-144">To get to the child items, or their names, of the data store, as well as methods that create, copy, rename, and remove items, you must implement the methods provided by the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) base class.</span></span> <span data-ttu-id="3d3e6-145">これらのメソッドの実装の詳細については、次を参照してください。 [Windows PowerShell コンテナー プロバイダーを作成する](./creating-a-windows-powershell-container-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-145">For more information about implementing these methods, see [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>

## <a name="creating-a-windows-powershell-path"></a><span data-ttu-id="3d3e6-146">Windows PowerShell パスの作成</span><span class="sxs-lookup"><span data-stu-id="3d3e6-146">Creating a Windows PowerShell Path</span></span>

<span data-ttu-id="3d3e6-147">Windows PowerShell ナビゲーション プロバイダーでは、プロバイダーの内部の Windows PowerShell パスを使用して、データ ストアの項目を移動します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-147">Windows PowerShell navigation provider use a provider-internal Windows PowerShell path to navigate the items of the data store.</span></span> <span data-ttu-id="3d3e6-148">プロバイダーの内部パス プロバイダーを作成する必要があります実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)結合パス コマンドレットからをサポートするメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-148">To create a provider-internal path the provider must implement the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method to supports calls from the Combine-Path cmdlet.</span></span> <span data-ttu-id="3d3e6-149">このメソッドは、親と子パス間のプロバイダー固有のパス区切り記号を使用して、プロバイダーの内部パスに、親と子パスを結合します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-149">This method combines a parent and child path into a provider-internal path, using a provider-specific path separator between the parent and child paths.</span></span>

<span data-ttu-id="3d3e6-150">既定の実装はでパスを受け取り「/」または"\\「へのパスの区切り文字を正規化パスの区切り文字として」\\"を含む文字列を返します、親と子パス部分を組み合わせて、それらの間の区切り記号、結合されたパス。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-150">The default implementation takes paths with "/" or "\\" as the path separator, normalizes the path separator to "\\", combines the parent and child path parts with the separator between them, and then returns a string that contains the combined paths.</span></span>

<span data-ttu-id="3d3e6-151">このナビゲーション プロバイダーは、このメソッドを実装していません。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-151">This navigation provider does not implement this method.</span></span> <span data-ttu-id="3d3e6-152">ただし、次のコードは、の既定の実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)メソッド。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-152">However, the following code is the default implementation of the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermakepath](Msh_samplestestcmdlets#testprovidermakepath)]  -->

#### <a name="things-to-remember-about-implementing-makepath"></a><span data-ttu-id="3d3e6-153">MakePath の実装に関する注意点</span><span class="sxs-lookup"><span data-stu-id="3d3e6-153">Things to Remember About Implementing MakePath</span></span>

<span data-ttu-id="3d3e6-154">実装に、次の条件が適用[System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath):</span><span class="sxs-lookup"><span data-stu-id="3d3e6-154">The following conditions may apply to your implementation of [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath):</span></span>

- <span data-ttu-id="3d3e6-155">実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)メソッドは、プロバイダーの名前空間で有効な完全修飾パスとしてパスを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-155">Your implementation of the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method should not validate the path as a legal fully-qualified path in the provider namespace.</span></span> <span data-ttu-id="3d3e6-156">各パラメーターは、パスの一部を表すことができますのみと、結合の部分では、完全修飾パスが生成されないことに注意します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-156">Be aware that each parameter can only represent a part of a path, and the combined parts might not generate a fully-qualified path.</span></span> <span data-ttu-id="3d3e6-157">たとえば、 [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)で"windows \system32"が表示される可能性があります、filesystem プロバイダーのメソッド、`parent`パラメーターは、「月」で、 `child`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-157">For example, the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method for the filesystem provider might receive "windows\system32" in the `parent` parameter and "abc.dll" in the `child` parameter.</span></span> <span data-ttu-id="3d3e6-158">メソッドは、これらの値を結合、"\\"区切り記号および返します"windows\system32\abc.dll"、完全修飾ファイル システム パスではないです。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-158">The method joins these values with the "\\" separator and returns "windows\system32\abc.dll", which is not a fully-qualified file system path.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="3d3e6-159">呼び出しで指定されたパスの一部[System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)プロバイダーの名前空間で使用できない文字が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-159">The path parts provided in the call to [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) might contain characters not allowed in the provider namespace.</span></span> <span data-ttu-id="3d3e6-160">これらの文字がワイルドカードの展開の使用はほとんどの場合と、このメソッドの実装は削除されません。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-160">These characters are most likely used for wildcard expansion and the implementation of this method should not remove them.</span></span>

## <a name="retrieving-the-parent-path"></a><span data-ttu-id="3d3e6-161">親パスを取得します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-161">Retrieving the Parent Path</span></span>

<span data-ttu-id="3d3e6-162">Windows PowerShell ナビゲーション プロバイダーの実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)の指定された親パーツ全体または一部を取得するメソッドプロバイダー固有のパス。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-162">Windows PowerShell navigation providers implement the [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method to retrieve the parent part of the indicated full or partial provider-specific path.</span></span> <span data-ttu-id="3d3e6-163">メソッドでは、パスの子の一部を削除し、親のパス部分を返します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-163">The method removes the child part of the path and returns the parent path part.</span></span> <span data-ttu-id="3d3e6-164">`root`パラメーターが、ドライブのルートへの完全修飾パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-164">The `root` parameter specifies the fully-qualified path to the root of a drive.</span></span> <span data-ttu-id="3d3e6-165">このパラメーターは、null または、マウントされたドライブは取得操作で使用されていない場合は、空にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-165">This parameter can be null or empty if a mounted drive is not in use for the retrieval operation.</span></span> <span data-ttu-id="3d3e6-166">ルートが指定されている場合、メソッドは、ルートと同じツリー内のコンテナーにパスを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-166">If a root is specified, the method must return a path to a container in the same tree as the root.</span></span>

<span data-ttu-id="3d3e6-167">サンプル ナビゲーション プロバイダーは、このメソッドをオーバーライドしませんが、既定の実装を使用します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-167">The sample navigation provider does not override this method, but uses the default implementation.</span></span> <span data-ttu-id="3d3e6-168">両方を使用してパスを受け入れる「/」と"\\"パスの区切り記号として。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-168">It accepts paths that use both "/" and "\\" as path separators.</span></span> <span data-ttu-id="3d3e6-169">のみがへのパスを最初に正規化"\\"区切り記号、オフ、最後に、親のパスを分割"\\"親パスを返します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-169">It first normalizes the path to have only "\\" separators, then splits the parent path off at the last "\\" and returns the parent path.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetparentpath](Msh_samplestestcmdlets#testprovidergetparentpath)]  -->

#### <a name="to-remember-about-implementing-getparentpath"></a><span data-ttu-id="3d3e6-170">GetParentPath の実装に関する注意</span><span class="sxs-lookup"><span data-stu-id="3d3e6-170">To Remember About Implementing GetParentPath</span></span>

<span data-ttu-id="3d3e6-171">実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)メソッドは、プロバイダーの名前空間のパスの区切り記号の構文上のパスを分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-171">Your implementation of the [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method should split the path lexically on the path separator for the provider namespace.</span></span> <span data-ttu-id="3d3e6-172">Filesystem プロバイダーがこのメソッドを使用して、最後の検索などの"\\"を区切り記号の左側にすべてのものを返します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-172">For example, the filesystem provider uses this method to look for the last "\\" and returns everything to the left of the separator.</span></span>

## <a name="retrieve-the-child-path-name"></a><span data-ttu-id="3d3e6-173">子のパス名を取得します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-173">Retrieve the Child Path Name</span></span>

<span data-ttu-id="3d3e6-174">ナビゲーション プロバイダーの実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName)アイテムの子の名前 (リーフ要素) を取得するメソッドがある、指定された完全なまたは部分的なプロバイダー固有のパス。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-174">Your navigation provider implements the [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method to retrieve the name (leaf element) of the child of the item located at the indicated full or partial provider-specific path.</span></span>

<span data-ttu-id="3d3e6-175">サンプル ナビゲーション プロバイダーは、このメソッドをオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-175">The sample navigation provider does not override this method.</span></span> <span data-ttu-id="3d3e6-176">既定の実装は、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-176">The default implementation is shown below.</span></span> <span data-ttu-id="3d3e6-177">両方を使用してパスを受け入れる「/」と"\\"パスの区切り記号として。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-177">It accepts paths that use both "/" and "\\" as path separators.</span></span> <span data-ttu-id="3d3e6-178">のみがへのパスを最初に正規化"\\"区切り記号、オフ、最後に、親のパスを分割"\\"し、パスの一部の子の名前を返します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-178">It first normalizes the path to have only "\\" separators, then splits the parent path off at the last "\\" and returns the name of the child path part.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchildname](Msh_samplestestcmdlets#testprovidergetchildname)]  -->

#### <a name="things-to-remember-about-implementing-getchildname"></a><span data-ttu-id="3d3e6-179">GetChildName の実装に関する注意点</span><span class="sxs-lookup"><span data-stu-id="3d3e6-179">Things to Remember About Implementing GetChildName</span></span>

<span data-ttu-id="3d3e6-180">実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName)メソッドは、パスの区切り文字の構文上のパスを分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-180">Your implementation of the [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method should split the path lexically on the path separator.</span></span> <span data-ttu-id="3d3e6-181">指定されたパスにパスの区切り記号が含まれていない場合、メソッドが変更されていないパスを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-181">If the supplied path contains no path separators, the method should return the path unmodified.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d3e6-182">このメソッドの呼び出しで指定されたパスは、プロバイダーの名前空間では無効な文字があります。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-182">The path provided in the call to this method might contain characters that are illegal in the provider namespace.</span></span> <span data-ttu-id="3d3e6-183">これらの文字はワイルドカードの展開または正規表現の照合に使用される可能性が最も高いと、このメソッドの実装は削除されません。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-183">These characters are most likely used for wildcard expansion or regular expression matching, and the implementation of this method should not remove them.</span></span>

## <a name="determining-if-an-item-is-a-container"></a><span data-ttu-id="3d3e6-184">項目がコンテナーであるを決定します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-184">Determining if an Item is a Container</span></span>

<span data-ttu-id="3d3e6-185">ナビゲーション プロバイダーを実装できる、 [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)メソッドを指定されたパスが、コンテナーを示すかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-185">The navigation provider can implement the [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method to determine if the specified path indicates a container.</span></span> <span data-ttu-id="3d3e6-186">パスには、それ以外の場合するコンテナー、および false が表している場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-186">It returns true if the path represents a container, and false otherwise.</span></span> <span data-ttu-id="3d3e6-187">ユーザーが、このメソッドを使用する必要があります、`Test-Path`コマンドレットに指定されたパス。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-187">The user needs this method to be able to use the `Test-Path` cmdlet for the supplied path.</span></span>

<span data-ttu-id="3d3e6-188">次のコードは、 [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)サンプル ナビゲーション プロバイダーで実装します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-188">The following code shows the [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) implementation in our sample navigation provider.</span></span> <span data-ttu-id="3d3e6-189">指定されたパスが正しいことと、テーブルが存在し、パスには、コンテナーが示されている場合は true を返すかどうか、メソッドを確認します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-189">The method verifies that  the specified path is correct and if the table exists, and returns true if the path indicates a container.</span></span>

[!code-csharp[AccessDBProviderSample05.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs#L847-L872 "AccessDBProviderSample05.cs")]

#### <a name="things-to-remember-about-implementing-isitemcontainer"></a><span data-ttu-id="3d3e6-190">IsItemContainer の実装に関する注意点</span><span class="sxs-lookup"><span data-stu-id="3d3e6-190">Things to Remember About Implementing IsItemContainer</span></span>

<span data-ttu-id="3d3e6-191">.NET クラスは、ナビゲーション プロバイダーはから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言する可能性があります、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-191">Your navigation provider .NET class might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="3d3e6-192">この場合は、実装の[System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)渡されたパスが要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-192">In this case, the implementation of [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) needs to ensure that the path passed meets requirements.</span></span> <span data-ttu-id="3d3e6-193">これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-193">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) property.</span></span>

## <a name="moving-an-item"></a><span data-ttu-id="3d3e6-194">アイテムを移動します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-194">Moving an Item</span></span>

<span data-ttu-id="3d3e6-195">サポート、`Move-Item`コマンドレット、ナビゲーションは、プロバイダーの実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)メソッド。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-195">In support of the `Move-Item` cmdlet, your navigation provider implements the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method.</span></span> <span data-ttu-id="3d3e6-196">このメソッドで指定された項目の移動、`path`パラメーターで指定されたパスにあるコンテナーを`destination`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-196">This method moves the item specified by the `path` parameter to the container at the path supplied in the `destination` parameter.</span></span>

<span data-ttu-id="3d3e6-197">サンプル ナビゲーション プロバイダーをオーバーライドしない、 [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)メソッド。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-197">The sample navigation provider does not override the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method.</span></span> <span data-ttu-id="3d3e6-198">既定の実装を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-198">The following is the default implementation.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermoveitem](Msh_samplestestcmdlets#testprovidermoveitem)]  -->

#### <a name="things-to-remember-about-implementing-moveitem"></a><span data-ttu-id="3d3e6-199">MoveItem の実装に関する注意点</span><span class="sxs-lookup"><span data-stu-id="3d3e6-199">Things to Remember About Implementing MoveItem</span></span>

<span data-ttu-id="3d3e6-200">.NET クラスは、ナビゲーション プロバイダーはから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言する可能性があります、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-200">Your navigation provider .NET class might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="3d3e6-201">この場合は、実装の[System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)渡されたパスが要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-201">In this case, the implementation of [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) must ensure that the path passed meets requirements.</span></span> <span data-ttu-id="3d3e6-202">これを行うには、メソッドがプロパティにアクセス適切なたとえば、 **CmdletProvider.Exclude**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-202">To do this, the method should access the appropriate property, for example, the **CmdletProvider.Exclude** property.</span></span>

<span data-ttu-id="3d3e6-203">既定では、このメソッドのオーバーライドする必要がありますオブジェクトを移動できません既存のオブジェクトに対する場合を除き、 [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティに設定されて`true`します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-203">By default, overrides of this method should not move objects over existing objects unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is set to `true`.</span></span> <span data-ttu-id="3d3e6-204">たとえば、filesystem プロバイダーはコピーしません c:\temp\abc.txt c:\bar.txt の既存のファイルにしない限り、 [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティに設定されて`true`します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-204">For example, the filesystem provider will not copy c:\temp\abc.txt over an existing c:\bar.txt file unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is set to `true`.</span></span> <span data-ttu-id="3d3e6-205">パスが指定されている場合、`destination`パラメーターが存在し、コンテナー、 [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-205">If the path specified in the `destination` parameter exists and is a container, the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is not required.</span></span> <span data-ttu-id="3d3e6-206">この場合、 [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)によって示される項目を移動する必要があります、`path`でコンテナーにパラメーターが示される、`destination`子としてパラメーター。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-206">In this case, [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) should move the item indicated by the `path` parameter to the container indicated by the `destination` parameter as a child.</span></span>

<span data-ttu-id="3d3e6-207">実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)メソッドを呼び出す必要があります[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)データ ストアに変更を加える前に、戻り値を確認します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-207">Your implementation of the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method should call [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) and check its return value before making any changes to the data store.</span></span> <span data-ttu-id="3d3e6-208">このメソッドは、操作の実行の確認が変更されたシステム状態、たとえば、ファイルを削除するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-208">This method is used to confirm execution of an operation when a change is made to system state, for example, deleting files.</span></span> <span data-ttu-id="3d3e6-209">[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)コマンドライン設定や ユーザー設定変数を考慮して、Windows PowerShell ランタイムで、ユーザーに変更するリソースの名前を送信します。何をユーザーに表示するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-209">[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) sends the name of the resource to be changed to the user, with the Windows PowerShell runtime taking into account any command line settings or preference variables in determining what should be displayed to the user.</span></span>

<span data-ttu-id="3d3e6-210">呼び出し後[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)返します`true`、 [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)メソッドを呼び出す必要があります、 [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)メソッド。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-210">After the call to [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) returns `true`, the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method should call the [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) method.</span></span> <span data-ttu-id="3d3e6-211">このメソッドは、操作を続行するかどうかにフィードバックを許可するユーザーにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-211">This method sends a message to the user to allow feedback to say if the operation should be continued.</span></span> <span data-ttu-id="3d3e6-212">ご利用のプロバイダーを呼び出す必要があります[System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)危険性のあるシステムの変更、追加のチェックとして。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-212">Your provider should call [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) as an additional check for potentially dangerous system modifications.</span></span>

## <a name="attaching-dynamic-parameters-to-the-move-item-cmdlet"></a><span data-ttu-id="3d3e6-213">Move-item コマンドレットに動的パラメーターを追加</span><span class="sxs-lookup"><span data-stu-id="3d3e6-213">Attaching Dynamic Parameters to the Move-Item Cmdlet</span></span>

<span data-ttu-id="3d3e6-214">場合によって、`Move-Item`コマンドレットが実行時に動的に提供される追加のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-214">Sometimes the `Move-Item` cmdlet requires additional parameters that are provided dynamically at runtime.</span></span> <span data-ttu-id="3d3e6-215">これらの動的パラメーターを提供するナビゲーション プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)必要なパラメーター値を取得するメソッド返された場合、指定されたパスにある項目を持つプロパティとフィールドを解析してオブジェクト属性コマンドレット クラスのように、または[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-215">To provide these dynamic parameters, the navigation provider must implement the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) method to get the required parameter values from the item at the indicated path, and return an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span>

<span data-ttu-id="3d3e6-216">このナビゲーション プロバイダーは、このメソッドを実装していません。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-216">This navigation provider does not implement this method.</span></span> <span data-ttu-id="3d3e6-217">ただし、次のコードは、既定の実装の[System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-217">However, the following code is the default implementation of [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters).</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermoveitemdynamicparameters](Msh_samplestestcmdlets#testprovidermoveitemdynamicparameters)]  -->

## <a name="normalizing-a-relative-path"></a><span data-ttu-id="3d3e6-218">相対パスの正規化</span><span class="sxs-lookup"><span data-stu-id="3d3e6-218">Normalizing a Relative Path</span></span>

<span data-ttu-id="3d3e6-219">ナビゲーション プロバイダーの実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)に完全修飾パスを正規化する方法が示されている、`path`パラメーター指定されたパスを基準として、`basePath`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-219">Your navigation provider implements the [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method to normalize the fully-qualified path indicated in the `path` parameter as being relative to the path specified by the `basePath` parameter.</span></span> <span data-ttu-id="3d3e6-220">メソッドは、正規化されたパスの文字列表現を返します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-220">The method returns a string representation of the normalized path.</span></span> <span data-ttu-id="3d3e6-221">書き込むエラーである場合、`path`パラメーターが存在しないパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-221">It writes an error if the `path` parameter specifies a nonexistent path.</span></span>

<span data-ttu-id="3d3e6-222">サンプル ナビゲーション プロバイダーは、このメソッドをオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-222">The sample navigation provider does not override this method.</span></span> <span data-ttu-id="3d3e6-223">既定の実装を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-223">The following is the default implementation.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernormalizepath](Msh_samplestestcmdlets#testprovidernormalizepath)]  -->

#### <a name="things-to-remember-about-implementing-normalizerelativepath"></a><span data-ttu-id="3d3e6-224">NormalizeRelativePath の実装に関する注意点</span><span class="sxs-lookup"><span data-stu-id="3d3e6-224">Things to Remember About Implementing NormalizeRelativePath</span></span>

<span data-ttu-id="3d3e6-225">実装[System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)解析する必要があります、`path`パラメーターが、これは純粋な構文の解析を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-225">Your implementation of [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) should parse the `path` parameter, but it does not have to use purely syntactical parsing.</span></span> <span data-ttu-id="3d3e6-226">パスを使用して、データ ストアのパス情報を検索し、パスを作成するには、このメソッドには、大文字と小文字が一致するデザインすることが推奨され、パスの構文を標準化します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-226">You are encouraged to design this method to use the path to look up the path information in the data store and create a path that matches the casing and standardized path syntax.</span></span>

## <a name="code-sample"></a><span data-ttu-id="3d3e6-227">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="3d3e6-227">Code Sample</span></span>

<span data-ttu-id="3d3e6-228">完全なサンプル コードでは、次を参照してください。 [AccessDbProviderSample05 コード サンプル](./accessdbprovidersample05-code-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-228">For complete sample code, see [AccessDbProviderSample05 Code Sample](./accessdbprovidersample05-code-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="3d3e6-229">オブジェクトの種類を定義して、書式設定</span><span class="sxs-lookup"><span data-stu-id="3d3e6-229">Defining Object Types and Formatting</span></span>

<span data-ttu-id="3d3e6-230">プロバイダーに既存のオブジェクトにメンバーを追加したり、新しいオブジェクトを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-230">It is possible for a provider to add members to existing objects or define new objects.</span></span> <span data-ttu-id="3d3e6-231">詳細については、次を参照してください。[を拡張するオブジェクトの種類と書式](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-231">For more information, see[Extending Object Types and Formatting](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-windows-powershell-provider"></a><span data-ttu-id="3d3e6-232">Windows PowerShell プロバイダーの構築</span><span class="sxs-lookup"><span data-stu-id="3d3e6-232">Building the Windows PowerShell provider</span></span>

<span data-ttu-id="3d3e6-233">詳細については、次を参照してください。[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-233">For more information, see [How to Register Cmdlets, Providers, and Host Applications](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-windows-powershell-provider"></a><span data-ttu-id="3d3e6-234">Windows PowerShell プロバイダーのテスト</span><span class="sxs-lookup"><span data-stu-id="3d3e6-234">Testing the Windows PowerShell provider</span></span>

<span data-ttu-id="3d3e6-235">Windows PowerShell を使用した、Windows PowerShell プロバイダーを登録しているときに、派生で利用できるコマンドレットなど、コマンドラインでサポートされているコマンドレットを実行してテストできます。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-235">When your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line, including cmdlets made available by derivation.</span></span> <span data-ttu-id="3d3e6-236">この例では、サンプルのナビゲーション プロバイダーをテストします。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-236">This example will test the sample navigation provider.</span></span>

1. <span data-ttu-id="3d3e6-237">新しいシェルを実行し、使用、`Set-Location`を Access データベースを示すためにパスを設定するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-237">Run your new shell and use the `Set-Location` cmdlet to set the path to indicate the Access database.</span></span>

   ```powershell
   Set-Location mydb:
   ```

2. <span data-ttu-id="3d3e6-238">今すぐ実行、`Get-Childitem`コマンドレットを使用可能なデータベース テーブルにはデータベースのアイテムの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-238">Now run the `Get-Childitem` cmdlet to retrieve a list of the database items, which are the available database tables.</span></span> <span data-ttu-id="3d3e6-239">テーブルごとに、このコマンドレットは、テーブル行の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-239">For each table, this cmdlet also retrieves the number of table rows.</span></span>

   ```powershell
   Get-ChildItem | Format-Table rowcount,name -AutoSize
   ```

   ```output
   RowCount   Name
   --------   ----
        180   MSysAccessObjects
          0   MSysACEs
          1   MSysCmdbars
          0   MSysIMEXColumns
          0   MSysIMEXSpecs
          0   MSysObjects
          0   MSysQueries
          7   MSysRelationships
          8   Categories
         91   Customers
          9   Employees
       2155   Order Details
        830   Orders
         77   Products
          3   Shippers
         29   Suppliers
   ```

3. <span data-ttu-id="3d3e6-240">使用して、`Set-Location`コマンドレットを再度従業員データのテーブルの場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-240">Use the `Set-Location` cmdlet again to set the location of the Employees data table.</span></span>

   ```powershell
   Set-Location Employees
   ```

4. <span data-ttu-id="3d3e6-241">ここで使用して、 `Get-Location` Employees テーブルへのパスを取得するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-241">Let's now use the `Get-Location` cmdlet to retrieve the path to the Employees table.</span></span>

   ```powershell
   Get-Location
   ```

   ```output
   Path
   ----
   mydb:\Employees
   ```

5. <span data-ttu-id="3d3e6-242">使用して、`Get-Childitem`コマンドレットにパイプする、`Format-Table`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-242">Now use the `Get-Childitem` cmdlet piped to the `Format-Table` cmdlet.</span></span> <span data-ttu-id="3d3e6-243">この一連のコマンドレットでは、テーブルの行には、従業員のデータ テーブルの項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-243">This set of cmdlets retrieves the items for the Employees data table, which are the table rows.</span></span> <span data-ttu-id="3d3e6-244">書式設定される指定に従って、`Format-Table`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-244">They are formatted as specified by the `Format-Table` cmdlet.</span></span>

   ```powershell
   Get-ChildItem | Format-Table rownumber,psiscontainer,data -AutoSize
   ```

   ```output
   RowNumber   PSIsContainer   Data
   ---------   --------------   ----
   0           False            System.Data.DataRow
   1           False            System.Data.DataRow
   2           False            System.Data.DataRow
   3           False            System.Data.DataRow
   4           False            System.Data.DataRow
   5           False            System.Data.DataRow
   6           False            System.Data.DataRow
   7           False            System.Data.DataRow
   8           False            System.Data.DataRow
   ```

6. <span data-ttu-id="3d3e6-245">今すぐ実行することができます、`Get-Item`従業員データのテーブルの行 0 の項目を取得するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-245">You can now run the `Get-Item` cmdlet to retrieve the items for row 0 of the Employees data table.</span></span>

   ```powershell
   Get-Item 0
   ```

   ```output
   PSPath        : AccessDB::C:\PS\Northwind.mdb\Employees\0
   PSParentPath  : AccessDB::C:\PS\Northwind.mdb\Employees
   PSChildName   : 0
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : False
   Data           : System.Data.DataRow
   RowNumber      : 0
   ```

7. <span data-ttu-id="3d3e6-246">使用して、`Get-Item`コマンドレットを再度従業員のデータ行 0 内の項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-246">Use the `Get-Item` cmdlet again to retrieve the employee data for the items in row 0.</span></span>

   ```powershell
   (Get-Item 0).data
   ```

   ```output
   EmployeeID      : 1
   LastName        : Davis
   FirstName       : Sara
   Title           : Sales Representative
   TitleOfCourtesy : Ms.
   BirthDate       : 12/8/1968 12:00:00 AM
   HireDate        : 5/1/1992 12:00:00 AM
   Address         : 4567 Main Street
                     Apt. 2A
   City            : Buffalo
   Region          : NY
   PostalCode      : 98052
   Country         : USA
   HomePhone       : (206) 555-9857
   Extension       : 5467
   Photo           : EmpID1.bmp
   Notes           : Education includes a BA in psychology from
                     Colorado State University. She also completed "The
                     Art of the Cold Call."  Nancy is a member of
                     Toastmasters International.
   ReportsTo       : 2
   ```

## <a name="see-also"></a><span data-ttu-id="3d3e6-247">参照</span><span class="sxs-lookup"><span data-stu-id="3d3e6-247">See Also</span></span>

[<span data-ttu-id="3d3e6-248">Windows PowerShell プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-248">Creating Windows PowerShell providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="3d3e6-249">デザイン、Windows PowerShell プロバイダー</span><span class="sxs-lookup"><span data-stu-id="3d3e6-249">Design Your Windows PowerShell provider</span></span>](./designing-your-windows-powershell-provider.md)

[<span data-ttu-id="3d3e6-250">オブジェクトの種類を拡張して、書式設定</span><span class="sxs-lookup"><span data-stu-id="3d3e6-250">Extending Object Types and Formatting</span></span>](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="3d3e6-251">コンテナーの Windows PowerShell プロバイダーを実装します。</span><span class="sxs-lookup"><span data-stu-id="3d3e6-251">Implement a Container Windows PowerShell provider</span></span>](./creating-a-windows-powershell-container-provider.md)

[<span data-ttu-id="3d3e6-252">登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法</span><span class="sxs-lookup"><span data-stu-id="3d3e6-252">How to Register Cmdlets, Providers, and Host Applications</span></span>](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="3d3e6-253">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="3d3e6-253">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="3d3e6-254">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="3d3e6-254">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)