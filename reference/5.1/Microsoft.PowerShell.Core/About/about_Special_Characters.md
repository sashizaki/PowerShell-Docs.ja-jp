---
description: PowerShell でシーケンス内の次の文字を解釈する方法を制御する特殊文字シーケンスについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 04/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_special_characters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Special_Characters
ms.openlocfilehash: 875a1c3c63e759151c3c64b5396312b030955cb7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222520"
---
# <a name="about-special-characters"></a><span data-ttu-id="f9ef9-104">特殊文字について</span><span class="sxs-lookup"><span data-stu-id="f9ef9-104">About Special Characters</span></span>

## <a name="short-description"></a><span data-ttu-id="f9ef9-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="f9ef9-105">Short description</span></span>

<span data-ttu-id="f9ef9-106">PowerShell でシーケンス内の次の文字を解釈する方法を制御する特殊文字シーケンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-106">Describes the special character sequences that control how PowerShell interprets the next characters in the sequence.</span></span>

## <a name="long-description"></a><span data-ttu-id="f9ef9-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="f9ef9-107">Long description</span></span>

<span data-ttu-id="f9ef9-108">PowerShell では、標準文字セットの一部ではない文字を表すために使用される特殊文字シーケンスのセットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-108">PowerShell supports a set of special character sequences that are used to represent characters that aren't part of the standard character set.</span></span> <span data-ttu-id="f9ef9-109">シーケンスは、一般に _エスケープシーケンス_ と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-109">The sequences are commonly known as _escape sequences_.</span></span>

<span data-ttu-id="f9ef9-110">エスケープシーケンスは、バックティック文字で始まり (ASCII 96)、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-110">Escape sequences begin with the backtick character, known as the grave accent (ASCII 96), and are case-sensitive.</span></span> <span data-ttu-id="f9ef9-111">バックティック文字は _エスケープ文字_ と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-111">The backtick character can also be referred to as the _escape character_.</span></span>

<span data-ttu-id="f9ef9-112">エスケープシーケンスは、二重引用符で囲まれた () 文字列に含まれている場合にのみ解釈され `"` ます。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-112">Escape sequences are only interpreted when contained in double-quoted (`"`) strings.</span></span>

<span data-ttu-id="f9ef9-113">PowerShell は、次のエスケープシーケンスを認識します。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-113">PowerShell recognizes these escape sequences:</span></span>

|  <span data-ttu-id="f9ef9-114">Sequence</span><span class="sxs-lookup"><span data-stu-id="f9ef9-114">Sequence</span></span>   |       <span data-ttu-id="f9ef9-115">説明</span><span class="sxs-lookup"><span data-stu-id="f9ef9-115">Description</span></span>       |
| ----------- | ----------------------- |
| `` `0 ``    | <span data-ttu-id="f9ef9-116">[Null]</span><span class="sxs-lookup"><span data-stu-id="f9ef9-116">Null</span></span>                    |
| `` `a ``    | <span data-ttu-id="f9ef9-117">アラート:</span><span class="sxs-lookup"><span data-stu-id="f9ef9-117">Alert</span></span>                   |
| `` `b ``    | <span data-ttu-id="f9ef9-118">バックスペース</span><span class="sxs-lookup"><span data-stu-id="f9ef9-118">Backspace</span></span>               |
| `` `f ``    | <span data-ttu-id="f9ef9-119">フォーム フィード</span><span class="sxs-lookup"><span data-stu-id="f9ef9-119">Form feed</span></span>               |
| `` `n ``    | <span data-ttu-id="f9ef9-120">改行</span><span class="sxs-lookup"><span data-stu-id="f9ef9-120">New line</span></span>                |
| `` `r ``    | <span data-ttu-id="f9ef9-121">キャリッジ リターン</span><span class="sxs-lookup"><span data-stu-id="f9ef9-121">Carriage return</span></span>         |
| `` `t ``    | <span data-ttu-id="f9ef9-122">水平タブ</span><span class="sxs-lookup"><span data-stu-id="f9ef9-122">Horizontal tab</span></span>          |
| `` `v ``    | <span data-ttu-id="f9ef9-123">垂直タブ</span><span class="sxs-lookup"><span data-stu-id="f9ef9-123">Vertical tab</span></span>            |

<span data-ttu-id="f9ef9-124">PowerShell には、解析を停止する場所をマークする特別なトークンもあります。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-124">PowerShell also has a special token to mark where you want parsing to stop.</span></span> <span data-ttu-id="f9ef9-125">このトークンの後に続くすべての文字は、解釈されないリテラル値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-125">All characters that follow this token are used as literal values that aren't interpreted.</span></span>

<span data-ttu-id="f9ef9-126">特別な解析トークン:</span><span class="sxs-lookup"><span data-stu-id="f9ef9-126">Special parsing token:</span></span>

| <span data-ttu-id="f9ef9-127">Sequence</span><span class="sxs-lookup"><span data-stu-id="f9ef9-127">Sequence</span></span> |            <span data-ttu-id="f9ef9-128">説明</span><span class="sxs-lookup"><span data-stu-id="f9ef9-128">Description</span></span>             |
| -------- | ---------------------------------- |
| `--%`    | <span data-ttu-id="f9ef9-129">次のいずれかの解析を停止します。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-129">Stop parsing anything that follows</span></span> |

## <a name="null-0"></a><span data-ttu-id="f9ef9-130">Null (' 0 ')</span><span class="sxs-lookup"><span data-stu-id="f9ef9-130">Null (\`0)</span></span>

<span data-ttu-id="f9ef9-131">Null ( `` `0 `` ) 文字は、PowerShell の出力に空の領域として表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-131">The null (`` `0 ``) character appears as an empty space in PowerShell output.</span></span>
<span data-ttu-id="f9ef9-132">この機能により、PowerShell を使用して、文字列終了インジケーターやレコード終了インジケーターなど、null 文字を使用するテキストファイルの読み取りと処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-132">This functionality allows you to use PowerShell to read and process text files that use null characters, such as string termination or record termination indicators.</span></span> <span data-ttu-id="f9ef9-133">Null 特殊文字は、 `$null` **null** 値を格納する変数と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-133">The null special character isn't equivalent to the `$null` variable, which stores a **null** value.</span></span>

## <a name="alert-a"></a><span data-ttu-id="f9ef9-134">アラート (' a)</span><span class="sxs-lookup"><span data-stu-id="f9ef9-134">Alert (\`a)</span></span>

<span data-ttu-id="f9ef9-135">Alert ( `` `a `` ) 文字は、コンピューターのスピーカーにビープ音を送ります。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-135">The alert (`` `a ``) character sends a beep signal to the computer's speaker.</span></span>
<span data-ttu-id="f9ef9-136">この文字を使用すると、ユーザーに対して、間もなく行われるアクションについて警告することができます。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-136">You can use this character to warn a user about an impending action.</span></span> <span data-ttu-id="f9ef9-137">次の例では、2つのビープ音信号をローカルコンピューターのスピーカーに送信します。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-137">The following example sends two beep signals to the local computer's speaker.</span></span>

```powershell
for ($i = 0; $i -le 1; $i++){"`a"}
```

## <a name="backspace-b"></a><span data-ttu-id="f9ef9-138">Backspace (' b)</span><span class="sxs-lookup"><span data-stu-id="f9ef9-138">Backspace (\`b)</span></span>

<span data-ttu-id="f9ef9-139">Backspace ( `` `b `` ) 文字はカーソルを1文字前に移動しますが、文字は削除しません。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-139">The backspace (`` `b ``) character moves the cursor back one character, but it doesn't delete any characters.</span></span>

<span data-ttu-id="f9ef9-140">この例では、 **バックアップ** という単語を書き込み、カーソルを2回移動します。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-140">The example writes the word **backup** and then moves the cursor back twice.</span></span>
<span data-ttu-id="f9ef9-141">次に、新しい位置で、スペースを書き込み、続けて「 **out** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-141">Then, at the new position, writes a space followed by the word **out**.</span></span>

```powershell
"backup`b`b out"
```

```Output
back out
```

## <a name="form-feed-f"></a><span data-ttu-id="f9ef9-142">フォームフィード (' f)</span><span class="sxs-lookup"><span data-stu-id="f9ef9-142">Form feed (\`f)</span></span>

<span data-ttu-id="f9ef9-143">Form feed ( `` `f `` ) 文字は、現在のページを取り出して次のページで印刷を続行する印刷命令です。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-143">The form feed (`` `f ``) character is a print instruction that ejects the current page and continues printing on the next page.</span></span> <span data-ttu-id="f9ef9-144">フォームフィード文字は、印刷されたドキュメントにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-144">The form feed character only affects printed documents.</span></span> <span data-ttu-id="f9ef9-145">画面出力には影響しません。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-145">It doesn't affect screen output.</span></span>

## <a name="new-line-n"></a><span data-ttu-id="f9ef9-146">改行 (' n)</span><span class="sxs-lookup"><span data-stu-id="f9ef9-146">New line (\`n)</span></span>

<span data-ttu-id="f9ef9-147">改行文字 ( `` `n `` ) を挿入すると、文字の直後に改行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-147">The new line (`` `n ``) character inserts a line break immediately after the character.</span></span>

<span data-ttu-id="f9ef9-148">この例では、改行文字を使用してコマンドで改行を作成する方法を示し `Write-Host` ます。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-148">This example shows how to use the new line character to create line breaks in a `Write-Host` command.</span></span>

```powershell
"There are two line breaks to create a blank line`n`nbetween the words."
```

```Output
There are two line breaks to create a blank line

between the words.
```

## <a name="carriage-return-r"></a><span data-ttu-id="f9ef9-149">キャリッジリターン (' r)</span><span class="sxs-lookup"><span data-stu-id="f9ef9-149">Carriage return (\`r)</span></span>

<span data-ttu-id="f9ef9-150">キャリッジリターン ( `` `r `` ) 文字は、出力カーソルを現在の行の先頭に移動し、書き込みを続行します。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-150">The carriage return (`` `r ``) character moves the output cursor to the beginning of the current line and continues writing.</span></span> <span data-ttu-id="f9ef9-151">現在の行のすべての文字が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-151">Any characters on the current line are overwritten.</span></span>

<span data-ttu-id="f9ef9-152">この例では、復帰前のテキストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-152">In this example, the text before the carriage return is overwritten.</span></span>

```powershell
Write-Host "These characters are overwritten.`rI want this text instead "
```

<span data-ttu-id="f9ef9-153">文字の前のテキストは削除されず、上書きされることに注意して `` `r `` ください。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-153">Notice that the text before the `` `r `` character is not deleted, it is overwritten.</span></span>

```Output
I want this text instead written.
```

## <a name="horizontal-tab-t"></a><span data-ttu-id="f9ef9-154">水平タブ (\)</span><span class="sxs-lookup"><span data-stu-id="f9ef9-154">Horizontal tab (\`t)</span></span>

<span data-ttu-id="f9ef9-155">水平タブ ( `` `t `` ) 文字は、次のタブストップに進み、その時点での書き込みを続行します。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-155">The horizontal tab (`` `t ``) character advances to the next tab stop and continues writing at that point.</span></span> <span data-ttu-id="f9ef9-156">既定では、PowerShell コンソールのタブは、8分ごとに停止します。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-156">By default, the PowerShell console has a tab stop at every eighth space.</span></span>

<span data-ttu-id="f9ef9-157">この例では、各列の間に2つのタブを挿入します。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-157">This example inserts two tabs between each column.</span></span>

```powershell
"Column1`t`tColumn2`t`tColumn3"
```

```Output
Column1         Column2         Column3
```

## <a name="vertical-tab-v"></a><span data-ttu-id="f9ef9-158">垂直タブ (' v)</span><span class="sxs-lookup"><span data-stu-id="f9ef9-158">Vertical tab (\`v)</span></span>

<span data-ttu-id="f9ef9-159">水平タブ ( `` `v `` ) 文字は、次の垂直タブに進み、その時点で残りの出力を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-159">The horizontal tab (`` `v ``) character advances to the next vertical tab stop and writes the remaining output at that point.</span></span> <span data-ttu-id="f9ef9-160">これは、既定の Windows コンソールには影響しません。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-160">This has no effect in the default Windows console.</span></span>

```powershell
Write-Host "There is a vertical tab`vbetween the words."
```

<span data-ttu-id="f9ef9-161">次の例は、プリンターまたは別のコンソールホストで取得する出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-161">The following example shows the output you would get on a printer or in a different console host.</span></span>

```Output
There is a vertical tab
                       between the words.
```

## <a name="stop-parsing-token---"></a><span data-ttu-id="f9ef9-162">ストップ解析トークン (--%)</span><span class="sxs-lookup"><span data-stu-id="f9ef9-162">Stop-parsing token (--%)</span></span>

<span data-ttu-id="f9ef9-163">ストップ解析 () トークンは、powershell が `--%` 文字列を powershell コマンドおよび式として解釈できないようにします。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-163">The stop-parsing (`--%`) token prevents PowerShell from interpreting strings as PowerShell commands and expressions.</span></span> <span data-ttu-id="f9ef9-164">これにより、これらの文字列を他のプログラムに渡して解釈することができます。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-164">This allows those strings to be passed to other programs for interpretation.</span></span>

<span data-ttu-id="f9ef9-165">プログラム名の後に、エラーの原因となる可能性のあるプログラム引数の前に、ストップ解析トークンを配置します。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-165">Place the stop-parsing token after the program name and before program arguments that might cause errors.</span></span>

<span data-ttu-id="f9ef9-166">この例では、 `Icacls` コマンドはストップ解析トークンを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-166">In this example, the `Icacls` command uses the stop-parsing token.</span></span>

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="f9ef9-167">PowerShell は、次の文字列をに送信し `Icacls` ます。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-167">PowerShell sends the following string to `Icacls`.</span></span>

```
X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="f9ef9-168">別の例を示します。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-168">Here is another example.</span></span> <span data-ttu-id="f9ef9-169">**Shoの gs** 関数は、渡された値を出力します。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-169">The **showArgs** function outputs the values passed to it.</span></span> <span data-ttu-id="f9ef9-170">この例では、という名前の変数を `$HOME` 関数に2回渡します。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-170">In this example, we pass the variable named `$HOME` to the function twice.</span></span>

```powershell
function showArgs {
  "`$args = " + ($args -join '|')
}

showArgs $HOME --% $HOME
```

出力では、最初のパラメーターとして変数 `$HOME` が PowerShell によって解釈されるため、変数の値が関数に渡されます。 <span data-ttu-id="f9ef9-172">の2番目の使用は、 `$HOME` 解析の停止トークンの後にあるため、文字列 "$HOME" は解釈せずに関数に渡されます。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-172">The second use of `$HOME` comes after the stop-parsing token, so the string "$HOME" is passed to the function without interpretation.</span></span>

```Output
$args = C:\Users\username|--%|$HOME
```

<span data-ttu-id="f9ef9-173">ストップ解析トークンの詳細については、「 [about_Parsing](about_Parsing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9ef9-173">For more information about the stop-parsing token, see [about_Parsing](about_Parsing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f9ef9-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9ef9-174">See also</span></span>

[<span data-ttu-id="f9ef9-175">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="f9ef9-175">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)
