---
ms.date: 12/31/2019
keywords: powershell,コマンドレット
title: ISEMenuItemCollection オブジェクト
ms.openlocfilehash: 39e8547c9b19ba323d4b224a46eda416542b2807
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809588"
---
# <a name="the-isemenuitemcollection-object"></a><span data-ttu-id="cf9ec-103">ISEMenuItemCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="cf9ec-103">The ISEMenuItemCollection Object</span></span>

<span data-ttu-id="cf9ec-104">**ISEMenuItemCollection** オブジェクトは、**ISEMenuItem** オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="cf9ec-104">An **ISEMenuItemCollection** object is a collection of **ISEMenuItem** objects.</span></span> <span data-ttu-id="cf9ec-105">これは **Microsoft.PowerShell.Host.ISE.ISEMenuItemCollection** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="cf9ec-105">It is an instance of the **Microsoft.PowerShell.Host.ISE.ISEMenuItemCollection** class.</span></span> <span data-ttu-id="cf9ec-106">例としては、Windows PowerShell® Integrated Scripting Environment (ISE) の **[アドオン]** メニューをカスタマイズするために使用される `$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus` オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="cf9ec-106">An example is the `$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus` object that is used to customize the **Add-On** menu in Windows PowerShell® Integrated Scripting Environment (ISE).</span></span>

## <a name="method"></a><span data-ttu-id="cf9ec-107">方法</span><span class="sxs-lookup"><span data-stu-id="cf9ec-107">Method</span></span>

### <a name="addstring-displayname-systemmanagementautomationscriptblock-action-systemwindowsinputkeygesture-shortcut-"></a><span data-ttu-id="cf9ec-108">Add\(string DisplayName, System.Management.Automation.ScriptBlock Action, System.Windows.Input.KeyGesture Shortcut \)</span><span class="sxs-lookup"><span data-stu-id="cf9ec-108">Add\(string DisplayName, System.Management.Automation.ScriptBlock Action, System.Windows.Input.KeyGesture Shortcut \)</span></span>

<span data-ttu-id="cf9ec-109">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cf9ec-109">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="cf9ec-110">メニュー項目をコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="cf9ec-110">Adds a menu item to the collection.</span></span>

<span data-ttu-id="cf9ec-111">**DisplayName** 追加するメニューの表示名。</span><span class="sxs-lookup"><span data-stu-id="cf9ec-111">**DisplayName** The display name of the menu to be added.</span></span>

<span data-ttu-id="cf9ec-112">**Action** このメニュー項目に関連付けられるアクションを指定する **System.Management.Automation.ScriptBlock** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cf9ec-112">**Action** The **System.Management.Automation.ScriptBlock** object that specifies the action that is associated with this menu item.</span></span>

<span data-ttu-id="cf9ec-113">**Shortcut** アクションのキーボード ショートカット。</span><span class="sxs-lookup"><span data-stu-id="cf9ec-113">**Shortcut** The keyboard shortcut for the action.</span></span>

<span data-ttu-id="cf9ec-114">**Returns** 追加した **ISEMenuItem** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cf9ec-114">**Returns** The **ISEMenuItem** object that was just added.</span></span>

```powershell
# Create an Add-ons menu with an fast access key and a shortcut.
# Note the use of "_"  as opposed to the "&" for mapping to the fast access key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
```

### <a name="clear"></a><span data-ttu-id="cf9ec-115">Clear\(\)</span><span class="sxs-lookup"><span data-stu-id="cf9ec-115">Clear\(\)</span></span>

<span data-ttu-id="cf9ec-116">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cf9ec-116">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="cf9ec-117">メニュー項目からすべてのサブメニューを削除します。</span><span class="sxs-lookup"><span data-stu-id="cf9ec-117">Removes all submenus from the menu item.</span></span>

```powershell
# Remove all custom submenu items from the AddOns menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
```

## <a name="see-also"></a><span data-ttu-id="cf9ec-118">参照</span><span class="sxs-lookup"><span data-stu-id="cf9ec-118">See Also</span></span>

- [<span data-ttu-id="cf9ec-119">ISEMenuItem オブジェクト</span><span class="sxs-lookup"><span data-stu-id="cf9ec-119">The ISEMenuItem Object</span></span>](The-ISEMenuItem-Object.md)
- [<span data-ttu-id="cf9ec-120">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="cf9ec-120">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="cf9ec-121">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="cf9ec-121">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)