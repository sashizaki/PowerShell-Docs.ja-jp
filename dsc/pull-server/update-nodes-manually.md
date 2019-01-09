---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: プル サーバーからのノードを更新する
ms.openlocfilehash: 4333a5bf82ef45f22a062942ebe93409433623f5
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402150"
---
# <a name="update-nodes-from-a-pull-server"></a><span data-ttu-id="76b35-103">プル サーバーからのノードを更新する</span><span class="sxs-lookup"><span data-stu-id="76b35-103">Update Nodes from a Pull Server</span></span>

<span data-ttu-id="76b35-104">以下のセクションでは、プル サーバーを既に設定したことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="76b35-104">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="76b35-105">プル サーバーを設定していない場合は、次のガイドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="76b35-105">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="76b35-106">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="76b35-106">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="76b35-107">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="76b35-107">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="76b35-108">各ターゲット ノードは、構成、リソースをダウンロードしてもその状態を報告を構成できます。</span><span class="sxs-lookup"><span data-stu-id="76b35-108">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="76b35-109">この記事では、ダウンロード、およびリソースを自動的にダウンロードするクライアントの構成に利用できるように、リソースをアップロードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="76b35-109">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="76b35-110">ノードがを通じて割り当てられた構成を受信すると**プル**または**プッシュ**(v5) では、自動的にダウンロードし、LCM で指定された場所からの構成に必要なすべてのリソース。</span><span class="sxs-lookup"><span data-stu-id="76b35-110">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="using-the-update-dscconfiguration-cmdlet"></a><span data-ttu-id="76b35-111">Update-dscconfiguration コマンドレットを使用してください。</span><span class="sxs-lookup"><span data-stu-id="76b35-111">Using the Update-DSCConfiguration cmdlet</span></span>

<span data-ttu-id="76b35-112">PowerShell 5.0 以降、 [Update-dscconfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration)コマンドレット、LCM の構成をプル サーバーからその構成を更新するノードを強制的にします。</span><span class="sxs-lookup"><span data-stu-id="76b35-112">Beginning in PowerShell 5.0, the [Update-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration) cmdlet, forces a Node to update its configuration from the Pull Server configured in the LCM.</span></span>

```powershell
Update-DSCConfiguration -ComputerName "Server01"
```

## <a name="using-invoke-cimmethod"></a><span data-ttu-id="76b35-113">呼び出す CIMMethod を使用します。</span><span class="sxs-lookup"><span data-stu-id="76b35-113">Using Invoke-CIMMethod</span></span>

<span data-ttu-id="76b35-114">PowerShell 4.0 では、プル クライアントを使用してその構成を更新する手動で強制できます[Invoke-cimmethod](/powershell/module/cimcmdlets/invoke-cimmethod)します。</span><span class="sxs-lookup"><span data-stu-id="76b35-114">In PowerShell 4.0, you can still manually force a Pull Client to update its Configuration using [Invoke-CIMMethod](/powershell/module/cimcmdlets/invoke-cimmethod).</span></span> <span data-ttu-id="76b35-115">次の例では、指定した資格情報で CIM セッションを作成するが適切な CIM メソッドを呼び出すおよびセッションを削除します。</span><span class="sxs-lookup"><span data-stu-id="76b35-115">The following example creates a CIM session with specified credentials, invokes the appropriate CIM method, and removes the session.</span></span>

```powershell
$cimSession = New-CimSession -ComputerName "Server01" -Credential $(Get-Credential)
Invoke-CimMethod -CimSession $cimSession -Namespace 'root/microsoft/windows/desiredstateconfiguration' -Class 'MSFT_DscLocalConfigurationManager' -MethodName 'PerformRequiredConfigurationChecks' -Arguments @{ 'Flags' = [uint32]1 } -Verbose
$cimSession | Remove-CimSession
```

## <a name="see-also"></a><span data-ttu-id="76b35-116">参照</span><span class="sxs-lookup"><span data-stu-id="76b35-116">See Also</span></span>

[<span data-ttu-id="76b35-117">PerformRequiredConfigurationChecks</span><span class="sxs-lookup"><span data-stu-id="76b35-117">PerformRequiredConfigurationChecks</span></span>](/powershell/dsc/msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks)
