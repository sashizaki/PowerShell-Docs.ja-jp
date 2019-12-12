---
title: Windows PowerShell プロバイダーを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- providers [PowerShell Programmer's Guide]
- providers [PowerShellProgrammer's Guide], creating
- Windows PowerShell Programmer's Guide, providers
ms.assetid: 863e48e9-7206-4c6a-a59a-2ab2d30396bc
caps.latest.revision: 5
ms.openlocfilehash: ffbf8028ba2b52e77d8e22c061baa9b8b67f6da3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366651"
---
# <a name="how-to-create-a-windows-powershell-provider"></a><span data-ttu-id="437ae-102">Windows PowerShell プロバイダーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="437ae-102">How to Create a Windows PowerShell Provider</span></span>

<span data-ttu-id="437ae-103">このセクションでは、Windows PowerShell プロバイダーを構築する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="437ae-103">This section describes how to build a Windows PowerShell provider.</span></span> <span data-ttu-id="437ae-104">Windows PowerShell プロバイダーは、次の2つの方法で考慮できます。</span><span class="sxs-lookup"><span data-stu-id="437ae-104">A Windows PowerShell provider can be considered in two ways.</span></span> <span data-ttu-id="437ae-105">プロバイダーは、ユーザーに対して格納されているデータのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="437ae-105">To the user, the provider represents a set of stored data.</span></span> <span data-ttu-id="437ae-106">たとえば、格納されているデータには、インターネットインフォメーションサービス (IIS) メタベース、Microsoft Windows レジストリ、Windows ファイルシステム、Active Directory、および Windows PowerShell によって格納される変数および別名データを使用できます。</span><span class="sxs-lookup"><span data-stu-id="437ae-106">For example, the stored data can be the Internet Information Services (IIS) Metabase, the Microsoft Windows Registry, the Windows file system, Active Directory, and the variable and alias data stored by Windows PowerShell.</span></span>

<span data-ttu-id="437ae-107">開発者にとって、Windows PowerShell プロバイダーは、ユーザーとユーザーがアクセスする必要があるデータの間のインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="437ae-107">To the developer, the Windows PowerShell provider is the interface between the user and the data that the user needs to access.</span></span> <span data-ttu-id="437ae-108">この観点からは、このセクションで説明する各種類のプロバイダーは、Windows PowerShell ランタイムが特定のコマンドレットを共通の方法でユーザーに公開できるようにする、特定の基本クラスとインターフェイスのセットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="437ae-108">From this perspective, each type of provider described in this section supports a set of specific base classes and interfaces that allow the Windows PowerShell runtime to expose certain cmdlets to the user in a common way.</span></span>

## <a name="providers-provided-by-windows-powershell"></a><span data-ttu-id="437ae-109">Windows PowerShell によって提供されるプロバイダー</span><span class="sxs-lookup"><span data-stu-id="437ae-109">Providers Provided by Windows PowerShell</span></span>

<span data-ttu-id="437ae-110">Windows PowerShell には、既知のデータストアへのアクセスに使用されるいくつかのプロバイダー (FileSystem プロバイダー、レジストリプロバイダー、別名プロバイダーなど) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="437ae-110">Windows PowerShell provides several providers (such as the FileSystem provider, Registry provider, and Alias provider) that are used to access known data stores.</span></span> <span data-ttu-id="437ae-111">Windows PowerShell によって提供されるプロバイダーの詳細については、次のコマンドを使用して、オンラインヘルプにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="437ae-111">For more information about the providers supplied by Windows PowerShell, use the following command to access online Help:</span></span>

<span data-ttu-id="437ae-112">**PS > get-help about_providers**</span><span class="sxs-lookup"><span data-stu-id="437ae-112">**PS>get-help about_providers**</span></span>

## <a name="accessing-the-stored-data-using-windows-powershell-paths"></a><span data-ttu-id="437ae-113">Windows PowerShell パスを使用した格納されたデータへのアクセス</span><span class="sxs-lookup"><span data-stu-id="437ae-113">Accessing the Stored Data Using Windows PowerShell Paths</span></span>

<span data-ttu-id="437ae-114">Windows powershell プロバイダーは、windows powershell ランタイムにアクセスしたり、Windows PowerShell パスを使用してプログラムでコマンドを実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="437ae-114">Windows PowerShell providers are accessible to the Windows PowerShell runtime and to commands programmatically through the use of Windows PowerShell paths.</span></span> <span data-ttu-id="437ae-115">ほとんどの場合、これらのパスは、プロバイダーを介してデータに直接アクセスするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="437ae-115">Most of the time, these paths are used to directly access the data through the provider.</span></span> <span data-ttu-id="437ae-116">ただし、一部のパスは、コマンドレットが Windows PowerShell 以外のアプリケーションプログラミングインターフェイス (Api) を使用してデータにアクセスできるようにする、プロバイダー内部パスに解決される場合があります。</span><span class="sxs-lookup"><span data-stu-id="437ae-116">However, some paths can be resolved to provider-internal paths that allow a cmdlet to use non-Windows PowerShell application programming interfaces (APIs) to access the data.</span></span> <span data-ttu-id="437ae-117">Windows powershell プロバイダーが Windows PowerShell 内で動作する方法の詳細については、「 [Windows powershell のしくみ](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="437ae-117">For more information about how Windows PowerShell providers operate within Windows PowerShell, see [How Windows PowerShell Works](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58).</span></span>

## <a name="exposing-provider-cmdlets-using-windows-powershell-drives"></a><span data-ttu-id="437ae-118">Windows PowerShell ドライブを使用したプロバイダーコマンドレットの公開</span><span class="sxs-lookup"><span data-stu-id="437ae-118">Exposing Provider Cmdlets Using Windows PowerShell Drives</span></span>

<span data-ttu-id="437ae-119">Windows PowerShell プロバイダーは、仮想 Windows PowerShell ドライブを使用して、サポートされているコマンドレットを公開します。</span><span class="sxs-lookup"><span data-stu-id="437ae-119">A Windows PowerShell provider exposes its supported cmdlets using virtual Windows PowerShell drives.</span></span> <span data-ttu-id="437ae-120">Windows PowerShell では、Windows PowerShell ドライブに対して次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="437ae-120">Windows PowerShell applies the following rules for a Windows PowerShell drive:</span></span>

- <span data-ttu-id="437ae-121">ドライブ名は、任意の英数字のシーケンスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="437ae-121">The name of a drive can be any alphanumeric sequence.</span></span>

- <span data-ttu-id="437ae-122">ドライブは、"ルート" と呼ばれるパス上の任意の有効なポイントで指定できます。</span><span class="sxs-lookup"><span data-stu-id="437ae-122">A drive can be specified at any valid point on a path, called a "root".</span></span>

- <span data-ttu-id="437ae-123">ドライブは、ファイルシステムだけでなく、格納されているデータに対しても実装できます。</span><span class="sxs-lookup"><span data-stu-id="437ae-123">A drive can be implemented for any stored data, not just the file system.</span></span>

- <span data-ttu-id="437ae-124">各ドライブは、現在の作業場所を保持するので、ユーザーはドライブ間を移動するときにコンテキストを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="437ae-124">Each drive keeps its own current working location, allowing the user to retain context when shifting between drives.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="437ae-125">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="437ae-125">In This Section</span></span>

<span data-ttu-id="437ae-126">次の表に、相互に構築されるコード例を含むトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="437ae-126">The following table lists topics that include code examples that build on each other.</span></span> <span data-ttu-id="437ae-127">2番目のトピックでは、Windows powershell ランタイムによって基本的な Windows PowerShell プロバイダーを初期化し初期化することができます。次のトピックでは、データにアクセスするための機能を追加します。次のトピックでは、データを操作するための機能を追加します (格納されているデータの項目など)。</span><span class="sxs-lookup"><span data-stu-id="437ae-127">Starting with the second topic, the basic Windows PowerShell provider can be initialized and uninitialized by the Windows PowerShell runtime, the next topic adds functionality for accessing the data, the next topic adds functionality for manipulating the data (the items in the stored data), and so on.</span></span>

|<span data-ttu-id="437ae-128">トピック</span><span class="sxs-lookup"><span data-stu-id="437ae-128">Topic</span></span>|<span data-ttu-id="437ae-129">定義</span><span class="sxs-lookup"><span data-stu-id="437ae-129">Definition</span></span>|
|-----------|----------------|
|[<span data-ttu-id="437ae-130">Windows PowerShell プロバイダーの設計</span><span class="sxs-lookup"><span data-stu-id="437ae-130">Designing Your Windows PowerShell Provider</span></span>](./designing-your-windows-powershell-provider.md)|<span data-ttu-id="437ae-131">このトピックでは、Windows PowerShell プロバイダーを実装する前に考慮する必要がある事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="437ae-131">This topic discusses things you should consider before implementing a Windows PowerShell provider.</span></span> <span data-ttu-id="437ae-132">使用される Windows PowerShell プロバイダーの基本クラスとインターフェイスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="437ae-132">It summarizes the Windows PowerShell provider base classes and interfaces that are used.</span></span>|
|[<span data-ttu-id="437ae-133">基本的な Windows PowerShell プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="437ae-133">Creating a Basic Windows PowerShell Provider</span></span>](./creating-a-basic-windows-powershell-provider.md)|<span data-ttu-id="437ae-134">このトピックでは、Windows powershell ランタイムがプロバイダーを初期化および初期化解除できるようにする Windows PowerShell プロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="437ae-134">This topic shows how to create a Windows PowerShell provider that allows the Windows PowerShell runtime to initialize and uninitialize the provider.</span></span>|
|[<span data-ttu-id="437ae-135">Windows PowerShell ドライブプロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="437ae-135">Creating a Windows PowerShell Drive Provider</span></span>](./creating-a-windows-powershell-drive-provider.md)|<span data-ttu-id="437ae-136">このトピックでは、windows PowerShell ドライブを介してユーザーがデータストアにアクセスできるようにする Windows PowerShell プロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="437ae-136">This topic shows how to create a Windows PowerShell provider that allows the user to access a data store through a Windows PowerShell drive.</span></span>|
|[<span data-ttu-id="437ae-137">Windows PowerShell 項目プロバイダーを作成する</span><span class="sxs-lookup"><span data-stu-id="437ae-137">Creating a Windows PowerShell Item Provider</span></span>](./creating-a-windows-powershell-item-provider.md)|<span data-ttu-id="437ae-138">このトピックでは、ユーザーがデータストア内の項目を操作できるようにする Windows PowerShell プロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="437ae-138">This topic shows how to create a Windows PowerShell provider that allows the user to manipulate the items in a data store.</span></span>|
|[<span data-ttu-id="437ae-139">Windows PowerShell コンテナープロバイダーを作成する</span><span class="sxs-lookup"><span data-stu-id="437ae-139">Creating a Windows PowerShell Container Provider</span></span>](./creating-a-windows-powershell-container-provider.md)|<span data-ttu-id="437ae-140">このトピックでは、ユーザーがマルチレイヤーデータストアを操作できるようにする Windows PowerShell プロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="437ae-140">This topic shows how to create a Windows PowerShell provider that allows the user to work on multilayer data stores.</span></span>|
|[<span data-ttu-id="437ae-141">Windows PowerShell ナビゲーションプロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="437ae-141">Creating a Windows PowerShell Navigation Provider</span></span>](./creating-a-windows-powershell-navigation-provider.md)|<span data-ttu-id="437ae-142">このトピックでは、ユーザーがデータストアの項目を階層構造で移動できるようにする Windows PowerShell プロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="437ae-142">This topic shows how to create a Windows PowerShell provider that allows the user to navigate the items of a data store in a hierarchical manner.</span></span>|
|[<span data-ttu-id="437ae-143">Windows PowerShell コンテンツプロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="437ae-143">Creating a Windows PowerShell Content Provider</span></span>](./creating-a-windows-powershell-content-provider.md)|<span data-ttu-id="437ae-144">このトピックでは、ユーザーがデータストア内の項目の内容を操作できるようにする Windows PowerShell プロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="437ae-144">This topic shows how to create a Windows PowerShell provider that allows the user to manipulate the content of items in a data store.</span></span>|
|[<span data-ttu-id="437ae-145">Windows PowerShell プロパティプロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="437ae-145">Creating a Windows PowerShell Property Provider</span></span>](./creating-a-windows-powershell-property-provider.md)|<span data-ttu-id="437ae-146">このトピックでは、ユーザーがデータストア内の項目のプロパティを操作できるようにする Windows PowerShell プロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="437ae-146">This topic shows how to create a Windows PowerShell provider that allows the user to manipulate the properties of items in a data store.</span></span>|

## <a name="see-also"></a><span data-ttu-id="437ae-147">参照</span><span class="sxs-lookup"><span data-stu-id="437ae-147">See Also</span></span>

[<span data-ttu-id="437ae-148">Windows PowerShell の動作</span><span class="sxs-lookup"><span data-stu-id="437ae-148">How Windows PowerShell Works</span></span>](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[<span data-ttu-id="437ae-149">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="437ae-149">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="437ae-150">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="437ae-150">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)
