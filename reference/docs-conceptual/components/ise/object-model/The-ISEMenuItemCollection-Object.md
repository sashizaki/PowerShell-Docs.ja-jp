---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: ISEMenuItemCollection オブジェクト
ms.assetid: 0c0f5484-3320-408e-8534-5bd1c8e48512
ms.openlocfilehash: 7e5030416df394aaa9e9d3f63978e204a7faabf1
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403165"
---
# <a name="the-isemenuitemcollection-object"></a><span data-ttu-id="39751-103">ISEMenuItemCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="39751-103">The ISEMenuItemCollection Object</span></span>

<span data-ttu-id="39751-104">**ISEMenuItemCollection** オブジェクトは、**ISEMenuItem** オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="39751-104">An **ISEMenuItemCollection** object is a collection of **ISEMenuItem** objects.</span></span> <span data-ttu-id="39751-105">これは Microsoft.PowerShell.Host.ISE.ISEMenuItemCollection クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="39751-105">It is an instance of the Microsoft.PowerShell.Host.ISE.ISEMenuItemCollection class.</span></span> <span data-ttu-id="39751-106">例としては、Windows PowerShell® Integrated Scripting Environment (ISE) の **アドオン** メニューをカスタマイズするために使用される **$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="39751-106">An example is the **$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus** object that is used to customize the **Add-On** menu in Windows PowerShell® Integrated Scripting Environment (ISE).</span></span>

## <a name="method"></a><span data-ttu-id="39751-107">方法</span><span class="sxs-lookup"><span data-stu-id="39751-107">Method</span></span>

### <a name="addstring-displayname-systemmanagementautomationscriptblock-action-systemwindowsinputkeygesture-shortcut-"></a><span data-ttu-id="39751-108">Add\(string DisplayName, System.Management.Automation.ScriptBlock Action, System.Windows.Input.KeyGesture Shortcut \)</span><span class="sxs-lookup"><span data-stu-id="39751-108">Add\(string DisplayName, System.Management.Automation.ScriptBlock Action, System.Windows.Input.KeyGesture Shortcut \)</span></span>

<span data-ttu-id="39751-109">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="39751-109">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="39751-110">メニュー項目をコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="39751-110">Adds a menu item to the collection.</span></span>

<span data-ttu-id="39751-111">**DisplayName** 追加するメニューの表示名。</span><span class="sxs-lookup"><span data-stu-id="39751-111">**DisplayName** The display name of the menu to be added.</span></span>

<span data-ttu-id="39751-112">**Action** このメニュー項目に関連付けられるアクションを指定する **System.Management.Automation.ScriptBlock** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="39751-112">**Action** The **System.Management.Automation.ScriptBlock** object that specifies the action that is associated with this menu item.</span></span>

<span data-ttu-id="39751-113">**Shortcut** アクションのキーボード ショートカット。</span><span class="sxs-lookup"><span data-stu-id="39751-113">**Shortcut** The keyboard shortcut for the action.</span></span>

<span data-ttu-id="39751-114">**Returns** 追加した ISEMenuItem オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="39751-114">**Returns** The ISEMenuItem object that was just added.</span></span>

```powershell
# Create an Add-ons menu with an fast access key and a shortcut.
# Note the use of "_"  as opposed to the "&" for mapping to the fast access key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
```

### <a name="clear"></a><span data-ttu-id="39751-115">Clear\(\)</span><span class="sxs-lookup"><span data-stu-id="39751-115">Clear\(\)</span></span>

<span data-ttu-id="39751-116">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="39751-116">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="39751-117">メニュー項目からすべてのサブメニューを削除します。</span><span class="sxs-lookup"><span data-stu-id="39751-117">Removes all submenus from the menu item.</span></span>

```powershell
# Remove all custom submenu items from the AddOns menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
```

## <a name="see-also"></a><span data-ttu-id="39751-118">参照</span><span class="sxs-lookup"><span data-stu-id="39751-118">See Also</span></span>

- [<span data-ttu-id="39751-119">ISEMenuItem オブジェクト</span><span class="sxs-lookup"><span data-stu-id="39751-119">The ISEMenuItem Object</span></span>](The-ISEMenuItem-Object.md)
- [<span data-ttu-id="39751-120">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="39751-120">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="39751-121">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="39751-121">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)