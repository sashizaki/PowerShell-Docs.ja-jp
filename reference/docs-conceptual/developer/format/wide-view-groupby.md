---
ms.date: 09/13/2016
ms.topic: reference
title: ワイド ビュー (グループ別)
description: ワイド ビュー (グループ別)
ms.openlocfilehash: 807bea2a5d44c38e2c9977f792bea2fb9bca0fc3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667676"
---
# <a name="wide-view-groupby"></a><span data-ttu-id="71570-103">ワイド ビュー (グループ別)</span><span class="sxs-lookup"><span data-stu-id="71570-103">Wide View (GroupBy)</span></span>

<span data-ttu-id="71570-104">この例では、Servicecontroller のグループを表示するワイドビューを実装する方法を示します。 [Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) コマンドレットによって返される Fullname オブジェクト `Get-Service` 。</span><span class="sxs-lookup"><span data-stu-id="71570-104">This example shows how to implement a wide view that displays groups of [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="71570-105">ワイドビューのコンポーネントの詳細については、「 [ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71570-105">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="71570-106">この書式設定ファイルを読み込むには</span><span class="sxs-lookup"><span data-stu-id="71570-106">To load this formatting file</span></span>

1. <span data-ttu-id="71570-107">このトピックの「例」のセクションにある XML をテキストファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="71570-107">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="71570-108">テキスト ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="71570-108">Save the text file.</span></span> <span data-ttu-id="71570-109">ファイルに拡張子を追加して、 `format.ps1xml` 書式設定ファイルとして識別するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="71570-109">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="71570-110">Windows PowerShell を開き、次のコマンドを実行して、書式設定ファイルを現在のセッションに読み込み `Update-formatdata -prependpath PathToFormattingFile` ます。</span><span class="sxs-lookup"><span data-stu-id="71570-110">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="71570-111">この書式設定ファイルは、Windows PowerShell の書式設定ファイルによって既に定義されているオブジェクトの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="71570-111">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting files.</span></span> <span data-ttu-id="71570-112">`prependPath`コマンドレットを実行するときにパラメーターを使用する必要があります。このフォーマットファイルをモジュールとして読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="71570-112">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="71570-113">対象</span><span class="sxs-lookup"><span data-stu-id="71570-113">Demonstrates</span></span>

<span data-ttu-id="71570-114">この書式設定ファイルは、次の XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="71570-114">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="71570-115">ビューの [Name](./name-element-for-view-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="71570-115">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="71570-116">ビューによって表示されるオブジェクトを定義する [Viewselectedby](./viewselectedby-element-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="71570-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="71570-117">新しいグループが表示されるタイミングを定義する [GroupBy](./groupby-element-for-view-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="71570-117">The [GroupBy](./groupby-element-for-view-format.md) element that defines when a new group is displayed.</span></span>

- <span data-ttu-id="71570-118">ビューによって表示されるプロパティを定義する [WideItem](./wideitem-element-for-widecontrol-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="71570-118">The [WideItem](./wideitem-element-for-widecontrol-format.md) element that defines what property is displayed by the view.</span></span>

## <a name="example"></a><span data-ttu-id="71570-119">例</span><span class="sxs-lookup"><span data-stu-id="71570-119">Example</span></span>

<span data-ttu-id="71570-120">次の XML は、オブジェクトのグループを表示するワイドビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="71570-120">The following XML defines a wide view that displays groups of objects.</span></span> <span data-ttu-id="71570-121">新しい各グループは、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) プロパティの値が変更されると開始されます。</span><span class="sxs-lookup"><span data-stu-id="71570-121">Each new group is started when the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

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

<span data-ttu-id="71570-122">次の例は、Windows PowerShell で Servicecontroller を表示する方法を示しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) オブジェクトこのフォーマットファイルが読み込まれた後。</span><span class="sxs-lookup"><span data-stu-id="71570-122">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="71570-123">参照</span><span class="sxs-lookup"><span data-stu-id="71570-123">See Also</span></span>

[<span data-ttu-id="71570-124">書式設定ファイルの例</span><span class="sxs-lookup"><span data-stu-id="71570-124">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="71570-125">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="71570-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
