---
description: PowerShell でワイルドカード文字を使用する方法について説明します。
Locale: en-US
ms.date: 02/13/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wildcards?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Wildcards
ms.openlocfilehash: 189bff70783b9277f242e8c4ca1c227ae68bae62
ms.sourcegitcommit: 9777152e026c47ba8d319593051416054cb62246
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2021
ms.locfileid: "100529959"
---
# <a name="about-wildcards"></a><span data-ttu-id="79e98-103">ワイルドカードについて</span><span class="sxs-lookup"><span data-stu-id="79e98-103">About Wildcards</span></span>

## <a name="short-description"></a><span data-ttu-id="79e98-104">概要</span><span class="sxs-lookup"><span data-stu-id="79e98-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="79e98-105">PowerShell でワイルドカード文字を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="79e98-105">Describes how to use wildcard characters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="79e98-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="79e98-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="79e98-107">ワイルドカード文字は、1つまたは複数の文字を表します。</span><span class="sxs-lookup"><span data-stu-id="79e98-107">Wildcard characters represent one or many characters.</span></span> <span data-ttu-id="79e98-108">これらのコマンドを使用して、コマンドで単語パターンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="79e98-108">You can use them to create word patterns in commands.</span></span> <span data-ttu-id="79e98-109">ワイルドカード式は、 `-like` 演算子またはワイルドカードを受け入れる任意のパラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="79e98-109">Wildcard expressions are used with the `-like` operator or with any parameter that accepts wildcards.</span></span>

<span data-ttu-id="79e98-110">たとえば、ディレクトリ内のすべてのファイルを `C:\Techdocs` ファイル名拡張子と照合するには、次のように `.ppt` 入力します。</span><span class="sxs-lookup"><span data-stu-id="79e98-110">For example, to match all the files in the `C:\Techdocs` directory with a `.ppt` file name extension, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\*.ppt
```

<span data-ttu-id="79e98-111">この場合、アスタリスク ( `*` ) ワイルドカード文字は、ファイル名拡張子の前に表示される任意の文字を表し `.ppt` ます。</span><span class="sxs-lookup"><span data-stu-id="79e98-111">In this case, the asterisk (`*`) wildcard character represents any characters that appear before the `.ppt` file name extension.</span></span>

<span data-ttu-id="79e98-112">ワイルドカード式は、正規表現よりも簡単です。</span><span class="sxs-lookup"><span data-stu-id="79e98-112">Wildcard expressions are simpler than regular expressions.</span></span> <span data-ttu-id="79e98-113">詳細については、「 [about_Regular_Expressions](./about_Regular_Expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79e98-113">For more information, see [about_Regular_Expressions](./about_Regular_Expressions.md).</span></span>

<span data-ttu-id="79e98-114">PowerShell では、次のワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="79e98-114">PowerShell supports the following wildcard characters:</span></span>

|<span data-ttu-id="79e98-115">ワイルドカード</span><span class="sxs-lookup"><span data-stu-id="79e98-115">Wildcard</span></span>|<span data-ttu-id="79e98-116">説明</span><span class="sxs-lookup"><span data-stu-id="79e98-116">Description</span></span>               |<span data-ttu-id="79e98-117">例</span><span class="sxs-lookup"><span data-stu-id="79e98-117">Example</span></span> |<span data-ttu-id="79e98-118">一致したもの</span><span class="sxs-lookup"><span data-stu-id="79e98-118">Match</span></span>        |<span data-ttu-id="79e98-119">一致なし</span><span class="sxs-lookup"><span data-stu-id="79e98-119">No Match</span></span>|
|--------|--------------------------|--------|-------------|--------|
|\*      |<span data-ttu-id="79e98-120">0個以上の文字と一致します</span><span class="sxs-lookup"><span data-stu-id="79e98-120">Match zero or more characters</span></span> | <span data-ttu-id="79e98-121">ある\*</span><span class="sxs-lookup"><span data-stu-id="79e98-121">a\*</span></span>  | <span data-ttu-id="79e98-122">aA、ag、Apple</span><span class="sxs-lookup"><span data-stu-id="79e98-122">aA, ag, Apple</span></span> | <span data-ttu-id="79e98-123">バナナ</span><span class="sxs-lookup"><span data-stu-id="79e98-123">banana</span></span> |
|<span data-ttu-id="79e98-124">?</span><span class="sxs-lookup"><span data-stu-id="79e98-124">?</span></span>       |<span data-ttu-id="79e98-125">その位置の1文字と一致します</span><span class="sxs-lookup"><span data-stu-id="79e98-125">Match one character in that position</span></span> | <span data-ttu-id="79e98-126">? n</span><span class="sxs-lookup"><span data-stu-id="79e98-126">?n</span></span> | <span data-ttu-id="79e98-127">、in、on</span><span class="sxs-lookup"><span data-stu-id="79e98-127">an, in, on</span></span> | <span data-ttu-id="79e98-128">済み</span><span class="sxs-lookup"><span data-stu-id="79e98-128">ran</span></span> |
|<span data-ttu-id="79e98-129">\[ \]</span><span class="sxs-lookup"><span data-stu-id="79e98-129">\[ \]</span></span>   |<span data-ttu-id="79e98-130">文字の範囲に一致</span><span class="sxs-lookup"><span data-stu-id="79e98-130">Match a range of characters</span></span> | <span data-ttu-id="79e98-131">\[a-l \] ook</span><span class="sxs-lookup"><span data-stu-id="79e98-131">\[a-l\]ook</span></span> | <span data-ttu-id="79e98-132">書籍、クック、ルック</span><span class="sxs-lookup"><span data-stu-id="79e98-132">book, cook, look</span></span> | <span data-ttu-id="79e98-133">所要</span><span class="sxs-lookup"><span data-stu-id="79e98-133">took</span></span> |
|<span data-ttu-id="79e98-134">\[ \]</span><span class="sxs-lookup"><span data-stu-id="79e98-134">\[ \]</span></span>   |<span data-ttu-id="79e98-135">特定の文字に一致</span><span class="sxs-lookup"><span data-stu-id="79e98-135">Match specific characters</span></span> | <span data-ttu-id="79e98-136">\[bc \] ook</span><span class="sxs-lookup"><span data-stu-id="79e98-136">\[bc\]ook</span></span> | <span data-ttu-id="79e98-137">書籍、クック</span><span class="sxs-lookup"><span data-stu-id="79e98-137">book, cook</span></span> | <span data-ttu-id="79e98-138">用</span><span class="sxs-lookup"><span data-stu-id="79e98-138">hook</span></span> |

<span data-ttu-id="79e98-139">同じ単語パターンに複数のワイルドカード文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="79e98-139">You can include multiple wildcard characters in the same word pattern.</span></span> <span data-ttu-id="79e98-140">たとえば、名前が **a** ~ **l** で始まるテキストファイルを検索するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="79e98-140">For example, to find text files with names that begin with the letters **a** through **l**, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\[a-l]*.txt
```

<span data-ttu-id="79e98-141">多くのコマンドレットでは、パラメーター値にワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="79e98-141">Many cmdlets accept wildcard characters in parameter values.</span></span> <span data-ttu-id="79e98-142">各コマンドレットのヘルプトピックでは、ワイルドカード文字を受け入れるパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="79e98-142">The Help topic for each cmdlet describes which parameters accept wildcard characters.</span></span> <span data-ttu-id="79e98-143">ワイルドカード文字を受け入れるパラメーターの場合、その使用では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="79e98-143">For parameters that accept wildcard characters, their use is case-insensitive.</span></span>

<span data-ttu-id="79e98-144">コマンドやスクリプトブロックでワイルドカード文字を使用すると、プロパティ値を表す単語パターンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="79e98-144">You can use wildcard characters in commands and script blocks, such as to create a word pattern that represents property values.</span></span> <span data-ttu-id="79e98-145">たとえば、次のコマンドは、 **ServiceType** プロパティ値に **Interactive** が含まれているサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="79e98-145">For example, the following command gets services in which the **ServiceType** property value includes **Interactive**.</span></span>

```powershell
Get-Service | Where-Object {$_.ServiceType -Like "*Interactive*"}
```

<span data-ttu-id="79e98-146">次の例では、 `If` ステートメントに、ワイルドカード文字を使用してプロパティ値を検索する条件が含まれています。</span><span class="sxs-lookup"><span data-stu-id="79e98-146">In the following example, the `If` statement includes a condition that uses wildcard characters to find property values.</span></span> <span data-ttu-id="79e98-147">復元ポイントの **説明** に **PowerShell** が含まれている場合、コマンドにより、復元ポイントの "バックアップ **後の時間** " プロパティの値がログファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="79e98-147">If the restore point's **Description** includes **PowerShell**, the command adds the value of the restore point's **CreationTime** property to a log file.</span></span>

```powershell
$p = Get-ComputerRestorePoint
foreach ($point in $p) {
  if ($point.description -like "*PowerShell*") {
    Add-Content -Path C:\TechDocs\RestoreLog.txt "$($point.CreationTime)"
  }
}
```

## <a name="see-also"></a><span data-ttu-id="79e98-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="79e98-148">SEE ALSO</span></span>

[<span data-ttu-id="79e98-149">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="79e98-149">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="79e98-150">about_If</span><span class="sxs-lookup"><span data-stu-id="79e98-150">about_If</span></span>](about_If.md)

[<span data-ttu-id="79e98-151">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="79e98-151">about_Script_Blocks</span></span>](about_Script_Blocks.md)
