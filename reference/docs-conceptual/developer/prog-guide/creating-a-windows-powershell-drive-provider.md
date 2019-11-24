---
title: Windows PowerShell ドライブプロバイダーを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- drive providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], drive provider
- drives [PowerShell Programmer's Guide]
ms.assetid: 2b446841-6616-4720-9ff8-50801d7576ed
caps.latest.revision: 6
ms.openlocfilehash: 2e3d97e224b06bdf36ac0bc1237911e029ea762d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366831"
---
# <a name="creating-a-windows-powershell-drive-provider"></a><span data-ttu-id="daa82-102">Windows PowerShell ドライブ プロバイダーを作成する</span><span class="sxs-lookup"><span data-stu-id="daa82-102">Creating a Windows PowerShell Drive Provider</span></span>

<span data-ttu-id="daa82-103">このトピックでは、windows PowerShell ドライブを介してデータストアにアクセスする方法を提供する Windows PowerShell ドライブプロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="daa82-103">This topic describes how to create a Windows PowerShell drive provider that provides a way to access a data store through a Windows PowerShell drive.</span></span> <span data-ttu-id="daa82-104">この種類のプロバイダーは、Windows PowerShell ドライブプロバイダーとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="daa82-104">This type of provider is also referred to as Windows PowerShell drive providers.</span></span> <span data-ttu-id="daa82-105">プロバイダーによって使用される Windows PowerShell ドライブは、データストアに接続する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="daa82-105">The Windows PowerShell drives used by the provider provide the means to connect to the data store.</span></span>

<span data-ttu-id="daa82-106">ここに記載されている Windows PowerShell ドライブプロバイダーは、Microsoft Access データベースへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="daa82-106">The Windows PowerShell drive provider described here provides access to a Microsoft Access database.</span></span> <span data-ttu-id="daa82-107">このプロバイダーの場合、Windows PowerShell ドライブはデータベースを表し (ドライブプロバイダーに任意の数のドライブを追加することができます)、ドライブの最上位のコンテナーはデータベースのテーブルを表し、コンテナーの項目は次の行を表します。テーブル。</span><span class="sxs-lookup"><span data-stu-id="daa82-107">For this provider, the Windows PowerShell drive represents the database (it is possible to add any number of drives to a drive provider), the top-level containers of the drive represent the tables in the database, and the items of the containers represent the rows in the tables.</span></span>

## <a name="defining-the-windows-powershell-provider-class"></a><span data-ttu-id="daa82-108">Windows PowerShell プロバイダークラスの定義</span><span class="sxs-lookup"><span data-stu-id="daa82-108">Defining the Windows PowerShell Provider Class</span></span>

<span data-ttu-id="daa82-109">Drive プロバイダーは、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)基底クラスから派生する .net クラスを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="daa82-109">Your drive provider must define a .NET class that derives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) base class.</span></span> <span data-ttu-id="daa82-110">このドライブプロバイダーのクラス定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="daa82-110">Here is the class definition for this drive provider:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L29-L30 "AccessDBProviderSample02.cs")]

<span data-ttu-id="daa82-111">この例[では、](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)この例では、コマンドの処理中にプロバイダーが windows powershell ランタイムに公開する、プロバイダーのユーザーフレンドリ名と、windows powershell 固有の機能を指定しています。</span><span class="sxs-lookup"><span data-stu-id="daa82-111">Notice that in this example, the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute specifies a user-friendly name for the provider and the Windows PowerShell specific capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span> <span data-ttu-id="daa82-112">プロバイダー機能に使用できる値は、system.servicemodel[機能](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙型によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="daa82-112">The possible values for the provider capabilities are defined by the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="daa82-113">このドライブプロバイダーは、これらの機能のいずれもサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="daa82-113">This drive provider does not support any of these capabilities.</span></span>

## <a name="defining-base-functionality"></a><span data-ttu-id="daa82-114">基本機能の定義</span><span class="sxs-lookup"><span data-stu-id="daa82-114">Defining Base Functionality</span></span>

<span data-ttu-id="daa82-115">「 [Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」で説明されているように、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスは、プロバイダーの初期化と初期化解除に必要なメソッドを定義する、system.servicemodel[プロバイダー](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)の基底クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="daa82-115">As described in [Design Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md), the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class derives from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) base class that defines the methods needed for initializing and uninitializing the provider.</span></span> <span data-ttu-id="daa82-116">セッション固有の初期化情報を追加し、プロバイダーによって使用されるリソースを解放するための機能を実装するには、「[基本的な Windows PowerShell プロバイダーの作成](./creating-a-basic-windows-powershell-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="daa82-116">To implement functionality for adding session-specific initialization information and for releasing resources that are used by the provider, see [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span> <span data-ttu-id="daa82-117">ただし、ほとんどのプロバイダー (ここで説明するプロバイダーを含む) は、Windows PowerShell によって提供されるこの機能の既定の実装を使用できます。</span><span class="sxs-lookup"><span data-stu-id="daa82-117">However, most providers (including the provider described here) can use the default implementation of this functionality that is provided by Windows PowerShell.</span></span>

## <a name="creating-drive-state-information"></a><span data-ttu-id="daa82-118">ドライブの状態情報の作成</span><span class="sxs-lookup"><span data-stu-id="daa82-118">Creating Drive State Information</span></span>

<span data-ttu-id="daa82-119">すべての Windows PowerShell プロバイダーはステートレスであると見なされます。つまり、ドライブプロバイダーは、プロバイダーを呼び出すときに、Windows PowerShell ランタイムが必要とする状態情報を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="daa82-119">All Windows PowerShell providers are considered stateless, which means that your drive provider needs to create any state information that is needed by the Windows PowerShell runtime when it calls your provider.</span></span>

<span data-ttu-id="daa82-120">このドライブプロバイダーの場合、状態情報には、ドライブ情報の一部として保持されているデータベースへの接続が含まれます。</span><span class="sxs-lookup"><span data-stu-id="daa82-120">For this drive provider, state information includes the connection to the database that is kept as part of the drive information.</span></span> <span data-ttu-id="daa82-121">次に示すコードは、この情報がドライブを説明する[system.management.automation.psdriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo)オブジェクトにどのように格納されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="daa82-121">Here is code that shows how this information is stored in the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object that describes the drive:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L130-L151 "AccessDBProviderSample02.cs")]

## <a name="creating-a-drive"></a><span data-ttu-id="daa82-122">ドライブの作成</span><span class="sxs-lookup"><span data-stu-id="daa82-122">Creating a Drive</span></span>

<span data-ttu-id="daa82-123">Windows PowerShell ランタイムがドライブを作成できるようにするには、ドライブプロバイダーが[Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="daa82-123">To allow the Windows PowerShell runtime to create a drive, the drive provider must implement the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method.</span></span> <span data-ttu-id="daa82-124">次のコードは、このドライブプロバイダーの[Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッドを実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="daa82-124">The following code shows the implementation of the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method for this drive provider:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L42-L84 "AccessDBProviderSample02.cs")]

<span data-ttu-id="daa82-125">このメソッドをオーバーライドするには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="daa82-125">Your override of this method should do the following:</span></span>

- <span data-ttu-id="daa82-126">[System.management.automation.psdriveinfo \*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root)メンバーが存在し、データストアへの接続が可能であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daa82-126">Verify that the [System.Management.Automation.PSDriveinfo.Root\*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) member exists and that a connection to the data store can be made.</span></span>

- <span data-ttu-id="daa82-127">`New-PSDrive` コマンドレットをサポートして、ドライブを作成し、接続メンバーを設定します。</span><span class="sxs-lookup"><span data-stu-id="daa82-127">Create a drive and populate the connection member, in support of the `New-PSDrive` cmdlet.</span></span>

- <span data-ttu-id="daa82-128">提案されたドライブの[system.management.automation.psdriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo)オブジェクトを検証します。</span><span class="sxs-lookup"><span data-stu-id="daa82-128">Validate the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object for the proposed drive.</span></span>

- <span data-ttu-id="daa82-129">ドライブを説明する[system.management.automation.psdriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo)オブジェクトを、必要なパフォーマンスまたは信頼性の情報で変更するか、ドライブを使用して呼び出し元に追加のデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="daa82-129">Modify the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object that describes the drive with any required performance or reliability information, or provide extra data for callers using the drive.</span></span>

- <span data-ttu-id="daa82-130">[WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError)メソッドを使用してエラーを処理した後、`null`を返します。</span><span class="sxs-lookup"><span data-stu-id="daa82-130">Handle failures using the [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) method and then return `null`.</span></span>

  <span data-ttu-id="daa82-131">このメソッドは、メソッドに渡されたドライブ情報またはプロバイダー固有のバージョンのいずれかを返します。</span><span class="sxs-lookup"><span data-stu-id="daa82-131">This method returns either the drive information that was passed to the method or a provider-specific version of it.</span></span>

## <a name="attaching-dynamic-parameters-to-newdrive"></a><span data-ttu-id="daa82-132">動的パラメーターを NewDrive にアタッチしています</span><span class="sxs-lookup"><span data-stu-id="daa82-132">Attaching Dynamic Parameters to NewDrive</span></span>

<span data-ttu-id="daa82-133">ドライブプロバイダーでサポートされている `New-PSDrive` コマンドレットでは、追加のパラメーターが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="daa82-133">The `New-PSDrive` cmdlet supported by your drive provider might require additional parameters.</span></span> <span data-ttu-id="daa82-134">これらの動的パラメーターをコマンドレットにアタッチするために、プロバイダーは[Drivecmdletprovider. Newdrivedynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters)メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="daa82-134">To attach these dynamic parameters to the cmdlet, the provider implements the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) method.</span></span> <span data-ttu-id="daa82-135">このメソッドは、コマンドレットクラスや[system.string オブジェクトと](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="daa82-135">This method returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span>

<span data-ttu-id="daa82-136">このドライブプロバイダーは、このメソッドをオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="daa82-136">This drive provider does not override this method.</span></span> <span data-ttu-id="daa82-137">ただし、次のコードは、このメソッドの既定の実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="daa82-137">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters](Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters)]  -->

## <a name="removing-a-drive"></a><span data-ttu-id="daa82-138">ドライブの取り外し</span><span class="sxs-lookup"><span data-stu-id="daa82-138">Removing a Drive</span></span>

<span data-ttu-id="daa82-139">データベース接続を閉じるには、ドライブプロバイダーが[Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを実装している必要があります。</span><span class="sxs-lookup"><span data-stu-id="daa82-139">To close the database connection, the drive provider must implement the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method.</span></span> <span data-ttu-id="daa82-140">このメソッドは、プロバイダー固有の情報をクリーンアップした後に、ドライブへの接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="daa82-140">This method closes the connection to the drive after cleaning up any provider-specific information.</span></span>

<span data-ttu-id="daa82-141">次のコードは、このドライブプロバイダーの[Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="daa82-141">The following code shows the implementation of the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method for this drive provider:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L91-L116 "AccessDBProviderSample02.cs")]

<span data-ttu-id="daa82-142">ドライブを削除できる場合、メソッドは `drive` パラメーターを使用してメソッドに渡された情報を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="daa82-142">If the drive can be removed, the method should return the information passed to the method through the `drive` parameter.</span></span> <span data-ttu-id="daa82-143">ドライブを削除できない場合、メソッドは例外を書き込み、`null`を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="daa82-143">If the drive cannot be removed, the method should write an exception and then return `null`.</span></span> <span data-ttu-id="daa82-144">プロバイダーがこのメソッドをオーバーライドしない場合、このメソッドの既定の実装は、入力として渡されたドライブ情報だけを返します。</span><span class="sxs-lookup"><span data-stu-id="daa82-144">If your provider does not override this method, the default implementation of this method just returns the drive information passed as input.</span></span>

## <a name="initializing-default-drives"></a><span data-ttu-id="daa82-145">既定のドライブの初期化</span><span class="sxs-lookup"><span data-stu-id="daa82-145">Initializing Default Drives</span></span>

<span data-ttu-id="daa82-146">ドライブプロバイダーは、 [Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives)メソッドを実装して、ドライブをマウントしますが、</span><span class="sxs-lookup"><span data-stu-id="daa82-146">Your drive provider implements the [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) method to mount drives.</span></span> <span data-ttu-id="daa82-147">たとえば、コンピューターがドメインに参加している場合、Active Directory プロバイダーが既定の名前付けコンテキストのドライブをマウントすることがあります。</span><span class="sxs-lookup"><span data-stu-id="daa82-147">For example, the Active Directory provider might mount a drive for the default naming context if the computer is joined to a domain.</span></span>

<span data-ttu-id="daa82-148">このメソッドは、初期化されたドライブまたは空のコレクションに関するドライブ情報のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="daa82-148">This method returns a collection of drive information about the initialized drives, or an empty collection.</span></span> <span data-ttu-id="daa82-149">このメソッドの呼び出しは、Windows PowerShell ランタイムによっ[て、プロバイダー](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start)を初期化するために、を呼び出した後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="daa82-149">The call to this method is made after the Windows PowerShell runtime calls the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method to initialize the provider.</span></span>

<span data-ttu-id="daa82-150">このドライブプロバイダーでは、 [Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives)メソッドがオーバーライドされていません。</span><span class="sxs-lookup"><span data-stu-id="daa82-150">This drive provider does not override the [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) method.</span></span> <span data-ttu-id="daa82-151">ただし、次のコードは、空のドライブコレクションを返す既定の実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="daa82-151">However, the following code shows the default implementation, which returns an empty drive collection:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinitializedefaultdrives](Msh_samplestestcmdlets#testproviderinitializedefaultdrives)]  -->

#### <a name="things-to-remember-about-implementing-initializedefaultdrives"></a><span data-ttu-id="daa82-152">InitializeDefaultDrives の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="daa82-152">Things to Remember About Implementing InitializeDefaultDrives</span></span>

<span data-ttu-id="daa82-153">すべてのドライブプロバイダーは、ユーザーが見つけやすいように、ルートドライブをマウントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="daa82-153">All drive providers should mount a root drive to help the user with discoverability.</span></span> <span data-ttu-id="daa82-154">ルートドライブには、他のマウントされたドライブのルートとして機能する場所が一覧表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="daa82-154">The root drive might list locations that serve as roots for other mounted drives.</span></span> <span data-ttu-id="daa82-155">たとえば、Active Directory プロバイダーは、ルート分散システム環境 (DSE) の `namingContext` 属性で見つかった名前付けコンテキストを一覧表示するドライブを作成する場合があります。</span><span class="sxs-lookup"><span data-stu-id="daa82-155">For example, the Active Directory provider might create a drive that lists the naming contexts found in the `namingContext` attributes on the root Distributed System Environment (DSE).</span></span> <span data-ttu-id="daa82-156">これは、ユーザーが他のドライブのマウントポイントを検出するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="daa82-156">This helps users discover mount points for other drives.</span></span>

## <a name="code-sample"></a><span data-ttu-id="daa82-157">コードサンプル</span><span class="sxs-lookup"><span data-stu-id="daa82-157">Code Sample</span></span>

<span data-ttu-id="daa82-158">完全なサンプルコードについては、「 [AccessDbProviderSample02 のコードサンプル](./accessdbprovidersample02-code-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="daa82-158">For complete sample code, see [AccessDbProviderSample02 Code Sample](./accessdbprovidersample02-code-sample.md).</span></span>

## <a name="testing-the-windows-powershell-drive-provider"></a><span data-ttu-id="daa82-159">Windows PowerShell ドライブプロバイダーのテスト</span><span class="sxs-lookup"><span data-stu-id="daa82-159">Testing the Windows PowerShell Drive Provider</span></span>

<span data-ttu-id="daa82-160">Windows PowerShell プロバイダーが Windows PowerShell に登録されている場合は、コマンドラインでサポートされているコマンドレットを実行してテストできます。これには、派生によって使用可能なコマンドレットも含まれます。</span><span class="sxs-lookup"><span data-stu-id="daa82-160">When your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line, including any cmdlets made available by derivation.</span></span> <span data-ttu-id="daa82-161">サンプルドライブプロバイダーをテストしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="daa82-161">Let's test the sample drive provider.</span></span>

1. <span data-ttu-id="daa82-162">`Get-PSProvider` コマンドレットを実行してプロバイダーの一覧を取得し、AccessDB ドライブプロバイダーが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="daa82-162">Run the `Get-PSProvider` cmdlet to retrieve the list of providers to ensure that the AccessDB drive provider is present:</span></span>

   <span data-ttu-id="daa82-163">**PS > `Get-PSProvider`**</span><span class="sxs-lookup"><span data-stu-id="daa82-163">**PS> `Get-PSProvider`**</span></span>

   <span data-ttu-id="daa82-164">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="daa82-164">The following output appears:</span></span>

   ```output
   Name                 Capabilities                  Drives
   ----                 ------------                  ------
   AccessDB             None                          {}
   Alias                ShouldProcess                 {Alias}
   Environment          ShouldProcess                 {Env}
   FileSystem           Filter, ShouldProcess         {C, Z}
   Function             ShouldProcess                 {function}
   Registry             ShouldProcess                 {HKLM, HKCU}
   ```

2. <span data-ttu-id="daa82-165">オペレーティングシステムの**管理ツール**の **[データソース]** 部分にアクセスして、データベースのデータベースサーバー名 (DSN) が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="daa82-165">Ensure that a database server name (DSN) exists for the database by accessing the **Data Sources** portion of the **Administrative Tools** for the operating system.</span></span> <span data-ttu-id="daa82-166">**[USER DSN]** テーブルで、 **[MS Access Database]** をダブルクリックし、ドライブパス C:\ps\northwind.mdb. を追加します。</span><span class="sxs-lookup"><span data-stu-id="daa82-166">In the **User DSN** table, double-click **MS Access Database** and add the drive path C:\ps\northwind.mdb.</span></span>

3. <span data-ttu-id="daa82-167">サンプルドライブプロバイダーを使用して新しいドライブを作成します。</span><span class="sxs-lookup"><span data-stu-id="daa82-167">Create a new drive using the sample drive provider:</span></span>

   <span data-ttu-id="daa82-168">**PS > psdrive-name mydb-root c:\ps\northwind.mdb-psprovider AccessDb**</span><span class="sxs-lookup"><span data-stu-id="daa82-168">**PS> new-psdrive -name mydb -root c:\ps\northwind.mdb -psprovider AccessDb**</span></span>

   <span data-ttu-id="daa82-169">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="daa82-169">The following output appears:</span></span>

   ```output
   Name     Provider     Root                   CurrentLocation
   ----     --------     ----                   ---------------
   mydb     AccessDB     c:\ps\northwind.mdb
   ```

4. <span data-ttu-id="daa82-170">接続を検証します。</span><span class="sxs-lookup"><span data-stu-id="daa82-170">Validate the connection.</span></span> <span data-ttu-id="daa82-171">接続はドライブのメンバーとして定義されているため、Get PDDrive コマンドレットを使用して確認できます。</span><span class="sxs-lookup"><span data-stu-id="daa82-171">Because the connection is defined as a member of the drive, you can check it using the Get-PDDrive cmdlet.</span></span>

   > [!NOTE]
   > <span data-ttu-id="daa82-172">ユーザーは、その対話にコンテナー機能を必要とするため、プロバイダーをドライブとして操作することはできません。</span><span class="sxs-lookup"><span data-stu-id="daa82-172">The user cannot yet interact with the provider as a drive, as the provider needs container functionality for that interaction.</span></span> <span data-ttu-id="daa82-173">詳細については、「 [Windows PowerShell コンテナープロバイダーの作成](./creating-a-windows-powershell-container-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="daa82-173">For more information, see [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>

   <span data-ttu-id="daa82-174">**PS > (psdrive mydb). 接続**</span><span class="sxs-lookup"><span data-stu-id="daa82-174">**PS> (get-psdrive mydb).connection**</span></span>

   <span data-ttu-id="daa82-175">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="daa82-175">The following output appears:</span></span>

   ```output
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

5. <span data-ttu-id="daa82-176">ドライブを取り外し、シェルを終了します。</span><span class="sxs-lookup"><span data-stu-id="daa82-176">Remove the drive and exit the shell:</span></span>

   <span data-ttu-id="daa82-177">**PS > psdrive mydb**</span><span class="sxs-lookup"><span data-stu-id="daa82-177">**PS> remove-psdrive mydb**</span></span>

   <span data-ttu-id="daa82-178">**PS > 終了**</span><span class="sxs-lookup"><span data-stu-id="daa82-178">**PS> exit**</span></span>

## <a name="see-also"></a><span data-ttu-id="daa82-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="daa82-179">See Also</span></span>

[<span data-ttu-id="daa82-180">Windows PowerShell プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="daa82-180">Creating Windows PowerShell Providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="daa82-181">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="daa82-181">Design Your Windows PowerShell Provider</span></span>](./designing-your-windows-powershell-provider.md)

[<span data-ttu-id="daa82-182">基本的な Windows PowerShell プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="daa82-182">Creating a Basic Windows PowerShell Provider</span></span>](./creating-a-basic-windows-powershell-provider.md)
