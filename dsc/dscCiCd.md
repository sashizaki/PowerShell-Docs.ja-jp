---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC を使用した継続的インテグレーションと継続的配置パイプラインの構築
ms.openlocfilehash: faeef5022cbd984cab0620b69db19de8b84cca0e
ms.sourcegitcommit: 68093cc12a7a22c53d11ce7d33c18622921a0dd1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36940346"
---
# <a name="building-a-continuous-integration-and-continuous-deployment-pipeline-with-dsc"></a><span data-ttu-id="b1f86-103">DSC を使用した継続的インテグレーションと継続的配置パイプラインの構築</span><span class="sxs-lookup"><span data-stu-id="b1f86-103">Building a Continuous Integration and Continuous Deployment pipeline with DSC</span></span>

<span data-ttu-id="b1f86-104">この例では、PowerShell、DSC、Pester、および Visual Studio Team Foundation Server (TFS) を使用して継続的インテグレーション/継続的配置 (CI/CD) パイプラインを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-104">This example demonstrates how to build a Continuous Integration/Continuous Deployment (CI/CD) pipeline by using PowerShell, DSC, Pester, and Visual Studio Team Foundation Server (TFS).</span></span>

<span data-ttu-id="b1f86-105">パイプラインを構築して構成したら、それを使用してDNS サーバーおよび関連付けられたホスト レコードを完全に配置、構成、テストできます。</span><span class="sxs-lookup"><span data-stu-id="b1f86-105">After the pipeline is built and configured, you can use it to fully deploy, configure and test a DNS server and associated host records.</span></span>
<span data-ttu-id="b1f86-106">このプロセスでは、開発環境で使用されるパイプラインの最初の部分をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="b1f86-106">This process simulates the first part of a pipeline that would be used in a development environment.</span></span>

<span data-ttu-id="b1f86-107">自動の CI/CD パイプラインでは、ソフトウェアをより早く、より確実に更新できるため、すべてのコードをテストして、コードの最新のビルドを常に使用可能な状態にします。</span><span class="sxs-lookup"><span data-stu-id="b1f86-107">An automated CI/CD pipeline helps you update software faster and more reliably, ensuring that all code is tested, and that a current build of your code is available at all times.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b1f86-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="b1f86-108">Prerequisites</span></span>

<span data-ttu-id="b1f86-109">この例を使用するには、以下について理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1f86-109">To use this example, you should be familiar with the following:</span></span>

- <span data-ttu-id="b1f86-110">CI/CD の概念。</span><span class="sxs-lookup"><span data-stu-id="b1f86-110">CI-CD concepts.</span></span> <span data-ttu-id="b1f86-111">『[The Release Pipeline Model (リリース パイプライン モデル)](http://aka.ms/thereleasepipelinemodelpdf)』が参考資料として役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b1f86-111">A good reference can be found at [The Release Pipeline Model](http://aka.ms/thereleasepipelinemodelpdf).</span></span>
- <span data-ttu-id="b1f86-112">[Git](https://git-scm.com/) ソース管理</span><span class="sxs-lookup"><span data-stu-id="b1f86-112">[Git](https://git-scm.com/) source control</span></span>
- <span data-ttu-id="b1f86-113">[Pester](https://github.com/pester/Pester) テスト フレームワーク</span><span class="sxs-lookup"><span data-stu-id="b1f86-113">The [Pester](https://github.com/pester/Pester) testing framework</span></span>
- [<span data-ttu-id="b1f86-114">Team Foundation Server</span><span class="sxs-lookup"><span data-stu-id="b1f86-114">Team Foundation Server</span></span>](https://www.visualstudio.com/tfs/)

## <a name="what-you-will-need"></a><span data-ttu-id="b1f86-115">必要なもの</span><span class="sxs-lookup"><span data-stu-id="b1f86-115">What you will need</span></span>

<span data-ttu-id="b1f86-116">この例をビルドして実行するには、コンピューター複数台と仮想マシン、またはそのいずれかを含む環境が必要です。</span><span class="sxs-lookup"><span data-stu-id="b1f86-116">To build and run this example, you will need an environment with several computers and/or virtual machines.</span></span>

### <a name="client"></a><span data-ttu-id="b1f86-117">クライアント</span><span class="sxs-lookup"><span data-stu-id="b1f86-117">Client</span></span>

<span data-ttu-id="b1f86-118">この例を設定して実行する、すべての作業を行うコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="b1f86-118">This is the computer where you'll do all of the work setting up and running the example.</span></span>

<span data-ttu-id="b1f86-119">クライアント コンピューターは Windows コンピューターで、以下がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1f86-119">The client computer must be a Windows computer with the following installed:</span></span>

- [<span data-ttu-id="b1f86-120">Git</span><span class="sxs-lookup"><span data-stu-id="b1f86-120">Git</span></span>](https://git-scm.com/)
- <span data-ttu-id="b1f86-121">https://github.com/PowerShell/Demo_CI から複製されたローカル Git リポジトリ</span><span class="sxs-lookup"><span data-stu-id="b1f86-121">a local git repo cloned from https://github.com/PowerShell/Demo_CI</span></span>
- <span data-ttu-id="b1f86-122">[Visual Studio Code](https://code.visualstudio.com/) などのテキスト エディター</span><span class="sxs-lookup"><span data-stu-id="b1f86-122">a text editor, such as [Visual Studio Code](https://code.visualstudio.com/)</span></span>

### <a name="tfssrv1"></a><span data-ttu-id="b1f86-123">TFSSrv1</span><span class="sxs-lookup"><span data-stu-id="b1f86-123">TFSSrv1</span></span>

<span data-ttu-id="b1f86-124">TFS サーバーをホストするコンピューター。ビルドを定義してリリースします。</span><span class="sxs-lookup"><span data-stu-id="b1f86-124">The computer that hosts the TFS server where you will define your build and release.</span></span>
<span data-ttu-id="b1f86-125">このコンピューターには、[Team Foundation Server 2017](https://www.visualstudio.com/tfs/) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1f86-125">This computer must have [Team Foundation Server 2017](https://www.visualstudio.com/tfs/) installed.</span></span>

### <a name="buildagent"></a><span data-ttu-id="b1f86-126">BuildAgent</span><span class="sxs-lookup"><span data-stu-id="b1f86-126">BuildAgent</span></span>

<span data-ttu-id="b1f86-127">プロジェクトをビルドする Windows ビルド エージェントを実行するコンピューター。</span><span class="sxs-lookup"><span data-stu-id="b1f86-127">The computer that runs the Windows build agent that builds the project.</span></span>
<span data-ttu-id="b1f86-128">このコンピューターには、Windows ビルド エージェントがインストールされ実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1f86-128">This computer must have a Windows build agent installed and running.</span></span>
<span data-ttu-id="b1f86-129">Windows ビルド エージェントをインストールし実行する方法については、「[Deploy an agent on Windows (Windows 上にエージェントを展開する)](https://www.visualstudio.com/en-us/docs/build/actions/agents/v2-windows)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b1f86-129">See [Deploy an agent on Windows](https://www.visualstudio.com/en-us/docs/build/actions/agents/v2-windows) for instructions on how to install and run a Windows build agent.</span></span>

<span data-ttu-id="b1f86-130">また、このコンピューターには `xDnsServer` と `xNetworking` の両方の DSC モジュールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1f86-130">You also need to install both the `xDnsServer` and `xNetworking` DSC modules on this computer.</span></span>

### <a name="testagent1"></a><span data-ttu-id="b1f86-131">TestAgent1</span><span class="sxs-lookup"><span data-stu-id="b1f86-131">TestAgent1</span></span>

<span data-ttu-id="b1f86-132">この例において、DSC 構成で DNS サーバーとして構成されるコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="b1f86-132">This is the computer that is configured as a DNS server by the DSC configuration in this example.</span></span>
<span data-ttu-id="b1f86-133">このコンピューターでは、[Windows Server 2016](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2016) が実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1f86-133">The computer must be running [Windows Server 2016](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2016).</span></span>

### <a name="testagent2"></a><span data-ttu-id="b1f86-134">TestAgent2</span><span class="sxs-lookup"><span data-stu-id="b1f86-134">TestAgent2</span></span>

<span data-ttu-id="b1f86-135">この例で構成する Web サイトをホストするコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="b1f86-135">This is the computer that hosts the website this example configures.</span></span>
<span data-ttu-id="b1f86-136">このコンピューターでは、[Windows Server 2016](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2016) が実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1f86-136">The computer must be running [Windows Server 2016](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2016).</span></span>

## <a name="add-the-code-to-tfs"></a><span data-ttu-id="b1f86-137">TFS にコードを追加する</span><span class="sxs-lookup"><span data-stu-id="b1f86-137">Add the code to TFS</span></span>

<span data-ttu-id="b1f86-138">まず TFS で Git リポジトリを作成し、クライアント コンピューターのローカル リポジトリからコードをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b1f86-138">We'll start out by creating a Git repository in TFS, and importing the code from your local repository on the client computer.</span></span>
<span data-ttu-id="b1f86-139">クライアント コンピューターに Demo_CI リポジトリを複製済みでない場合は、この時点で次の git コマンドを実行してください。</span><span class="sxs-lookup"><span data-stu-id="b1f86-139">If you have not already cloned the Demo_CI repository to your client computer, do so now by running the following git command:</span></span>

`git clone https://github.com/PowerShell/Demo_CI`

1. <span data-ttu-id="b1f86-140">クライアント コンピューターで、Web ブラウザーから TFS サーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-140">On your client computer, navigate to your TFS server in a web browser.</span></span>
1. <span data-ttu-id="b1f86-141">TFS で、[新しいチーム プロジェクトを作成](https://www.visualstudio.com/en-us/docs/setup-admin/create-team-project)し、Demo_CI という名前にします。</span><span class="sxs-lookup"><span data-stu-id="b1f86-141">In TFS, [Create a new team project](https://www.visualstudio.com/en-us/docs/setup-admin/create-team-project) named Demo_CI.</span></span>

   <span data-ttu-id="b1f86-142">**バージョン コントロール** が **Git** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-142">Make sure that **Version control** is set to **Git**.</span></span>
1. <span data-ttu-id="b1f86-143">クライアント コンピューターで、次のコマンドを使用して、いま TFS で作成したリポジトリにリモートを追加します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-143">On your client computer, add a remote to the repository you just created in TFS with the following command:</span></span>

   `git remote add tfs <YourTFSRepoURL>`

   <span data-ttu-id="b1f86-144">ここで `<YourTFSRepoURL>` は、前の手順で作成した TFS リポジトリのクローン URL です。</span><span class="sxs-lookup"><span data-stu-id="b1f86-144">Where `<YourTFSRepoURL>` is the clone URL to the TFS repository you created in the previous step.</span></span>

   <span data-ttu-id="b1f86-145">この URL の場所がわからない場合は、「[Clone an existing Git repo (既存の Git リポジトリを複製する)](https://www.visualstudio.com/en-us/docs/git/tutorial/clone)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b1f86-145">If you don't know where to find this URL, see [Clone an existing Git repo](https://www.visualstudio.com/en-us/docs/git/tutorial/clone).</span></span>
1. <span data-ttu-id="b1f86-146">次のコマンドで、ローカル リポジトリから TFS リポジトリにコードをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="b1f86-146">Push the code from your local repository to your TFS repository with the following command:</span></span>

   `git push tfs --all`
1. <span data-ttu-id="b1f86-147">TFS リポジトリが Demo_CI のコードで設定されます。</span><span class="sxs-lookup"><span data-stu-id="b1f86-147">The TFS repository will be populated with the Demo_CI code.</span></span>

> [!NOTE]
> <span data-ttu-id="b1f86-148">この例では Git リポジトリの `ci-cd-example` ブランチのコードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="b1f86-148">This example uses the code in the `ci-cd-example` branch of the Git repo.</span></span>
> <span data-ttu-id="b1f86-149">このブランチを TFS プロジェクトの既定ブランチとし、また作成する CI/CD トリガーに必ず指定してください。</span><span class="sxs-lookup"><span data-stu-id="b1f86-149">Be sure to specify this branch as the default branch in your TFS project, and for the CI/CD triggers you create.</span></span>

## <a name="understanding-the-code"></a><span data-ttu-id="b1f86-150">コードを理解する</span><span class="sxs-lookup"><span data-stu-id="b1f86-150">Understanding the code</span></span>

<span data-ttu-id="b1f86-151">ビルドおよび配置パイプラインを作成する前に、コードの一部を見て何が起きているかを理解しましょう。</span><span class="sxs-lookup"><span data-stu-id="b1f86-151">Before we create the build and deployment pipelines, let's look at some of the code to understand what is going on.</span></span>
<span data-ttu-id="b1f86-152">クライアント コンピューターで、使い慣れたテキスト エディターを開き、Demo_CI Git リポジトリのルートに移動します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-152">On your client computer, open your favorite text editor and navigate to the root of your Demo_CI Git repository.</span></span>

### <a name="the-dsc-configuration"></a><span data-ttu-id="b1f86-153">DSC 構成</span><span class="sxs-lookup"><span data-stu-id="b1f86-153">The DSC configuration</span></span>

<span data-ttu-id="b1f86-154">ファイル `DNSServer.ps1` を開きます (ローカルの Demo_CI リポジトリのルート `./InfraDNS/Configs/DNSServer.ps1` から)。</span><span class="sxs-lookup"><span data-stu-id="b1f86-154">Open the file `DNSServer.ps1` (from the root of the local Demo_CI repository, `./InfraDNS/Configs/DNSServer.ps1`).</span></span>

<span data-ttu-id="b1f86-155">このファイルには、DNS サーバーをセットアップする DSC 構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1f86-155">This file contains the DSC configuration that sets up the DNS server.</span></span> <span data-ttu-id="b1f86-156">その全体は以下の通りです。</span><span class="sxs-lookup"><span data-stu-id="b1f86-156">Here it is in its entirety:</span></span>

```powershell
configuration DNSServer
{
    Import-DscResource -module 'xDnsServer','xNetworking', 'PSDesiredStateConfiguration'

    Node $AllNodes.Where{$_.Role -eq 'DNSServer'}.NodeName
    {
        WindowsFeature DNS
        {
            Ensure  = 'Present'
            Name    = 'DNS'
        }

        xDnsServerPrimaryZone $Node.zone
        {
            Ensure    = 'Present'
            Name      = $Node.Zone
            DependsOn = '[WindowsFeature]DNS'
        }

        foreach ($ARec in $Node.ARecords.keys) {
            xDnsRecord $ARec
            {
                Ensure    = 'Present'
                Name      = $ARec
                Zone      = $Node.Zone
                Type      = 'ARecord'
                Target    = $Node.ARecords[$ARec]
                DependsOn = '[WindowsFeature]DNS'
            }
        }

        foreach ($CName in $Node.CNameRecords.keys) {
            xDnsRecord $CName
            {
                Ensure    = 'Present'
                Name      = $CName
                Zone      = $Node.Zone
                Type      = 'CName'
                Target    = $Node.CNameRecords[$CName]
                DependsOn = '[WindowsFeature]DNS'
            }
        }
    }
}
```

<span data-ttu-id="b1f86-157">`Node` ステートメントに着目しましょう。</span><span class="sxs-lookup"><span data-stu-id="b1f86-157">Notice the `Node` statement:</span></span>

```powershell
Node $AllNodes.Where{$_.Role -eq 'DNSServer'}.NodeName
```

<span data-ttu-id="b1f86-158">これは、`DevEnv.ps1` スクリプトによって作成された[構成データ](configData.md)内で、`DNSServer` の役割を持つものとして定義されたすべてのノードを検索します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-158">This finds any nodes that were defined as having a role of `DNSServer` in the [configuration data](configData.md), which is created by the `DevEnv.ps1` script.</span></span>

<span data-ttu-id="b1f86-159">`Where` メソッドの詳細については、「[about_arrays](/powershell/reference/3.0/Microsoft.PowerShell.Core/About/about_Arrays.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f86-159">You can read more about the `Where` method in [about_arrays](/powershell/reference/3.0/Microsoft.PowerShell.Core/About/about_Arrays.md)</span></span>

<span data-ttu-id="b1f86-160">CI を行う場合、ノード情報は環境によって変わることがあるため、ノードの定義に構成データを使用することは重要です。構成データを使用すれば、構成コードを変更することなく、ノード情報を簡単に変更できます。</span><span class="sxs-lookup"><span data-stu-id="b1f86-160">Using configuration data to define nodes is important when doing CI because node information will likely change between environments, and using configuration data allows you to easily make changes to node information without changing the configuration code.</span></span>

<span data-ttu-id="b1f86-161">最初のリソース ブロックでは、構成で [WindowsFeature](windowsFeatureResource.md) を呼び出し、DNS 機能が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-161">In the first resource block, the configuration calls the [WindowsFeature](windowsFeatureResource.md) to ensure that the DNS feature is enabled.</span></span>
<span data-ttu-id="b1f86-162">それに続くリソース ブロックでは、[xDnsServer](https://github.com/PowerShell/xDnsServer) モジュールからリソースを呼び出し、プライマリ ゾーンと DNS レコードを構成します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-162">The resource blocks that follow call resources from the [xDnsServer](https://github.com/PowerShell/xDnsServer) module to configure the primary zone and DNS records.</span></span>

<span data-ttu-id="b1f86-163">2 つの `xDnsRecord` ブロックが、構成データの配列を反復処理する `foreach` ループ内にラップされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b1f86-163">Notice that the two `xDnsRecord` blocks are wrapped in `foreach` loops that iterate through arrays in the configuration data.</span></span>
<span data-ttu-id="b1f86-164">繰り返しますが、構成データは `DevEnv.ps1` スクリプトで作成されます。これは次に見ていきます。</span><span class="sxs-lookup"><span data-stu-id="b1f86-164">Again, the configuration data is created by the `DevEnv.ps1` script, which we'll look at next.</span></span>

### <a name="configuration-data"></a><span data-ttu-id="b1f86-165">構成データ</span><span class="sxs-lookup"><span data-stu-id="b1f86-165">Configuration data</span></span>

<span data-ttu-id="b1f86-166">`DevEnv.ps1` ファイル (ローカルの Demo_CI リポジトリのルート `./InfraDNS/DevEnv.ps1` から) は、ハッシュ テーブル内の環境固有の構成データを指定し、そのハッシュ テーブルを `New-DscConfigurationDataDocument` 関数の呼び出しに渡します。これは `DscPipelineTools.psm`(`./Assets/DscPipelineTools/DscPipelineTools.psm1`) で定義されています。</span><span class="sxs-lookup"><span data-stu-id="b1f86-166">The `DevEnv.ps1` file (from the root of the local Demo_CI repository, `./InfraDNS/DevEnv.ps1`) specifies the environment-specific configuration data in a hashtable, and then passes that hashtable to a call to the `New-DscConfigurationDataDocument` function, which is defined in `DscPipelineTools.psm` (`./Assets/DscPipelineTools/DscPipelineTools.psm1`).</span></span>

<span data-ttu-id="b1f86-167">`DevEnv.ps1` ファイルは以下の通りです。</span><span class="sxs-lookup"><span data-stu-id="b1f86-167">The `DevEnv.ps1` file:</span></span>

```powershell
param(
    [parameter(Mandatory=$true)]
    [string]
    $OutputPath
)

Import-Module $PSScriptRoot\..\Assets\DscPipelineTools\DscPipelineTools.psd1 -Force

# Define Unit Test Environment
$DevEnvironment = @{
    Name                        = 'DevEnv';
    Roles = @(
        @{  Role                = 'DNSServer';
            VMName              = 'TestAgent1';
            Zone                = 'Contoso.com';
            ARecords            = @{'TFSSrv1'= '10.0.0.10';'Client'='10.0.0.15';'BuildAgent'='10.0.0.30';'TestAgent1'='10.0.0.40';'TestAgent2'='10.0.0.50'};
            CNameRecords        = @{'DNS' = 'TestAgent1.contoso.com'};
        }
    )
}

Return New-DscConfigurationDataDocument -RawEnvData $DevEnvironment -OutputPath $OutputPath
```

<span data-ttu-id="b1f86-168">`New-DscConfigurationDataDocument` 関数 (`\Assets\DscPipelineTools\DscPipelineTools.psm1` で定義されている) は、`RawEnvData` パラメーターおよび `OtherEnvData` パラメーターとして渡されるハッシュ テーブル (ノードのデータ) および配列 (ノード以外のデータ) から、プログラムで構成データ ドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-168">The `New-DscConfigurationDataDocument` function (defined in `\Assets\DscPipelineTools\DscPipelineTools.psm1`) programmatically creates a configuration data document from the hashtable (node data) and array (non-node data) that are passed as the `RawEnvData` and `OtherEnvData` parameters.</span></span>

<span data-ttu-id="b1f86-169">ここでは、`RawEnvData` パラメーターのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-169">In our case, only the `RawEnvData` parameter is used.</span></span>

### <a name="the-psake-build-script"></a><span data-ttu-id="b1f86-170">psake ビルド スクリプト</span><span class="sxs-lookup"><span data-stu-id="b1f86-170">The psake build script</span></span>

<span data-ttu-id="b1f86-171">`Build.ps1` (Demo_CI リポジトリのルート `./InfraDNS/Build.ps1` から) で定義されている [psake](https://github.com/psake/psake) ビルド スクリプトでは、ビルドの一部となるタスクを定義します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-171">The [psake](https://github.com/psake/psake) build script defined in `Build.ps1` (from the root of the Demo_CI repository, `./InfraDNS/Build.ps1`) defines tasks that are part of the build.</span></span>
<span data-ttu-id="b1f86-172">また、各タスクが依存する他のタスクも定義します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-172">It also defines which other tasks each task depends on.</span></span>
<span data-ttu-id="b1f86-173">psake スクリプトは、呼び出されると、指定されたタスク (またはタスクが指定されていない場合は `Default` という名前のタスク) が実行され、すべての依存関係も実行されること (これは再帰的で、依存関係の依存関係を実行する) を確認します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-173">When invoked, the psake script ensures that the specified task (or the task named `Default` if none is specified) runs, and that all dependencies also run (this is recursive, so that dependencies of dependencies run, and so on).</span></span>

<span data-ttu-id="b1f86-174">この例では、`Default` タスクを以下のように定義します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-174">In this example, the `Default` task is defined as:</span></span>

```powershell
Task Default -depends UnitTests
```

<span data-ttu-id="b1f86-175">`Default` タスクにはそれ自体の実装はなく、`CompileConfigs` タスクに依存しています。</span><span class="sxs-lookup"><span data-stu-id="b1f86-175">The `Default` task has no implementation itself, but has a dependency on the `CompileConfigs` task.</span></span>
<span data-ttu-id="b1f86-176">その結果、タスクの依存関係が連鎖することで、ビルド スクリプトのすべてのタスクが確実に実行されます。</span><span class="sxs-lookup"><span data-stu-id="b1f86-176">The resulting chain of task dependencies ensures that all tasks in the build script are run.</span></span>

<span data-ttu-id="b1f86-177">この例では、psake スクリプトは、`Initiate.ps1` ファイル (Demo_CI リポジトリのルートにある) 内の `Invoke-PSake` の呼び出しによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b1f86-177">In this example, the psake script is invoked by a call to `Invoke-PSake` in the `Initiate.ps1` file (located at the root of the Demo_CI repository):</span></span>

```powershell
param(
    [parameter()]
    [ValidateSet('Build','Deploy')]
    [string]
    $fileName
)

#$Error.Clear()

Invoke-PSake $PSScriptRoot\InfraDNS\$fileName.ps1

<#if($Error.count)
{
    Throw "$fileName script failed. Check logs for failure details."
}
#>
```

<span data-ttu-id="b1f86-178">TFS でこの例のビルド定義を作成する場合、psake スクリプト ファイルをこのスクリプトの `fileName` パラメーターとして提供します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-178">When we create the build definition for our example in TFS, we will supply our psake script file as the `fileName` parameter for this script.</span></span>

<span data-ttu-id="b1f86-179">ビルド スクリプトでは、次のタスクを定義します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-179">The build script defines the following tasks:</span></span>

#### <a name="generateenvironmentfiles"></a><span data-ttu-id="b1f86-180">GenerateEnvironmentFiles</span><span class="sxs-lookup"><span data-stu-id="b1f86-180">GenerateEnvironmentFiles</span></span>

<span data-ttu-id="b1f86-181">`DevEnv.ps1` を実行し、構成データ ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-181">Runs `DevEnv.ps1`, which generates the configuration data file.</span></span>

#### <a name="installmodules"></a><span data-ttu-id="b1f86-182">InstallModules</span><span class="sxs-lookup"><span data-stu-id="b1f86-182">InstallModules</span></span>

<span data-ttu-id="b1f86-183">`DNSServer.ps1` 構成に必要なモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b1f86-183">Installs the modules required by the configuration `DNSServer.ps1`.</span></span>

#### <a name="scriptanalysis"></a><span data-ttu-id="b1f86-184">ScriptAnalysis</span><span class="sxs-lookup"><span data-stu-id="b1f86-184">ScriptAnalysis</span></span>

<span data-ttu-id="b1f86-185">[PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-185">Calls the [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer).</span></span>

#### <a name="unittests"></a><span data-ttu-id="b1f86-186">UnitTests</span><span class="sxs-lookup"><span data-stu-id="b1f86-186">UnitTests</span></span>

<span data-ttu-id="b1f86-187">[Pester](https://github.com/pester/Pester/wiki) 単体テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-187">Runs the [Pester](https://github.com/pester/Pester/wiki) unit tests.</span></span>

#### <a name="compileconfigs"></a><span data-ttu-id="b1f86-188">CompileConfigs</span><span class="sxs-lookup"><span data-stu-id="b1f86-188">CompileConfigs</span></span>

<span data-ttu-id="b1f86-189">`GenerateEnvironmentFiles` タスクによって生成された構成データを使用して、構成 (`DNSServer.ps1`) をコンパイルして MOF ファイルにします。</span><span class="sxs-lookup"><span data-stu-id="b1f86-189">Compiles the configuration (`DNSServer.ps1`) into a MOF file, using the configuration data generated by the `GenerateEnvironmentFiles` task.</span></span>

#### <a name="clean"></a><span data-ttu-id="b1f86-190">Clean</span><span class="sxs-lookup"><span data-stu-id="b1f86-190">Clean</span></span>

<span data-ttu-id="b1f86-191">例に使用するフォルダーを作成し、以前の実行によるテスト結果、構成データ ファイル、およびモジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-191">Creates the folders used for the example, and removes any test results, configuration data files, and modules from previous runs.</span></span>

### <a name="the-psake-deploy-script"></a><span data-ttu-id="b1f86-192">psake 配置スクリプト</span><span class="sxs-lookup"><span data-stu-id="b1f86-192">The psake deploy script</span></span>

<span data-ttu-id="b1f86-193">`Deploy.ps1` (Demo_CI リポジトリのルート `./InfraDNS/Deploy.ps1` から) で定義されている [psake](https://github.com/psake/psake) 配置スクリプトでは、構成を配置して実行するタスクを定義します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-193">The [psake](https://github.com/psake/psake) deployment script defined in `Deploy.ps1` (from the root of the Demo_CI repository, `./InfraDNS/Deploy.ps1`) defines tasks that deploy and run the configuration.</span></span>

<span data-ttu-id="b1f86-194">`Deploy.ps1` では以下のタスクを定義します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-194">`Deploy.ps1` defines the following tasks:</span></span>

#### <a name="deploymodules"></a><span data-ttu-id="b1f86-195">DeployModules</span><span class="sxs-lookup"><span data-stu-id="b1f86-195">DeployModules</span></span>

<span data-ttu-id="b1f86-196">`TestAgent1` で PowerShell セッションを開始し、構成に必要な DSC リソースを含むモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b1f86-196">Starts a PowerShell session on `TestAgent1` and installs the modules containing the DSC resources required for the configuration.</span></span>

#### <a name="deployconfigs"></a><span data-ttu-id="b1f86-197">DeployConfigs</span><span class="sxs-lookup"><span data-stu-id="b1f86-197">DeployConfigs</span></span>

<span data-ttu-id="b1f86-198">[Start-DscConfiguration](/reference/5.1/PSDesiredStateConfiguration/Start-DscConfiguration.md) コマンドレットを呼び出して、`TestAgent1` で構成を実行します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-198">Calls the [Start-DscConfiguration](/reference/5.1/PSDesiredStateConfiguration/Start-DscConfiguration.md) cmdlet to run the configuration on `TestAgent1`.</span></span>

#### <a name="integrationtests"></a><span data-ttu-id="b1f86-199">IntegrationTests</span><span class="sxs-lookup"><span data-stu-id="b1f86-199">IntegrationTests</span></span>

<span data-ttu-id="b1f86-200">[Pester](https://github.com/pester/Pester/wiki) 統合テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-200">Runs the [Pester](https://github.com/pester/Pester/wiki) integration tests.</span></span>

#### <a name="acceptancetests"></a><span data-ttu-id="b1f86-201">AcceptanceTests</span><span class="sxs-lookup"><span data-stu-id="b1f86-201">AcceptanceTests</span></span>

<span data-ttu-id="b1f86-202">[Pester](https://github.com/pester/Pester/wiki) 受け入れテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-202">Runs the [Pester](https://github.com/pester/Pester/wiki) acceptance tests.</span></span>

#### <a name="clean"></a><span data-ttu-id="b1f86-203">Clean</span><span class="sxs-lookup"><span data-stu-id="b1f86-203">Clean</span></span>

<span data-ttu-id="b1f86-204">以前の実行でインストールされたすべてのモジュールを削除し、テスト結果フォルダーが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-204">Removes any modules installed in previous runs, and ensures that the test result folder exists.</span></span>

### <a name="test-scripts"></a><span data-ttu-id="b1f86-205">テスト スクリプト</span><span class="sxs-lookup"><span data-stu-id="b1f86-205">Test scripts</span></span>

<span data-ttu-id="b1f86-206">受け入れテスト、統合テスト、および単体テストは、`Tests` フォルダー (Demo_CI リポジトリのルート `./InfraDNS/Tests` から) 内のスクリプトで定義されており、それぞれのフォルダーにある `DNSServer.tests.ps1` という名前のファイル内にあります。</span><span class="sxs-lookup"><span data-stu-id="b1f86-206">Acceptance, Integration, and Unit tests are defined in scripts in the `Tests` folder (from the root of the Demo_CI repository, `./InfraDNS/Tests`), each in files named `DNSServer.tests.ps1` in their respective folders.</span></span>

<span data-ttu-id="b1f86-207">テスト スクリプトは [Pester](https://github.com/pester/Pester/wiki) 構文および [PoshSpec](https://github.com/Ticketmaster/poshspec/wiki/Introduction) 構文を使用しています。</span><span class="sxs-lookup"><span data-stu-id="b1f86-207">The test scripts use [Pester](https://github.com/pester/Pester/wiki) and [PoshSpec](https://github.com/Ticketmaster/poshspec/wiki/Introduction) syntax.</span></span>

#### <a name="unit-tests"></a><span data-ttu-id="b1f86-208">単体テスト</span><span class="sxs-lookup"><span data-stu-id="b1f86-208">Unit tests</span></span>

<span data-ttu-id="b1f86-209">単体テストでは、DSC 構成自体をテストして、構成が実行時に期待通りに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-209">The unit tests test the DSC configurations themselves to ensure that the configurations will do what is expected when they run.</span></span>
<span data-ttu-id="b1f86-210">単体テスト スクリプトは [Pester](https://github.com/pester/Pester/wiki) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="b1f86-210">The unit test script uses [Pester](https://github.com/pester/Pester/wiki).</span></span>

#### <a name="integration-tests"></a><span data-ttu-id="b1f86-211">統合テスト</span><span class="sxs-lookup"><span data-stu-id="b1f86-211">Integration tests</span></span>

<span data-ttu-id="b1f86-212">統合テストでは、システムの構成をテストして、他のコンポーネントと統合したときにシステムが期待通りに構成されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-212">The integration tests test the configuration of the system to ensure that when integrated with other components, the system is configured as expected.</span></span> <span data-ttu-id="b1f86-213">これらのテストは、DSC で構成した後、ターゲット ノードで実行します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-213">These tests run on the target node after it has been configured with DSC.</span></span>
<span data-ttu-id="b1f86-214">統合テスト スクリプトは [Pester](https://github.com/pester/Pester/wiki) 構文と [PoshSpec](https://github.com/Ticketmaster/poshspec/wiki/Introduction) 構文を組み合わせて使用しています。</span><span class="sxs-lookup"><span data-stu-id="b1f86-214">The integration test script uses a mixture of [Pester](https://github.com/pester/Pester/wiki) and [PoshSpec](https://github.com/Ticketmaster/poshspec/wiki/Introduction) syntax.</span></span>

#### <a name="acceptance-tests"></a><span data-ttu-id="b1f86-215">受け入れテスト</span><span class="sxs-lookup"><span data-stu-id="b1f86-215">Acceptance tests</span></span>

<span data-ttu-id="b1f86-216">受け入れテストではシステムをテストして、期待通りに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-216">Acceptance tests test the system to ensure that it behaves as expected.</span></span>
<span data-ttu-id="b1f86-217">たとえば、Web ページにクエリが実行されたときに、適切な情報が返されるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="b1f86-217">For example, it tests to ensure a web page returns the right information when queried.</span></span>
<span data-ttu-id="b1f86-218">実際のシナリオをテストするために、これらのテストはターゲット ノードからリモートで実行します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-218">These tests run remotely from the target node in order to test real world scenarios.</span></span>
<span data-ttu-id="b1f86-219">統合テスト スクリプトは [Pester](https://github.com/pester/Pester/wiki) 構文と [PoshSpec](https://github.com/Ticketmaster/poshspec/wiki/Introduction) 構文を組み合わせて使用しています。</span><span class="sxs-lookup"><span data-stu-id="b1f86-219">The integration test script uses a mixture of [Pester](https://github.com/pester/Pester/wiki) and [PoshSpec](https://github.com/Ticketmaster/poshspec/wiki/Introduction) syntax.</span></span>

## <a name="define-the-build"></a><span data-ttu-id="b1f86-220">ビルドを定義する</span><span class="sxs-lookup"><span data-stu-id="b1f86-220">Define the build</span></span>

<span data-ttu-id="b1f86-221">コードを TFS にアップロードして内容を確認したので、ビルドを定義しましょう。</span><span class="sxs-lookup"><span data-stu-id="b1f86-221">Now that we've uploaded our code to TFS and looked at what it does, let's define our build.</span></span>

<span data-ttu-id="b1f86-222">ここでは、ビルドに追加するビルド ステップのみを説明します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-222">Here, we'll cover only the build steps that you'll add to the build.</span></span> <span data-ttu-id="b1f86-223">TFS でビルド定義を作成する方法の手順については、[ビルド定義の作成とキュー](https://www.visualstudio.com/en-us/docs/build/define/create)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b1f86-223">For instructions on how to create a build definition in TFS, see [Create and queue a build definition](https://www.visualstudio.com/en-us/docs/build/define/create).</span></span>

<span data-ttu-id="b1f86-224">新しいビルド定義を作成して (**空**のテンプレートを選択)、"InfraDNS" という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="b1f86-224">Create a new build definition (select the **Empty** template) named "InfraDNS".</span></span>
<span data-ttu-id="b1f86-225">ビルド定義に以下のステップを追加します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-225">Add the following steps to you build definition:</span></span>

- <span data-ttu-id="b1f86-226">PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="b1f86-226">PowerShell Script</span></span>
- <span data-ttu-id="b1f86-227">テスト結果の公開</span><span class="sxs-lookup"><span data-stu-id="b1f86-227">Publish Test Results</span></span>
- <span data-ttu-id="b1f86-228">ファイルのコピー</span><span class="sxs-lookup"><span data-stu-id="b1f86-228">Copy Files</span></span>
- <span data-ttu-id="b1f86-229">成果物の公開</span><span class="sxs-lookup"><span data-stu-id="b1f86-229">Publish Artifact</span></span>

<span data-ttu-id="b1f86-230">これらのビルド ステップを追加したら、各ステップのプロパティを次のように編集します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-230">After adding these build steps, edit the properties of each step as follows:</span></span>

### <a name="powershell-script"></a><span data-ttu-id="b1f86-231">PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="b1f86-231">PowerShell Script</span></span>

1. <span data-ttu-id="b1f86-232">**[型]** プロパティを `File Path` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-232">Set the **Type** property to `File Path`.</span></span>
1. <span data-ttu-id="b1f86-233">**[スクリプト パス]** プロパティを `initiate.ps1` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-233">Set the **Script Path** property to `initiate.ps1`.</span></span>
1. <span data-ttu-id="b1f86-234">**[引数]** プロパティに `-fileName build` を追加します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-234">Add `-fileName build` to the **Arguments** property.</span></span>

<span data-ttu-id="b1f86-235">このビルド ステップは `initiate.ps1` ファイルを実行し、psake ビルド スクリプトを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-235">This build step runs the `initiate.ps1` file, which calls the psake build script.</span></span>

### <a name="publish-test-results"></a><span data-ttu-id="b1f86-236">テスト結果の公開</span><span class="sxs-lookup"><span data-stu-id="b1f86-236">Publish Test Results</span></span>

1. <span data-ttu-id="b1f86-237">**[テスト結果の形式]** を `NUnit` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-237">Set **Test Result Format** to `NUnit`</span></span>
1. <span data-ttu-id="b1f86-238">**[テスト結果ファイル]** を `InfraDNS/Tests/Results/*.xml` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-238">Set **Test Results Files** to `InfraDNS/Tests/Results/*.xml`</span></span>
1. <span data-ttu-id="b1f86-239">**[テスト実行のタイトル]** を `Unit` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-239">Set **Test Run Title** to `Unit`.</span></span>
1. <span data-ttu-id="b1f86-240">**[コントロール オプション]** **[有効]** と **[常に実行する]** が両方とも選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-240">Make sure **Control Options** **Enabled** and **Always run** are both selected.</span></span>

<span data-ttu-id="b1f86-241">このビルド ステップでは、先ほど確認した Pester スクリプトでの単体テストを実行し、その結果を `InfraDNS/Tests/Results/*.xml` フォルダーに格納します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-241">This build step runs the unit tests in the Pester script we looked at earlier, and stores the results in the `InfraDNS/Tests/Results/*.xml` folder.</span></span>

### <a name="copy-files"></a><span data-ttu-id="b1f86-242">ファイルのコピー</span><span class="sxs-lookup"><span data-stu-id="b1f86-242">Copy Files</span></span>

1. <span data-ttu-id="b1f86-243">以下の行すべてを、**[内容]** に追加します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-243">Add each of the following lines to **Contents**:</span></span>

   ```
   initiate.ps1
   **\deploy.ps1
   **\Acceptance\**
   **\Integration\**
   ```

1. <span data-ttu-id="b1f86-244">**TargetFolder** を `$(Build.ArtifactStagingDirectory)\` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-244">Set **TargetFolder** to `$(Build.ArtifactStagingDirectory)\`</span></span>

<span data-ttu-id="b1f86-245">このステップでは、ビルドおよびテスト スクリプトをステージング ディレクトリにコピーし、次のステップでビルド成果物として公開できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b1f86-245">This step copies the build and test scripts to the staging directory so that the can be published as build artifacts by the next step.</span></span>

### <a name="publish-artifact"></a><span data-ttu-id="b1f86-246">成果物の公開</span><span class="sxs-lookup"><span data-stu-id="b1f86-246">Publish Artifact</span></span>

1. <span data-ttu-id="b1f86-247">**[発行するためのパス]** を `$(Build.ArtifactStagingDirectory)\` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-247">Set **Path to Publish** to `$(Build.ArtifactStagingDirectory)\`</span></span>
1. <span data-ttu-id="b1f86-248">**[成果物名]** を `Deploy` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-248">Set **Artifact Name** to `Deploy`</span></span>
1. <span data-ttu-id="b1f86-249">**[成果物の種類]** を `Server` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-249">Set **Artifact Type** to `Server`</span></span>
1. <span data-ttu-id="b1f86-250">**[コントロール オプション]** で `Enabled` を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-250">Select `Enabled` in **Control Options**</span></span>

## <a name="enable-continuous-integration"></a><span data-ttu-id="b1f86-251">継続的インテグレーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="b1f86-251">Enable continuous integration</span></span>

<span data-ttu-id="b1f86-252">git リポジトリの `ci-cd-example` ブランチに変更がチェックインされたときにプロジェクトがビルドを開始するように、トリガーを設定します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-252">Now we'll set up a trigger that causes the project to build any time a change is checked in to the `ci-cd-example` branch of the git repository.</span></span>

1. <span data-ttu-id="b1f86-253">TFS で、**[ビルドとリリース]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1f86-253">In TFS, click the **Build & Release** tab</span></span>
1. <span data-ttu-id="b1f86-254">`DNS Infra` ビルド定義を選択して、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1f86-254">Select the `DNS Infra` build definition, and click **Edit**</span></span>
1. <span data-ttu-id="b1f86-255">**[トリガー]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1f86-255">Click the **Triggers** tab</span></span>
1. <span data-ttu-id="b1f86-256">**[継続的インテグレーション (CI)]** を選択して、ブランチのドロップダウン リストで `refs/heads/ci-cd-example` を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-256">Select **Continuous integration (CI)**, and select `refs/heads/ci-cd-example` in the branch drop-down list</span></span>
1. <span data-ttu-id="b1f86-257">**[保存]** をクリックしてから **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1f86-257">Click **Save** and then **OK**</span></span>

<span data-ttu-id="b1f86-258">これで、TFS git リポジトリに何らかの変更があると、自動ビルドがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="b1f86-258">Now any change in the TFS git repository triggers an automated build.</span></span>

## <a name="create-the-release-definition"></a><span data-ttu-id="b1f86-259">リリース定義を作成する</span><span class="sxs-lookup"><span data-stu-id="b1f86-259">Create the release definition</span></span>

<span data-ttu-id="b1f86-260">リリース定義を作成して、コードのチェックインが行われるたびにプロジェクトが開発環境に展開されるようにしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="b1f86-260">Let's create a release definition so that the project is deployed to the development environment with every code check-in.</span></span>

<span data-ttu-id="b1f86-261">これを行うには、既に作成したビルド定義 `InfraDNS` に関連付けられた新しいリリース定義を追加します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-261">To do this, add a new release definition associated with the `InfraDNS` build definition you created previously.</span></span>
<span data-ttu-id="b1f86-262">必ず **[継続的配置]** を選択し、新しいビルドが完了したらいつでも新しいリリースがトリガーされるようにして </span><span class="sxs-lookup"><span data-stu-id="b1f86-262">Be sure to select **Continuous deployment** so that a new release will be triggered any time a new build is completed.</span></span>
<span data-ttu-id="b1f86-263">(「[How to: Work with release definitions」](https://www.visualstudio.com/en-us/docs/build/actions/work-with-release-definitions) (方法: リリース定義の作業) を参照)、次のように構成します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-263">([How to: Work with release definitions](https://www.visualstudio.com/en-us/docs/build/actions/work-with-release-definitions)) and configure it as follows:</span></span>

<span data-ttu-id="b1f86-264">リリース定義に以下のステップを追加します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-264">Add the following steps to the release definition:</span></span>

- <span data-ttu-id="b1f86-265">PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="b1f86-265">PowerShell Script</span></span>
- <span data-ttu-id="b1f86-266">テスト結果の公開</span><span class="sxs-lookup"><span data-stu-id="b1f86-266">Publish Test Results</span></span>
- <span data-ttu-id="b1f86-267">テスト結果の公開</span><span class="sxs-lookup"><span data-stu-id="b1f86-267">Publish Test Results</span></span>

<span data-ttu-id="b1f86-268">ステップを次のように編集します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-268">Edit the steps as follows:</span></span>

### <a name="powershell-script"></a><span data-ttu-id="b1f86-269">PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="b1f86-269">PowerShell Script</span></span>

1. <span data-ttu-id="b1f86-270">**[スクリプト パス]** フィールドを `$(Build.DefinitionName)\Deploy\initiate.ps1"` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-270">Set the **Script Path** field to `$(Build.DefinitionName)\Deploy\initiate.ps1"`</span></span>
1. <span data-ttu-id="b1f86-271">**[引数]** フィールドを `-fileName Deploy` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-271">Set the **Arguments** field to `-fileName Deploy`</span></span>

### <a name="first-publish-test-results"></a><span data-ttu-id="b1f86-272">1 つめのテスト結果の公開</span><span class="sxs-lookup"><span data-stu-id="b1f86-272">First Publish Test Results</span></span>

1. <span data-ttu-id="b1f86-273">**[テスト結果の形式]** フィールドとして `NUnit` を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-273">Select `NUnit` for the **Test Result Format** field</span></span>
1. <span data-ttu-id="b1f86-274">**[テスト結果ファイル]** フィールドを `$(Build.DefinitionName)\Deploy\InfraDNS\Tests\Results\Integration*.xml` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-274">Set the **Test Result Files** field to `$(Build.DefinitionName)\Deploy\InfraDNS\Tests\Results\Integration*.xml`</span></span>
1. <span data-ttu-id="b1f86-275">**[テスト実行のタイトル]** を `Integration` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-275">Set the **Test Run Title** to `Integration`</span></span>
1. <span data-ttu-id="b1f86-276">**[コントロール オプション]** で、**[常に実行する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-276">Under **Control Options**, check **Always run**</span></span>

### <a name="second-publish-test-results"></a><span data-ttu-id="b1f86-277">2 つめのテスト結果の公開</span><span class="sxs-lookup"><span data-stu-id="b1f86-277">Second Publish Test Results</span></span>

1. <span data-ttu-id="b1f86-278">**[テスト結果の形式]** フィールドとして `NUnit` を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-278">Select `NUnit` for the **Test Result Format** field</span></span>
1. <span data-ttu-id="b1f86-279">**[テスト結果ファイル]** フィールドを `$(Build.DefinitionName)\Deploy\InfraDNS\Tests\Results\Acceptance*.xml` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-279">Set the **Test Result Files** field to `$(Build.DefinitionName)\Deploy\InfraDNS\Tests\Results\Acceptance*.xml`</span></span>
1. <span data-ttu-id="b1f86-280">**[テスト実行のタイトル]** を `Acceptance` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-280">Set the **Test Run Title** to `Acceptance`</span></span>
1. <span data-ttu-id="b1f86-281">**[コントロール オプション]** で、**[常に実行する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f86-281">Under **Control Options**, check **Always run**</span></span>

## <a name="verify-your-results"></a><span data-ttu-id="b1f86-282">結果を確認する</span><span class="sxs-lookup"><span data-stu-id="b1f86-282">Verify your results</span></span>

<span data-ttu-id="b1f86-283">これで、`ci-cd-example` ブランチの変更を TFS にプッシュするたび、新しいビルドが開始されます。</span><span class="sxs-lookup"><span data-stu-id="b1f86-283">Now, any time you push changes in the `ci-cd-example` branch to TFS, a new build will start.</span></span>
<span data-ttu-id="b1f86-284">ビルドが正常に完了すると、新しい配置がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="b1f86-284">If the build completes successfully, a new deployment is triggered.</span></span>

<span data-ttu-id="b1f86-285">クライアント コンピューターでブラウザーを開いて `www.contoso.com` に移動して、配置結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b1f86-285">You can check the result of the deployment by opening a browser on the client machine and navigating to `www.contoso.com`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b1f86-286">次の手順</span><span class="sxs-lookup"><span data-stu-id="b1f86-286">Next steps</span></span>

<span data-ttu-id="b1f86-287">この例では、URL `www.contoso.com` が `TestAgent2` に解決されるように DNS サーバー `TestAgent1` を構成していますが、Web サイトの配置は実際には行いません。</span><span class="sxs-lookup"><span data-stu-id="b1f86-287">This example configures the DNS server `TestAgent1` so that the URL `www.contoso.com` resolves to `TestAgent2`, but it does not actually deploy a website.</span></span>
<span data-ttu-id="b1f86-288">それを行うためのスケルトンは、`WebApp` フォルダー下のリポジトリで提供されています。</span><span class="sxs-lookup"><span data-stu-id="b1f86-288">The skeleton for doing so is provided in the repo under the `WebApp` folder.</span></span>
<span data-ttu-id="b1f86-289">提供されるスタブを使用して、psake スクリプト、Pester テスト、DSC 構成を作成し、自分の Web サイトを配置することができます。</span><span class="sxs-lookup"><span data-stu-id="b1f86-289">You can use the stubs provided to create psake scripts, Pester tests, and DSC configurations to deploy your own website.</span></span>