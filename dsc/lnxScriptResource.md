---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 DSC の nxScript リソース
ms.openlocfilehash: 339968512ab1c16c4c3785a3a19b00c3fbbf9ea1
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="dsc-for-linux-nxscript-resource"></a><span data-ttu-id="e8410-103">Linux 用 DSC の nxScript リソース</span><span class="sxs-lookup"><span data-stu-id="e8410-103">DSC for Linux nxScript Resource</span></span>

<span data-ttu-id="e8410-104">PowerShell Desired State Configuration (DSC) の **nxScript** リソースは、Linux ノード上で Linux スクリプトを実行するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="e8410-104">The **nxScript** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to run Linux scripts on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="e8410-105">構文</span><span class="sxs-lookup"><span data-stu-id="e8410-105">Syntax</span></span>

```
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

## <a name="properties"></a><span data-ttu-id="e8410-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e8410-106">Properties</span></span>

|  <span data-ttu-id="e8410-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e8410-107">Property</span></span> |  <span data-ttu-id="e8410-108">説明</span><span class="sxs-lookup"><span data-stu-id="e8410-108">Description</span></span> |
|---|---|
| <span data-ttu-id="e8410-109">GetScript</span><span class="sxs-lookup"><span data-stu-id="e8410-109">GetScript</span></span>| <span data-ttu-id="e8410-110">[Get-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521625.aspx) コマンドレットを呼び出すと実行されるスクリプトを提供します。</span><span class="sxs-lookup"><span data-stu-id="e8410-110">Provides a script that runs when you invoke the [Get-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521625.aspx) cmdlet.</span></span> <span data-ttu-id="e8410-111">スクリプトは、#!/bin/bash などのシバンで開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8410-111">The script must begin with a shebang, such as #!/bin/bash.</span></span>|
| <span data-ttu-id="e8410-112">SetScript</span><span class="sxs-lookup"><span data-stu-id="e8410-112">SetScript</span></span>| <span data-ttu-id="e8410-113">スクリプトを提供します。</span><span class="sxs-lookup"><span data-stu-id="e8410-113">Provides a script.</span></span> <span data-ttu-id="e8410-114">[Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) コマンドレットを呼び出すと、**TestScript** が最初に実行されます。</span><span class="sxs-lookup"><span data-stu-id="e8410-114">When you invoke the [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) cmdlet, the **TestScript** runs first.</span></span> <span data-ttu-id="e8410-115">**TestScript** ブロックが 0 以外の終了コードを返した場合は、**SetScript** ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e8410-115">If the **TestScript** block returns an exit code other than 0, the **SetScript** block will run.</span></span> <span data-ttu-id="e8410-116">**TestScript** が終了コード 0 を返した場合は、**SetScript** が実行されません。</span><span class="sxs-lookup"><span data-stu-id="e8410-116">If the **TestScript** returns an exit code of 0, the **SetScript** will not run.</span></span> <span data-ttu-id="e8410-117">スクリプトは、`#!/bin/bash` などのシバンで開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8410-117">The script must begin with a shebang, such as `#!/bin/bash`.</span></span>|
| <span data-ttu-id="e8410-118">TestScript</span><span class="sxs-lookup"><span data-stu-id="e8410-118">TestScript</span></span>| <span data-ttu-id="e8410-119">スクリプトを提供します。</span><span class="sxs-lookup"><span data-stu-id="e8410-119">Provides a script.</span></span> <span data-ttu-id="e8410-120">[Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) コマンドレットを呼び出すと、このスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e8410-120">When you invoke the [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) cmdlet, this script runs.</span></span> <span data-ttu-id="e8410-121">0 以外の終了コードが返された場合、SetScript が実行されます。</span><span class="sxs-lookup"><span data-stu-id="e8410-121">If it returns an exit code other than 0, the SetScript will run.</span></span> <span data-ttu-id="e8410-122">終了コード 0 が返された場合、**SetScript** は実行されません。</span><span class="sxs-lookup"><span data-stu-id="e8410-122">If it returns an exit code of 0, the **SetScript** will not run.</span></span> <span data-ttu-id="e8410-123">[Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) コマンドレットを呼び出すと、**TestScript** も実行されます。</span><span class="sxs-lookup"><span data-stu-id="e8410-123">The **TestScript** also runs when you invoke the [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) cmdlet.</span></span> <span data-ttu-id="e8410-124">ただし、この場合、**TestScript** からどのような終了コードが返されるに関係なく、**SetScript** は実行されません。</span><span class="sxs-lookup"><span data-stu-id="e8410-124">However, in this case, the **SetScript** will not run, no matter what exit code is returned from the **TestScript**.</span></span> <span data-ttu-id="e8410-125">実際の構成が現在の Desired State Configuration と一致する場合、**TestScript** は終了コード 0 を返す必要があります。一致しない場合は、0 以外の終了コードを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8410-125">The **TestScript** must return an exit code of 0 if the actual configuration matches the current desired state configuration, and an exit code other than 0 if it does not match.</span></span> <span data-ttu-id="e8410-126">(現在の Desired State Configuration は DSC を使用しているノードで適用された最後の構成です)。</span><span class="sxs-lookup"><span data-stu-id="e8410-126">(The current desired state configuration is the last configuration enacted on the node that is using DSC).</span></span> <span data-ttu-id="e8410-127">スクリプトは、1#!/bin/bash.1 などのシバンで開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8410-127">The script must begin with a shebang, such as 1#!/bin/bash.1</span></span>|
| <span data-ttu-id="e8410-128">User</span><span class="sxs-lookup"><span data-stu-id="e8410-128">User</span></span>| <span data-ttu-id="e8410-129">スクリプトを実行するユーザー。</span><span class="sxs-lookup"><span data-stu-id="e8410-129">The user to run the script as.</span></span>|
| <span data-ttu-id="e8410-130">グループ</span><span class="sxs-lookup"><span data-stu-id="e8410-130">Group</span></span>| <span data-ttu-id="e8410-131">スクリプトを実行するグループ。</span><span class="sxs-lookup"><span data-stu-id="e8410-131">The group to run the script as.</span></span>|
| <span data-ttu-id="e8410-132">DependsOn</span><span class="sxs-lookup"><span data-stu-id="e8410-132">DependsOn</span></span> | <span data-ttu-id="e8410-133">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="e8410-133">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="e8410-134">たとえば、最初に実行するリソース構成スクリプト ブロックの **ID** が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="e8410-134">For example, if the **ID** of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="example"></a><span data-ttu-id="e8410-135">例</span><span class="sxs-lookup"><span data-stu-id="e8410-135">Example</span></span>

<span data-ttu-id="e8410-136">次の例では、追加の構成管理を実行するための **nxScript** リソースの使用を示します。</span><span class="sxs-lookup"><span data-stu-id="e8410-136">The following example demonstrates the use of the **nxScript** resource to perform additional configuration management.</span></span>

```
Import-DSCResource -Module nx

Node $node {
nxScript KeepDirEmpty{

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