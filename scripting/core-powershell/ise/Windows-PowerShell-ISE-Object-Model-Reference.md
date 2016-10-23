---
title: "Windows PowerShell ISE オブジェクト モデル リファレンス"
ms.date: 2016-05-11
keywords: "powershell,コマンドレット"
description: 
ms.topic: article
author: jpjofre
manager: dongill
ms.prod: powershell
ms.assetid: e1a9e7d1-0fd5-47de-8d9b-f1be1ed13b0c
translationtype: Human Translation
ms.sourcegitcommit: 16608d8b97ec816d77ec7b8ac2438a4d64b55fba
ms.openlocfilehash: c60a7adb5cce55392d5dc09c7ca357bfc4c73e15

---

# Windows PowerShell ISE オブジェクト モデル リファレンス
  
## オブジェクト モデル リファレンス
 このセクションでは、Windows PowerShell® Integrated Scripting Environment (ISE) で各種オブジェクトを定義する基礎となるクラスへのリファレンスを提供します。 これらのオブジェクトの階層構造については、「[ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)」を参照してください。

 [ISEAddOnTool オブジェクト](The-ISEAddOnTool-Object.md)
 例: $psISE.CurrentVisibleHorizontalTool、$psISE.CurrentVisibleVerticalTool。

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
- [Windows PowerShell ISE スクリプト オブジェクト モデル](The-Windows-PowerShell-ISE-Scripting-Object-Model.md)

  



<!--HONumber=Oct16_HO1-->


