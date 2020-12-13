---
ms.date: 09/13/2016
ms.topic: reference
title: 書式設定ファイルを作成する方法 (.format.ps1xml)
description: 書式設定ファイルを作成する方法 (.format.ps1xml)
ms.openlocfilehash: 5bbc1ba40bfccf13636abc0f0751938aa724b761
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651993"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a><span data-ttu-id="5eee4-103">書式設定ファイルを作成する方法 (.format.ps1xml)</span><span class="sxs-lookup"><span data-stu-id="5eee4-103">How to Create a Formatting File (.format.ps1xml)</span></span>

<span data-ttu-id="5eee4-104">このトピックでは、書式設定ファイル (.format.ps1xml) を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5eee4-104">This topic describes how to create a formatting file (.format.ps1xml).</span></span>

> [!NOTE]
> <span data-ttu-id="5eee4-105">また、Windows PowerShell によって提供されるいずれかのファイルのコピーを作成することによって、フォーマットファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5eee4-105">You can also create a formatting file by making a copy of one of the files provided by Windows PowerShell.</span></span> <span data-ttu-id="5eee4-106">既存のファイルのコピーを作成する場合は、既存のデジタル署名を削除し、独自の署名を新しいファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="5eee4-106">If you make a copy of an existing file, delete the existing digital signature, and add your own signature to the new file.</span></span>

### <a name="to-create-a-formatps1xml-file"></a><span data-ttu-id="5eee4-107">.format.ps1xml ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5eee4-107">To create a .format.ps1xml file.</span></span>

1. <span data-ttu-id="5eee4-108">メモ帳などのテキストエディターを使用して、テキストファイル (.txt) を作成します。</span><span class="sxs-lookup"><span data-stu-id="5eee4-108">Create a text file (.txt) using a text editor such as Notepad.</span></span>

2. <span data-ttu-id="5eee4-109">次の行を書式設定ファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="5eee4-109">Copy the following lines into the formatting file.</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - <span data-ttu-id="5eee4-110">タグによっ `<Configuration></Configuration>` て、ルートノードが定義され `Configuration` ます。</span><span class="sxs-lookup"><span data-stu-id="5eee4-110">The `<Configuration></Configuration>` tags define the root `Configuration` node.</span></span> <span data-ttu-id="5eee4-111">その他のすべての XML タグは、このノード内で囲まれます。</span><span class="sxs-lookup"><span data-stu-id="5eee4-111">All additional XML tags will be enclosed within this node.</span></span>

   - <span data-ttu-id="5eee4-112">タグによっ `<ViewDefinitions></ViewDefinitions>` てノードが定義され `ViewDefinitions` ます。</span><span class="sxs-lookup"><span data-stu-id="5eee4-112">The `<ViewDefinitions></ViewDefinitions>` tags define the `ViewDefinitions` node.</span></span> <span data-ttu-id="5eee4-113">すべてのビューは、このノード内で定義されます。</span><span class="sxs-lookup"><span data-stu-id="5eee4-113">All views are defined within this node.</span></span>

3. <span data-ttu-id="5eee4-114">Windows PowerShell のインストールフォルダー、モジュールフォルダー、またはモジュールフォルダーのサブフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="5eee4-114">Save the file to the Windows PowerShell installation folder, to your module folder, or to a subfolder of the module folder.</span></span> <span data-ttu-id="5eee4-115">ファイルを保存するときは、次の名前形式を  `MyFile.format.ps1xml` 使用します。</span><span class="sxs-lookup"><span data-stu-id="5eee4-115">Use the following name format when you save the file:  `MyFile.format.ps1xml`.</span></span> <span data-ttu-id="5eee4-116">フォーマットファイルでは、拡張機能を使用する必要があり `.format.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="5eee4-116">Formatting files must use the `.format.ps1xml` extension.</span></span>

   <span data-ttu-id="5eee4-117">これで、書式設定ファイルにビューを追加する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="5eee4-117">You are now ready to add views to the formatting file.</span></span> <span data-ttu-id="5eee4-118">書式設定ファイルで定義できるビューの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="5eee4-118">There is no limit to the number of views that can be defined in a formatting file.</span></span> <span data-ttu-id="5eee4-119">オブジェクトごとに1つのビュー、同じオブジェクトに対して複数のビュー、または複数のオブジェクトで使用される1つのビューを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5eee4-119">You can add a single view for each object, multiple views for the same object, or a single view that is used by multiple objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="5eee4-120">参照</span><span class="sxs-lookup"><span data-stu-id="5eee4-120">See Also</span></span>

[<span data-ttu-id="5eee4-121">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="5eee4-121">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
