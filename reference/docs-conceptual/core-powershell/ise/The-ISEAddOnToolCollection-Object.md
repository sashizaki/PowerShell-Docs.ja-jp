---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "ISEAddOnToolCollection オブジェクト"
ms.assetid: 634eab89-0845-4016-974b-361b09bb8f7b
ms.openlocfilehash: ba8b4e0e3952226407f00dea8b32785633256089
ms.sourcegitcommit: 74255f0b5f386a072458af058a15240140acb294
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2017
---
# <a name="the-iseaddontoolcollection-object"></a><span data-ttu-id="4b742-103">ISEAddOnToolCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="4b742-103">The ISEAddOnToolCollection Object</span></span>
  <span data-ttu-id="4b742-104">**ISEAddOnToolCollection** オブジェクトは、**ISEAddOnTool** オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="4b742-104">The **ISEAddOnToolCollection** object is a collection of **ISEAddOnTool** objects.</span></span> <span data-ttu-id="4b742-105">例としては、**$psISE.CurrentPowerShellTab.VerticalAddOnTools** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="4b742-105">An example is the **$psISE.CurrentPowerShellTab.VerticalAddOnTools** object.</span></span>

## <a name="methods"></a><span data-ttu-id="4b742-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="4b742-106">Methods</span></span>

### <a name="add-name-controltype-isvisible-"></a><span data-ttu-id="4b742-107">Add\( Name、ControlType、\[IsVisible\] \)</span><span class="sxs-lookup"><span data-stu-id="4b742-107">Add\( Name, ControlType, \[IsVisible\] \)</span></span>
  <span data-ttu-id="4b742-108">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="4b742-108">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="4b742-109">新しいアドオン ツールをコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="4b742-109">Adds a new add-on tool to the collection.</span></span> <span data-ttu-id="4b742-110">新しく追加されたアドオン ツールが返されます。</span><span class="sxs-lookup"><span data-stu-id="4b742-110">It returns the newly added add-on tool.</span></span> <span data-ttu-id="4b742-111">このコマンドを実行する前に、ローカル コンピューターにアドオン ツールをインストールし、アセンブリを読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b742-111">Before you run this command, you must install the add-on tool on the local computer and load the assembly.</span></span>

 <span data-ttu-id="4b742-112">**Name** - Windows PowerShell ISE に追加するアドオン ツールの表示名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="4b742-112">**Name** - String Specifies the display name of the add-on tool that is added to Windows PowerShell ISE.</span></span>

 <span data-ttu-id="4b742-113">**ControlType** - 追加するコントロールを指定する種類。</span><span class="sxs-lookup"><span data-stu-id="4b742-113">**ControlType** -Type Specifies the control that is added.</span></span>

 <span data-ttu-id="4b742-114">**\[IsVisible\]** - 省略可能なブール値は、**$true** に設定すると、アドオン ツールが、関連付けられているツール ウィンドウに直ちに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b742-114">**\[IsVisible\]** - optional Boolean If set to **$true**, the add-on tool is immediately visible in the associated tool pane.</span></span>

```powershell
# Load a DLL with an add-on and then add it to the ISE
[reflection.assembly]::LoadFile("c:\test\ISESimpleSolution\ISESimpleSolution.dll")
$psISE.CurrentPowerShellTab.VerticalAddOnTools.Add("Solutions", [ISESimpleSolution.Solution], $true)
```

### <a name="remove-item-"></a><span data-ttu-id="4b742-115">Remove\( Item \)</span><span class="sxs-lookup"><span data-stu-id="4b742-115">Remove\( Item \)</span></span>
  <span data-ttu-id="4b742-116">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="4b742-116">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="4b742-117">コレクションから指定したアドオン ツールを削除します。</span><span class="sxs-lookup"><span data-stu-id="4b742-117">Removes the specified add-on tool from the collection.</span></span>

 <span data-ttu-id="4b742-118">**Item** - Microsoft.PowerShell.Host.ISE.ISEAddOnTool Windows PowerShell ISE から削除するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4b742-118">**Item** - Microsoft.PowerShell.Host.ISE.ISEAddOnTool Specifies the object to be removed from Windows PowerShell ISE.</span></span>

```powershell
# Load a DLL with an add-on and then add it to the ISE
[reflection.assembly]::LoadFile("c:\test\ISESimpleSolution\ISESimpleSolution.dll")
$psISE.CurrentPowerShellTab.VerticalAddOnTools.Add("Solutions", [ISESimpleSolution.Solution], $true)
```

### <a name="setselectedpowershelltab-pstab-"></a><span data-ttu-id="4b742-119">SetSelectedPowerShellTab\( psTab \)</span><span class="sxs-lookup"><span data-stu-id="4b742-119">SetSelectedPowerShellTab\( psTab \)</span></span>
  <span data-ttu-id="4b742-120">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="4b742-120">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="4b742-121">**psTab** パラメーターが指定する PowerShell タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b742-121">Selects the PowerShell tab that the **psTab** parameter specifies.</span></span>

 <span data-ttu-id="4b742-122">**psTab** - PowerShell タブが選択するMicrosoft.PowerShell.Host.ISE.PowerShellTab。</span><span class="sxs-lookup"><span data-stu-id="4b742-122">**psTab** - Microsoft.PowerShell.Host.ISE.PowerShellTab The PowerShell tab to select.</span></span>

```powershell
      $newTab = $psISE.PowerShellTabs.Add()
# Change the DisplayName of the new PowerShell tab. 
$newTab.DisplayName="Brand New Tab"
```

### <a name="remove-pstab-"></a><span data-ttu-id="4b742-123">Remove\( psTab \)</span><span class="sxs-lookup"><span data-stu-id="4b742-123">Remove\( psTab \)</span></span>
  <span data-ttu-id="4b742-124">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="4b742-124">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="4b742-125">**psTab** パラメーターが指定する PowerShell タブを削除します。</span><span class="sxs-lookup"><span data-stu-id="4b742-125">Removes the PowerShell tab that the **psTab** parameter specifies.</span></span>

 <span data-ttu-id="4b742-126">**psTab** - PowerShell タブが削除する Microsoft.PowerShell.Host.ISE.PowerShellTab。</span><span class="sxs-lookup"><span data-stu-id="4b742-126">**psTab** - Microsoft.PowerShell.Host.ISE.PowerShellTab The PowerShell tab to remove.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab. 
$newTab.DisplayName="This tab will go away in 5 seconds" 
sleep 5 
$psISE.PowerShellTabs.Remove($newTab)
```

## <a name="see-also"></a><span data-ttu-id="4b742-127">参照</span><span class="sxs-lookup"><span data-stu-id="4b742-127">See Also</span></span>
- [<span data-ttu-id="4b742-128">PowerShellTab オブジェクト</span><span class="sxs-lookup"><span data-stu-id="4b742-128">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md) 
- [<span data-ttu-id="4b742-129">Windows PowerShell ISE スクリプト オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="4b742-129">The Windows PowerShell ISE Scripting Object Model</span></span>](The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
- [<span data-ttu-id="4b742-130">Windows PowerShell ISE オブジェクト モデル リファレンス</span><span class="sxs-lookup"><span data-stu-id="4b742-130">Windows PowerShell ISE Object Model Reference</span></span>](Windows-PowerShell-ISE-Object-Model-Reference.md) 
- [<span data-ttu-id="4b742-131">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="4b742-131">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)

  
