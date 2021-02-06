---
description: PowerShell のオブジェクトに関する重要な情報を提供します。
Locale: en-US
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_objects?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Objects
ms.openlocfilehash: bfb66e72a74d20379123558b85047097dc801e9d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601229"
---
# <a name="about-objects"></a><span data-ttu-id="fc101-103">オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="fc101-103">About Objects</span></span>

## <a name="short-description"></a><span data-ttu-id="fc101-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="fc101-104">Short Description</span></span>
<span data-ttu-id="fc101-105">PowerShell のオブジェクトに関する重要な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="fc101-105">Provides essential information about objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="fc101-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="fc101-106">Long Description</span></span>

<span data-ttu-id="fc101-107">PowerShell で実行するすべてのアクションは、オブジェクトのコンテキスト内で発生します。</span><span class="sxs-lookup"><span data-stu-id="fc101-107">Every action you take in PowerShell occurs within the context of objects.</span></span> <span data-ttu-id="fc101-108">あるコマンドから次のコマンドにデータを移動すると、1つまたは複数の識別可能なオブジェクトとして移動します。</span><span class="sxs-lookup"><span data-stu-id="fc101-108">As data moves from one command to the next, it moves as one or more identifiable objects.</span></span> <span data-ttu-id="fc101-109">オブジェクトは、アイテムを表すデータのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="fc101-109">An object, then, is a collection of data that represents an item.</span></span> <span data-ttu-id="fc101-110">オブジェクトは、オブジェクトの種類、メソッド、およびそのプロパティの3種類のデータで構成されます。</span><span class="sxs-lookup"><span data-stu-id="fc101-110">An object is made up of three types of data: the objects type, its methods, and its properties.</span></span>

## <a name="types-methods-and-properties"></a><span data-ttu-id="fc101-111">型、メソッド、およびプロパティ</span><span class="sxs-lookup"><span data-stu-id="fc101-111">Types, Methods, and Properties</span></span>

<span data-ttu-id="fc101-112">オブジェクトの種類は、オブジェクトの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="fc101-112">The object type tells what kind of object it is.</span></span> <span data-ttu-id="fc101-113">たとえば、ファイルを表すオブジェクトは、FileInfo オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="fc101-113">For example, an object that represents a file is a FileInfo object.</span></span>

<span data-ttu-id="fc101-114">オブジェクトメソッドは、オブジェクトに対して実行できるアクションです。</span><span class="sxs-lookup"><span data-stu-id="fc101-114">The object methods are actions that you can perform on the object.</span></span>
<span data-ttu-id="fc101-115">たとえば、FileInfo オブジェクトには、ファイルのコピーに使用できる CopyTo メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="fc101-115">For example, FileInfo objects have a CopyTo method that you can use to copy the file.</span></span>

<span data-ttu-id="fc101-116">オブジェクトのプロパティには、オブジェクトに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="fc101-116">Object properties store information about the object.</span></span> <span data-ttu-id="fc101-117">たとえば、FileInfo オブジェクトには、ファイルが最後にアクセスされた日付と時刻を格納する LastWriteTime プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="fc101-117">For example, FileInfo objects have a LastWriteTime property that stores the date and time that the file was most recently accessed.</span></span>

<span data-ttu-id="fc101-118">オブジェクトを操作する場合は、コマンドでそのメソッドとプロパティを使用して、アクションを実行したり、データを管理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="fc101-118">When working with objects, you can use their methods and properties in commands to take action and manage data.</span></span>

## <a name="objects-in-pipelines"></a><span data-ttu-id="fc101-119">パイプライン内のオブジェクト</span><span class="sxs-lookup"><span data-stu-id="fc101-119">Objects in Pipelines</span></span>

<span data-ttu-id="fc101-120">パイプラインでコマンドを結合すると、それらのコマンドはオブジェクトとして相互に情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="fc101-120">When commands are combined in a pipeline, they pass information to each other as objects.</span></span> <span data-ttu-id="fc101-121">最初のコマンドが実行されると、パイプライン内の1つ以上のオブジェクトが2番目のコマンドに送信されます。</span><span class="sxs-lookup"><span data-stu-id="fc101-121">When the first command runs, it sends one or more objects down the pipeline to the second command.</span></span> <span data-ttu-id="fc101-122">2番目のコマンドは、最初のコマンドからオブジェクトを受け取り、オブジェクトを処理してから、新しいオブジェクトまたは変更されたオブジェクトをパイプラインの次のコマンドに渡します。</span><span class="sxs-lookup"><span data-stu-id="fc101-122">The second command receives the objects from the first command, processes the objects, and then passes new or revised objects to the next command in the pipeline.</span></span>
<span data-ttu-id="fc101-123">これは、パイプライン内のすべてのコマンドが実行されるまで続行されます。</span><span class="sxs-lookup"><span data-stu-id="fc101-123">This continues until all commands in the pipeline run.</span></span>

<span data-ttu-id="fc101-124">次の例は、オブジェクトが1つのコマンドから次のコマンドに渡される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fc101-124">The following example demonstrates how objects are passed from one command to the next:</span></span>

```powershell
Get-ChildItem C: | where { $_.PsIsContainer -eq $false } | Format-List
```

<span data-ttu-id="fc101-125">最初のコマンドは、 `Get-ChildItem C:` ファイルシステムのルートディレクトリ内の各項目について、ファイルまたはディレクトリオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="fc101-125">The first command `Get-ChildItem C:` returns a file or directory object for each item in the root directory of the file system.</span></span> <span data-ttu-id="fc101-126">File オブジェクトと directory オブジェクトは、パイプラインから2番目のコマンドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="fc101-126">The file and directory objects are passed down the pipeline to the second command.</span></span>

<span data-ttu-id="fc101-127">2番目のコマンドは、 `where { $_.PsIsContainer -eq $false }` すべてのファイルシステムオブジェクトの PsIsContainer プロパティを使用して、PsIsContainer プロパティの値が false (false) のファイルのみを選択し \$ ます。</span><span class="sxs-lookup"><span data-stu-id="fc101-127">The second command `where { $_.PsIsContainer -eq $false }` uses the PsIsContainer property of all file system objects to select only files, which have a value of False (\$false) in their PsIsContainer property.</span></span> <span data-ttu-id="fc101-128">フォルダーはコンテナーであり、PsIsContainer プロパティに True (true) という値が設定されて \$ いますが、これは選択されていません。</span><span class="sxs-lookup"><span data-stu-id="fc101-128">Folders, which are containers and, thus, have a value of True (\$true) in their PsIsContainer property, are not selected.</span></span>

<span data-ttu-id="fc101-129">2番目のコマンドは、ファイルオブジェクトのみを3番目のコマンドに渡します。このコマンドは、 `Format-List` ファイルオブジェクトを一覧に表示します。</span><span class="sxs-lookup"><span data-stu-id="fc101-129">The second command passes only the file objects to the third command `Format-List`, which displays the file objects in a list.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc101-130">参照</span><span class="sxs-lookup"><span data-stu-id="fc101-130">See Also</span></span>

[<span data-ttu-id="fc101-131">about_Methods</span><span class="sxs-lookup"><span data-stu-id="fc101-131">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="fc101-132">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="fc101-132">about_Object_Creation</span></span>](about_Object_Creation.md)

[<span data-ttu-id="fc101-133">about_Properties</span><span class="sxs-lookup"><span data-stu-id="fc101-133">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="fc101-134">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="fc101-134">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="fc101-135">Get-Member</span><span class="sxs-lookup"><span data-stu-id="fc101-135">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

