---
title: Windows PowerShell プロバイダーのクイック スタート |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e879ba7-c334-460b-94a1-3e9b63d3d8de
caps.latest.revision: 5
ms.openlocfilehash: 151b7125afe1b0d386467a0e5f89225716857ac2
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054919"
---
# <a name="windows-powershell-provider-quickstart"></a><span data-ttu-id="0fb1b-102">Windows PowerShell プロバイダー クイック スタート</span><span class="sxs-lookup"><span data-stu-id="0fb1b-102">Windows PowerShell Provider Quickstart</span></span>

<span data-ttu-id="0fb1b-103">このトピックでは、新しいドライブを作成する基本的な機能を備えた Windows PowerShell プロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-103">This topic explains how to create a Windows PowerShell provider that has basic functionality of creating a new drive.</span></span> <span data-ttu-id="0fb1b-104">プロバイダーの詳細については、次を参照してください。 [Windows PowerShell プロバイダーの概要](./windows-powershell-provider-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-104">For general information about providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span> <span data-ttu-id="0fb1b-105">完全な機能を持つプロバイダーの例については、次を参照してください。[プロバイダ サンプル](./provider-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-105">For examples of providers with more complete functionality, see [Provider Samples](./provider-samples.md).</span></span>

## <a name="writing-a-basic-provider"></a><span data-ttu-id="0fb1b-106">基本的なプロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="0fb1b-106">Writing a basic provider</span></span>

<span data-ttu-id="0fb1b-107">Windows PowerShell プロバイダーの最も基本的な機能を作成し、ドライブを削除します。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-107">The most basic functionality of a Windows PowerShell provider is to create and remove drives.</span></span> <span data-ttu-id="0fb1b-108">この例では、実装、 [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)と[System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッド、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-108">In this example, we implement the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) and [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) methods of the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class.</span></span> <span data-ttu-id="0fb1b-109">プロバイダー クラスを宣言する方法も表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-109">You will also see how to declare a provider class.</span></span>

<span data-ttu-id="0fb1b-110">プロバイダーを作成する場合は、既定のドライブのドライブ、プロバイダーが使用可能なときに自動的に作成されるを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-110">When you write a provider, you can specify default drives-drives that are created automatically when the provider is available.</span></span> <span data-ttu-id="0fb1b-111">また、そのプロバイダーを使用して、新しいドライブを作成するメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-111">You also define a method to create new drives that use that provider.</span></span>

<span data-ttu-id="0fb1b-112">このトピックで例がに基づいて、 [AccessDBProviderSample02](./accessdbprovidersample02.md)サンプルについては、Windows PowerShell ドライブとして Access データベースを表す大規模なサンプルの一部であります。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-112">The examples provided in this topic are based on the [AccessDBProviderSample02](./accessdbprovidersample02.md) sample, which is part of a larger sample that represents an Access database as a Windows PowerShell drive.</span></span>

### <a name="setting-up-the-project"></a><span data-ttu-id="0fb1b-113">プロジェクトの設定</span><span class="sxs-lookup"><span data-stu-id="0fb1b-113">Setting up the project</span></span>

<span data-ttu-id="0fb1b-114">Visual Studio で、AccessDBProviderSample をという名前のクラス ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-114">In Visual Studio, create a Class Library project named AccessDBProviderSample.</span></span> <span data-ttu-id="0fb1b-115">ビルドして、プロジェクトを開始できるように、Windows PowerShell が起動し、プロバイダーがセッションに読み込まれるが、プロジェクトを構成する次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-115">Complete the following steps to configure your project so that Windows PowerShell will start, and the provider will be loaded into the session, when you build and start your project.</span></span>

##### <a name="configure-the-provider-project"></a><span data-ttu-id="0fb1b-116">プロバイダーのプロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-116">Configure the provider project</span></span>

1. <span data-ttu-id="0fb1b-117">プロジェクトへの参照として System.Management.Automation アセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-117">Add the System.Management.Automation assembly as a reference to your project.</span></span>

2. <span data-ttu-id="0fb1b-118">クリックして**プロジェクト > AccessDBProviderSample プロパティ > デバッグ**します。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-118">Click **Project > AccessDBProviderSample Properties > Debug**.</span></span> <span data-ttu-id="0fb1b-119">**スタート プロジェクト**、 をクリックして**外部プログラムの開始**、Windows PowerShell の実行可能ファイルに移動します (通常は c:\Windows\System32\WindowsPowerShell\v1.0\\。 powershell.exe)。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-119">In **Start project**, click **Start external program**, and navigate to the Windows PowerShell executable (typically c:\Windows\System32\WindowsPowerShell\v1.0\\.powershell.exe).</span></span>

3. <span data-ttu-id="0fb1b-120">**開始オプション**に次の入力、**コマンドライン引数**ボックス。 `-noexit -command "[reflection.assembly]::loadFrom(AccessDBProviderSample.dll' ) | import-module"`</span><span class="sxs-lookup"><span data-stu-id="0fb1b-120">Under **Start Options**, enter the following into the **Command line arguments** box: `-noexit -command "[reflection.assembly]::loadFrom(AccessDBProviderSample.dll' ) | import-module"`</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="0fb1b-121">プロバイダー クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-121">Declaring the provider class</span></span>

<span data-ttu-id="0fb1b-122">派生して、プロバイダー、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-122">Our provider derives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class.</span></span> <span data-ttu-id="0fb1b-123">派生して実際の機能 (へのアクセスし項目を操作する、データ ストアを移動し、取得および設定項目の内容) を提供するほとんどのプロバイダー、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-123">Most providers that provide real functionality (accessing and manipulating items, navigating the data store, and getting and setting content of items) derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

<span data-ttu-id="0fb1b-124">クラスの派生元を指定するだけでなく[System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)で装飾する必要があります、 [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)の例で示すようにします。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-124">In addition to specifying that the class derives from [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider), you must decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) as shown in the example.</span></span>

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

### <a name="implementing-newdrive"></a><span data-ttu-id="0fb1b-125">NewDrive を実装します。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-125">Implementing NewDrive</span></span>

<span data-ttu-id="0fb1b-126">[System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッドは、ユーザーを呼び出すと、Windows PowerShell エンジンによって呼び出されます、 [Microsoft.PowerShell.Commands.New PSDrive](/dotnet/api/Microsoft.PowerShell.Commands.New-PSDrive)コマンドレット、プロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-126">The [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method is called by the Windows PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.New-PSDrive](/dotnet/api/Microsoft.PowerShell.Commands.New-PSDrive) cmdlet specifying the name of your provider.</span></span> <span data-ttu-id="0fb1b-127">Windows PowerShell エンジンによって PSDriveInfo パラメーターが渡され、メソッドは、Windows PowerShell エンジンに新しいドライブを返します。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-127">The PSDriveInfo parameter is passed by the Windows PowerShell engine, and the method returns the new drive to the Windows PowerShell engine.</span></span> <span data-ttu-id="0fb1b-128">このメソッドは、上記で作成したクラス内で宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-128">This method must be declared within the class created above.</span></span>

<span data-ttu-id="0fb1b-129">メソッドは、まず、そのドライブ オブジェクトとドライブのルートで渡された両方存在、返すかどうかを確認する`null`それらのいずれかがない場合。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-129">The method first checks to make sure both the drive object and the drive root that were passed in exist, returning `null` if either of them do not.</span></span> <span data-ttu-id="0fb1b-130">新しいドライブを作成する次の内部クラス AccessDBPSDriveInfo コンス トラクターを使用して、Access データベース ドライブへの接続を表します。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-130">It then uses a constructor of the internal class AccessDBPSDriveInfo to create a new drive and a connection to the Access database the drive represents.</span></span>

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

<span data-ttu-id="0fb1b-131">次は、新しいドライブを作成するために使用するコンス トラクターが含まれていますし、ドライブの状態情報を含む AccessDBPSDriveInfo 内部クラスです。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-131">The following is the AccessDBPSDriveInfo internal class that includes the constructor used to create a new drive, and contains the state information for the drive.</span></span>

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

### <a name="implementing-removedrive"></a><span data-ttu-id="0fb1b-132">RemoveDrive を実装します。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-132">Implementing RemoveDrive</span></span>

<span data-ttu-id="0fb1b-133">[System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドは、ユーザーを呼び出すと、Windows PowerShell エンジンによって呼び出されます、 [Microsoft.PowerShell.Commands.Remove PSDrive](/dotnet/api/Microsoft.PowerShell.Commands.Remove-PSDrive)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-133">The [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method is called by the Windows PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.Remove-PSDrive](/dotnet/api/Microsoft.PowerShell.Commands.Remove-PSDrive) cmdlet.</span></span> <span data-ttu-id="0fb1b-134">このプロバイダーでこのメソッドは、Access データベースへの接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="0fb1b-134">The method in this provider closes the connection to the Access database.</span></span>

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