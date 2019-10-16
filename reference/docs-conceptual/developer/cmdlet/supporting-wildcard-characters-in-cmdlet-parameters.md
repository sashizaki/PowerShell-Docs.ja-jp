---
title: コマンドレット パラメーターでワイルドカード文字をサポートする
ms.custom: ''
ms.date: 08/26/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.openlocfilehash: 19644c5bc186a5554d6b134a67fc7c4d7aa7b64c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365311"
---
# <a name="supporting-wildcard-characters-in-cmdlet-parameters"></a><span data-ttu-id="dc5c5-102">コマンドレット パラメーターでワイルドカード文字をサポートする</span><span class="sxs-lookup"><span data-stu-id="dc5c5-102">Supporting Wildcard Characters in Cmdlet Parameters</span></span>

<span data-ttu-id="dc5c5-103">多くの場合、1つのリソースに対してではなく、リソースのグループに対して実行するようにコマンドレットを設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-103">Often, you will have to design a cmdlet to run against a group of resources rather than against a single resource.</span></span> <span data-ttu-id="dc5c5-104">たとえば、コマンドレットでは、同じ名前または拡張子を持つデータストア内のすべてのファイルを検索することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-104">For example, a cmdlet might need to locate all the files in a data store that have the same name or extension.</span></span> <span data-ttu-id="dc5c5-105">リソースグループに対して実行されるコマンドレットを設計するときは、ワイルドカード文字のサポートを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-105">You must provide support for wildcard characters when you design a cmdlet that will be run against a group of resources.</span></span>

> [!NOTE]
> <span data-ttu-id="dc5c5-106">ワイルドカード文字の使用は、*グロビング*と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-106">Using wildcard characters is sometimes referred to as *globbing*.</span></span>

## <a name="windows-powershell-cmdlets-that-use-wildcards"></a><span data-ttu-id="dc5c5-107">ワイルドカードを使用する Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="dc5c5-107">Windows PowerShell Cmdlets That Use Wildcards</span></span>

 <span data-ttu-id="dc5c5-108">多くの Windows PowerShell コマンドレットは、パラメーター値としてワイルドカード文字をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-108">Many Windows PowerShell cmdlets support wildcard characters for their parameter values.</span></span> <span data-ttu-id="dc5c5-109">たとえば、`Name` または `Path` パラメーターを持つほとんどすべてのコマンドレットは、これらのパラメーターに対してワイルドカード文字をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-109">For example, almost every cmdlet that has a `Name` or `Path` parameter supports wildcard characters for these parameters.</span></span> <span data-ttu-id="dc5c5-110">(@No__t 0 パラメーターを持つほとんどのコマンドレットには、ワイルドカード文字をサポートしない `LiteralPath` パラメーターもあります)。次のコマンドは、名前に Get 動詞が含まれている現在のセッションのすべてのコマンドレットを返すために、ワイルドカード文字を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-110">(Although most cmdlets that have a `Path` parameter also have a `LiteralPath` parameter that does not support wildcard characters.) The following command shows how a wildcard character is used to return all the cmdlets in the current session whose name contains the Get verb.</span></span>

 `Get-Command get-*`

## <a name="supported-wildcard-characters"></a><span data-ttu-id="dc5c5-111">サポートされているワイルドカード文字</span><span class="sxs-lookup"><span data-stu-id="dc5c5-111">Supported Wildcard Characters</span></span>

<span data-ttu-id="dc5c5-112">Windows PowerShell では、次のワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-112">Windows PowerShell supports the following wildcard characters.</span></span>

| <span data-ttu-id="dc5c5-113">ワイルドカード</span><span class="sxs-lookup"><span data-stu-id="dc5c5-113">Wildcard</span></span> |                             <span data-ttu-id="dc5c5-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="dc5c5-114">Description</span></span>                             |  <span data-ttu-id="dc5c5-115">例</span><span class="sxs-lookup"><span data-stu-id="dc5c5-115">Example</span></span>   |     <span data-ttu-id="dc5c5-116">[一致する]</span><span class="sxs-lookup"><span data-stu-id="dc5c5-116">Matches</span></span>      | <span data-ttu-id="dc5c5-117">［次の値に一致しない］</span><span class="sxs-lookup"><span data-stu-id="dc5c5-117">Does not match</span></span> |
| -------- | ------------------------------------------------------------------- | ---------- | ---------------- | -------------- |
| *        | <span data-ttu-id="dc5c5-118">指定された位置を開始位置として、0個以上の文字と一致します</span><span class="sxs-lookup"><span data-stu-id="dc5c5-118">Matches zero or more characters, starting at the specified position</span></span> | `a*`       | <span data-ttu-id="dc5c5-119">A、ag、Apple</span><span class="sxs-lookup"><span data-stu-id="dc5c5-119">A, ag, Apple</span></span>     |                |
| <span data-ttu-id="dc5c5-120">?</span><span class="sxs-lookup"><span data-stu-id="dc5c5-120">?</span></span>        | <span data-ttu-id="dc5c5-121">指定した位置にある任意の文字と一致します</span><span class="sxs-lookup"><span data-stu-id="dc5c5-121">Matches any character at the specified position</span></span>                     | `?n`       | <span data-ttu-id="dc5c5-122">、In、on</span><span class="sxs-lookup"><span data-stu-id="dc5c5-122">An, in, on</span></span>       | <span data-ttu-id="dc5c5-123">済み</span><span class="sxs-lookup"><span data-stu-id="dc5c5-123">ran</span></span>            |
| <span data-ttu-id="dc5c5-124">[ ]</span><span class="sxs-lookup"><span data-stu-id="dc5c5-124">[ ]</span></span>      | <span data-ttu-id="dc5c5-125">文字の範囲に一致します。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-125">Matches a range of characters</span></span>                                       | `[a-l]ook` | <span data-ttu-id="dc5c5-126">書籍、クック、ルック</span><span class="sxs-lookup"><span data-stu-id="dc5c5-126">book, cook, look</span></span> | <span data-ttu-id="dc5c5-127">nook、所要時間</span><span class="sxs-lookup"><span data-stu-id="dc5c5-127">nook, took</span></span>     |
| <span data-ttu-id="dc5c5-128">[ ]</span><span class="sxs-lookup"><span data-stu-id="dc5c5-128">[ ]</span></span>      | <span data-ttu-id="dc5c5-129">指定した文字と一致します</span><span class="sxs-lookup"><span data-stu-id="dc5c5-129">Matches the specified characters</span></span>                                    | `[bn]ook`  | <span data-ttu-id="dc5c5-130">book、nook</span><span class="sxs-lookup"><span data-stu-id="dc5c5-130">book, nook</span></span>       | <span data-ttu-id="dc5c5-131">クック、外観</span><span class="sxs-lookup"><span data-stu-id="dc5c5-131">cook, look</span></span>     |

<span data-ttu-id="dc5c5-132">ワイルドカード文字をサポートするコマンドレットを設計する場合は、ワイルドカード文字の組み合わせを許可します。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-132">When you design cmdlets that support wildcard characters, allow for combinations of wildcard characters.</span></span> <span data-ttu-id="dc5c5-133">たとえば、次のコマンドでは、`Get-ChildItem` のコマンドレットを使用して、C:\ 文書フォルダー内にあり、"a" ~ "l" の文字で始まるすべての .txt ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-133">For example, the following command uses the `Get-ChildItem` cmdlet to retrieve all the .txt files that are in the c:\Techdocs folder and that begin with the letters "a" through "l."</span></span>

`Get-ChildItem c:\techdocs\[a-l]\*.txt`

<span data-ttu-id="dc5c5-134">前のコマンドでは、範囲のワイルドカード `[a-l]` を使用して、ファイル名の先頭文字が "a" ~ "l" であることを指定し、`*` のワイルドカード文字を、ファイル名の最初の文字と .txt の間の任意の文字のプレースホルダーとして使用し**ます。** 拡張機能。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-134">The previous command uses the range wildcard `[a-l]` to specify that the file name should begin with the characters "a" through "l" and uses the `*` wildcard character as a placeholder for any characters between the first letter of the filename and the **.txt** extension.</span></span>

<span data-ttu-id="dc5c5-135">次の例では、文字 "d" を除くが、"a" ~ "f" の他のすべての文字を含む、範囲のワイルドカードパターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-135">The following example uses a range wildcard pattern that excludes the letter "d" but includes all the other letters from "a" through "f."</span></span>

`Get-ChildItem c:\techdocs\[a-cef]\*.txt`

## <a name="handling-literal-characters-in-wildcard-patterns"></a><span data-ttu-id="dc5c5-136">ワイルドカードパターンでのリテラル文字の処理</span><span class="sxs-lookup"><span data-stu-id="dc5c5-136">Handling Literal Characters in Wildcard Patterns</span></span>

<span data-ttu-id="dc5c5-137">指定したワイルドカードパターンに、ワイルドカード文字として interpretted ないリテラル文字が含まれている場合は、エスケープ文字としてバックティック文字 (`` ` ``) を使用します。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-137">If the wildcard pattern you specify contains literal characters that should not be interpretted as wildcard characters, use the backtick character (`` ` ``) as an escape character.</span></span> <span data-ttu-id="dc5c5-138">PowerShell API のリテラル文字を指定する場合は、1つのバックティックを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-138">When you specify literal characters int the PowerShell API, use a single backtick.</span></span> <span data-ttu-id="dc5c5-139">PowerShell コマンドプロンプトでリテラル文字を指定する場合は、2つのバックティックを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-139">When you specify literal characters at the PowerShell command prompt, use two backticks.</span></span>

<span data-ttu-id="dc5c5-140">たとえば、次のパターンには、文字どおりに実行する必要がある2つの角かっこが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-140">For example, the following pattern contains two brackets that must be taken literally.</span></span>

<span data-ttu-id="dc5c5-141">PowerShell API で使用する場合は、次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-141">When used in the PowerShell API use:</span></span>

- <span data-ttu-id="dc5c5-142">"John Smith \` [\* ']"</span><span class="sxs-lookup"><span data-stu-id="dc5c5-142">"John Smith \`[\*\`]"</span></span>

<span data-ttu-id="dc5c5-143">PowerShell コマンドプロンプトから使用する場合:</span><span class="sxs-lookup"><span data-stu-id="dc5c5-143">When used from the PowerShell command prompt:</span></span>

- <span data-ttu-id="dc5c5-144">"John Smith \` @ no__t [\* \` ']"</span><span class="sxs-lookup"><span data-stu-id="dc5c5-144">"John Smith \`\`[\*\`\`]"</span></span>

<span data-ttu-id="dc5c5-145">このパターンは、"John Smith [Marketing]" または "John Smith [Development]" と一致します。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-145">This pattern matches "John Smith [Marketing]" or "John Smith [Development]".</span></span> <span data-ttu-id="dc5c5-146">たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-146">For example:</span></span>

```
PS> "John Smith [Marketing]" -like "John Smith ``[*``]"
True

PS> "John Smith [Development]" -like "John Smith ``[*``]"
True
```

## <a name="cmdlet-output-and-wildcard-characters"></a><span data-ttu-id="dc5c5-147">コマンドレットの出力とワイルドカード文字</span><span class="sxs-lookup"><span data-stu-id="dc5c5-147">Cmdlet Output and Wildcard Characters</span></span>

<span data-ttu-id="dc5c5-148">コマンドレットのパラメーターでワイルドカード文字がサポートされている場合、通常、この操作では配列の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-148">When cmdlet parameters support wildcard characters, the operation usually generates an array output.</span></span>
<span data-ttu-id="dc5c5-149">場合によっては、ユーザーが1つの項目のみを使用する可能性があるため、配列の出力をサポートすることは意味がありません。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-149">Occasionally, it makes no sense to support an array output because the user might use only a single item.</span></span> <span data-ttu-id="dc5c5-150">たとえば、`Set-Location` コマンドレットでは、ユーザーが1つの場所のみを設定するため、配列の出力はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-150">For example, the `Set-Location` cmdlet does not support array output because the user sets only a single location.</span></span> <span data-ttu-id="dc5c5-151">このインスタンスでは、コマンドレットはワイルドカード文字を引き続きサポートしますが、1つの場所を強制的に解決します。</span><span class="sxs-lookup"><span data-stu-id="dc5c5-151">In this instance, the cmdlet still supports wildcard characters, but it forces resolution to a single location.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc5c5-152">参照</span><span class="sxs-lookup"><span data-stu-id="dc5c5-152">See Also</span></span>

[<span data-ttu-id="dc5c5-153">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="dc5c5-153">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="dc5c5-154">WildcardPattern クラス</span><span class="sxs-lookup"><span data-stu-id="dc5c5-154">WildcardPattern Class</span></span>](/dotnet/api/system.management.automation.wildcardpattern)
