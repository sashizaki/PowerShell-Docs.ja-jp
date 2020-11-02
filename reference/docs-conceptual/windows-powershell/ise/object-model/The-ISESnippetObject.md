---
ms.date: 06/05/2017
title: ISESnippetObject
description: ISESnippet オブジェクトは、Microsoft.PowerShell.Host.ISE.ISESnippet クラスのインスタンスです。
ms.openlocfilehash: 602b344686cbcfb1e994914d4e26438ff7e4b1de
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663409"
---
# <a name="the-isesnippetobject"></a>ISESnippetObject

**ISESnippet** オブジェクトは、Microsoft.PowerShell.Host.ISE.ISESnippet クラスのインスタンスです。 `$psISE.CurrentPowerShellTab.Snippets` コレクションのメンバーは、すべて **ISESnippet** オブジェクトの例です。 スニペットを作成する最も簡単な方法として、[New-IseSnippet](/powershell/module/ISE/New-IseSnippet) コマンドレットを使用します。

## <a name="properties"></a>Properties

### <a name="author"></a>Author

Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。

スニペットの作成者名を取得する読み取り専用プロパティ。

```powershell
# Get the author of the first snippet item
$psISE.CurrentPowerShellTab.Snippets.Item(0).Author
```

### <a name="codefragment"></a>CodeFragment

Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。

エディターに挿入するコード フラグメントを取得する読み取り専用プロパティ。

```powershell
# Get the code fragment associated with the first snippet item.
$psISE.CurrentPowerShellTab.Snippets.Item(0).CodeFragment
```

### <a name="shortcut"></a>ショートカット

Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。

メニュー項目の Windows ショートカット キーを取得する読み取り専用プロパティ。

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

## <a name="see-also"></a>参照

- [ISESnippetCollection オブジェクト](The-ISESnippetCollection-Object.md)
- [Windows PowerShell ISE スクリプト オブジェクト モデルの目的](purpose-of-the-windows-powershell-ise-scripting-object-model.md)
- [ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)
