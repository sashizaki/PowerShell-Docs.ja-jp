---
title: ワイド ビューを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d4303c5-b451-4ccb-9831-b17a17ceac20
caps.latest.revision: 16
ms.openlocfilehash: 651de5d3bc2619f20438f3951ac5a8c4b0bf46d4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858498"
---
# <a name="creating-a-wide-view"></a><span data-ttu-id="e5b96-102">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="e5b96-102">Creating a Wide View</span></span>

<span data-ttu-id="e5b96-103">全体のビューには、表示される各オブジェクトの単一の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-103">A wide view displays a single value for each object that is displayed.</span></span> <span data-ttu-id="e5b96-104">表示される値には、.NET オブジェクトのプロパティの値またはスクリプトの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-104">The displayed value can be the value of a .NET object property or the value of a script.</span></span> <span data-ttu-id="e5b96-105">既定ではありませんラベルまたはこのビューのヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="e5b96-105">By default, there is no label or header for this view.</span></span>

## <a name="a-wide-view-display"></a><span data-ttu-id="e5b96-106">表示幅が広い表示</span><span class="sxs-lookup"><span data-stu-id="e5b96-106">A Wide View Display</span></span>

<span data-ttu-id="e5b96-107">次の例は、Windows PowerShell を表示する方法を示しています、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクトによって返される、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットの出力がパイプを使用するとき、 [Format-wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="e5b96-107">The following example shows how Windows PowerShell displays the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object that is returned by the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet when its output is piped to the [Format-Wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide) cmdlet.</span></span> <span data-ttu-id="e5b96-108">(既定で、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットは、テーブル ビューを返します)。この例では、2 つの列が返された各オブジェクトのプロセスの名前を表示に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-108">(By default, the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns a table view.) In this example, the two columns are used to display the name of the process for each returned object.</span></span> <span data-ttu-id="e5b96-109">オブジェクトのプロパティの名前が表示されないプロパティの値のみです。</span><span class="sxs-lookup"><span data-stu-id="e5b96-109">The name of the object's property is not displayed, only the value of the property.</span></span>

```
Get-Process | format-wide
AEADISRV                     agrsmsvc
Ati2evxx                     Ati2evxx
audiodg                      CCC
CcmExec                      communicator
Crypserv                     csrss
csrss                        DevDtct2
DM1Service                   dpupdchk
dwm                          DxStudio
EXCEL                        explorer
GoogleToolbarNotifier        GrooveMonitor
hpqwmiex                     hpservice
Idle                         InoRpc
InoRT                        InoTask
ipoint                       lsass
lsm                          MOM
MSASCui                      notepad
...                          ...

```

## <a name="defining-the-wide-view"></a><span data-ttu-id="e5b96-110">ワイド ビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-110">Defining the Wide View</span></span>

<span data-ttu-id="e5b96-111">次の XML の表示幅が広いスキーマを示しています、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e5b96-111">The following XML shows the wide view schema for the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <GroupBy>...</GroupBy>
  <Controls>...</Controls>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

<span data-ttu-id="e5b96-112">次の XML 要素は、ワイド ビュー定義に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-112">The following XML elements are used to define a wide view:</span></span>

- <span data-ttu-id="e5b96-113">[ビュー](./view-element-format.md)要素は、ワイド ビューの親要素です。</span><span class="sxs-lookup"><span data-stu-id="e5b96-113">The [View](./view-element-format.md) element is the parent element of the wide view.</span></span> <span data-ttu-id="e5b96-114">(これは、テーブル、リスト、およびカスタムのコントロール ビューに、同じ親要素です)。</span><span class="sxs-lookup"><span data-stu-id="e5b96-114">(This is the same parent element for the table, list, and custom control views.)</span></span>

- <span data-ttu-id="e5b96-115">[名前](./name-element-for-view-format.md)要素は、ビューの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-115">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="e5b96-116">この要素は、すべてのビューに必要です。</span><span class="sxs-lookup"><span data-stu-id="e5b96-116">This element is required for all views.</span></span>

- <span data-ttu-id="e5b96-117">[ViewSelectedBy](./viewselectedby-element-format.md)要素は、ビューを使用するオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-117">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="e5b96-118">この要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="e5b96-118">This element is required.</span></span>

- <span data-ttu-id="e5b96-119">[GroupBy](./groupby-element-for-view-format.md)オブジェクトの新しいグループが表示される要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-119">The [GroupBy](./groupby-element-for-view-format.md) element defines when a new group of objects is displayed.</span></span> <span data-ttu-id="e5b96-120">特定のプロパティまたはスクリプトの値が変更されるたびに新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-120">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="e5b96-121">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e5b96-121">This element is optional.</span></span>

- <span data-ttu-id="e5b96-122">[コントロール](./controls-element-for-view-format.md)要素は、ワイド ビューで定義されているカスタム コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-122">The [Controls](./controls-element-for-view-format.md) elements defines the custom controls that are defined by the wide view.</span></span> <span data-ttu-id="e5b96-123">コントロールでは、さらに、データの表示方法を指定する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-123">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="e5b96-124">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e5b96-124">This element is optional.</span></span> <span data-ttu-id="e5b96-125">ビューがその独自のカスタム コントロールを定義できます。 または書式設定ファイルに任意のビューで使用できる一般的なコントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-125">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="e5b96-126">カスタム コントロールの詳細については、次を参照してください。[カスタム コントロールを作成する](./creating-custom-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-126">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="e5b96-127">[WideControl](./widecontrol-element-format.md)要素とその子要素は、ビューに表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-127">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span> <span data-ttu-id="e5b96-128">前の例では、表示するビューを設計、 [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName)プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e5b96-128">In the preceding example, the view is designed to display the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span>

<span data-ttu-id="e5b96-129">単純なワイド ビューを定義する完全な書式設定ファイルの例は、次を参照してください。[表示 (Basic) の幅が広い](./wide-view-basic.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-129">For an example of a complete formatting file that defines a simple wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="providing-definitions-for-your-wide-view"></a><span data-ttu-id="e5b96-130">ワイド ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-130">Providing Definitions for Your Wide View</span></span>

<span data-ttu-id="e5b96-131">ワイド ビューの子要素を使用して、1 つまたは複数の定義を提供することができます、 [WideControl](./widecontrol-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="e5b96-131">Wide views can provide one or more definitions by using the child elements of the [WideControl](./widecontrol-element-format.md) element.</span></span> <span data-ttu-id="e5b96-132">通常、ビューには、1 つだけ定義があります。</span><span class="sxs-lookup"><span data-stu-id="e5b96-132">Typically, a view will have only one definition.</span></span> <span data-ttu-id="e5b96-133">ビューでの値を表示する 1 つの定義は、次の例では、 [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName)プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e5b96-133">In the following example, the view provides a single definition that displays the value of the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span> <span data-ttu-id="e5b96-134">ワイド ビューには、プロパティの値またはスクリプト (この例では表示されません) の値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-134">A wide view can display the value of a property or the value of a script (not shown in the example).</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber></ColumnNumber>
  <WideEntries>
    <WideEntry>
      <WideItem>
        <PropertyName>ProcessName</PropertyName>
      </WideItem>
    </WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="e5b96-135">次の XML 要素は、ワイド ビューの定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-135">The following XML elements can be used to provide definitions for a wide view:</span></span>

- <span data-ttu-id="e5b96-136">[WideControl](./widecontrol-element-format.md)要素とその子要素は、ビューに表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-136">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span>

- <span data-ttu-id="e5b96-137">[AutoSize](./autosize-element-for-widecontrol-format.md)要素は、かどうか、列のサイズと列の数が調整のデータのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-137">The [AutoSize](./autosize-element-for-widecontrol-format.md) element specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span> <span data-ttu-id="e5b96-138">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e5b96-138">This element is optional.</span></span>

- <span data-ttu-id="e5b96-139">[ColumnNumber](./columnnumber-element-for-widecontrol-format.md)要素をワイド ビューに表示される列の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-139">The [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element specifies the number of columns displayed in the wide view.</span></span> <span data-ttu-id="e5b96-140">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e5b96-140">This element is optional.</span></span>

- <span data-ttu-id="e5b96-141">[WideEntries](./wideentries-element-for-widecontrol-format.md)要素は、ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-141">The [WideEntries](./wideentries-element-for-widecontrol-format.md) element provides the definitions of the view.</span></span> <span data-ttu-id="e5b96-142">ほとんどの場合、ビューは 1 つだけ定義になります。</span><span class="sxs-lookup"><span data-stu-id="e5b96-142">In most cases, a view will have only one definition.</span></span> <span data-ttu-id="e5b96-143">この要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="e5b96-143">This element is required.</span></span>

- <span data-ttu-id="e5b96-144">[WideEntry](./wideentry-element-for-widecontrol-format.md)要素は、ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-144">The [WideEntry](./wideentry-element-for-widecontrol-format.md) element provides a definition of the view.</span></span> <span data-ttu-id="e5b96-145">少なくとも 1 つ[WideEntry](./wideentry-element-for-widecontrol-format.md)が必要です。 ただし、追加できる要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="e5b96-145">At least one [WideEntry](./wideentry-element-for-widecontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="e5b96-146">ほとんどの場合、ビューは 1 つだけ定義になります。</span><span class="sxs-lookup"><span data-stu-id="e5b96-146">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="e5b96-147">[EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md)要素は、特定の定義によって表示されるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-147">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="e5b96-148">この要素は省略可能と複数を定義する場合にのみ必要です[WideEntry](./wideentry-element-for-widecontrol-format.md)さまざまなオブジェクトを表示する要素。</span><span class="sxs-lookup"><span data-stu-id="e5b96-148">This element is optional and is needed only when you define multiple [WideEntry](./wideentry-element-for-widecontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="e5b96-149">[WideItem](./wideitem-element-for-widecontrol-format.md)要素は、ビューによって表示されるデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-149">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span> <span data-ttu-id="e5b96-150">他の種類のビューとは対照的ワイド コントロールは、1 つの項目を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-150">In contrast to other types of views, a wide control can display only one item.</span></span>

- <span data-ttu-id="e5b96-151">[PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md)要素が値を持つが、ビューによって表示されるプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-151">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="e5b96-152">プロパティまたはスクリプトのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5b96-152">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="e5b96-153">[ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md)要素は、ビューによって表示される値を持つスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-153">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="e5b96-154">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5b96-154">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="e5b96-155">[FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md)要素は、データを表示するために使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-155">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a pattern that is used to display the data.</span></span> <span data-ttu-id="e5b96-156">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e5b96-156">This element is optional.</span></span>

<span data-ttu-id="e5b96-157">表示幅が広い定義を定義する完全な書式設定ファイルの例は、次を参照してください。[表示 (Basic) の幅が広い](./wide-view-basic.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-157">For an example of a complete formatting file that defines a wide view definition, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="defining-the-objects-that-use-the-wide-view"></a><span data-ttu-id="e5b96-158">表示幅が広いを使用するオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-158">Defining the Objects That Use the Wide View</span></span>

<span data-ttu-id="e5b96-159">.NET オブジェクトを使用して、表示幅が広いを定義する 2 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="e5b96-159">There are two ways to define which .NET objects use the wide view.</span></span> <span data-ttu-id="e5b96-160">使用することができます、 [ViewSelectedBy](./viewselectedby-element-format.md)するか、ビューのすべての定義を表示できるオブジェクトを定義する要素を使用できる、 [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md)によって表示されるオブジェクトを定義する要素、ビューの定義を特定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-160">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="e5b96-161">ほとんどの場合、ビューでは 1 つだけ定義は、オブジェクトは通常で定義されるため、 [ViewSelectedBy](./viewselectedby-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="e5b96-161">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="e5b96-162">次の例は、表示幅が広いを使用して表示されるオブジェクトを定義する方法を示します、 [ViewSelectedBy](./viewselectedby-element-format.md)と[TypeName](./typename-element-for-viewselectedby-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="e5b96-162">The following example shows how to define the objects that are displayed by the wide view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="e5b96-163">数に制限はありません[TypeName](./typename-element-for-viewselectedby-format.md)要素を指定できますが、およびその順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="e5b96-163">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="e5b96-164">表示幅が広いによって使用されるオブジェクトを指定する、次の XML 要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-164">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="e5b96-165">[ViewSelectedBy](./viewselectedby-element-format.md)要素は、ワイド ビューによって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-165">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="e5b96-166">[TypeName](./typename-element-for-viewselectedby-format.md)要素は、ビューによって表示される、.NET を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-166">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the view.</span></span> <span data-ttu-id="e5b96-167">完全修飾 .NET 型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="e5b96-167">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="e5b96-168">少なくとも 1 つの型またはビューの設定の選択範囲を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="e5b96-168">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="e5b96-169">完全な書式設定ファイルの例は、次を参照してください。[表示 (Basic) の幅が広い](./wide-view-basic.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-169">For an example of a complete formatting file, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

<span data-ttu-id="e5b96-170">次の例では、 [ViewSelectedBy](./viewselectedby-element-format.md)と[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="e5b96-170">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="e5b96-171">関連する一連のワイド ビューを定義する場合など、複数のビューおよびテーブル ビューを使用して、同じオブジェクトに対して表示されるオブジェクトがある選択範囲のセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-171">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a wide view and a table view for the same objects.</span></span> <span data-ttu-id="e5b96-172">選択範囲のセットを作成する方法の詳細については、次を参照してください。[選択範囲のセットを定義する](./defining-selection-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-172">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="e5b96-173">表示幅が広いによって使用されるオブジェクトを指定する、次の XML 要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-173">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="e5b96-174">[ViewSelectedBy](./viewselectedby-element-format.md)要素は、ワイド ビューによって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-174">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="e5b96-175">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素は、一連のビューで表示できるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-175">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="e5b96-176">少なくとも 1 つの選択範囲のセットまたはビューの種類を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="e5b96-176">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="e5b96-177">次の例は、特定の定義を使用して、表示幅が広いで表示されるオブジェクトを定義する方法を示します、 [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="e5b96-177">The following example shows how to define the objects displayed by a specific definition of the wide view using the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element.</span></span> <span data-ttu-id="e5b96-178">この要素を使用して、オブジェクト、オブジェクトの選択範囲のセットまたは定義を使用する場合を指定する選択条件の .NET 型名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-178">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="e5b96-179">選択条件を作成する方法の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-179">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</WideEntry>
```

<span data-ttu-id="e5b96-180">表示幅が広いの特定の定義で使用されるオブジェクトを指定する、次の XML 要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-180">The following XML elements can be used to specify the objects that are used by a specific definition of the wide view:</span></span>

- <span data-ttu-id="e5b96-181">[EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md)要素定義によって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-181">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="e5b96-182">[TypeName](./typename-element-for-viewselectedby-format.md)要素を定義して表示される .NET を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-182">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the definition.</span></span> <span data-ttu-id="e5b96-183">この要素を使用する場合は、完全修飾 .NET 型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="e5b96-183">When using this element the fully qualified .NET type name is required.</span></span> <span data-ttu-id="e5b96-184">少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="e5b96-184">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="e5b96-185">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) (表示されない) 要素は、この定義で表示できるオブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-185">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="e5b96-186">少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="e5b96-186">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="e5b96-187">[SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) (表示されない) 要素は、この定義を使用するのに必要な条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-187">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="e5b96-188">少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="e5b96-188">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="e5b96-189">選択条件を定義する詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-189">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="displaying-groups-of-objects-in-a-wide-view"></a><span data-ttu-id="e5b96-190">ワイド ビューでオブジェクトのグループを表示します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-190">Displaying Groups of objects in a Wide View</span></span>

<span data-ttu-id="e5b96-191">グループにワイド ビューによって表示されるオブジェクトを分離することができます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-191">You can separate the objects that are displayed by the wide view into groups.</span></span> <span data-ttu-id="e5b96-192">限りませんグループを定義するだけで、特定のプロパティまたはスクリプトの値が変更されるたびに、その Windows PowerShell は新しいグループを開始します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-192">This does not mean that you define a group, only that Windows PowerShell starts a new group whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="e5b96-193">次の例で新しいグループが開始されるたびの値、 [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType)プロパティの変更。</span><span class="sxs-lookup"><span data-stu-id="e5b96-193">In the following example, a new group is started whenever the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="e5b96-194">次の XML 要素は、グループの開始時に定義に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-194">The following XML elements are used to define when a group is started:</span></span>

- <span data-ttu-id="e5b96-195">[GroupBy](./groupby-element-for-view-format.md)プロパティまたは新しいグループを開始し、グループの表示方法を定義するスクリプト要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-195">The [GroupBy](./groupby-element-for-view-format.md) element defines the property or script that starts the new group and defines how the group is displayed.</span></span>

- <span data-ttu-id="e5b96-196">[PropertyName](./propertyname-element-for-groupby-format.md)要素は、その値が変更されるたびに新しいグループを開始するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-196">The [PropertyName](./propertyname-element-for-groupby-format.md) element specifies the property that starts a new group whenever its value changes.</span></span> <span data-ttu-id="e5b96-197">プロパティまたはグループを開始するスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5b96-197">You must specify a property or script to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="e5b96-198">[ScriptBlock](./scriptblock-element-for-groupby-format.md)要素は、その値が変更されるたびに、新しいグループを開始するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-198">The [ScriptBlock](./scriptblock-element-for-groupby-format.md) element specifies the script that starts a new group whenever its value changes.</span></span> <span data-ttu-id="e5b96-199">スクリプトまたはグループを開始するプロパティを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5b96-199">You must specify a script or property to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="e5b96-200">[ラベル](./label-element-for-groupby-format.md)要素は、各グループの先頭に表示されるラベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-200">The [Label](./label-element-for-groupby-format.md) element defines a label that is displayed at the beginning of each group.</span></span> <span data-ttu-id="e5b96-201">この要素で指定されたテキスト、だけでなく Windows PowerShell には、新しいグループがトリガーされ、ラベルの前後に空白行を追加する値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-201">In addition to the text specified by this element, Windows PowerShell displays the value that triggered the new group and adds a blank line before and after the label.</span></span> <span data-ttu-id="e5b96-202">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e5b96-202">This element is optional.</span></span>

- <span data-ttu-id="e5b96-203">[カスタム コントロール](./customcontrol-element-for-groupby-format.md)要素は、データを表示するために使用するコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-203">The [CustomControl](./customcontrol-element-for-groupby-format.md) element defines a control that is used to display the data.</span></span> <span data-ttu-id="e5b96-204">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e5b96-204">This element is optional.</span></span>

- <span data-ttu-id="e5b96-205">[CustomControlName](./customcontrolname-element-for-groupby-format.md)要素は、一般的なを指定します。 または、データを表示するために使用するコントロールを表示します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-205">The [CustomControlName](./customcontrolname-element-for-groupby-format.md) element specifies a common or view control that is used to display the data.</span></span> <span data-ttu-id="e5b96-206">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e5b96-206">This element is optional.</span></span>

<span data-ttu-id="e5b96-207">グループを定義する完全な書式設定ファイルの例は、次を参照してください。[表示幅が広い (GroupBy)](./wide-view-groupby.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-207">For an example of a complete formatting file that defines groups, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="e5b96-208">書式指定文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-208">Using Format Strings</span></span>

<span data-ttu-id="e5b96-209">さらに、データの表示方法を定義するワイド ビューには、書式設定文字列を追加できます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-209">Formatting strings can be added to a wide view to further define how the data is displayed.</span></span> <span data-ttu-id="e5b96-210">次の例の値の書式指定文字列を定義する方法を示しています、`StartTime`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e5b96-210">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

<span data-ttu-id="e5b96-211">次の XML 要素を使用して、書式パターンを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-211">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="e5b96-212">[WideItem](./wideitem-element-for-widecontrol-format.md)要素は、ビューによって表示されるデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-212">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="e5b96-213">[PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md)要素が値を持つが、ビューによって表示されるプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-213">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="e5b96-214">プロパティまたはスクリプトのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5b96-214">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="e5b96-215">[FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md)要素は、ビューで、プロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します</span><span class="sxs-lookup"><span data-stu-id="e5b96-215">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed in the view</span></span>

- <span data-ttu-id="e5b96-216">[ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) (表示されない) 要素をビューで表示される値を持つスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-216">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="e5b96-217">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5b96-217">You must specify either a script or a property, but you cannot specify both.</span></span>

<span data-ttu-id="e5b96-218">次の例では、`ToString`スクリプトの値の書式設定メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-218">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="e5b96-219">スクリプトでは、オブジェクトのすべてのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-219">Scripts can call any method of an object.</span></span> <span data-ttu-id="e5b96-220">そのため、オブジェクトが、メソッドがなど`ToString`、書式設定パラメーターを持つ、スクリプトは、スクリプトの出力値の書式を指定するには、そのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e5b96-220">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<WideItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</WideItem>
```

<span data-ttu-id="e5b96-221">次の XML 要素を呼び出すことができます、`ToString`メソッド。</span><span class="sxs-lookup"><span data-stu-id="e5b96-221">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="e5b96-222">[WideItem](./wideitem-element-for-widecontrol-format.md)要素は、ビューによって表示されるデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-222">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="e5b96-223">[ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) (表示されない) 要素をビューで表示される値を持つスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b96-223">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="e5b96-224">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5b96-224">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5b96-225">参照</span><span class="sxs-lookup"><span data-stu-id="e5b96-225">See Also</span></span>

[<span data-ttu-id="e5b96-226">表示幅が広い (Basic)</span><span class="sxs-lookup"><span data-stu-id="e5b96-226">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="e5b96-227">表示幅が広い (GroupBy)</span><span class="sxs-lookup"><span data-stu-id="e5b96-227">Wide View (GroupBy)</span></span>](./wide-view-groupby.md)

[<span data-ttu-id="e5b96-228">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="e5b96-228">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
