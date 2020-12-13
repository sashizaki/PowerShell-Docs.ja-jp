---
ms.date: 09/13/2016
ms.topic: reference
title: ワイド ビュー (基本)
description: ワイド ビュー (基本)
ms.openlocfilehash: bfc647da9b78fcd22aac83cf330e466b6759471c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667693"
---
# <a name="wide-view-basic"></a><span data-ttu-id="4cd2a-103">ワイド ビュー (基本)</span><span class="sxs-lookup"><span data-stu-id="4cd2a-103">Wide View (Basic)</span></span>

<span data-ttu-id="4cd2a-104">この例では、Servicecontroller を表示する基本的なワイドビューを実装する方法を示します。 [Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) コマンドレットによって返される Fullname オブジェクト `Get-Service` 。</span><span class="sxs-lookup"><span data-stu-id="4cd2a-104">This example shows how to implement a basic wide view that displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="4cd2a-105">ワイドビューのコンポーネントの詳細については、「 [ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cd2a-105">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="4cd2a-106">この書式設定ファイルを読み込むには</span><span class="sxs-lookup"><span data-stu-id="4cd2a-106">To load this formatting file</span></span>

1. <span data-ttu-id="4cd2a-107">このトピックの「例」のセクションにある XML をテキストファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="4cd2a-107">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="4cd2a-108">テキスト ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="4cd2a-108">Save the text file.</span></span> <span data-ttu-id="4cd2a-109">ファイルに拡張子を追加して、 `format.ps1xml` 書式設定ファイルとして識別するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="4cd2a-109">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="4cd2a-110">Windows PowerShell を開き、次のコマンドを実行して、書式設定ファイルを現在のセッションに読み込み `Update-formatdata -prependpath PathToFormattingFile` ます。</span><span class="sxs-lookup"><span data-stu-id="4cd2a-110">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="4cd2a-111">この書式設定ファイルは、Windows PowerShell の書式設定ファイルによって既に定義されているオブジェクトの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="4cd2a-111">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="4cd2a-112">`prependPath`コマンドレットを実行するときにパラメーターを使用する必要があります。このフォーマットファイルをモジュールとして読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="4cd2a-112">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="4cd2a-113">対象</span><span class="sxs-lookup"><span data-stu-id="4cd2a-113">Demonstrates</span></span>

<span data-ttu-id="4cd2a-114">この書式設定ファイルは、次の XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="4cd2a-114">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="4cd2a-115">ビューの [Name](./name-element-for-view-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="4cd2a-115">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="4cd2a-116">ビューによって表示されるオブジェクトを定義する [Viewselectedby](./viewselectedby-element-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="4cd2a-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="4cd2a-117">ビューによって表示されるプロパティを定義する [WideItem](./wideitem-element-for-widecontrol-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="4cd2a-117">The [WideItem](./wideitem-element-for-widecontrol-format.md) element that defines what property is displayed by the view.</span></span>

## <a name="example"></a><span data-ttu-id="4cd2a-118">例</span><span class="sxs-lookup"><span data-stu-id="4cd2a-118">Example</span></span>

<span data-ttu-id="4cd2a-119">次の XML は、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController.ServiceName) プロパティの値を表示するワイドビューを定義しています。</span><span class="sxs-lookup"><span data-stu-id="4cd2a-119">The following XML defines a wide view that displays the value of the [System.Serviceprocess.Servicecontroller.Servicename](/dotnet/api/System.ServiceProcess.ServiceController.ServiceName) property.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>

<Configuration>
  <ViewDefinitions>
    <View>
      <Name>ServiceWideView</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
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

<span data-ttu-id="4cd2a-120">次の例は、Windows PowerShell で Servicecontroller を表示する方法を示しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) オブジェクトこのフォーマットファイルが読み込まれた後。</span><span class="sxs-lookup"><span data-stu-id="4cd2a-120">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
Fax                      FCSAM
fdPHost                  FDResPub
FontCache                FontCache3.0.0.0
FSysAgent                FwcAgent
```

## <a name="see-also"></a><span data-ttu-id="4cd2a-121">参照</span><span class="sxs-lookup"><span data-stu-id="4cd2a-121">See Also</span></span>

[<span data-ttu-id="4cd2a-122">書式設定ファイルの例</span><span class="sxs-lookup"><span data-stu-id="4cd2a-122">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="4cd2a-123">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="4cd2a-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
