---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: ISESnippetObject
ms.openlocfilehash: 60456ec90f56753fa96f141b8b8299ef3f7e41c9
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736966"
---
# <a name="the-isesnippetobject"></a>ISESnippetObject

**ISESnippet** オブジェクトは、Microsoft.PowerShell.Host.ISE.ISESnippet クラスのインスタンスです。 `$psISE.CurrentPowerShellTab.Snippets` コレクションのメンバーは、すべて **ISESnippet** オブジェクトの例です。 スニペットを作成する最も簡単な方法として、[New-IseSnippet](/reference/5.1/ISE/New-IseSnippet.md) コマンドレットを使用します。

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
