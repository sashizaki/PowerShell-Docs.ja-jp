---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell ISE オブジェクト モデル リファレンス"
ms.assetid: e1a9e7d1-0fd5-47de-8d9b-f1be1ed13b0c
ms.openlocfilehash: 624ddca3895ba3e24bf52a27babdb07e8714baae
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2017
---
# <a name="windows-powershell-ise-object-model-reference"></a><span data-ttu-id="27594-103">Windows PowerShell ISE オブジェクト モデル リファレンス</span><span class="sxs-lookup"><span data-stu-id="27594-103">Windows PowerShell ISE Object Model Reference</span></span>
  
## <a name="object-model-reference"></a><span data-ttu-id="27594-104">オブジェクト モデル リファレンス</span><span class="sxs-lookup"><span data-stu-id="27594-104">Object Model Reference</span></span>
 <span data-ttu-id="27594-105">このセクションでは、Windows PowerShell® Integrated Scripting Environment (ISE) で各種オブジェクトを定義する基礎となるクラスへのリファレンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="27594-105">This section provides a reference on the underlying classes that define the various objects inWindows PowerShell® Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="27594-106">これらのオブジェクトの階層構造については、「[ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27594-106">To see the objects organized in their hierarchy, see [The ISE Object Model Hierarchy](The-ISE-Object-Model-Hierarchy.md).</span></span>

 <span data-ttu-id="27594-107">[ISEAddOnTool オブジェクト](The-ISEAddOnTool-Object.md) 例: $psISE.CurrentVisibleHorizontalTool、$psISE.CurrentVisibleVerticalTool。</span><span class="sxs-lookup"><span data-stu-id="27594-107">[The ISEAddOnTool Object](The-ISEAddOnTool-Object.md) Examples: $psISE.CurrentVisibleHorizontalTool, $psISE.CurrentVisibleVerticalTool.</span></span>

 <span data-ttu-id="27594-108">[ISEAddOnTool オブジェクト](The-ISEAddOnTool-Object.md)[ISEEditor オブジェクト](The-ISEEditor-Object.md) 例: $psISE.CurrentFile.Editor、$psISE.CurrentPowerShellTab.Output、$psISE.CurrentPowerShellTab.CommandPane。</span><span class="sxs-lookup"><span data-stu-id="27594-108">[The ISEAddOnTool Object](The-ISEAddOnTool-Object.md) [The ISEEditor Object](The-ISEEditor-Object.md) Examples: $psISE.CurrentFile.Editor, $psISE.CurrentPowerShellTab.Output, $psISE.CurrentPowerShellTab.CommandPane.</span></span>

 <span data-ttu-id="27594-109">[ISEFile オブジェクト](The-ISEFile-Object.md) 例: $psISE.CurrentFile、$psISE.PowerShellTabs.Files\[0\]。</span><span class="sxs-lookup"><span data-stu-id="27594-109">[The ISEFile Object](The-ISEFile-Object.md) Examples: $psISE.CurrentFile, $psISE.PowerShellTabs.Files\[0\].</span></span>

 <span data-ttu-id="27594-110">[ISEFileCollection オブジェクト](The-ISEFileCollection-Object.md) 例: $psISE.PowerShellTabs.Files。</span><span class="sxs-lookup"><span data-stu-id="27594-110">[The ISEFileCollection Object](The-ISEFileCollection-Object.md) Examples: $psISE.PowerShellTabs.Files.</span></span>

 <span data-ttu-id="27594-111">[ISEMenuItem オブジェクト](The-ISEMenuItem-Object.md) 例: $psISE.CurrentPowerShellTab.AddOnsMenu、$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus\[0\]。</span><span class="sxs-lookup"><span data-stu-id="27594-111">[The ISEMenuItem Object](The-ISEMenuItem-Object.md) Examples: $psISE.CurrentPowerShellTab.AddOnsMenu , $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus\[0\].</span></span>

 <span data-ttu-id="27594-112">[ISEMenuItemCollection オブジェクト](The-ISEMenuItemCollection-Object.md) 例: $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus。</span><span class="sxs-lookup"><span data-stu-id="27594-112">[The ISEMenuItemCollection Object](The-ISEMenuItemCollection-Object.md) Example: $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.</span></span>

 <span data-ttu-id="27594-113">[ISEOptions オブジェクト](The-ISEOptions-Object.md) 例: $psISE.Options、$psISE.Options.DefaultOptions。</span><span class="sxs-lookup"><span data-stu-id="27594-113">[The ISEOptions Object](The-ISEOptions-Object.md) Examples: $psISE.Options, $psISE.Options.DefaultOptions.</span></span>

 <span data-ttu-id="27594-114">[ObjectModelRoot オブジェクト](The-ObjectModelRoot-Object.md) 例: ルート $psISE オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="27594-114">[The ObjectModelRoot Object](The-ObjectModelRoot-Object.md) Example: The root $psISE object.</span></span>

 <span data-ttu-id="27594-115">[PowerShellTab オブジェクト](The-PowerShellTab-Object.md) 例: $psISE.CurrentPowerShellTab、$psISE.PowerShellTabs\[0\]。</span><span class="sxs-lookup"><span data-stu-id="27594-115">[The PowerShellTab Object](The-PowerShellTab-Object.md) Examples: $psISE.CurrentPowerShellTab, $psISE.PowerShellTabs\[0\].</span></span>

 <span data-ttu-id="27594-116">[PowerShellTabCollection オブジェクト](The-PowerShellTabCollection-Object.md) 例: $psISE.PowerShellTabs。</span><span class="sxs-lookup"><span data-stu-id="27594-116">[The PowerShellTabCollection Object](The-PowerShellTabCollection-Object.md) Example: $psISE.PowerShellTabs.</span></span>

## <a name="see-also"></a><span data-ttu-id="27594-117">参照</span><span class="sxs-lookup"><span data-stu-id="27594-117">See Also</span></span>
- [<span data-ttu-id="27594-118">Windows PowerShell ISE スクリプト オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="27594-118">The Windows PowerShell ISE Scripting Object Model</span></span>](The-Windows-PowerShell-ISE-Scripting-Object-Model.md)
