---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: ISESnippetObject
ms.assetid: 98bc8113-c3cd-4201-bdb9-9d9bdb7e266c
ms.openlocfilehash: 5cc49cd504a1343a5737f78eb886bb41591d087d
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="the-isesnippetobject"></a><span data-ttu-id="69431-103">ISESnippetObject</span><span class="sxs-lookup"><span data-stu-id="69431-103">The ISESnippetObject</span></span>
  <span data-ttu-id="69431-104">**ISESnippet** オブジェクトは、Microsoft.PowerShell.Host.ISE.ISESnippet クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="69431-104">An **ISESnippet** object is an instance of the Microsoft.PowerShell.Host.ISE.ISESnippet class.</span></span> <span data-ttu-id="69431-105">**$psISE.CurrentPowerShellTab.Snippets** コレクションのメンバーは、すべて **ISESnippet** オブジェクトの例です。</span><span class="sxs-lookup"><span data-stu-id="69431-105">The members of the **$psISE.CurrentPowerShellTab.Snippets** collection are all examples of **ISESnippet** objects.</span></span> <span data-ttu-id="69431-106">スニペットを作成する最も簡単な方法として、[New-IseSnippet&#91;PSITPro5_ISE&#93;](https://technet.microsoft.com/en-us/library/0a6339a3-2683-4a8e-8929-90ad9a95c3e0) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="69431-106">The easiest way to create a snippet is to use the [New-IseSnippet&#91;PSITPro5_ISE&#93;](https://technet.microsoft.com/en-us/library/0a6339a3-2683-4a8e-8929-90ad9a95c3e0) cmdlet.</span></span>

## <a name="properties"></a><span data-ttu-id="69431-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="69431-107">Properties</span></span>

###  <span data-ttu-id="69431-108"><a name="DisplayName"></a> Author</span><span class="sxs-lookup"><span data-stu-id="69431-108"><a name="DisplayName"></a> Author</span></span>
  <span data-ttu-id="69431-109">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="69431-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="69431-110">スニペットの作成者名を取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="69431-110">The read-only property that gets the name of the author of the snippet.</span></span>

```
# Get the author of the first snippet item
$psISE.CurrentPowerShellTab.Snippets.Item(0).Author

```

###  <span data-ttu-id="69431-111"><a name="Action"></a> CodeFragment</span><span class="sxs-lookup"><span data-stu-id="69431-111"><a name="Action"></a> CodeFragment</span></span>
  <span data-ttu-id="69431-112">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="69431-112">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="69431-113">エディターに挿入するコード フラグメントを取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="69431-113">The read-only property that gets the code fragment to be inserted into the editor.</span></span>

```
# Get the code fragment associated with the first snippet item.
$psISE.CurrentPowerShellTab.Snippets.Item(0).CodeFragment

```

###  <span data-ttu-id="69431-114"><a name="Shortcut"></a> Shortcut</span><span class="sxs-lookup"><span data-stu-id="69431-114"><a name="Shortcut"></a> Shortcut</span></span>
  <span data-ttu-id="69431-115">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="69431-115">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="69431-116">メニュー項目の Windows ショートカット キーを取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="69431-116">The read-only property that gets the Windows keyboard shortcut for the menu item.</span></span>

```
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add("_Process",{get-process},"Alt+P")
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

## <a name="see-also"></a><span data-ttu-id="69431-117">参照</span><span class="sxs-lookup"><span data-stu-id="69431-117">See Also</span></span>
- [<span data-ttu-id="69431-118">ISESnippetCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="69431-118">The ISESnippetCollection Object</span></span>](The-ISESnippetCollection-Object.md) 
- [<span data-ttu-id="69431-119">Windows PowerShell ISE スクリプト オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="69431-119">The Windows PowerShell ISE Scripting Object Model</span></span>](The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
- [<span data-ttu-id="69431-120">Windows PowerShell ISE オブジェクト モデル リファレンス</span><span class="sxs-lookup"><span data-stu-id="69431-120">Windows PowerShell ISE Object Model Reference</span></span>](Windows-PowerShell-ISE-Object-Model-Reference.md) 
- [<span data-ttu-id="69431-121">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="69431-121">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)

  
