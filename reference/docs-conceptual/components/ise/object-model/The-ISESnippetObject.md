---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: ISESnippetObject
ms.openlocfilehash: 62d470569deb051fca80005235d4c492319cf5ec
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "67028894"
---
# <a name="the-isesnippetobject"></a>ISESnippetObject

**ISESnippet** オブジェクトは、Microsoft.PowerShell.Host.ISE.ISESnippet クラスのインスタンスです。 **$psISE.CurrentPowerShellTab.Snippets** コレクションのメンバーは、すべて **ISESnippet** オブジェクトの例です。 スニペットを作成する最も簡単な方法として、[New-IseSnippet&#91;PSITPro5_ISE&#93;](https://technet.microsoft.com/library/0a6339a3-2683-4a8e-8929-90ad9a95c3e0) コマンドレットを使用します。

## <a name="properties"></a>プロパティ

### <a name="author"></a>作成者

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

### <a name="shortcut"></a>Shortcut

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
