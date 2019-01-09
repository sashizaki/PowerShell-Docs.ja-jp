---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: PowerShell 4.0 では、構成 Id を使用して、プル クライアントの設定します。
ms.openlocfilehash: 9adc767e91ff19d373c122a0d493e7b8703d5476
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402990"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-40"></a>PowerShell 4.0 では、構成 Id を使用して、プル クライアントの設定します。

>適用先:Windows PowerShell 4.0、Windows PowerShell 5.0

> [!IMPORTANT]
> プル サーバー (Windows Feature *DSC-Service*) は、Windows Server のサポート対象のコンポーネントですが、新機能がオファーされる予定はありません。 管理対象のクライアントは、(Windows Server のプル サーバー以降の機能が含まれる) [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) または、[こちら](pullserver.md#community-solutions-for-pull-service)に列挙されているコミュニティ ソリューションのいずれかに切り替えを開始することをお勧めします。

プル クライアントをセットアップする前に、プル サーバーを設定する必要があります。 この順序は必要ありませんが、トラブルシューティングに役立つし、登録が成功したことを確認するのに役立ちます。 プル サーバーを設定するには、次のガイドを使用できます。

- [DSC SMB プル サーバーを設定する](pullServerSmb.md)
- [DSC HTTP プル サーバーを設定する](pullServer.md)

各ターゲット ノードは、構成、リソースをダウンロードしてもその状態を報告を構成できます。 以下のセクションでは、SMB 共有または HTTP プル サーバーの DSC プル クライアントを構成する方法を説明します。 ノードの LCM が更新されるは、割り当てられた構成のダウンロードを構成した場所に連絡されます。 ノードで必要なリソースが存在しない場合に自動的に構成されている場所からダウンロードには。 ノードが構成されている場合、[レポート サーバー](reportServer.md)操作の状態は報告します。

## <a name="configure-the-pull-client-lcm"></a>プル クライアントの LCM を構成します。

次の例のいずれかを実行するという名前の新しい出力フォルダーを作成**PullClientConfigID**と、メタ構成 MOF ファイルが格納されます。 この場合、メタ構成 MOF ファイルの名前は `localhost.meta.mof` になります。

構成を適用するには、**Path** をメタ構成 MOF ファイルの場所に設定して **Set-DscLocalConfigurationManager** コマンドレットを呼び出します。 たとえば、次のように入力します。

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a>構成 ID

以下の一連の例、 **ConfigurationID**を LCM のプロパティを**Guid**を以前に作成したこの目的のためです。 **ConfigurationID** は、LCM がプル サーバーで適切な構成を検索する場合に使用します。 プル サーバー上の構成 MOF ファイルは、`ConfigurationID.mof` という名前にする必要があります。ここで、*ConfigurationID* はターゲット ノードの LCM の **ConfigurationID** プロパティの値です。 詳細については、次を参照してください。[構成プル サーバー (v4/v5) を発行](publishConfigs.md)します。

乱数を作成することができます**Guid**次の例を使用します。

```powershell
[System.Guid]::NewGuid()
```

## <a name="set-up-a-pull-client-to-download-configurations"></a>プル クライアントの設定の構成をダウンロードするには

各クライアントを構成する必要があります**プル**モードとその構成が格納されている、プル サーバーの url を指定します。 これを行うには、必要な情報を備えるようにローカル構成マネージャー (LCM) を構成する必要があります。 LCM を構成すると、特別な種類の構成を作成する、 **LocalConfigurationManager**ブロックします。 LCM の構成の詳細については、「[ローカル構成マネージャーの構成](../managing-nodes/metaConfig4.md)」をご覧ください。

## <a name="http-dsc-pull-server"></a>HTTP の DSC プル サーバー

プル サーバーは、web サービスとしてセットアップは、設定、 **DownloadManagerName**に**WebDownloadManager**します。 **WebDownloadManager**指定する必要があります、 **ServerUrl**を**DownloadManagerCustomData**キー。 値を指定することもできます。 **AllowUnsecureConnection**次の例のようにします。 次のスクリプトは、"PullServer" という名前のサーバーから構成をプルするように LCM を構成します。

```powershell
Configuration PullClientConfigId
{
    LocalConfigurationManager
    {
        ConfigurationID = "1C707B86-EF8E-4C29-B7C1-34DA2190AE24";
        RefreshMode = "PULL";
        DownloadManagerName = "WebDownloadManager";
        RebootNodeIfNeeded = $true;
        RefreshFrequencyMins = 30;
        ConfigurationModeFrequencyMins = 30;
        ConfigurationMode = "ApplyAndAutoCorrect";
        DownloadManagerCustomData = @{ServerUrl = "http://PullServer:8080/PSDSCPullServer/PSDSCPullServer.svc"; AllowUnsecureConnection = “TRUE”}
    }
}
PullClientConfigId -Output "."
```

## <a name="smb-share"></a>SMB 共有

プル サーバーは、web サービスではなく、SMB ファイル共有としてセットアップは、設定、 **DownloadManagerName**に**DscFileDownloadManager**なく**WebDownLoadManager**. **DscFileDownloadManager**指定する必要があります、 **SourcePath**プロパティ、 **DownloadManagerCustomData**します。 次のスクリプトは、"CONTOSO-SERVER" という名前のサーバーの "SmbDscShare" という名前の SMB 共有から構成をプルするように LCM を構成します。

```powershell
Configuration PullClientConfigId
{
    LocalConfigurationManager
    {
        ConfigurationID = "1C707B86-EF8E-4C29-B7C1-34DA2190AE24";
        RefreshMode = "PULL";
        DownloadManagerName = "DscFileDownloadManager";
        RebootNodeIfNeeded = $true;
        RefreshFrequencyMins = 30;
        ConfigurationModeFrequencyMins = 30;
        ConfigurationMode = "ApplyAndAutoCorrect";
        DownloadManagerCustomData = @{ServerUrl = "\\CONTOSO-SERVER\SmbDscShare"}
    }
}
PullClientConfigId -Output "."
```

## <a name="next-steps"></a>次の手順

プル クライアントを構成すると、次の手順を実行するのに、次のガイドを使用できます。

- [プル サーバーに構成を発行する (v4/v5)](publishConfigs.md)
- [リソースのパッケージ化とプル サーバーへのアップロード (v4)](package-upload-resources.md)

## <a name="see-also"></a>参照

- [DSC web プル サーバーをセットアップします。](pullServer.md)
- [DSC SMB プル サーバーを設定する](pullServerSMB.md)
