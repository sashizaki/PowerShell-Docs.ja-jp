---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: PowerShell 5.0 以降で、構成 Id を使用して、プル クライアントの設定します。
ms.openlocfilehash: 8d8cf478f9127e1b7005d1b9e832e84b11612c9c
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402782"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-50-and-later"></a>PowerShell 5.0 以降で、構成 Id を使用して、プル クライアントの設定します。

> 適用先:Windows PowerShell 5.0

> [!IMPORTANT]
> プル サーバー (Windows Feature *DSC-Service*) は、Windows Server のサポート対象のコンポーネントですが、新機能がオファーされる予定はありません。 管理対象のクライアントは、(Windows Server のプル サーバー以降の機能が含まれる) [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) または、[こちら](pullserver.md#community-solutions-for-pull-service)に列挙されているコミュニティ ソリューションのいずれかに切り替えを開始することをお勧めします。

プル クライアントをセットアップする前に、プル サーバーを設定する必要があります。 この順序は必要ありませんが、トラブルシューティングに役立つし、登録が成功したことを確認するのに役立ちます。 プル サーバーを設定するには、次のガイドを使用できます。

- [DSC SMB プル サーバーを設定する](pullServerSmb.md)
- [DSC HTTP プル サーバーを設定する](pullServer.md)

各ターゲット ノードは、構成、リソースをダウンロードしてもその状態を報告を構成できます。 以下のセクションでは、SMB 共有または HTTP プル サーバーの DSC プル クライアントを構成する方法を説明します。 ノードの LCM が更新されるは、割り当てられた構成のダウンロードを構成した場所に連絡されます。 ノードで必要なリソースが存在しない場合に自動的に構成されている場所からダウンロードには。 ノードが構成されている場合、[レポート サーバー](reportServer.md)操作の状態は報告します。

> **注**:このトピックでは、PowerShell 5.0 に適用されます。 PowerShell 4.0 でのプル クライアントのセットアップについては、「[PowerShell 4.0 での構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID4.md)」をご覧ください。

## <a name="configure-the-pull-client-lcm"></a>プル クライアントの LCM を構成します。

次の例のいずれかを実行するという名前の新しい出力フォルダーを作成**PullClientConfigID**と、メタ構成 MOF ファイルが格納されます。 この場合、メタ構成 MOF ファイルの名前は `localhost.meta.mof` になります。

構成を適用するには、**Path** をメタ構成 MOF ファイルの場所に設定して **Set-DscLocalConfigurationManager** コマンドレットを呼び出します。 たとえば、次のように入力します。

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a>構成 ID

セットの下の例、 **ConfigurationID**を LCM のプロパティを**Guid**を以前に作成したこの目的のためです。 **ConfigurationID** は、LCM がプル サーバーで適切な構成を検索する場合に使用します。 プル サーバー上の構成 MOF ファイルは、`ConfigurationID.mof` という名前にする必要があります。ここで、*ConfigurationID* はターゲット ノードの LCM の **ConfigurationID** プロパティの値です。 詳細については、次を参照してください。[構成プル サーバー (v4/v5) を発行](publishConfigs.md)します。

乱数を作成することができます**Guid**またはを使用して、次の例を使用して、 [New-guid](/powershell/module/microsoft.powershell.utility/new-guid)コマンドレット。

```powershell
[System.Guid]::NewGuid()
```

使用しての詳細については**Guid** 、環境内で、次を参照してください。 [Guid の計画](/powershell/dsc/secureserver#guids)します。

## <a name="set-up-a-pull-client-to-download-configurations"></a>プル クライアントの設定の構成をダウンロードするには

各クライアントを構成する必要があります**プル**モードとその構成が格納されている、プル サーバーの url を指定します。 これを行うには、必要な情報を備えるようにローカル構成マネージャー (LCM) を構成する必要があります。 LCM を構成するには、**DSCLocalConfigurationManager** 属性で修飾された特別な種類の構成を作成します。 LCM の構成の詳細については、「[ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)」をご覧ください。

### <a name="http-dsc-pull-server"></a>HTTP の DSC プル サーバー

次のスクリプトは、"CONTOSO-PullSrv" という名前のサーバーから構成をプルするように LCM を構成します。

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }
    }
}
PullClientConfigID
```

このスクリプトでは、**ConfigurationRepositoryWeb** ブロックでプル サーバーを定義しています。 **ServerUrl** DSC プルの url を指定します

### <a name="smb-share"></a>SMB 共有

次のスクリプトは SMB 共有から構成をプルする LCM を構成します`\\SMBPullServer\Pull`します。

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryShare SMBPullServer
        {
            SourcePath = '\\SMBPullServer\Pull'
        }
    }
}
PullClientConfigID
```

スクリプトでは、 **ConfigurationRepositoryShare**ブロックは、この場合は、SMB 共有だけであるプル サーバーを定義します。

## <a name="set-up-a-pull-client-to-download-resources"></a>プル クライアントのセットアップ リソースをダウンロードするには

のみを指定する場合、 **ConfigurationRepositoryWeb**または**ConfigurationRepositoryShare** (前の例では) のように LCM 構成でブロック、プル クライアントは、同じリソースをプルします。場所がその構成を取得します。 リソースの別の場所を指定することもできます。 別のサーバーとして、リソースの場所を指定するには、使用、 **ResourceRepositoryWeb**ブロックします。 SMB 共有として、リソースの場所を指定するには、使用、 **ResourceRepositoryShare**ブロックします。

> [!NOTE]
> 組み合わせることができます**ConfigurationRepositoryWeb**で**ResourceRepositoryShare**または**ConfigurationRepositoryShare**で**ResourceRepositoryWeb**. この例は、以下は表示されません。

### <a name="http-dsc-pull-server"></a>HTTP の DSC プル サーバー

次のメタ構成から構成を取得するプル クライアント**Contoso-pullsrv**とそのリソースから**Contoso-resourcesrv**します。

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }

        ResourceRepositoryWeb CONTOSO-ResourceSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

### <a name="smb-share"></a>SMB 共有

次の例では、SMB 共有から構成をプルするクライアントを設定するメタ構成を`\\SMBPullServer\Configurations`、および SMB 共有からリソース`\\SMBPullServer\Resources`します。

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryShare SMBPullServer
        {
            SourcePath = '\\SMBPullServer\Configurations'
        }

        ResourceRepositoryShare SMBResourceServer
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigID
```

#### <a name="automatically-download-resources-in-push-mode"></a>プッシュ モードでリソースを自動的にダウンロードします。

PowerShell 5.0 以降では、プル クライアントできますからモジュールをダウンロード、SMB 共有が構成されている場合でも**プッシュ**モード。 これは、プル サーバーをセットアップしないシナリオで特に便利です。 **ResourceRepositoryShare**ブロックを指定することがなく使用できる、 **ConfigurationRepositoryShare**します。 次の例では、SMB 共有からプル リソースへのクライアントを設定するメタ構成を`\\SMBPullServer\Resources`します。 とき**PUSHED**構成では、そのは自動的にダウンロード必要なリソースをすべて指定された共有から。

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Push'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
        }

        ResourceRepositoryShare SMBResourceServer
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigID
```

## <a name="set-up-a-pull-client-to-report-status"></a>レポートの状態をプル クライアントをセットアップします。

既定では、ノードはレポートを構成プル サーバーに送信するはしません。 構成、リソース、およびレポートについて単一のプル サーバーを使うことができますが、レポートをセットアップするために **ReportRepositoryWeb** ブロックを作成する必要があります。

### <a name="http-dsc-pull-server"></a>HTTP の DSC プル サーバー

次の例は、単一のプル サーバーに対して構成とリソースをプルし、レポート データを送信するようにクライアントを設定するメタ構成を示しています。

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
        }

        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

レポート サーバーを指定するには、**ReportRepositoryWeb** ブロックを使用します。 レポート サーバーを SMB サーバーにすることはできません。
次のメタ構成は、**CONTOSO-PullSrv** から構成を取得し、**CONTOSO-ResourceSrv** からリソースを取得し、**CONTOSO-ReportSrv** に状態レポートを送信するように、プル クライアントを構成します。

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }

        ResourceRepositoryWeb CONTOSO-ResourceSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }

        ReportServerWeb CONTOSO-ReportSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

### <a name="smb-share"></a>SMB 共有

レポート サーバーは、SMB 共有にすることはできません。

## <a name="next-steps"></a>次の手順

プル クライアントを構成すると、次の手順を実行するのに、次のガイドを使用できます。

- [プル サーバーに構成を発行する (v4/v5)](publishConfigs.md)
- [リソースのパッケージ化とプル サーバーへのアップロード (v4)](package-upload-resources.md)

## <a name="see-also"></a>参照

* [構成名を使用したプル クライアントのセットアップ](pullClientConfigNames.md)
