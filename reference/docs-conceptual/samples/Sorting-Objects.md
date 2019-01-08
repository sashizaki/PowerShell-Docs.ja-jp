---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: オブジェクトの並べ替え
ms.assetid: 8530caa8-3ed4-4c56-aed7-1295dd9ba199
ms.openlocfilehash: 06aa15d89888f1ecbe60b8e1dfb4efebb1d73673
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402230"
---
# <a name="sorting-objects"></a><span data-ttu-id="c0776-103">オブジェクトの並べ替え</span><span class="sxs-lookup"><span data-stu-id="c0776-103">Sorting Objects</span></span>

<span data-ttu-id="c0776-104">表示されているデータを使用してスキャンするが容易に整理できます、`Sort-Object`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="c0776-104">We can organize displayed data to make it easier to scan by using the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="c0776-105">`Sort-Object` 並べ替えには、使用する 1 つまたは複数のプロパティの名前を受け取り、これらのプロパティの値で並べ替えられたデータを返します。</span><span class="sxs-lookup"><span data-stu-id="c0776-105">`Sort-Object` takes the name of one or more properties to sort on, and returns data sorted by the values of those properties.</span></span>

## <a name="basic-sorting"></a><span data-ttu-id="c0776-106">基本的な並べ替え</span><span class="sxs-lookup"><span data-stu-id="c0776-106">Basic sorting</span></span>

<span data-ttu-id="c0776-107">サブディレクトリと現在のディレクトリにファイルを一覧表示の問題を検討してください。</span><span class="sxs-lookup"><span data-stu-id="c0776-107">Consider the problem of listing subdirectories and files in the current directory.</span></span>
<span data-ttu-id="c0776-108">並べ替えたい場合**LastWriteTime** 、まず**名前**、」と入力して実行できます。</span><span class="sxs-lookup"><span data-stu-id="c0776-108">If we want to sort by **LastWriteTime** and then by **Name**, we can do it by typing:</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property LastWriteTime, Name |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
11/6/2017 10:10:11 AM  .localization-config
11/6/2017 10:10:11 AM  .openpublishing.build.ps1
11/6/2017 10:10:11 AM  appveyor.yml
11/6/2017 10:10:11 AM  LICENSE
11/6/2017 10:10:11 AM  LICENSE-CODE
11/6/2017 10:10:11 AM  ThirdPartyNotices
11/6/2017 10:10:15 AM  tests
6/6/2018 7:58:59 PM    CONTRIBUTING.md
6/6/2018 7:58:59 PM    README.md
...
```

<span data-ttu-id="c0776-109">並べ替えることができますも、オブジェクトを逆の順序を指定して、**降順**スイッチ パラメーター。</span><span class="sxs-lookup"><span data-stu-id="c0776-109">You can also sort the objects in reverse order by specifying the **Descending** switch parameter.</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property LastWriteTime, Name -Descending |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
12/1/2018 10:13:50 PM  reference
12/1/2018 10:13:50 PM  dsc
...
6/6/2018 7:58:59 PM    README.md
6/6/2018 7:58:59 PM    CONTRIBUTING.md
11/6/2017 10:10:15 AM  tests
11/6/2017 10:10:11 AM  ThirdPartyNotices
11/6/2017 10:10:11 AM  LICENSE-CODE
11/6/2017 10:10:11 AM  LICENSE
11/6/2017 10:10:11 AM  appveyor.yml
11/6/2017 10:10:11 AM  .openpublishing.build.ps1
11/6/2017 10:10:11 AM  .localization-config
```

## <a name="using-hash-tables"></a><span data-ttu-id="c0776-110">ハッシュ テーブルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c0776-110">Using hash tables</span></span>

<span data-ttu-id="c0776-111">配列のハッシュ テーブルを使用して、異なる順序でさまざまなプロパティを並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="c0776-111">You can sort different properties in different orders by using hash tables in an array.</span></span>
<span data-ttu-id="c0776-112">各ハッシュ テーブルを使用して、**式**キー プロパティ名を文字列として指定して、**昇順**または**降順**キーによって並べ替え順序を指定する`$true`または`$false`.</span><span class="sxs-lookup"><span data-stu-id="c0776-112">Each hash table uses an **Expression** key to specify the property name as string and an **Ascending** or **Descending** key to specify the sort order by `$true` or `$false`.</span></span>
<span data-ttu-id="c0776-113">**式**キーは必須です。</span><span class="sxs-lookup"><span data-stu-id="c0776-113">The **Expression** key is mandatory.</span></span>
<span data-ttu-id="c0776-114">**昇順**または**降順**キーは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c0776-114">The **Ascending** or **Descending** key is optional.</span></span>

<span data-ttu-id="c0776-115">次の例は、降順でオブジェクトを並べ替えます**LastWriteTime**順序、昇順**名前**順序。</span><span class="sxs-lookup"><span data-stu-id="c0776-115">The following example sorts objects in descending **LastWriteTime** order and ascending **Name** order.</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property @{ Expression = 'LastWriteTime'; Descending = $true }, @{ Expression = 'Name'; Ascending = $true } |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
12/1/2018 10:13:50 PM  dsc
12/1/2018 10:13:50 PM  reference
11/29/2018 6:56:01 PM  .openpublishing.redirection.json
11/29/2018 6:56:01 PM  gallery
11/24/2018 10:33:22 AM developer
11/20/2018 7:22:19 PM  .markdownlint.json
...
```

<span data-ttu-id="c0776-116">スクリプト ブロックを設定することも、**式**キー。</span><span class="sxs-lookup"><span data-stu-id="c0776-116">You can also set a scriptblock to the **Expression** key.</span></span>
<span data-ttu-id="c0776-117">実行するときに、`Sort-Object`コマンドレットは、スクリプト ブロックが実行され、結果の並べ替えに使用します。</span><span class="sxs-lookup"><span data-stu-id="c0776-117">When running the `Sort-Object` cmdlet, the scriptblock is executed and the result is used for sorting.</span></span>

<span data-ttu-id="c0776-118">次の例は、間の時間の降順でオブジェクトを並べ替えます**CreationTime**と**LastWriteTime**します。</span><span class="sxs-lookup"><span data-stu-id="c0776-118">The following example sorts objects in descending order by the time span between **CreationTime** and **LastWriteTime**.</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property @{ Expression = { $_.LastWriteTime - $_.CreationTime }; Descending = $true } |
  Format-Table -Property LastWriteTime, CreationTime
```

```output
LastWriteTime          CreationTime
-------------          ------------
12/1/2018 10:13:50 PM  11/6/2017 10:10:11 AM
12/1/2018 10:13:50 PM  11/6/2017 10:10:11 AM
11/7/2018 6:52:24 PM   11/6/2017 10:10:11 AM
11/7/2018 6:52:24 PM   11/6/2017 10:10:15 AM
11/3/2018 9:58:17 AM   11/6/2017 10:10:11 AM
10/26/2018 4:50:21 PM  11/6/2017 10:10:11 AM
11/17/2018 1:10:57 PM  11/29/2017 5:48:30 PM
11/12/2018 6:29:53 PM  12/7/2017 7:57:07 PM
...
```

## <a name="tips"></a><span data-ttu-id="c0776-119">ヒント</span><span class="sxs-lookup"><span data-stu-id="c0776-119">Tips</span></span>

<span data-ttu-id="c0776-120">省略することができます、**プロパティ**として次のパラメーター名。</span><span class="sxs-lookup"><span data-stu-id="c0776-120">You can omit the **Property** parameter name as following:</span></span>

```powershell
Sort-Object LastWriteTime, Name
```

<span data-ttu-id="c0776-121">参照する以外にも、`Sort-Object`その組み込みエイリアスで`sort`:</span><span class="sxs-lookup"><span data-stu-id="c0776-121">Besides, you can refer to `Sort-Object` by its built-in alias, `sort`:</span></span>

```powershell
sort LastWriteTime, Name
```

<span data-ttu-id="c0776-122">次のように、ハッシュ テーブル内の並べ替えのキーを省略できます。</span><span class="sxs-lookup"><span data-stu-id="c0776-122">The keys in the hash tables for sorting can be abbreviated as following:</span></span>

```powershell
Sort-Object @{ e = 'LastWriteTime'; d = $true }, @{ e = 'Name'; a = $true }
```

<span data-ttu-id="c0776-123">この例で、 **e**略**式**、 **d**略**降順**、および **、** 略**昇順**します。</span><span class="sxs-lookup"><span data-stu-id="c0776-123">In this example, the **e** stands for **Expression**, the **d** stands for **Descending**, and the **a** stands for **Ascending**.</span></span>

<span data-ttu-id="c0776-124">読みやすさを向上させるのには、別個の変数に、ハッシュ テーブルを配置できます。</span><span class="sxs-lookup"><span data-stu-id="c0776-124">To improve readability, you can place the hash tables into a separate variable:</span></span>

```powershell
$order = @(
  @{ Expression = 'LastWriteTime'; Descending = $true }
  @{ Expression = 'Name'; Ascending = $true }
)

Get-ChildItem |
  Sort-Object $order |
  Format-Table LastWriteTime, Name
```