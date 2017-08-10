---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "PowerShellTabCollection オブジェクト"
ms.assetid: 81f4bf4a-83bf-415e-8378-1703792fbb58
ms.openlocfilehash: dcdc16ae126453b6ade64917ac4950cc05e5f8ad
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="the-powershelltabcollection-object"></a><span data-ttu-id="38fe4-103">PowerShellTabCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="38fe4-103">The PowerShellTabCollection Object</span></span>
  <span data-ttu-id="38fe4-104">**PowerShellTab** コレクション オブジェクトは **PowerShellTab** オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="38fe4-104">The **PowerShellTab** collection object is a collection of **PowerShellTab** objects.</span></span> <span data-ttu-id="38fe4-105">個々の **PowerShellTab** オブジェクトは、個別のランタイム環境として機能します。</span><span class="sxs-lookup"><span data-stu-id="38fe4-105">Each **PowerShellTab** object functions as a separate runtime environment.</span></span> <span data-ttu-id="38fe4-106">これは Microsoft.PowerShell.Host.ISE.PowerShellTabs クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="38fe4-106">It is an instance of Microsoft.PowerShell.Host.ISE.PowerShellTabs class.</span></span> <span data-ttu-id="38fe4-107">たとえば **$psISE.PowerShellTabs** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="38fe4-107">An example is the **$psISE.PowerShellTabs** object.</span></span>

## <a name="methods"></a><span data-ttu-id="38fe4-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="38fe4-108">Methods</span></span>

### <a name="add"></a><span data-ttu-id="38fe4-109">Add\(\)</span><span class="sxs-lookup"><span data-stu-id="38fe4-109">Add\(\)</span></span>
  <span data-ttu-id="38fe4-110">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="38fe4-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="38fe4-111">新しい PowerShell タブをコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="38fe4-111">Adds a new PowerShell tab to the collection.</span></span> <span data-ttu-id="38fe4-112">新しく追加されたタブが返されます。</span><span class="sxs-lookup"><span data-stu-id="38fe4-112">It returns the newly added tab.</span></span>

```
$NewTab=$psISE.PowerShellTabs.Add()
$newTab.DisplayName="Brand New Tab"
```

### <a name="removemicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="38fe4-113">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="38fe4-113">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>
  <span data-ttu-id="38fe4-114">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="38fe4-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="38fe4-115">**psTab** パラメーターにより指定されたタブが削除されます。</span><span class="sxs-lookup"><span data-stu-id="38fe4-115">Removes the tab that is specified by the **psTab** parameter.</span></span>

 <span data-ttu-id="38fe4-116">**psTab**
 削除する PowerShell タブ。</span><span class="sxs-lookup"><span data-stu-id="38fe4-116">**psTab**
 The PowerShell tab to remove.</span></span>

```

$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab. 
$newTab.DisplayName="This tab will go away in 5 seconds" 
sleep 5 
$psISE.PowerShellTabs.Remove($newTab)
```

### <a name="setselectedpowershelltabmicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="38fe4-117">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="38fe4-117">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>
  <span data-ttu-id="38fe4-118">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="38fe4-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="38fe4-119">**psTab** パラメーターにより指定された PowerShell タブを選択し、そのタブを現在アクティブな PowerShell タブとして指定します。</span><span class="sxs-lookup"><span data-stu-id="38fe4-119">Selects the PowerShell tab that is specified by the **psTab** parameter to make it the currently active PowerShell tab.</span></span>

 <span data-ttu-id="38fe4-120">**psTab**
 選択する PowerShell タブ。</span><span class="sxs-lookup"><span data-stu-id="38fe4-120">**psTab**
 The PowerShell tab to select.</span></span>

```
# Save the current tab in a variable and rename it
$OldTab = $psISE.CurrentPowerShellTab
$psISE.CurrentPowerShellTab.DisplayName="Old Tab"
# Create a new tab and give it a new display name
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName="Brand New Tab" 
# Switch back to the original tab
$psISE.PowerShellTabs.SelectedPowerShellTab=$oldtab
```

## <a name="see-also"></a><span data-ttu-id="38fe4-121">参照</span><span class="sxs-lookup"><span data-stu-id="38fe4-121">See Also</span></span>
- [<span data-ttu-id="38fe4-122">PowerShellTab オブジェクト</span><span class="sxs-lookup"><span data-stu-id="38fe4-122">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md) 
- [<span data-ttu-id="38fe4-123">Windows PowerShell ISE スクリプト オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="38fe4-123">The Windows PowerShell ISE Scripting Object Model</span></span>](../ise/The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
- [<span data-ttu-id="38fe4-124">Windows PowerShell ISE オブジェクト モデル リファレンス</span><span class="sxs-lookup"><span data-stu-id="38fe4-124">Windows PowerShell ISE Object Model Reference</span></span>](../ise/Windows-PowerShell-ISE-Object-Model-Reference.md) 
- [<span data-ttu-id="38fe4-125">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="38fe4-125">The ISE Object Model Hierarchy</span></span>](../ise/The-ISE-Object-Model-Hierarchy.md)

  
