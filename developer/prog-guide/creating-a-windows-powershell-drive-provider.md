---
title: Windows PowerShell ドライブ プロバイダーの作成 |Microsoft Docs
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
ms.openlocfilehash: 174d3a6860790295e1b73f32d9c1bad46b653917
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055651"
---
# <a name="creating-a-windows-powershell-drive-provider"></a><span data-ttu-id="18f9d-102">Windows PowerShell ドライブ プロバイダーを作成する</span><span class="sxs-lookup"><span data-stu-id="18f9d-102">Creating a Windows PowerShell Drive Provider</span></span>

<span data-ttu-id="18f9d-103">このトピックでは、Windows PowerShell ドライブをデータ ストアにアクセスする手段を提供する Windows PowerShell ドライブ プロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-103">This topic describes how to create a Windows PowerShell drive provider that provides a way to access a data store through a Windows PowerShell drive.</span></span> <span data-ttu-id="18f9d-104">この種類のプロバイダーは、"Windows PowerShell ドライブ プロバイダー"とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="18f9d-104">This type of provider is also referred to as Windows PowerShell drive providers.</span></span> <span data-ttu-id="18f9d-105">プロバイダーによって使用される Windows PowerShell ドライブでは、データ ストアに接続するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-105">The Windows PowerShell drives used by the provider provide the means to connect to the data store.</span></span>

<span data-ttu-id="18f9d-106">ここで説明されている Windows PowerShell ドライブ プロバイダーでは、Microsoft Access データベースへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-106">The Windows PowerShell drive provider described here provides access to a Microsoft Access database.</span></span> <span data-ttu-id="18f9d-107">このプロバイダーでは、Windows PowerShell ドライブを表します (ドライブ プロバイダーにドライブの任意の数を追加することは)、データベース ドライブの最上位のコンテナーは、データベース内のテーブルを表し、コンテナーの項目が内の行を表しますテーブル。</span><span class="sxs-lookup"><span data-stu-id="18f9d-107">For this provider, the Windows PowerShell drive represents the database (it is possible to add any number of drives to a drive provider), the top-level containers of the drive represent the tables in the database, and the items of the containers represent the rows in the tables.</span></span>

<span data-ttu-id="18f9d-108">このトピックのセクションの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-108">Here is a list of the sections in this topic.</span></span> <span data-ttu-id="18f9d-109">Windows PowerShell ドライブ プロバイダーの記述に慣れていない場合に、出現する順序でこれらのセクションが読み取られます。</span><span class="sxs-lookup"><span data-stu-id="18f9d-109">If you are unfamiliar with writing a Windows PowerShell drive provider, read these sections in the order that they appear.</span></span> <span data-ttu-id="18f9d-110">ただし、ドライブ プロバイダーの作成に習熟する場合は、直接」に進んでください必要な情報。</span><span class="sxs-lookup"><span data-stu-id="18f9d-110">However, if you are familiar with writing a drive provider, please go directly to the information that you need.</span></span>

- [<span data-ttu-id="18f9d-111">Windows PowerShell プロバイダー クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-111">Defining the Windows PowerShell Provider Class</span></span>](#Defining-the-Windows-PowerShell-Provider-Class)

- [<span data-ttu-id="18f9d-112">基本機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-112">Defining Base Functionality</span></span>](#Defining-Base-Functionality)

- [<span data-ttu-id="18f9d-113">ドライブの状態情報の作成</span><span class="sxs-lookup"><span data-stu-id="18f9d-113">Creating Drive State Information</span></span>](#Creating-Drive-State-Information)

- [<span data-ttu-id="18f9d-114">ドライブの作成</span><span class="sxs-lookup"><span data-stu-id="18f9d-114">Creating a Drive</span></span>](#Creating-a-Drive)

- [<span data-ttu-id="18f9d-115">NewDrive に動的パラメーターを追加</span><span class="sxs-lookup"><span data-stu-id="18f9d-115">Attaching Dynamic Parameters to NewDrive</span></span>](#Attaching-Dynamic-Parameters-to-NewDrive)

- [<span data-ttu-id="18f9d-116">ドライブを削除します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-116">Removing a Drive</span></span>](#Removing-a-Drive)

- [<span data-ttu-id="18f9d-117">ドライブの既定の初期化</span><span class="sxs-lookup"><span data-stu-id="18f9d-117">Initializing Default Drives</span></span>](#Initializing-Default-Drives)

- [<span data-ttu-id="18f9d-118">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="18f9d-118">Code Sample</span></span>](#Code-Sample)

- [<span data-ttu-id="18f9d-119">Windows PowerShell ドライブ プロバイダーのテスト</span><span class="sxs-lookup"><span data-stu-id="18f9d-119">Testing the Windows PowerShell Drive Provider</span></span>](#Testing-the-Windows-PowerShell-Drive-Provider)

## <a name="defining-the-windows-powershell-provider-class"></a><span data-ttu-id="18f9d-120">Windows PowerShell プロバイダー クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-120">Defining the Windows PowerShell Provider Class</span></span>

<span data-ttu-id="18f9d-121">ドライブは、プロバイダーから派生する .NET クラスを定義する必要があります、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)基本クラス。</span><span class="sxs-lookup"><span data-stu-id="18f9d-121">Your drive provider must define a .NET class that derives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) base class.</span></span> <span data-ttu-id="18f9d-122">このドライブ プロバイダーのクラス定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-122">Here is the class definition for this drive provider:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L29-L30 "AccessDBProviderSample02.cs")]

<span data-ttu-id="18f9d-123">この例では、注意、 [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)属性は、プロバイダーと Windows PowerShell の特定の機能のわかりやすい名前を指定するプロバイダーコマンドの処理中に、Windows PowerShell ランタイムに公開されます。</span><span class="sxs-lookup"><span data-stu-id="18f9d-123">Notice that in this example, the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute specifies a user-friendly name for the provider and the Windows PowerShell specific capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span> <span data-ttu-id="18f9d-124">によって、プロバイダーの機能の有効な値が定義されている、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。</span><span class="sxs-lookup"><span data-stu-id="18f9d-124">The possible values for the provider capabilities are defined by the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="18f9d-125">このドライブ プロバイダーは、これらの機能のいずれかのことをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="18f9d-125">This drive provider does not support any of these capabilities.</span></span>

## <a name="defining-base-functionality"></a><span data-ttu-id="18f9d-126">基本機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-126">Defining Base Functionality</span></span>

<span data-ttu-id="18f9d-127">」の説明に従って[デザイン、Windows PowerShell プロバイダー](./designing-your-windows-powershell-provider.md)、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスから派生、 [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)基本クラスを初期化し、プロバイダーの初期化解除に必要なメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-127">As described in [Design Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md), the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class derives from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) base class that defines the methods needed for initializing and uninitializing the provider.</span></span> <span data-ttu-id="18f9d-128">セッション固有の初期化情報を追加して、プロバイダーによって使用されているリソースを解放するための機能を実装するを参照してください。[基本的な Windows PowerShell プロバイダーを作成する](./creating-a-basic-windows-powershell-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-128">To implement functionality for adding session-specific initialization information and for releasing resources that are used by the provider, see [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span> <span data-ttu-id="18f9d-129">ただし、ほとんどのプロバイダー (ここで説明されているプロバイダーを含む) は、この Windows PowerShell によって提供される機能の既定の実装を使用できます。</span><span class="sxs-lookup"><span data-stu-id="18f9d-129">However, most providers (including the provider described here) can use the default implementation of this functionality that is provided by Windows PowerShell.</span></span>

## <a name="creating-drive-state-information"></a><span data-ttu-id="18f9d-130">ドライブの状態情報の作成</span><span class="sxs-lookup"><span data-stu-id="18f9d-130">Creating Drive State Information</span></span>

<span data-ttu-id="18f9d-131">すべての Windows PowerShell プロバイダーは、ドライブは、プロバイダーが、プロバイダーを呼び出すときに、Windows PowerShell ランタイムで必要なすべての状態情報を作成する必要があることを意味する、ステートレスで考慮されます。</span><span class="sxs-lookup"><span data-stu-id="18f9d-131">All Windows PowerShell providers are considered stateless, which means that your drive provider needs to create any state information that is needed by the Windows PowerShell runtime when it calls your provider.</span></span>

<span data-ttu-id="18f9d-132">このドライブ プロバイダーの状態情報には、ドライブ情報の一部として保持されているデータベースへの接続が含まれています。</span><span class="sxs-lookup"><span data-stu-id="18f9d-132">For this drive provider, state information includes the connection to the database that is kept as part of the drive information.</span></span> <span data-ttu-id="18f9d-133">この情報を格納する方法を示すコードをここでは、 [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo)ドライブを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="18f9d-133">Here is code that shows how this information is stored in the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object that describes the drive:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L130-L151 "AccessDBProviderSample02.cs")]

## <a name="creating-a-drive"></a><span data-ttu-id="18f9d-134">ドライブの作成</span><span class="sxs-lookup"><span data-stu-id="18f9d-134">Creating a Drive</span></span>

<span data-ttu-id="18f9d-135">ドライブを作成するには、Windows PowerShell ランタイムを許可するドライブのプロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッド。</span><span class="sxs-lookup"><span data-stu-id="18f9d-135">To allow the Windows PowerShell runtime to create a drive, the drive provider must implement the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method.</span></span> <span data-ttu-id="18f9d-136">次のコードの実装を示しています、 [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)このドライブ プロバイダーのメソッド。</span><span class="sxs-lookup"><span data-stu-id="18f9d-136">The following code shows the implementation of the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method for this drive provider:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L42-L84 "AccessDBProviderSample02.cs")]

<span data-ttu-id="18f9d-137">このメソッドのオーバーライドは、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="18f9d-137">Your override of this method should do the following:</span></span>

- <span data-ttu-id="18f9d-138">いることを確認、 [System.Management.Automation.PSDriveinfo.Root\*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root)メンバーが存在して、データ ストアへの接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="18f9d-138">Verify that the [System.Management.Automation.PSDriveinfo.Root\*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) member exists and that a connection to the data store can be made.</span></span>

- <span data-ttu-id="18f9d-139">ドライブを作成しのサポートに、接続メンバーを設定、`New-PSDrive`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="18f9d-139">Create a drive and populate the connection member, in support of the `New-PSDrive` cmdlet.</span></span>

- <span data-ttu-id="18f9d-140">検証、 [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo)提案されたドライブのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="18f9d-140">Validate the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object for the proposed drive.</span></span>

- <span data-ttu-id="18f9d-141">変更、 [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo)任意の必要なパフォーマンスと信頼性については、ドライブを記述するオブジェクトまたはドライブを使用して呼び出し元の余分なデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-141">Modify the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object that describes the drive with any required performance or reliability information, or provide extra data for callers using the drive.</span></span>

- <span data-ttu-id="18f9d-142">使用してエラーを処理、 [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError)メソッドと戻り値`null`します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-142">Handle failures using the [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) method and then return `null`.</span></span>

  <span data-ttu-id="18f9d-143">このメソッドは、そのプロバイダーに固有のバージョンのメソッドに渡されたいずれかのドライブ情報を返します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-143">This method returns either the drive information that was passed to the method or a provider-specific version of it.</span></span>

## <a name="attaching-dynamic-parameters-to-newdrive"></a><span data-ttu-id="18f9d-144">NewDrive に動的パラメーターを追加</span><span class="sxs-lookup"><span data-stu-id="18f9d-144">Attaching Dynamic Parameters to NewDrive</span></span>

<span data-ttu-id="18f9d-145">`New-PSDrive`ドライブは、プロバイダーでサポートされているコマンドレットは、追加のパラメーターを必要があります。</span><span class="sxs-lookup"><span data-stu-id="18f9d-145">The `New-PSDrive` cmdlet supported by your drive provider might require additional parameters.</span></span> <span data-ttu-id="18f9d-146">これらの動的パラメーターをコマンドレットに添付するプロバイダーを実装、 [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters)メソッド。</span><span class="sxs-lookup"><span data-stu-id="18f9d-146">To attach these dynamic parameters to the cmdlet, the provider implements the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) method.</span></span> <span data-ttu-id="18f9d-147">このメソッドは、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="18f9d-147">This method returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span>

<span data-ttu-id="18f9d-148">このドライブ プロバイダーは、このメソッドをオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="18f9d-148">This drive provider does not override this method.</span></span> <span data-ttu-id="18f9d-149">ただし、次のコードは、このメソッドの既定の実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="18f9d-149">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters](Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters)]  -->

## <a name="removing-a-drive"></a><span data-ttu-id="18f9d-150">ドライブを削除します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-150">Removing a Drive</span></span>

<span data-ttu-id="18f9d-151">データベース接続を閉じるには、ドライブのプロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッド。</span><span class="sxs-lookup"><span data-stu-id="18f9d-151">To close the database connection, the drive provider must implement the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method.</span></span> <span data-ttu-id="18f9d-152">このメソッドは、任意のプロバイダーに固有の情報をクリーンアップした後は、ドライブへの接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="18f9d-152">This method closes the connection to the drive after cleaning up any provider-specific information.</span></span>

<span data-ttu-id="18f9d-153">次のコードの実装を示しています、 [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)このドライブ プロバイダーのメソッド。</span><span class="sxs-lookup"><span data-stu-id="18f9d-153">The following code shows the implementation of the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method for this drive provider:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L91-L116 "AccessDBProviderSample02.cs")]

<span data-ttu-id="18f9d-154">メソッドをメソッドに渡される情報を返す必要があります、ドライブが削除できる場合、`drive`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="18f9d-154">If the drive can be removed, the method should return the information passed to the method through the `drive` parameter.</span></span> <span data-ttu-id="18f9d-155">メソッドが例外を記述する必要があります、戻りますドライブを削除できない場合は`null`します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-155">If the drive cannot be removed, the method should write an exception and then return `null`.</span></span> <span data-ttu-id="18f9d-156">プロバイダーがこのメソッドをオーバーライドしない場合、このメソッドの既定の実装はだけ入力として渡さドライブ情報を返します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-156">If your provider does not override this method, the default implementation of this method just returns the drive information passed as input.</span></span>

## <a name="initializing-default-drives"></a><span data-ttu-id="18f9d-157">ドライブの既定の初期化</span><span class="sxs-lookup"><span data-stu-id="18f9d-157">Initializing Default Drives</span></span>

<span data-ttu-id="18f9d-158">ドライブ プロバイダーの実装して、 [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives)ドライブをマウントするメソッド。</span><span class="sxs-lookup"><span data-stu-id="18f9d-158">Your drive provider implements the [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) method to mount drives.</span></span> <span data-ttu-id="18f9d-159">たとえば、Active Directory プロバイダーは、名前付けコンテキストをコンピューターがドメインに参加している場合、既定のドライブをマウントする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18f9d-159">For example, the Active Directory provider might mount a drive for the default naming context if the computer is joined to a domain.</span></span>

<span data-ttu-id="18f9d-160">このメソッドは、初期化済みのドライブのドライブについてのコレクションまたは空のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-160">This method returns a collection of drive information about the initialized drives, or an empty collection.</span></span> <span data-ttu-id="18f9d-161">Windows PowerShell ランタイムの呼び出し後にこのメソッドの呼び出しが行われた、 [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start)プロバイダーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-161">The call to this method is made after the Windows PowerShell runtime calls the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method to initialize the provider.</span></span>

<span data-ttu-id="18f9d-162">このドライブ プロバイダーをオーバーライドしない、 [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives)メソッド。</span><span class="sxs-lookup"><span data-stu-id="18f9d-162">This drive provider does not override the [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) method.</span></span> <span data-ttu-id="18f9d-163">ただし、次のコードは、空のドライブのコレクションを返します既定の実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="18f9d-163">However, the following code shows the default implementation, which returns an empty drive collection:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinitializedefaultdrives](Msh_samplestestcmdlets#testproviderinitializedefaultdrives)]  -->

#### <a name="things-to-remember-about-implementing-initializedefaultdrives"></a><span data-ttu-id="18f9d-164">InitializeDefaultDrives の実装に関する注意点</span><span class="sxs-lookup"><span data-stu-id="18f9d-164">Things to Remember About Implementing InitializeDefaultDrives</span></span>

<span data-ttu-id="18f9d-165">すべてのドライブ プロバイダーは、見つけやすさと、ユーザーを支援するルート ドライブをマウントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="18f9d-165">All drive providers should mount a root drive to help the user with discoverability.</span></span> <span data-ttu-id="18f9d-166">ルート ドライブでは、その他のマウントされたドライブのルートとして機能する場所を一覧表示可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18f9d-166">The root drive might list locations that serve as roots for other mounted drives.</span></span> <span data-ttu-id="18f9d-167">たとえば、Active Directory プロバイダーを作成、ドライブにある名前付けコンテキストを一覧表示する、`namingContext`ルート分散システム環境 (DSE) の属性。</span><span class="sxs-lookup"><span data-stu-id="18f9d-167">For example, the Active Directory provider might create a drive that lists the naming contexts found in the `namingContext` attributes on the root Distributed System Environment (DSE).</span></span> <span data-ttu-id="18f9d-168">これにより、ユーザーが他のドライブのマウント ポイントを検出できます。</span><span class="sxs-lookup"><span data-stu-id="18f9d-168">This helps users discover mount points for other drives.</span></span>

## <a name="code-sample"></a><span data-ttu-id="18f9d-169">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="18f9d-169">Code Sample</span></span>

<span data-ttu-id="18f9d-170">完全なサンプル コードでは、[AccessDbProviderSample02 コード サンプル](./accessdbprovidersample02-code-sample.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18f9d-170">For complete sample code, see [AccessDbProviderSample02 Code Sample](./accessdbprovidersample02-code-sample.md).</span></span>

## <a name="testing-the-windows-powershell-drive-provider"></a><span data-ttu-id="18f9d-171">Windows PowerShell ドライブ プロバイダーのテスト</span><span class="sxs-lookup"><span data-stu-id="18f9d-171">Testing the Windows PowerShell Drive Provider</span></span>

<span data-ttu-id="18f9d-172">Windows PowerShell を使用した、Windows PowerShell プロバイダーを登録しているときに、派生で利用できる任意のコマンドレットなど、コマンドラインでサポートされているコマンドレットを実行してテストできます。</span><span class="sxs-lookup"><span data-stu-id="18f9d-172">When your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line, including any cmdlets made available by derivation.</span></span> <span data-ttu-id="18f9d-173">サンプルのドライブのプロバイダーをテストしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="18f9d-173">Let's test the sample drive provider.</span></span>

1. <span data-ttu-id="18f9d-174">実行、 `Get-PSProvider` AccessDB ドライブ プロバイダーが存在することを確認するプロバイダーの一覧を取得するコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="18f9d-174">Run the `Get-PSProvider` cmdlet to retrieve the list of providers to ensure that the AccessDB drive provider is present:</span></span>

   <span data-ttu-id="18f9d-175">**PS> `Get-PSProvider`**</span><span class="sxs-lookup"><span data-stu-id="18f9d-175">**PS> `Get-PSProvider`**</span></span>

   <span data-ttu-id="18f9d-176">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="18f9d-176">The following output appears:</span></span>

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

2. <span data-ttu-id="18f9d-177">アクセスして、データベースのデータベース サーバー名 (DSN) が存在することを**データソース**の部分、**管理ツール**オペレーティング システム。</span><span class="sxs-lookup"><span data-stu-id="18f9d-177">Ensure that a database server name (DSN) exists for the database by accessing the **Data Sources** portion of the **Administrative Tools** for the operating system.</span></span> <span data-ttu-id="18f9d-178">**ユーザー DSN**テーブルをダブルクリックします**MS Access データベース**C:\ps\northwind.mdb ドライブ パスを追加します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-178">In the **User DSN** table, double-click **MS Access Database** and add the drive path C:\ps\northwind.mdb.</span></span>

3. <span data-ttu-id="18f9d-179">サンプルのドライブのプロバイダーを使用して新しいドライブを作成します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-179">Create a new drive using the sample drive provider:</span></span>

   <span data-ttu-id="18f9d-180">**PS> new-psdrive -name mydb -root c:\ps\northwind.mdb -psprovider AccessDb**</span><span class="sxs-lookup"><span data-stu-id="18f9d-180">**PS> new-psdrive -name mydb -root c:\ps\northwind.mdb -psprovider AccessDb**</span></span>

   <span data-ttu-id="18f9d-181">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="18f9d-181">The following output appears:</span></span>

   ```output
   Name     Provider     Root                   CurrentLocation
   ----     --------     ----                   ---------------
   mydb     AccessDB     c:\ps\northwind.mdb
   ```

4. <span data-ttu-id="18f9d-182">接続を検証します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-182">Validate the connection.</span></span> <span data-ttu-id="18f9d-183">接続は、ドライブのメンバーとして定義されている、ために、Get PDDrive コマンドレットを使用してチェックできます。</span><span class="sxs-lookup"><span data-stu-id="18f9d-183">Because the connection is defined as a member of the drive, you can check it using the Get-PDDrive cmdlet.</span></span>

   > [!NOTE]
   > <span data-ttu-id="18f9d-184">プロバイダーは、その操作のコンテナーの機能をニーズに応じて、ユーザーはドライブとしてプロバイダーとやり取りまだことはできません。</span><span class="sxs-lookup"><span data-stu-id="18f9d-184">The user cannot yet interact with the provider as a drive, as the provider needs container functionality for that interaction.</span></span> <span data-ttu-id="18f9d-185">詳細については、[Windows PowerShell コンテナー プロバイダーを作成する](./creating-a-windows-powershell-container-provider.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18f9d-185">For more information, see [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>

   <span data-ttu-id="18f9d-186">**PS > (である get-psdrive mydb) .connection**</span><span class="sxs-lookup"><span data-stu-id="18f9d-186">**PS> (get-psdrive mydb).connection**</span></span>

   <span data-ttu-id="18f9d-187">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="18f9d-187">The following output appears:</span></span>

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

5. <span data-ttu-id="18f9d-188">ドライブを削除し、シェルを終了します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-188">Remove the drive and exit the shell:</span></span>

   <span data-ttu-id="18f9d-189">**PS > - remove-psdrive mydb**</span><span class="sxs-lookup"><span data-stu-id="18f9d-189">**PS> remove-psdrive mydb**</span></span>

   <span data-ttu-id="18f9d-190">**PS > 終了**</span><span class="sxs-lookup"><span data-stu-id="18f9d-190">**PS> exit**</span></span>

## <a name="see-also"></a><span data-ttu-id="18f9d-191">参照</span><span class="sxs-lookup"><span data-stu-id="18f9d-191">See Also</span></span>

[<span data-ttu-id="18f9d-192">Windows PowerShell プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-192">Creating Windows PowerShell Providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="18f9d-193">Windows PowerShell プロバイダーを設計します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-193">Design Your Windows PowerShell Provider</span></span>](./designing-your-windows-powershell-provider.md)

[<span data-ttu-id="18f9d-194">基本的な Windows PowerShell プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="18f9d-194">Creating a Basic Windows PowerShell Provider</span></span>](./creating-a-basic-windows-powershell-provider.md)