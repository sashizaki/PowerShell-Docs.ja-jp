---
ms.date: 12/31/2019
keywords: powershell,コマンドレット
title: ISEMenuItem オブジェクト
ms.openlocfilehash: c3ffe6e8f0b28987543fe0a873c552292dc5158a
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809318"
---
# <a name="the-isemenuitem-object"></a><span data-ttu-id="4d9ec-103">ISEMenuItem オブジェクト</span><span class="sxs-lookup"><span data-stu-id="4d9ec-103">The ISEMenuItem Object</span></span>

<span data-ttu-id="4d9ec-104">**ISEMenuItem** オブジェクトは **Microsoft.PowerShell.Host.ISE.ISEMenuItem** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="4d9ec-104">An **ISEMenuItem** object is an instance of the **Microsoft.PowerShell.Host.ISE.ISEMenuItem** class.</span></span>
<span data-ttu-id="4d9ec-105">**[アドオン]** メニューにあるすべてのオブジェクトは、**Microsoft.PowerShell.Host.ISE.ISEMenuItem** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="4d9ec-105">All menu objects on the **Add-ons** menu are instances of the **Microsoft.PowerShell.Host.ISE.ISEMenuItem** class.</span></span>

## <a name="properties"></a><span data-ttu-id="4d9ec-106">Properties</span><span class="sxs-lookup"><span data-stu-id="4d9ec-106">Properties</span></span>

### <a name="displayname"></a><span data-ttu-id="4d9ec-107">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4d9ec-107">DisplayName</span></span>

<span data-ttu-id="4d9ec-108">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4d9ec-108">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="4d9ec-109">メニュー項目の名前を表示する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4d9ec-109">The read-only property that gets the display name of the menu item.</span></span>

```powershell
# Get the display name of the Add-ons menu item
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.DisplayName
```

### <a name="action"></a><span data-ttu-id="4d9ec-110">アクション</span><span class="sxs-lookup"><span data-stu-id="4d9ec-110">Action</span></span>

<span data-ttu-id="4d9ec-111">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4d9ec-111">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="4d9ec-112">スクリプトのブロックを取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4d9ec-112">The read-only property that gets the block of script.</span></span> <span data-ttu-id="4d9ec-113">メニュー項目をクリックすると、アクションが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4d9ec-113">It invokes the action when you click the menu item.</span></span>

```powershell
# Get the action associated with the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Action

# Invoke the script associated with the first submenu item
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Action.Invoke()
```

### <a name="shortcut"></a><span data-ttu-id="4d9ec-114">ショートカット</span><span class="sxs-lookup"><span data-stu-id="4d9ec-114">Shortcut</span></span>

<span data-ttu-id="4d9ec-115">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4d9ec-115">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="4d9ec-116">メニュー項目の Windows 入力用ショートカット キーを取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4d9ec-116">The read-only property that gets the Windows input keyboard shortcut for the menu item.</span></span>

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

### <a name="submenus"></a><span data-ttu-id="4d9ec-117">Submenus</span><span class="sxs-lookup"><span data-stu-id="4d9ec-117">Submenus</span></span>

<span data-ttu-id="4d9ec-118">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4d9ec-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="4d9ec-119">メニュー項目の[サブメニューの一覧](The-ISEMenuItemCollection-Object.md)を取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4d9ec-119">The read-only property that gets the [list of submenus](The-ISEMenuItemCollection-Object.md) of the menu item.</span></span>

```powershell
# List the submenus of the Add-ons menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus
```

## <a name="scripting-example"></a><span data-ttu-id="4d9ec-120">スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="4d9ec-120">Scripting example</span></span>

<span data-ttu-id="4d9ec-121">[アドオン] メニューとそのスクリプト可能なプロパティの使用をさらに理解するには、次のスクリプトの例に目を通してください。</span><span class="sxs-lookup"><span data-stu-id="4d9ec-121">To better understand the use of the Add-ons menu and its scriptable properties, read through the following scripting example.</span></span>

```powershell
# This is a scripting example that shows the use of the Add-ons menu.
# Clear the Add-ons menu if any entries currently exist
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()

# Add an Add-ons menu item with an shortcut and fast access key.
# Note the use of “_”  as opposed to the “&” for mapping to the fast access key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add('_Process', {Get-Process}, 'Alt+P')
# Add a nested menu - a parent and a child submenu item.
$parentAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('Parent', $null, $null)
$parentAdded.SubMenus.Add('_Dir', {dir}, 'Alt+D')
```

## <a name="see-also"></a><span data-ttu-id="4d9ec-122">参照</span><span class="sxs-lookup"><span data-stu-id="4d9ec-122">See Also</span></span>

- [<span data-ttu-id="4d9ec-123">ISEMenuItemCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="4d9ec-123">The ISEMenuItemCollection Object</span></span>](The-ISEMenuItemCollection-Object.md)
- [<span data-ttu-id="4d9ec-124">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="4d9ec-124">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="4d9ec-125">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="4d9ec-125">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
