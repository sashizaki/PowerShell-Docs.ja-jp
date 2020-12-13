---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell ドライブ プロバイダーを作成する
description: Windows PowerShell ドライブ プロバイダーを作成する
ms.openlocfilehash: 639518fce27d941b7529b091364c5905c91a5c0c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92663042"
---
# <a name="creating-a-windows-powershell-drive-provider"></a><span data-ttu-id="156cf-103">Windows PowerShell ドライブ プロバイダーを作成する</span><span class="sxs-lookup"><span data-stu-id="156cf-103">Creating a Windows PowerShell Drive Provider</span></span>

<span data-ttu-id="156cf-104">このトピックでは、windows PowerShell ドライブを介してデータストアにアクセスする方法を提供する Windows PowerShell ドライブプロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="156cf-104">This topic describes how to create a Windows PowerShell drive provider that provides a way to access a data store through a Windows PowerShell drive.</span></span> <span data-ttu-id="156cf-105">この種類のプロバイダーは、Windows PowerShell ドライブプロバイダーとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="156cf-105">This type of provider is also referred to as Windows PowerShell drive providers.</span></span> <span data-ttu-id="156cf-106">プロバイダーによって使用される Windows PowerShell ドライブは、データストアに接続する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="156cf-106">The Windows PowerShell drives used by the provider provide the means to connect to the data store.</span></span>

<span data-ttu-id="156cf-107">ここに記載されている Windows PowerShell ドライブプロバイダーは、Microsoft Access データベースへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="156cf-107">The Windows PowerShell drive provider described here provides access to a Microsoft Access database.</span></span>
<span data-ttu-id="156cf-108">このプロバイダーの場合、Windows PowerShell ドライブはデータベースを表し (ドライブプロバイダーに任意の数のドライブを追加することができます)、ドライブの最上位のコンテナーはデータベース内のテーブルを表し、コンテナーの項目はテーブル内の行を表します。</span><span class="sxs-lookup"><span data-stu-id="156cf-108">For this provider, the Windows PowerShell drive represents the database (it is possible to add any number of drives to a drive provider), the top-level containers of the drive represent the tables in the database, and the items of the containers represent the rows in the tables.</span></span>

## <a name="defining-the-windows-powershell-provider-class"></a><span data-ttu-id="156cf-109">Windows PowerShell プロバイダークラスの定義</span><span class="sxs-lookup"><span data-stu-id="156cf-109">Defining the Windows PowerShell Provider Class</span></span>

<span data-ttu-id="156cf-110">Drive プロバイダーは、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) 基底クラスから派生する .net クラスを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="156cf-110">Your drive provider must define a .NET class that derives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) base class.</span></span> <span data-ttu-id="156cf-111">このドライブプロバイダーのクラス定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="156cf-111">Here is the class definition for this drive provider:</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="29-30":::

<span data-ttu-id="156cf-112">この例 [では、](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) この例では、コマンドの処理中にプロバイダーが windows powershell ランタイムに公開する、プロバイダーのユーザーフレンドリ名と、windows powershell 固有の機能を指定しています。</span><span class="sxs-lookup"><span data-stu-id="156cf-112">Notice that in this example, the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute specifies a user-friendly name for the provider and the Windows PowerShell specific capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span>
<span data-ttu-id="156cf-113">プロバイダー機能に使用できる値は、system.servicemodel [機能](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) の列挙型によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="156cf-113">The possible values for the provider capabilities are defined by the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="156cf-114">このドライブプロバイダーは、これらの機能のいずれもサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="156cf-114">This drive provider does not support any of these capabilities.</span></span>

## <a name="defining-base-functionality"></a><span data-ttu-id="156cf-115">基本機能の定義</span><span class="sxs-lookup"><span data-stu-id="156cf-115">Defining Base Functionality</span></span>

<span data-ttu-id="156cf-116">「 [Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」で説明されているように、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) クラスは、プロバイダーの初期化と初期化解除に必要なメソッドを定義する、system.servicemodel [プロバイダー](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) の基底クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="156cf-116">As described in [Design Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md), the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class derives from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) base class that defines the methods needed for initializing and uninitializing the provider.</span></span> <span data-ttu-id="156cf-117">セッション固有の初期化情報を追加し、プロバイダーによって使用されるリソースを解放するための機能を実装するには、「 [基本的な Windows PowerShell プロバイダーの作成](./creating-a-basic-windows-powershell-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="156cf-117">To implement functionality for adding session-specific initialization information and for releasing resources that are used by the provider, see [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span>
<span data-ttu-id="156cf-118">ただし、ほとんどのプロバイダー (ここで説明するプロバイダーを含む) は、Windows PowerShell によって提供されるこの機能の既定の実装を使用できます。</span><span class="sxs-lookup"><span data-stu-id="156cf-118">However, most providers (including the provider described here) can use the default implementation of this functionality that is provided by Windows PowerShell.</span></span>

## <a name="creating-drive-state-information"></a><span data-ttu-id="156cf-119">ドライブの状態情報の作成</span><span class="sxs-lookup"><span data-stu-id="156cf-119">Creating Drive State Information</span></span>

<span data-ttu-id="156cf-120">すべての Windows PowerShell プロバイダーはステートレスであると見なされます。つまり、ドライブプロバイダーは、プロバイダーを呼び出すときに、Windows PowerShell ランタイムが必要とする状態情報を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="156cf-120">All Windows PowerShell providers are considered stateless, which means that your drive provider needs to create any state information that is needed by the Windows PowerShell runtime when it calls your provider.</span></span>

<span data-ttu-id="156cf-121">このドライブプロバイダーの場合、状態情報には、ドライブ情報の一部として保持されているデータベースへの接続が含まれます。</span><span class="sxs-lookup"><span data-stu-id="156cf-121">For this drive provider, state information includes the connection to the database that is kept as part of the drive information.</span></span> <span data-ttu-id="156cf-122">次に示すコードは、この情報がドライブを説明する [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) オブジェクトにどのように格納されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="156cf-122">Here is code that shows how this information is stored in the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object that describes the drive:</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="130-151":::

## <a name="creating-a-drive"></a><span data-ttu-id="156cf-123">ドライブの作成</span><span class="sxs-lookup"><span data-stu-id="156cf-123">Creating a Drive</span></span>

<span data-ttu-id="156cf-124">Windows PowerShell ランタイムがドライブを作成できるようにするには、ドライブプロバイダーが [Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="156cf-124">To allow the Windows PowerShell runtime to create a drive, the drive provider must implement the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method.</span></span> <span data-ttu-id="156cf-125">次のコードは、このドライブプロバイダーの [Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) メソッドを実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="156cf-125">The following code shows the implementation of the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method for this drive provider:</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="42-84":::

<span data-ttu-id="156cf-126">このメソッドをオーバーライドするには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="156cf-126">Your override of this method should do the following:</span></span>

- <span data-ttu-id="156cf-127">System.Management.Automation.PSDriveinfo であることを確認し [ ます。ルート \*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) メンバーが存在し、データストアへの接続を確立できます。</span><span class="sxs-lookup"><span data-stu-id="156cf-127">Verify that the [System.Management.Automation.PSDriveinfo.Root\*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) member exists and that a connection to the data store can be made.</span></span>
- <span data-ttu-id="156cf-128">コマンドレットのサポートで、ドライブを作成し、接続メンバーを設定し `New-PSDrive` ます。</span><span class="sxs-lookup"><span data-stu-id="156cf-128">Create a drive and populate the connection member, in support of the `New-PSDrive` cmdlet.</span></span>
- <span data-ttu-id="156cf-129">提案されたドライブの [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) オブジェクトを検証します。</span><span class="sxs-lookup"><span data-stu-id="156cf-129">Validate the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object for the proposed drive.</span></span>
- <span data-ttu-id="156cf-130">ドライブを記述する [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) オブジェクトを、必要なパフォーマンス情報または信頼性情報を使用して変更するか、ドライブを使用して呼び出し元に追加のデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="156cf-130">Modify the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object that describes the drive with any required performance or reliability information, or provide extra data for callers using the drive.</span></span>
- <span data-ttu-id="156cf-131">[WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError)メソッドを使用してエラーを処理してから、を返し `null` ます。</span><span class="sxs-lookup"><span data-stu-id="156cf-131">Handle failures using the [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) method and then return `null`.</span></span>

  <span data-ttu-id="156cf-132">このメソッドは、メソッドに渡されたドライブ情報またはプロバイダー固有のバージョンのいずれかを返します。</span><span class="sxs-lookup"><span data-stu-id="156cf-132">This method returns either the drive information that was passed to the method or a provider-specific version of it.</span></span>

## <a name="attaching-dynamic-parameters-to-newdrive"></a><span data-ttu-id="156cf-133">動的パラメーターを NewDrive にアタッチしています</span><span class="sxs-lookup"><span data-stu-id="156cf-133">Attaching Dynamic Parameters to NewDrive</span></span>

<span data-ttu-id="156cf-134">`New-PSDrive`ドライブプロバイダーでサポートされているコマンドレットでは、追加のパラメーターが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="156cf-134">The `New-PSDrive` cmdlet supported by your drive provider might require additional parameters.</span></span> <span data-ttu-id="156cf-135">これらの動的パラメーターをコマンドレットにアタッチするために、プロバイダーは [Drivecmdletprovider. Newdrivedynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="156cf-135">To attach these dynamic parameters to the cmdlet, the provider implements the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) method.</span></span> <span data-ttu-id="156cf-136">このメソッドは、コマンドレットクラスや [system.string オブジェクトと](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) 同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="156cf-136">This method returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span>

<span data-ttu-id="156cf-137">このドライブプロバイダーは、このメソッドをオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="156cf-137">This drive provider does not override this method.</span></span> <span data-ttu-id="156cf-138">ただし、次のコードは、このメソッドの既定の実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="156cf-138">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters](Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters)]  -->

## <a name="removing-a-drive"></a><span data-ttu-id="156cf-139">ドライブの取り外し</span><span class="sxs-lookup"><span data-stu-id="156cf-139">Removing a Drive</span></span>

<span data-ttu-id="156cf-140">データベース接続を閉じるには、ドライブプロバイダーが [Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) メソッドを実装している必要があります。</span><span class="sxs-lookup"><span data-stu-id="156cf-140">To close the database connection, the drive provider must implement the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method.</span></span> <span data-ttu-id="156cf-141">このメソッドは、プロバイダー固有の情報をクリーンアップした後に、ドライブへの接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="156cf-141">This method closes the connection to the drive after cleaning up any provider-specific information.</span></span>

<span data-ttu-id="156cf-142">次のコードは、このドライブプロバイダーの [Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) メソッドを実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="156cf-142">The following code shows the implementation of the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method for this drive provider:</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="91-116":::

<span data-ttu-id="156cf-143">ドライブを削除できる場合、メソッドはパラメーターを使用してメソッドに渡された情報を返す必要があり `drive` ます。</span><span class="sxs-lookup"><span data-stu-id="156cf-143">If the drive can be removed, the method should return the information passed to the method through the `drive` parameter.</span></span> <span data-ttu-id="156cf-144">ドライブを削除できない場合、メソッドは例外を書き込み、を返す必要があり `null` ます。</span><span class="sxs-lookup"><span data-stu-id="156cf-144">If the drive cannot be removed, the method should write an exception and then return `null`.</span></span> <span data-ttu-id="156cf-145">プロバイダーがこのメソッドをオーバーライドしない場合、このメソッドの既定の実装は、入力として渡されたドライブ情報だけを返します。</span><span class="sxs-lookup"><span data-stu-id="156cf-145">If your provider does not override this method, the default implementation of this method just returns the drive information passed as input.</span></span>

## <a name="initializing-default-drives"></a><span data-ttu-id="156cf-146">既定のドライブの初期化</span><span class="sxs-lookup"><span data-stu-id="156cf-146">Initializing Default Drives</span></span>

<span data-ttu-id="156cf-147">ドライブプロバイダーは、ドライブをマウントするために [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="156cf-147">Your drive provider implements the [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) method to mount drives.</span></span> <span data-ttu-id="156cf-148">たとえば、コンピューターがドメインに参加している場合、Active Directory プロバイダーが既定の名前付けコンテキストのドライブをマウントすることがあります。</span><span class="sxs-lookup"><span data-stu-id="156cf-148">For example, the Active Directory provider might mount a drive for the default naming context if the computer is joined to a domain.</span></span>

<span data-ttu-id="156cf-149">このメソッドは、初期化されたドライブまたは空のコレクションに関するドライブ情報のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="156cf-149">This method returns a collection of drive information about the initialized drives, or an empty collection.</span></span> <span data-ttu-id="156cf-150">このメソッドの呼び出しは、Windows PowerShell ランタイムによっ [て、プロバイダー](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) を初期化するために、を呼び出した後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="156cf-150">The call to this method is made after the Windows PowerShell runtime calls the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method to initialize the provider.</span></span>

<span data-ttu-id="156cf-151">このドライブプロバイダーは、 [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) メソッドをオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="156cf-151">This drive provider does not override the [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) method.</span></span> <span data-ttu-id="156cf-152">ただし、次のコードは、空のドライブコレクションを返す既定の実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="156cf-152">However, the following code shows the default implementation, which returns an empty drive collection:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinitializedefaultdrives](Msh_samplestestcmdlets#testproviderinitializedefaultdrives)]  -->

#### <a name="things-to-remember-about-implementing-initializedefaultdrives"></a><span data-ttu-id="156cf-153">InitializeDefaultDrives の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="156cf-153">Things to Remember About Implementing InitializeDefaultDrives</span></span>

<span data-ttu-id="156cf-154">すべてのドライブプロバイダーは、ユーザーが見つけやすいように、ルートドライブをマウントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="156cf-154">All drive providers should mount a root drive to help the user with discoverability.</span></span> <span data-ttu-id="156cf-155">ルートドライブには、他のマウントされたドライブのルートとして機能する場所が一覧表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="156cf-155">The root drive might list locations that serve as roots for other mounted drives.</span></span> <span data-ttu-id="156cf-156">たとえば、Active Directory プロバイダーは、 `namingContext` ルート分散システム環境 (DSE) の属性で見つかった名前付けコンテキストを一覧表示するドライブを作成する場合があります。</span><span class="sxs-lookup"><span data-stu-id="156cf-156">For example, the Active Directory provider might create a drive that lists the naming contexts found in the `namingContext` attributes on the root Distributed System Environment (DSE).</span></span> <span data-ttu-id="156cf-157">これは、ユーザーが他のドライブのマウントポイントを検出するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="156cf-157">This helps users discover mount points for other drives.</span></span>

## <a name="code-sample"></a><span data-ttu-id="156cf-158">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="156cf-158">Code Sample</span></span>

<span data-ttu-id="156cf-159">完全なサンプルコードについては、「 [AccessDbProviderSample02 のコードサンプル](./accessdbprovidersample02-code-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="156cf-159">For complete sample code, see [AccessDbProviderSample02 Code Sample](./accessdbprovidersample02-code-sample.md).</span></span>

## <a name="testing-the-windows-powershell-drive-provider"></a><span data-ttu-id="156cf-160">Windows PowerShell ドライブプロバイダーのテスト</span><span class="sxs-lookup"><span data-stu-id="156cf-160">Testing the Windows PowerShell Drive Provider</span></span>

<span data-ttu-id="156cf-161">Windows PowerShell プロバイダーが Windows PowerShell に登録されている場合は、コマンドラインでサポートされているコマンドレットを実行してテストできます。これには、派生によって使用可能なコマンドレットも含まれます。</span><span class="sxs-lookup"><span data-stu-id="156cf-161">When your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line, including any cmdlets made available by derivation.</span></span> <span data-ttu-id="156cf-162">サンプルドライブプロバイダーをテストしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="156cf-162">Let's test the sample drive provider.</span></span>

1. <span data-ttu-id="156cf-163">コマンドレットを実行して `Get-PSProvider` プロバイダーの一覧を取得し、AccessDB ドライブプロバイダーが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="156cf-163">Run the `Get-PSProvider` cmdlet to retrieve the list of providers to ensure that the AccessDB drive provider is present:</span></span>

   <span data-ttu-id="156cf-164">**PS> `Get-PSProvider`**</span><span class="sxs-lookup"><span data-stu-id="156cf-164">**PS> `Get-PSProvider`**</span></span>

   <span data-ttu-id="156cf-165">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="156cf-165">The following output appears:</span></span>

   ```Output
   Name                 Capabilities                  Drives
   ----                 ------------                  ------
   AccessDB             None                          {}
   Alias                ShouldProcess                 {Alias}
   Environment          ShouldProcess                 {Env}
   FileSystem           Filter, ShouldProcess         {C, Z}
   Function             ShouldProcess                 {function}
   Registry             ShouldProcess                 {HKLM, HKCU}
   ```

2. <span data-ttu-id="156cf-166">オペレーティングシステムの **管理ツール** の [**データソース**] 部分にアクセスして、データベースのデータベースサーバー名 (DSN) が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="156cf-166">Ensure that a database server name (DSN) exists for the database by accessing the **Data Sources** portion of the **Administrative Tools** for the operating system.</span></span> <span data-ttu-id="156cf-167">**ユーザー DSN** テーブルで、[ **MS Access データベース**] をダブルクリックし、ドライブパスを追加し `C:\ps\northwind.mdb` ます。</span><span class="sxs-lookup"><span data-stu-id="156cf-167">In the **User DSN** table, double-click **MS Access Database** and add the drive path `C:\ps\northwind.mdb`.</span></span>

3. <span data-ttu-id="156cf-168">サンプルドライブプロバイダーを使用して新しいドライブを作成します。</span><span class="sxs-lookup"><span data-stu-id="156cf-168">Create a new drive using the sample drive provider:</span></span>

   ```powershell
   new-psdrive -name mydb -root c:\ps\northwind.mdb -psprovider AccessDb`
   ```

   <span data-ttu-id="156cf-169">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="156cf-169">The following output appears:</span></span>

   ```Output
   Name     Provider     Root                   CurrentLocation
   ----     --------     ----                   ---------------
   mydb     AccessDB     c:\ps\northwind.mdb
   ```

4. <span data-ttu-id="156cf-170">接続を検証します。</span><span class="sxs-lookup"><span data-stu-id="156cf-170">Validate the connection.</span></span> <span data-ttu-id="156cf-171">接続はドライブのメンバーとして定義されているため、Get-PDDrive コマンドレットを使用して確認できます。</span><span class="sxs-lookup"><span data-stu-id="156cf-171">Because the connection is defined as a member of the drive, you can check it using the Get-PDDrive cmdlet.</span></span>

   > [!NOTE]
   > <span data-ttu-id="156cf-172">ユーザーは、その対話にコンテナー機能を必要とするため、プロバイダーをドライブとして操作することはできません。</span><span class="sxs-lookup"><span data-stu-id="156cf-172">The user cannot yet interact with the provider as a drive, as the provider needs container functionality for that interaction.</span></span> <span data-ttu-id="156cf-173">詳細については、「 [Windows PowerShell コンテナープロバイダーの作成](./creating-a-windows-powershell-container-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="156cf-173">For more information, see [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>

   <span data-ttu-id="156cf-174">**PS> (psdrive mydb). 接続**</span><span class="sxs-lookup"><span data-stu-id="156cf-174">**PS> (get-psdrive mydb).connection**</span></span>

   <span data-ttu-id="156cf-175">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="156cf-175">The following output appears:</span></span>

   ```Output
   ConnectionString  : Driver={Microsoft Access Driver (*.mdb)};DBQ=c:\ps\northwind.mdb
   ConnectionTimeout : 15
   Database          : c:\ps\northwind
   DataSource        : ACCESS
   ServerVersion     : 04.00.0000
   Driver            : odbcjt32.dll
   State             : Open
   Site              :
   Container         :
   ```

5. <span data-ttu-id="156cf-176">ドライブを取り外し、シェルを終了します。</span><span class="sxs-lookup"><span data-stu-id="156cf-176">Remove the drive and exit the shell:</span></span>

   ```powershell
   PS> remove-psdrive mydb
   PS> exit
   ```

## <a name="see-also"></a><span data-ttu-id="156cf-177">参照</span><span class="sxs-lookup"><span data-stu-id="156cf-177">See Also</span></span>

[<span data-ttu-id="156cf-178">Windows PowerShell プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="156cf-178">Creating Windows PowerShell Providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="156cf-179">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="156cf-179">Design Your Windows PowerShell Provider</span></span>](./designing-your-windows-powershell-provider.md)

[<span data-ttu-id="156cf-180">基本的な Windows PowerShell プロバイダーを作成する</span><span class="sxs-lookup"><span data-stu-id="156cf-180">Creating a Basic Windows PowerShell Provider</span></span>](./creating-a-basic-windows-powershell-provider.md)
