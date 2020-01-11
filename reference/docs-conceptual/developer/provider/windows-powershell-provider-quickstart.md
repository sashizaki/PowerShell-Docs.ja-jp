---
title: Windows PowerShell プロバイダーのクイックスタート |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e879ba7-c334-460b-94a1-3e9b63d3d8de
caps.latest.revision: 5
ms.openlocfilehash: 949c0d63b1e5bca1bfe670362df4297c29e98fcc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359921"
---
# <a name="windows-powershell-provider-quickstart"></a>Windows PowerShell プロバイダー クイック スタート

このトピックでは、新しいドライブを作成する基本的な機能を備えた Windows PowerShell プロバイダーを作成する方法について説明します。 プロバイダーの一般的な情報については、「 [Windows PowerShell プロバイダーの概要](./windows-powershell-provider-overview.md)」を参照してください。 より詳細な機能を持つプロバイダーの例については、[プロバイダーのサンプル](./provider-samples.md)を参照してください。

## <a name="writing-a-basic-provider"></a>基本的なプロバイダーの作成

Windows PowerShell プロバイダーの最も基本的な機能は、ドライブを作成および削除することです。 この例では、[Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) クラスの[Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) * メソッドと[Drivecmdletprovider *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを実装しています。この例では、クラスが使用されています。この例を次に示します。 また、プロバイダークラスを宣言する方法についても説明します。

プロバイダーを作成するときに、プロバイダーが利用可能になったときに自動的に作成される既定のドライブドライブを指定できます。 また、そのプロバイダーを使用する新しいドライブを作成するためのメソッドを定義します。

このトピックで示す例は、Access データベースを Windows PowerShell ドライブとして表す大規模なサンプルの一部である[AccessDBProviderSample02](./accessdbprovidersample02.md)サンプルに基づいています。

### <a name="setting-up-the-project"></a>プロジェクトの設定

Visual Studio で、AccessDBProviderSample という名前のクラスライブラリプロジェクトを作成します。 次の手順を実行して、Windows PowerShell が起動するようにプロジェクトを構成し、プロジェクトをビルドして起動すると、プロバイダーがセッションに読み込まれるようにします。

##### <a name="configure-the-provider-project"></a>プロバイダープロジェクトの構成

1. プロジェクトへの参照として、system.servicemodel アセンブリを追加します。

2. **[プロジェクト > AccessDBProviderSample のプロパティ > デバッグ]** をクリックします。 **[プロジェクトの開始]** で、 **[外部プログラムの開始]** をクリックし、Windows PowerShell 実行可能ファイル (通常は c:\Windows\System32\WindowsPowerShell\v1.0\\) に移動します。

3. **[開始オプション]** で、 **[コマンドライン引数]** ボックスに次のように入力し `-noexit -command "[reflection.assembly]::loadFrom(AccessDBProviderSample.dll' ) | import-module"`

### <a name="declaring-the-provider-class"></a>プロバイダークラスの宣言

このプロバイダーは、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスから派生します。 実際の機能 (項目へのアクセスと操作、データストア内の移動、項目のコンテンツの取得と設定) を提供する[ほとんどのプロバイダーは、system.servicemodel](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスから派生します。

クラスが [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) から派生することを指定するだけでなく、例に示すように、このクラスをプロバイダーの[System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)属性で修飾する必要がありますが、

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

### <a name="implementing-newdrive"></a>NewDrive の実装

[Drivecmdletprovider *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッドは、ユーザーがプロバイダーの名前を指定して[NewPSDriveCommand](/dotnet/api/Microsoft.PowerShell.Commands.Newpsdrivecommand)コマンドレットを呼び出したときに、Windows PowerShell エンジンによって呼び出されたときに使用されます。 System.management.automation.psdriveinfo パラメーターは Windows PowerShell エンジンによって渡され、メソッドは新しいドライブを Windows PowerShell エンジンに返します。 このメソッドは、上記で作成したクラス内で宣言する必要があります。

メソッドは、最初に、渡されたドライブオブジェクトとドライブルートの両方が存在することを確認し、そのいずれかが存在しない場合は `null` を返します。 次に、内部クラス AccessDBPSDriveInfo のコンストラクターを使用して、新しいドライブと、ドライブが表す Access データベースへの接続を作成します。

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

次に示すのは、新しいドライブの作成に使用されるコンストラクターを含む AccessDBPSDriveInfo 内部クラスです。ドライブの状態情報が含まれています。

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

### <a name="implementing-removedrive"></a>RemoveDrive の実装

[Drivecmdletprovider *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドは、ユーザーが[RemovePSDriveCommand](/dotnet/api/Microsoft.PowerShell.Commands.removepsdrivecommand)コマンドレットを呼び出したときに、Windows PowerShell エンジンによって呼び出されたときに呼び出されます。 このプロバイダーのメソッドは、Access データベースへの接続を閉じます。

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