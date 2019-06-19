---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: ISEAddOnToolCollection オブジェクト
ms.openlocfilehash: 28ab9747e573b7a76ee655289b341870b1728bc2
ms.sourcegitcommit: a6f13c16a535acea279c0ddeca72f1f0d8a8ce4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67030629"
---
# <a name="the-iseaddontoolcollection-object"></a><span data-ttu-id="8e48a-103">ISEAddOnToolCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="8e48a-103">The ISEAddOnToolCollection Object</span></span>

<span data-ttu-id="8e48a-104">**ISEAddOnToolCollection** オブジェクトは、**ISEAddOnTool** オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="8e48a-104">The **ISEAddOnToolCollection** object is a collection of **ISEAddOnTool** objects.</span></span> <span data-ttu-id="8e48a-105">例としては、 **$psISE.CurrentPowerShellTab.VerticalAddOnTools** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="8e48a-105">An example is the **$psISE.CurrentPowerShellTab.VerticalAddOnTools** object.</span></span>

## <a name="methods"></a><span data-ttu-id="8e48a-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="8e48a-106">Methods</span></span>

### <a name="add-name-controltype-isvisible-"></a><span data-ttu-id="8e48a-107">Add\( Name、ControlType、\[IsVisible\] \)</span><span class="sxs-lookup"><span data-stu-id="8e48a-107">Add\( Name, ControlType, \[IsVisible\] \)</span></span>

<span data-ttu-id="8e48a-108">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="8e48a-108">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="8e48a-109">新しいアドオン ツールをコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="8e48a-109">Adds a new add-on tool to the collection.</span></span> <span data-ttu-id="8e48a-110">新しく追加されたアドオン ツールが返されます。</span><span class="sxs-lookup"><span data-stu-id="8e48a-110">It returns the newly added add-on tool.</span></span> <span data-ttu-id="8e48a-111">このコマンドを実行する前に、ローカル コンピューターにアドオン ツールをインストールし、アセンブリを読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e48a-111">Before you run this command, you must install the add-on tool on the local computer and load the assembly.</span></span>

<span data-ttu-id="8e48a-112">**Name** - Windows PowerShell ISE に追加するアドオン ツールの表示名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="8e48a-112">**Name** - String Specifies the display name of the add-on tool that is added to Windows PowerShell ISE.</span></span>

<span data-ttu-id="8e48a-113">**ControlType** - 追加するコントロールを指定する種類。</span><span class="sxs-lookup"><span data-stu-id="8e48a-113">**ControlType** -Type Specifies the control that is added.</span></span>

<span data-ttu-id="8e48a-114">**\[IsVisible\]** - 省略可能なブール値は、 **$true** に設定すると、アドオン ツールが、関連付けられているツール ウィンドウに直ちに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e48a-114">**\[IsVisible\]** - optional Boolean If set to **$true**, the add-on tool is immediately visible in the associated tool pane.</span></span>

```powershell
# Load a DLL with an add-on and then add it to the ISE
[reflection.assembly]::LoadFile("c:\test\ISESimpleSolution\ISESimpleSolution.dll")
$psISE.CurrentPowerShellTab.VerticalAddOnTools.Add("Solutions", [ISESimpleSolution.Solution], $true)
```

### <a name="remove-item-"></a><span data-ttu-id="8e48a-115">Remove\( Item \)</span><span class="sxs-lookup"><span data-stu-id="8e48a-115">Remove\( Item \)</span></span>

<span data-ttu-id="8e48a-116">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="8e48a-116">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="8e48a-117">コレクションから指定したアドオン ツールを削除します。</span><span class="sxs-lookup"><span data-stu-id="8e48a-117">Removes the specified add-on tool from the collection.</span></span>

<span data-ttu-id="8e48a-118">**Item** - Microsoft.PowerShell.Host.ISE.ISEAddOnTool Windows PowerShell ISE から削除するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="8e48a-118">**Item** - Microsoft.PowerShell.Host.ISE.ISEAddOnTool Specifies the object to be removed from Windows PowerShell ISE.</span></span>

```powershell
# Load a DLL with an add-on and then add it to the ISE
[reflection.assembly]::LoadFile("c:\test\ISESimpleSolution\ISESimpleSolution.dll")
$psISE.CurrentPowerShellTab.VerticalAddOnTools.Add("Solutions", [ISESimpleSolution.Solution], $true)
```

### <a name="setselectedpowershelltab-pstab-"></a><span data-ttu-id="8e48a-119">SetSelectedPowerShellTab\( psTab \)</span><span class="sxs-lookup"><span data-stu-id="8e48a-119">SetSelectedPowerShellTab\( psTab \)</span></span>

<span data-ttu-id="8e48a-120">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="8e48a-120">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="8e48a-121">**psTab** パラメーターが指定する PowerShell タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="8e48a-121">Selects the PowerShell tab that the **psTab** parameter specifies.</span></span>

<span data-ttu-id="8e48a-122">**psTab** - PowerShell タブが選択するMicrosoft.PowerShell.Host.ISE.PowerShellTab。</span><span class="sxs-lookup"><span data-stu-id="8e48a-122">**psTab** - Microsoft.PowerShell.Host.ISE.PowerShellTab The PowerShell tab to select.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
# Change the DisplayName of the new PowerShell tab.
$newTab.DisplayName = 'Brand New Tab'
```

### <a name="remove-pstab-"></a><span data-ttu-id="8e48a-123">Remove\( psTab \)</span><span class="sxs-lookup"><span data-stu-id="8e48a-123">Remove\( psTab \)</span></span>

<span data-ttu-id="8e48a-124">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="8e48a-124">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="8e48a-125">**psTab** パラメーターが指定する PowerShell タブを削除します。</span><span class="sxs-lookup"><span data-stu-id="8e48a-125">Removes the PowerShell tab that the **psTab** parameter specifies.</span></span>

<span data-ttu-id="8e48a-126">**psTab** - PowerShell タブが削除する Microsoft.PowerShell.Host.ISE.PowerShellTab。</span><span class="sxs-lookup"><span data-stu-id="8e48a-126">**psTab** - Microsoft.PowerShell.Host.ISE.PowerShellTab The PowerShell tab to remove.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab.
$newTab.DisplayName = 'This tab will go away in 5 seconds'
sleep 5
$psISE.PowerShellTabs.Remove($newTab)
```

## <a name="see-also"></a><span data-ttu-id="8e48a-127">参照</span><span class="sxs-lookup"><span data-stu-id="8e48a-127">See Also</span></span>

- [<span data-ttu-id="8e48a-128">PowerShellTab オブジェクト</span><span class="sxs-lookup"><span data-stu-id="8e48a-128">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md)
- [<span data-ttu-id="8e48a-129">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="8e48a-129">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="8e48a-130">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="8e48a-130">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
