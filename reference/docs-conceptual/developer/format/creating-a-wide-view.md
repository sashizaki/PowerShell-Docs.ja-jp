---
title: ワイドビューを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d4303c5-b451-4ccb-9831-b17a17ceac20
caps.latest.revision: 16
ms.openlocfilehash: 651de5d3bc2619f20438f3951ac5a8c4b0bf46d4
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368951"
---
# <a name="creating-a-wide-view"></a><span data-ttu-id="b5415-102">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="b5415-102">Creating a Wide View</span></span>

<span data-ttu-id="b5415-103">ワイドビューでは、表示されているオブジェクトごとに1つの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5415-103">A wide view displays a single value for each object that is displayed.</span></span> <span data-ttu-id="b5415-104">表示される値には、.NET オブジェクトプロパティの値、またはスクリプトの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b5415-104">The displayed value can be the value of a .NET object property or the value of a script.</span></span> <span data-ttu-id="b5415-105">既定では、このビューにはラベルまたはヘッダーがありません。</span><span class="sxs-lookup"><span data-stu-id="b5415-105">By default, there is no label or header for this view.</span></span>

## <a name="a-wide-view-display"></a><span data-ttu-id="b5415-106">ワイドビューの表示</span><span class="sxs-lookup"><span data-stu-id="b5415-106">A Wide View Display</span></span>

<span data-ttu-id="b5415-107">次の例は、Windows PowerShell の出力が[フォーマット全体](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide)のコマンドレットにパイプされるときに、 [Get process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットによって返さ[れる system.object オブジェクトを表示](/dotnet/api/System.Diagnostics.Process)する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b5415-107">The following example shows how Windows PowerShell displays the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object that is returned by the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet when its output is piped to the [Format-Wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide) cmdlet.</span></span> <span data-ttu-id="b5415-108">(既定では、 [Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットはテーブルビューを返します)。この例では、2つの列を使用して、返された各オブジェクトのプロセスの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="b5415-108">(By default, the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns a table view.) In this example, the two columns are used to display the name of the process for each returned object.</span></span> <span data-ttu-id="b5415-109">オブジェクトのプロパティの名前は表示されず、プロパティの値のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5415-109">The name of the object's property is not displayed, only the value of the property.</span></span>

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

## <a name="defining-the-wide-view"></a><span data-ttu-id="b5415-110">ワイドビューの定義</span><span class="sxs-lookup"><span data-stu-id="b5415-110">Defining the Wide View</span></span>

<span data-ttu-id="b5415-111">次の XML[は、system.string オブジェクトの](/dotnet/api/System.Diagnostics.Process)ワイドビュースキーマを示しています。</span><span class="sxs-lookup"><span data-stu-id="b5415-111">The following XML shows the wide view schema for the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

<span data-ttu-id="b5415-112">ワイドビューを定義するには、次の XML 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5415-112">The following XML elements are used to define a wide view:</span></span>

- <span data-ttu-id="b5415-113">[ビュー](./view-element-format.md)要素は、ワイドビューの親要素です。</span><span class="sxs-lookup"><span data-stu-id="b5415-113">The [View](./view-element-format.md) element is the parent element of the wide view.</span></span> <span data-ttu-id="b5415-114">(これは、テーブル、リスト、およびカスタムコントロールビューの親要素と同じです)。</span><span class="sxs-lookup"><span data-stu-id="b5415-114">(This is the same parent element for the table, list, and custom control views.)</span></span>

- <span data-ttu-id="b5415-115">[Name](./name-element-for-view-format.md)要素は、ビューの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-115">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="b5415-116">この要素は、すべてのビューに必要です。</span><span class="sxs-lookup"><span data-stu-id="b5415-116">This element is required for all views.</span></span>

- <span data-ttu-id="b5415-117">[Viewselectedby](./viewselectedby-element-format.md)要素は、ビューを使用するオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="b5415-117">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="b5415-118">この要素は必須です。</span><span class="sxs-lookup"><span data-stu-id="b5415-118">This element is required.</span></span>

- <span data-ttu-id="b5415-119">[GroupBy](./groupby-element-for-view-format.md)要素は、オブジェクトの新しいグループが表示されるタイミングを定義します。</span><span class="sxs-lookup"><span data-stu-id="b5415-119">The [GroupBy](./groupby-element-for-view-format.md) element defines when a new group of objects is displayed.</span></span> <span data-ttu-id="b5415-120">特定のプロパティまたはスクリプトの値が変更されるたびに、新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="b5415-120">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="b5415-121">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b5415-121">This element is optional.</span></span>

- <span data-ttu-id="b5415-122">[Controls](./controls-element-for-view-format.md)要素は、ワイドビューによって定義されるカスタムコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="b5415-122">The [Controls](./controls-element-for-view-format.md) elements defines the custom controls that are defined by the wide view.</span></span> <span data-ttu-id="b5415-123">コントロールを使用すると、データの表示方法をさらに指定することができます。</span><span class="sxs-lookup"><span data-stu-id="b5415-123">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="b5415-124">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b5415-124">This element is optional.</span></span> <span data-ttu-id="b5415-125">ビューでは、独自のカスタムコントロールを定義することも、書式設定ファイルの任意のビューで使用できるコモンコントロールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b5415-125">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="b5415-126">カスタムコントロールの詳細については、「[カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5415-126">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="b5415-127">[WideControl](./widecontrol-element-format.md)要素とその子要素は、ビューに表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="b5415-127">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span> <span data-ttu-id="b5415-128">前の例では、ビューは[Processname](/dotnet/api/System.Diagnostics.Process.ProcessName)プロパティを表示するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="b5415-128">In the preceding example, the view is designed to display the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span>

<span data-ttu-id="b5415-129">単純なワイドビューを定義する完全な書式設定ファイルの例については、「 [Wide ビュー (基本)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5415-129">For an example of a complete formatting file that defines a simple wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="providing-definitions-for-your-wide-view"></a><span data-ttu-id="b5415-130">ワイドビューの定義を提供する</span><span class="sxs-lookup"><span data-stu-id="b5415-130">Providing Definitions for Your Wide View</span></span>

<span data-ttu-id="b5415-131">ワイドビューでは、 [WideControl](./widecontrol-element-format.md)要素の子要素を使用して1つ以上の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b5415-131">Wide views can provide one or more definitions by using the child elements of the [WideControl](./widecontrol-element-format.md) element.</span></span> <span data-ttu-id="b5415-132">通常、ビューの定義は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="b5415-132">Typically, a view will have only one definition.</span></span> <span data-ttu-id="b5415-133">次の例では、ビューは[Processname](/dotnet/api/System.Diagnostics.Process.ProcessName)プロパティの値を表示する1つの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="b5415-133">In the following example, the view provides a single definition that displays the value of the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span> <span data-ttu-id="b5415-134">ワイドビューでは、プロパティの値やスクリプトの値を表示できます (例には示されていません)。</span><span class="sxs-lookup"><span data-stu-id="b5415-134">A wide view can display the value of a property or the value of a script (not shown in the example).</span></span>

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

<span data-ttu-id="b5415-135">次の XML 要素を使用して、ワイドビューの定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b5415-135">The following XML elements can be used to provide definitions for a wide view:</span></span>

- <span data-ttu-id="b5415-136">[WideControl](./widecontrol-element-format.md)要素とその子要素は、ビューに表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="b5415-136">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span>

- <span data-ttu-id="b5415-137">[AutoSize](./autosize-element-for-widecontrol-format.md)要素は、列のサイズと列の数をデータのサイズに基づいて調整するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-137">The [AutoSize](./autosize-element-for-widecontrol-format.md) element specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span> <span data-ttu-id="b5415-138">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b5415-138">This element is optional.</span></span>

- <span data-ttu-id="b5415-139">[Columnnumber](./columnnumber-element-for-widecontrol-format.md)要素は、ワイドビューに表示される列の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-139">The [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element specifies the number of columns displayed in the wide view.</span></span> <span data-ttu-id="b5415-140">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b5415-140">This element is optional.</span></span>

- <span data-ttu-id="b5415-141">[WideEntries](./wideentries-element-for-widecontrol-format.md)要素は、ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="b5415-141">The [WideEntries](./wideentries-element-for-widecontrol-format.md) element provides the definitions of the view.</span></span> <span data-ttu-id="b5415-142">ほとんどの場合、ビューには定義が1つだけ含まれます。</span><span class="sxs-lookup"><span data-stu-id="b5415-142">In most cases, a view will have only one definition.</span></span> <span data-ttu-id="b5415-143">この要素は必須です。</span><span class="sxs-lookup"><span data-stu-id="b5415-143">This element is required.</span></span>

- <span data-ttu-id="b5415-144">[WideEntry](./wideentry-element-for-widecontrol-format.md)要素は、ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="b5415-144">The [WideEntry](./wideentry-element-for-widecontrol-format.md) element provides a definition of the view.</span></span> <span data-ttu-id="b5415-145">少なくとも1つの[WideEntry](./wideentry-element-for-widecontrol-format.md)が必要です。ただし、追加できる要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="b5415-145">At least one [WideEntry](./wideentry-element-for-widecontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="b5415-146">ほとんどの場合、ビューには定義が1つだけ含まれます。</span><span class="sxs-lookup"><span data-stu-id="b5415-146">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="b5415-147">[Entryselectedby](./entryselectedby-element-for-wideentry-format.md)要素は、特定の定義によって表示されるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-147">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="b5415-148">この要素は省略可能であり、異なるオブジェクトを表示する複数の[WideEntry](./wideentry-element-for-widecontrol-format.md)要素を定義する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="b5415-148">This element is optional and is needed only when you define multiple [WideEntry](./wideentry-element-for-widecontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="b5415-149">[WideItem](./wideitem-element-for-widecontrol-format.md)要素は、ビューによって表示されるデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-149">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span> <span data-ttu-id="b5415-150">他の種類のビューとは異なり、ワイドコントロールで表示できる項目は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="b5415-150">In contrast to other types of views, a wide control can display only one item.</span></span>

- <span data-ttu-id="b5415-151">[PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md)要素は、ビューによって表示される値を持つプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-151">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="b5415-152">プロパティまたはスクリプトのどちらかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b5415-152">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="b5415-153">[ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md)要素は、ビューによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-153">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="b5415-154">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b5415-154">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="b5415-155">[FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md)要素は、データの表示に使用されるパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-155">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a pattern that is used to display the data.</span></span> <span data-ttu-id="b5415-156">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b5415-156">This element is optional.</span></span>

<span data-ttu-id="b5415-157">ワイドビュー定義を定義する完全な書式設定ファイルの例については、「 [Wide ビュー (基本)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5415-157">For an example of a complete formatting file that defines a wide view definition, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="defining-the-objects-that-use-the-wide-view"></a><span data-ttu-id="b5415-158">ワイドビューを使用するオブジェクトの定義</span><span class="sxs-lookup"><span data-stu-id="b5415-158">Defining the Objects That Use the Wide View</span></span>

<span data-ttu-id="b5415-159">ワイドビューを使用する .NET オブジェクトを定義するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="b5415-159">There are two ways to define which .NET objects use the wide view.</span></span> <span data-ttu-id="b5415-160">[Viewselectedby](./viewselectedby-element-format.md)要素を使用すると、ビューのすべての定義で表示できるオブジェクトを定義できます。また、 [entryselectedby](./entryselectedby-element-for-wideentry-format.md)要素を使用して、ビューの特定の定義によって表示されるオブジェクトを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="b5415-160">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="b5415-161">ほとんどの場合、ビューには定義が1つしかないため、オブジェクトは通常、 [Viewselectedby](./viewselectedby-element-format.md)要素によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="b5415-161">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="b5415-162">次の例は、 [Viewselectedby](./viewselectedby-element-format.md)および[TypeName](./typename-element-for-viewselectedby-format.md)要素を使用して、ワイドビューによって表示されるオブジェクトを定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b5415-162">The following example shows how to define the objects that are displayed by the wide view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="b5415-163">指定できる[TypeName](./typename-element-for-viewselectedby-format.md)要素の数に制限はありません。これらの要素の順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="b5415-163">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="b5415-164">次の XML 要素を使用して、ワイドビューで使用されるオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b5415-164">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="b5415-165">[Viewselectedby](./viewselectedby-element-format.md)要素は、ワイドビューによって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="b5415-165">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="b5415-166">[TypeName](./typename-element-for-viewselectedby-format.md)要素は、ビューによって表示される .net を指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-166">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the view.</span></span> <span data-ttu-id="b5415-167">完全修飾 .NET 型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="b5415-167">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="b5415-168">ビューには少なくとも1つの種類または選択セットを指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="b5415-168">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="b5415-169">完全な書式設定ファイルの例については、「[ワイドビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5415-169">For an example of a complete formatting file, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

<span data-ttu-id="b5415-170">次の例では、 [Viewselectedby](./viewselectedby-element-format.md)要素と[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5415-170">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="b5415-171">複数のビューを使用して表示される関連オブジェクトのセットを持つ選択セットを使用します。たとえば、同じオブジェクトに対してワイドビューやテーブルビューを定義する場合などです。</span><span class="sxs-lookup"><span data-stu-id="b5415-171">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a wide view and a table view for the same objects.</span></span> <span data-ttu-id="b5415-172">選択セットを作成する方法の詳細については、「[選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5415-172">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="b5415-173">次の XML 要素を使用して、ワイドビューで使用されるオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b5415-173">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="b5415-174">[Viewselectedby](./viewselectedby-element-format.md)要素は、ワイドビューによって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="b5415-174">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="b5415-175">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素は、ビューで表示できるオブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-175">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="b5415-176">ビューには少なくとも1つの選択セットまたは型を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="b5415-176">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="b5415-177">次の例では、 [Entryselectedby](./entryselectedby-element-for-wideentry-format.md)要素を使用して、ワイドビューの特定の定義によって表示されるオブジェクトを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b5415-177">The following example shows how to define the objects displayed by a specific definition of the wide view using the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element.</span></span> <span data-ttu-id="b5415-178">この要素を使用して、オブジェクトの .NET 型名、選択したオブジェクトのセット、または定義を使用するタイミングを指定する選択条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b5415-178">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="b5415-179">選択条件を作成する方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5415-179">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</WideEntry>
```

<span data-ttu-id="b5415-180">次の XML 要素を使用して、ワイドビューの特定の定義で使用されるオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b5415-180">The following XML elements can be used to specify the objects that are used by a specific definition of the wide view:</span></span>

- <span data-ttu-id="b5415-181">[Entryselectedby](./entryselectedby-element-for-wideentry-format.md)要素は、定義によって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="b5415-181">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="b5415-182">[TypeName](./typename-element-for-viewselectedby-format.md)要素は、定義によって表示される .net を指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-182">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the definition.</span></span> <span data-ttu-id="b5415-183">この要素を使用する場合は、完全修飾 .NET 型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="b5415-183">When using this element the fully qualified .NET type name is required.</span></span> <span data-ttu-id="b5415-184">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="b5415-184">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="b5415-185">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素 (表示されません) は、この定義で表示できるオブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-185">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="b5415-186">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="b5415-186">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="b5415-187">[Selectioncondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)要素 (表示されません) は、この定義を使用するために存在する必要がある条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-187">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="b5415-188">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="b5415-188">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="b5415-189">選択条件の定義の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5415-189">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="displaying-groups-of-objects-in-a-wide-view"></a><span data-ttu-id="b5415-190">ワイドビューでのオブジェクトのグループの表示</span><span class="sxs-lookup"><span data-stu-id="b5415-190">Displaying Groups of objects in a Wide View</span></span>

<span data-ttu-id="b5415-191">ワイドビューで表示されるオブジェクトは、グループに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="b5415-191">You can separate the objects that are displayed by the wide view into groups.</span></span> <span data-ttu-id="b5415-192">これは、グループを定義することではなく、特定のプロパティまたはスクリプトの値が変更されるたびに、Windows PowerShell によって新しいグループが開始されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b5415-192">This does not mean that you define a group, only that Windows PowerShell starts a new group whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="b5415-193">次の例では、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType)プロパティの値が変更されるたびに、新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="b5415-193">In the following example, a new group is started whenever the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="b5415-194">グループがいつ開始されるかを定義するには、次の XML 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5415-194">The following XML elements are used to define when a group is started:</span></span>

- <span data-ttu-id="b5415-195">[GroupBy](./groupby-element-for-view-format.md)要素は、新しいグループを開始するプロパティまたはスクリプトを定義し、グループの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="b5415-195">The [GroupBy](./groupby-element-for-view-format.md) element defines the property or script that starts the new group and defines how the group is displayed.</span></span>

- <span data-ttu-id="b5415-196">[PropertyName](./propertyname-element-for-groupby-format.md)要素は、値が変更されるたびに新しいグループを開始するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-196">The [PropertyName](./propertyname-element-for-groupby-format.md) element specifies the property that starts a new group whenever its value changes.</span></span> <span data-ttu-id="b5415-197">グループを開始するには、プロパティまたはスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b5415-197">You must specify a property or script to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="b5415-198">[ScriptBlock](./scriptblock-element-for-groupby-format.md)要素は、値が変更されるたびに新しいグループを開始するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-198">The [ScriptBlock](./scriptblock-element-for-groupby-format.md) element specifies the script that starts a new group whenever its value changes.</span></span> <span data-ttu-id="b5415-199">グループを開始するには、スクリプトまたはプロパティを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b5415-199">You must specify a script or property to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="b5415-200">[Label](./label-element-for-groupby-format.md)要素は、各グループの先頭に表示されるラベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="b5415-200">The [Label](./label-element-for-groupby-format.md) element defines a label that is displayed at the beginning of each group.</span></span> <span data-ttu-id="b5415-201">Windows PowerShell は、この要素で指定されたテキストに加えて、新しいグループをトリガーした値を表示し、ラベルの前後に空白行を追加します。</span><span class="sxs-lookup"><span data-stu-id="b5415-201">In addition to the text specified by this element, Windows PowerShell displays the value that triggered the new group and adds a blank line before and after the label.</span></span> <span data-ttu-id="b5415-202">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b5415-202">This element is optional.</span></span>

- <span data-ttu-id="b5415-203">[CustomControl](./customcontrol-element-for-groupby-format.md)要素は、データの表示に使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="b5415-203">The [CustomControl](./customcontrol-element-for-groupby-format.md) element defines a control that is used to display the data.</span></span> <span data-ttu-id="b5415-204">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b5415-204">This element is optional.</span></span>

- <span data-ttu-id="b5415-205">[CustomControlName](./customcontrolname-element-for-groupby-format.md)要素は、データの表示に使用されるコモンコントロールまたはビューコントロールを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-205">The [CustomControlName](./customcontrolname-element-for-groupby-format.md) element specifies a common or view control that is used to display the data.</span></span> <span data-ttu-id="b5415-206">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b5415-206">This element is optional.</span></span>

<span data-ttu-id="b5415-207">グループを定義する完全な書式設定ファイルの例については、「 [Wide ビュー (GroupBy)](./wide-view-groupby.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5415-207">For an example of a complete formatting file that defines groups, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="b5415-208">書式指定文字列の使用</span><span class="sxs-lookup"><span data-stu-id="b5415-208">Using Format Strings</span></span>

<span data-ttu-id="b5415-209">書式設定文字列をワイドビューに追加して、データの表示方法をさらに詳細に定義できます。</span><span class="sxs-lookup"><span data-stu-id="b5415-209">Formatting strings can be added to a wide view to further define how the data is displayed.</span></span> <span data-ttu-id="b5415-210">次の例は、`StartTime` プロパティの値の書式設定文字列を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b5415-210">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

<span data-ttu-id="b5415-211">次の XML 要素を使用して、書式パターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b5415-211">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="b5415-212">[WideItem](./wideitem-element-for-widecontrol-format.md)要素は、ビューによって表示されるデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-212">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="b5415-213">[PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md)要素は、ビューによって表示される値を持つプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-213">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="b5415-214">プロパティまたはスクリプトのどちらかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b5415-214">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="b5415-215">[FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md)要素は、プロパティまたはスクリプトの値をビューに表示する方法を定義する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-215">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed in the view</span></span>

- <span data-ttu-id="b5415-216">[ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md)要素 (表示されません) は、ビューによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-216">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="b5415-217">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b5415-217">You must specify either a script or a property, but you cannot specify both.</span></span>

<span data-ttu-id="b5415-218">次の例では、スクリプトの値の書式を設定するために、`ToString` メソッドが呼び出されています。</span><span class="sxs-lookup"><span data-stu-id="b5415-218">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="b5415-219">スクリプトは、オブジェクトの任意のメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="b5415-219">Scripts can call any method of an object.</span></span> <span data-ttu-id="b5415-220">したがって、オブジェクトに、書式設定パラメーターを持つメソッド (`ToString`など) がある場合、スクリプトはそのメソッドを呼び出してスクリプトの出力値を書式設定できます。</span><span class="sxs-lookup"><span data-stu-id="b5415-220">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<WideItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</WideItem>
```

<span data-ttu-id="b5415-221">次の XML 要素を使用して、`ToString` メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="b5415-221">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="b5415-222">[WideItem](./wideitem-element-for-widecontrol-format.md)要素は、ビューによって表示されるデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-222">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="b5415-223">[ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md)要素 (表示されません) は、ビューによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5415-223">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="b5415-224">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b5415-224">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5415-225">参照</span><span class="sxs-lookup"><span data-stu-id="b5415-225">See Also</span></span>

[<span data-ttu-id="b5415-226">ワイドビュー (基本)</span><span class="sxs-lookup"><span data-stu-id="b5415-226">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="b5415-227">Wide ビュー (GroupBy)</span><span class="sxs-lookup"><span data-stu-id="b5415-227">Wide View (GroupBy)</span></span>](./wide-view-groupby.md)

[<span data-ttu-id="b5415-228">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="b5415-228">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
