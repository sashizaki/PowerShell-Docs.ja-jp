---
title: 書式設定ファイル (types.ps1xml) を作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb568878-f63e-4561-98e2-16ee2ac7559d
caps.latest.revision: 8
ms.openlocfilehash: 7a578dd63a53562f992b2970573258b8676e2a52
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692271"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a><span data-ttu-id="ba59d-102">書式設定ファイルを作成する方法 (.format.ps1xml)</span><span class="sxs-lookup"><span data-stu-id="ba59d-102">How to Create a Formatting File (.format.ps1xml)</span></span>

<span data-ttu-id="ba59d-103">このトピックでは、書式設定ファイル (types.ps1xml) を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba59d-103">This topic describes how to create a formatting file (.format.ps1xml).</span></span>

> [!NOTE]
> <span data-ttu-id="ba59d-104">また、Windows PowerShell によって提供されるいずれかのファイルのコピーを作成することによって、フォーマットファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ba59d-104">You can also create a formatting file by making a copy of one of the files provided by Windows PowerShell.</span></span> <span data-ttu-id="ba59d-105">既存のファイルのコピーを作成する場合は、既存のデジタル署名を削除し、独自の署名を新しいファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="ba59d-105">If you make a copy of an existing file, delete the existing digital signature, and add your own signature to the new file.</span></span>

### <a name="to-create-a-formatps1xml-file"></a><span data-ttu-id="ba59d-106">Types.ps1xml ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ba59d-106">To create a .format.ps1xml file.</span></span>

1. <span data-ttu-id="ba59d-107">メモ帳などのテキストエディターを使用して、テキストファイル (.txt) を作成します。</span><span class="sxs-lookup"><span data-stu-id="ba59d-107">Create a text file (.txt) using a text editor such as Notepad.</span></span>

2. <span data-ttu-id="ba59d-108">次の行を書式設定ファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="ba59d-108">Copy the following lines into the formatting file.</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - <span data-ttu-id="ba59d-109">タグによっ `<Configuration></Configuration>` て、ルートノードが定義され `Configuration` ます。</span><span class="sxs-lookup"><span data-stu-id="ba59d-109">The `<Configuration></Configuration>` tags define the root `Configuration` node.</span></span> <span data-ttu-id="ba59d-110">その他のすべての XML タグは、このノード内で囲まれます。</span><span class="sxs-lookup"><span data-stu-id="ba59d-110">All additional XML tags will be enclosed within this node.</span></span>

   - <span data-ttu-id="ba59d-111">タグによっ `<ViewDefinitions></ViewDefinitions>` てノードが定義され `ViewDefinitions` ます。</span><span class="sxs-lookup"><span data-stu-id="ba59d-111">The `<ViewDefinitions></ViewDefinitions>` tags define the `ViewDefinitions` node.</span></span> <span data-ttu-id="ba59d-112">すべてのビューは、このノード内で定義されます。</span><span class="sxs-lookup"><span data-stu-id="ba59d-112">All views are defined within this node.</span></span>

3. <span data-ttu-id="ba59d-113">Windows PowerShell のインストールフォルダー、モジュールフォルダー、またはモジュールフォルダーのサブフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ba59d-113">Save the file to the Windows PowerShell installation folder, to your module folder, or to a subfolder of the module folder.</span></span> <span data-ttu-id="ba59d-114">ファイルを保存するときは、次の名前形式を `MyFile.format.ps1xml` 使用します。</span><span class="sxs-lookup"><span data-stu-id="ba59d-114">Use the following name format when you save the file:  `MyFile.format.ps1xml`.</span></span> <span data-ttu-id="ba59d-115">フォーマットファイルでは、拡張機能を使用する必要があり `.format.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="ba59d-115">Formatting files must use the `.format.ps1xml` extension.</span></span>

   <span data-ttu-id="ba59d-116">これで、書式設定ファイルにビューを追加する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="ba59d-116">You are now ready to add views to the formatting file.</span></span> <span data-ttu-id="ba59d-117">書式設定ファイルで定義できるビューの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="ba59d-117">There is no limit to the number of views that can be defined in a formatting file.</span></span> <span data-ttu-id="ba59d-118">オブジェクトごとに1つのビュー、同じオブジェクトに対して複数のビュー、または複数のオブジェクトで使用される1つのビューを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ba59d-118">You can add a single view for each object, multiple views for the same object, or a single view that is used by multiple objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba59d-119">参照</span><span class="sxs-lookup"><span data-stu-id="ba59d-119">See Also</span></span>

[<span data-ttu-id="ba59d-120">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="ba59d-120">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
