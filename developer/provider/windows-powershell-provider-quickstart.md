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
ms.openlocfilehash: ab78bcad301215bca9b5324bdb8de863899edec6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862148"
---
# <a name="windows-powershell-provider-quickstart"></a>Windows PowerShell プロバイダー クイック スタート

このトピックでは、新しいドライブを作成する基本的な機能を備えた Windows PowerShell プロバイダーを作成する方法について説明します。 プロバイダーの詳細については、次を参照してください。 [Windows PowerShell プロバイダーの概要](./windows-powershell-provider-overview.md)します。 完全な機能を持つプロバイダーの例については、次を参照してください。[プロバイダ サンプル](./provider-samples.md)します。

## <a name="writing-a-basic-provider"></a>基本的なプロバイダーの作成

Windows PowerShell プロバイダーの最も基本的な機能を作成し、ドライブを削除します。 この例では、実装、 [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)と[System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッド、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラス。 プロバイダー クラスを宣言する方法も表示されます。

プロバイダーを作成する場合は、既定のドライブのドライブ、プロバイダーが使用可能なときに自動的に作成されるを指定できます。 また、そのプロバイダーを使用して、新しいドライブを作成するメソッドを定義します。

このトピックで例がに基づいて、 [AccessDBProviderSample02](./accessdbprovidersample02.md)サンプルについては、Windows PowerShell ドライブとして Access データベースを表す大規模なサンプルの一部であります。

### <a name="setting-up-the-project"></a>プロジェクトの設定

Visual Studio で、AccessDBProviderSample をという名前のクラス ライブラリ プロジェクトを作成します。 ビルドして、プロジェクトを開始できるように、Windows PowerShell が起動し、プロバイダーがセッションに読み込まれるが、プロジェクトを構成する次の手順を完了します。

##### <a name="configure-the-provider-project"></a>プロバイダーのプロジェクトを構成します。

1. プロジェクトへの参照として System.Management.Automation アセンブリを追加します。

2. クリックして**プロジェクト > AccessDBProviderSample プロパティ > デバッグ**します。 **スタート プロジェクト**、 をクリックして**外部プログラムの開始**、Windows PowerShell の実行可能ファイルに移動します (通常は c:\Windows\System32\WindowsPowerShell\v1.0\\。 powershell.exe)。

3. **開始オプション**に次の入力、**コマンドライン引数**ボックス。 `-noexit -command "[reflection.assembly]::loadFrom(AccessDBProviderSample.dll' ) | import-module"`

### <a name="declaring-the-provider-class"></a>プロバイダー クラスを宣言します。

派生して、プロバイダー、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラス。 派生して実際の機能 (へのアクセスし項目を操作する、データ ストアを移動し、取得および設定項目の内容) を提供するほとんどのプロバイダー、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラス。

クラスの派生元を指定するだけでなく[System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)で装飾する必要があります、 [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)の例で示すようにします。

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

### <a name="implementing-newdrive"></a>NewDrive を実装します。

[System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッドは、ユーザーを呼び出すと、Windows PowerShell エンジンによって呼び出されます、 [Microsoft.Powershell.Commands.New Psdrive](/dotnet/api/Microsoft.PowerShell.Commands.New-PSDrive)コマンドレット、プロバイダーの名前を指定します。 Windows PowerShell エンジンによって PSDriveInfo パラメーターが渡され、メソッドは、Windows PowerShell エンジンに新しいドライブを返します。 このメソッドは、上記で作成したクラス内で宣言する必要があります。

メソッドは、まず、そのドライブ オブジェクトとドライブのルートで渡された両方存在、返すかどうかを確認する`null`それらのいずれかがない場合。 新しいドライブを作成する次の内部クラス AccessDBPSDriveInfo コンス トラクターを使用して、Access データベース ドライブへの接続を表します。

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

次は、新しいドライブを作成するために使用するコンス トラクターが含まれていますし、ドライブの状態情報を含む AccessDBPSDriveInfo 内部クラスです。

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

### <a name="implementing-removedrive"></a>RemoveDrive を実装します。

[System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドは、ユーザーを呼び出すと、Windows PowerShell エンジンによって呼び出されます、 [Microsoft.Powershell.Commands.Remove Psdrive](/dotnet/api/Microsoft.PowerShell.Commands.Remove-PSDrive)コマンドレット。 このプロバイダーでこのメソッドは、Access データベースへの接続を閉じます。

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