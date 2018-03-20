---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "PowerShell Desired State Configuration の概要"
ms.openlocfilehash: 04404696bef128805e4f1c191711eaab33cf7e4c
ms.sourcegitcommit: 99227f62dcf827354770eb2c3e95c5cf6a3118b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="getting-started-with-powershell-desired-state-configuration"></a><span data-ttu-id="99a8c-103">PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="99a8c-103">Getting Started with PowerShell Desired State Configuration</span></span> #

<span data-ttu-id="99a8c-104">このガイドでは、PowerShell Desired State Configuration ドキュメントの作成を開始し、マシンに適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="99a8c-104">This guide describes how to begin creating PowerShell Desired State Configuration documents and apply them to machines.</span></span> <span data-ttu-id="99a8c-105">PowerShell コマンドレット、モジュール、および関数の基礎知識があることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="99a8c-105">It assumes basic familiarity with PowerShell cmdlets, modules, and functions.</span></span> 


## <a name="create-a-configuration"></a><span data-ttu-id="99a8c-106">構成の作成</span><span class="sxs-lookup"><span data-stu-id="99a8c-106">Create a Configuration</span></span> ##

<span data-ttu-id="99a8c-107">[**構成**](https://msdn.microsoft.com/powershell/dsc/configurations)は、環境について説明するドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="99a8c-107">[**Configurations**](https://msdn.microsoft.com/powershell/dsc/configurations) are documents that describe an environment.</span></span> <span data-ttu-id="99a8c-108">環境は "**ノード**" で構成され、ノードは通常、仮想マシンまたは物理マシンです。</span><span class="sxs-lookup"><span data-stu-id="99a8c-108">Environments consist of "**nodes**", which are commonly virtual or physical machines.</span></span> 

<span data-ttu-id="99a8c-109">構成には、さまざまな形式があります。</span><span class="sxs-lookup"><span data-stu-id="99a8c-109">Configurations can come in a variety of forms.</span></span> <span data-ttu-id="99a8c-110">新しい構成を作成する最も簡単な方法は、.ps1 (PowerShell スクリプト) ファイルを作成することです。</span><span class="sxs-lookup"><span data-stu-id="99a8c-110">The easiest way to create a new configuration is to create a .ps1 (PowerShell script) file.</span></span> <span data-ttu-id="99a8c-111">これを行うには、任意のエディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="99a8c-111">To do this, open your editor of choice.</span></span> <span data-ttu-id="99a8c-112">PowerShell ISE では DSC がネイティブに認識されるため、適切な選択です。</span><span class="sxs-lookup"><span data-stu-id="99a8c-112">The PowerShell ISE is a good choice, since it understands DSC natively.</span></span> <span data-ttu-id="99a8c-113">以下を PS1 として保存します。</span><span class="sxs-lookup"><span data-stu-id="99a8c-113">Save the following as a PS1:</span></span>

```powershell
configuration MyFirstConfiguration
{
    Import-DscResource -Name WindowsFeature

    Node localhost
    {
        WindowsFeature IIS
        {
            Name = "IIS"

        }
        
    }

}
```
## <a name="parts-of-a-configuration"></a><span data-ttu-id="99a8c-114">構成のパーツ</span><span class="sxs-lookup"><span data-stu-id="99a8c-114">Parts of a Configuration</span></span> ##
<span data-ttu-id="99a8c-115">**Configuration** は、PowerShell 4.0 に追加されたキーワードです。</span><span class="sxs-lookup"><span data-stu-id="99a8c-115">**Configuration** is a keyword that has been added to PowerShell 4.0.</span></span> <span data-ttu-id="99a8c-116">これは、Desired State Configuration で使用される特別な種類の PowerShell 関数を示します。</span><span class="sxs-lookup"><span data-stu-id="99a8c-116">It signifies a special kind of PowerShell function used by Desired State Configuration.</span></span> <span data-ttu-id="99a8c-117">この例では、関数の名前は myFirstConfiguration です。</span><span class="sxs-lookup"><span data-stu-id="99a8c-117">In this example, the function is named myFirstConfiguration.</span></span> 

<span data-ttu-id="99a8c-118">次の行は、モジュールのインポートと同様のインポート ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="99a8c-118">The next line is an import statement, similar to importing a module.</span></span> <span data-ttu-id="99a8c-119">これについては後で説明します。</span><span class="sxs-lookup"><span data-stu-id="99a8c-119">It will be discussed later on.</span></span>

<span data-ttu-id="99a8c-120">"Node" では、この構成が機能するマシン名を定義します。</span><span class="sxs-lookup"><span data-stu-id="99a8c-120">"Node" defines the machine name this configuration will act on.</span></span> <span data-ttu-id="99a8c-121">この構成はローカルで編集されますが、構成はリモート ノードに到達し、それらを構成できます。</span><span class="sxs-lookup"><span data-stu-id="99a8c-121">Although this configuration is edited locally, configurations can reach out to remote nodes and configure them.</span></span> 

<span data-ttu-id="99a8c-122">ノードには、マシン名または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="99a8c-122">Nodes can be machine names or IP addresses.</span></span> <span data-ttu-id="99a8c-123">1 つの構成ドキュメントに複数のノードを指定できます。</span><span class="sxs-lookup"><span data-stu-id="99a8c-123">You can have multiple nodes in a single configuration document.</span></span> <span data-ttu-id="99a8c-124">[構成データ](https://msdn.microsoft.com/powershell/dsc/configdata)を使用して、同じ構成を複数のノードに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="99a8c-124">Using [configuration data](https://msdn.microsoft.com/powershell/dsc/configdata), you can also have the same configuration apply to multiple nodes.</span></span> <span data-ttu-id="99a8c-125">この場合、ノードは "localhost" であり、ローカル コンピューターを意味します。</span><span class="sxs-lookup"><span data-stu-id="99a8c-125">In this case, the node is "localhost" - which means the local computer.</span></span> 

<span data-ttu-id="99a8c-126">次の項目は、[**リソース**](https://msdn.microsoft.com/powershell/dsc/resources)です。</span><span class="sxs-lookup"><span data-stu-id="99a8c-126">The next item is a [**resource**](https://msdn.microsoft.com/powershell/dsc/resources).</span></span> <span data-ttu-id="99a8c-127">リソースは、構成の構成要素です。</span><span class="sxs-lookup"><span data-stu-id="99a8c-127">Resources are building blocks of configurations.</span></span> <span data-ttu-id="99a8c-128">各リソースは、マシンの 1 つの側面の実装ロジックを定義するモジュールです。</span><span class="sxs-lookup"><span data-stu-id="99a8c-128">Each resource is a module that defines the implementation logic of a single aspect of a machine.</span></span> <span data-ttu-id="99a8c-129">PowerShell で **Get-DscResource** を実行して、コンピューター上のすべてのリソースを表示できます。</span><span class="sxs-lookup"><span data-stu-id="99a8c-129">You can view every resource on your machine by running **Get-DscResource** in PowerShell.</span></span> <span data-ttu-id="99a8c-130">この構成の 2 行目にある **Import-DscResource** を含む構成で使用するには、リソースがローカル コンピューター上に存在し、インポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="99a8c-130">Resources must be present on the local machine and imported before they can be used in a configuration with **Import-DscResource** which is on the second line of this configuration.</span></span> 

<span data-ttu-id="99a8c-131">**構成の適用**</span><span class="sxs-lookup"><span data-stu-id="99a8c-131">**Enacting a Configuration**</span></span>

<span data-ttu-id="99a8c-132">上記のスクリプトを保存して実行した場合、出力は生成されません。</span><span class="sxs-lookup"><span data-stu-id="99a8c-132">If the script above is saved and run, no output will be produced.</span></span> <span data-ttu-id="99a8c-133">これは、構成は単なる関数であり、上記のスクリプトでは関数を定義してもまだ実行されていないためです。</span><span class="sxs-lookup"><span data-stu-id="99a8c-133">This is because a configuration is just a function, and the script above has defined the function but not yet run it.</span></span> <span data-ttu-id="99a8c-134">関数を定義した後、呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="99a8c-134">After the function is defined, it must be invoked:</span></span>
```powershell
myFirstConfiguration
```

<span data-ttu-id="99a8c-135">実行すると、構成関数により構成が有効であることが検証されます。</span><span class="sxs-lookup"><span data-stu-id="99a8c-135">When executed, configuration functions validate the configuration is valid.</span></span> <span data-ttu-id="99a8c-136">構成に構文エラーがなく、リソースにすべての必須パラメーターが定義され、実行前にすべてのリソースがインポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="99a8c-136">It should have no syntax errors, resources should have all mandatory parameters defined, and all resources should be imported before execution.</span></span>

<span data-ttu-id="99a8c-137">構成を実行すると、構成内の各ノードに対して **.MOF ファイル**を含む構成の名前が付いたフォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="99a8c-137">Once the configuration is executed, it creates a folder with the name of the configuration containing a **.MOF file** for every node in the configuration.</span></span> <span data-ttu-id="99a8c-138">.MOF ファイルは、ネットワーク経由で通信するために PowerShell DSC で使用される標準ベースの管理形式です。</span><span class="sxs-lookup"><span data-stu-id="99a8c-138">The .MOF file is a standards-based management format which is used by PowerShell DSC to communicate over the network.</span></span>

<span data-ttu-id="99a8c-139">構成を適用するには:</span><span class="sxs-lookup"><span data-stu-id="99a8c-139">To enact the configuration:</span></span>
```powershell
Start-DscConfiguration -Path ./myFirstConfiguration
```
<span data-ttu-id="99a8c-140">これにより、構成内のノードに到達してそれらを構成する PowerShell ジョブが作成されます。</span><span class="sxs-lookup"><span data-stu-id="99a8c-140">This creates a PowerShell job that reaches out to the nodes in the configuration and configures them.</span></span> <span data-ttu-id="99a8c-141">ジョブの出力を表示するには、-Wait を使用します。</span><span class="sxs-lookup"><span data-stu-id="99a8c-141">To see the output of the job, use -Wait.</span></span> 
```powershell
Start-DscConfiguration -Path ./myFirstConfiguration -Wait
```

