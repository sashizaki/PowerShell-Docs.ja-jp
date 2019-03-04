---
title: コマンドレットのパラメーターでのワイルドカード文字のサポート |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- wildcards [PowerShell Programer's Guide]
- parameters [PowerShell Programmer's Guide], wildcards
ms.assetid: 9b26e1e9-9350-4a5a-aad5-ddcece658d93
caps.latest.revision: 12
ms.openlocfilehash: 296490e4692e72f823be0b00aee90dc8c3dc9131
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862518"
---
# <a name="supporting-wildcard-characters-in-cmdlet-parameters"></a><span data-ttu-id="211b8-102">コマンドレット パラメーターでワイルドカード文字をサポートする</span><span class="sxs-lookup"><span data-stu-id="211b8-102">Supporting Wildcard Characters in Cmdlet Parameters</span></span>

<span data-ttu-id="211b8-103">多くの場合、1 つのリソースではなく、リソースのグループに対して実行するコマンドレットを設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="211b8-103">Often, you will have to design a cmdlet to run against a group of resources rather than against a single resource.</span></span> <span data-ttu-id="211b8-104">たとえば、コマンドレットは、同じ名前または拡張機能を持つデータ ストア内ですべてのファイルを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="211b8-104">For example, a cmdlet might need to locate all the files in a data store that have the same name or extension.</span></span> <span data-ttu-id="211b8-105">リソースのグループに対して実行されるコマンドレットを設計する場合は、ワイルドカード文字のサポートを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="211b8-105">You must provide support for wildcard characters when you design a cmdlet that will be run against a group of resources.</span></span>

> [!NOTE]
> <span data-ttu-id="211b8-106">ワイルドカード文字を使用するとも呼ば*グロビング*します。</span><span class="sxs-lookup"><span data-stu-id="211b8-106">Using wildcard characters is sometimes referred to as *globbing*.</span></span>

## <a name="windows-powershell-cmdlets-that-use-wildcards"></a><span data-ttu-id="211b8-107">ワイルドカードを使用する Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="211b8-107">Windows PowerShell Cmdlets That Use Wildcards</span></span>

 <span data-ttu-id="211b8-108">多くの Windows PowerShell コマンドレットは、パラメーター値をワイルドカード文字をサポートします。</span><span class="sxs-lookup"><span data-stu-id="211b8-108">Many Windows PowerShell cmdlets support wildcard characters for their parameter values.</span></span> <span data-ttu-id="211b8-109">たとえば、ほぼすべてのコマンドレットを持つ、`Name`または`Path`パラメーターは、これらのパラメーターにワイルドカード文字をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="211b8-109">For example, almost every cmdlet that has a `Name` or `Path` parameter supports wildcard characters for these parameters.</span></span> <span data-ttu-id="211b8-110">(する必要はほとんどのコマンドレット、`Path`パラメーターがあることも、`LiteralPath`パラメーターがワイルドカード文字はサポートされていない)。次のコマンドは、名前持つにはには、Get 動詞が含まれています。 現在のセッションですべてのコマンドレットを返すワイルドカード文字を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="211b8-110">(Although most cmdlets that have a `Path` parameter also have a `LiteralPath` parameter that does not support wildcard characters.) The following command shows how a wildcard character is used to return all the cmdlets in the current session whose name contains the Get verb.</span></span>

 <span data-ttu-id="211b8-111">**PS > get コマンド get-\***</span><span class="sxs-lookup"><span data-stu-id="211b8-111">**PS>get-command get-\***</span></span>

## <a name="supported-wildcard-characters"></a><span data-ttu-id="211b8-112">サポートされているワイルドカード文字</span><span class="sxs-lookup"><span data-stu-id="211b8-112">Supported Wildcard Characters</span></span>

<span data-ttu-id="211b8-113">Windows PowerShell では、次のワイルドカード文字をサポートします。</span><span class="sxs-lookup"><span data-stu-id="211b8-113">Windows PowerShell supports the following wildcard characters.</span></span>

|<span data-ttu-id="211b8-114">ワイルドカード文字</span><span class="sxs-lookup"><span data-stu-id="211b8-114">Wildcard character</span></span>|<span data-ttu-id="211b8-115">説明</span><span class="sxs-lookup"><span data-stu-id="211b8-115">Description</span></span>|<span data-ttu-id="211b8-116">例</span><span class="sxs-lookup"><span data-stu-id="211b8-116">Example</span></span>|<span data-ttu-id="211b8-117">[一致する]</span><span class="sxs-lookup"><span data-stu-id="211b8-117">Matches</span></span>|<span data-ttu-id="211b8-118">［次の値に一致しない］</span><span class="sxs-lookup"><span data-stu-id="211b8-118">Does not match</span></span>|
|------------------------|-----------------|-------------|-------------|--------------------|
|*|<span data-ttu-id="211b8-119">指定した位置から始まり、0 個以上の文字と一致</span><span class="sxs-lookup"><span data-stu-id="211b8-119">Matches zero or more characters, starting at the specified position</span></span>|<span data-ttu-id="211b8-120">\*</span><span class="sxs-lookup"><span data-stu-id="211b8-120">a\*</span></span>|<span data-ttu-id="211b8-121">Apple は、可用性グループ</span><span class="sxs-lookup"><span data-stu-id="211b8-121">A, ag, Apple</span></span>||
|<span data-ttu-id="211b8-122">?</span><span class="sxs-lookup"><span data-stu-id="211b8-122">?</span></span>|<span data-ttu-id="211b8-123">指定した位置に一致する任意の文字</span><span class="sxs-lookup"><span data-stu-id="211b8-123">Matches anycharacter at the specified position</span></span>|<span data-ttu-id="211b8-124">?n</span><span class="sxs-lookup"><span data-stu-id="211b8-124">?n</span></span>|<span data-ttu-id="211b8-125">で、オン</span><span class="sxs-lookup"><span data-stu-id="211b8-125">An, in, on</span></span>|<span data-ttu-id="211b8-126">実行</span><span class="sxs-lookup"><span data-stu-id="211b8-126">ran</span></span>|
|<span data-ttu-id="211b8-127">[ ]</span><span class="sxs-lookup"><span data-stu-id="211b8-127">[ ]</span></span>|<span data-ttu-id="211b8-128">文字の範囲に一致します。</span><span class="sxs-lookup"><span data-stu-id="211b8-128">Matches a range of characters</span></span>|<span data-ttu-id="211b8-129">[a-l] ook</span><span class="sxs-lookup"><span data-stu-id="211b8-129">[a-l]ook</span></span>|<span data-ttu-id="211b8-130">書籍、cook、参照してください。</span><span class="sxs-lookup"><span data-stu-id="211b8-130">book, cook, look</span></span>|<span data-ttu-id="211b8-131">かかりました</span><span class="sxs-lookup"><span data-stu-id="211b8-131">took</span></span>|
|<span data-ttu-id="211b8-132">[ ]</span><span class="sxs-lookup"><span data-stu-id="211b8-132">[ ]</span></span>|<span data-ttu-id="211b8-133">指定した文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="211b8-133">Matches the specified characters</span></span>|<span data-ttu-id="211b8-134">[bc] ook</span><span class="sxs-lookup"><span data-stu-id="211b8-134">[bc]ook</span></span>|<span data-ttu-id="211b8-135">書籍、クック</span><span class="sxs-lookup"><span data-stu-id="211b8-135">book, cook</span></span>|<span data-ttu-id="211b8-136">ほら</span><span class="sxs-lookup"><span data-stu-id="211b8-136">look</span></span>|

<span data-ttu-id="211b8-137">ワイルドカード文字をサポートするコマンドレットを設計する場合は、ワイルドカード文字の組み合わせに対して許可します。</span><span class="sxs-lookup"><span data-stu-id="211b8-137">When you design cmdlets that support wildcard characters, allow for combinations of wildcard characters.</span></span> <span data-ttu-id="211b8-138">たとえば、次のコマンドを使用して、`Get-ChildItem`コマンドレットすべての .txt ファイル c:\Techdocs フォルダー内にあるし、"a"から"l です"文字で開始されるを取得するには。</span><span class="sxs-lookup"><span data-stu-id="211b8-138">For example, the following command uses the `Get-ChildItem` cmdlet to retrieve all the .txt files that are in the c:\Techdocs folder and that begin with the letters "a" through "l."</span></span>

<span data-ttu-id="211b8-139">**get-childitem c:\techdocs\\[a-l]\*.txt**</span><span class="sxs-lookup"><span data-stu-id="211b8-139">**get-childitem c:\techdocs\\[a-l]\*.txt**</span></span>

<span data-ttu-id="211b8-140">前のコマンドは、範囲のワイルドカードを使用して **[、l]** ことファイル名は文字で始まる、"a"から"l です"を指定するには。</span><span class="sxs-lookup"><span data-stu-id="211b8-140">The previous command uses the range wildcard **[a-l]** to specify that the file name should begin with the characters "a" through "l."</span></span> <span data-ttu-id="211b8-141">次にコマンドは、\* ワイルドカード文字をファイル名の最初の文字と、.txt 拡張子の間の任意の文字のプレース ホルダーとして。</span><span class="sxs-lookup"><span data-stu-id="211b8-141">The command then uses the \* wildcard character as a placeholder for any characters between the first letter of the file name and the .txt extension.</span></span>

<span data-ttu-id="211b8-142">次のコードの例では、文字"d"は含まれませんが、"a"~"f"からの他のすべての文字が含まれています、範囲のワイルドカード パターン</span><span class="sxs-lookup"><span data-stu-id="211b8-142">The following example uses a range wildcard pattern that excludes the letter "d" but includes all the other letters from "a" through "f."</span></span>

<span data-ttu-id="211b8-143">**get-childitem c:\techdocs\\[、cef]\*.txt**</span><span class="sxs-lookup"><span data-stu-id="211b8-143">**get-childitem c:\techdocs\\[a-cef]\*.txt**</span></span>

## <a name="handling-literal-characters-in-wildcard-patterns"></a><span data-ttu-id="211b8-144">ワイルドカード パターン内のリテラル文字の処理</span><span class="sxs-lookup"><span data-stu-id="211b8-144">Handling Literal Characters in Wildcard Patterns</span></span>

<span data-ttu-id="211b8-145">指定したワイルドカード パターンにリテラル文字が含まれている場合は、エスケープ文字として、アクサン グラーブ文字 (') を使用します。</span><span class="sxs-lookup"><span data-stu-id="211b8-145">If the wildcard pattern you specify contains literal characters, use the backtick character (\`) as an escape character.</span></span> <span data-ttu-id="211b8-146">リテラル文字をプログラムで指定する場合は、1 つのバッククォートを使用します。</span><span class="sxs-lookup"><span data-stu-id="211b8-146">When you specify literal characters programmatically, use a single backtick.</span></span> <span data-ttu-id="211b8-147">コマンド プロンプトで、リテラル文字を指定する場合は、2 つのバッククォートを使用します。</span><span class="sxs-lookup"><span data-stu-id="211b8-147">When you specify literal characters at the command prompt, use two backticks.</span></span> <span data-ttu-id="211b8-148">たとえば、次のパターンには、そのまま使用する必要がありますがある 2 つの角かっこが含まれています。</span><span class="sxs-lookup"><span data-stu-id="211b8-148">For example, the following pattern contains two brackets that must be taken literally.</span></span>

<span data-ttu-id="211b8-149">"John Smith \`[\*']"(プログラムで指定)</span><span class="sxs-lookup"><span data-stu-id="211b8-149">"John Smith \`[\*\`]" (specified programmatically)</span></span>

<span data-ttu-id="211b8-150">"John Smith \` \`[\*\`']"(コマンド プロンプトで指定)</span><span class="sxs-lookup"><span data-stu-id="211b8-150">"John Smith \`\`[\*\`\`]"  (specified at the command prompt)</span></span>

<span data-ttu-id="211b8-151">このパターンは、"John Smith [マーケティング]"または"John Smith [開発]"と一致します。</span><span class="sxs-lookup"><span data-stu-id="211b8-151">This pattern matches "John Smith [Marketing]" or "John Smith [Development]".</span></span>

## <a name="cmdlet-output-and-wildcard-characters"></a><span data-ttu-id="211b8-152">コマンドレットの出力とワイルドカード文字</span><span class="sxs-lookup"><span data-stu-id="211b8-152">Cmdlet Output and Wildcard Characters</span></span>

<span data-ttu-id="211b8-153">コマンドレットのパラメーターは、ワイルドカード文字をサポートと、コマンドレットの操作は、通常は配列出力を生成します。</span><span class="sxs-lookup"><span data-stu-id="211b8-153">When cmdlet parameters support wildcard characters, a cmdlet operation usually generates an array output.</span></span> <span data-ttu-id="211b8-154">場合によっては、ユーザーは一度に 1 つの項目のみを使用する場合がありますので、出力配列をサポートするために意味がありません。</span><span class="sxs-lookup"><span data-stu-id="211b8-154">Occasionally, it makes no sense to support an array output because the user might use only a single item at a time.</span></span> <span data-ttu-id="211b8-155">たとえば、`Set-Location`コマンドレットは、ユーザーが 1 つの場所のみを設定するため、出力配列をサポートします。</span><span class="sxs-lookup"><span data-stu-id="211b8-155">For example, the `Set-Location` cmdlet does support an array output because the user sets only a single location.</span></span> <span data-ttu-id="211b8-156">このインスタンスでは、コマンドレットには、ワイルドカード文字を引き続きサポートされますが解像度を強制的に 1 つの場所にします。</span><span class="sxs-lookup"><span data-stu-id="211b8-156">In this instance, the cmdlet still supports wildcard characters, but it forces resolution to a single location.</span></span>

## <a name="see-also"></a><span data-ttu-id="211b8-157">参照</span><span class="sxs-lookup"><span data-stu-id="211b8-157">See Also</span></span>

[<span data-ttu-id="211b8-158">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="211b8-158">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="211b8-159">WildcardPattern クラス</span><span class="sxs-lookup"><span data-stu-id="211b8-159">WildcardPattern Class</span></span>](/dotnet/api/system.management.automation.wildcardpattern)
