---
title: "ネットワーク スイッチ マネージャーのコマンドレットの失敗"
contributor: vaibch
ms.openlocfilehash: e32e31762b665a7e2c6f6938fe494cb6127d4264
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
ms.translationtype: HT
ms.contentlocale: ja-JP
---
<span data-ttu-id="3dfde-102">ネットワーク スイッチ マネージャーのコマンドレットを使用すれば、WSMAN 経由でネットワーク スイッチを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="3dfde-102">The Network Switch Manager cmdlets can be used to manage network switches over WSMAN.</span></span> <span data-ttu-id="3dfde-103">このモジュールのコマンドレットの中には、パイプラインからの値を受け入れられるものがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="3dfde-103">A few cmdlets of this module are capable of accepting values from pipelines.</span></span> <span data-ttu-id="3dfde-104">WMF 5.1 プレビューの場合、パイプラインからの値を受け入れ可能なコマンドレットは、値がパイプラインを介して渡されていないと、実行に失敗します。</span><span class="sxs-lookup"><span data-stu-id="3dfde-104">In WMF 5.1 Preview, the cmdlets that can accept value from pipeline fail to execute when the values are not passed through pipelines.</span></span>

<span data-ttu-id="3dfde-105">"InputObject" パラメーターが指定されていない場合、コマンドレットは問題なく実行を継続します。</span><span class="sxs-lookup"><span data-stu-id="3dfde-105">If "InputObject" parameter is not used, the cmdlet should continue to execute without failures.</span></span>

<span data-ttu-id="3dfde-106">影響を受けるコマンドレット、すなわち、パイプラインから "InputObject" パラメーターの値を受け入れることができるコマンドレットの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3dfde-106">Here is the list of affected cmdlets i.e. these cmdlets can accept value for "InputObject" parameter from pipeline.</span></span> <span data-ttu-id="3dfde-107">この値がパイプラインから渡されたものでない場合、コマンドレットの実行は失敗します。</span><span class="sxs-lookup"><span data-stu-id="3dfde-107">If this value is not passed from pipeline the execution of cmdlet will fail.</span></span>

- <span data-ttu-id="3dfde-108">Disable-NetworkSwitchEthernetPort</span><span class="sxs-lookup"><span data-stu-id="3dfde-108">Disable-NetworkSwitchEthernetPort</span></span>
- <span data-ttu-id="3dfde-109">Enable-NetworkSwitchEthernetPort</span><span class="sxs-lookup"><span data-stu-id="3dfde-109">Enable-NetworkSwitchEthernetPort</span></span>
- <span data-ttu-id="3dfde-110">Remove-NetworkSwitchEthernetPortIPAddress</span><span class="sxs-lookup"><span data-stu-id="3dfde-110">Remove-NetworkSwitchEthernetPortIPAddress</span></span>
- <span data-ttu-id="3dfde-111">Set-NetworkSwitchEthernetPortIPAddress</span><span class="sxs-lookup"><span data-stu-id="3dfde-111">Set-NetworkSwitchEthernetPortIPAddress</span></span>
- <span data-ttu-id="3dfde-112">Set-NetworkSwitchPortMode</span><span class="sxs-lookup"><span data-stu-id="3dfde-112">Set-NetworkSwitchPortMode</span></span>
- <span data-ttu-id="3dfde-113">Set-NetworkSwitchPortProperty</span><span class="sxs-lookup"><span data-stu-id="3dfde-113">Set-NetworkSwitchPortProperty</span></span>
- <span data-ttu-id="3dfde-114">Disable-NetworkSwitchFeature</span><span class="sxs-lookup"><span data-stu-id="3dfde-114">Disable-NetworkSwitchFeature</span></span>
- <span data-ttu-id="3dfde-115">Enable-NetworkSwitchFeature</span><span class="sxs-lookup"><span data-stu-id="3dfde-115">Enable-NetworkSwitchFeature</span></span>
- <span data-ttu-id="3dfde-116">Remove-NetworkSwitchVlan</span><span class="sxs-lookup"><span data-stu-id="3dfde-116">Remove-NetworkSwitchVlan</span></span>
- <span data-ttu-id="3dfde-117">Set-NetworkSwitchVlanProperty</span><span class="sxs-lookup"><span data-stu-id="3dfde-117">Set-NetworkSwitchVlanProperty</span></span>

### <a name="resolution"></a><span data-ttu-id="3dfde-118">解決方法</span><span class="sxs-lookup"><span data-stu-id="3dfde-118">Resolution</span></span>
<span data-ttu-id="3dfde-119">InputObject パラメーターの値をパイプラインを介して渡すと、コマンドレットは正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="3dfde-119">The cmdlets work fine when the value of InputObject parameter are passed into it through pipeline.</span></span> <span data-ttu-id="3dfde-120">上記のコマンドレットのいくつかの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3dfde-120">A few examples that work for the above cmdlets are:</span></span>

- <span data-ttu-id="3dfde-121">Disable-NetworkSwitchEthernetPort</span><span class="sxs-lookup"><span data-stu-id="3dfde-121">Disable-NetworkSwitchEthernetPort</span></span>
```powershell
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$port | Disable-NetworkSwitchEthernetPort -CimSession $cimSession
```
- <span data-ttu-id="3dfde-122">Enable-NetworkSwitchEthernetPort</span><span class="sxs-lookup"><span data-stu-id="3dfde-122">Enable-NetworkSwitchEthernetPort</span></span>
```powershell
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$port | Enable-NetworkSwitchEthernetPort -CimSession $cimSession
```

- <span data-ttu-id="3dfde-123">Remove-NetworkSwitchEthernetPortIPAddress</span><span class="sxs-lookup"><span data-stu-id="3dfde-123">Remove-NetworkSwitchEthernetPortIPAddress</span></span>
```powershell
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$port | Remove-NetworkSwitchEthernetPortIPAddress -CimSession $cimSession
```

- <span data-ttu-id="3dfde-124">Set-NetworkSwitchEthernetPortIPAddress</span><span class="sxs-lookup"><span data-stu-id="3dfde-124">Set-NetworkSwitchEthernetPortIPAddress</span></span>
```powershell
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$ipAddress = "192.168.10.1"
$subnetAddress = "255.255.255.0"
$port | Set-NetworkSwitchEthernetPortIPAddress -IpAddress $ipAddress -SubnetAddress $subnetAddress -CimSession $cimSession
```

- <span data-ttu-id="3dfde-125">Set-NetworkSwitchPortProperty</span><span class="sxs-lookup"><span data-stu-id="3dfde-125">Set-NetworkSwitchPortProperty</span></span>
```powershell
$portProperties = @{Caption = "New Caption"}
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$port | Set-NetworkSwitchPortProperty -Property $portProperties -CimSession $cimSession
```

- <span data-ttu-id="3dfde-126">Disable-NetworkSwitchFeature</span><span class="sxs-lookup"><span data-stu-id="3dfde-126">Disable-NetworkSwitchFeature</span></span>
```powershell
$feature = Get-CimInstance -Namespace root/interop -ClassName MSFT_Feature -CimSession $cimSession | Select-Object -First 1
$feature | Disable-NetworkSwitchFeature -CimSession $cimSession
```

- <span data-ttu-id="3dfde-127">Enable-NetworkSwitchFeature</span><span class="sxs-lookup"><span data-stu-id="3dfde-127">Enable-NetworkSwitchFeature</span></span>
```powershell
$feature = Get-CimInstance -Namespace root/interop -ClassName MSFT_Feature -CimSession $cimSession | Select-Object -First 1
$feature | Enable-NetworkSwitchFeature -CimSession $cimSession
```

- <span data-ttu-id="3dfde-128">Set-NetworkSwitchVlanProperty</span><span class="sxs-lookup"><span data-stu-id="3dfde-128">Set-NetworkSwitchVlanProperty</span></span>
```powershell
$properties = @{Caption = "New Caption"}
$vlan = Get-CimInstance -ClassName CIM_NetworkVlan -Namespace root/interop -CimSession $cimSession | Select-Object -First 1
$vlan | Set-NetworkSwitchVlanProperty -Property $properties -CimSession $cimSession
```
