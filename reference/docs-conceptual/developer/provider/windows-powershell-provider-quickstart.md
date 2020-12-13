---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell プロバイダー クイック スタート
description: Windows PowerShell プロバイダー クイック スタート
ms.openlocfilehash: f0fe0ad60e9d10efd505cda60af995c597226b92
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664343"
---
# <a name="windows-powershell-provider-quickstart"></a><span data-ttu-id="775c4-103">Windows PowerShell プロバイダー クイック スタート</span><span class="sxs-lookup"><span data-stu-id="775c4-103">Windows PowerShell Provider Quickstart</span></span>

<span data-ttu-id="775c4-104">このトピックでは、新しいドライブを作成する基本的な機能を備えた Windows PowerShell プロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="775c4-104">This topic explains how to create a Windows PowerShell provider that has basic functionality of creating a new drive.</span></span> <span data-ttu-id="775c4-105">プロバイダーの一般的な情報については、「 [Windows PowerShell プロバイダーの概要](./windows-powershell-provider-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="775c4-105">For general information about providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span> <span data-ttu-id="775c4-106">より詳細な機能を持つプロバイダーの例については、 [プロバイダーのサンプル](./provider-samples.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="775c4-106">For examples of providers with more complete functionality, see [Provider Samples](./provider-samples.md).</span></span>

## <a name="writing-a-basic-provider"></a><span data-ttu-id="775c4-107">基本的なプロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="775c4-107">Writing a basic provider</span></span>

<span data-ttu-id="775c4-108">Windows PowerShell プロバイダーの最も基本的な機能は、ドライブを作成および削除することです。</span><span class="sxs-lookup"><span data-stu-id="775c4-108">The most basic functionality of a Windows PowerShell provider is to create and remove drives.</span></span> <span data-ttu-id="775c4-109">この例では、Drivecmdletprovider クラスの[Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) \* メソッドと[Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを実装しています。この例では、 [](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスが使用されています。この例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="775c4-109">In this example, we implement the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) and [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) methods of the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class.</span></span> <span data-ttu-id="775c4-110">また、プロバイダークラスを宣言する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="775c4-110">You will also see how to declare a provider class.</span></span>

<span data-ttu-id="775c4-111">プロバイダーを作成するときに、プロバイダーが利用可能になったときに自動的に作成される既定のドライブドライブを指定できます。</span><span class="sxs-lookup"><span data-stu-id="775c4-111">When you write a provider, you can specify default drives-drives that are created automatically when the provider is available.</span></span> <span data-ttu-id="775c4-112">また、そのプロバイダーを使用する新しいドライブを作成するためのメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="775c4-112">You also define a method to create new drives that use that provider.</span></span>

<span data-ttu-id="775c4-113">このトピックで示す例は、Access データベースを Windows PowerShell ドライブとして表す大規模なサンプルの一部である [AccessDBProviderSample02](./accessdbprovidersample02.md) サンプルに基づいています。</span><span class="sxs-lookup"><span data-stu-id="775c4-113">The examples provided in this topic are based on the [AccessDBProviderSample02](./accessdbprovidersample02.md) sample, which is part of a larger sample that represents an Access database as a Windows PowerShell drive.</span></span>

### <a name="setting-up-the-project"></a><span data-ttu-id="775c4-114">プロジェクトの設定</span><span class="sxs-lookup"><span data-stu-id="775c4-114">Setting up the project</span></span>

<span data-ttu-id="775c4-115">Visual Studio で、AccessDBProviderSample という名前のクラスライブラリプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="775c4-115">In Visual Studio, create a Class Library project named AccessDBProviderSample.</span></span> <span data-ttu-id="775c4-116">次の手順を実行して、Windows PowerShell が起動するようにプロジェクトを構成し、プロジェクトをビルドして起動すると、プロバイダーがセッションに読み込まれるようにします。</span><span class="sxs-lookup"><span data-stu-id="775c4-116">Complete the following steps to configure your project so that Windows PowerShell will start, and the provider will be loaded into the session, when you build and start your project.</span></span>

##### <a name="configure-the-provider-project"></a><span data-ttu-id="775c4-117">プロバイダープロジェクトの構成</span><span class="sxs-lookup"><span data-stu-id="775c4-117">Configure the provider project</span></span>

1. <span data-ttu-id="775c4-118">プロジェクトへの参照として、system.servicemodel アセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="775c4-118">Add the System.Management.Automation assembly as a reference to your project.</span></span>

2. <span data-ttu-id="775c4-119">[ **プロジェクト > AccessDBProviderSample のプロパティ > デバッグ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="775c4-119">Click **Project > AccessDBProviderSample Properties > Debug**.</span></span> <span data-ttu-id="775c4-120">[ **プロジェクトの開始**] で、[ **外部プログラムの開始**] をクリックし、Windows PowerShell 実行可能ファイル (通常は c:\Windows\System32\WindowsPowerShell\v1.0.powershell.exe) に移動し \\ ます。</span><span class="sxs-lookup"><span data-stu-id="775c4-120">In **Start project**, click **Start external program**, and navigate to the Windows PowerShell executable (typically c:\Windows\System32\WindowsPowerShell\v1.0\\.powershell.exe).</span></span>

3. <span data-ttu-id="775c4-121">[ **開始オプション**] で、[ **コマンドライン引数** ] ボックスに次のように入力します。 `-noexit -command "[reflection.assembly]::loadFrom(AccessDBProviderSample.dll' ) | import-module"`</span><span class="sxs-lookup"><span data-stu-id="775c4-121">Under **Start Options**, enter the following into the **Command line arguments** box: `-noexit -command "[reflection.assembly]::loadFrom(AccessDBProviderSample.dll' ) | import-module"`</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="775c4-122">プロバイダークラスの宣言</span><span class="sxs-lookup"><span data-stu-id="775c4-122">Declaring the provider class</span></span>

<span data-ttu-id="775c4-123">このプロバイダーは、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="775c4-123">Our provider derives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class.</span></span> <span data-ttu-id="775c4-124">実際の機能 (項目へのアクセスと操作、データストア内の移動、項目のコンテンツの取得と設定) を提供する [ほとんどのプロバイダーは、system.servicemodel](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="775c4-124">Most providers that provide real functionality (accessing and manipulating items, navigating the data store, and getting and setting content of items) derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

<span data-ttu-id="775c4-125">クラスが Drivecmdletprovider から派生することを指定するだけでなく、例に示すように、このクラスを[](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)プロバイダーの[属性](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)で修飾する必要がありますが、</span><span class="sxs-lookup"><span data-stu-id="775c4-125">In addition to specifying that the class derives from [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider), you must decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) as shown in the example.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Providers
{
  using System;
  using System.Data;
  using System.Data.Odbc;
  using System.IO;
  using System.Management.Automation;
  using System.Management.Automation.Provider;

  #region AccessDBProvider

  [CmdletProvider("AccessDB", ProviderCapabilities.None)]
  public class AccessDBProvider : DriveCmdletProvider
  {

}
}
```

### <a name="implementing-newdrive"></a><span data-ttu-id="775c4-126">NewDrive の実装</span><span class="sxs-lookup"><span data-stu-id="775c4-126">Implementing NewDrive</span></span>

<span data-ttu-id="775c4-127">[Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッドは、ユーザーがプロバイダーの名前を指定して[NewPSDriveCommand](/dotnet/api/Microsoft.PowerShell.Commands.Newpsdrivecommand)コマンドレットを呼び出したときに、Windows PowerShell エンジンによって呼び出されたときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="775c4-127">The [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method is called by the Windows PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.NewPSDriveCommand](/dotnet/api/Microsoft.PowerShell.Commands.Newpsdrivecommand) cmdlet specifying the name of your provider.</span></span> <span data-ttu-id="775c4-128">System.management.automation.psdriveinfo パラメーターは Windows PowerShell エンジンによって渡され、メソッドは新しいドライブを Windows PowerShell エンジンに返します。</span><span class="sxs-lookup"><span data-stu-id="775c4-128">The PSDriveInfo parameter is passed by the Windows PowerShell engine, and the method returns the new drive to the Windows PowerShell engine.</span></span> <span data-ttu-id="775c4-129">このメソッドは、上記で作成したクラス内で宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="775c4-129">This method must be declared within the class created above.</span></span>

<span data-ttu-id="775c4-130">メソッドは、最初に、渡されたドライブオブジェクトとドライブルートの両方が存在することを確認し、 `null` いずれかの場合はを返します。</span><span class="sxs-lookup"><span data-stu-id="775c4-130">The method first checks to make sure both the drive object and the drive root that were passed in exist, returning `null` if either of them do not.</span></span> <span data-ttu-id="775c4-131">次に、内部クラス AccessDBPSDriveInfo のコンストラクターを使用して、新しいドライブと、ドライブが表す Access データベースへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="775c4-131">It then uses a constructor of the internal class AccessDBPSDriveInfo to create a new drive and a connection to the Access database the drive represents.</span></span>

```csharp
protected override PSDriveInfo NewDrive(PSDriveInfo drive)
    {
      // Check if the drive object is null.
      if (drive == null)
      {
        WriteError(new ErrorRecord(
                   new ArgumentNullException("drive"),
                   "NullDrive",
                   ErrorCategory.InvalidArgument,
                   null));

        return null;
      }

      // Check if the drive root is not null or empty
      // and if it is an existing file.
      if (String.IsNullOrEmpty(drive.Root) || (File.Exists(drive.Root) == false))
      {
        WriteError(new ErrorRecord(
                   new ArgumentException("drive.Root"),
                   "NoRoot",
                   ErrorCategory.InvalidArgument,
                   drive));

        return null;
      }

      // Create a new drive and create an ODBC connection to the new drive.
      AccessDBPSDriveInfo accessDBPSDriveInfo = new AccessDBPSDriveInfo(drive);
      OdbcConnectionStringBuilder builder = new OdbcConnectionStringBuilder();

      builder.Driver = "Microsoft Access Driver (*.mdb)";
      builder.Add("DBQ", drive.Root);

      OdbcConnection conn = new OdbcConnection(builder.ConnectionString);
      conn.Open();
      accessDBPSDriveInfo.Connection = conn;

      return accessDBPSDriveInfo;
    }
```

<span data-ttu-id="775c4-132">次に示すのは、新しいドライブの作成に使用されるコンストラクターを含む AccessDBPSDriveInfo 内部クラスです。ドライブの状態情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="775c4-132">The following is the AccessDBPSDriveInfo internal class that includes the constructor used to create a new drive, and contains the state information for the drive.</span></span>

```csharp
internal class AccessDBPSDriveInfo : PSDriveInfo
  {
    /// <summary>
    /// A reference to the connection to the database.
    /// </summary>
    private OdbcConnection connection;

    /// <summary>
    /// Initializes a new instance of the AccessDBPSDriveInfo class.
    /// The constructor takes a single argument.
    /// </summary>
    /// <param name="driveInfo">Drive defined by this provider</param>
    public AccessDBPSDriveInfo(PSDriveInfo driveInfo)
           : base(driveInfo)
    {
    }

    /// <summary>
    /// Gets or sets the ODBC connection information.
    /// </summary>
    public OdbcConnection Connection
    {
        get { return this.connection; }
        set { this.connection = value; }
    }
  }
```

### <a name="implementing-removedrive"></a><span data-ttu-id="775c4-133">RemoveDrive の実装</span><span class="sxs-lookup"><span data-stu-id="775c4-133">Implementing RemoveDrive</span></span>

<span data-ttu-id="775c4-134">[Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドは、ユーザーが[RemovePSDriveCommand](/dotnet/api/Microsoft.PowerShell.Commands.removepsdrivecommand)コマンドレットを呼び出したときに、Windows PowerShell エンジンによって呼び出されたときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="775c4-134">The [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method is called by the Windows PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.RemovePSDriveCommand](/dotnet/api/Microsoft.PowerShell.Commands.removepsdrivecommand) cmdlet.</span></span> <span data-ttu-id="775c4-135">このプロバイダーのメソッドは、Access データベースへの接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="775c4-135">The method in this provider closes the connection to the Access database.</span></span>

```csharp
protected override PSDriveInfo RemoveDrive(PSDriveInfo drive)
    {
      // Check if drive object is null.
      if (drive == null)
      {
        WriteError(new ErrorRecord(
                   new ArgumentNullException("drive"),
                   "NullDrive",
                   ErrorCategory.InvalidArgument,
                   drive));

        return null;
      }

      // Close the ODBC connection to the drive.
      AccessDBPSDriveInfo accessDBPSDriveInfo = drive as AccessDBPSDriveInfo;

      if (accessDBPSDriveInfo == null)
      {
         return null;
      }

      accessDBPSDriveInfo.Connection.Close();

      return accessDBPSDriveInfo;
    }
```
