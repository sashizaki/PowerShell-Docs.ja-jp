---
description: 
manager: dongill
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット, JEA"
ms.date: 2016-06-22
title: "複数のコンピューターの展開と保守"
ms.technology: powershell
ms.openlocfilehash: 8117d0d12c062b460cb7117b54c138c8db5a1d0c
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
ms.translationtype: HT
ms.contentlocale: ja-JP
---
# <a name="multi-machine-deployment-and-maintenance"></a><span data-ttu-id="a1a51-103">複数のコンピューターの展開と保守</span><span class="sxs-lookup"><span data-stu-id="a1a51-103">Multi-machine Deployment and Maintenance</span></span>
<span data-ttu-id="a1a51-104">この時点で、JEA をローカル システムに何回か展開しています。</span><span class="sxs-lookup"><span data-stu-id="a1a51-104">At this point, you have deployed JEA to local systems several times.</span></span>
<span data-ttu-id="a1a51-105">運用環境はおそらく複数のコンピューターで構成されているため、展開プロセスの重要な手順に従って、各コンピューターでこれらを繰り返すことが重要です。</span><span class="sxs-lookup"><span data-stu-id="a1a51-105">Because your production environment probably consists of more than one machine, it's important to walk through the critical steps in the deployment process that must be repeated on each machine.</span></span>

## <a name="high-level-steps"></a><span data-ttu-id="a1a51-106">大まかな手順:</span><span class="sxs-lookup"><span data-stu-id="a1a51-106">High Level Steps:</span></span>
1.  <span data-ttu-id="a1a51-107">モジュールを (ロール機能により) 各ノードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a1a51-107">Copy your modules (with Role Capabilities) to each node.</span></span>
2.  <span data-ttu-id="a1a51-108">セッション構成ファイルを各ノードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a1a51-108">Copy your session configuration files to each node.</span></span>
3.  <span data-ttu-id="a1a51-109">セッション構成を使用して `Register-PSSessionConfiguration` を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1a51-109">Run `Register-PSSessionConfiguration` with your session configuration.</span></span>
4.  <span data-ttu-id="a1a51-110">セッション構成とツールキットのコピーを安全な場所に保管します。</span><span class="sxs-lookup"><span data-stu-id="a1a51-110">Keep a copy of your session configuration and toolkits in a secure location.</span></span>
<span data-ttu-id="a1a51-111">変更を行う際は、"信頼できる唯一の情報源" を採用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a1a51-111">As you make modifications, it's good to have a "single source of truth."</span></span>

## <a name="example-script"></a><span data-ttu-id="a1a51-112">スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="a1a51-112">Example Script</span></span>
<span data-ttu-id="a1a51-113">配置のスクリプトの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a1a51-113">Here's an example script for deployment.</span></span>
<span data-ttu-id="a1a51-114">これを自身の環境で使用する場合、実際のファイル共有とモジュールの名前とパスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1a51-114">To use it in your environment, you'll have to use the names/paths of real file shares and modules.</span></span>
```PowerShell
# First, copy the session configuration and modules (containing role capability files) onto a file share you have access to.
Copy-Item -Path 'C:\Demo\Demo.pssc' -Destination '\\FileShare\JEA\Demo.pssc'
Copy-Item -Path 'C:\Program Files\WindowsPowerShell\Modules\SomeModule\' -Recurse -Destination '\\FileShare\JEA\SomeModule'

# Next, author a setup script (C:\JEA\Deploy.ps1) to run on each individual node
    # Contents of C:\JEA\Deploy.ps1
    New-Item -ItemType Directory -Path C:\JEADeploy
    Copy-Item -Path '\\FileShare\JEA\Demo.pssc' -Destination 'C:\JEADeploy\'
    Copy-Item -Path '\\FileShare\JEA\SomeModule' -Recurse -Destination 'C:\Program Files\WindowsPowerShell\Modules' # Remember, Role Capability Files are found in modules
    if (Get-PSSessionConfiguration -Name JEADemo -ErrorAction SilentlyContinue)
    {
        Unregister-PSSessionConfiguration -Name JEADemo -ErrorAction Stop
    }

    Register-PSSessionConfiguration -Name JEADemo -Path 'C:\JEADeploy\Demo.pssc'
    Remove-Item -Path 'C:\JEADeploy' # Don't forget to clean up!

# Now, invoke the script on all of the target machines.
# Note: this requires PowerShell Remoting be enabled on each machine. Enabling PowerShell remoting is a requirement to use JEA as well.
# You may need to provide the "-Credential" parameter if your current user account does not have admin permissions on these machines.
Invoke-Command –ComputerName 'Node1', 'Node2', 'Node3', 'NodeN' -FilePath 'C:\JEA\Deploy.ps1'

# Finally, delete the session configuration and role capability files from the file share.
Remove-Item -Path '\\FileShare\JEA\Demo.pssc'
Remove-Item -Path '\\FileShare\JEA\SomeModule' -Recurse
```
## <a name="modifying-capabilities"></a><span data-ttu-id="a1a51-115">機能の変更</span><span class="sxs-lookup"><span data-stu-id="a1a51-115">Modifying Capabilities</span></span>
<span data-ttu-id="a1a51-116">多くのコンピューターを扱う際、一貫した方法で変更を反映させることが重要です。</span><span class="sxs-lookup"><span data-stu-id="a1a51-116">When dealing with many machines, it's important that modifications are rolled out in a consistent manner.</span></span>
<span data-ttu-id="a1a51-117">JEA に DSC リソースがあれば、環境を同期することができます。</span><span class="sxs-lookup"><span data-stu-id="a1a51-117">Once JEA has a DSC Resource, this will help ensure your environment is in sync.</span></span>
<span data-ttu-id="a1a51-118">それまでは、セッション構成のマスター コピーを保持し、変更を加えるたびに再展開することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a1a51-118">Until that time, we highly recommend you keep a master copy of your session configurations and re-deploy each time you make a modification.</span></span>

## <a name="removing-capabilities"></a><span data-ttu-id="a1a51-119">機能の削除</span><span class="sxs-lookup"><span data-stu-id="a1a51-119">Removing Capabilities</span></span>
<span data-ttu-id="a1a51-120">JEA 構成をシステムから削除するには、各コンピューターで次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1a51-120">To remove your JEA configuration from your systems, use the following command on each machine:</span></span>
```PowerShell
Unregister-PSSessionConfiguration -Name JEADemo
```

