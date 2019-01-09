---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成 Id (v4/v5) を使用して、プル サーバーへの公開します。
ms.openlocfilehash: 0144fec43d7a8d65b79891567cc0dc3952175343
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402398"
---
# <a name="publish-to-a-pull-server-using-configuration-ids-v4v5"></a>構成 Id (v4/v5) を使用して、プル サーバーへの公開します。

以下のセクションでは、プル サーバーを既に設定したことを前提としています。 プル サーバーを設定していない場合は、次のガイドを使用できます。

- [DSC SMB プル サーバーを設定する](pullServerSmb.md)
- [DSC HTTP プル サーバーを設定する](pullServer.md)

各ターゲット ノードは、構成、リソースをダウンロードしてもその状態を報告を構成できます。 この記事では、ダウンロード、およびリソースを自動的にダウンロードするクライアントの構成に利用できるように、リソースをアップロードする方法を示します。 ノードがを通じて割り当てられた構成を受信すると**プル**または**プッシュ**(v5) では、自動的にダウンロードし、LCM で指定された場所からの構成に必要なすべてのリソース。

## <a name="compile-configurations"></a>構成をコンパイルします。

格納するため、まず[構成](../configurations/configurations.md)プル サーバーでは、".mof"ファイルにコンパイルします。 構成を汎用、および多くのクライアントに適用するのには使用`localhost`ノード ブロックにします。 次の例を使用する構成シェル`localhost`特定のクライアント名の代わりにします。

```powershell
Configuration GenericConfig
{
    Node localhost
    {

    }
}
GenericConfig
```

一般的な構成をコンパイルした後、"localhost.mof"ファイルが必要です。

## <a name="renaming-the-mof-file"></a>MOF ファイルの名前を変更します。

により、プル サーバー上の構成".mof"ファイルを保存できる**ConfigurationName**または**ConfigurationID**します。 によって、プル クライアントをセットアップする方法、正しくコンパイル".mof"ファイルの名前を変更するのには、次のセクションを選択できます。

### <a name="configuration-ids-guid"></a>構成 Id (GUID)

"Localhost.mof"ファイルの名前を変更する必要があります"<GUID>.mof"ファイル。 乱数を作成することができます**Guid**またはを使用して、次の例を使用して、 [New-guid](/powershell/module/microsoft.powershell.utility/new-guid)コマンドレット。

```powershell
[System.Guid]::NewGuid()
```

サンプル出力

```output
Guid
----
64856475-939e-41fb-aba5-4469f4006059
```

許容可能な任意のメソッドを使用して、".mof"ファイルの名前を変更することができます。 次の例を使用して、 [Rename-item](/powershell/module/microsoft.powershell.management/rename-item)コマンドレット。

```powershell
Rename-Item -Path .\localhost.mof -NewName '64856475-939e-41fb-aba5-4469f4006059.mof'
```

使用しての詳細については**Guid** 、環境内で、次を参照してください。 [Guid の計画](/powershell/dsc/secureserver#guids)します。

### <a name="configuration-names"></a>構成名

"Localhost.mof"ファイルの名前を変更する必要があります"<Configuration Name>.mof"ファイル。 次の例では、前のセクションから構成の名前が使用されます。 許容可能な任意のメソッドを使用して、".mof"ファイルの名前を変更することができます。 次の例を使用して、 [Rename-item](/powershell/module/microsoft.powershell.management/rename-item)コマンドレット。

```powershell
Rename-Item -Path .\localhost.mof -NewName 'GenericConfig.mof'
```

## <a name="create-the-checksum"></a>チェックサムを作成します。

関連付けられている".checksum"ファイルが存在する必要がある、プル サーバーの場合、または SMB 共有で".mof"の各ファイルが格納されます。 このファイルには、クライアントが関連付けられている".mof"ファイルが変更され再度ダウンロードする必要がありますを知ることができます。

作成することができます、**チェックサム**で、 [New-dscchecksum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum)コマンドレット。 実行することも`New-DSCCheckSum`を使用してファイルのディレクトリに対して、`-Path`パラメーター。 チェックサムが既に存在する場合に再作成することを強制できます、`-Force`パラメーター。 次の例は、前のセクションから".mof"ファイルを含むディレクトリを指定しを使用して、`-Force`パラメーター。

```powershell
New-DscChecksum -Path '.\' -Force
```

出力は表示されませんが、表示する必要があります、"<GUID or Configuration Name>。 mof.checksum"ファイル。

## <a name="where-to-store-mof-files-and-checksums"></a>MOF ファイルとチェックサムを格納する場所

### <a name="on-a-dsc-http-pull-server"></a>DSC の HTTP プル サーバー

設定すると、HTTP プル サーバー上で説明したよう[DSC HTTP プル サーバーを設定する](pullServer.md)、用のディレクトリを指定する、 **ModulePath**と**ConfigurationPath**キー。 **ConfigurationPath**キーは、".mof"ファイルの格納場所を示します。 **ConfigurationPath** ".mof"ファイルと".checksum"ファイルを格納することを示します。

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

### <a name="on-an-smb-share"></a>SMB 共有に

指定した SMB 共有を使用するプル クライアントを設定すると、 **ConfigurationRepositoryShare**します。 すべての".mof"ファイルと".checksum"ファイルを格納する必要がありますし、 **SourcePath**ディレクトリから、 **ConfigurationRepositoryShare**ブロックします。

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

## <a name="next-steps"></a>次の手順

次に、指定した構成をプルするプル クライアントを構成するされます。 詳細については、次のガイドのいずれかを参照してください。

- [構成 Id (v4) を使用して、プル クライアントの設定します。](pullClientConfigId4.md)
- [構成 Id (v5) を使用して、プル クライアントの設定します。](pullClientConfigId.md)
- [構成名 (v5) を使用したプル クライアントのセットアップします。](pullClientConfigNames.md)

## <a name="see-also"></a>関連項目

- [DSC SMB プル サーバーを設定する](pullServerSmb.md)
- [DSC HTTP プル サーバーを設定する](pullServer.md)
- [パッケージと、プル サーバーにアップロード リソース](package-upload-resources.md)
