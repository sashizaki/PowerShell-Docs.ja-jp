---
title: Wide ビュー (GroupBy) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39388197-4ff9-4889-aa32-526011afa1f6
caps.latest.revision: 6
ms.openlocfilehash: e95ec550a7815a76a8bd7f9526dfa405a9644360
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367951"
---
# <a name="wide-view-groupby"></a><span data-ttu-id="60ce1-102">ワイド ビュー (グループ別)</span><span class="sxs-lookup"><span data-stu-id="60ce1-102">Wide View (GroupBy)</span></span>

<span data-ttu-id="60ce1-103">この例では、Servicecontroller のグループを表示するワイドビューを実装する方法を示します。 [Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) `Get-Service` コマンドレットによって返される Fullname オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="60ce1-103">This example shows how to implement a wide view that displays groups of [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="60ce1-104">ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60ce1-104">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="60ce1-105">この書式設定ファイルを読み込むには</span><span class="sxs-lookup"><span data-stu-id="60ce1-105">To load this formatting file</span></span>

1. <span data-ttu-id="60ce1-106">このトピックの「例」のセクションにある XML をテキストファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="60ce1-106">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="60ce1-107">テキストファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="60ce1-107">Save the text file.</span></span> <span data-ttu-id="60ce1-108">フォーマットファイルとして識別するには、ファイルに `format.ps1xml` 拡張子を追加してください。</span><span class="sxs-lookup"><span data-stu-id="60ce1-108">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="60ce1-109">Windows PowerShell を開き、次のコマンドを実行して、書式設定ファイルを現在のセッションに読み込みます。 `Update-formatdata -prependpath PathToFormattingFile`。</span><span class="sxs-lookup"><span data-stu-id="60ce1-109">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="60ce1-110">この書式設定ファイルは、Windows PowerShell の書式設定ファイルによって既に定義されているオブジェクトの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="60ce1-110">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting files.</span></span> <span data-ttu-id="60ce1-111">コマンドレットの実行時には `prependPath` パラメーターを使用する必要があり、このフォーマットファイルをモジュールとして読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="60ce1-111">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="60ce1-112">サンプル</span><span class="sxs-lookup"><span data-stu-id="60ce1-112">Demonstrates</span></span>

<span data-ttu-id="60ce1-113">この書式設定ファイルは、次の XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="60ce1-113">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="60ce1-114">ビューの[Name](./name-element-for-view-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="60ce1-114">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="60ce1-115">ビューによって表示されるオブジェクトを定義する[Viewselectedby](./viewselectedby-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="60ce1-115">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="60ce1-116">新しいグループが表示されるタイミングを定義する[GroupBy](./groupby-element-for-view-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="60ce1-116">The [GroupBy](./groupby-element-for-view-format.md) element that defines when a new group is displayed.</span></span>

- <span data-ttu-id="60ce1-117">ビューによって表示されるプロパティを定義する[WideItem](./wideitem-element-for-widecontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="60ce1-117">The [WideItem](./wideitem-element-for-widecontrol-format.md) element that defines what property is displayed by the view.</span></span>

## <a name="example"></a><span data-ttu-id="60ce1-118">例</span><span class="sxs-lookup"><span data-stu-id="60ce1-118">Example</span></span>

<span data-ttu-id="60ce1-119">次の XML は、オブジェクトのグループを表示するワイドビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="60ce1-119">The following XML defines a wide view that displays groups of objects.</span></span> <span data-ttu-id="60ce1-120">新しい各グループは、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType)プロパティの値が変更されると開始されます。</span><span class="sxs-lookup"><span data-stu-id="60ce1-120">Each new group is started when the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>

<Configuration>
  <ViewDefinitions>
    <View>
      <Name>ServiceWideView</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <Label>Service Type</Label>
        <PropertyName>ServiceType</PropertyName>
      </GroupBy>
      <WideControl>
        <WideEntries>
          <WideEntry>
            <WideItem>
              <PropertyName>ServiceName</PropertyName>
            </WideItem>
          </WideEntry>
        </WideEntries>
      </WideControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

<span data-ttu-id="60ce1-121">次の例は、Windows PowerShell で Servicecontroller を表示する方法を示しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトこのフォーマットファイルが読み込まれた後。</span><span class="sxs-lookup"><span data-stu-id="60ce1-121">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
   Service Type: Win32OwnProcess

Fax                             FCSAM

   Service Type: Win32ShareProcess

fdPHost                         FDResPub
FontCache

   Service Type: Win32OwnProcess

FontCache3.0.0.0                FSysAgent
FwcAgent
```

## <a name="see-also"></a><span data-ttu-id="60ce1-122">参照</span><span class="sxs-lookup"><span data-stu-id="60ce1-122">See Also</span></span>

[<span data-ttu-id="60ce1-123">フォーマットファイルの例</span><span class="sxs-lookup"><span data-stu-id="60ce1-123">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="60ce1-124">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="60ce1-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
