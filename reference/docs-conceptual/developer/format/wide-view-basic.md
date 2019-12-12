---
title: ワイドビュー (基本) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9abb63b8-6d02-4e24-9c0e-2d15a04e9051
caps.latest.revision: 8
ms.openlocfilehash: 7a36f548a3eccdf2c9cad04a8bfe28bf4e8d6dfd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367941"
---
# <a name="wide-view-basic"></a><span data-ttu-id="96cd2-102">ワイド ビュー (基本)</span><span class="sxs-lookup"><span data-stu-id="96cd2-102">Wide View (Basic)</span></span>

<span data-ttu-id="96cd2-103">この例では、Servicecontroller を表示する基本的なワイドビューを実装する方法を示します。 [Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) `Get-Service` コマンドレットによって返される Fullname オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="96cd2-103">This example shows how to implement a basic wide view that displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="96cd2-104">ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96cd2-104">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="96cd2-105">この書式設定ファイルを読み込むには</span><span class="sxs-lookup"><span data-stu-id="96cd2-105">To load this formatting file</span></span>

1. <span data-ttu-id="96cd2-106">このトピックの「例」のセクションにある XML をテキストファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="96cd2-106">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="96cd2-107">テキスト ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="96cd2-107">Save the text file.</span></span> <span data-ttu-id="96cd2-108">`format.ps1xml` 拡張機能をファイルに追加して、フォーマットファイルとして識別するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="96cd2-108">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="96cd2-109">Windows PowerShell を開き、次のコマンドを実行して、書式設定ファイルを現在のセッションに読み込みます: `Update-formatdata -prependpath PathToFormattingFile`。</span><span class="sxs-lookup"><span data-stu-id="96cd2-109">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="96cd2-110">この書式設定ファイルは、Windows PowerShell の書式設定ファイルによって既に定義されているオブジェクトの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="96cd2-110">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="96cd2-111">コマンドレットの実行時には `prependPath` パラメーターを使用する必要があり、このフォーマットファイルをモジュールとして読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="96cd2-111">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="96cd2-112">使用例</span><span class="sxs-lookup"><span data-stu-id="96cd2-112">Demonstrates</span></span>

<span data-ttu-id="96cd2-113">この書式設定ファイルは、次の XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="96cd2-113">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="96cd2-114">ビューの[Name](./name-element-for-view-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="96cd2-114">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="96cd2-115">ビューによって表示されるオブジェクトを定義する[Viewselectedby](./viewselectedby-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="96cd2-115">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="96cd2-116">ビューによって表示されるプロパティを定義する[WideItem](./wideitem-element-for-widecontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="96cd2-116">The [WideItem](./wideitem-element-for-widecontrol-format.md) element that defines what property is displayed by the view.</span></span>

## <a name="example"></a><span data-ttu-id="96cd2-117">例</span><span class="sxs-lookup"><span data-stu-id="96cd2-117">Example</span></span>

<span data-ttu-id="96cd2-118">次の XML は、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController.ServiceName)プロパティの値を表示するワイドビューを定義しています。</span><span class="sxs-lookup"><span data-stu-id="96cd2-118">The following XML defines a wide view that displays the value of the [System.Serviceprocess.Servicecontroller.Servicename](/dotnet/api/System.ServiceProcess.ServiceController.ServiceName) property.</span></span>

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

<span data-ttu-id="96cd2-119">次の例は、Windows PowerShell で Servicecontroller を表示する方法を示しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトこのフォーマットファイルが読み込まれた後。</span><span class="sxs-lookup"><span data-stu-id="96cd2-119">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
Fax                      FCSAM
fdPHost                  FDResPub
FontCache                FontCache3.0.0.0
FSysAgent                FwcAgent
```

## <a name="see-also"></a><span data-ttu-id="96cd2-120">参照</span><span class="sxs-lookup"><span data-stu-id="96cd2-120">See Also</span></span>

[<span data-ttu-id="96cd2-121">フォーマットファイルの例</span><span class="sxs-lookup"><span data-stu-id="96cd2-121">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="96cd2-122">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="96cd2-122">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
