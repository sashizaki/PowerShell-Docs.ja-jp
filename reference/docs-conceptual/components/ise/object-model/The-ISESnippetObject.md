---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: ISESnippetObject
ms.openlocfilehash: f810e6b26f0ded04be15bdc37f336d7890e29dad
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "80500915"
---
# <a name="the-isesnippetobject"></a><span data-ttu-id="05063-103">ISESnippetObject</span><span class="sxs-lookup"><span data-stu-id="05063-103">The ISESnippetObject</span></span>

<span data-ttu-id="05063-104">**ISESnippet** オブジェクトは、Microsoft.PowerShell.Host.ISE.ISESnippet クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="05063-104">An **ISESnippet** object is an instance of the Microsoft.PowerShell.Host.ISE.ISESnippet class.</span></span> <span data-ttu-id="05063-105">`$psISE.CurrentPowerShellTab.Snippets` コレクションのメンバーは、すべて **ISESnippet** オブジェクトの例です。</span><span class="sxs-lookup"><span data-stu-id="05063-105">The members of the `$psISE.CurrentPowerShellTab.Snippets` collection are all examples of **ISESnippet** objects.</span></span> <span data-ttu-id="05063-106">スニペットを作成する最も簡単な方法として、[New-IseSnippet](/powershell/module/ISE/New-IseSnippet) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="05063-106">The easiest way to create a snippet is to use the [New-IseSnippet](/powershell/module/ISE/New-IseSnippet) cmdlet.</span></span>

## <a name="properties"></a><span data-ttu-id="05063-107">Properties</span><span class="sxs-lookup"><span data-stu-id="05063-107">Properties</span></span>

### <a name="author"></a><span data-ttu-id="05063-108">Author</span><span class="sxs-lookup"><span data-stu-id="05063-108">Author</span></span>

<span data-ttu-id="05063-109">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="05063-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="05063-110">スニペットの作成者名を取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="05063-110">The read-only property that gets the name of the author of the snippet.</span></span>

```powershell
# Get the author of the first snippet item
$psISE.CurrentPowerShellTab.Snippets.Item(0).Author
```

### <a name="codefragment"></a><span data-ttu-id="05063-111">CodeFragment</span><span class="sxs-lookup"><span data-stu-id="05063-111">CodeFragment</span></span>

<span data-ttu-id="05063-112">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="05063-112">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="05063-113">エディターに挿入するコード フラグメントを取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="05063-113">The read-only property that gets the code fragment to be inserted into the editor.</span></span>

```powershell
# Get the code fragment associated with the first snippet item.
$psISE.CurrentPowerShellTab.Snippets.Item(0).CodeFragment
```

### <a name="shortcut"></a><span data-ttu-id="05063-114">ショートカット</span><span class="sxs-lookup"><span data-stu-id="05063-114">Shortcut</span></span>

<span data-ttu-id="05063-115">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="05063-115">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="05063-116">メニュー項目の Windows ショートカット キーを取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="05063-116">The read-only property that gets the Windows keyboard shortcut for the menu item.</span></span>

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

## <a name="see-also"></a><span data-ttu-id="05063-117">参照</span><span class="sxs-lookup"><span data-stu-id="05063-117">See Also</span></span>

- [<span data-ttu-id="05063-118">ISESnippetCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="05063-118">The ISESnippetCollection Object</span></span>](The-ISESnippetCollection-Object.md)
- [<span data-ttu-id="05063-119">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="05063-119">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](purpose-of-the-windows-powershell-ise-scripting-object-model.md)
- [<span data-ttu-id="05063-120">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="05063-120">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
