---
ms.date: 12/31/2019
title: ISEMenuItem オブジェクト
description: ISEMenuItem オブジェクトは Microsoft.PowerShell.Host.ISE.ISEMenuItem クラスのインスタンスです。 **[アドオン]** メニューにあるすべてのオブジェクトは、ISEMenuItem クラスのインスタンスです。
ms.openlocfilehash: 15036e3551687a21dfbe50834a89247c80949656
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663439"
---
# <a name="the-isemenuitem-object"></a><span data-ttu-id="795e8-104">ISEMenuItem オブジェクト</span><span class="sxs-lookup"><span data-stu-id="795e8-104">The ISEMenuItem Object</span></span>

<span data-ttu-id="795e8-105">**ISEMenuItem** オブジェクトは **Microsoft.PowerShell.Host.ISE.ISEMenuItem** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="795e8-105">An **ISEMenuItem** object is an instance of the **Microsoft.PowerShell.Host.ISE.ISEMenuItem** class.</span></span>
<span data-ttu-id="795e8-106">**[アドオン]** メニューにあるすべてのオブジェクトは、 **Microsoft.PowerShell.Host.ISE.ISEMenuItem** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="795e8-106">All menu objects on the **Add-ons** menu are instances of the **Microsoft.PowerShell.Host.ISE.ISEMenuItem** class.</span></span>

## <a name="properties"></a><span data-ttu-id="795e8-107">Properties</span><span class="sxs-lookup"><span data-stu-id="795e8-107">Properties</span></span>

### <a name="displayname"></a><span data-ttu-id="795e8-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="795e8-108">DisplayName</span></span>

<span data-ttu-id="795e8-109">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="795e8-109">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="795e8-110">メニュー項目の名前を表示する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="795e8-110">The read-only property that gets the display name of the menu item.</span></span>

```powershell
# Get the display name of the Add-ons menu item
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.DisplayName
```

### <a name="action"></a><span data-ttu-id="795e8-111">アクション</span><span class="sxs-lookup"><span data-stu-id="795e8-111">Action</span></span>

<span data-ttu-id="795e8-112">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="795e8-112">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="795e8-113">スクリプトのブロックを取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="795e8-113">The read-only property that gets the block of script.</span></span> <span data-ttu-id="795e8-114">メニュー項目をクリックすると、アクションが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="795e8-114">It invokes the action when you click the menu item.</span></span>

```powershell
# Get the action associated with the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Action

# Invoke the script associated with the first submenu item
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Action.Invoke()
```

### <a name="shortcut"></a><span data-ttu-id="795e8-115">ショートカット</span><span class="sxs-lookup"><span data-stu-id="795e8-115">Shortcut</span></span>

<span data-ttu-id="795e8-116">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="795e8-116">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="795e8-117">メニュー項目の Windows 入力用ショートカット キーを取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="795e8-117">The read-only property that gets the Windows input keyboard shortcut for the menu item.</span></span>

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

### <a name="submenus"></a><span data-ttu-id="795e8-118">Submenus</span><span class="sxs-lookup"><span data-stu-id="795e8-118">Submenus</span></span>

<span data-ttu-id="795e8-119">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="795e8-119">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="795e8-120">メニュー項目の[サブメニューの一覧](The-ISEMenuItemCollection-Object.md)を取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="795e8-120">The read-only property that gets the [list of submenus](The-ISEMenuItemCollection-Object.md) of the menu item.</span></span>

```powershell
# List the submenus of the Add-ons menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus
```

## <a name="scripting-example"></a><span data-ttu-id="795e8-121">スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="795e8-121">Scripting example</span></span>

<span data-ttu-id="795e8-122">[アドオン] メニューとそのスクリプト可能なプロパティの使用をさらに理解するには、次のスクリプトの例に目を通してください。</span><span class="sxs-lookup"><span data-stu-id="795e8-122">To better understand the use of the Add-ons menu and its scriptable properties, read through the following scripting example.</span></span>

```powershell
# This is a scripting example that shows the use of the Add-ons menu.
# Clear the Add-ons menu if any entries currently exist
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()

# Add an Add-ons menu item with an shortcut and fast access key.
# Note the use of "_"  as opposed to the "&" for mapping to the fast access key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add('_Process', {Get-Process}, 'Alt+P')
# Add a nested menu - a parent and a child submenu item.
$parentAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('Parent', $null, $null)
$parentAdded.SubMenus.Add('_Dir', {dir}, 'Alt+D')
```

## <a name="see-also"></a><span data-ttu-id="795e8-123">参照</span><span class="sxs-lookup"><span data-stu-id="795e8-123">See Also</span></span>

- [<span data-ttu-id="795e8-124">ISEMenuItemCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="795e8-124">The ISEMenuItemCollection Object</span></span>](The-ISEMenuItemCollection-Object.md)
- [<span data-ttu-id="795e8-125">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="795e8-125">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="795e8-126">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="795e8-126">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
