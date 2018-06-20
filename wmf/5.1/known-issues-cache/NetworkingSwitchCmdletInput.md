---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.topic: conceptual
contributor: vaibch
title: ネットワーク スイッチ マネージャーのコマンドレットの失敗
ms.openlocfilehash: 197a25411a82e5d256a9420706535d5411991f1b
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
ms.locfileid: "34188685"
---
<span data-ttu-id="ddec9-103">ネットワーク スイッチ マネージャーのコマンドレットを使用すれば、WSMAN 経由でネットワーク スイッチを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="ddec9-103">The Network Switch Manager cmdlets can be used to manage network switches over WSMAN.</span></span>
<span data-ttu-id="ddec9-104">このモジュールのコマンドレットの中には、パイプラインからの値を受け入れられるものがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="ddec9-104">A few cmdlets of this module are capable of accepting values from pipelines.</span></span>
<span data-ttu-id="ddec9-105">WMF 5.1 プレビューの場合、パイプラインからの値を受け入れ可能なコマンドレットは、値がパイプラインを介して渡されていないと、実行に失敗します。</span><span class="sxs-lookup"><span data-stu-id="ddec9-105">In WMF 5.1 Preview, the cmdlets that can accept value from pipeline fail to execute when the values are not passed through pipelines.</span></span>

<span data-ttu-id="ddec9-106">"InputObject" パラメーターが指定されていない場合、コマンドレットは問題なく実行を継続します。</span><span class="sxs-lookup"><span data-stu-id="ddec9-106">If "InputObject" parameter is not used, the cmdlet should continue to execute without failures.</span></span>

<span data-ttu-id="ddec9-107">影響を受けるコマンドレット、すなわち、パイプラインから "InputObject" パラメーターの値を受け入れることができるコマンドレットの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ddec9-107">Here is the list of affected cmdlets i.e. these cmdlets can accept value for "InputObject" parameter from pipeline.</span></span>
<span data-ttu-id="ddec9-108">この値がパイプラインから渡されたものでない場合、コマンドレットの実行は失敗します。</span><span class="sxs-lookup"><span data-stu-id="ddec9-108">If this value is not passed from pipeline the execution of cmdlet will fail.</span></span>

- <span data-ttu-id="ddec9-109">Disable-NetworkSwitchEthernetPort</span><span class="sxs-lookup"><span data-stu-id="ddec9-109">Disable-NetworkSwitchEthernetPort</span></span>
- <span data-ttu-id="ddec9-110">Enable-NetworkSwitchEthernetPort</span><span class="sxs-lookup"><span data-stu-id="ddec9-110">Enable-NetworkSwitchEthernetPort</span></span>
- <span data-ttu-id="ddec9-111">Remove-NetworkSwitchEthernetPortIPAddress</span><span class="sxs-lookup"><span data-stu-id="ddec9-111">Remove-NetworkSwitchEthernetPortIPAddress</span></span>
- <span data-ttu-id="ddec9-112">Set-NetworkSwitchEthernetPortIPAddress</span><span class="sxs-lookup"><span data-stu-id="ddec9-112">Set-NetworkSwitchEthernetPortIPAddress</span></span>
- <span data-ttu-id="ddec9-113">Set-NetworkSwitchPortMode</span><span class="sxs-lookup"><span data-stu-id="ddec9-113">Set-NetworkSwitchPortMode</span></span>
- <span data-ttu-id="ddec9-114">Set-NetworkSwitchPortProperty</span><span class="sxs-lookup"><span data-stu-id="ddec9-114">Set-NetworkSwitchPortProperty</span></span>
- <span data-ttu-id="ddec9-115">Disable-NetworkSwitchFeature</span><span class="sxs-lookup"><span data-stu-id="ddec9-115">Disable-NetworkSwitchFeature</span></span>
- <span data-ttu-id="ddec9-116">Enable-NetworkSwitchFeature</span><span class="sxs-lookup"><span data-stu-id="ddec9-116">Enable-NetworkSwitchFeature</span></span>
- <span data-ttu-id="ddec9-117">Remove-NetworkSwitchVlan</span><span class="sxs-lookup"><span data-stu-id="ddec9-117">Remove-NetworkSwitchVlan</span></span>
- <span data-ttu-id="ddec9-118">Set-NetworkSwitchVlanProperty</span><span class="sxs-lookup"><span data-stu-id="ddec9-118">Set-NetworkSwitchVlanProperty</span></span>

### <a name="resolution"></a><span data-ttu-id="ddec9-119">解決方法</span><span class="sxs-lookup"><span data-stu-id="ddec9-119">Resolution</span></span>
<span data-ttu-id="ddec9-120">InputObject パラメーターの値をパイプラインを介して渡すと、コマンドレットは正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="ddec9-120">The cmdlets work fine when the value of InputObject parameter are passed into it through pipeline.</span></span> <span data-ttu-id="ddec9-121">上記のコマンドレットのいくつかの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ddec9-121">A few examples that work for the above cmdlets are:</span></span>

- <span data-ttu-id="ddec9-122">Disable-NetworkSwitchEthernetPort</span><span class="sxs-lookup"><span data-stu-id="ddec9-122">Disable-NetworkSwitchEthernetPort</span></span>
```powershell
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$port | Disable-NetworkSwitchEthernetPort -CimSession $cimSession
```

- <span data-ttu-id="ddec9-123">Enable-NetworkSwitchEthernetPort</span><span class="sxs-lookup"><span data-stu-id="ddec9-123">Enable-NetworkSwitchEthernetPort</span></span>
```powershell
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$port | Enable-NetworkSwitchEthernetPort -CimSession $cimSession
```

- <span data-ttu-id="ddec9-124">Remove-NetworkSwitchEthernetPortIPAddress</span><span class="sxs-lookup"><span data-stu-id="ddec9-124">Remove-NetworkSwitchEthernetPortIPAddress</span></span>
```powershell
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$port | Remove-NetworkSwitchEthernetPortIPAddress -CimSession $cimSession
```

- <span data-ttu-id="ddec9-125">Set-NetworkSwitchEthernetPortIPAddress</span><span class="sxs-lookup"><span data-stu-id="ddec9-125">Set-NetworkSwitchEthernetPortIPAddress</span></span>
```powershell
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$ipAddress = "192.168.10.1"
$subnetAddress = "255.255.255.0"
$port | Set-NetworkSwitchEthernetPortIPAddress -IpAddress $ipAddress -SubnetAddress $subnetAddress -CimSession $cimSession
```

- <span data-ttu-id="ddec9-126">Set-NetworkSwitchPortProperty</span><span class="sxs-lookup"><span data-stu-id="ddec9-126">Set-NetworkSwitchPortProperty</span></span>
```powershell
$portProperties = @{Caption = "New Caption"}
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$port | Set-NetworkSwitchPortProperty -Property $portProperties -CimSession $cimSession
```

- <span data-ttu-id="ddec9-127">Disable-NetworkSwitchFeature</span><span class="sxs-lookup"><span data-stu-id="ddec9-127">Disable-NetworkSwitchFeature</span></span>
```powershell
$feature = Get-CimInstance -Namespace root/interop -ClassName MSFT_Feature -CimSession $cimSession | Select-Object -First 1
$feature | Disable-NetworkSwitchFeature -CimSession $cimSession
```

- <span data-ttu-id="ddec9-128">Enable-NetworkSwitchFeature</span><span class="sxs-lookup"><span data-stu-id="ddec9-128">Enable-NetworkSwitchFeature</span></span>
```powershell
$feature = Get-CimInstance -Namespace root/interop -ClassName MSFT_Feature -CimSession $cimSession | Select-Object -First 1
$feature | Enable-NetworkSwitchFeature -CimSession $cimSession
```

- <span data-ttu-id="ddec9-129">Set-NetworkSwitchVlanProperty</span><span class="sxs-lookup"><span data-stu-id="ddec9-129">Set-NetworkSwitchVlanProperty</span></span>
```powershell
$properties = @{Caption = "New Caption"}
$vlan = Get-CimInstance -ClassName CIM_NetworkVlan -Namespace root/interop -CimSession $cimSession | Select-Object -First 1
$vlan | Set-NetworkSwitchVlanProperty -Property $properties -CimSession $cimSession
```
