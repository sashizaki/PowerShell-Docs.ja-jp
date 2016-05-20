---
title: ISEMenuItemCollection オブジェクト
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0c0f5484-3320-408e-8534-5bd1c8e48512
---
# ISEMenuItemCollection オブジェクト
  **ISEMenuItemCollection** オブジェクトは、**ISEMenuItem** オブジェクトのコレクションです。 これは Microsoft.PowerShell.Host.ISE.ISEMenuItemCollection クラスのインスタンスです。 例としては、Windows PowerShellÂ® Integrated Scripting Environment (ISE) の **アドオン** メニューをカスタマイズするために使用される **$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus** オブジェクトです。

## 方法

### Add\(string DisplayName, System.Management.Automation.ScriptBlock Action, System.Windows.Input.KeyGesture Shortcut \)
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 メニュー項目をコレクションに追加します。

 **表示名**
 追加するメニューの表示名。

 **操作**
 このメニュー項目に関連付けられるアクションを指定する **System.Management.Automation.ScriptBlock** オブジェクト。

 **Shortcut**
 アクションのキーボード ショートカット。

 **戻り値**
 追加した ISEMenuItem オブジェクト。

```
# Create an Add-ons menu with an fast access key and a shortcut.
# Note the use of "_"  as opposed to the "&" for mapping to the fast access key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add("_Process",{get-process},"Alt+P")
```

### Clear\(\)
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 メニュー項目からすべてのサブメニューを削除します。

```
# Remove all custom submenu items from the AddOns menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()

```

## 参照
 [ISEMenuItem オブジェクト](The-ISEMenuItem-Object.md) 
 [Windows PowerShell ISE スクリプト オブジェクト モデル](The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
 [Windows PowerShell ISE オブジェクト モデル リファレンス](Windows-PowerShell-ISE-Object-Model-Reference.md) 
 [ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)

  


<!--HONumber=May16_HO2-->


