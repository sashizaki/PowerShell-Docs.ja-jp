---
ms.date: 2017-06-05T00:00:00.000Z
keywords: "PowerShell, コマンドレット"
title: ISESnippetObject
ms.assetid: 98bc8113-c3cd-4201-bdb9-9d9bdb7e266c
ms.openlocfilehash: 5cc49cd504a1343a5737f78eb886bb41591d087d
ms.sourcegitcommit: 74255f0b5f386a072458af058a15240140acb294
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2017
---
# <a name="the-isesnippetobject"></a>ISESnippetObject
  **ISESnippet** オブジェクトは、Microsoft.PowerShell.Host.ISE.ISESnippet クラスのインスタンスです。 **$psISE.CurrentPowerShellTab.Snippets** コレクションのメンバーは、すべて **ISESnippet** オブジェクトの例です。 スニペットを作成する最も簡単な方法として、[New-IseSnippet&#91;PSITPro5_ISE&#93;](https://technet.microsoft.com/en-us/library/0a6339a3-2683-4a8e-8929-90ad9a95c3e0) コマンドレットを使用します。

## <a name="properties"></a>プロパティ

###  <a name="DisplayName"></a> Author
  Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。 

 スニペットの作成者名を取得する読み取り専用プロパティ。

```
# Get the author of the first snippet item
$psISE.CurrentPowerShellTab.Snippets.Item(0).Author

```

###  <a name="Action"></a> CodeFragment
  Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。 

 エディターに挿入するコード フラグメントを取得する読み取り専用プロパティ。

```
# Get the code fragment associated with the first snippet item.
$psISE.CurrentPowerShellTab.Snippets.Item(0).CodeFragment

```

###  <a name="Shortcut"></a> Shortcut
  Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。 

 メニュー項目の Windows ショートカット キーを取得する読み取り専用プロパティ。

```
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add("_Process",{get-process},"Alt+P")
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

## <a name="see-also"></a>参照
- [ISESnippetCollection オブジェクト](The-ISESnippetCollection-Object.md) 
- [Windows PowerShell ISE スクリプト オブジェクト モデル](The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
- [Windows PowerShell ISE オブジェクト モデル リファレンス](Windows-PowerShell-ISE-Object-Model-Reference.md) 
- [ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)

  
