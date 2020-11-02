---
ms.date: 06/05/2017
title: PowerShellTabCollection オブジェクト
description: PowerShellTab コレクション オブジェクトは PowerShellTab オブジェクトのコレクションです。 個々の PowerShellTab オブジェクトは、個別のランタイム環境として機能します。
ms.openlocfilehash: 60f8001f096b50bd8433a5685f1f70a350f07f61
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658276"
---
# <a name="the-powershelltabcollection-object"></a>PowerShellTabCollection オブジェクト

**PowerShellTab** コレクション オブジェクトは **PowerShellTab** オブジェクトのコレクションです。 個々の **PowerShellTab** オブジェクトは、個別のランタイム環境として機能します。 これは Microsoft.PowerShell.Host.ISE.PowerShellTabs クラスのインスタンスです。 例は、`$psISE.PowerShellTabs` オブジェクトです。

## <a name="methods"></a>メソッド

### <a name="add"></a>Add\(\)

Windows PowerShell ISE 2.0 以降でサポートされています。

新しい PowerShell タブをコレクションに追加します。 新しく追加されたタブが返されます。

```powershell
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
```

### <a name="removemicrosoftpowershellhostisepowershelltab-pstab"></a>Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)

Windows PowerShell ISE 2.0 以降でサポートされています。

**psTab** パラメーターにより指定されたタブが削除されます。

**psTab** 削除する PowerShell タブ。

```powershell
$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab.
$newTab.DisplayName = 'This tab will go away in 5 seconds'
sleep 5
$psISE.PowerShellTabs.Remove($newTab)
```

### <a name="setselectedpowershelltabmicrosoftpowershellhostisepowershelltab-pstab"></a>SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)

Windows PowerShell ISE 2.0 以降でサポートされています。

**psTab** パラメーターにより指定された PowerShell タブを選択し、そのタブを現在アクティブな PowerShell タブとして指定します。

**psTab** 選択する PowerShell タブ。

```powershell
# Save the current tab in a variable and rename it
$oldTab = $psISE.CurrentPowerShellTab
$psISE.CurrentPowerShellTab.DisplayName = 'Old Tab'
# Create a new tab and give it a new display name
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
# Switch back to the original tab
$psISE.PowerShellTabs.SelectedPowerShellTab = $oldTab
```

## <a name="see-also"></a>参照

- [PowerShellTab オブジェクト](The-PowerShellTab-Object.md)
- [Windows PowerShell ISE スクリプト オブジェクト モデルの目的](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)
