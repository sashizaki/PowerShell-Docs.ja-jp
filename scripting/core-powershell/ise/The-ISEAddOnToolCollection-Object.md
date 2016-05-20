---
title: ISEAddOnToolCollection オブジェクト
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 634eab89-0845-4016-974b-361b09bb8f7b
---
# ISEAddOnToolCollection オブジェクト
  **ISEAddOnToolCollection** オブジェクトは、**ISEAddOnTool** オブジェクトのコレクションです。 例としては、 **$psISE.CurrentPowerShellTab.VerticalAddOnTools** オブジェクトです。

## メソッド

### Add\( Name, ControlType, \[IsVisible\] \)
  Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。 

 新しいアドオン ツールをコレクションに追加します。 新しく追加されたアドオン ツールが返されます。 このコマンドを実行する前に、ローカル コンピューターにアドオン ツールをインストールし、アセンブリを読み込む必要があります。

 **Name** – 文字列
 Windows PowerShell ISE に追加するアドオン ツールの表示名を指定します。

 **ControlType** – 種類
 追加するコントロールを指定します。

 **\[IsVisible\]** – 省略可能なブール値
 **$true** に設定すると、アドオン ツールは、関連付けられているツール ウィンドウに直ちに表示されます。

```
# Load a DLL with an add-on and then add it to the ISE
[reflection.assembly]::LoadFile("c:\test\ISESimpleSolution\ISESimpleSolution.dll")
$psISE.CurrentPowerShellTab.VerticalAddOnTools.Add("Solutions", [ISESimpleSolution.Solution], $true)

```

### Remove\( Item \)
  Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。 

 コレクションから指定したアドオン ツールを削除します。

 **Item** – Microsoft.PowerShell.Host.ISE.ISEAddOnTool
 Windows PowerShell ISE から削除するオブジェクトを指定します。

```
# Load a DLL with an add-on and then add it to the ISE
[reflection.assembly]::LoadFile("c:\test\ISESimpleSolution\ISESimpleSolution.dll")
$psISE.CurrentPowerShellTab.VerticalAddOnTools.Add("Solutions", [ISESimpleSolution.Solution], $true)

```

### SetSelectedPowerShellTab\( psTab \)
  Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。 

 **psTab** パラメーターが指定する PowerShell タブを選択します。

 **psTab** – Microsoft.PowerShell.Host.ISE.PowerShellTab
 選択する PowerShell タブ。

```

      $newTab = $psISE.PowerShellTabs.Add()
# Change the DisplayName of the new PowerShell tab. 
$newTab.DisplayName="Brand New Tab"

```

### Remove\( psTab \)
  Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。 

 **psTab** パラメーターが指定する PowerShell タブを削除します。

 **psTab** – Microsoft.PowerShell.Host.ISE.PowerShellTab
 削除する PowerShell タブ。

```

$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab. 
$newTab.DisplayName="This tab will go away in 5 seconds" 
sleep 5 
$psISE.PowerShellTabs.Remove($newTab)
```

## 参照
 [PowerShellTab オブジェクト](The-PowerShellTab-Object.md) 
 [Windows PowerShell ISE スクリプト オブジェクト モデル](The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
 [Windows PowerShell ISE オブジェクト モデル リファレンス](Windows-PowerShell-ISE-Object-Model-Reference.md) 
 [ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)

  


<!--HONumber=May16_HO2-->


