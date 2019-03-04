---
title: AccessDBProviderSample02 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aaf9351e-157f-4d48-8b8f-1fd64855b682
caps.latest.revision: 10
ms.openlocfilehash: d291e401bbf3da998735ebb00f1eb35521f9a19c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853488"
---
# <a name="accessdbprovidersample02"></a>AccessDBProviderSample02

このサンプルを上書きする方法を示しています、 [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)と[System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッド呼び出しをサポートする、`New-PSDrive`と`Remove-PSDrive`コマンドレット。 このサンプルのプロバイダー クラスから派生、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラス。

## <a name="demonstrates"></a>使用例

> [!IMPORTANT]
> プロバイダー クラスは、ほとんどの場合、次のクラスのいずれかから派生され、可能性があるその他のプロバイダーのインターフェイスが実装されます。
>
> -   [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。 参照してください[AccessDBProviderSample03](./accessdbprovidersample03.md)します。
> -   [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラス。 参照してください[AccessDBProviderSample04](./accessdbprovidersample04.md)します。
> -   [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラス。 参照してください[AccessDBProviderSample05](./accessdbprovidersample05.md)します。
>
> プロバイダーの機能に基づくから派生するを参照しているプロバイダー クラスの選択の詳細については[Your Windows PowerShell プロバイダーの設計](./provider-types.md)します。

このサンプルでは、次の項目を示しています。

- 宣言、`CmdletProvider`属性。

- ドライブのプロバイダー クラスを定義する、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラス。

- 上書き、 [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)新しいドライブの作成をサポートするメソッド。 (このサンプルで動的パラメーターを追加する方法が表示されない、`New-PSDrive`コマンドレットです)。

- 上書き、 [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを既存のドライブの削除をサポートします。

## <a name="example"></a>例

このサンプルを上書きする方法を示しています、 [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)と[System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッド。 このサンプルのプロバイダー ドライブが作成されたときにその接続情報に格納されます、`AccessDBPsDriveInfo`オブジェクト。

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

  /// <summary>
  /// This sample implements a Windows PowerShell provider class
  /// that acts upon an Access database.
  /// </summary>
  /// <remarks>
  /// This example demonstrates only the drive overrides used to
  /// add and remove drives from the database.</remarks>
  [CmdletProvider("AccessDB", ProviderCapabilities.None)]
  public class AccessDBProvider : DriveCmdletProvider
  {
    #region Drive Manipulation

    /// <summary>
    /// The Windows PowerShell engine calls this method when the
    /// New-PSDrive cmdlet is run and the path to this provider is
    /// specified. This method creates a connection to the database
    /// file and sets the Connection property of the PSDriveInfo object.
    /// </summary>
    /// <param name="drive">
    /// Information describing the drive to create.
    /// </param>
    /// <returns>An accessDBPSDriveInfo object that represents
    /// the new drive.</returns>
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
    } // End NewDrive.

    /// <summary>
    /// The Windows PowerShell engine calls this method when the
    /// Remove-PSDrive cmdlet is run and the path to this provider is
    /// specified. This method closes the ODBC connection of the drive.
    /// </summary>
    /// <param name="drive">The drive to remove.</param>
    /// <returns>An accessDBPSDriveInfo object that represents
    /// the removed drive.</returns>
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
    } // End RemoveDrive.

    #endregion Drive Manipulation
  } // End AccessDBProvider class.

  #endregion AccessDBProvider

  #region AccessDBPSDriveInfo

  /// <summary>
  /// Any state associated with the drive is held here. In this
  /// case, the state information is the connection to the database.
  /// </summary>
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
  } // End AccessDBPSDriveInfo class.

  #endregion AccessDBPSDriveInfo
}
```

## <a name="see-also"></a>参照

[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Windows PowerShell プロバイダーのデザイン](./provider-types.md)