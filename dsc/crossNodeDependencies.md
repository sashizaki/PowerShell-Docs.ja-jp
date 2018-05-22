---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: ノードの相互依存関係の指定
ms.openlocfilehash: c1802d6baa1f2b3449603e0374a83e213abf598e
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="specifying-cross-node-dependencies"></a><span data-ttu-id="f183a-103">ノードの相互依存関係の指定</span><span class="sxs-lookup"><span data-stu-id="f183a-103">Specifying cross-node dependencies</span></span>

> <span data-ttu-id="f183a-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="f183a-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="f183a-105">DSC には、**WaitForAll**、**WaitForAny**、**WaitForSome** などの特別なリソースが用意されています。このリソースを構成で使用すると、他のノードの構成への依存関係を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="f183a-105">DSC provides special resources, **WaitForAll**, **WaitForAny**, and **WaitForSome** that can be used in configurations to specify dependencies on configurations on other nodes.</span></span> <span data-ttu-id="f183a-106">これらのリソースの動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f183a-106">The behavior of these resources is as follows:</span></span>

* <span data-ttu-id="f183a-107">**WaitForAll**: **NodeName** プロパティで定義されているすべてのターゲット ノードで、指定されたリソースが目的の状態である場合に成功します。</span><span class="sxs-lookup"><span data-stu-id="f183a-107">**WaitForAll**: Succeeds if the specified resource is in the desired state on all target nodes defined in the **NodeName** property.</span></span>
* <span data-ttu-id="f183a-108">**WaitForAny**: **NodeName** プロパティで定義されているターゲット ノードの少なくとも 1 つで、指定されたリソースが目的の状態である場合に成功します。</span><span class="sxs-lookup"><span data-stu-id="f183a-108">**WaitForAny**: Succeeds if the specified resource is in the desired state on at least one of the target nodes defined in the **NodeName** property.</span></span>
* <span data-ttu-id="f183a-109">**WaitForSome**: **NodeName** プロパティのほか、**NodeCount** プロパティも指定します。</span><span class="sxs-lookup"><span data-stu-id="f183a-109">**WaitForSome**: Specifies a **NodeCount** property in addition to a **NodeName** property.</span></span> <span data-ttu-id="f183a-110">リソースは、**NodeName** プロパティで定義されたノードの最小数 (**NodeCount** で指定) で目的の状態になった場合に成功します。</span><span class="sxs-lookup"><span data-stu-id="f183a-110">The resource succeeds if the resource is in the desired state on a minimum number of nodes (specified by **NodeCount**) defined by the **NodeName** property.</span></span>

## <a name="using-waitforxxxx-resources"></a><span data-ttu-id="f183a-111">WaitForXXXX リソースの使用</span><span class="sxs-lookup"><span data-stu-id="f183a-111">Using WaitForXXXX resources</span></span>

<span data-ttu-id="f183a-112">**WaitForXXXX** リソースを使用するには、待機する DSC リソースとノードを指定する、そのリソースの種類のリソース ブロックを作成します。</span><span class="sxs-lookup"><span data-stu-id="f183a-112">To use the **WaitForXXXX** resources, you create a resource block of that resource type that specifies the DSC resource and node(s) to wait for.</span></span> <span data-ttu-id="f183a-113">その後、構成の他のリソース ブロックで **DependsOn** プロパティを使用して、**WaitForXXXX** ノードで指定されている条件が成功するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="f183a-113">You then use the **DependsOn** property in any other resource blocks in your configuration to wait for the conditions specified in the **WaitForXXXX** node to succeed.</span></span>

<span data-ttu-id="f183a-114">たとえば、次の構成では、ターゲット ノードは **MyDC** ノード上の **xADDomain** リソースが完了するまで 15 秒間隔で最大 30 回試行しながら待機した後、ドメインに参加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f183a-114">For example, in the following configuration, the target node is waiting for the **xADDomain** resource to finish on the **MyDC** node with maximum number of 30 retries, at 15-second intervals, before the target node can join the domain.</span></span>

```powershell
Configuration JoinDomain

{
    Import-DscResource -Module xComputerManagement, xActiveDirectory

    Node myDC
    {
        WindowsFeature InstallAD
        {
            Ensure = 'Present'
            Name = 'AD-Domain-Services'
        }

        xADDomain NewDomain
        {
            DomainName = 'Contoso.com'
            DomainAdministratorCredential = (Get-Credential)
            SafemodeAdministratorPassword = (Get-Credential)
            DatabasePath = "C:\Windows\NTDS"
            LogPath = "C:\Windows\NTDS"
            SysvolPath = "C:\Windows\Sysvol"
        }

    }

    Node myDomainJoinedServer
    {

        WaitForAll DC
        {
            ResourceName      = '[xADDomain]NewDomain'
            NodeName          = 'MyDC'
            RetryIntervalSec  = 15
            RetryCount        = 30
        }

        xComputer JoinDomain
        {
            Name             = 'myPC'
            DomainName       = 'Contoso.com'
            Credential       = (Get-Credential)
            DependsOn        ='[WaitForAll]DC'
        }
    }
}
```

><span data-ttu-id="f183a-115">**注:** 既定では、WaitForXXX リソースは 1 回試行してから失敗します。</span><span class="sxs-lookup"><span data-stu-id="f183a-115">**Note:** By default the WaitForXXX resources try one time and then fail.</span></span> <span data-ttu-id="f183a-116">これは必須ではありませんが、通常は、再試行の間隔と回数を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f183a-116">Although it is not required, you will typically want to specify a retry interval and count.</span></span>

## <a name="see-also"></a><span data-ttu-id="f183a-117">参照</span><span class="sxs-lookup"><span data-stu-id="f183a-117">See Also</span></span>
* [<span data-ttu-id="f183a-118">DSC 構成</span><span class="sxs-lookup"><span data-stu-id="f183a-118">DSC Configurations</span></span>](configurations.md)
* [<span data-ttu-id="f183a-119">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="f183a-119">DSC Resources</span></span>](resources.md)
* [<span data-ttu-id="f183a-120">ローカル構成マネージャーの構成</span><span class="sxs-lookup"><span data-stu-id="f183a-120">Configuring The Local Configuration Manager</span></span>](metaConfig.md)