# DSC SMB プル サーバーのセットアップ

>適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

DSC [SMB](https://technet.microsoft.com/en-us/library/hh831795.aspx) プル サーバーは、DSC 構成ファイルや DSC リソースを
必要なときに ターゲット ノードに提供する SMB ファイル共有です。

DSC の SMB プル サーバーを使うには、次のことが必要です。
- PowerShell 4.0 以降を実行しているサーバーに SMB ファイル共有をセットアップする
- SMB 共有からプルするための、PowerShell 4.0 以降を実行しているクライアントを構成する

## xSmbShare リソースを使用して SMB ファイル共有を作成する

SMB ファイル共有を設定する方法はいくつかありますが、ここでは DSC を使って設定する方法を紹介します。

### xSmbShare リソースをインストールする

[Install-Module](https://technet.microsoft.com/en-us/library/dn807162.aspx) コマンドレットを呼び出して **xSmbShare** モジュールをインストールします。
>**注**: **Install-Module** は、PowerShell 5.0 に含まれている **PowerShellGet** モジュールに含まれています。 PowerShell 3.0 および 4.0 用の **PowerShellGet** モジュールは、
>「[PackageManagement PowerShell Modules Preview (PackageManagement PowerShell モジュールのプレビュー)](https://www.microsoft.com/en-us/download/details.aspx?id=49186)」でダウンロードできます。 **xSmbShare** に含まれる DSC リソース **xSmbShare** を使うと、
SMB ファイル共有を作成できます。

### ディレクトリとファイル共有を作成する

次の構成では、[File](fileResource.md) リソースを使って共有するディレクトリを作成し、**xSmbShare** リソースを使って SMB 共有をセットアップします。

```powershell
Configuration SmbShare {

Import-DscResource -ModuleName PSDesiredStateConfiguration
Import-DscResource -ModuleName xSmbShare
 
    Node localhost {
 
        File CreateFolder {
 
            DestinationPath = 'C:\DscSmbShare'
            Type = 'Directory'
            Ensure = 'Present'
 
        }
 
        xSMBShare CreateShare {
 
            Name = 'DscSmbShare'
            Path = 'C:\DscSmbShare'
            FullAccess = 'admininstrator'
            ReadAccess = 'myDomain\Contoso-Server$'
            FolderEnumerationMode = 'AccessBased'
            Ensure = 'Present'
            DependsOn = '[File]CreateFolder'
 
        }
        
    }
 
}
```

ディレクトリ `C:\DscSmbShare` がまだ存在しない場合は、構成によって作成され、そのディレクトリが SMB ファイル共有として使用されます。 **FullAccess** は、
ファイル共有に書き込む必要がある、またはファイル共有から削除する必要があるアカウントに与える必要があります。**ReadAccess** は、共有から構成や DSC リソースを取得するすべてのクライアント ノードに与える必要があります (
これは、DSC が既定ではシステム アカウントとして実行されるので、コンピューター自体も共有にアクセスする必要があるためです)。


### ファイル システムにプル クライアントへのアクセス権限を付与する

クライアント ノードに **ReadAccess** を与えると、そのノードは SMB 共有にアクセスできるようになりますが、その共有内のファイルやフォルダーにはアクセスできません。 SMB 共有ノードのフォルダーやサブフォルダーに対するアクセス権限をクライアントに明示的に許可する必要があります。
folder and sub-folders. DSC でこれを行うには、[cNtfsAccessControl](https://www.powershellgallery.com/packages/cNtfsAccessControl/1.2.0) モジュールに含まれている **cNtfsPermissionEntry** リソースを追加して使用します。
module. 次の構成では、プル クライアントに ReadAndExecute アクセスを付与する **cNtfsPermissionEntry** ブロックを追加します。

```powershell
Configuration DSCSMB {

Import-DscResource -ModuleName PSDesiredStateConfiguration
Import-DscResource -ModuleName xSmbShare
Import-DscResource -ModuleName cNtfsAccessControl
 
    Node localhost {
 
        File CreateFolder {
 
            DestinationPath = 'DscSmbShare'
            Type = 'Directory'
            Ensure = 'Present'
 
        }
 
        xSMBShare CreateShare {
 
            Name = 'DscSmbShare'
            Path = 'DscSmbShare'
            FullAccess = 'administrator'
            ReadAccess = 'myDomain\Contoso-Server$'
            FolderEnumerationMode = 'AccessBased'
            Ensure = 'Present'
            DependsOn = '[File]CreateFolder'
 
        }

        cNtfsPermissionEntry PermissionSet1 {
            
        Ensure = 'Present'
        Path = 'C:\DSCSMB'
        Principal = 'myDomain\Contoso-Server$'
        AccessControlInformation = @(
            cNtfsAccessControlInformation
            {
                AccessControlType = 'Allow'
                FileSystemRights = 'ReadAndExecute'
                Inheritance = 'ThisFolderSubfoldersAndFiles'
                NoPropagateInherit = $false
            }
        )
        DependsOn = '[File]CreateFolder'
        
        }
 
        
    }
 
}
```

## 構成とリソースの配置

クライアント ノードがプルする必要のある構成 MOF ファイルや DSC リソースを SMB 共有フォルダーに保存します。

すべての構成 MOF ファイルは、_ConfigurationID_.mof という名前である必要があります。ここで、_ConfigurationID_ はターゲット ノードの LCM の **ConfigurationID** プロパティの値です。 以下の詳細については、
プル クライアントの設定については、「[構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID.md)」をご覧ください。

>**注:** SMB プル サーバーを使っている場合は、構成 ID を使う必要があります。 構成名は、SMB ではサポートされません。

クライアントに必要なすべてのリソースは、アーカイブ済みの `.zip` ファイルとして SMB 共有フォルダーに配置する必要があります。  

## MOF チェックサムの作成
ターゲット ノード上の LCM が構成を検証できるように、構成 MOF ファイルはチェックサム ファイルと組み合わせて使用する必要があります。 
チェックサムを作成するには、[New-DSCCheckSum](https://technet.microsoft.com/en-us/library/dn521622.aspx) コマンドレットを呼び出します。 このコマンドレットは、構成 MOF が存在するフォルダーが指定された **Path** パラメーターを受け取ります。 
where the configuration MOF is located. このコマンドレットは、`ConfigurationMOFName.mof.checksum` という名前でチェックサム ファイルを作成します。ここで、`ConfigurationMOFName` は構成 MOF ファイルの名前です。 
指定のフォルダーに複数の構成 MOF ファイルがある場合は、そのフォルダー内の構成ごとにチェックサムが作成されます。

チェックサム ファイルは、構成 MOF ファイルと同じディレクトリ (既定では `$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration`) に存在し、拡張子として `.checksum` が付けられた同じ名前である必要があります。

>**注**: 何らかの方法で構成 MOF ファイルを変更した場合は、チェックサム ファイルも作成し直す必要があります。

## 謝辞

次の方々に感謝します。

- DSC で SMB を使用することに関する Mike F. Robbins 氏の投稿を、このトピックの内容として参考にしました。 彼のブログは [Mike F Robbins](http://mikefrobbins.com/) にあります。
- **cNtfsAccessControl** モジュールを作成した Serge Nikalaichyk 氏。 このモジュールのソースは、https://github.com/SNikalaichyk/cNtfsAccessControl にあります。

## 関連項目
- [Windows PowerShell Desired State Configuration の概要](overview.md)
- [構成の適用](enactingConfigurations.md)
- [構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID.md)

 

<!--HONumber=Mar16_HO2-->


