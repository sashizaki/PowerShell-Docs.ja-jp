---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "ISEAddOnToolCollection オブジェクト"
ms.assetid: 634eab89-0845-4016-974b-361b09bb8f7b
ms.openlocfilehash: 09088c9e7307a26b86e82f2dc10d2648213c6bd2
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="the-iseaddontoolcollection-object"></a>ISEAddOnToolCollection オブジェクト
  **ISEAddOnToolCollection** オブジェクトは、**ISEAddOnTool** オブジェクトのコレクションです。 例としては、**$psISE.CurrentPowerShellTab.VerticalAddOnTools** オブジェクトです。

## <a name="methods"></a>メソッド

### <a name="add-name-controltype-isvisible-"></a>Add\( Name、ControlType、\[IsVisible\] \)
  Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。 

 新しいアドオン ツールをコレクションに追加します。 新しく追加されたアドオン ツールが返されます。 このコマンドを実行する前に、ローカル コンピューターにアドオン ツールをインストールし、アセンブリを読み込む必要があります。

 **Name** - Windows PowerShell ISE に追加するアドオン ツールの表示名を指定する文字列。

 **ControlType** - 追加するコントロールを指定する種類。

 **\[IsVisible\]** - 省略可能なブール値は、**$true** に設定すると、アドオン ツールが、関連付けられているツール ウィンドウに直ちに表示されます。

```PowerShell
# Load a DLL with an add-on and then add it to the ISE
[reflection.assembly]::LoadFile("c:\test\ISESimpleSolution\ISESimpleSolution.dll")
$psISE.CurrentPowerShellTab.VerticalAddOnTools.Add("Solutions", [ISESimpleSolution.Solution], $true)
```

### <a name="remove-item-"></a>Remove\( Item \)
  Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。 

 コレクションから指定したアドオン ツールを削除します。

 **Item** - Microsoft.PowerShell.Host.ISE.ISEAddOnTool Windows PowerShell ISE から削除するオブジェクトを指定します。

```PowerShell
# Load a DLL with an add-on and then add it to the ISE
[reflection.assembly]::LoadFile("c:\test\ISESimpleSolution\ISESimpleSolution.dll")
$psISE.CurrentPowerShellTab.VerticalAddOnTools.Add("Solutions", [ISESimpleSolution.Solution], $true)
```

### <a name="setselectedpowershelltab-pstab-"></a>SetSelectedPowerShellTab\( psTab \)
  Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。 

 **psTab** パラメーターが指定する PowerShell タブを選択します。

 **psTab** - PowerShell タブが選択するMicrosoft.PowerShell.Host.ISE.PowerShellTab。

```PowerShell
      $newTab = $psISE.PowerShellTabs.Add()
# Change the DisplayName of the new PowerShell tab. 
$newTab.DisplayName="Brand New Tab"
```

### <a name="remove-pstab-"></a>Remove\( psTab \)
  Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。 

 **psTab** パラメーターが指定する PowerShell タブを削除します。

 **psTab** - PowerShell タブが削除する Microsoft.PowerShell.Host.ISE.PowerShellTab。

```PowerShell
$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab. 
$newTab.DisplayName="This tab will go away in 5 seconds" 
sleep 5 
$psISE.PowerShellTabs.Remove($newTab)
```

## <a name="see-also"></a>参照
- [PowerShellTab オブジェクト](The-PowerShellTab-Object.md) 
- [Windows PowerShell ISE スクリプト オブジェクト モデル](The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
- [Windows PowerShell ISE オブジェクト モデル リファレンス](Windows-PowerShell-ISE-Object-Model-Reference.md) 
- [ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)

  