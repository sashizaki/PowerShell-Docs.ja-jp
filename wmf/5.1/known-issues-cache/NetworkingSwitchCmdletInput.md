---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
contributor: vaibch
title: ネットワーク スイッチ マネージャーのコマンドレットの失敗
ms.openlocfilehash: 626809513e7a8f1aa2c47a48c74e69ca4077f598
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
ネットワーク スイッチ マネージャーのコマンドレットを使用すれば、WSMAN 経由でネットワーク スイッチを管理することができます。
このモジュールのコマンドレットの中には、パイプラインからの値を受け入れられるものがいくつかあります。
WMF 5.1 プレビューの場合、パイプラインからの値を受け入れ可能なコマンドレットは、値がパイプラインを介して渡されていないと、実行に失敗します。

"InputObject" パラメーターが指定されていない場合、コマンドレットは問題なく実行を継続します。

影響を受けるコマンドレット、すなわち、パイプラインから "InputObject" パラメーターの値を受け入れることができるコマンドレットの一覧を次に示します。
この値がパイプラインから渡されたものでない場合、コマンドレットの実行は失敗します。

- Disable-NetworkSwitchEthernetPort
- Enable-NetworkSwitchEthernetPort
- Remove-NetworkSwitchEthernetPortIPAddress
- Set-NetworkSwitchEthernetPortIPAddress
- Set-NetworkSwitchPortMode
- Set-NetworkSwitchPortProperty
- Disable-NetworkSwitchFeature
- Enable-NetworkSwitchFeature
- Remove-NetworkSwitchVlan
- Set-NetworkSwitchVlanProperty

### <a name="resolution"></a>解決方法
InputObject パラメーターの値をパイプラインを介して渡すと、コマンドレットは正常に動作します。 上記のコマンドレットのいくつかの使用例を次に示します。

- Disable-NetworkSwitchEthernetPort
```powershell
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$port | Disable-NetworkSwitchEthernetPort -CimSession $cimSession
```

- Enable-NetworkSwitchEthernetPort
```powershell
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$port | Enable-NetworkSwitchEthernetPort -CimSession $cimSession
```

- Remove-NetworkSwitchEthernetPortIPAddress
```powershell
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$port | Remove-NetworkSwitchEthernetPortIPAddress -CimSession $cimSession
```

- Set-NetworkSwitchEthernetPortIPAddress
```powershell
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$ipAddress = "192.168.10.1"
$subnetAddress = "255.255.255.0"
$port | Set-NetworkSwitchEthernetPortIPAddress -IpAddress $ipAddress -SubnetAddress $subnetAddress -CimSession $cimSession
```

- Set-NetworkSwitchPortProperty
```powershell
$portProperties = @{Caption = "New Caption"}
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$port | Set-NetworkSwitchPortProperty -Property $portProperties -CimSession $cimSession
```

- Disable-NetworkSwitchFeature
```powershell
$feature = Get-CimInstance -Namespace root/interop -ClassName MSFT_Feature -CimSession $cimSession | Select-Object -First 1
$feature | Disable-NetworkSwitchFeature -CimSession $cimSession
```

- Enable-NetworkSwitchFeature
```powershell
$feature = Get-CimInstance -Namespace root/interop -ClassName MSFT_Feature -CimSession $cimSession | Select-Object -First 1
$feature | Enable-NetworkSwitchFeature -CimSession $cimSession
```

- Set-NetworkSwitchVlanProperty
```powershell
$properties = @{Caption = "New Caption"}
$vlan = Get-CimInstance -ClassName CIM_NetworkVlan -Namespace root/interop -CimSession $cimSession | Select-Object -First 1
$vlan | Set-NetworkSwitchVlanProperty -Property $properties -CimSession $cimSession
```