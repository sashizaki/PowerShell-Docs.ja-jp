---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 DSC の nxScript リソース
ms.openlocfilehash: a7f2114aba47bb581cdd19168e784b79dfc5b6ad
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953189"
---
# <a name="dsc-for-linux-nxscript-resource"></a><span data-ttu-id="547f5-103">Linux 用 DSC の nxScript リソース</span><span class="sxs-lookup"><span data-stu-id="547f5-103">DSC for Linux nxScript Resource</span></span>

<span data-ttu-id="547f5-104">PowerShell Desired State Configuration (DSC) の **nxScript** リソースは、Linux ノード上で Linux スクリプトを実行するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="547f5-104">The **nxScript** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to run Linux scripts on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="547f5-105">構文</span><span class="sxs-lookup"><span data-stu-id="547f5-105">Syntax</span></span>

```Syntax
nxScript <string> #ResourceName
{
    GetScript = <string>
    SetScript = <string>
    TestScript = <string>
    [ User = <string> ]
    [ Group = <string> ]
    [ DependsOn = <string[]> ]
}
```

## <a name="properties"></a><span data-ttu-id="547f5-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="547f5-106">Properties</span></span>

|<span data-ttu-id="547f5-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="547f5-107">Property</span></span> |<span data-ttu-id="547f5-108">説明</span><span class="sxs-lookup"><span data-stu-id="547f5-108">Description</span></span> |
|---|---|
|<span data-ttu-id="547f5-109">GetScript</span><span class="sxs-lookup"><span data-stu-id="547f5-109">GetScript</span></span> |<span data-ttu-id="547f5-110">コンピューターの現在の状態を返すスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="547f5-110">Provides a script to return current status of the machine.</span></span> <span data-ttu-id="547f5-111">このスクリプトは、[GetDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) スクリプトを呼び出したときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="547f5-111">This script runs when you invoke the [GetDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script.</span></span> <span data-ttu-id="547f5-112">スクリプトは、`#!/bin/bash` などのシバンで開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="547f5-112">The script must begin with a shebang, such as `#!/bin/bash`.</span></span> |
|<span data-ttu-id="547f5-113">SetScript</span><span class="sxs-lookup"><span data-stu-id="547f5-113">SetScript</span></span> |<span data-ttu-id="547f5-114">コンピューターを正しい状態にするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="547f5-114">Provides a script that puts the machine in the correct state.</span></span> <span data-ttu-id="547f5-115">[StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) スクリプトを呼び出すと、**TestScript** が最初に実行されます。</span><span class="sxs-lookup"><span data-stu-id="547f5-115">When you invoke the [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script, the **TestScript** runs first.</span></span> <span data-ttu-id="547f5-116">**TestScript** ブロックが 0 以外の終了コードを返した場合は、**SetScript** ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="547f5-116">If the **TestScript** block returns an exit code other than 0, the **SetScript** block will run.</span></span> <span data-ttu-id="547f5-117">**TestScript** が終了コード 0 を返した場合は、**SetScript** が実行されません。</span><span class="sxs-lookup"><span data-stu-id="547f5-117">If the **TestScript** returns an exit code of 0, the **SetScript** will not run.</span></span> <span data-ttu-id="547f5-118">スクリプトは、`#!/bin/bash` などのシバンで開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="547f5-118">The script must begin with a shebang, such as `#!/bin/bash`.</span></span> |
|<span data-ttu-id="547f5-119">TestScript</span><span class="sxs-lookup"><span data-stu-id="547f5-119">TestScript</span></span> |<span data-ttu-id="547f5-120">ノードが現在正しい状態であるかどうかを評価するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="547f5-120">Provides a script that evaluates whether the node is currently in the correct state.</span></span> <span data-ttu-id="547f5-121">[StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) スクリプトを呼び出すと、このスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="547f5-121">When you invoke the [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script, this script runs.</span></span> <span data-ttu-id="547f5-122">0 以外の終了コードが返された場合、**SetScript** が実行されます。</span><span class="sxs-lookup"><span data-stu-id="547f5-122">If it returns an exit code other than 0, the **SetScript** will run.</span></span> <span data-ttu-id="547f5-123">終了コード 0 が返された場合、**SetScript** は実行されません。</span><span class="sxs-lookup"><span data-stu-id="547f5-123">If it returns an exit code of 0, the **SetScript** will not run.</span></span> <span data-ttu-id="547f5-124">[TestDscConfiguration](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) スクリプトを呼び出すと、**TestScript** も実行されます。</span><span class="sxs-lookup"><span data-stu-id="547f5-124">The **TestScript** also runs when you invoke the [TestDscConfiguration](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script.</span></span> <span data-ttu-id="547f5-125">ただし、この場合、**TestScript** からどのような終了コードが返されるに関係なく、**SetScript** は実行されません。</span><span class="sxs-lookup"><span data-stu-id="547f5-125">However, in this case, the **SetScript** will not run, no matter what exit code is returned from the **TestScript**.</span></span> <span data-ttu-id="547f5-126">実際の構成が現在の必要な状態の構成と一致する場合、**TestScript** はコンテンツを含み、かつ終了コード 0 を返す必要があります。一致しない場合は、0 以外の終了コードを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="547f5-126">The **TestScript** must contain content and must return an exit code of 0 if the actual configuration matches the current desired state configuration, and an exit code other than 0 if it does not match.</span></span> <span data-ttu-id="547f5-127">現在の Desired State Configuration は DSC を使用しているノードに適用された最後の構成です。</span><span class="sxs-lookup"><span data-stu-id="547f5-127">The current desired state configuration is the last configuration enacted on the node that is using DSC.</span></span> <span data-ttu-id="547f5-128">スクリプトは、`#!/bin/bash` などのシバンで開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="547f5-128">The script must begin with a shebang, such as `#!/bin/bash`.</span></span> |
|<span data-ttu-id="547f5-129">User</span><span class="sxs-lookup"><span data-stu-id="547f5-129">User</span></span> |<span data-ttu-id="547f5-130">スクリプトを実行するユーザー。</span><span class="sxs-lookup"><span data-stu-id="547f5-130">The user to run the script as.</span></span> |
|<span data-ttu-id="547f5-131">グループ</span><span class="sxs-lookup"><span data-stu-id="547f5-131">Group</span></span> |<span data-ttu-id="547f5-132">スクリプトを実行するグループ。</span><span class="sxs-lookup"><span data-stu-id="547f5-132">The group to run the script as.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="547f5-133">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="547f5-133">Common properties</span></span>

|<span data-ttu-id="547f5-134">プロパティ</span><span class="sxs-lookup"><span data-stu-id="547f5-134">Property</span></span> |<span data-ttu-id="547f5-135">説明</span><span class="sxs-lookup"><span data-stu-id="547f5-135">Description</span></span> |
|---|---|
|<span data-ttu-id="547f5-136">DependsOn</span><span class="sxs-lookup"><span data-stu-id="547f5-136">DependsOn</span></span> |<span data-ttu-id="547f5-137">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="547f5-137">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="547f5-138">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="547f5-138">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |

## <a name="example"></a><span data-ttu-id="547f5-139">例</span><span class="sxs-lookup"><span data-stu-id="547f5-139">Example</span></span>

<span data-ttu-id="547f5-140">次の例では、追加の構成管理を実行するための **nxScript** リソースの使用を示します。</span><span class="sxs-lookup"><span data-stu-id="547f5-140">The following example demonstrates the use of the **nxScript** resource to perform additional configuration management.</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxScript KeepDirEmpty {

    GetScript = @"
#!/bin/bash
ls /tmp/mydir/ | wc -l
"@

    SetScript = @"
#!/bin/bash
rm -rf /tmp/mydir/*
"@

    TestScript = @'
#!/bin/bash
filecount=`ls /tmp/mydir | wc -l`
if [ $filecount -gt 0 ]
then
    exit 1
else
    exit 0
fi
'@
    }
}
```
