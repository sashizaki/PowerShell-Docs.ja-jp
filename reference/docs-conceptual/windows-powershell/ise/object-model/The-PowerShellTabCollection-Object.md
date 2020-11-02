---
ms.date: 06/05/2017
title: PowerShellTabCollection オブジェクト
description: PowerShellTab コレクション オブジェクトは PowerShellTab オブジェクトのコレクションです。 個々の PowerShellTab オブジェクトは、個別のランタイム環境として機能します。
ms.openlocfilehash: 60f8001f096b50bd8433a5685f1f70a350f07f61
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658276"
---
# <a name="the-powershelltabcollection-object"></a><span data-ttu-id="7acdc-104">PowerShellTabCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7acdc-104">The PowerShellTabCollection Object</span></span>

<span data-ttu-id="7acdc-105">**PowerShellTab** コレクション オブジェクトは **PowerShellTab** オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="7acdc-105">The **PowerShellTab** collection object is a collection of **PowerShellTab** objects.</span></span> <span data-ttu-id="7acdc-106">個々の **PowerShellTab** オブジェクトは、個別のランタイム環境として機能します。</span><span class="sxs-lookup"><span data-stu-id="7acdc-106">Each **PowerShellTab** object functions as a separate runtime environment.</span></span> <span data-ttu-id="7acdc-107">これは Microsoft.PowerShell.Host.ISE.PowerShellTabs クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="7acdc-107">It is an instance of Microsoft.PowerShell.Host.ISE.PowerShellTabs class.</span></span> <span data-ttu-id="7acdc-108">例は、`$psISE.PowerShellTabs` オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="7acdc-108">An example is the `$psISE.PowerShellTabs` object.</span></span>

## <a name="methods"></a><span data-ttu-id="7acdc-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="7acdc-109">Methods</span></span>

### <a name="add"></a><span data-ttu-id="7acdc-110">Add\(\)</span><span class="sxs-lookup"><span data-stu-id="7acdc-110">Add\(\)</span></span>

<span data-ttu-id="7acdc-111">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7acdc-111">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7acdc-112">新しい PowerShell タブをコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="7acdc-112">Adds a new PowerShell tab to the collection.</span></span> <span data-ttu-id="7acdc-113">新しく追加されたタブが返されます。</span><span class="sxs-lookup"><span data-stu-id="7acdc-113">It returns the newly added tab.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
```

### <a name="removemicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="7acdc-114">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="7acdc-114">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="7acdc-115">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7acdc-115">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7acdc-116">**psTab** パラメーターにより指定されたタブが削除されます。</span><span class="sxs-lookup"><span data-stu-id="7acdc-116">Removes the tab that is specified by the **psTab** parameter.</span></span>

<span data-ttu-id="7acdc-117">**psTab** 削除する PowerShell タブ。</span><span class="sxs-lookup"><span data-stu-id="7acdc-117">**psTab** The PowerShell tab to remove.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab.
$newTab.DisplayName = 'This tab will go away in 5 seconds'
sleep 5
$psISE.PowerShellTabs.Remove($newTab)
```

### <a name="setselectedpowershelltabmicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="7acdc-118">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="7acdc-118">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="7acdc-119">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7acdc-119">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7acdc-120">**psTab** パラメーターにより指定された PowerShell タブを選択し、そのタブを現在アクティブな PowerShell タブとして指定します。</span><span class="sxs-lookup"><span data-stu-id="7acdc-120">Selects the PowerShell tab that is specified by the **psTab** parameter to make it the currently active PowerShell tab.</span></span>

<span data-ttu-id="7acdc-121">**psTab** 選択する PowerShell タブ。</span><span class="sxs-lookup"><span data-stu-id="7acdc-121">**psTab** The PowerShell tab to select.</span></span>

```powershell
# Save the current tab in a variable and rename it
$oldTab = $psISE.CurrentPowerShellTab
$psISE.CurrentPowerShellTab.DisplayName = 'Old Tab'
# Create a new tab and give it a new display name
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
# Switch back to the original tab
$psISE.PowerShellTabs.SelectedPowerShellTab = $oldTab
```

## <a name="see-also"></a><span data-ttu-id="7acdc-122">参照</span><span class="sxs-lookup"><span data-stu-id="7acdc-122">See Also</span></span>

- [<span data-ttu-id="7acdc-123">PowerShellTab オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7acdc-123">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md)
- [<span data-ttu-id="7acdc-124">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="7acdc-124">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="7acdc-125">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="7acdc-125">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
