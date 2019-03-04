---
title: 書式設定ファイルを作成する方法 (. format.ps1xml) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb568878-f63e-4561-98e2-16ee2ac7559d
caps.latest.revision: 8
ms.openlocfilehash: e97e9ddb1bf81ba66e5f3cedddd22e3a861ce228
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862968"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a><span data-ttu-id="423c4-102">書式設定ファイルを作成する方法 (.format.ps1xml)</span><span class="sxs-lookup"><span data-stu-id="423c4-102">How to Create a Formatting File (.format.ps1xml)</span></span>

<span data-ttu-id="423c4-103">このトピックでは、書式設定ファイルを作成する方法を説明します (. format.ps1xml)。</span><span class="sxs-lookup"><span data-stu-id="423c4-103">This topic describes how to create a formatting file (.format.ps1xml).</span></span>

> [!NOTE]
> <span data-ttu-id="423c4-104">Windows PowerShell によって提供されるファイルの 1 つのコピーを作成して、書式設定ファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="423c4-104">You can also create a formatting file by making a copy of one of the files provided by Windows PowerShell.</span></span> <span data-ttu-id="423c4-105">既存のファイルのコピーを作成する場合は、既存のデジタル署名を削除し、新しいファイルに独自の署名を追加します。</span><span class="sxs-lookup"><span data-stu-id="423c4-105">If you make a copy of an existing file, delete the existing digital signature, and add your own signature to the new file.</span></span>

### <a name="to-create-a-formatps1xml-file"></a><span data-ttu-id="423c4-106">作成する。 format.ps1xml ファイル。</span><span class="sxs-lookup"><span data-stu-id="423c4-106">To create a .format.ps1xml file.</span></span>

1. <span data-ttu-id="423c4-107">メモ帳などのエディター、テキストを使用して、テキスト ファイル (.txt) を作成します。</span><span class="sxs-lookup"><span data-stu-id="423c4-107">Create a text file (.txt) using a text editor such as Notepad.</span></span>

2. <span data-ttu-id="423c4-108">書式設定ファイルには、次の行をコピーします。</span><span class="sxs-lookup"><span data-stu-id="423c4-108">Copy the following lines into the formatting file.</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - <span data-ttu-id="423c4-109">\<構成 >\<設定 > タグ定義のルート`Configuration`ノード。</span><span class="sxs-lookup"><span data-stu-id="423c4-109">The \<Configuration>\</Configuration> tags define the root `Configuration` node.</span></span> <span data-ttu-id="423c4-110">その他のすべての XML タグは、このノード内で囲まれます。</span><span class="sxs-lookup"><span data-stu-id="423c4-110">All additional XML tags will be enclosed within this node.</span></span>

   - <span data-ttu-id="423c4-111"><ViewDefinitions> </ViewDefinitions>タグを定義、`ViewDefinitions`ノード。</span><span class="sxs-lookup"><span data-stu-id="423c4-111">The <ViewDefinitions></ViewDefinitions> tags define the `ViewDefinitions` node.</span></span> <span data-ttu-id="423c4-112">このノード内のすべてのビューが定義されます。</span><span class="sxs-lookup"><span data-stu-id="423c4-112">All views are defined within this node.</span></span>

3. <span data-ttu-id="423c4-113">Windows PowerShell のインストール フォルダーに、モジュールのフォルダー、またはモジュール フォルダーのサブフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="423c4-113">Save the file to the Windows PowerShell installation folder, to your module folder, or to a subfolder of the module folder.</span></span> <span data-ttu-id="423c4-114">ファイルを保存するときに、次の名前形式を使用:`MyFile.format.ps1xml`します。</span><span class="sxs-lookup"><span data-stu-id="423c4-114">Use the following name format when you save the file:  `MyFile.format.ps1xml`.</span></span> <span data-ttu-id="423c4-115">書式設定ファイルを使用する必要があります、`.format.ps1xml`拡張機能。</span><span class="sxs-lookup"><span data-stu-id="423c4-115">Formatting files must use the `.format.ps1xml` extension.</span></span>

   <span data-ttu-id="423c4-116">書式設定ファイルにビューを追加する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="423c4-116">You are now ready to add views to the formatting file.</span></span> <span data-ttu-id="423c4-117">書式設定ファイルで定義できるビューの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="423c4-117">There is no limit to the number of views that can be defined in a formatting file.</span></span> <span data-ttu-id="423c4-118">各オブジェクト、同じオブジェクトに複数のビュー、または複数のオブジェクトによって使用される 1 つのビューの 1 つのビューを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="423c4-118">You can add a single view for each object, multiple views for the same object, or a single view that is used by multiple objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="423c4-119">参照</span><span class="sxs-lookup"><span data-stu-id="423c4-119">See Also</span></span>

[<span data-ttu-id="423c4-120">Windows PowerShell の書式設定の書き込みとファイルの種類</span><span class="sxs-lookup"><span data-stu-id="423c4-120">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
