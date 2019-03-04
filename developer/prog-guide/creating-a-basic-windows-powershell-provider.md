---
title: 基本的な Windows PowerShell プロバイダーを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- base provider [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], base provider
ms.assetid: 11eeea41-15c8-47ad-9016-0f4b72573305
caps.latest.revision: 7
ms.openlocfilehash: 19cc3817016d96e1412a5f3506e9d694ba55b48d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861768"
---
# <a name="creating-a-basic-windows-powershell-provider"></a><span data-ttu-id="1f096-102">基本的な Windows PowerShell プロバイダーを作成する</span><span class="sxs-lookup"><span data-stu-id="1f096-102">Creating a Basic Windows PowerShell Provider</span></span>

<span data-ttu-id="1f096-103">このトピックでは、Windows PowerShell プロバイダーを作成する方法を学習するための開始点です。</span><span class="sxs-lookup"><span data-stu-id="1f096-103">This topic is the starting point for learning how to create a Windows PowerShell provider.</span></span> <span data-ttu-id="1f096-104">ここで説明した基本的なプロバイダーが開始と停止、プロバイダーのメソッドを提供し、このプロバイダーには、データ ストアにアクセスするか、取得またはデータ ストアにデータを設定することはできませんで必要とされる基本的な機能が、すべてのプロバイダー。</span><span class="sxs-lookup"><span data-stu-id="1f096-104">The basic provider described here provides methods for starting and stopping the provider, and although this provider does not provide a means to access a data store or to get or set the data in the data store, it does provide the basic functionality that is required by all providers.</span></span>

<span data-ttu-id="1f096-105">以前は、「基本的なプロバイダーを説明したようにここでの開始と、プロバイダーを停止するメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="1f096-105">As mentioned previously, the basic provider described here implements methods for starting and stopping the provider.</span></span> <span data-ttu-id="1f096-106">Windows PowerShell ランタイムでは、プロバイダーを初期化して、これらのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1f096-106">The Windows PowerShell runtime calls these methods to initialize and uninitialize the provider.</span></span>

> [!NOTE]
> <span data-ttu-id="1f096-107">Windows PowerShell によって提供される AccessDBSampleProvider01.cs ファイルでは、このプロバイダーのサンプルが見つかります。</span><span class="sxs-lookup"><span data-stu-id="1f096-107">You can find a sample of this provider in the AccessDBSampleProvider01.cs file provided by Windows PowerShell.</span></span>

<span data-ttu-id="1f096-108">このトピックのセクションは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1f096-108">The sections in this topic include the following:</span></span>

- [<span data-ttu-id="1f096-109">Windows PowerShell プロバイダー クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="1f096-109">Defining the Windows PowerShell Provider Class</span></span>](#Defining-the-Windows-PowerShell-Provider-Class)

- [<span data-ttu-id="1f096-110">プロバイダー固有の状態情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="1f096-110">Defining Provider-Specific State Information</span></span>](#Defining-Provider-Specific-State-Information)

- [<span data-ttu-id="1f096-111">プロバイダーの初期化</span><span class="sxs-lookup"><span data-stu-id="1f096-111">Initializing the Provider</span></span>](#Initializing-the-Provider)

- [<span data-ttu-id="1f096-112">動的パラメーターを開始します。</span><span class="sxs-lookup"><span data-stu-id="1f096-112">Start Dynamic Parameters</span></span>](#Start-Dynamic-Parameters)

- [<span data-ttu-id="1f096-113">プロバイダーの初期化解除</span><span class="sxs-lookup"><span data-stu-id="1f096-113">Uninitializing the Provider</span></span>](#Uninitializing-the-Provider)

- [<span data-ttu-id="1f096-114">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="1f096-114">Code Sample</span></span>](#Code-Sample)

- [<span data-ttu-id="1f096-115">Windows PowerShell プロバイダーのテスト</span><span class="sxs-lookup"><span data-stu-id="1f096-115">Testing the Windows PowerShell Provider</span></span>](#Testing-the-Windows-PowerShell-Provider)

## <a name="defining-the-windows-powershell-provider-class"></a><span data-ttu-id="1f096-116">Windows PowerShell プロバイダー クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="1f096-116">Defining the Windows PowerShell Provider Class</span></span>

<span data-ttu-id="1f096-117">Windows PowerShell プロバイダーを作成する最初の手順では、その .NET クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="1f096-117">The first step in creating a Windows PowerShell provider is to define its .NET class.</span></span> <span data-ttu-id="1f096-118">この基本的なプロバイダーと呼ばれるクラスを定義する`AccessDBProvider`から派生した、 [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)基本クラス。</span><span class="sxs-lookup"><span data-stu-id="1f096-118">This basic provider defines a class called `AccessDBProvider` that derives from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) base class.</span></span>

<span data-ttu-id="1f096-119">プロバイダーのクラスを配置することをお勧めしますが、 `Providers` API 名前空間、xxx などの名前空間。PowerShell.Providers します。</span><span class="sxs-lookup"><span data-stu-id="1f096-119">It is recommended that you place your provider classes in a `Providers` namespace of your API namespace, for example, xxx.PowerShell.Providers.</span></span> <span data-ttu-id="1f096-120">このプロバイダーを使用して、`Microsoft.Samples.PowerShell.Provider`名前空間、すべての Windows PowerShell プロバイダーのサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="1f096-120">This provider uses the `Microsoft.Samples.PowerShell.Provider` namespace, in which all Windows PowerShell provider samples run.</span></span>

> [!NOTE]
> <span data-ttu-id="1f096-121">Windows PowerShell プロバイダーのクラスする必要があります明示的にパブリックと指定します。</span><span class="sxs-lookup"><span data-stu-id="1f096-121">The class for a Windows PowerShell provider must be explicitly marked as public.</span></span> <span data-ttu-id="1f096-122">Public としてマークされていないクラスは、内部には既定であり、Windows PowerShell ランタイムでは検出されません。</span><span class="sxs-lookup"><span data-stu-id="1f096-122">Classes not marked as public will default to internal and will not be found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="1f096-123">この基本的なプロバイダーのクラス定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1f096-123">Here is the class definition for this basic provider:</span></span>

[!code-csharp[AccessDBProviderSample01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs#L23-L24 "AccessDBProviderSample01.cs")]

<span data-ttu-id="1f096-124">宣言する必要があります、クラス定義の直前、 [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)属性には、[CmdletProvider()] 構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f096-124">Right before the class definition, you must declare the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute, with the syntax [CmdletProvider()].</span></span>

<span data-ttu-id="1f096-125">必要に応じてさらに、クラスを宣言する属性のキーワードを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="1f096-125">You can set attribute keywords to further declare the class if necessary.</span></span> <span data-ttu-id="1f096-126">なお、 [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)ここで宣言された属性には、2 つのパラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1f096-126">Notice that the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute declared here includes two parameters.</span></span> <span data-ttu-id="1f096-127">属性の最初のパラメーターには、プロバイダーは、ユーザーが後で変更できる既定のわかりやすい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f096-127">The first attribute parameter specifies the default-friendly name for the provider, which the user can modify later.</span></span> <span data-ttu-id="1f096-128">2 番目のパラメーターには、プロバイダーがコマンドの処理中に、Windows PowerShell ランタイムに公開する Windows PowerShell で定義されている機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f096-128">The second parameter specifies the Windows PowerShell-defined capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span> <span data-ttu-id="1f096-129">によって、プロバイダーの機能の有効な値が定義されている、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。</span><span class="sxs-lookup"><span data-stu-id="1f096-129">The possible values for the provider capabilities are defined by the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="1f096-130">これは、基本プロバイダーであるためありませんの機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="1f096-130">Because this is a base provider, it supports no capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="1f096-131">Windows PowerShell プロバイダーの完全修飾名には、アセンブリの名前と、プロバイダーの登録時に Windows PowerShell によって決定するその他の属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1f096-131">The fully qualified name of the Windows PowerShell provider includes the assembly name and other attributes determined by Windows PowerShell upon registration of the provider.</span></span>

## <a name="defining-provider-specific-state-information"></a><span data-ttu-id="1f096-132">プロバイダー固有の状態情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="1f096-132">Defining Provider-Specific State Information</span></span>

<span data-ttu-id="1f096-133">[System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)基底クラスとすべての派生クラスはステートレスと見なされるため、Windows PowerShell ランタイムが必要なだけのプロバイダーのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f096-133">The [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) base class and all derived classes are considered stateless because the Windows PowerShell runtime creates provider instances only as required.</span></span> <span data-ttu-id="1f096-134">そのため、ご利用のプロバイダーは、フル コントロール、プロバイダー固有のデータの状態のメンテナンスを必要とする場合にする必要がありますからクラスを派生、 [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo)クラス。</span><span class="sxs-lookup"><span data-stu-id="1f096-134">Therefore, if your provider requires full control and state maintenance for provider-specific data, it must derive a class from the [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) class.</span></span> <span data-ttu-id="1f096-135">派生クラスは、プロバイダー固有のデータは、Windows PowerShell ランタイムが呼び出すと、アクセスできるように、状態を維持するために必要なメンバーを定義する必要があります、 [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start)プロバイダーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="1f096-135">Your derived class should define the members necessary to maintain the state so that the provider-specific data can be accessed when the Windows PowerShell runtime calls the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method to initialize the provider.</span></span>

<span data-ttu-id="1f096-136">Windows PowerShell プロバイダーは、接続ベースの状態を維持することもできます。</span><span class="sxs-lookup"><span data-stu-id="1f096-136">A Windows PowerShell provider can also maintain connection-based state.</span></span> <span data-ttu-id="1f096-137">接続の状態を維持する詳細については、次を参照してください。 [PowerShell ドライブ プロバイダーを作成する](./creating-a-windows-powershell-drive-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f096-137">For more information about maintaining connection state, see [Creating a PowerShell Drive Provider](./creating-a-windows-powershell-drive-provider.md).</span></span>

## <a name="initializing-the-provider"></a><span data-ttu-id="1f096-138">プロバイダーの初期化</span><span class="sxs-lookup"><span data-stu-id="1f096-138">Initializing the Provider</span></span>

<span data-ttu-id="1f096-139">プロバイダーを Windows PowerShell ランタイムを初期化するために、 [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start)メソッドは、Windows PowerShell の開始時にします。</span><span class="sxs-lookup"><span data-stu-id="1f096-139">To initialize the provider, the Windows PowerShell runtime calls the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method when Windows PowerShell is started.</span></span> <span data-ttu-id="1f096-140">プロバイダーがこのメソッドは、単純に返すの既定の実装を使用するほとんどの場合、 [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo)プロバイダーを記述するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1f096-140">For the most part, your provider can use the default implementation of this method, which simply returns the [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) object that describes your provider.</span></span> <span data-ttu-id="1f096-141">ただし、追加の初期化情報を追加する場合は、実装すること、独自[System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) の修正バージョンを返すメソッド[System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo)をプロバイダーに渡されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1f096-141">However, in the case where you want to add additional initialization information, you should implement your own [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method that returns a modified version of the [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) object that is passed to your provider.</span></span> <span data-ttu-id="1f096-142">一般に、このメソッドは、指定された返します[System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) 、または、変更されたオブジェクトが渡される[System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo)オブジェクトその他の初期化情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1f096-142">In general, this method should return the provided [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) object passed to it or a modified [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) object that contains other initialization information.</span></span>

<span data-ttu-id="1f096-143">この基本的なプロバイダーは、このメソッドをオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="1f096-143">This basic provider does not override this method.</span></span> <span data-ttu-id="1f096-144">ただし、次のコードは、このメソッドの既定の実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="1f096-144">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStart](Msh_samplesaccessdbprov01#accessdbprov01ProviderStart)]  -->

<span data-ttu-id="1f096-145">」の説明に従って、プロバイダーはプロバイダー固有の情報の状態を保持できる[プロバイダーに固有のデータの状態を定義する](#Defining-Provider-Specific-State-Information)します。</span><span class="sxs-lookup"><span data-stu-id="1f096-145">The provider can maintain the state of provider-specific information as described in [Defining Provider-specific Data State](#Defining-Provider-Specific-State-Information).</span></span> <span data-ttu-id="1f096-146">この場合、実装をオーバーライドする必要があります、 [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start)派生クラスのインスタンスを返すメソッド。</span><span class="sxs-lookup"><span data-stu-id="1f096-146">In this case, your implementation must override the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method to return an instance of the derived class.</span></span>

## <a name="start-dynamic-parameters"></a><span data-ttu-id="1f096-147">動的パラメーターを開始します。</span><span class="sxs-lookup"><span data-stu-id="1f096-147">Start Dynamic Parameters</span></span>

<span data-ttu-id="1f096-148">プロバイダーの実装、 [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start)メソッドは、追加のパラメーターを必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f096-148">Your provider implementation of the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method might require additional parameters.</span></span> <span data-ttu-id="1f096-149">この場合、プロバイダーをオーバーライドする必要があります、 [System.Management.Automation.Provider.Cmdletprovider.Startdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.StartDynamicParameters)メソッドおよびプロパティと解析を持つフィールドを持つオブジェクトの属性のような戻り値をcmdlet クラスまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1f096-149">In this case, the provider should override the [System.Management.Automation.Provider.Cmdletprovider.Startdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.StartDynamicParameters) method and return an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span>

<span data-ttu-id="1f096-150">この基本的なプロバイダーは、このメソッドをオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="1f096-150">This basic provider does not override this method.</span></span> <span data-ttu-id="1f096-151">ただし、次のコードは、このメソッドの既定の実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="1f096-151">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters](Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters)]  -->

## <a name="uninitializing-the-provider"></a><span data-ttu-id="1f096-152">プロバイダーの初期化解除</span><span class="sxs-lookup"><span data-stu-id="1f096-152">Uninitializing the Provider</span></span>

<span data-ttu-id="1f096-153">Windows PowerShell プロバイダーで使用されるリソースを解放する、プロバイダー実装する独自[System.Management.Automation.Provider.Cmdletprovider.Stop\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Stop)メソッド。</span><span class="sxs-lookup"><span data-stu-id="1f096-153">To free resources that the Windows PowerShell provider uses, your provider should implement its own [System.Management.Automation.Provider.Cmdletprovider.Stop\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Stop) method.</span></span> <span data-ttu-id="1f096-154">このメソッドは、セッションの終了時のプロバイダーの初期化解除に Windows PowerShell ランタイムによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1f096-154">This method is called by the Windows PowerShell runtime to uninitialize the provider at the close of a session.</span></span>

<span data-ttu-id="1f096-155">この基本的なプロバイダーは、このメソッドをオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="1f096-155">This basic provider does not override this method.</span></span> <span data-ttu-id="1f096-156">ただし、次のコードは、このメソッドの既定の実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="1f096-156">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStop](Msh_samplesaccessdbprov01#accessdbprov01ProviderStop)]  -->

## <a name="code-sample"></a><span data-ttu-id="1f096-157">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="1f096-157">Code Sample</span></span>

<span data-ttu-id="1f096-158">完全なサンプル コードでは、次を参照してください。 [AccessDbProviderSample01 コード サンプル](./accessdbprovidersample01-code-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f096-158">For complete sample code, see [AccessDbProviderSample01 Code Sample](./accessdbprovidersample01-code-sample.md).</span></span>

## <a name="testing-the-windows-powershell-provider"></a><span data-ttu-id="1f096-159">Windows PowerShell プロバイダーのテスト</span><span class="sxs-lookup"><span data-stu-id="1f096-159">Testing the Windows PowerShell Provider</span></span>

<span data-ttu-id="1f096-160">Windows PowerShell を使用した、Windows PowerShell プロバイダーを登録すると、コマンドラインでサポートされているコマンドレットを実行してテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="1f096-160">Once your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line.</span></span> <span data-ttu-id="1f096-161">この基本的なプロバイダーに、新しいシェルを実行し、使用、`Get-PSProvider`コマンドレットをプロバイダーの一覧を取得して AccessDb プロバイダーが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f096-161">For this basic provider, run the new shell and use the `Get-PSProvider` cmdlet to retrieve the list of providers and ensure that the AccessDb provider is present.</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="1f096-162">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f096-162">The following output appears:</span></span>

```output
Name                 Capabilities                  Drives
----                 ------------                  ------
AccessDb             None                          {}
Alias                ShouldProcess                 {Alias}
Environment          ShouldProcess                 {Env}
FileSystem           Filter, ShouldProcess         {C, Z}
Function             ShouldProcess                 {function}
Registry             ShouldProcess                 {HKLM, HKCU}
```

## <a name="see-also"></a><span data-ttu-id="1f096-163">参照</span><span class="sxs-lookup"><span data-stu-id="1f096-163">See Also</span></span>

[<span data-ttu-id="1f096-164">Windows PowerShell プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f096-164">Creating Windows PowerShell Providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="1f096-165">Windows PowerShell プロバイダーのデザイン</span><span class="sxs-lookup"><span data-stu-id="1f096-165">Designing Your Windows PowerShell Provider</span></span>](./designing-your-windows-powershell-provider.md)