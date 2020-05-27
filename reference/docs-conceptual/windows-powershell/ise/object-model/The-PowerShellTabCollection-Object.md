---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: PowerShellTabCollection オブジェクト
ms.openlocfilehash: 0aad885afd3ba3ae3b00f5c11d2c62a9ff303798
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808568"
---
# <a name="the-powershelltabcollection-object"></a><span data-ttu-id="6fc95-103">PowerShellTabCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="6fc95-103">The PowerShellTabCollection Object</span></span>

<span data-ttu-id="6fc95-104">**PowerShellTab** コレクション オブジェクトは **PowerShellTab** オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="6fc95-104">The **PowerShellTab** collection object is a collection of **PowerShellTab** objects.</span></span> <span data-ttu-id="6fc95-105">個々の **PowerShellTab** オブジェクトは、個別のランタイム環境として機能します。</span><span class="sxs-lookup"><span data-stu-id="6fc95-105">Each **PowerShellTab** object functions as a separate runtime environment.</span></span> <span data-ttu-id="6fc95-106">これは Microsoft.PowerShell.Host.ISE.PowerShellTabs クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="6fc95-106">It is an instance of Microsoft.PowerShell.Host.ISE.PowerShellTabs class.</span></span> <span data-ttu-id="6fc95-107">例は、`$psISE.PowerShellTabs` オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="6fc95-107">An example is the `$psISE.PowerShellTabs` object.</span></span>

## <a name="methods"></a><span data-ttu-id="6fc95-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="6fc95-108">Methods</span></span>

### <a name="add"></a><span data-ttu-id="6fc95-109">Add\(\)</span><span class="sxs-lookup"><span data-stu-id="6fc95-109">Add\(\)</span></span>

<span data-ttu-id="6fc95-110">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6fc95-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="6fc95-111">新しい PowerShell タブをコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="6fc95-111">Adds a new PowerShell tab to the collection.</span></span> <span data-ttu-id="6fc95-112">新しく追加されたタブが返されます。</span><span class="sxs-lookup"><span data-stu-id="6fc95-112">It returns the newly added tab.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
```

### <a name="removemicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="6fc95-113">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="6fc95-113">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="6fc95-114">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6fc95-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="6fc95-115">**psTab** パラメーターにより指定されたタブが削除されます。</span><span class="sxs-lookup"><span data-stu-id="6fc95-115">Removes the tab that is specified by the **psTab** parameter.</span></span>

<span data-ttu-id="6fc95-116">**psTab** 削除する PowerShell タブ。</span><span class="sxs-lookup"><span data-stu-id="6fc95-116">**psTab** The PowerShell tab to remove.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab.
$newTab.DisplayName = 'This tab will go away in 5 seconds'
sleep 5
$psISE.PowerShellTabs.Remove($newTab)
```

### <a name="setselectedpowershelltabmicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="6fc95-117">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="6fc95-117">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="6fc95-118">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6fc95-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="6fc95-119">**psTab** パラメーターにより指定された PowerShell タブを選択し、そのタブを現在アクティブな PowerShell タブとして指定します。</span><span class="sxs-lookup"><span data-stu-id="6fc95-119">Selects the PowerShell tab that is specified by the **psTab** parameter to make it the currently active PowerShell tab.</span></span>

<span data-ttu-id="6fc95-120">**psTab** 選択する PowerShell タブ。</span><span class="sxs-lookup"><span data-stu-id="6fc95-120">**psTab** The PowerShell tab to select.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6fc95-121">参照</span><span class="sxs-lookup"><span data-stu-id="6fc95-121">See Also</span></span>

- [<span data-ttu-id="6fc95-122">PowerShellTab オブジェクト</span><span class="sxs-lookup"><span data-stu-id="6fc95-122">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md)
- [<span data-ttu-id="6fc95-123">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="6fc95-123">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="6fc95-124">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="6fc95-124">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
