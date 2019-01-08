---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: ISEMenuItem オブジェクト
ms.assetid: a16660bd-0aee-46fd-ac17-3f022165d089
ms.openlocfilehash: 556f88117c07100b1734c8ffd8956dce6efe6fb1
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403363"
---
# <a name="the-isemenuitem-object"></a><span data-ttu-id="55e17-103">ISEMenuItem オブジェクト</span><span class="sxs-lookup"><span data-stu-id="55e17-103">The ISEMenuItem Object</span></span>

<span data-ttu-id="55e17-104">**ISEMenuItem** オブジェクトは Microsoft.PowerShell.Host.ISE.ISEMenuItem クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="55e17-104">An **ISEMenuItem** object is an instance of the Microsoft.PowerShell.Host.ISE.ISEMenuItem class.</span></span> <span data-ttu-id="55e17-105">**[アドオン]** メニューにあるすべてのオブジェクトは、**Microsoft.PowerShell.Host.ISE.ISEMenuItem** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="55e17-105">All menu objects on the **Add-ons** menu are instances of the **Microsoft.PowerShell.Host.ISE.ISEMenuItem** class.</span></span>

## <a name="properties"></a><span data-ttu-id="55e17-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="55e17-106">Properties</span></span>

### <a name="displayname"></a><span data-ttu-id="55e17-107">表示名</span><span class="sxs-lookup"><span data-stu-id="55e17-107">DisplayName</span></span>

<span data-ttu-id="55e17-108">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="55e17-108">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="55e17-109">メニュー項目の名前を表示する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="55e17-109">The read-only property that gets the display name of the menu item.</span></span>

```powershell
# Get the display name of the Add-ons menu item
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.DisplayName
```

### <a name="action"></a><span data-ttu-id="55e17-110">操作</span><span class="sxs-lookup"><span data-stu-id="55e17-110">Action</span></span>

<span data-ttu-id="55e17-111">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="55e17-111">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="55e17-112">スクリプトのブロックを取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="55e17-112">The read-only property that gets the block of script.</span></span> <span data-ttu-id="55e17-113">メニュー項目をクリックすると、アクションが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="55e17-113">It invokes the action when you click the menu item.</span></span>

```powershell
# Get the action associated with the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Action

# Invoke the script associated with the first submenu item
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Action.Invoke()
```

### <a name="shortcut"></a><span data-ttu-id="55e17-114">Shortcut</span><span class="sxs-lookup"><span data-stu-id="55e17-114">Shortcut</span></span>

<span data-ttu-id="55e17-115">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="55e17-115">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="55e17-116">メニュー項目の Windows 入力用ショートカット キーを取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="55e17-116">The read-only property that gets the Windows input keyboard shortcut for the menu item.</span></span>

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

### <a name="submenus"></a><span data-ttu-id="55e17-117">Submenus</span><span class="sxs-lookup"><span data-stu-id="55e17-117">Submenus</span></span>

<span data-ttu-id="55e17-118">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="55e17-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="55e17-119">メニュー項目の[サブメニューの一覧](The-ISEMenuItemCollection-Object.md)を取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="55e17-119">The read-only property that gets the [list of submenus](The-ISEMenuItemCollection-Object.md) of the menu item.</span></span>

```powershell
# List the submenus of the Add-ons menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus
```

## <a name="scripting-example"></a><span data-ttu-id="55e17-120">スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="55e17-120">Scripting example</span></span>

<span data-ttu-id="55e17-121">[アドオン] メニューとそのスクリプト可能なプロパティの使用をさらに理解するには、次のスクリプトの例に目を通してください。</span><span class="sxs-lookup"><span data-stu-id="55e17-121">To better understand the use of the Add-ons menu and its scriptable properties, read through the following scripting example.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="55e17-122">参照</span><span class="sxs-lookup"><span data-stu-id="55e17-122">See Also</span></span>

- [<span data-ttu-id="55e17-123">ISEMenuItemCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="55e17-123">The ISEMenuItemCollection Object</span></span>](The-ISEMenuItemCollection-Object.md)
- [<span data-ttu-id="55e17-124">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="55e17-124">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="55e17-125">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="55e17-125">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)