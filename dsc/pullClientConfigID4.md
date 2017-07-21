---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "PowerShell 4.0 での構成 ID を使用したプル クライアントのセットアップ"
ms.openlocfilehash: 19328018d276cddd0877869b0ec69c14c51e4b85
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="setting-up-a-pull-client-using-configuration-id-in-powershell-40"></a><span data-ttu-id="70862-103">PowerShell 4.0 での構成 ID を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="70862-103">Setting up a pull client using configuration ID in PowerShell 4.0</span></span>

><span data-ttu-id="70862-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="70862-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="70862-105">各ターゲット ノードに対し、プル モードを使用するように指示し、プル サーバーに接続して構成を取得するための URL を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70862-105">Each target node has to be told to use pull mode and given the URL where it can contact the pull server to get configurations.</span></span> <span data-ttu-id="70862-106">これを行うには、必要な情報を備えるようにローカル構成マネージャー (LCM) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70862-106">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="70862-107">LCM を構成するには、"メタ構成" と呼ばれる特殊な種類の構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="70862-107">To configure the LCM, you create a special type of configuration known as a "metaconfiguration".</span></span> <span data-ttu-id="70862-108">LCM の構成の詳細については、「[Windows PowerShell 4.0 Desired State Configuration のローカル構成マネージャー (LCM)](metaConfig4.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="70862-108">For more information about configuring the LCM, see [Windows PowerShell 4.0 Desired State Configuration Local Configuration Manager](metaConfig4.md)</span></span>

<span data-ttu-id="70862-109">次のスクリプトは、"PullServer" という名前のサーバーから構成をプルするように LCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="70862-109">The following script configures the LCM to pull configurations from a server named "PullServer":</span></span>

```powershell
Configuration SimpleMetaConfigurationForPull 
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
SimpleMetaConfigurationForPull -Output "."
```

<span data-ttu-id="70862-110">このスクリプトでは、**DownloadManagerCustomData** がプル サーバーの URL を渡し、(この例の場合) セキュリティ保護されていない接続を許可します。</span><span class="sxs-lookup"><span data-stu-id="70862-110">In the script, **DownloadManagerCustomData** passes the URL of the pull server and (for this example) allows an unsecured connection.</span></span> 

<span data-ttu-id="70862-111">このスクリプトを実行すると、**SimpleMetaConfigurationForPull** という名前の新しい出力フォルダーが作成され、そこにメタ構成 MOF ファイルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="70862-111">After this script runs, it creates a new output folder called **SimpleMetaConfigurationForPull** and puts a metaconfiguration MOF file there.</span></span>

<span data-ttu-id="70862-112">構成を適用するには、**ComputerName** ("localhost" を使用) と **Path** (ターゲット ノードの localhost.meta.mof ファイルの場所へのパス) のパラメーターを指定した **Set-DscLocalConfigurationManager** を使用します。</span><span class="sxs-lookup"><span data-stu-id="70862-112">To apply the configuration, use **Set-DscLocalConfigurationManager** with parameters for **ComputerName** (use “localhost”) and **Path** (the path to the location of the target node’s localhost.meta.mof file).</span></span> <span data-ttu-id="70862-113">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="70862-113">For example:</span></span> 
```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path . –Verbose.
```

## <a name="configuration-id"></a><span data-ttu-id="70862-114">構成 ID</span><span class="sxs-lookup"><span data-stu-id="70862-114">Configuration ID</span></span>
<span data-ttu-id="70862-115">このスクリプトは、LCM の **ConfigurationID** プロパティをこの目的で以前に作成した GUID に設定します (GUID を作成するには、**New-Guid** コマンドレットを使用します)。</span><span class="sxs-lookup"><span data-stu-id="70862-115">The script sets the **ConfigurationID** property of the LCM to a GUID that had been previously created for this purpose (you can create a GUID by using the **New-Guid** cmdlet).</span></span> <span data-ttu-id="70862-116">**ConfigurationID** は、LCM がプル サーバーで適切な構成を検索する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="70862-116">The **ConfigurationID** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="70862-117">プル サーバー上の構成 MOF ファイルは、`ConfigurationID.mof` という名前にする必要があります。ここで、*ConfigurationID* はターゲット ノードの LCM の **ConfigurationID** プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="70862-117">The configuration MOF file on the pull server must be named `ConfigurationID.mof`, where *ConfigurationID* is the value of the **ConfigurationID** property of the target node's LCM.</span></span>

## <a name="pulling-from-an-smb-server"></a><span data-ttu-id="70862-118">SMB サーバーからプルする</span><span class="sxs-lookup"><span data-stu-id="70862-118">Pulling from an SMB server</span></span>

<span data-ttu-id="70862-119">プル サーバーを、Web サービスではなく SMB ファイル共有としてセットアップするには、**WebDownLoadManager** ではなく **DscFileDownloadManager** を指定します。</span><span class="sxs-lookup"><span data-stu-id="70862-119">If the pull server is set up as an SMB file share, rather than a web service, you specify the **DscFileDownloadManager** rather than the **WebDownLoadManager**.</span></span>
<span data-ttu-id="70862-120">**DscFileDownloadManager** は、**ServerUrl** の代わりに **SourcePath** プロパティを取ります。</span><span class="sxs-lookup"><span data-stu-id="70862-120">The **DscFileDownloadManager** takes a **SourcePath** property instead of **ServerUrl**.</span></span> <span data-ttu-id="70862-121">次のスクリプトは、"CONTOSO-SERVER" という名前のサーバーの "SmbDscShare" という名前の SMB 共有から構成をプルするように LCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="70862-121">The following script configures the LCM to pull configurations from an SMB share named "SmbDscShare" on a server named "CONTOSO-SERVER":</span></span>

```powershell
Configuration SimpleMetaConfigurationForPull 
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
SimpleMetaConfigurationForPull -Output "."
```

## <a name="see-also"></a><span data-ttu-id="70862-122">参照</span><span class="sxs-lookup"><span data-stu-id="70862-122">See Also</span></span>

- [<span data-ttu-id="70862-123">DSC Web プル サーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="70862-123">Setting up a DSC web pull server</span></span>](pullServer.md)
- [<span data-ttu-id="70862-124">DSC SMB プル サーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="70862-124">Setting up a DSC SMB pull server</span></span>](pullServerSMB.md)

