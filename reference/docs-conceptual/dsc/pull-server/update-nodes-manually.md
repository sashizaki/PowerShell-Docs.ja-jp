---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: プル サーバーからのノードを更新する
ms.openlocfilehash: 4333a5bf82ef45f22a062942ebe93409433623f5
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71955099"
---
# <a name="update-nodes-from-a-pull-server"></a><span data-ttu-id="6b76d-103">プル サーバーからのノードを更新する</span><span class="sxs-lookup"><span data-stu-id="6b76d-103">Update Nodes from a Pull Server</span></span>

<span data-ttu-id="6b76d-104">以下のセクションでは、プル サーバーを既にセットアップしてあるものとします。</span><span class="sxs-lookup"><span data-stu-id="6b76d-104">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="6b76d-105">プル サーバーをセットアップしていない場合は、次のガイドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b76d-105">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="6b76d-106">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="6b76d-106">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="6b76d-107">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="6b76d-107">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="6b76d-108">各ターゲット ノードは、構成やリソースをダウンロードし、さらにその状態を報告するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="6b76d-108">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="6b76d-109">この記事では、ダウンロードできるようにリソースをアップロードする方法、およびリソースを自動的にダウンロードするようにクライアントを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6b76d-109">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="6b76d-110">ノードは、割り当てられた構成を**プル**または**プッシュ** (v5) によって受け取ると、構成で必要なすべてのリソースを LCM で指定された場所から自動的にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6b76d-110">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="using-the-update-dscconfiguration-cmdlet"></a><span data-ttu-id="6b76d-111">Update-DSCConfiguration コマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="6b76d-111">Using the Update-DSCConfiguration cmdlet</span></span>

<span data-ttu-id="6b76d-112">PowerShell 5.0 以降では、[Update-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration) コマンドレットによって、LCM で構成されているプル サーバーからノードの構成が強制的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="6b76d-112">Beginning in PowerShell 5.0, the [Update-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration) cmdlet, forces a Node to update its configuration from the Pull Server configured in the LCM.</span></span>

```powershell
Update-DSCConfiguration -ComputerName "Server01"
```

## <a name="using-invoke-cimmethod"></a><span data-ttu-id="6b76d-113">Invoke-CIMMethod の使用</span><span class="sxs-lookup"><span data-stu-id="6b76d-113">Using Invoke-CIMMethod</span></span>

<span data-ttu-id="6b76d-114">PowerShell 4.0 ではまだ、[Invoke-CIMMethod](/powershell/module/cimcmdlets/invoke-cimmethod) を使用して手動で強制的にプル クライアントの構成を更新できます。</span><span class="sxs-lookup"><span data-stu-id="6b76d-114">In PowerShell 4.0, you can still manually force a Pull Client to update its Configuration using [Invoke-CIMMethod](/powershell/module/cimcmdlets/invoke-cimmethod).</span></span> <span data-ttu-id="6b76d-115">次の例では、指定した資格情報で CIM セッションを作成し、適切な CIM メソッドを呼び出して、セッションを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b76d-115">The following example creates a CIM session with specified credentials, invokes the appropriate CIM method, and removes the session.</span></span>

```powershell
$cimSession = New-CimSession -ComputerName "Server01" -Credential $(Get-Credential)
Invoke-CimMethod -CimSession $cimSession -Namespace 'root/microsoft/windows/desiredstateconfiguration' -Class 'MSFT_DscLocalConfigurationManager' -MethodName 'PerformRequiredConfigurationChecks' -Arguments @{ 'Flags' = [uint32]1 } -Verbose
$cimSession | Remove-CimSession
```

## <a name="see-also"></a><span data-ttu-id="6b76d-116">参照</span><span class="sxs-lookup"><span data-stu-id="6b76d-116">See Also</span></span>

[<span data-ttu-id="6b76d-117">PerformRequiredConfigurationChecks</span><span class="sxs-lookup"><span data-stu-id="6b76d-117">PerformRequiredConfigurationChecks</span></span>](/powershell/dsc/msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks)