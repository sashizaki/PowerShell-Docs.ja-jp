---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell ISE オブジェクト モデル リファレンス"
ms.assetid: e1a9e7d1-0fd5-47de-8d9b-f1be1ed13b0c
ms.openlocfilehash: e5d4ae03158d9b5b0efd98db1272bc13872181ac
ms.sourcegitcommit: 74255f0b5f386a072458af058a15240140acb294
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2017
---
# <a name="windows-powershell-ise-object-model-reference"></a>Windows PowerShell ISE オブジェクト モデル リファレンス
  
## <a name="object-model-reference"></a>オブジェクト モデル リファレンス
 このセクションでは、Windows PowerShell® Integrated Scripting Environment (ISE) で各種オブジェクトを定義する基礎となるクラスへのリファレンスを提供します。 これらのオブジェクトの階層構造については、「[ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)」を参照してください。

 [ISEAddOnTool オブジェクト](The-ISEAddOnTool-Object.md) 例: $psISE.CurrentVisibleHorizontalTool、$psISE.CurrentVisibleVerticalTool。

 [ISEAddOnTool オブジェクト](The-ISEAddOnTool-Object.md)[ISEEditor オブジェクト](The-ISEEditor-Object.md) 例: $psISE.CurrentFile.Editor、$psISE.CurrentPowerShellTab.Output、$psISE.CurrentPowerShellTab.CommandPane。

 [ISEFile オブジェクト](The-ISEFile-Object.md) 例: $psISE.CurrentFile、$psISE.PowerShellTabs.Files\[0\]。

 [ISEFileCollection オブジェクト](The-ISEFileCollection-Object.md) 例: $psISE.PowerShellTabs.Files。

 [ISEMenuItem オブジェクト](The-ISEMenuItem-Object.md) 例: $psISE.CurrentPowerShellTab.AddOnsMenu、$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus\[0\]。

 [ISEMenuItemCollection オブジェクト](The-ISEMenuItemCollection-Object.md) 例: $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus。

 [ISEOptions オブジェクト](The-ISEOptions-Object.md) 例: $psISE.Options、$psISE.Options.DefaultOptions。

 [ObjectModelRoot オブジェクト](The-ObjectModelRoot-Object.md) 例: ルート $psISE オブジェクト。

 [PowerShellTab オブジェクト](The-PowerShellTab-Object.md) 例: $psISE.CurrentPowerShellTab、$psISE.PowerShellTabs\[0\]。

 [PowerShellTabCollection オブジェクト](The-PowerShellTabCollection-Object.md) 例: $psISE.PowerShellTabs。

## <a name="see-also"></a>参照
- [Windows PowerShell ISE スクリプト オブジェクト モデル](The-Windows-PowerShell-ISE-Scripting-Object-Model.md)

  
