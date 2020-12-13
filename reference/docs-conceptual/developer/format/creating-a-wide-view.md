---
ms.date: 09/13/2016
ms.topic: reference
title: ワイド ビューを作成する
description: ワイド ビューを作成する
ms.openlocfilehash: 4230ef91a3612e962b2773b12e8016df6f760eae
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655598"
---
# <a name="creating-a-wide-view"></a><span data-ttu-id="12160-103">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="12160-103">Creating a Wide View</span></span>

<span data-ttu-id="12160-104">ワイドビューでは、表示されているオブジェクトごとに1つの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="12160-104">A wide view displays a single value for each object that is displayed.</span></span> <span data-ttu-id="12160-105">表示される値には、.NET オブジェクトプロパティの値、またはスクリプトの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="12160-105">The displayed value can be the value of a .NET object property or the value of a script.</span></span> <span data-ttu-id="12160-106">既定では、このビューにはラベルまたはヘッダーがありません。</span><span class="sxs-lookup"><span data-stu-id="12160-106">By default, there is no label or header for this view.</span></span>

## <a name="a-wide-view-display"></a><span data-ttu-id="12160-107">ワイドビューの表示</span><span class="sxs-lookup"><span data-stu-id="12160-107">A Wide View Display</span></span>

<span data-ttu-id="12160-108">次の例は、Windows PowerShell の出力が[フォーマット全体](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide)のコマンドレットにパイプされるときに、 [Get process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットによって返さ[れる system.object オブジェクトを表示](/dotnet/api/System.Diagnostics.Process)する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="12160-108">The following example shows how Windows PowerShell displays the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object that is returned by the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet when its output is piped to the [Format-Wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide) cmdlet.</span></span> <span data-ttu-id="12160-109">(既定では、 [Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) コマンドレットはテーブルビューを返します)。この例では、2つの列を使用して、返された各オブジェクトのプロセスの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="12160-109">(By default, the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns a table view.) In this example, the two columns are used to display the name of the process for each returned object.</span></span> <span data-ttu-id="12160-110">オブジェクトのプロパティの名前は表示されず、プロパティの値のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="12160-110">The name of the object's property is not displayed, only the value of the property.</span></span>

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

## <a name="defining-the-wide-view"></a><span data-ttu-id="12160-111">ワイドビューの定義</span><span class="sxs-lookup"><span data-stu-id="12160-111">Defining the Wide View</span></span>

<span data-ttu-id="12160-112">次の XML [は、system.string オブジェクトの](/dotnet/api/System.Diagnostics.Process) ワイドビュースキーマを示しています。</span><span class="sxs-lookup"><span data-stu-id="12160-112">The following XML shows the wide view schema for the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

<span data-ttu-id="12160-113">ワイドビューを定義するには、次の XML 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="12160-113">The following XML elements are used to define a wide view:</span></span>

- <span data-ttu-id="12160-114">[ビュー](./view-element-format.md)要素は、ワイドビューの親要素です。</span><span class="sxs-lookup"><span data-stu-id="12160-114">The [View](./view-element-format.md) element is the parent element of the wide view.</span></span> <span data-ttu-id="12160-115">(これは、テーブル、リスト、およびカスタムコントロールビューの親要素と同じです)。</span><span class="sxs-lookup"><span data-stu-id="12160-115">(This is the same parent element for the table, list, and custom control views.)</span></span>

- <span data-ttu-id="12160-116">[Name](./name-element-for-view-format.md)要素は、ビューの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-116">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="12160-117">この要素は、すべてのビューに必要です。</span><span class="sxs-lookup"><span data-stu-id="12160-117">This element is required for all views.</span></span>

- <span data-ttu-id="12160-118">[Viewselectedby](./viewselectedby-element-format.md)要素は、ビューを使用するオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="12160-118">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="12160-119">この要素は必須です。</span><span class="sxs-lookup"><span data-stu-id="12160-119">This element is required.</span></span>

- <span data-ttu-id="12160-120">[GroupBy](./groupby-element-for-view-format.md)要素は、オブジェクトの新しいグループが表示されるタイミングを定義します。</span><span class="sxs-lookup"><span data-stu-id="12160-120">The [GroupBy](./groupby-element-for-view-format.md) element defines when a new group of objects is displayed.</span></span> <span data-ttu-id="12160-121">特定のプロパティまたはスクリプトの値が変更されるたびに、新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="12160-121">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="12160-122">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="12160-122">This element is optional.</span></span>

- <span data-ttu-id="12160-123">[Controls](./controls-element-for-view-format.md)要素は、ワイドビューによって定義されるカスタムコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="12160-123">The [Controls](./controls-element-for-view-format.md) elements defines the custom controls that are defined by the wide view.</span></span> <span data-ttu-id="12160-124">コントロールを使用すると、データの表示方法をさらに指定することができます。</span><span class="sxs-lookup"><span data-stu-id="12160-124">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="12160-125">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="12160-125">This element is optional.</span></span> <span data-ttu-id="12160-126">ビューでは、独自のカスタムコントロールを定義することも、書式設定ファイルの任意のビューで使用できるコモンコントロールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="12160-126">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="12160-127">カスタムコントロールの詳細については、「 [カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12160-127">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="12160-128">[WideControl](./widecontrol-element-format.md)要素とその子要素は、ビューに表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="12160-128">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span> <span data-ttu-id="12160-129">前の例では、ビューは [Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) プロパティを表示するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="12160-129">In the preceding example, the view is designed to display the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span>

<span data-ttu-id="12160-130">単純なワイドビューを定義する完全な書式設定ファイルの例については、「 [Wide ビュー (基本)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12160-130">For an example of a complete formatting file that defines a simple wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="providing-definitions-for-your-wide-view"></a><span data-ttu-id="12160-131">ワイドビューの定義を提供する</span><span class="sxs-lookup"><span data-stu-id="12160-131">Providing Definitions for Your Wide View</span></span>

<span data-ttu-id="12160-132">ワイドビューでは、 [WideControl](./widecontrol-element-format.md) 要素の子要素を使用して1つ以上の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="12160-132">Wide views can provide one or more definitions by using the child elements of the [WideControl](./widecontrol-element-format.md) element.</span></span> <span data-ttu-id="12160-133">通常、ビューの定義は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="12160-133">Typically, a view will have only one definition.</span></span> <span data-ttu-id="12160-134">次の例では、ビューは [Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) プロパティの値を表示する1つの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="12160-134">In the following example, the view provides a single definition that displays the value of the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span> <span data-ttu-id="12160-135">ワイドビューでは、プロパティの値やスクリプトの値を表示できます (例には示されていません)。</span><span class="sxs-lookup"><span data-stu-id="12160-135">A wide view can display the value of a property or the value of a script (not shown in the example).</span></span>

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

<span data-ttu-id="12160-136">次の XML 要素を使用して、ワイドビューの定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="12160-136">The following XML elements can be used to provide definitions for a wide view:</span></span>

- <span data-ttu-id="12160-137">[WideControl](./widecontrol-element-format.md)要素とその子要素は、ビューに表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="12160-137">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span>

- <span data-ttu-id="12160-138">[AutoSize](./autosize-element-for-widecontrol-format.md)要素は、列のサイズと列の数をデータのサイズに基づいて調整するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-138">The [AutoSize](./autosize-element-for-widecontrol-format.md) element specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span> <span data-ttu-id="12160-139">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="12160-139">This element is optional.</span></span>

- <span data-ttu-id="12160-140">[Columnnumber](./columnnumber-element-for-widecontrol-format.md)要素は、ワイドビューに表示される列の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-140">The [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element specifies the number of columns displayed in the wide view.</span></span> <span data-ttu-id="12160-141">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="12160-141">This element is optional.</span></span>

- <span data-ttu-id="12160-142">[WideEntries](./wideentries-element-for-widecontrol-format.md)要素は、ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="12160-142">The [WideEntries](./wideentries-element-for-widecontrol-format.md) element provides the definitions of the view.</span></span> <span data-ttu-id="12160-143">ほとんどの場合、ビューには定義が1つだけ含まれます。</span><span class="sxs-lookup"><span data-stu-id="12160-143">In most cases, a view will have only one definition.</span></span> <span data-ttu-id="12160-144">この要素は必須です。</span><span class="sxs-lookup"><span data-stu-id="12160-144">This element is required.</span></span>

- <span data-ttu-id="12160-145">[WideEntry](./wideentry-element-for-widecontrol-format.md)要素は、ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="12160-145">The [WideEntry](./wideentry-element-for-widecontrol-format.md) element provides a definition of the view.</span></span> <span data-ttu-id="12160-146">少なくとも1つの [WideEntry](./wideentry-element-for-widecontrol-format.md) が必要です。ただし、追加できる要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="12160-146">At least one [WideEntry](./wideentry-element-for-widecontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="12160-147">ほとんどの場合、ビューには定義が1つだけ含まれます。</span><span class="sxs-lookup"><span data-stu-id="12160-147">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="12160-148">[Entryselectedby](./entryselectedby-element-for-wideentry-format.md)要素は、特定の定義によって表示されるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-148">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="12160-149">この要素は省略可能であり、異なるオブジェクトを表示する複数の [WideEntry](./wideentry-element-for-widecontrol-format.md) 要素を定義する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="12160-149">This element is optional and is needed only when you define multiple [WideEntry](./wideentry-element-for-widecontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="12160-150">[WideItem](./wideitem-element-for-widecontrol-format.md)要素は、ビューによって表示されるデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-150">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span> <span data-ttu-id="12160-151">他の種類のビューとは異なり、ワイドコントロールで表示できる項目は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="12160-151">In contrast to other types of views, a wide control can display only one item.</span></span>

- <span data-ttu-id="12160-152">[PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md)要素は、ビューによって表示される値を持つプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-152">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="12160-153">プロパティまたはスクリプトのどちらかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="12160-153">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="12160-154">[ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md)要素は、ビューによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-154">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="12160-155">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="12160-155">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="12160-156">[FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md)要素は、データの表示に使用されるパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-156">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a pattern that is used to display the data.</span></span> <span data-ttu-id="12160-157">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="12160-157">This element is optional.</span></span>

<span data-ttu-id="12160-158">ワイドビュー定義を定義する完全な書式設定ファイルの例については、「 [Wide ビュー (基本)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12160-158">For an example of a complete formatting file that defines a wide view definition, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="defining-the-objects-that-use-the-wide-view"></a><span data-ttu-id="12160-159">ワイドビューを使用するオブジェクトの定義</span><span class="sxs-lookup"><span data-stu-id="12160-159">Defining the Objects That Use the Wide View</span></span>

<span data-ttu-id="12160-160">ワイドビューを使用する .NET オブジェクトを定義するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="12160-160">There are two ways to define which .NET objects use the wide view.</span></span> <span data-ttu-id="12160-161">[Viewselectedby](./viewselectedby-element-format.md)要素を使用すると、ビューのすべての定義で表示できるオブジェクトを定義できます。また、 [entryselectedby](./entryselectedby-element-for-wideentry-format.md)要素を使用して、ビューの特定の定義によって表示されるオブジェクトを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="12160-161">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="12160-162">ほとんどの場合、ビューには定義が1つしかないため、オブジェクトは通常、 [Viewselectedby](./viewselectedby-element-format.md) 要素によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="12160-162">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="12160-163">次の例は、 [Viewselectedby](./viewselectedby-element-format.md) および [TypeName](./typename-element-for-viewselectedby-format.md) 要素を使用して、ワイドビューによって表示されるオブジェクトを定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="12160-163">The following example shows how to define the objects that are displayed by the wide view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="12160-164">指定できる [TypeName](./typename-element-for-viewselectedby-format.md) 要素の数に制限はありません。これらの要素の順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="12160-164">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="12160-165">次の XML 要素を使用して、ワイドビューで使用されるオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="12160-165">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="12160-166">[Viewselectedby](./viewselectedby-element-format.md)要素は、ワイドビューによって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="12160-166">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="12160-167">[TypeName](./typename-element-for-viewselectedby-format.md)要素は、ビューによって表示される .net を指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-167">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the view.</span></span> <span data-ttu-id="12160-168">完全修飾 .NET 型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="12160-168">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="12160-169">ビューには少なくとも1つの種類または選択セットを指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="12160-169">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="12160-170">完全な書式設定ファイルの例については、「 [ワイドビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12160-170">For an example of a complete formatting file, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

<span data-ttu-id="12160-171">次の例では、 [Viewselectedby](./viewselectedby-element-format.md) 要素と [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="12160-171">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="12160-172">複数のビューを使用して表示される関連オブジェクトのセットを持つ選択セットを使用します。たとえば、同じオブジェクトに対してワイドビューやテーブルビューを定義する場合などです。</span><span class="sxs-lookup"><span data-stu-id="12160-172">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a wide view and a table view for the same objects.</span></span> <span data-ttu-id="12160-173">選択セットを作成する方法の詳細については、「 [選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12160-173">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="12160-174">次の XML 要素を使用して、ワイドビューで使用されるオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="12160-174">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="12160-175">[Viewselectedby](./viewselectedby-element-format.md)要素は、ワイドビューによって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="12160-175">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="12160-176">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素は、ビューで表示できるオブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-176">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="12160-177">ビューには少なくとも1つの選択セットまたは型を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="12160-177">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="12160-178">次の例では、 [Entryselectedby](./entryselectedby-element-for-wideentry-format.md) 要素を使用して、ワイドビューの特定の定義によって表示されるオブジェクトを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="12160-178">The following example shows how to define the objects displayed by a specific definition of the wide view using the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element.</span></span> <span data-ttu-id="12160-179">この要素を使用して、オブジェクトの .NET 型名、選択したオブジェクトのセット、または定義を使用するタイミングを指定する選択条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="12160-179">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="12160-180">選択条件を作成する方法の詳細については、「 [データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12160-180">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</WideEntry>
```

<span data-ttu-id="12160-181">次の XML 要素を使用して、ワイドビューの特定の定義で使用されるオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="12160-181">The following XML elements can be used to specify the objects that are used by a specific definition of the wide view:</span></span>

- <span data-ttu-id="12160-182">[Entryselectedby](./entryselectedby-element-for-wideentry-format.md)要素は、定義によって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="12160-182">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="12160-183">[TypeName](./typename-element-for-viewselectedby-format.md)要素は、定義によって表示される .net を指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-183">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the definition.</span></span> <span data-ttu-id="12160-184">この要素を使用する場合は、完全修飾 .NET 型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="12160-184">When using this element the fully qualified .NET type name is required.</span></span> <span data-ttu-id="12160-185">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="12160-185">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="12160-186">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素 (表示されません) は、この定義で表示できるオブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-186">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="12160-187">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="12160-187">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="12160-188">[Selectioncondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)要素 (表示されません) は、この定義を使用するために存在する必要がある条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-188">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="12160-189">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="12160-189">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="12160-190">選択条件の定義の詳細については、「 [データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12160-190">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="displaying-groups-of-objects-in-a-wide-view"></a><span data-ttu-id="12160-191">ワイドビューでのオブジェクトのグループの表示</span><span class="sxs-lookup"><span data-stu-id="12160-191">Displaying Groups of objects in a Wide View</span></span>

<span data-ttu-id="12160-192">ワイドビューで表示されるオブジェクトは、グループに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="12160-192">You can separate the objects that are displayed by the wide view into groups.</span></span> <span data-ttu-id="12160-193">これは、グループを定義することではなく、特定のプロパティまたはスクリプトの値が変更されるたびに、Windows PowerShell によって新しいグループが開始されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="12160-193">This does not mean that you define a group, only that Windows PowerShell starts a new group whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="12160-194">次の例では、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) プロパティの値が変更されるたびに、新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="12160-194">In the following example, a new group is started whenever the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="12160-195">グループがいつ開始されるかを定義するには、次の XML 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="12160-195">The following XML elements are used to define when a group is started:</span></span>

- <span data-ttu-id="12160-196">[GroupBy](./groupby-element-for-view-format.md)要素は、新しいグループを開始するプロパティまたはスクリプトを定義し、グループの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="12160-196">The [GroupBy](./groupby-element-for-view-format.md) element defines the property or script that starts the new group and defines how the group is displayed.</span></span>

- <span data-ttu-id="12160-197">[PropertyName](./propertyname-element-for-groupby-format.md)要素は、値が変更されるたびに新しいグループを開始するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-197">The [PropertyName](./propertyname-element-for-groupby-format.md) element specifies the property that starts a new group whenever its value changes.</span></span> <span data-ttu-id="12160-198">グループを開始するには、プロパティまたはスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="12160-198">You must specify a property or script to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="12160-199">[ScriptBlock](./scriptblock-element-for-groupby-format.md)要素は、値が変更されるたびに新しいグループを開始するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-199">The [ScriptBlock](./scriptblock-element-for-groupby-format.md) element specifies the script that starts a new group whenever its value changes.</span></span> <span data-ttu-id="12160-200">グループを開始するには、スクリプトまたはプロパティを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="12160-200">You must specify a script or property to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="12160-201">[Label](./label-element-for-groupby-format.md)要素は、各グループの先頭に表示されるラベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="12160-201">The [Label](./label-element-for-groupby-format.md) element defines a label that is displayed at the beginning of each group.</span></span> <span data-ttu-id="12160-202">Windows PowerShell は、この要素で指定されたテキストに加えて、新しいグループをトリガーした値を表示し、ラベルの前後に空白行を追加します。</span><span class="sxs-lookup"><span data-stu-id="12160-202">In addition to the text specified by this element, Windows PowerShell displays the value that triggered the new group and adds a blank line before and after the label.</span></span> <span data-ttu-id="12160-203">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="12160-203">This element is optional.</span></span>

- <span data-ttu-id="12160-204">[CustomControl](./customcontrol-element-for-groupby-format.md)要素は、データの表示に使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="12160-204">The [CustomControl](./customcontrol-element-for-groupby-format.md) element defines a control that is used to display the data.</span></span> <span data-ttu-id="12160-205">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="12160-205">This element is optional.</span></span>

- <span data-ttu-id="12160-206">[CustomControlName](./customcontrolname-element-for-groupby-format.md)要素は、データの表示に使用されるコモンコントロールまたはビューコントロールを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-206">The [CustomControlName](./customcontrolname-element-for-groupby-format.md) element specifies a common or view control that is used to display the data.</span></span> <span data-ttu-id="12160-207">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="12160-207">This element is optional.</span></span>

<span data-ttu-id="12160-208">グループを定義する完全な書式設定ファイルの例については、「 [Wide ビュー (GroupBy)](./wide-view-groupby.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12160-208">For an example of a complete formatting file that defines groups, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="12160-209">書式指定文字列の使用</span><span class="sxs-lookup"><span data-stu-id="12160-209">Using Format Strings</span></span>

<span data-ttu-id="12160-210">書式設定文字列をワイドビューに追加して、データの表示方法をさらに詳細に定義できます。</span><span class="sxs-lookup"><span data-stu-id="12160-210">Formatting strings can be added to a wide view to further define how the data is displayed.</span></span> <span data-ttu-id="12160-211">次の例は、プロパティの値の書式設定文字列を定義する方法を示して `StartTime` います。</span><span class="sxs-lookup"><span data-stu-id="12160-211">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

<span data-ttu-id="12160-212">次の XML 要素を使用して、書式パターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="12160-212">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="12160-213">[WideItem](./wideitem-element-for-widecontrol-format.md)要素は、ビューによって表示されるデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-213">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="12160-214">[PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md)要素は、ビューによって表示される値を持つプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-214">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="12160-215">プロパティまたはスクリプトのどちらかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="12160-215">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="12160-216">[FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md)要素は、プロパティまたはスクリプトの値をビューに表示する方法を定義する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-216">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed in the view</span></span>

- <span data-ttu-id="12160-217">[ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md)要素 (表示されません) は、ビューによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-217">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="12160-218">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="12160-218">You must specify either a script or a property, but you cannot specify both.</span></span>

<span data-ttu-id="12160-219">次の例では、 `ToString` スクリプトの値の書式を設定するためにメソッドが呼び出されています。</span><span class="sxs-lookup"><span data-stu-id="12160-219">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="12160-220">スクリプトは、オブジェクトの任意のメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="12160-220">Scripts can call any method of an object.</span></span> <span data-ttu-id="12160-221">したがって、オブジェクトに、書式設定パラメーターを持つなどのメソッドがある場合、 `ToString` スクリプトはそのメソッドを呼び出してスクリプトの出力値を書式設定できます。</span><span class="sxs-lookup"><span data-stu-id="12160-221">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<WideItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</WideItem>
```

<span data-ttu-id="12160-222">次の XML 要素を使用して、メソッドを呼び出すことができ `ToString` ます。</span><span class="sxs-lookup"><span data-stu-id="12160-222">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="12160-223">[WideItem](./wideitem-element-for-widecontrol-format.md)要素は、ビューによって表示されるデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-223">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="12160-224">[ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md)要素 (表示されません) は、ビューによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="12160-224">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="12160-225">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="12160-225">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="12160-226">参照</span><span class="sxs-lookup"><span data-stu-id="12160-226">See Also</span></span>

[<span data-ttu-id="12160-227">ワイド ビュー (基本)</span><span class="sxs-lookup"><span data-stu-id="12160-227">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="12160-228">ワイド ビュー (グループ別)</span><span class="sxs-lookup"><span data-stu-id="12160-228">Wide View (GroupBy)</span></span>](./wide-view-groupby.md)

[<span data-ttu-id="12160-229">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="12160-229">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
