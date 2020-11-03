---
description: PowerShell でワイルドカード文字を使用する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 3/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wildcards?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Wildcards
ms.openlocfilehash: 4778de5022f35f354e7783cedc5019198d11604b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223960"
---
# <a name="about-wildcards"></a><span data-ttu-id="e317c-104">ワイルドカードについて</span><span class="sxs-lookup"><span data-stu-id="e317c-104">About Wildcards</span></span>

## <a name="short-description"></a><span data-ttu-id="e317c-105">概要</span><span class="sxs-lookup"><span data-stu-id="e317c-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="e317c-106">PowerShell でワイルドカード文字を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e317c-106">Describes how to use wildcard characters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="e317c-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="e317c-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="e317c-108">ワイルドカード文字は、1つまたは複数の文字を表します。</span><span class="sxs-lookup"><span data-stu-id="e317c-108">Wildcard characters represent one or many characters.</span></span> <span data-ttu-id="e317c-109">これらのコマンドを使用して、コマンドで単語パターンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e317c-109">You can use them to create word patterns in commands.</span></span> <span data-ttu-id="e317c-110">たとえば、ディレクトリ内のファイル名拡張子を持つすべてのファイルを取得するには、次のように `C:\Techdocs` `.ppt` 入力します。</span><span class="sxs-lookup"><span data-stu-id="e317c-110">For example, to get all the files in the `C:\Techdocs` directory with a `.ppt` file name extension, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\*.ppt
```

<span data-ttu-id="e317c-111">この場合、アスタリスク ( `*` ) ワイルドカード文字は、ファイル名拡張子の前に表示される任意の文字を表し `.ppt` ます。</span><span class="sxs-lookup"><span data-stu-id="e317c-111">In this case, the asterisk (`*`) wildcard character represents any characters that appear before the `.ppt` file name extension.</span></span>

<span data-ttu-id="e317c-112">PowerShell では、次のワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e317c-112">PowerShell supports the following wildcard characters:</span></span>

|<span data-ttu-id="e317c-113">ワイルドカード</span><span class="sxs-lookup"><span data-stu-id="e317c-113">Wildcard</span></span>|<span data-ttu-id="e317c-114">説明</span><span class="sxs-lookup"><span data-stu-id="e317c-114">Description</span></span>               |<span data-ttu-id="e317c-115">例</span><span class="sxs-lookup"><span data-stu-id="e317c-115">Example</span></span> |<span data-ttu-id="e317c-116">一致する</span><span class="sxs-lookup"><span data-stu-id="e317c-116">Match</span></span>        |<span data-ttu-id="e317c-117">一致なし</span><span class="sxs-lookup"><span data-stu-id="e317c-117">No Match</span></span>|
|--------|--------------------------|--------|-------------|--------|
|\*      |<span data-ttu-id="e317c-118">0個以上の文字と一致します</span><span class="sxs-lookup"><span data-stu-id="e317c-118">Match zero or more characters</span></span> | <span data-ttu-id="e317c-119">ある\*</span><span class="sxs-lookup"><span data-stu-id="e317c-119">a\*</span></span>  | <span data-ttu-id="e317c-120">aA、ag、Apple</span><span class="sxs-lookup"><span data-stu-id="e317c-120">aA, ag, Apple</span></span> | <span data-ttu-id="e317c-121">バナナ</span><span class="sxs-lookup"><span data-stu-id="e317c-121">banana</span></span> |
|<span data-ttu-id="e317c-122">?</span><span class="sxs-lookup"><span data-stu-id="e317c-122">?</span></span>       |<span data-ttu-id="e317c-123">その位置の1文字と一致します</span><span class="sxs-lookup"><span data-stu-id="e317c-123">Match one character in that position</span></span> | <span data-ttu-id="e317c-124">? n</span><span class="sxs-lookup"><span data-stu-id="e317c-124">?n</span></span> | <span data-ttu-id="e317c-125">、in、on</span><span class="sxs-lookup"><span data-stu-id="e317c-125">an, in, on</span></span> | <span data-ttu-id="e317c-126">済み</span><span class="sxs-lookup"><span data-stu-id="e317c-126">ran</span></span> |
|<span data-ttu-id="e317c-127">\[ \]</span><span class="sxs-lookup"><span data-stu-id="e317c-127">\[ \]</span></span>   |<span data-ttu-id="e317c-128">文字の範囲に一致</span><span class="sxs-lookup"><span data-stu-id="e317c-128">Match a range of characters</span></span> | <span data-ttu-id="e317c-129">\[a-l \] ook</span><span class="sxs-lookup"><span data-stu-id="e317c-129">\[a-l\]ook</span></span> | <span data-ttu-id="e317c-130">書籍、クック、ルック</span><span class="sxs-lookup"><span data-stu-id="e317c-130">book, cook, look</span></span> | <span data-ttu-id="e317c-131">所要</span><span class="sxs-lookup"><span data-stu-id="e317c-131">took</span></span> |
|<span data-ttu-id="e317c-132">\[ \]</span><span class="sxs-lookup"><span data-stu-id="e317c-132">\[ \]</span></span>   |<span data-ttu-id="e317c-133">特定の文字に一致</span><span class="sxs-lookup"><span data-stu-id="e317c-133">Match specific characters</span></span> | <span data-ttu-id="e317c-134">\[bc \] ook</span><span class="sxs-lookup"><span data-stu-id="e317c-134">\[bc\]ook</span></span> | <span data-ttu-id="e317c-135">書籍、クック</span><span class="sxs-lookup"><span data-stu-id="e317c-135">book, cook</span></span> | <span data-ttu-id="e317c-136">用</span><span class="sxs-lookup"><span data-stu-id="e317c-136">hook</span></span> |

<span data-ttu-id="e317c-137">同じ単語パターンに複数のワイルドカード文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e317c-137">You can include multiple wildcard characters in the same word pattern.</span></span> <span data-ttu-id="e317c-138">たとえば、名前が **a** ~ **l** で始まるテキストファイルを検索するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e317c-138">For example, to find text files with names that begin with the letters **a** through **l** , type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\[a-l]*.txt
```

<span data-ttu-id="e317c-139">多くのコマンドレットでは、パラメーター値にワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e317c-139">Many cmdlets accept wildcard characters in parameter values.</span></span> <span data-ttu-id="e317c-140">各コマンドレットのヘルプトピックでは、ワイルドカード文字を受け入れるパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e317c-140">The Help topic for each cmdlet describes which parameters accept wildcard characters.</span></span> <span data-ttu-id="e317c-141">ワイルドカード文字を受け入れるパラメーターの場合、その使用では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="e317c-141">For parameters that accept wildcard characters, their use is case-insensitive.</span></span>

<span data-ttu-id="e317c-142">コマンドやスクリプトブロックでワイルドカード文字を使用すると、プロパティ値を表す単語パターンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e317c-142">You can use wildcard characters in commands and script blocks, such as to create a word pattern that represents property values.</span></span> <span data-ttu-id="e317c-143">たとえば、次のコマンドは、 **ServiceType** プロパティ値に **Interactive** が含まれているサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e317c-143">For example, the following command gets services in which the **ServiceType** property value includes **Interactive**.</span></span>

```powershell
Get-Service | Where-Object {$_.ServiceType -Like "*Interactive*"}
```

<span data-ttu-id="e317c-144">次の例では、 `If` ステートメントに、ワイルドカード文字を使用してプロパティ値を検索する条件が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e317c-144">In the following example, the `If` statement includes a condition that uses wildcard characters to find property values.</span></span> <span data-ttu-id="e317c-145">復元ポイントの **説明** に **PowerShell** が含まれている場合、コマンドにより、復元ポイントの "バックアップ **後の時間** " プロパティの値がログファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="e317c-145">If the restore point's **Description** includes **PowerShell** , the command adds the value of the restore point's **CreationTime** property to a log file.</span></span>

```powershell
$p = Get-ComputerRestorePoint
foreach ($point in $p) {
  if ($point.description -like "*PowerShell*") {
    Add-Content -Path C:\TechDocs\RestoreLog.txt "$($point.CreationTime)"
  }
}
```

## <a name="see-also"></a><span data-ttu-id="e317c-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="e317c-146">SEE ALSO</span></span>

[<span data-ttu-id="e317c-147">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="e317c-147">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="e317c-148">about_If</span><span class="sxs-lookup"><span data-stu-id="e317c-148">about_If</span></span>](about_If.md)

[<span data-ttu-id="e317c-149">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="e317c-149">about_Script_Blocks</span></span>](about_Script_Blocks.md)

