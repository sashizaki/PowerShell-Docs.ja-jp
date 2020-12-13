---
ms.date: 08/26/2019
ms.topic: reference
title: コマンドレット パラメーターでワイルドカード文字をサポートする
description: コマンドレット パラメーターでワイルドカード文字をサポートする
ms.openlocfilehash: 06693c62cd2613050bdeb9d6b12ad6e9597a9894
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646398"
---
# <a name="supporting-wildcard-characters-in-cmdlet-parameters"></a><span data-ttu-id="d9979-103">コマンドレット パラメーターでワイルドカード文字をサポートする</span><span class="sxs-lookup"><span data-stu-id="d9979-103">Supporting Wildcard Characters in Cmdlet Parameters</span></span>

<span data-ttu-id="d9979-104">多くの場合、1つのリソースに対してではなく、リソースのグループに対して実行するようにコマンドレットを設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9979-104">Often, you will have to design a cmdlet to run against a group of resources rather than against a single resource.</span></span> <span data-ttu-id="d9979-105">たとえば、コマンドレットでは、同じ名前または拡張子を持つデータストア内のすべてのファイルを検索することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9979-105">For example, a cmdlet might need to locate all the files in a data store that have the same name or extension.</span></span> <span data-ttu-id="d9979-106">リソースグループに対して実行されるコマンドレットを設計するときは、ワイルドカード文字のサポートを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9979-106">You must provide support for wildcard characters when you design a cmdlet that will be run against a group of resources.</span></span>

> [!NOTE]
> <span data-ttu-id="d9979-107">ワイルドカード文字の使用は、 *グロビング* と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="d9979-107">Using wildcard characters is sometimes referred to as *globbing*.</span></span>

## <a name="windows-powershell-cmdlets-that-use-wildcards"></a><span data-ttu-id="d9979-108">ワイルドカードを使用する Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="d9979-108">Windows PowerShell Cmdlets That Use Wildcards</span></span>

 <span data-ttu-id="d9979-109">多くの Windows PowerShell コマンドレットは、パラメーター値としてワイルドカード文字をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d9979-109">Many Windows PowerShell cmdlets support wildcard characters for their parameter values.</span></span> <span data-ttu-id="d9979-110">たとえば、パラメーターまたはパラメーターを持つほとんどすべてのコマンドレットは、 `Name` `Path` これらのパラメーターに対してワイルドカード文字をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d9979-110">For example, almost every cmdlet that has a `Name` or `Path` parameter supports wildcard characters for these parameters.</span></span> <span data-ttu-id="d9979-111">(パラメーターを持つほとんどのコマンドレットには `Path` 、 `LiteralPath` ワイルドカード文字をサポートしないパラメーターもあります)。次のコマンドは、名前に Get 動詞が含まれている現在のセッションのすべてのコマンドレットを返すために、ワイルドカード文字を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d9979-111">(Although most cmdlets that have a `Path` parameter also have a `LiteralPath` parameter that does not support wildcard characters.) The following command shows how a wildcard character is used to return all the cmdlets in the current session whose name contains the Get verb.</span></span>

 `Get-Command get-*`

## <a name="supported-wildcard-characters"></a><span data-ttu-id="d9979-112">サポートされているワイルドカード文字</span><span class="sxs-lookup"><span data-stu-id="d9979-112">Supported Wildcard Characters</span></span>

<span data-ttu-id="d9979-113">Windows PowerShell では、次のワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d9979-113">Windows PowerShell supports the following wildcard characters.</span></span>

| <span data-ttu-id="d9979-114">ワイルドカード</span><span class="sxs-lookup"><span data-stu-id="d9979-114">Wildcard</span></span> |                             <span data-ttu-id="d9979-115">説明</span><span class="sxs-lookup"><span data-stu-id="d9979-115">Description</span></span>                             |  <span data-ttu-id="d9979-116">例</span><span class="sxs-lookup"><span data-stu-id="d9979-116">Example</span></span>   |     <span data-ttu-id="d9979-117">［一致する］</span><span class="sxs-lookup"><span data-stu-id="d9979-117">Matches</span></span>      | <span data-ttu-id="d9979-118">［次の値に一致しない］</span><span class="sxs-lookup"><span data-stu-id="d9979-118">Does not match</span></span> |
| -------- | ------------------------------------------------------------------- | ---------- | ---------------- | -------------- |
| *        | <span data-ttu-id="d9979-119">指定された位置を開始位置として、0個以上の文字と一致します</span><span class="sxs-lookup"><span data-stu-id="d9979-119">Matches zero or more characters, starting at the specified position</span></span> | `a*`       | <span data-ttu-id="d9979-120">A、ag、Apple</span><span class="sxs-lookup"><span data-stu-id="d9979-120">A, ag, Apple</span></span>     |                |
| <span data-ttu-id="d9979-121">?</span><span class="sxs-lookup"><span data-stu-id="d9979-121">?</span></span>        | <span data-ttu-id="d9979-122">指定した位置にある任意の文字と一致します</span><span class="sxs-lookup"><span data-stu-id="d9979-122">Matches any character at the specified position</span></span>                     | `?n`       | <span data-ttu-id="d9979-123">、In、on</span><span class="sxs-lookup"><span data-stu-id="d9979-123">An, in, on</span></span>       | <span data-ttu-id="d9979-124">済み</span><span class="sxs-lookup"><span data-stu-id="d9979-124">ran</span></span>            |
| <span data-ttu-id="d9979-125">[ ]</span><span class="sxs-lookup"><span data-stu-id="d9979-125">[ ]</span></span>      | <span data-ttu-id="d9979-126">文字の範囲に一致します。</span><span class="sxs-lookup"><span data-stu-id="d9979-126">Matches a range of characters</span></span>                                       | `[a-l]ook` | <span data-ttu-id="d9979-127">書籍、クック、ルック</span><span class="sxs-lookup"><span data-stu-id="d9979-127">book, cook, look</span></span> | <span data-ttu-id="d9979-128">nook、所要時間</span><span class="sxs-lookup"><span data-stu-id="d9979-128">nook, took</span></span>     |
| <span data-ttu-id="d9979-129">[ ]</span><span class="sxs-lookup"><span data-stu-id="d9979-129">[ ]</span></span>      | <span data-ttu-id="d9979-130">指定した文字と一致します</span><span class="sxs-lookup"><span data-stu-id="d9979-130">Matches the specified characters</span></span>                                    | `[bn]ook`  | <span data-ttu-id="d9979-131">book、nook</span><span class="sxs-lookup"><span data-stu-id="d9979-131">book, nook</span></span>       | <span data-ttu-id="d9979-132">クック、外観</span><span class="sxs-lookup"><span data-stu-id="d9979-132">cook, look</span></span>     |

<span data-ttu-id="d9979-133">ワイルドカード文字をサポートするコマンドレットを設計する場合は、ワイルドカード文字の組み合わせを許可します。</span><span class="sxs-lookup"><span data-stu-id="d9979-133">When you design cmdlets that support wildcard characters, allow for combinations of wildcard characters.</span></span> <span data-ttu-id="d9979-134">たとえば、次のコマンドは、コマンドレットを使用して、 `Get-ChildItem` c:\ の docs フォルダー内にあり、"a" ~ "l" の文字で始まるすべての .txt ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="d9979-134">For example, the following command uses the `Get-ChildItem` cmdlet to retrieve all the .txt files that are in the c:\Techdocs folder and that begin with the letters "a" through "l."</span></span>

`Get-ChildItem c:\techdocs\[a-l]\*.txt`

<span data-ttu-id="d9979-135">前のコマンドでは、範囲のワイルドカードを使用して、 `[a-l]` ファイル名の先頭文字が "a" ~ "l" であることを指定します。また、 `*` ワイルドカード文字を、ファイル名の最初の文字と **.txt** 拡張子の間にある任意の文字のプレースホルダーとして使用します。</span><span class="sxs-lookup"><span data-stu-id="d9979-135">The previous command uses the range wildcard `[a-l]` to specify that the file name should begin with the characters "a" through "l" and uses the `*` wildcard character as a placeholder for any characters between the first letter of the filename and the **.txt** extension.</span></span>

<span data-ttu-id="d9979-136">次の例では、文字 "d" を除くが、"a" ~ "f" の他のすべての文字を含む、範囲のワイルドカードパターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9979-136">The following example uses a range wildcard pattern that excludes the letter "d" but includes all the other letters from "a" through "f."</span></span>

`Get-ChildItem c:\techdocs\[a-cef]\*.txt`

## <a name="handling-literal-characters-in-wildcard-patterns"></a><span data-ttu-id="d9979-137">ワイルドカードパターンでのリテラル文字の処理</span><span class="sxs-lookup"><span data-stu-id="d9979-137">Handling Literal Characters in Wildcard Patterns</span></span>

<span data-ttu-id="d9979-138">指定したワイルドカードパターンに、ワイルドカード文字として interpretted ないリテラル文字が含まれている場合は、バックティック文字 ( `` ` `` ) をエスケープ文字として使用します。</span><span class="sxs-lookup"><span data-stu-id="d9979-138">If the wildcard pattern you specify contains literal characters that should not be interpretted as wildcard characters, use the backtick character (`` ` ``) as an escape character.</span></span> <span data-ttu-id="d9979-139">PowerShell API のリテラル文字を指定する場合は、1つのバックティックを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9979-139">When you specify literal characters int the PowerShell API, use a single backtick.</span></span> <span data-ttu-id="d9979-140">PowerShell コマンドプロンプトでリテラル文字を指定する場合は、2つのバックティックを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9979-140">When you specify literal characters at the PowerShell command prompt, use two backticks.</span></span>

<span data-ttu-id="d9979-141">たとえば、次のパターンには、文字どおりに実行する必要がある2つの角かっこが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d9979-141">For example, the following pattern contains two brackets that must be taken literally.</span></span>

<span data-ttu-id="d9979-142">PowerShell API で使用する場合は、次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="d9979-142">When used in the PowerShell API use:</span></span>

- <span data-ttu-id="d9979-143">"John Smith \` [\* ']"</span><span class="sxs-lookup"><span data-stu-id="d9979-143">"John Smith \`[\*\`]"</span></span>

<span data-ttu-id="d9979-144">PowerShell コマンドプロンプトから使用する場合:</span><span class="sxs-lookup"><span data-stu-id="d9979-144">When used from the PowerShell command prompt:</span></span>

- <span data-ttu-id="d9979-145">"John Smith \` \` [\* \` ']"</span><span class="sxs-lookup"><span data-stu-id="d9979-145">"John Smith \`\`[\*\`\`]"</span></span>

<span data-ttu-id="d9979-146">このパターンは、"John Smith [Marketing]" または "John Smith [Development]" と一致します。</span><span class="sxs-lookup"><span data-stu-id="d9979-146">This pattern matches "John Smith [Marketing]" or "John Smith [Development]".</span></span> <span data-ttu-id="d9979-147">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d9979-147">For example:</span></span>

```
PS> "John Smith [Marketing]" -like "John Smith ``[*``]"
True

PS> "John Smith [Development]" -like "John Smith ``[*``]"
True
```

## <a name="cmdlet-output-and-wildcard-characters"></a><span data-ttu-id="d9979-148">コマンドレットの出力とワイルドカード文字</span><span class="sxs-lookup"><span data-stu-id="d9979-148">Cmdlet Output and Wildcard Characters</span></span>

<span data-ttu-id="d9979-149">コマンドレットのパラメーターでワイルドカード文字がサポートされている場合、通常、この操作では配列の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d9979-149">When cmdlet parameters support wildcard characters, the operation usually generates an array output.</span></span>
<span data-ttu-id="d9979-150">場合によっては、ユーザーが1つの項目のみを使用する可能性があるため、配列の出力をサポートすることは意味がありません。</span><span class="sxs-lookup"><span data-stu-id="d9979-150">Occasionally, it makes no sense to support an array output because the user might use only a single item.</span></span> <span data-ttu-id="d9979-151">たとえば、 `Set-Location` コマンドレットでは、ユーザーが1つの場所のみを設定するため、配列の出力はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d9979-151">For example, the `Set-Location` cmdlet does not support array output because the user sets only a single location.</span></span> <span data-ttu-id="d9979-152">このインスタンスでは、コマンドレットはワイルドカード文字を引き続きサポートしますが、1つの場所を強制的に解決します。</span><span class="sxs-lookup"><span data-stu-id="d9979-152">In this instance, the cmdlet still supports wildcard characters, but it forces resolution to a single location.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9979-153">参照</span><span class="sxs-lookup"><span data-stu-id="d9979-153">See Also</span></span>

[<span data-ttu-id="d9979-154">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="d9979-154">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="d9979-155">WildcardPattern クラス</span><span class="sxs-lookup"><span data-stu-id="d9979-155">WildcardPattern Class</span></span>](/dotnet/api/system.management.automation.wildcardpattern)
