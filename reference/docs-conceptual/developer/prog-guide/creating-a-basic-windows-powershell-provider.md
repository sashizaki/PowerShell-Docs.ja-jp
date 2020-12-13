---
ms.date: 09/13/2016
ms.topic: reference
title: 基本的な Windows PowerShell プロバイダーを作成する
description: 基本的な Windows PowerShell プロバイダーを作成する
ms.openlocfilehash: 03b5784fd063b5457fc64d92a32e286e3bf9cce4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647505"
---
# <a name="creating-a-basic-windows-powershell-provider"></a><span data-ttu-id="c9f68-103">基本的な Windows PowerShell プロバイダーを作成する</span><span class="sxs-lookup"><span data-stu-id="c9f68-103">Creating a Basic Windows PowerShell Provider</span></span>

<span data-ttu-id="c9f68-104">このトピックは、Windows PowerShell プロバイダーを作成する方法を学習するための出発点となります。</span><span class="sxs-lookup"><span data-stu-id="c9f68-104">This topic is the starting point for learning how to create a Windows PowerShell provider.</span></span> <span data-ttu-id="c9f68-105">ここで説明する基本的なプロバイダーは、プロバイダーを開始および停止するためのメソッドを提供します。このプロバイダーは、データストアにアクセスしたり、データストア内のデータを取得または設定したりする手段を提供するものではなく、すべてのプロバイダーで必要な基本的な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="c9f68-105">The basic provider described here provides methods for starting and stopping the provider, and although this provider does not provide a means to access a data store or to get or set the data in the data store, it does provide the basic functionality that is required by all providers.</span></span>

<span data-ttu-id="c9f68-106">前述のように、ここで説明する基本的なプロバイダーは、プロバイダーを起動および停止するためのメソッドを実装しています。</span><span class="sxs-lookup"><span data-stu-id="c9f68-106">As mentioned previously, the basic provider described here implements methods for starting and stopping the provider.</span></span> <span data-ttu-id="c9f68-107">Windows PowerShell ランタイムは、これらのメソッドを呼び出して、プロバイダーの初期化と初期化解除を行います。</span><span class="sxs-lookup"><span data-stu-id="c9f68-107">The Windows PowerShell runtime calls these methods to initialize and uninitialize the provider.</span></span>

> [!NOTE]
> <span data-ttu-id="c9f68-108">このプロバイダーのサンプルは、Windows PowerShell によって提供される AccessDBSampleProvider01.cs ファイルにあります。</span><span class="sxs-lookup"><span data-stu-id="c9f68-108">You can find a sample of this provider in the AccessDBSampleProvider01.cs file provided by Windows PowerShell.</span></span>

## <a name="defining-the-windows-powershell-provider-class"></a><span data-ttu-id="c9f68-109">Windows PowerShell プロバイダークラスの定義</span><span class="sxs-lookup"><span data-stu-id="c9f68-109">Defining the Windows PowerShell Provider Class</span></span>

<span data-ttu-id="c9f68-110">Windows PowerShell プロバイダーを作成するための最初の手順は、.NET クラスを定義することです。</span><span class="sxs-lookup"><span data-stu-id="c9f68-110">The first step in creating a Windows PowerShell provider is to define its .NET class.</span></span> <span data-ttu-id="c9f68-111">この基本プロバイダーでは、というクラスを定義しています。このクラスは、という `AccessDBProvider` [プロバイダー](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) の基底クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="c9f68-111">This basic provider defines a class called `AccessDBProvider` that derives from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) base class.</span></span>

<span data-ttu-id="c9f68-112">プロバイダークラスは、 `Providers` API 名前空間の名前空間 (たとえば、xxx. PowerShell プロバイダー) に配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c9f68-112">It is recommended that you place your provider classes in a `Providers` namespace of your API namespace, for example, xxx.PowerShell.Providers.</span></span> <span data-ttu-id="c9f68-113">このプロバイダーは、 `Microsoft.Samples.PowerShell.Provider` すべての Windows PowerShell プロバイダーのサンプルを実行する名前空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f68-113">This provider uses the `Microsoft.Samples.PowerShell.Provider` namespace, in which all Windows PowerShell provider samples run.</span></span>

> [!NOTE]
> <span data-ttu-id="c9f68-114">Windows PowerShell プロバイダーのクラスは、明示的にパブリックとしてマークされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9f68-114">The class for a Windows PowerShell provider must be explicitly marked as public.</span></span> <span data-ttu-id="c9f68-115">パブリックとしてマークされていないクラスは、既定で内部に設定され、Windows PowerShell ランタイムによって検出されません。</span><span class="sxs-lookup"><span data-stu-id="c9f68-115">Classes not marked as public will default to internal and will not be found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="c9f68-116">この基本プロバイダーのクラス定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c9f68-116">Here is the class definition for this basic provider:</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="23-24":::

<span data-ttu-id="c9f68-117">クラス定義の直前に、構文 [[の表示プロバイダー ()] を使用して、"system.servicemodel" 属性を宣言する必要が[あります。](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)</span><span class="sxs-lookup"><span data-stu-id="c9f68-117">Right before the class definition, you must declare the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute, with the syntax [CmdletProvider()].</span></span>

<span data-ttu-id="c9f68-118">必要に応じて、クラスをさらに宣言する属性キーワードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c9f68-118">You can set attribute keywords to further declare the class if necessary.</span></span> <span data-ttu-id="c9f68-119">ここで宣言されている system.string 属性に [は、2つのパラメーター](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) が含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c9f68-119">Notice that the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute declared here includes two parameters.</span></span> <span data-ttu-id="c9f68-120">最初の属性パラメーターは、プロバイダーの既定のわかりやすい名前を指定します。ユーザーは後で変更できます。</span><span class="sxs-lookup"><span data-stu-id="c9f68-120">The first attribute parameter specifies the default-friendly name for the provider, which the user can modify later.</span></span> <span data-ttu-id="c9f68-121">2番目のパラメーターは、コマンドの処理中にプロバイダーが Windows PowerShell ランタイムに公開する Windows PowerShell 定義の機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="c9f68-121">The second parameter specifies the Windows PowerShell-defined capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span> <span data-ttu-id="c9f68-122">プロバイダー機能に使用できる値は、system.servicemodel [機能](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) の列挙型によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="c9f68-122">The possible values for the provider capabilities are defined by the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="c9f68-123">これは基本プロバイダーであるため、機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c9f68-123">Because this is a base provider, it supports no capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="c9f68-124">Windows PowerShell プロバイダーの完全修飾名には、アセンブリ名と、プロバイダーの登録時に Windows PowerShell によって決定されるその他の属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9f68-124">The fully qualified name of the Windows PowerShell provider includes the assembly name and other attributes determined by Windows PowerShell upon registration of the provider.</span></span>

## <a name="defining-provider-specific-state-information"></a><span data-ttu-id="c9f68-125">Provider-Specific 状態情報の定義</span><span class="sxs-lookup"><span data-stu-id="c9f68-125">Defining Provider-Specific State Information</span></span>

<span data-ttu-id="c9f68-126">Windows PowerShell ランタイムでは必要に応じてプロバイダーインスタンスが作成される [ため、この基本クラス](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) とすべての派生クラスはステートレスと見なされます。</span><span class="sxs-lookup"><span data-stu-id="c9f68-126">The [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) base class and all derived classes are considered stateless because the Windows PowerShell runtime creates provider instances only as required.</span></span> <span data-ttu-id="c9f68-127">したがって、プロバイダー固有のデータに対して完全な制御と状態の保守が必要な場合は、クラスを system.servicemodel クラスから派生させる必要が[あります。](/dotnet/api/System.Management.Automation.ProviderInfo)</span><span class="sxs-lookup"><span data-stu-id="c9f68-127">Therefore, if your provider requires full control and state maintenance for provider-specific data, it must derive a class from the [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) class.</span></span> <span data-ttu-id="c9f68-128">派生クラスでは、状態を維持するために必要なメンバーを定義する必要があります。これにより、Windows PowerShell ランタイムが、プロバイダーを初期化するため [に、このメソッドを](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) 呼び出すときに、プロバイダー固有のデータにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="c9f68-128">Your derived class should define the members necessary to maintain the state so that the provider-specific data can be accessed when the Windows PowerShell runtime calls the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method to initialize the provider.</span></span>

<span data-ttu-id="c9f68-129">Windows PowerShell プロバイダーは、接続ベースの状態を維持することもできます。</span><span class="sxs-lookup"><span data-stu-id="c9f68-129">A Windows PowerShell provider can also maintain connection-based state.</span></span> <span data-ttu-id="c9f68-130">接続状態の維持の詳細については、「 [PowerShell ドライブプロバイダーの作成](./creating-a-windows-powershell-drive-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9f68-130">For more information about maintaining connection state, see [Creating a PowerShell Drive Provider](./creating-a-windows-powershell-drive-provider.md).</span></span>

## <a name="initializing-the-provider"></a><span data-ttu-id="c9f68-131">プロバイダーを初期化しています</span><span class="sxs-lookup"><span data-stu-id="c9f68-131">Initializing the Provider</span></span>

<span data-ttu-id="c9f68-132">プロバイダーを初期化するために、windows powershell ランタイムは、Windows PowerShell が起動されたときに、 [システムの起動](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c9f68-132">To initialize the provider, the Windows PowerShell runtime calls the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method when Windows PowerShell is started.</span></span> <span data-ttu-id="c9f68-133">ほとんどの場合、プロバイダーはこのメソッドの既定の実装を使用できます。これにより、プロバイダーを記述する [system.servicemodel オブジェクトが返されます](/dotnet/api/System.Management.Automation.ProviderInfo) 。</span><span class="sxs-lookup"><span data-stu-id="c9f68-133">For the most part, your provider can use the default implementation of this method, which simply returns the [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) object that describes your provider.</span></span> <span data-ttu-id="c9f68-134">ただし、追加の初期化情報を追加する場合は、独自の [システム](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) を実装する必要があります。このメソッドは、プロバイダーに渡される変更されたバージョンの [system.string オブジェクトを](/dotnet/api/System.Management.Automation.ProviderInfo) 返す、変更されたバージョンのを返します。</span><span class="sxs-lookup"><span data-stu-id="c9f68-134">However, in the case where you want to add additional initialization information, you should implement your own [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method that returns a modified version of the [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) object that is passed to your provider.</span></span> <span data-ttu-id="c9f68-135">一般に、このメソッドは渡された [指定さ](/dotnet/api/System.Management.Automation.ProviderInfo) れた system.servicemodel オブジェクト、または他の初期化情報を含む変更された [system.servicemodel オブジェクトを](/dotnet/api/System.Management.Automation.ProviderInfo) 返します。</span><span class="sxs-lookup"><span data-stu-id="c9f68-135">In general, this method should return the provided [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) object passed to it or a modified [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) object that contains other initialization information.</span></span>

<span data-ttu-id="c9f68-136">この基本プロバイダーは、このメソッドをオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="c9f68-136">This basic provider does not override this method.</span></span> <span data-ttu-id="c9f68-137">ただし、次のコードは、このメソッドの既定の実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="c9f68-137">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStart](Msh_samplesaccessdbprov01#accessdbprov01ProviderStart)]  -->

<span data-ttu-id="c9f68-138">プロバイダーは、「 [プロバイダー固有のデータの状態の定義](#defining-provider-specific-state-information)」で説明されているように、プロバイダー固有の情報の状態を維持できます。</span><span class="sxs-lookup"><span data-stu-id="c9f68-138">The provider can maintain the state of provider-specific information as described in [Defining Provider-specific Data State](#defining-provider-specific-state-information).</span></span> <span data-ttu-id="c9f68-139">この場合、の実装では、派生クラスのインスタンスを返すように、 [このメソッドを](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) オーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9f68-139">In this case, your implementation must override the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method to return an instance of the derived class.</span></span>

## <a name="start-dynamic-parameters"></a><span data-ttu-id="c9f68-140">動的パラメーターの開始</span><span class="sxs-lookup"><span data-stu-id="c9f68-140">Start Dynamic Parameters</span></span>

<span data-ttu-id="c9f68-141">プロバイダーによる [システム](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) の実装では、追加のパラメーターが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c9f68-141">Your provider implementation of the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method might require additional parameters.</span></span> <span data-ttu-id="c9f68-142">この場合、プロバイダー [は、このメソッドを](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.StartDynamicParameters) オーバーライドして、コマンドレットクラスや [system.string オブジェクトと](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) 同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。この場合、プロバイダーはこのメソッドをオーバーライドして、プロパティとフィールドを持つオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c9f68-142">In this case, the provider should override the [System.Management.Automation.Provider.Cmdletprovider.Startdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.StartDynamicParameters) method and return an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span>

<span data-ttu-id="c9f68-143">この基本プロバイダーは、このメソッドをオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="c9f68-143">This basic provider does not override this method.</span></span> <span data-ttu-id="c9f68-144">ただし、次のコードは、このメソッドの既定の実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="c9f68-144">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters](Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters)]  -->

## <a name="uninitializing-the-provider"></a><span data-ttu-id="c9f68-145">プロバイダーの初期化解除</span><span class="sxs-lookup"><span data-stu-id="c9f68-145">Uninitializing the Provider</span></span>

<span data-ttu-id="c9f68-146">Windows PowerShell プロバイダーが使用するリソースを解放するには、プロバイダーが独自の [システムの管理](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Stop) を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9f68-146">To free resources that the Windows PowerShell provider uses, your provider should implement its own [System.Management.Automation.Provider.Cmdletprovider.Stop\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Stop) method.</span></span> <span data-ttu-id="c9f68-147">このメソッドは、セッションの終了時にプロバイダーを初期化解除するために、Windows PowerShell ランタイムによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c9f68-147">This method is called by the Windows PowerShell runtime to uninitialize the provider at the close of a session.</span></span>

<span data-ttu-id="c9f68-148">この基本プロバイダーは、このメソッドをオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="c9f68-148">This basic provider does not override this method.</span></span> <span data-ttu-id="c9f68-149">ただし、次のコードは、このメソッドの既定の実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="c9f68-149">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStop](Msh_samplesaccessdbprov01#accessdbprov01ProviderStop)]  -->

## <a name="code-sample"></a><span data-ttu-id="c9f68-150">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="c9f68-150">Code Sample</span></span>

<span data-ttu-id="c9f68-151">完全なサンプルコードについては、「 [AccessDbProviderSample01 のコードサンプル](./accessdbprovidersample01-code-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9f68-151">For complete sample code, see [AccessDbProviderSample01 Code Sample](./accessdbprovidersample01-code-sample.md).</span></span>

## <a name="testing-the-windows-powershell-provider"></a><span data-ttu-id="c9f68-152">Windows PowerShell プロバイダーのテスト</span><span class="sxs-lookup"><span data-stu-id="c9f68-152">Testing the Windows PowerShell Provider</span></span>

<span data-ttu-id="c9f68-153">Windows powershell プロバイダーが Windows PowerShell に登録されたら、サポートされているコマンドレットをコマンドラインで実行することでテストできます。</span><span class="sxs-lookup"><span data-stu-id="c9f68-153">Once your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line.</span></span> <span data-ttu-id="c9f68-154">この基本プロバイダーでは、新しいシェルを実行し、コマンドレットを使用して `Get-PSProvider` プロバイダーの一覧を取得し、AccessDb プロバイダーが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9f68-154">For this basic provider, run the new shell and use the `Get-PSProvider` cmdlet to retrieve the list of providers and ensure that the AccessDb provider is present.</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="c9f68-155">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9f68-155">The following output appears:</span></span>

```Output
Name                 Capabilities                  Drives
----                 ------------                  ------
AccessDb             None                          {}
Alias                ShouldProcess                 {Alias}
Environment          ShouldProcess                 {Env}
FileSystem           Filter, ShouldProcess         {C, Z}
Function             ShouldProcess                 {function}
Registry             ShouldProcess                 {HKLM, HKCU}
```

## <a name="see-also"></a><span data-ttu-id="c9f68-156">参照</span><span class="sxs-lookup"><span data-stu-id="c9f68-156">See Also</span></span>

[<span data-ttu-id="c9f68-157">Windows PowerShell プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="c9f68-157">Creating Windows PowerShell Providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="c9f68-158">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="c9f68-158">Designing Your Windows PowerShell Provider</span></span>](./designing-your-windows-powershell-provider.md)
