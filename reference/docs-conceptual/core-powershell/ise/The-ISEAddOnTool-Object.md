---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: ISEAddOnTool オブジェクト
ms.assetid: ce84d8bc-07ba-41f6-bdde-d6f3fddcd1e3
ms.openlocfilehash: e091f37601c7a4fdaf5deff8c668b18ee7369e74
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
ms.locfileid: "30954808"
---
# <a name="the-iseaddontool-object"></a><span data-ttu-id="b2955-103">ISEAddOnTool オブジェクト</span><span class="sxs-lookup"><span data-stu-id="b2955-103">The ISEAddOnTool Object</span></span>

<span data-ttu-id="b2955-104">**ISEAddonTool** オブジェクトは、Windows PowerShell ISE に追加の機能を提供する、インストール済みのアドオン ツールを表します。</span><span class="sxs-lookup"><span data-stu-id="b2955-104">An **ISEAddonTool** object represents an installed add-on tool that provides additional functionality toWindows PowerShell ISE.</span></span> <span data-ttu-id="b2955-105">例としては、**[表示]**、**[コマンド アドオンの表示]** の順にクリックして表示できる**コマンド** ツールです。</span><span class="sxs-lookup"><span data-stu-id="b2955-105">An example is the **Commands** tool that you can display by clicking **View**, then **Show Command Add-on**.</span></span> <span data-ttu-id="b2955-106">このツールには、利用可能なさまざまな **ISEAddOnTool** オブジェクトを操作することでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b2955-106">This tool is then accessible to you by manipulating the various available **ISEAddOnTool** objects.</span></span>

<span data-ttu-id="b2955-107">各アドオン ツールは、垂直方向のウィンドウまたは水平方向のウィンドウのいずれかと関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="b2955-107">Each add-on tool can be associated with either the vertical pane or the horizontal pane.</span></span> <span data-ttu-id="b2955-108">垂直方向のウィンドウは、Windows PowerShell ISE の右端にドッキングされています。</span><span class="sxs-lookup"><span data-stu-id="b2955-108">The vertical pane is docked to the right edge of Windows PowerShell ISE.</span></span> <span data-ttu-id="b2955-109">水平方向のウィンドウは、下端にドッキングされています。</span><span class="sxs-lookup"><span data-stu-id="b2955-109">The horizontal pane is docked to the bottom edge.</span></span>

<span data-ttu-id="b2955-110">Windows PowerShell ISE の各 PowerShell タブには、インストール済みのアドオン ツールの固有のセットを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b2955-110">Each PowerShell tab in Windows PowerShell ISE can have its own set of add-on tools installed.</span></span> <span data-ttu-id="b2955-111">現在選択しているタブで使用できるツールのコレクション、または [$psISE.PowerShellTabs](The-PowerShellTabCollection-Object.md) コレクション オブジェクトのいずれかの **PowerShellTab** オブジェクトの同じプロパティのコレクションにアクセスするには、[$psISE.CurrentPowerShellTab.HorizontalAddOnTools](The-PowerShellTab-Object.md) および [$psISE.CurrentPowerShellTab.VerticalAddOnTools](The-PowerShellTab-Object.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2955-111">See [$psISE.CurrentPowerShellTab.HorizontalAddOnTools](The-PowerShellTab-Object.md) and [$psISE.CurrentPowerShellTab.VerticalAddOnTools](The-PowerShellTab-Object.md) to access the collection of tools available to the currently selected tab or the same properties on any of the **PowerShellTab** objects in the [$psISE.PowerShellTabs](The-PowerShellTabCollection-Object.md) collection object.</span></span>

## <a name="methods"></a><span data-ttu-id="b2955-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="b2955-112">Methods</span></span>

<span data-ttu-id="b2955-113">このクラスのオブジェクトで使用できる Windows PowerShell ISE 固有のメソッドはありません。</span><span class="sxs-lookup"><span data-stu-id="b2955-113">There are no Windows PowerShell ISE-specific methods available for objects of this class.</span></span>

## <a name="properties"></a><span data-ttu-id="b2955-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b2955-114">Properties</span></span>

### <a name="control"></a><span data-ttu-id="b2955-115">Control</span><span class="sxs-lookup"><span data-stu-id="b2955-115">Control</span></span>

<span data-ttu-id="b2955-116">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="b2955-116">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="b2955-117">**コントロール** プロパティは、コマンド アドオン ツールの詳細への読み取りアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b2955-117">The **Control** property provides read access to many of the details of the Commands add-on tool.</span></span>

```powershell
# View the properties of the Commands add-on tool.
# (assumes that it is visible in the vertical pane)
$psISE.CurrentVisibleVerticalTool.Control
HostObject                  : Microsoft.PowerShell.Host.ISE.ObjectModelRoot
Content                     :
HasContent                  :
ContentTemplate             :
ContentTemplateSelector     :
ContentStringFormat         :
BorderBrush                 :
BorderThickness             :
Background                  :
Foreground                  :
FontFamily                  :
FontSize                    :
FontStretch                 :
FontStyle                   :
FontWeight                  :
HorizontalContentAlignment  :
VerticalContentAlignment    :
TabIndex                    :
IsTabStop                   :
Padding                     :
Template                    : System.Windows.Controls.ControlTemplate
Style                       :
OverridesDefaultStyle       :
UseLayoutRounding           :
Triggers                    : {}
TemplatedParent             :
Resources                   : {System.Windows.Controls.TabItem}
DataContext                 :
BindingGroup                :
Language                    :
Name                        :
Tag                         :
InputScope                  :
ActualWidth                 : 370.75
ActualHeight                : 676.559097412109
LayoutTransform             :
Width                       :
MinWidth                    :
MaxWidth                    :
Height                      :
MinHeight                   :
MaxHeight                   :
FlowDirection               : LeftToRight
Margin                      :
HorizontalAlignment         :
VerticalAlignment           :
FocusVisualStyle            :
Cursor                      :
ForceCursor                 :
IsInitialized               : True
IsLoaded                    :
ToolTip                     :
ContextMenu                 :
Parent                      :
HasAnimatedProperties       :
InputBindings               :
CommandBindings             :
AllowDrop                   :
DesiredSize                 : 227.66,676.559097412109
IsMeasureValid              : True
IsArrangeValid              : True
RenderSize                  : 370.75,676.559097412109
RenderTransform             :
RenderTransformOrigin       :
IsMouseDirectlyOver         : False
IsMouseOver                 : False
IsStylusOver                : False
IsKeyboardFocusWithin       : False
IsMouseCaptured             :
IsMouseCaptureWithin        : False
IsStylusDirectlyOver        : False
IsStylusCaptured            :
IsStylusCaptureWithin       : False
IsKeyboardFocused           : False
IsInputMethodEnabled        :
Opacity                     :
OpacityMask                 :
BitmapEffect                :
Effect                      :
BitmapEffectInput           :
CacheMode                   :
Uid                         :
Visibility                  : Visible
ClipToBounds                : False
Clip                        :
SnapsToDevicePixels         : False
IsFocused                   :
IsEnabled                   :
IsHitTestVisible            :
IsVisible                   : True
Focusable                   :
PersistId                   : 1
IsManipulationEnabled       :
AreAnyTouchesOver           : False
AreAnyTouchesDirectlyOver   :
AreAnyTouchesCapturedWithin : False
AreAnyTouchesCaptured       :
TouchesCaptured             : {}
TouchesCapturedWithin       : {}
TouchesOver                 : {}
TouchesDirectlyOver         : {}
DependencyObjectType        : System.Windows.DependencyObjectType
IsSealed                    : False
Dispatcher                  : System.Windows.Threading.Dispatcher
```

### <a name="isvisible"></a><span data-ttu-id="b2955-118">IsVisible</span><span class="sxs-lookup"><span data-stu-id="b2955-118">IsVisible</span></span>

<span data-ttu-id="b2955-119">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="b2955-119">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="b2955-120">割り当てられているウィンドウにアドオン ツールが現在表示されているかどうかを示すブール型プロパティ。</span><span class="sxs-lookup"><span data-stu-id="b2955-120">The Boolean property that indicates whether the add-on tool is currently visible in its assigned pane.</span></span> <span data-ttu-id="b2955-121">表示されている場合は、**IsVisible** プロパティを **$false** を設定すると、ツールを非表示にすることができます。**IsVisible** プロパティを **$true** に設定すると、PowerShell でアドオン ツールが表示されます。アドオン ツールを非表示にすると、**CurrentVisibleHorizontalTool** または **CurrentVisibleVerticalTool** オブジェクトからアクセスできなくなるため、これらのオブジェクトのこのプロパティを使用して表示するようにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b2955-121">If it is visible, you can set the **IsVisible** property to **$false** to hide the tool, or set the **IsVisible** property to **$true** to make an add-on tool visible on its PowerShell tab. Note that after an add-on tool is hidden, it is no longer accessible through the **CurrentVisibleHorizontalTool** or **CurrentVisibleVerticalTool** objects, and therefore cannot be made visible by using this property on that object.</span></span>

```powershell
# Hide the current tool in the vertical tool pane
$psISE.CurrentVisibleVerticalTool.IsVisible = $false
# Show the first tool on the currently selected PowerShell tab
$psISE.CurrentPowerShellTab.VerticalAddOnTools[0].IsVisible = $true
```

### <a name="name"></a><span data-ttu-id="b2955-122">名前</span><span class="sxs-lookup"><span data-stu-id="b2955-122">Name</span></span>

<span data-ttu-id="b2955-123">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="b2955-123">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="b2955-124">アドオン ツールの名前を取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="b2955-124">The read-only property that gets the name of the add-on tool.</span></span>

```powershell
# Gets the name of the visible vertical pane add-on tool.
$psISE.CurrentVisibleVerticalTool.Name
Commands
```

## <a name="see-also"></a><span data-ttu-id="b2955-125">参照</span><span class="sxs-lookup"><span data-stu-id="b2955-125">See Also</span></span>

- [<span data-ttu-id="b2955-126">ISEAddOnToolCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="b2955-126">The ISEAddOnToolCollection Object</span></span>](The-ISEAddOnToolCollection-Object.md)
- [<span data-ttu-id="b2955-127">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="b2955-127">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="b2955-128">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="b2955-128">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)