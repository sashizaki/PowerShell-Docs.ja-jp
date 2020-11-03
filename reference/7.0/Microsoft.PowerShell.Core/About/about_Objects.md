---
description: PowerShell のオブジェクトに関する重要な情報を提供します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_objects?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Objects
ms.openlocfilehash: b845dc8b55a19bb642c194398b0c9f5f13d24cb3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223664"
---
# <a name="about-objects"></a><span data-ttu-id="fcaf0-104">オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="fcaf0-104">About Objects</span></span>

## <a name="short-description"></a><span data-ttu-id="fcaf0-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="fcaf0-105">Short Description</span></span>
<span data-ttu-id="fcaf0-106">PowerShell のオブジェクトに関する重要な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-106">Provides essential information about objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="fcaf0-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="fcaf0-107">Long Description</span></span>

<span data-ttu-id="fcaf0-108">PowerShell で実行するすべてのアクションは、オブジェクトのコンテキスト内で発生します。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-108">Every action you take in PowerShell occurs within the context of objects.</span></span> <span data-ttu-id="fcaf0-109">あるコマンドから次のコマンドにデータを移動すると、1つまたは複数の識別可能なオブジェクトとして移動します。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-109">As data moves from one command to the next, it moves as one or more identifiable objects.</span></span> <span data-ttu-id="fcaf0-110">オブジェクトは、アイテムを表すデータのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-110">An object, then, is a collection of data that represents an item.</span></span> <span data-ttu-id="fcaf0-111">オブジェクトは、オブジェクトの種類、メソッド、およびそのプロパティの3種類のデータで構成されます。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-111">An object is made up of three types of data: the objects type, its methods, and its properties.</span></span>

## <a name="types-methods-and-properties"></a><span data-ttu-id="fcaf0-112">型、メソッド、およびプロパティ</span><span class="sxs-lookup"><span data-stu-id="fcaf0-112">Types, Methods, and Properties</span></span>

<span data-ttu-id="fcaf0-113">オブジェクトの種類は、オブジェクトの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-113">The object type tells what kind of object it is.</span></span> <span data-ttu-id="fcaf0-114">たとえば、ファイルを表すオブジェクトは、FileInfo オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-114">For example, an object that represents a file is a FileInfo object.</span></span>

<span data-ttu-id="fcaf0-115">オブジェクトメソッドは、オブジェクトに対して実行できるアクションです。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-115">The object methods are actions that you can perform on the object.</span></span>
<span data-ttu-id="fcaf0-116">たとえば、FileInfo オブジェクトには、ファイルのコピーに使用できる CopyTo メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-116">For example, FileInfo objects have a CopyTo method that you can use to copy the file.</span></span>

<span data-ttu-id="fcaf0-117">オブジェクトのプロパティには、オブジェクトに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-117">Object properties store information about the object.</span></span> <span data-ttu-id="fcaf0-118">たとえば、FileInfo オブジェクトには、ファイルが最後にアクセスされた日付と時刻を格納する LastWriteTime プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-118">For example, FileInfo objects have a LastWriteTime property that stores the date and time that the file was most recently accessed.</span></span>

<span data-ttu-id="fcaf0-119">オブジェクトを操作する場合は、コマンドでそのメソッドとプロパティを使用して、アクションを実行したり、データを管理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-119">When working with objects, you can use their methods and properties in commands to take action and manage data.</span></span>

## <a name="objects-in-pipelines"></a><span data-ttu-id="fcaf0-120">パイプライン内のオブジェクト</span><span class="sxs-lookup"><span data-stu-id="fcaf0-120">Objects in Pipelines</span></span>

<span data-ttu-id="fcaf0-121">パイプラインでコマンドを結合すると、それらのコマンドはオブジェクトとして相互に情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-121">When commands are combined in a pipeline, they pass information to each other as objects.</span></span> <span data-ttu-id="fcaf0-122">最初のコマンドが実行されると、パイプライン内の1つ以上のオブジェクトが2番目のコマンドに送信されます。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-122">When the first command runs, it sends one or more objects down the pipeline to the second command.</span></span> <span data-ttu-id="fcaf0-123">2番目のコマンドは、最初のコマンドからオブジェクトを受け取り、オブジェクトを処理してから、新しいオブジェクトまたは変更されたオブジェクトをパイプラインの次のコマンドに渡します。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-123">The second command receives the objects from the first command, processes the objects, and then passes new or revised objects to the next command in the pipeline.</span></span>
<span data-ttu-id="fcaf0-124">これは、パイプライン内のすべてのコマンドが実行されるまで続行されます。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-124">This continues until all commands in the pipeline run.</span></span>

<span data-ttu-id="fcaf0-125">次の例は、オブジェクトが1つのコマンドから次のコマンドに渡される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-125">The following example demonstrates how objects are passed from one command to the next:</span></span>

```powershell
Get-ChildItem C: | where { $_.PsIsContainer -eq $false } | Format-List
```

<span data-ttu-id="fcaf0-126">最初のコマンドは、 `Get-ChildItem C:` ファイルシステムのルートディレクトリ内の各項目について、ファイルまたはディレクトリオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-126">The first command `Get-ChildItem C:` returns a file or directory object for each item in the root directory of the file system.</span></span> <span data-ttu-id="fcaf0-127">File オブジェクトと directory オブジェクトは、パイプラインから2番目のコマンドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-127">The file and directory objects are passed down the pipeline to the second command.</span></span>

<span data-ttu-id="fcaf0-128">2番目のコマンドは、 `where { $_.PsIsContainer -eq $false }` すべてのファイルシステムオブジェクトの PsIsContainer プロパティを使用して、PsIsContainer プロパティの値が false (false) のファイルのみを選択し \$ ます。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-128">The second command `where { $_.PsIsContainer -eq $false }` uses the PsIsContainer property of all file system objects to select only files, which have a value of False (\$false) in their PsIsContainer property.</span></span> <span data-ttu-id="fcaf0-129">フォルダーはコンテナーであり、PsIsContainer プロパティに True (true) という値が設定されて \$ いますが、これは選択されていません。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-129">Folders, which are containers and, thus, have a value of True (\$true) in their PsIsContainer property, are not selected.</span></span>

<span data-ttu-id="fcaf0-130">2番目のコマンドは、ファイルオブジェクトのみを3番目のコマンドに渡します。このコマンドは、 `Format-List` ファイルオブジェクトを一覧に表示します。</span><span class="sxs-lookup"><span data-stu-id="fcaf0-130">The second command passes only the file objects to the third command `Format-List`, which displays the file objects in a list.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcaf0-131">参照</span><span class="sxs-lookup"><span data-stu-id="fcaf0-131">See Also</span></span>

[<span data-ttu-id="fcaf0-132">about_Methods</span><span class="sxs-lookup"><span data-stu-id="fcaf0-132">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="fcaf0-133">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="fcaf0-133">about_Object_Creation</span></span>](about_Object_Creation.md)

[<span data-ttu-id="fcaf0-134">about_Properties</span><span class="sxs-lookup"><span data-stu-id="fcaf0-134">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="fcaf0-135">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="fcaf0-135">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="fcaf0-136">Get-Member</span><span class="sxs-lookup"><span data-stu-id="fcaf0-136">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)
