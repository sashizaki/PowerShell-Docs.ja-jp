---
title: 表示幅が広い (GroupBy) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39388197-4ff9-4889-aa32-526011afa1f6
caps.latest.revision: 6
ms.openlocfilehash: e95ec550a7815a76a8bd7f9526dfa405a9644360
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083656"
---
# <a name="wide-view-groupby"></a><span data-ttu-id="3a676-102">ワイド ビュー (グループ別)</span><span class="sxs-lookup"><span data-stu-id="3a676-102">Wide View (GroupBy)</span></span>

<span data-ttu-id="3a676-103">この例のグループを表示するワイド ビューを実装する方法を示しています。 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)によって返されるオブジェクト、`Get-Service`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="3a676-103">This example shows how to implement a wide view that displays groups of [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="3a676-104">ワイド ビューのコンポーネントに関する詳細については、次を参照してください。[ワイド ビューを作成する](./creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="3a676-104">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="3a676-105">この書式設定ファイルを読み込む</span><span class="sxs-lookup"><span data-stu-id="3a676-105">To load this formatting file</span></span>

1. <span data-ttu-id="3a676-106">このトピックの例のセクションからテキスト ファイルに XML をコピーします。</span><span class="sxs-lookup"><span data-stu-id="3a676-106">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="3a676-107">テキスト ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="3a676-107">Save the text file.</span></span> <span data-ttu-id="3a676-108">追加してください、`format.ps1xml`書式設定ファイルとして識別するファイルへの拡張機能。</span><span class="sxs-lookup"><span data-stu-id="3a676-108">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="3a676-109">Windows PowerShell を開き、現在のセッションに書式設定ファイルを読み込むには、次のコマンドを実行します。`Update-formatdata -prependpath PathToFormattingFile`します。</span><span class="sxs-lookup"><span data-stu-id="3a676-109">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="3a676-110">この書式設定ファイルは、Windows PowerShell の書式設定ファイルで既に定義されているオブジェクトの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="3a676-110">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting files.</span></span> <span data-ttu-id="3a676-111">使用する必要があります、`prependPath`をモジュールとしてファイルのパラメーター、コマンドレットを実行すると、この書式設定を読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="3a676-111">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="3a676-112">使用例</span><span class="sxs-lookup"><span data-stu-id="3a676-112">Demonstrates</span></span>

<span data-ttu-id="3a676-113">この書式設定ファイルには、次の XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="3a676-113">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="3a676-114">[名前](./name-element-for-view-format.md)ビューの要素。</span><span class="sxs-lookup"><span data-stu-id="3a676-114">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="3a676-115">[ViewSelectedBy](./viewselectedby-element-format.md)どのようなオブジェクトはビューで表示を定義する要素。</span><span class="sxs-lookup"><span data-stu-id="3a676-115">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="3a676-116">[GroupBy](./groupby-element-for-view-format.md)新しいグループが表示される場合を定義する要素。</span><span class="sxs-lookup"><span data-stu-id="3a676-116">The [GroupBy](./groupby-element-for-view-format.md) element that defines when a new group is displayed.</span></span>

- <span data-ttu-id="3a676-117">[WideItem](./wideitem-element-for-widecontrol-format.md)どのようなプロパティを表示するビューを定義する要素。</span><span class="sxs-lookup"><span data-stu-id="3a676-117">The [WideItem](./wideitem-element-for-widecontrol-format.md) element that defines what property is displayed by the view.</span></span>

## <a name="example"></a><span data-ttu-id="3a676-118">例</span><span class="sxs-lookup"><span data-stu-id="3a676-118">Example</span></span>

<span data-ttu-id="3a676-119">次の XML では、オブジェクトのグループを表示するワイド ビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="3a676-119">The following XML defines a wide view that displays groups of objects.</span></span> <span data-ttu-id="3a676-120">新しいグループのそれぞれの開始時の値、 [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType)プロパティの変更。</span><span class="sxs-lookup"><span data-stu-id="3a676-120">Each new group is started when the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

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

<span data-ttu-id="3a676-121">次の例は、Windows PowerShell を表示する方法を示しています、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)このフォーマット ファイルが読み込まれた後のオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="3a676-121">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="3a676-122">参照</span><span class="sxs-lookup"><span data-stu-id="3a676-122">See Also</span></span>

[<span data-ttu-id="3a676-123">書式設定ファイルの例</span><span class="sxs-lookup"><span data-stu-id="3a676-123">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="3a676-124">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="3a676-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
