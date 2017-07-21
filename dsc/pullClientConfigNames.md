---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "構成名を使用したプル クライアントのセットアップ"
ms.openlocfilehash: 9bfcac87300d30a59b66e60ed24add32e2420e21
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="setting-up-a-pull-client-using-configuration-names"></a><span data-ttu-id="04667-103">構成名を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="04667-103">Setting up a pull client using configuration names</span></span>

> <span data-ttu-id="04667-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="04667-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="04667-105">各ターゲット ノードに対し、プル モードを使用するように指示し、プル サーバーに接続して構成を取得するための URL を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04667-105">Each target node has to be told to use pull mode and given the URL where it can contact the pull server to get configurations.</span></span>
<span data-ttu-id="04667-106">これを行うには、必要な情報を備えるようにローカル構成マネージャー (LCM) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04667-106">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span>
<span data-ttu-id="04667-107">LCM を構成するには、**DSCLocalConfigurationManager** 属性で修飾された特別な種類の構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="04667-107">To configure the LCM, you create a special type of configuration, decorated with the **DSCLocalConfigurationManager** attribute.</span></span>
<span data-ttu-id="04667-108">LCM の構成の詳細については、「[ローカル構成マネージャーの構成](metaConfig.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="04667-108">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](metaConfig.md).</span></span>

> <span data-ttu-id="04667-109">**注**: このトピックは、PowerShell 5.0 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="04667-109">**Note**: This topic applies to PowerShell 5.0.</span></span>
<span data-ttu-id="04667-110">PowerShell 4.0 でのプル クライアントのセットアップについては、「[PowerShell 4.0 での構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID4.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04667-110">For information on setting up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)</span></span>

<span data-ttu-id="04667-111">次のスクリプトは、"CONTOSO-PullSrv" という名前のサーバーから構成をプルするように LCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="04667-111">The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv":</span></span>

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

<span data-ttu-id="04667-112">このスクリプトでは、**ConfigurationRepositoryWeb** ブロックにプル サーバーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="04667-112">In the script, the **ConfigurationRepositoryWeb** block defines the pull server.</span></span>
<span data-ttu-id="04667-113">**ServerURL** プロパティには、プル サーバー用のエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="04667-113">The **ServerURL** property specifies the endpoint for the pull server.</span></span>

<span data-ttu-id="04667-114">**RegistrationKey** プロパティは、プル サーバーのすべてのクライアント ノードとそのプル サーバーとの間で共有されるキーです。</span><span class="sxs-lookup"><span data-stu-id="04667-114">The **RegistrationKey** property is a shared key between all client nodes for a pull server and that pull server.</span></span>
<span data-ttu-id="04667-115">同じ値がプル サーバー上のファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="04667-115">The same value is stored in a file on the pull server.</span></span>

<span data-ttu-id="04667-116">**ConfigurationNames** プロパティは、クライアント ノード用の構成の名前を指定する配列です。</span><span class="sxs-lookup"><span data-stu-id="04667-116">The **ConfigurationNames** property is an array that specifies the names of the configurations intended for the client node.</span></span>
<span data-ttu-id="04667-117">プル サーバーでは、このクライアント ノードの構成 MOF ファイルに *ConfigurationNames*.mof という名前を指定する必要があります。ここで、*ConfigurationNames* はこのメタ構成に設定した **ConfigurationNames** プロパティの値と一致します。</span><span class="sxs-lookup"><span data-stu-id="04667-117">On the pull server, the configuration MOF file for this client node must be named *ConfigurationNames*.mof, where *ConfigurationNames* matches the value of the **ConfigurationNames** property you set in this metaconfiguration.</span></span>

><span data-ttu-id="04667-118">**注:** **ConfigurationNames** に複数の値を指定する場合、構成に **PartialConfiguration** ブロックも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04667-118">**Note:** If you specify more than one value in the **ConfigurationNames**, you must also specify **PartialConfiguration** blocks in your configuration.</span></span>
<span data-ttu-id="04667-119">部分構成の詳細については、「[PowerShell Desired State Configuration の部分構成](partialConfigs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04667-119">For information about partial configurations, see [PowerShell Desired State Configuration partial configurations](partialConfigs.md).</span></span>

<span data-ttu-id="04667-120">このスクリプトを実行すると、**PullClientConfigNames** という名前の新しい出力フォルダーが作成され、そこにメタ構成 MOF ファイルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="04667-120">After this script runs, it creates a new output folder named **PullClientConfigNames** and puts a metaconfiguration MOF file there.</span></span>
<span data-ttu-id="04667-121">この場合、メタ構成 MOF ファイルの名前は `localhost.meta.mof` になります。</span><span class="sxs-lookup"><span data-stu-id="04667-121">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="04667-122">構成を適用するには、**Path** をメタ構成 MOF ファイルの場所に設定して **Set-DscLocalConfigurationManager** コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="04667-122">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span>

```powershell
Set-DSCLocalConfigurationManager localhost –Path .\PullClientConfigNames –Verbose.
```

> <span data-ttu-id="04667-123">**注**: 登録キーは、Web プル サーバーでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="04667-123">**Note**: Registration keys work only with web pull servers.</span></span>
<span data-ttu-id="04667-124">SMB プル サーバーでは、引き続き **ConfigurationID** を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04667-124">You must still use **ConfigurationID** with an SMB pull server.</span></span>
<span data-ttu-id="04667-125">**ConfigurationID** を使用したプル サーバーの構成については、「[構成 ID を使用したプル クライアントのセットアップ](PullClientConfigNames.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04667-125">For information about configuring a pull server by using **ConfigurationID**, see [Setting up a pull client using configuration ID](PullClientConfigNames.md)</span></span>

## <a name="resource-and-report-servers"></a><span data-ttu-id="04667-126">リソースおよびレポート サーバー</span><span class="sxs-lookup"><span data-stu-id="04667-126">Resource and report servers</span></span>

<span data-ttu-id="04667-127">LCM 構成で **ConfigurationRepositoryWeb** ブロックまたは **ConfigurationRepositoryShare** ブロックのみを指定した場合 (前の例はこれに当たります)、プル クライアントは、指定されたサーバーからリソースをプルしますが、そのサーバーに対してレポートは送信しません。</span><span class="sxs-lookup"><span data-stu-id="04667-127">If you specify only a **ConfigurationRepositoryWeb** or **ConfigurationRepositoryShare** block in your LCM configuration (as in the previous example), the pull client will pull resources from the specified server, but it will not send reports to it.</span></span>
<span data-ttu-id="04667-128">構成、リソース、およびレポートについて単一のプル サーバーを使うことができますが、レポートをセットアップするために **ReportRepositoryWeb** ブロックを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04667-128">You can use a single pull server for configurations, resources, and reporting, but you have to create a **ReportRepositoryWeb** block to set up reporting.</span></span>
<span data-ttu-id="04667-129">次の例は、単一のプル サーバーに対して構成とリソースをプルし、レポート データを送信するようにクライアントを設定するメタ構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="04667-129">The following example shows a metaconfiguration that sets up a client to pull configurations and resources, and send reporting data, to a single pull server.</span></span>

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
        }
    }
}
PullClientConfigNames
```

<span data-ttu-id="04667-130">また、リソース用とレポート用にそれぞれ異なるプル サーバーを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="04667-130">You can also specify different pull servers for resources and reporting.</span></span>
<span data-ttu-id="04667-131">リソース サーバーを指定するには、**ResourceRepositoryWeb** (Web プル サーバーの場合) または **ResourceRepositoryShare** ブロック (SMB プル サーバーの場合) を使用します。</span><span class="sxs-lookup"><span data-stu-id="04667-131">To specify a resource server, you use either a **ResourceRepositoryWeb** (for a web pull server) or a **ResourceRepositoryShare** block (for an SMB pull server).</span></span>
<span data-ttu-id="04667-132">レポート サーバーを指定するには、**ReportRepositoryWeb** ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="04667-132">To specify a report server, you use a **ReportRepositoryWeb** block.</span></span>
<span data-ttu-id="04667-133">レポート サーバーを SMB サーバーにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="04667-133">A report server cannot be an SMB server.</span></span>
<span data-ttu-id="04667-134">次のメタ構成は、**CONTOSO-PullSrv** から構成を取得し、**CONTOSO-ResourceSrv** からリソースを取得し、**CONTOSO-ReportSrv** に状態レポートを送信するように、プル クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="04667-134">The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv**, and to send status reports to **CONTOSO-ReportSrv**:</span></span>

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

        ResourceRepositoryWeb CONTOSO-ResourceSrv
        {
            ServerURL = 'https://CONTOSO-ResourceSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = '30ef9bd8-9acf-4e01-8374-4dc35710fc90'
        }

        ReportServerWeb CONTOSO-ReportSrv
        {
            ServerURL = 'https://CONTOSO-ReportSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = '6b392c6a-818c-4b24-bf38-47124f1e2f14'
        }
    }
}
PullClientConfigNames
```

## <a name="see-also"></a><span data-ttu-id="04667-135">参照</span><span class="sxs-lookup"><span data-stu-id="04667-135">See Also</span></span>

* [<span data-ttu-id="04667-136">構成 ID を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="04667-136">Setting up a pull client with configuration ID</span></span>](PullClientConfigNames.md)
* [<span data-ttu-id="04667-137">DSC Web プル サーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="04667-137">Setting up a DSC web pull server</span></span>](pullServer.md)

