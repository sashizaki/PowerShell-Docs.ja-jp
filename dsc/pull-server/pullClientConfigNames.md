---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: PowerShell 5.0 以降の構成名を使用したプル クライアントのセットアップします。
ms.openlocfilehash: fd038a105da7a83ecad9b571e611b65c8ec847b3
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403030"
---
# <a name="set-up-a-pull-client-using-configuration-names-in-powershell-50-and-later"></a>PowerShell 5.0 以降の構成名を使用したプル クライアントのセットアップします。

> 適用先:Windows PowerShell 5.0

> [!IMPORTANT]
> プル サーバー (Windows Feature *DSC-Service*) は、Windows Server のサポート対象のコンポーネントですが、新機能がオファーされる予定はありません。 管理対象のクライアントは、(Windows Server のプル サーバー以降の機能が含まれる) [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) または、[こちら](pullserver.md#community-solutions-for-pull-service)に列挙されているコミュニティ ソリューションのいずれかに切り替えを開始することをお勧めします。

プル クライアントをセットアップする前に、プル サーバーを設定する必要があります。 この順序は必要ありませんが、トラブルシューティングに役立つし、登録が成功したことを確認するのに役立ちます。 プル サーバーを設定するには、次のガイドを使用できます。

- [DSC SMB プル サーバーを設定する](pullServerSmb.md)
- [DSC HTTP プル サーバーを設定する](pullServer.md)

各ターゲット ノードは、構成、リソースをダウンロードしてもその状態を報告を構成できます。 以下のセクションでは、SMB 共有または HTTP プル サーバーの DSC プル クライアントを構成する方法を説明します。 ノードの LCM が更新されるは、割り当てられた構成のダウンロードを構成した場所に連絡されます。 ノードで必要なリソースが存在しない場合に自動的に構成されている場所からダウンロードには。 ノードが構成されている場合、[レポート サーバー](reportServer.md)操作の状態は報告します。

> **注**:このトピックでは、PowerShell 5.0 に適用されます。
PowerShell 4.0 でのプル クライアントの設定については、次を参照してください[構成 ID を使用して、PowerShell 4.0 でのプル クライアントの設定。](pullClientConfigID4.md)

## <a name="configure-the-pull-client-lcm"></a>プル クライアントの LCM を構成します。

次の例のいずれかを実行するという名前の新しい出力フォルダーを作成**PullClientConfigName**と、メタ構成 MOF ファイルが格納されます。 この場合、メタ構成 MOF ファイルの名前は `localhost.meta.mof` になります。

構成を適用するには、**Path** をメタ構成 MOF ファイルの場所に設定して **Set-DscLocalConfigurationManager** コマンドレットを呼び出します。 たとえば、次のように入力します。

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigName –Verbose.
```

## <a name="configuration-name"></a>構成名

セットの下の例、 **ConfigurationName**コンパイル済みの構成の名前を LCM のプロパティは、この目的で作成します。 **ConfigurationName** LCM がプル サーバーで適切な構成を検索に使用するものです。 プル サーバーで構成 MOF ファイルの名前を`<ConfigurationName>.mof`、ここでは、"ClientConfig.mof"。 詳細については、次を参照してください。[構成プル サーバー (v4/v5) を発行](publishConfigs.md)します。

## <a name="set-up-a-pull-client-to-download-configurations"></a>プル クライアントの設定の構成をダウンロードするには

各クライアントを構成する必要があります**プル**モードとその構成が格納されている、プル サーバーの url を指定します。 これを行うには、必要な情報を備えるようにローカル構成マネージャー (LCM) を構成する必要があります。 LCM を構成するには、**DSCLocalConfigurationManager** 属性で修飾された特別な種類の構成を作成します。 LCM の構成の詳細については、「[ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)」をご覧ください。

次のスクリプトは、"CONTOSO-PullSrv" という名前のサーバーから構成をプルするように LCM を構成します。

- このスクリプトでは、**ConfigurationRepositoryWeb** ブロックでプル サーバーを定義しています。 **ServerURL** プロパティには、プル サーバー用のエンドポイントを指定します。

- **RegistrationKey** プロパティは、プル サーバーのすべてのクライアント ノードとそのプル サーバーとの間で共有されるキーです。 同じ値がプル サーバー上のファイルに格納されます。
  > **注**:登録キーでのみ動作**web**プル サーバー。 **SMB** プル サーバーでは、引き続き **ConfigurationID** を使用する必要があります。
  > **ConfigurationID** を使用したプル サーバーの構成については、「[構成 ID を使用したプル クライアントのセットアップ](pullClientConfigId.md)」を参照してください。

- **ConfigurationNames** プロパティは、クライアント ノード用の構成の名前を指定する配列です。
  >**注:** **ConfigurationNames** に複数の値を指定する場合、構成に **PartialConfiguration** ブロックも指定する必要があります。
  >部分構成の詳細については、「[PowerShell Desired State Configuration の部分構成](partialConfigs.md)」を参照してください。

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = '140a952b-b9d6-406b-b416-e0f759c9c0e4'
            ConfigurationNames = @('ClientConfig')
        }
    }
}
PullClientConfigNames
```

## <a name="set-up-a-pull-client-to-download-resources"></a>プル クライアントのセットアップ リソースをダウンロードするには

のみを指定する場合、 **ConfigurationRepositoryWeb**または**ConfigurationRepositoryShare** (前の例では) のように LCM 構成でブロック、プル クライアントは、同じリソースをプルします。".mof"ファイルの保存場所。 クライアントがリソースをダウンロードできる別の場所を指定することもできます。 リソース サーバーを指定するには、**ResourceRepositoryWeb** (Web プル サーバーの場合) または **ResourceRepositoryShare** ブロック (SMB プル サーバーの場合) を使用します。

次の例では、プル サーバーでは、および SMB 共有からのリソースから構成をダウンロードするクライアントを設定するメタ構成を示します。

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }

        ResourceRepositoryShare SMBResources
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigNames
```

## <a name="set-up-a-pull-client-to-report-status"></a>レポートの状態をプル クライアントをセットアップします。

構成、リソース、およびレポートについて単一のプル サーバーを使用できます。 レポートは、既定で構成されてクライアントのいません。 状態をレポートのクライアントを構成するには、作成する必要が、 **ReportRepositoryWeb**ブロックします。 次の例は、単一のプル サーバーに対して構成とリソースをプルし、レポート データを送信するようにクライアントを設定するメタ構成を示しています。

> [!NOTE]
> レポート サーバーは、SMB 共有にすることはできません。

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }

        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }
    }
}
PullClientConfigNames
```

## <a name="see-also"></a>参照

* [構成 ID を使用したプル クライアントのセットアップ](PullClientConfigNames.md)
* [DSC Web プル サーバーのセットアップ](pullServer.md)
