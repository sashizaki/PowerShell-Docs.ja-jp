---
title: ワイドビュー (基本) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d92c29c33c5104b6186ae53ccf544be197d657b1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772401"
---
# <a name="wide-view-basic"></a><span data-ttu-id="2b1b1-102">ワイド ビュー (基本)</span><span class="sxs-lookup"><span data-stu-id="2b1b1-102">Wide View (Basic)</span></span>

<span data-ttu-id="2b1b1-103">この例では、Servicecontroller を表示する基本的なワイドビューを実装する方法を示します。 [Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController)コマンドレットによって返される Fullname オブジェクト `Get-Service` 。</span><span class="sxs-lookup"><span data-stu-id="2b1b1-103">This example shows how to implement a basic wide view that displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="2b1b1-104">ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b1b1-104">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="2b1b1-105">この書式設定ファイルを読み込むには</span><span class="sxs-lookup"><span data-stu-id="2b1b1-105">To load this formatting file</span></span>

1. <span data-ttu-id="2b1b1-106">このトピックの「例」のセクションにある XML をテキストファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="2b1b1-106">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="2b1b1-107">テキスト ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="2b1b1-107">Save the text file.</span></span> <span data-ttu-id="2b1b1-108">ファイルに拡張子を追加して、 `format.ps1xml` 書式設定ファイルとして識別するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="2b1b1-108">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="2b1b1-109">Windows PowerShell を開き、次のコマンドを実行して、書式設定ファイルを現在のセッションに読み込み `Update-formatdata -prependpath PathToFormattingFile` ます。</span><span class="sxs-lookup"><span data-stu-id="2b1b1-109">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="2b1b1-110">この書式設定ファイルは、Windows PowerShell の書式設定ファイルによって既に定義されているオブジェクトの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="2b1b1-110">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="2b1b1-111">`prependPath`コマンドレットを実行するときにパラメーターを使用する必要があります。このフォーマットファイルをモジュールとして読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="2b1b1-111">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="2b1b1-112">対象</span><span class="sxs-lookup"><span data-stu-id="2b1b1-112">Demonstrates</span></span>

<span data-ttu-id="2b1b1-113">この書式設定ファイルは、次の XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b1b1-113">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="2b1b1-114">ビューの[Name](./name-element-for-view-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="2b1b1-114">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="2b1b1-115">ビューによって表示されるオブジェクトを定義する[Viewselectedby](./viewselectedby-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="2b1b1-115">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="2b1b1-116">ビューによって表示されるプロパティを定義する[WideItem](./wideitem-element-for-widecontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="2b1b1-116">The [WideItem](./wideitem-element-for-widecontrol-format.md) element that defines what property is displayed by the view.</span></span>

## <a name="example"></a><span data-ttu-id="2b1b1-117">例</span><span class="sxs-lookup"><span data-stu-id="2b1b1-117">Example</span></span>

<span data-ttu-id="2b1b1-118">次の XML は、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController.ServiceName)プロパティの値を表示するワイドビューを定義しています。</span><span class="sxs-lookup"><span data-stu-id="2b1b1-118">The following XML defines a wide view that displays the value of the [System.Serviceprocess.Servicecontroller.Servicename](/dotnet/api/System.ServiceProcess.ServiceController.ServiceName) property.</span></span>

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

<span data-ttu-id="2b1b1-119">次の例は、Windows PowerShell で Servicecontroller を表示する方法を示しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトこのフォーマットファイルが読み込まれた後。</span><span class="sxs-lookup"><span data-stu-id="2b1b1-119">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
Fax                      FCSAM
fdPHost                  FDResPub
FontCache                FontCache3.0.0.0
FSysAgent                FwcAgent
```

## <a name="see-also"></a><span data-ttu-id="2b1b1-120">参照</span><span class="sxs-lookup"><span data-stu-id="2b1b1-120">See Also</span></span>

[<span data-ttu-id="2b1b1-121">書式設定ファイルの例</span><span class="sxs-lookup"><span data-stu-id="2b1b1-121">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="2b1b1-122">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="2b1b1-122">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
