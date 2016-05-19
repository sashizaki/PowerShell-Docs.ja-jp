---
title: Windows PowerShell ISE オブジェクト モデル リファレンス
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e1a9e7d1-0fd5-47de-8d9b-f1be1ed13b0c
---
# Windows PowerShell ISE オブジェクト モデル リファレンス
  
## オブジェクト モデル リファレンス
 このセクションでは、Windows PowerShellÂ® Integrated Scripting Environment (ISE) でさまざまなオブジェクトを定義する基礎となるクラスのリファレンスを示します。 階層構造のオブジェクトを確認するには、[ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)に関するページを参照してください。.

 [ISEAddOnTool オブジェクト](The-ISEAddOnTool-Object.md)
 例: $psISE.CurrentVisibleHorizontalTool、$psISE.CurrentVisibleVerticalTool 。

 [ISEAddOnTool オブジェクト](The-ISEAddOnTool-Object.md)
  [ISEEditor オブジェクト](The-ISEEditor-Object.md)
 例: $psISE.CurrentFile.Editor、$psISE.CurrentPowerShellTab.Output、$psISE.CurrentPowerShellTab.CommandPane。

 [ISEFile オブジェクト](The-ISEFile-Object.md)
 例: $psISE.CurrentFile、$psISE.PowerShellTabs.Files\[0\]。

 [ISEFileCollection オブジェクト](The-ISEFileCollection-Object.md)
 例: $psISE.PowerShellTabs.Files。

 [ISEMenuItem オブジェクト](The-ISEMenuItem-Object.md)
 例: $psISE.CurrentPowerShellTab.AddOnsMenu、$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus\[0\]。

 [ISEMenuItemCollection オブジェクト](The-ISEMenuItemCollection-Object.md)
 例: $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus。

 [ISEOptions オブジェクト](The-ISEOptions-Object.md)
 例: $psISE.Options、$psISE.Options.DefaultOptions。

 [ObjectModelRoot オブジェクト](The-ObjectModelRoot-Object.md)
 例: ルート $psISE オブジェクト。

 [PowerShellTab オブジェクト](The-PowerShellTab-Object.md)
 例: $psISE.CurrentPowerShellTab、$psISE.PowerShellTabs\[0\]。

 [PowerShellTabCollection オブジェクト](The-PowerShellTabCollection-Object.md)
 例: $psISE.PowerShellTabs。

## 参照
 [Windows PowerShell ISE スクリプト オブジェクト モデル](The-Windows-PowerShell-ISE-Scripting-Object-Model.md)

  


<!--HONumber=May16_HO2-->


