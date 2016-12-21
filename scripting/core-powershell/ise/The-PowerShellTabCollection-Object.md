---
description: 
manager: carmonm
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット"
ms.date: 2016-12-12
title: "PowerShellTabCollection オブジェクト"
ms.technology: powershell
ms.assetid: 81f4bf4a-83bf-415e-8378-1703792fbb58
ms.openlocfilehash: 38bac3445fd94022f03c0f336bd17f9033dfedc2
ms.sourcegitcommit: 8acbf9827ad8f4ef9753f826ecaff58495ca51b0
translationtype: HT
---
# <a name="the-powershelltabcollection-object"></a>PowerShellTabCollection オブジェクト
  **PowerShellTab** コレクション オブジェクトは **PowerShellTab** オブジェクトのコレクションです。 個々の **PowerShellTab** オブジェクトは、個別のランタイム環境として機能します。 これは Microsoft.PowerShell.Host.ISE.PowerShellTabs クラスのインスタンスです。 たとえば **$psISE.PowerShellTabs** オブジェクトです。

## <a name="methods"></a>メソッド

### <a name="add"></a>Add\(\)
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 新しい PowerShell タブをコレクションに追加します。 新しく追加されたタブが返されます。

```
$NewTab=$psISE.PowerShellTabs.Add()
$newTab.DisplayName="Brand New Tab"
```

### <a name="removemicrosoftpowershellhostisepowershelltab-pstab"></a>Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 **psTab** パラメーターにより指定されたタブが削除されます。

 **psTab**
 削除する PowerShell タブ。

```

$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab. 
$newTab.DisplayName="This tab will go away in 5 seconds" 
sleep 5 
$psISE.PowerShellTabs.Remove($newTab)
```

### <a name="setselectedpowershelltabmicrosoftpowershellhostisepowershelltab-pstab"></a>SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 **psTab** パラメーターにより指定された PowerShell タブを選択し、そのタブを現在アクティブな PowerShell タブとして指定します。

 **psTab**
 選択する PowerShell タブ。

```
# Save the current tab in a variable and rename it
$OldTab = $psISE.CurrentPowerShellTab
$psISE.CurrentPowerShellTab.DisplayName="Old Tab"
# Create a new tab and give it a new display name
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName="Brand New Tab" 
# Switch back to the original tab
$psISE.PowerShellTabs.SelectedPowerShellTab=$oldtab
```

## <a name="see-also"></a>参照
- [PowerShellTab オブジェクト](The-PowerShellTab-Object.md) 
- [Windows PowerShell ISE スクリプト オブジェクト モデル](../ise/The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
- [Windows PowerShell ISE オブジェクト モデル リファレンス](../ise/Windows-PowerShell-ISE-Object-Model-Reference.md) 
- [ISE オブジェクト モデルの階層](../ise/The-ISE-Object-Model-Hierarchy.md)

  
