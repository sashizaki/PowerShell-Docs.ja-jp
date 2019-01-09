---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: パッケージと、プル サーバーにアップロード リソース
ms.openlocfilehash: 29a62f96393a53c9e7da57a5e51732dcb0937194
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402301"
---
# <a name="package-and-upload-resources-to-a-pull-server"></a>パッケージと、プル サーバーにアップロード リソース

以下のセクションでは、プル サーバーを既に設定したことを前提としています。 プル サーバーを設定していない場合は、次のガイドを使用できます。

- [DSC SMB プル サーバーを設定する](pullServerSmb.md)
- [DSC HTTP プル サーバーを設定する](pullServer.md)

各ターゲット ノードは、構成、リソースをダウンロードしてもその状態を報告を構成できます。 この記事では、ダウンロード、およびリソースを自動的にダウンロードするクライアントの構成に利用できるように、リソースをアップロードする方法を示します。 ノードがを通じて割り当てられた構成を受信すると**プル**または**プッシュ**(v5) では、自動的にダウンロードし、LCM で指定された場所からの構成に必要なすべてのリソース。

## <a name="package-resource-modules"></a>パッケージ リソース モジュール

クライアントをダウンロードするために使用可能な各リソースは、".zip"ファイルに格納する必要があります。 次の例を使用して必要な手順が表示されます、 [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0)リソース。

> [!NOTE]
> PowerShell 4.0 を使用して、クライアントがある場合に、リソースのフォルダー構造 flaten する必要があり、バージョン フォルダーを削除します。 詳細については、次を参照してください。[複数のリソース バージョン](../configurations/import-dscresource.md#multiple-resource-versions)します。

任意のユーティリティ、スクリプト、または使用するメソッドを使用して、リソース ディレクトリを圧縮することができます。 、Windows で実行できます*を右クリックして*"xPSDesiredStateConfiguration"ディレクトリ、および「を送信する」、し、「圧縮フォルダー」を選択します。

![右クリック](../media/right-click.gif)

### <a name="naming-the-resource-archive"></a>リソースのアーカイブの名前を付ける

リソースのアーカイブは、次の形式で名前を指定する必要があります。

```
{ModuleName}_{Version}.zip
```

上記の例では、"xPSDesiredStateConfiguration.zip"によって"xPSDesiredStateConfiguration_8.4.4.0.zip"の名前を変更する必要があります。

### <a name="create-checksums"></a>チェックサムを作成します。

リソース モジュールを圧縮され名前を変更すると、作成する必要があります、**チェックサム**します。  **チェックサム**使用して、クライアントでは、LCM によってリソースが変更されていると再度ダウンロードする必要があります。 作成することができます、**チェックサム**で、 [New-dscchecksum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum)コマンドレットは、次の例で示すようにします。

```powershell
New-DscChecksum -Path .\xPSDesiredStateConfiguration_8.4.4.0.zip
```

出力は表示されませんが、"xPSDesiredStateConfiguration_8.4.4.0.zip.checksum"が表示されます。 実行することも`New-DSCCheckSum`を使用してファイルのディレクトリに対して、`-Path`パラメーター。 チェックサムが既に存在する場合に再作成することを強制できます、`-Force`パラメーター。

### <a name="where-to-store-resource-archives"></a>リソースのアーカイブを格納する場所

#### <a name="on-a-dsc-http-pull-server"></a>DSC の HTTP プル サーバー

設定すると、HTTP プル サーバー上で説明したよう[DSC HTTP プル サーバーを設定する](pullServer.md)、用のディレクトリを指定する、 **ModulePath**と**ConfigurationPath**キー。 **ConfigurationPath**キーは、".mof"ファイルの格納場所を示します。 **ModulePath** DSC リソース モジュールを格納する場所を示します。

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

#### <a name="on-an-smb-share"></a>SMB 共有に

指定した場合、 **ResourceRepositoryShare**、プル クライアントのセットアップは、アーカイブと内のチェックサムを保存すると、 **SourcePath**ディレクトリから、 **ResourceRepositoryShare**ブロックします。

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Configurations'
}

ResourceRepositoryShare SMBResourceServer
{
    SourcePath = '\\SMBPullServer\Resources'
}
```

のみを指定した場合、 **ConfigurationRepositoryShare**、プル クライアントのセットアップは、アーカイブと内のチェックサムを保存すると、 **SourcePath**ディレクトリから、 **ConfigurationRepositoryShare**ブロックします。

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

#### <a name="updating-resources"></a>リソースの更新

アーカイブの名、バージョン番号を変更するか、新しいチェックサムを作成して、そのリソースを更新するノードを強制することができます。 プル クライアントは、必要なリソースの新しいバージョンの確認だけでなく、LCM が更新されると、チェックサムを更新します。

## <a name="see-also"></a>関連項目

- [DSC SMB プル サーバーを設定する](pullServerSmb.md)
- [DSC HTTP プル サーバーを設定する](pullServer.md)
