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
ms.openlocfilehash: 06910f32752668f13400f9be0767a2179133df04
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081752"
---
# <a name="how-to-create-a-windows-powershell-provider"></a><span data-ttu-id="bcdfe-102">Windows PowerShell プロバイダーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="bcdfe-102">How to Create a Windows PowerShell Provider</span></span>

<span data-ttu-id="bcdfe-103">このセクションでは、Windows PowerShell プロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-103">This section describes how to build a Windows PowerShell provider.</span></span> <span data-ttu-id="bcdfe-104">2 つの方法で、Windows PowerShell プロバイダーを見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-104">A Windows PowerShell provider can be considered in two ways.</span></span> <span data-ttu-id="bcdfe-105">ユーザーには、プロバイダーは、格納されたデータのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-105">To the user, the provider represents a set of stored data.</span></span> <span data-ttu-id="bcdfe-106">たとえば、格納されているデータには、インターネット インフォメーション サービス (IIS) メタベース、Microsoft Windows レジストリ、Windows ファイル システム、Active Directory、および Windows PowerShell によって格納される変数とエイリアス データができます。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-106">For example, the stored data can be the Internet Information Services (IIS) Metabase, the Microsoft Windows Registry, the Windows file system, Active Directory, and the variable and alias data stored by Windows PowerShell.</span></span>

<span data-ttu-id="bcdfe-107">開発者には、Windows PowerShell プロバイダーは、ユーザー データとの間、ユーザーがアクセスする必要があるインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-107">To the developer, the Windows PowerShell provider is the interface between the user and the data that the user needs to access.</span></span> <span data-ttu-id="bcdfe-108">この観点からは、このセクションで説明されているプロバイダーの種類ごとには、特定の基底クラスと Windows PowerShell ランタイムの一般的な方法でユーザーに特定のコマンドレットを公開できるようにするインターフェイスのセットがサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-108">From this perspective, each type of provider described in this section supports a set of specific base classes and interfaces that allow the Windows PowerShell runtime to expose certain cmdlets to the user in a common way.</span></span>

## <a name="providers-provided-by-windows-powershell"></a><span data-ttu-id="bcdfe-109">Windows PowerShell によって提供されるプロバイダー</span><span class="sxs-lookup"><span data-stu-id="bcdfe-109">Providers Provided by Windows PowerShell</span></span>

<span data-ttu-id="bcdfe-110">Windows PowerShell では、既知のデータ ストアへのアクセスに使用されるいくつかのプロバイダー (FileSystem プロバイダー、レジストリ プロバイダーでは、Alias プロバイダーなど) を提供します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-110">Windows PowerShell provides several providers (such as the FileSystem provider, Registry provider, and Alias provider) that are used to access known data stores.</span></span> <span data-ttu-id="bcdfe-111">Windows PowerShell によって提供されるプロバイダーの詳細については、オンライン ヘルプにアクセスして、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-111">For more information about the providers supplied by Windows PowerShell, use the following command to access online Help:</span></span>

<span data-ttu-id="bcdfe-112">**PS > get-help about_providers**</span><span class="sxs-lookup"><span data-stu-id="bcdfe-112">**PS>get-help about_providers**</span></span>

## <a name="accessing-the-stored-data-using-windows-powershell-paths"></a><span data-ttu-id="bcdfe-113">Windows PowerShell のパスを使用して、格納されたデータにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-113">Accessing the Stored Data Using Windows PowerShell Paths</span></span>

<span data-ttu-id="bcdfe-114">Windows PowerShell プロバイダーは、Windows PowerShell パスを使用してプログラムでのコマンドを Windows PowerShell ランタイムにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-114">Windows PowerShell providers are accessible to the Windows PowerShell runtime and to commands programmatically through the use of Windows PowerShell paths.</span></span> <span data-ttu-id="bcdfe-115">ほとんどの場合、これらのパスは、プロバイダーを介してデータに直接アクセスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-115">Most of the time, these paths are used to directly access the data through the provider.</span></span> <span data-ttu-id="bcdfe-116">ただし、いくつかのパスは、データにアクセスする Windows PowerShell 以外のアプリケーション プログラミング インターフェイス (Api) を使用するコマンドレットを許可するプロバイダーの内部のパスに解決できます。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-116">However, some paths can be resolved to provider-internal paths that allow a cmdlet to use non-Windows PowerShell application programming interfaces (APIs) to access the data.</span></span> <span data-ttu-id="bcdfe-117">Windows PowerShell 内での Windows PowerShell プロバイダーの動作方法の詳細については、次を参照してください。 [Windows PowerShell のしくみ](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-117">For more information about how Windows PowerShell providers operate within Windows PowerShell, see [How Windows PowerShell Works](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58).</span></span>

## <a name="exposing-provider-cmdlets-using-windows-powershell-drives"></a><span data-ttu-id="bcdfe-118">ドライブの Windows PowerShell を使用して、プロバイダー コマンドレットを公開します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-118">Exposing Provider Cmdlets Using Windows PowerShell Drives</span></span>

<span data-ttu-id="bcdfe-119">Windows PowerShell プロバイダーは、仮想の Windows PowerShell ドライブを使用して、サポートされているコマンドレットを公開します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-119">A Windows PowerShell provider exposes its supported cmdlets using virtual Windows PowerShell drives.</span></span> <span data-ttu-id="bcdfe-120">Windows PowerShell には、Windows PowerShell ドライブに対して次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-120">Windows PowerShell applies the following rules for a Windows PowerShell drive:</span></span>

- <span data-ttu-id="bcdfe-121">ドライブの名前は、任意の英数字のシーケンスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-121">The name of a drive can be any alphanumeric sequence.</span></span>

- <span data-ttu-id="bcdfe-122">"Root"と呼ばれる、パス上の任意の有効なポイントでは、ドライブを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-122">A drive can be specified at any valid point on a path, called a "root".</span></span>

- <span data-ttu-id="bcdfe-123">ドライブは、ファイル システムだけでなく、格納されているデータを実装できます。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-123">A drive can be implemented for any stored data, not just the file system.</span></span>

- <span data-ttu-id="bcdfe-124">各ドライブでは、独自の現在の作業場所ドライブ間で移行するときに、コンテキストを保持するユーザーを許可するが保持されます。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-124">Each drive keeps its own current working location, allowing the user to retain context when shifting between drives.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="bcdfe-125">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bcdfe-125">In This Section</span></span>

<span data-ttu-id="bcdfe-126">次の表は、相互に構築するコード例が含まれるトピックを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-126">The following table lists topics that include code examples that build on each other.</span></span> <span data-ttu-id="bcdfe-127">以降、2 番目のトピックでは、基本的な Windows PowerShell プロバイダーを初期化し、Windows PowerShell ランタイムによって初期化されていない、次のトピックでは、データにアクセスするための機能を追加します、次のトピックでは、データ (を操作するための機能を追加します。格納されているデータの項目)、これにします。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-127">Starting with the second topic, the basic Windows PowerShell provider can be initialized and uninitialized by the Windows PowerShell runtime, the next topic adds functionality for accessing the data, the next topic adds functionality for manipulating the data (the items in the stored data), and so on.</span></span>

|<span data-ttu-id="bcdfe-128">トピック</span><span class="sxs-lookup"><span data-stu-id="bcdfe-128">Topic</span></span>|<span data-ttu-id="bcdfe-129">定義</span><span class="sxs-lookup"><span data-stu-id="bcdfe-129">Definition</span></span>|
|-----------|----------------|
|[<span data-ttu-id="bcdfe-130">Windows PowerShell プロバイダーのデザイン</span><span class="sxs-lookup"><span data-stu-id="bcdfe-130">Designing Your Windows PowerShell Provider</span></span>](./designing-your-windows-powershell-provider.md)|<span data-ttu-id="bcdfe-131">このトピックでは、Windows PowerShell プロバイダーを実装する前に考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-131">This topic discusses things you should consider before implementing a Windows PowerShell provider.</span></span> <span data-ttu-id="bcdfe-132">Windows PowerShell プロバイダーの基本クラスと使用されるインターフェイスをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-132">It summarizes the Windows PowerShell provider base classes and interfaces that are used.</span></span>|
|[<span data-ttu-id="bcdfe-133">基本的な Windows PowerShell プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-133">Creating a Basic Windows PowerShell Provider</span></span>](./creating-a-basic-windows-powershell-provider.md)|<span data-ttu-id="bcdfe-134">このトピックでは、Windows PowerShell プロバイダーにより、プロバイダーを初期化して、Windows PowerShell ランタイムを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-134">This topic shows how to create a Windows PowerShell provider that allows the Windows PowerShell runtime to initialize and uninitialize the provider.</span></span>|
|[<span data-ttu-id="bcdfe-135">Windows PowerShell ドライブ プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-135">Creating a Windows PowerShell Drive Provider</span></span>](./creating-a-windows-powershell-drive-provider.md)|<span data-ttu-id="bcdfe-136">このトピックでは、Windows PowerShell ドライブをデータ ストアにアクセスするユーザーのための Windows PowerShell プロバイダーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-136">This topic shows how to create a Windows PowerShell provider that allows the user to access a data store through a Windows PowerShell drive.</span></span>|
|[<span data-ttu-id="bcdfe-137">Windows PowerShell 項目プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-137">Creating a Windows PowerShell Item Provider</span></span>](./creating-a-windows-powershell-item-provider.md)|<span data-ttu-id="bcdfe-138">このトピックでは、ユーザーがデータ ストア内のアイテムを操作できる Windows PowerShell プロバイダーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-138">This topic shows how to create a Windows PowerShell provider that allows the user to manipulate the items in a data store.</span></span>|
|[<span data-ttu-id="bcdfe-139">Windows PowerShell コンテナー プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-139">Creating a Windows PowerShell Container Provider</span></span>](./creating-a-windows-powershell-container-provider.md)|<span data-ttu-id="bcdfe-140">このトピックでは、複数レイヤーのデータ ストアで作業するユーザーのための Windows PowerShell プロバイダーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-140">This topic shows how to create a Windows PowerShell provider that allows the user to work on multilayer data stores.</span></span>|
|[<span data-ttu-id="bcdfe-141">Windows PowerShell ナビゲーション プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-141">Creating a Windows PowerShell Navigation Provider</span></span>](./creating-a-windows-powershell-navigation-provider.md)|<span data-ttu-id="bcdfe-142">このトピックでは、階層的にデータ ストアの項目を移動するユーザーのための Windows PowerShell プロバイダーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-142">This topic shows how to create a Windows PowerShell provider that allows the user to navigate the items of a data store in a hierarchical manner.</span></span>|
|[<span data-ttu-id="bcdfe-143">Windows PowerShell コンテンツ プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-143">Creating a Windows PowerShell Content Provider</span></span>](./creating-a-windows-powershell-content-provider.md)|<span data-ttu-id="bcdfe-144">このトピックでは、データ ストア内のアイテムのコンテンツを操作するユーザーのための Windows PowerShell プロバイダーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-144">This topic shows how to create a Windows PowerShell provider that allows the user to manipulate the content of items in a data store.</span></span>|
|[<span data-ttu-id="bcdfe-145">Windows PowerShell プロパティ プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-145">Creating a Windows PowerShell Property Provider</span></span>](./creating-a-windows-powershell-property-provider.md)|<span data-ttu-id="bcdfe-146">このトピックでは、ユーザーがデータ ストア内のアイテムのプロパティを操作できる Windows PowerShell プロバイダーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bcdfe-146">This topic shows how to create a Windows PowerShell provider that allows the user to manipulate the properties of items in a data store.</span></span>|

## <a name="see-also"></a><span data-ttu-id="bcdfe-147">参照</span><span class="sxs-lookup"><span data-stu-id="bcdfe-147">See Also</span></span>

[<span data-ttu-id="bcdfe-148">Windows PowerShell の動作</span><span class="sxs-lookup"><span data-stu-id="bcdfe-148">How Windows PowerShell Works</span></span>](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[<span data-ttu-id="bcdfe-149">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="bcdfe-149">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="bcdfe-150">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="bcdfe-150">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)
