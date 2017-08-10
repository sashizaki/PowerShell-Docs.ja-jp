---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "ISEMenuItem オブジェクト"
ms.assetid: a16660bd-0aee-46fd-ac17-3f022165d089
ms.openlocfilehash: 33de866d706ec2b0894c5bfe49e07fee142b95c0
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="the-isemenuitem-object"></a><span data-ttu-id="cddfa-103">ISEMenuItem オブジェクト</span><span class="sxs-lookup"><span data-stu-id="cddfa-103">The ISEMenuItem Object</span></span>
  <span data-ttu-id="cddfa-104">**ISEMenuItem** オブジェクトは Microsoft.PowerShell.Host.ISE.ISEMenuItem クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="cddfa-104">An **ISEMenuItem** object is an instance of the Microsoft.PowerShell.Host.ISE.ISEMenuItem class.</span></span> <span data-ttu-id="cddfa-105">**[アドオン]** メニューにあるすべてのオブジェクトは、**Microsoft.PowerShell.Host.ISE.ISEMenuItem** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="cddfa-105">All menu objects on the **Add-ons** menu are instances of the **Microsoft.PowerShell.Host.ISE.ISEMenuItem** class.</span></span>

## <a name="properties"></a><span data-ttu-id="cddfa-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="cddfa-106">Properties</span></span>

###  <span data-ttu-id="cddfa-107"><a name="DisplayName"></a> DisplayName</span><span class="sxs-lookup"><span data-stu-id="cddfa-107"><a name="DisplayName"></a> DisplayName</span></span>
  <span data-ttu-id="cddfa-108">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cddfa-108">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="cddfa-109">メニュー項目の名前を表示する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="cddfa-109">The read-only property that gets the display name of the menu item.</span></span>

```
# Get the display name of the Add-ons menu item
$psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add("_Process",{get-process},"Alt+P")
$psISE.CurrentPowerShellTab.AddOnsMenu.DisplayName

```

###  <span data-ttu-id="cddfa-110"><a name="Action"></a> Action</span><span class="sxs-lookup"><span data-stu-id="cddfa-110"><a name="Action"></a> Action</span></span>
  <span data-ttu-id="cddfa-111">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cddfa-111">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="cddfa-112">スクリプトのブロックを取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="cddfa-112">The read-only property that gets the block of script.</span></span> <span data-ttu-id="cddfa-113">メニュー項目をクリックすると、アクションが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cddfa-113">It invokes the action when you click the menu item.</span></span>

```
# Get the action associated with the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add("_Process",{get-process},"Alt+P")
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Action

# Invoke the script associated with the first submenu item 
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Action.Invoke()
```

###  <span data-ttu-id="cddfa-114"><a name="Shortcut"></a> Shortcut</span><span class="sxs-lookup"><span data-stu-id="cddfa-114"><a name="Shortcut"></a> Shortcut</span></span>
  <span data-ttu-id="cddfa-115">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cddfa-115">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="cddfa-116">メニュー項目の Windows 入力用ショートカット キーを取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="cddfa-116">The read-only property that gets the Windows input keyboard shortcut for the menu item.</span></span>

```
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add("_Process",{get-process},"Alt+P")
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

###  <span data-ttu-id="cddfa-117"><a name="Submenus"></a> Submenus</span><span class="sxs-lookup"><span data-stu-id="cddfa-117"><a name="Submenus"></a> Submenus</span></span>
  <span data-ttu-id="cddfa-118">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cddfa-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="cddfa-119">メニュー項目の[サブメニューの一覧](The-ISEMenuItemCollection-Object.md)を取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="cddfa-119">The read-only property that gets the [list of submenus](The-ISEMenuItemCollection-Object.md) of the menu item.</span></span>

```
# List the submenus of the Add-ons menu
$psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add("_Process",{get-process},"Alt+P")
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus
```

## <a name="scripting-example"></a><span data-ttu-id="cddfa-120">スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="cddfa-120">Scripting example</span></span>
 <span data-ttu-id="cddfa-121">[アドオン] メニューとそのスクリプト可能なプロパティの使用をさらに理解するには、次のスクリプトの例に目を通してください。</span><span class="sxs-lookup"><span data-stu-id="cddfa-121">To better understand the use of the Add-ons menu and its scriptable properties, read through the following scripting example.</span></span>

```

# This is a scripting example that shows the use of the Add-ons menu.
# Clear the Add-ons menu if any entries currently exist
$psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Clear()

# Add an Add-ons menu item with an shortcut and fast access key.
# Note the use of “_”  as opposed to the “&” for mapping to the fast access key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add("_Process",{get-process},"Alt+P") 
# Add a nested menu - a parent and a child submenu item. 
$parentAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add("Parent",$null,$null) 
$parentAdded.SubMenus.Add("_Dir",{dir},"Alt+D")

```

## <a name="see-also"></a><span data-ttu-id="cddfa-122">参照</span><span class="sxs-lookup"><span data-stu-id="cddfa-122">See Also</span></span>
- [<span data-ttu-id="cddfa-123">ISEMenuItemCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="cddfa-123">The ISEMenuItemCollection Object</span></span>](The-ISEMenuItemCollection-Object.md) 
- [<span data-ttu-id="cddfa-124">Windows PowerShell ISE スクリプト オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="cddfa-124">The Windows PowerShell ISE Scripting Object Model</span></span>](The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
- [<span data-ttu-id="cddfa-125">Windows PowerShell ISE オブジェクト モデル リファレンス</span><span class="sxs-lookup"><span data-stu-id="cddfa-125">Windows PowerShell ISE Object Model Reference</span></span>](Windows-PowerShell-ISE-Object-Model-Reference.md) 
- [<span data-ttu-id="cddfa-126">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="cddfa-126">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)

  
