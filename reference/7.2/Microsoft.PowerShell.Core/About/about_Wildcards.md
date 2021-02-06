---
description: PowerShell でワイルドカード文字を使用する方法について説明します。
Locale: en-US
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wildcards?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Wildcards
ms.openlocfilehash: b5f13fdbfbc24e19e5ad0b1cd6ecc1b99f68914f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599718"
---
# <a name="about-wildcards"></a><span data-ttu-id="a37ad-103">ワイルドカードについて</span><span class="sxs-lookup"><span data-stu-id="a37ad-103">About Wildcards</span></span>

## <a name="short-description"></a><span data-ttu-id="a37ad-104">概要</span><span class="sxs-lookup"><span data-stu-id="a37ad-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="a37ad-105">PowerShell でワイルドカード文字を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a37ad-105">Describes how to use wildcard characters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="a37ad-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="a37ad-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="a37ad-107">ワイルドカード文字は、1つまたは複数の文字を表します。</span><span class="sxs-lookup"><span data-stu-id="a37ad-107">Wildcard characters represent one or many characters.</span></span> <span data-ttu-id="a37ad-108">これらのコマンドを使用して、コマンドで単語パターンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a37ad-108">You can use them to create word patterns in commands.</span></span> <span data-ttu-id="a37ad-109">たとえば、ディレクトリ内のファイル名拡張子を持つすべてのファイルを取得するには、次のように `C:\Techdocs` `.ppt` 入力します。</span><span class="sxs-lookup"><span data-stu-id="a37ad-109">For example, to get all the files in the `C:\Techdocs` directory with a `.ppt` file name extension, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\*.ppt
```

<span data-ttu-id="a37ad-110">この場合、アスタリスク ( `*` ) ワイルドカード文字は、ファイル名拡張子の前に表示される任意の文字を表し `.ppt` ます。</span><span class="sxs-lookup"><span data-stu-id="a37ad-110">In this case, the asterisk (`*`) wildcard character represents any characters that appear before the `.ppt` file name extension.</span></span>

<span data-ttu-id="a37ad-111">PowerShell では、次のワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a37ad-111">PowerShell supports the following wildcard characters:</span></span>

|<span data-ttu-id="a37ad-112">ワイルドカード</span><span class="sxs-lookup"><span data-stu-id="a37ad-112">Wildcard</span></span>|<span data-ttu-id="a37ad-113">説明</span><span class="sxs-lookup"><span data-stu-id="a37ad-113">Description</span></span>               |<span data-ttu-id="a37ad-114">例</span><span class="sxs-lookup"><span data-stu-id="a37ad-114">Example</span></span> |<span data-ttu-id="a37ad-115">一致したもの</span><span class="sxs-lookup"><span data-stu-id="a37ad-115">Match</span></span>        |<span data-ttu-id="a37ad-116">一致なし</span><span class="sxs-lookup"><span data-stu-id="a37ad-116">No Match</span></span>|
|--------|--------------------------|--------|-------------|--------|
|\*      |<span data-ttu-id="a37ad-117">0個以上の文字と一致します</span><span class="sxs-lookup"><span data-stu-id="a37ad-117">Match zero or more characters</span></span> | <span data-ttu-id="a37ad-118">ある\*</span><span class="sxs-lookup"><span data-stu-id="a37ad-118">a\*</span></span>  | <span data-ttu-id="a37ad-119">aA、ag、Apple</span><span class="sxs-lookup"><span data-stu-id="a37ad-119">aA, ag, Apple</span></span> | <span data-ttu-id="a37ad-120">バナナ</span><span class="sxs-lookup"><span data-stu-id="a37ad-120">banana</span></span> |
|<span data-ttu-id="a37ad-121">?</span><span class="sxs-lookup"><span data-stu-id="a37ad-121">?</span></span>       |<span data-ttu-id="a37ad-122">その位置の1文字と一致します</span><span class="sxs-lookup"><span data-stu-id="a37ad-122">Match one character in that position</span></span> | <span data-ttu-id="a37ad-123">? n</span><span class="sxs-lookup"><span data-stu-id="a37ad-123">?n</span></span> | <span data-ttu-id="a37ad-124">、in、on</span><span class="sxs-lookup"><span data-stu-id="a37ad-124">an, in, on</span></span> | <span data-ttu-id="a37ad-125">済み</span><span class="sxs-lookup"><span data-stu-id="a37ad-125">ran</span></span> |
|<span data-ttu-id="a37ad-126">\[ \]</span><span class="sxs-lookup"><span data-stu-id="a37ad-126">\[ \]</span></span>   |<span data-ttu-id="a37ad-127">文字の範囲に一致</span><span class="sxs-lookup"><span data-stu-id="a37ad-127">Match a range of characters</span></span> | <span data-ttu-id="a37ad-128">\[a-l \] ook</span><span class="sxs-lookup"><span data-stu-id="a37ad-128">\[a-l\]ook</span></span> | <span data-ttu-id="a37ad-129">書籍、クック、ルック</span><span class="sxs-lookup"><span data-stu-id="a37ad-129">book, cook, look</span></span> | <span data-ttu-id="a37ad-130">所要</span><span class="sxs-lookup"><span data-stu-id="a37ad-130">took</span></span> |
|<span data-ttu-id="a37ad-131">\[ \]</span><span class="sxs-lookup"><span data-stu-id="a37ad-131">\[ \]</span></span>   |<span data-ttu-id="a37ad-132">特定の文字に一致</span><span class="sxs-lookup"><span data-stu-id="a37ad-132">Match specific characters</span></span> | <span data-ttu-id="a37ad-133">\[bc \] ook</span><span class="sxs-lookup"><span data-stu-id="a37ad-133">\[bc\]ook</span></span> | <span data-ttu-id="a37ad-134">書籍、クック</span><span class="sxs-lookup"><span data-stu-id="a37ad-134">book, cook</span></span> | <span data-ttu-id="a37ad-135">用</span><span class="sxs-lookup"><span data-stu-id="a37ad-135">hook</span></span> |

<span data-ttu-id="a37ad-136">同じ単語パターンに複数のワイルドカード文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a37ad-136">You can include multiple wildcard characters in the same word pattern.</span></span> <span data-ttu-id="a37ad-137">たとえば、名前が **a** ~ **l** で始まるテキストファイルを検索するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a37ad-137">For example, to find text files with names that begin with the letters **a** through **l**, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\[a-l]*.txt
```

<span data-ttu-id="a37ad-138">多くのコマンドレットでは、パラメーター値にワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a37ad-138">Many cmdlets accept wildcard characters in parameter values.</span></span> <span data-ttu-id="a37ad-139">各コマンドレットのヘルプトピックでは、ワイルドカード文字を受け入れるパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a37ad-139">The Help topic for each cmdlet describes which parameters accept wildcard characters.</span></span> <span data-ttu-id="a37ad-140">ワイルドカード文字を受け入れるパラメーターの場合、その使用では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="a37ad-140">For parameters that accept wildcard characters, their use is case-insensitive.</span></span>

<span data-ttu-id="a37ad-141">コマンドやスクリプトブロックでワイルドカード文字を使用すると、プロパティ値を表す単語パターンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a37ad-141">You can use wildcard characters in commands and script blocks, such as to create a word pattern that represents property values.</span></span> <span data-ttu-id="a37ad-142">たとえば、次のコマンドは、 **ServiceType** プロパティ値に **Interactive** が含まれているサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a37ad-142">For example, the following command gets services in which the **ServiceType** property value includes **Interactive**.</span></span>

```powershell
Get-Service | Where-Object {$_.ServiceType -Like "*Interactive*"}
```

<span data-ttu-id="a37ad-143">次の例では、 `If` ステートメントに、ワイルドカード文字を使用してプロパティ値を検索する条件が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a37ad-143">In the following example, the `If` statement includes a condition that uses wildcard characters to find property values.</span></span> <span data-ttu-id="a37ad-144">復元ポイントの **説明** に **PowerShell** が含まれている場合、コマンドにより、復元ポイントの "バックアップ **後の時間** " プロパティの値がログファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a37ad-144">If the restore point's **Description** includes **PowerShell**, the command adds the value of the restore point's **CreationTime** property to a log file.</span></span>

```powershell
$p = Get-ComputerRestorePoint
foreach ($point in $p) {
  if ($point.description -like "*PowerShell*") {
    Add-Content -Path C:\TechDocs\RestoreLog.txt "$($point.CreationTime)"
  }
}
```

## <a name="see-also"></a><span data-ttu-id="a37ad-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="a37ad-145">SEE ALSO</span></span>

[<span data-ttu-id="a37ad-146">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="a37ad-146">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="a37ad-147">about_If</span><span class="sxs-lookup"><span data-stu-id="a37ad-147">about_If</span></span>](about_If.md)

[<span data-ttu-id="a37ad-148">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="a37ad-148">about_Script_Blocks</span></span>](about_Script_Blocks.md)

