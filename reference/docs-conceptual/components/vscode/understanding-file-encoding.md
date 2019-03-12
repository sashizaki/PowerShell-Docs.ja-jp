---
title: VSCode と PowerShell でのファイルのエンコードの概要
description: VSCode と PowerShell でファイルのエンコードを構成します。
ms.date: 02/28/2019
ms.openlocfilehash: 9cf445ebd0c2bb2dbdf4438f02dafe3df3a5d1e2
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429807"
---
# <a name="understanding-file-encoding-in-vscode-and-powershell"></a><span data-ttu-id="d332d-103">VSCode と PowerShell でのファイルのエンコードの概要</span><span class="sxs-lookup"><span data-stu-id="d332d-103">Understanding file encoding in VSCode and PowerShell</span></span>

<span data-ttu-id="d332d-104">を作成および PowerShell スクリプトを編集する VS Code を使用する場合、正しい文字のエンコード形式を使用して、ファイルを保存することが重要です。</span><span class="sxs-lookup"><span data-stu-id="d332d-104">When using VS Code to create and edit PowerShell scripts, it is important that your files are saved using the correct character encoding format.</span></span>

## <a name="what-is-file-encoding-and-why-is-it-important"></a><span data-ttu-id="d332d-105">ファイルのエンコードと、重要である理由とは</span><span class="sxs-lookup"><span data-stu-id="d332d-105">What is file encoding and why is it important?</span></span>

<span data-ttu-id="d332d-106">VSCode では、バッファーに文字の人間の入力文字列とファイル システムにバイトの読み取り/書き込みブロック間のインターフェイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="d332d-106">VSCode manages the interface between a human entering strings of characters into a buffer and reading/writing blocks of bytes to the filesystem.</span></span> <span data-ttu-id="d332d-107">VSCode では、ファイルを保存、これを行うエンコード テキストが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d332d-107">When VSCode saves a file, it uses a text encoding to do this.</span></span>

<span data-ttu-id="d332d-108">同様に、PowerShell スクリプトの実行時に、PowerShell のプログラムにファイルを再構築する文字をファイル内のバイトを変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d332d-108">Similarly, when PowerShell runs a script it must convert the bytes in a file to characters to reconstruct the file into a PowerShell program.</span></span> <span data-ttu-id="d332d-109">VSCode がファイルを書き込むし、PowerShell は、ファイルを読み取るために、同じエンコーディング システムを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d332d-109">Since VSCode writes the file and PowerShell reads the file, they need to use the same encoding system.</span></span> <span data-ttu-id="d332d-110">このプロセスの PowerShell スクリプトの解析に:*バイト* -> *文字* -> *トークン* ->  *抽象構文ツリー* -> *実行*します。</span><span class="sxs-lookup"><span data-stu-id="d332d-110">This process of parsing a PowerShell script goes: *bytes* -> *characters* -> *tokens* -> *abstract syntax tree* -> *execution*.</span></span>

<span data-ttu-id="d332d-111">VSCode と PowerShell の両方が、実用的な既定のエンコード構成と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d332d-111">Both VSCode and PowerShell are installed with a sensible default encoding configuration.</span></span> <span data-ttu-id="d332d-112">ただし、PowerShell で使用される既定のエンコーディングは、PowerShell Core (v6.x) のリリースで変更されました。</span><span class="sxs-lookup"><span data-stu-id="d332d-112">However, the default encoding used by PowerShell has changed with the release of PowerShell Core (v6.x).</span></span> <span data-ttu-id="d332d-113">VSCode での PowerShell または PowerShell の拡張機能の使用に関する問題がないことを確認するには、VSCode と PowerShell の設定を構成する必要があります適切です。</span><span class="sxs-lookup"><span data-stu-id="d332d-113">To ensure you have no problems using PowerShell or the PowerShell extension in VSCode, you need to configure your VSCode and PowerShell settings properly.</span></span>

## <a name="common-causes-of-encoding-issues"></a><span data-ttu-id="d332d-114">エンコーディングの問題の一般的な原因</span><span class="sxs-lookup"><span data-stu-id="d332d-114">Common causes of encoding issues</span></span>

<span data-ttu-id="d332d-115">VSCode またはスクリプト ファイルのエンコードしても PowerShell の必要なエンコードは一致しない場合、エンコーディングの問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="d332d-115">Encoding problems occur when the encoding of VSCode or your script file does not match the expected encoding of PowerShell.</span></span> <span data-ttu-id="d332d-116">PowerShell ファイルのエンコーディングを自動的に決定する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="d332d-116">There is no way for PowerShell to automatically determine the file encoding.</span></span>

<span data-ttu-id="d332d-117">内にない文字を使用しているときに、問題をエンコードする可能性が高く、 [7 ビット ASCII 文字セット](https://ascii.cl/)します。</span><span class="sxs-lookup"><span data-stu-id="d332d-117">You're more likely to have encoding problems when you're using characters not in the [7-bit ASCII character set](https://ascii.cl/).</span></span> <span data-ttu-id="d332d-118">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d332d-118">For example:</span></span>

- <span data-ttu-id="d332d-119">ラテン文字にアクセント記号 (`É`、 `ü`)</span><span class="sxs-lookup"><span data-stu-id="d332d-119">Accented latin characters (`É`, `ü`)</span></span>
- <span data-ttu-id="d332d-120">キリル語などのラテン文字以外の文字 (`Д`、 `Ц`)</span><span class="sxs-lookup"><span data-stu-id="d332d-120">Non-latin characters like Cyrillic (`Д`, `Ц`)</span></span>
- <span data-ttu-id="d332d-121">Han 中国語 (`脚`、 `本`)</span><span class="sxs-lookup"><span data-stu-id="d332d-121">Han Chinese (`脚`, `本`)</span></span>

<span data-ttu-id="d332d-122">エンコーディングの問題の一般的な理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d332d-122">Common reasons for encoding issues are:</span></span>

- <span data-ttu-id="d332d-123">VSCode と PowerShell のエンコーディングがその既定値から変更されていません。</span><span class="sxs-lookup"><span data-stu-id="d332d-123">The encodings of VSCode and PowerShell have not been changed from their defaults.</span></span> <span data-ttu-id="d332d-124">PowerShell 5.1 と下、既定値は、VSCode の異なるエンコードです。</span><span class="sxs-lookup"><span data-stu-id="d332d-124">For PowerShell 5.1 and below, the default encoding is different from VSCode's.</span></span>
- <span data-ttu-id="d332d-125">別のエディターが開き、新しいエンコードでファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="d332d-125">Another editor has opened and overwritten the file in a new encoding.</span></span> <span data-ttu-id="d332d-126">これは、多くの場合、ISE で発生します。</span><span class="sxs-lookup"><span data-stu-id="d332d-126">This often happens with the ISE.</span></span>
- <span data-ttu-id="d332d-127">ファイルは、どのような VSCode または PowerShell から期待とは別のエンコーディングをソース管理にチェックします。</span><span class="sxs-lookup"><span data-stu-id="d332d-127">The file is checked into source control in an encoding that is different from what VSCode or PowerShell expects.</span></span> <span data-ttu-id="d332d-128">これは、コラボレーターでさまざまなエンコード構成エディターを使用する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="d332d-128">This can happen when collaborators use editors with different encoding configurations.</span></span>

### <a name="how-to-tell-when-you-have-encoding-issues"></a><span data-ttu-id="d332d-129">エンコーディングの問題を作成するときに指定する方法</span><span class="sxs-lookup"><span data-stu-id="d332d-129">How to tell when you have encoding issues</span></span>

<span data-ttu-id="d332d-130">多くの場合、エンコーディング エラーが発生、スクリプトのエラーを解析します。</span><span class="sxs-lookup"><span data-stu-id="d332d-130">Often encoding errors present themselves as parse errors in scripts.</span></span> <span data-ttu-id="d332d-131">スクリプトに奇妙な文字のシーケンスがある場合、問題できます。</span><span class="sxs-lookup"><span data-stu-id="d332d-131">If you find strange character sequences in your script, this can be the problem.</span></span> <span data-ttu-id="d332d-132">En dash を次の例で (`–`) 文字として表示される`â€“`:</span><span class="sxs-lookup"><span data-stu-id="d332d-132">In the example below, an en-dash (`–`) appears as the characters `â€“`:</span></span>

```Output
Send-MailMessage : A positional parameter cannot be found that accepts argument 'Testing FuseMail SMTP...'.
At C:\Users\<User>\<OneDrive>\Development\PowerShell\Scripts\Send-EmailUsingSmtpRelay.ps1:6 char:1
+ Send-MailMessage â€“From $from â€“To $recipient1 â€“Subject $subject  ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Send-MailMessage], ParameterBindingException
    + FullyQualifiedErrorId : PositionalParameterNotFound,Microsoft.PowerShell.Commands.SendMailMessage
```

<span data-ttu-id="d332d-133">この問題は、VSCode、文字をエンコードするために発生します。 `–` utf-8 バイトとして`0xE2 0x80 0x93`します。</span><span class="sxs-lookup"><span data-stu-id="d332d-133">This problem occurs because VSCode encodes the character `–` in UTF-8 as the bytes `0xE2 0x80 0x93`.</span></span>
<span data-ttu-id="d332d-134">文字として解釈されるときに、これらのバイトは、Windows 1252 としてデコード、`â€“`します。</span><span class="sxs-lookup"><span data-stu-id="d332d-134">When these bytes are decoded as Windows-1252, they are interpreted as the characters `â€“`.</span></span>

<span data-ttu-id="d332d-135">表示されるいくつかの奇妙な文字シーケンスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d332d-135">Some strange character sequences that you might see include:</span></span>

- <span data-ttu-id="d332d-136">`–` の代わりに `â€“`</span><span class="sxs-lookup"><span data-stu-id="d332d-136">`â€“` instead of `–`</span></span>
- <span data-ttu-id="d332d-137">`—` の代わりに `â€”`</span><span class="sxs-lookup"><span data-stu-id="d332d-137">`â€”` instead of `—`</span></span>
- <span data-ttu-id="d332d-138">`Ä` の代わりに `Ã„2`</span><span class="sxs-lookup"><span data-stu-id="d332d-138">`Ã„2` instead of `Ä`</span></span>
- <span data-ttu-id="d332d-139">`Â` 代わりに` `(改行なしスペース)</span><span class="sxs-lookup"><span data-stu-id="d332d-139">`Â` instead of ` `  (a non-breaking space)</span></span>
- <span data-ttu-id="d332d-140">`é` の代わりに `Ã©`</span><span class="sxs-lookup"><span data-stu-id="d332d-140">`Ã©` instead of `é`</span></span>

<span data-ttu-id="d332d-141">この便利な[参照](https://www.i18nqa.com/debug/utf8-debug.html)UTF 8/Windows 1252 のエンコーディングの問題を示す一般的なパターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="d332d-141">This handy [reference](https://www.i18nqa.com/debug/utf8-debug.html) lists the common patterns that indicate a UTF-8/Windows-1252 encoding problem.</span></span>

## <a name="how-the-powershell-extension-in-vscode-interacts-with-encodings"></a><span data-ttu-id="d332d-142">VSCode での PowerShell の拡張機能がエンコーディングと対話する方法</span><span class="sxs-lookup"><span data-stu-id="d332d-142">How the PowerShell extension in VSCode interacts with encodings</span></span>

<span data-ttu-id="d332d-143">PowerShell の拡張機能は、さまざまな方法でスクリプトを使用した操作します。</span><span class="sxs-lookup"><span data-stu-id="d332d-143">The PowerShell extension interacts with scripts in a number of ways:</span></span>

1. <span data-ttu-id="d332d-144">VSCode でスクリプトを編集した内容は、拡張機能に VSCode で送信されます。</span><span class="sxs-lookup"><span data-stu-id="d332d-144">When scripts are edited in VSCode, the contents are sent by VSCode to the extension.</span></span> <span data-ttu-id="d332d-145">[言語サーバー プロトコル][]を utf-8 でこのコンテンツが転送されることを義務付けています。</span><span class="sxs-lookup"><span data-stu-id="d332d-145">The [Language Server Protocol][] mandates that this content is transferred in UTF-8.</span></span> <span data-ttu-id="d332d-146">そのため、間違ったエンコーディングを取得する拡張機能のことはできません。</span><span class="sxs-lookup"><span data-stu-id="d332d-146">Therefore, it is not possible for the extension to get the wrong encoding.</span></span>
2. <span data-ttu-id="d332d-147">スクリプトが、統合されたコンソールで直接実行された、読み込まれるファイルから PowerShell によって直接します。</span><span class="sxs-lookup"><span data-stu-id="d332d-147">When scripts are executed directly in the Integrated Console, they're read from the file by PowerShell directly.</span></span> <span data-ttu-id="d332d-148">VSCode の PowerShell のエンコードと異なる場合、ものはここへ記述が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="d332d-148">If PowerShell's encoding differs from VSCode's, something can go wrong here.</span></span>
3. <span data-ttu-id="d332d-149">VSCode で開いているスクリプトでは、VSCode で開かれていない別のスクリプトを参照する、拡張機能は、ファイル システムからそのスクリプトのコンテンツの読み込みにフォールバックします。</span><span class="sxs-lookup"><span data-stu-id="d332d-149">When a script that is open in VSCode references another script that is not open in VSCode, the extension falls back to loading that script's content from the file system.</span></span> <span data-ttu-id="d332d-150">PowerShell の拡張機能が既定では utf-8 がエンコーディングが使用[バイト オーダー マーク][]、または BOM 検出の正しいエンコーディングを選択します。</span><span class="sxs-lookup"><span data-stu-id="d332d-150">The PowerShell extension defaults to UTF-8 encoding, but uses [byte-order mark][], or BOM, detection to select the correct encoding.</span></span>

<span data-ttu-id="d332d-151">問題は、BOM なしの形式のエンコーディングを前提とする場合に発生します (など[utf-8][] BOM なしでと[Windows-1252][])。</span><span class="sxs-lookup"><span data-stu-id="d332d-151">The problem occurs when assuming the encoding of BOM-less formats (like [UTF-8][] with no BOM and [Windows-1252][]).</span></span>
<span data-ttu-id="d332d-152">PowerShell の拡張機能の既定値は utf-8 です。</span><span class="sxs-lookup"><span data-stu-id="d332d-152">The PowerShell extension defaults to UTF-8.</span></span> <span data-ttu-id="d332d-153">拡張機能では、VSCode のエンコード設定を変更できません。</span><span class="sxs-lookup"><span data-stu-id="d332d-153">The extension cannot change VSCode's encoding settings.</span></span>
<span data-ttu-id="d332d-154">詳細については、次を参照してください。[発行 #824](https://github.com/Microsoft/vscode/issues/824)します。</span><span class="sxs-lookup"><span data-stu-id="d332d-154">For more information, see [issue #824](https://github.com/Microsoft/vscode/issues/824).</span></span>

## <a name="choosing-the-right-encoding"></a><span data-ttu-id="d332d-155">適切なエンコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="d332d-155">Choosing the right encoding</span></span>

<span data-ttu-id="d332d-156">さまざまなシステムやアプリケーションは、さまざまなエンコーディングを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d332d-156">Different systems and applications can use different encodings:</span></span>

- <span data-ttu-id="d332d-157">.NET standard では、web、および Linux の世界で utf-8 はここで主要なエンコーディングです。</span><span class="sxs-lookup"><span data-stu-id="d332d-157">In .NET Standard, on the web, and in the Linux world, UTF-8 is now the dominant encoding.</span></span>
- <span data-ttu-id="d332d-158">多くの .NET Framework アプリケーションを使用して、 [utf-16][]します。</span><span class="sxs-lookup"><span data-stu-id="d332d-158">Many .NET Framework applications use [UTF-16][].</span></span> <span data-ttu-id="d332d-159">歴史的な理由から、これは、"Unicode"と呼ば、用語のようになりましたが、広範なを指す[標準](https://en.wikipedia.org/wiki/Unicode)utf-8 と utf-16 の両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d332d-159">For historical reasons, this is sometimes called "Unicode", a term that now refers to a broad [standard](https://en.wikipedia.org/wiki/Unicode) that includes both UTF-8 and UTF-16.</span></span>
- <span data-ttu-id="d332d-160">Windows には、Unicode のためよりも多くのネイティブ アプリケーションは、既定では、Windows 1252 を使用する継続します。</span><span class="sxs-lookup"><span data-stu-id="d332d-160">On Windows, many native applications that predate Unicode continue to use Windows-1252 by default.</span></span>

<span data-ttu-id="d332d-161">Unicode エンコーディングでは、バイト順マーク (BOM) 概念もあります。</span><span class="sxs-lookup"><span data-stu-id="d332d-161">Unicode encodings also have the concept of a byte-order mark (BOM).</span></span> <span data-ttu-id="d332d-162">テキストを使用するエンコーディングをデコーダーに指示するテキストの先頭の Bom が発生します。</span><span class="sxs-lookup"><span data-stu-id="d332d-162">BOMs occur at the beginning of text to tell a decoder which encoding the text is using.</span></span> <span data-ttu-id="d332d-163">マルチ バイト エンコーディングでは、BOM も示されます[エンディアン](https://en.wikipedia.org/wiki/Endianness)のエンコーディングします。</span><span class="sxs-lookup"><span data-stu-id="d332d-163">For multi-byte encodings, the BOM also indicates [endianness](https://en.wikipedia.org/wiki/Endianness) of the encoding.</span></span> <span data-ttu-id="d332d-164">Bom は、バイトのテキストが Unicode BOM が存在する場合、合理的に推測できるように、Unicode 以外のテキストではめったに設計されています。</span><span class="sxs-lookup"><span data-stu-id="d332d-164">BOMs are designed to be bytes that rarely occur in non-Unicode text, allowing a reasonable guess that text is Unicode when a BOM is present.</span></span>

<span data-ttu-id="d332d-165">Bom は省略可能で、utf-8 の信頼性の高い規則があらゆる場所で使用されるため、Linux の世界で一般的な導入ではありません。</span><span class="sxs-lookup"><span data-stu-id="d332d-165">BOMs are optional and their adoption isn't as popular in the Linux world because a dependable convention of UTF-8 is used everywhere.</span></span> <span data-ttu-id="d332d-166">ほとんどの Linux アプリケーションでは、テキスト入力は utf-8 でエンコードされていることを推測します。</span><span class="sxs-lookup"><span data-stu-id="d332d-166">Most Linux applications presume that text input is encoded in UTF-8.</span></span> <span data-ttu-id="d332d-167">多くの Linux アプリケーションでは、認識され、BOM を正しく処理することが、数値必要ありません、それらのアプリケーションを使用して操作するテキストの成果物に先行します。</span><span class="sxs-lookup"><span data-stu-id="d332d-167">While many Linux applications will recognize and correctly handle a BOM, a number do not, leading to artifacts in text manipulated with those applications.</span></span>

<span data-ttu-id="d332d-168">**したがって**:</span><span class="sxs-lookup"><span data-stu-id="d332d-168">**Therefore**:</span></span>

- <span data-ttu-id="d332d-169">Windows アプリケーションと Windows PowerShell で主に作業している場合、BOM または utf-16 と utf-8 エンコードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d332d-169">If you work primarily with Windows applications and Windows PowerShell, you should prefer an encoding like UTF-8 with BOM or UTF-16.</span></span>
- <span data-ttu-id="d332d-170">プラットフォーム間で作業している場合は、bom が付加された utf-8 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d332d-170">If you work across platforms, you should prefer UTF-8 with BOM.</span></span>
- <span data-ttu-id="d332d-171">Linux に関連付けられているコンテキストで主に作業する場合は、BOM なしの utf-8 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d332d-171">If you work mainly in Linux-associated contexts, you should prefer UTF-8 without BOM.</span></span>
- <span data-ttu-id="d332d-172">Windows 1252、ラテン語-1 は、可能であれば避ける必要のあるレガシ エンコーディング基本的にです。</span><span class="sxs-lookup"><span data-stu-id="d332d-172">Windows-1252 and latin-1 are essentially legacy encodings that you should avoid if possible.</span></span>
  <span data-ttu-id="d332d-173">ただし、一部の古い Windows アプリケーションは、それらに依存可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d332d-173">However, some older Windows applications may depend on them.</span></span>
- <span data-ttu-id="d332d-174">スクリプトの署名がある注目すべきも[エンコード依存](https://github.com/PowerShell/PowerShell/issues/3466)、つまり署名されたスクリプトのエンコードの変更が必要場合します。</span><span class="sxs-lookup"><span data-stu-id="d332d-174">It's also worth noting that script signing is [encoding-dependent](https://github.com/PowerShell/PowerShell/issues/3466), meaning a change of encoding on a signed script will require resigning.</span></span>

## <a name="configuring-vscode"></a><span data-ttu-id="d332d-175">VSCode を構成します。</span><span class="sxs-lookup"><span data-stu-id="d332d-175">Configuring VSCode</span></span>

<span data-ttu-id="d332d-176">VSCode の既定のエンコードは BOM なしの utf-8 です。</span><span class="sxs-lookup"><span data-stu-id="d332d-176">VSCode's default encoding is UTF-8 without BOM.</span></span>

<span data-ttu-id="d332d-177">設定する[VSCode のエンコード][]VSCode 設定には、(<kbd>Ctrl<kbd>+</kbd>、</kbd>) を設定し、`"files.encoding"`設定。</span><span class="sxs-lookup"><span data-stu-id="d332d-177">To set [VSCode's encoding][], go to the VSCode settings (<kbd>Ctrl<kbd>+</kbd>,</kbd>) and set the `"files.encoding"` setting:</span></span>

```json
"files.encoding": "utf8bom"
```

<span data-ttu-id="d332d-178">いくつか使用可能な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d332d-178">Some possible values are:</span></span>

- <span data-ttu-id="d332d-179">`utf8`: [Utf-8] BOM なし</span><span class="sxs-lookup"><span data-stu-id="d332d-179">`utf8`: [UTF-8] without BOM</span></span>
- <span data-ttu-id="d332d-180">`utf8bom`: [Utf-8] bom が付加されました。</span><span class="sxs-lookup"><span data-stu-id="d332d-180">`utf8bom`: [UTF-8] with BOM</span></span>
- <span data-ttu-id="d332d-181">`utf16le`: リトル エンディアン[utf-16]</span><span class="sxs-lookup"><span data-stu-id="d332d-181">`utf16le`: Little endian [UTF-16]</span></span>
- <span data-ttu-id="d332d-182">`utf16be`: ビッグ エンディアン[utf-16]</span><span class="sxs-lookup"><span data-stu-id="d332d-182">`utf16be`: Big endian [UTF-16]</span></span>
- <span data-ttu-id="d332d-183">`windows1252`: [Windows-1252]</span><span class="sxs-lookup"><span data-stu-id="d332d-183">`windows1252`: [Windows-1252]</span></span>

<span data-ttu-id="d332d-184">GUI ビューで、このドロップダウン リストを取得する必要があります。 または JSON での入力候補を表示します。</span><span class="sxs-lookup"><span data-stu-id="d332d-184">You should get a dropdown for this in the GUI view, or completions for it in the JSON view.</span></span>

<span data-ttu-id="d332d-185">可能な場合のエンコードを自動検出に、次を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="d332d-185">You can also add the following to autodetect encoding when possible:</span></span>

```json
"files.autoGuessEncoding": true
```

<span data-ttu-id="d332d-186">これらの設定をすべてのファイルの種類に影響しない場合は、VSCode は言語ごとの構成もできます。</span><span class="sxs-lookup"><span data-stu-id="d332d-186">If you don't want these settings to affect all files types, VSCode also allows per-language configurations.</span></span> <span data-ttu-id="d332d-187">設定を配置することで、言語固有の設定を作成、`[<language-name>]`フィールド。</span><span class="sxs-lookup"><span data-stu-id="d332d-187">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="d332d-188">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d332d-188">For example:</span></span>

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

## <a name="configuring-powershell"></a><span data-ttu-id="d332d-189">PowerShell を構成します。</span><span class="sxs-lookup"><span data-stu-id="d332d-189">Configuring PowerShell</span></span>

<span data-ttu-id="d332d-190">PowerShell の既定のエンコードのバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d332d-190">PowerShell's default encoding varies depending on version:</span></span>

- <span data-ttu-id="d332d-191">PowerShell 6 以降で既定のエンコーディング BOM なしの utf-8 すべてのプラットフォームでは。</span><span class="sxs-lookup"><span data-stu-id="d332d-191">In PowerShell 6+, the default encoding is UTF-8 without BOM on all platforms.</span></span>
- <span data-ttu-id="d332d-192">Windows PowerShell で、既定のエンコーディングは、通常、Windows 1252、拡張機能の[ラテン 1][]ISO 8859-1 とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d332d-192">In Windows PowerShell, the default encoding is usually Windows-1252, an extension of [latin-1][], also known as ISO 8859-1.</span></span>

<span data-ttu-id="d332d-193">PowerShell 5 以降では、この既定エンコーディングを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d332d-193">In PowerShell 5+ you can find your default encoding with this:</span></span>

```powershell
[psobject].Assembly.GetTypes() | Where-Object { $_.Name -eq 'ClrFacade'} |
  ForEach-Object {
    $_.GetMethod('GetDefaultEncoding', [System.Reflection.BindingFlags]'nonpublic,static').Invoke($null, @())
  }
```

<span data-ttu-id="d332d-194">次[スクリプト](https://gist.github.com/rjmholt/3d8dd4849f718c914132ce3c5b278e0e)BOM なしのスクリプトについては、PowerShell セッションのエンコードとは推測を判断するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d332d-194">The following [script](https://gist.github.com/rjmholt/3d8dd4849f718c914132ce3c5b278e0e) can be used to determine what encoding your PowerShell session infers for a script without a BOM.</span></span>

```powershell
$badBytes = [byte[]]@(0xC3, 0x80)
$utf8Str = [System.Text.Encoding]::UTF8.GetString($badBytes)
$bytes = [System.Text.Encoding]::ASCII.GetBytes('Write-Output "') + [byte[]]@(0xC3, 0x80) + [byte[]]@(0x22)
$path = Join-Path ([System.IO.Path]::GetTempPath()) 'encodingtest.ps1'

try
{
    [System.IO.File]::WriteAllBytes($path, $bytes)

    switch (& $path)
    {
        $utf8Str
        {
            return 'UTF-8'
            break
        }

        default
        {
            return 'Windows-1252'
            break
        }
    }
}
finally
{
    Remove-Item $path
}
```

<span data-ttu-id="d332d-195">一般的にはプロファイルの設定を使用して特定のエンコーディングを使用する PowerShell の構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d332d-195">It's possible to configure PowerShell to use a given encoding more generally using profile settings.</span></span> <span data-ttu-id="d332d-196">次の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d332d-196">See the following articles:</span></span>

- <span data-ttu-id="d332d-197">[@mklement0][StackOverflow で PowerShell のエンコードに関する回答](https://stackoverflow.com/a/40098904)します。</span><span class="sxs-lookup"><span data-stu-id="d332d-197">[@mklement0]'s [answer about PowerShell encoding on StackOverflow](https://stackoverflow.com/a/40098904).</span></span>
- <span data-ttu-id="d332d-198">[@rkeithhill][PowerShell で BOM なしの utf-8 入力に対処する方法のブログの投稿](https://rkeithhill.wordpress.com/2010/05/26/handling-native-exe-output-encoding-in-utf8-with-no-bom/)します。</span><span class="sxs-lookup"><span data-stu-id="d332d-198">[@rkeithhill]'s [blog post about dealing with BOM-less UTF-8 input in PowerShell](https://rkeithhill.wordpress.com/2010/05/26/handling-native-exe-output-encoding-in-utf8-with-no-bom/).</span></span>

<span data-ttu-id="d332d-199">PowerShell を使用して、特定の入力エンコードを強制することはできません。</span><span class="sxs-lookup"><span data-stu-id="d332d-199">It's not possible to force PowerShell to use a specific input encoding.</span></span> <span data-ttu-id="d332d-200">PowerShell 5.1 であると、Windows 1252 エンコード BOM が存在しない場合に既定の下。</span><span class="sxs-lookup"><span data-stu-id="d332d-200">PowerShell 5.1 and below default to Windows-1252 encoding when there's no BOM.</span></span> <span data-ttu-id="d332d-201">相互運用性の理由から、bom が付加された Unicode 形式でスクリプトを保存することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d332d-201">For interoperability reasons, it's best to save scripts in a Unicode format with a BOM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d332d-202">PowerShell スクリプトは、エンコード選択肢の影響を受ける可能性がありますまたは別のエンコードするようにスクリプトを再エンコードするタッチがある他のツール。</span><span class="sxs-lookup"><span data-stu-id="d332d-202">Any other tools you have that touch PowerShell scripts may be affected by your encoding choices or re-encode your scripts to another encoding.</span></span>

### <a name="existing-scripts"></a><span data-ttu-id="d332d-203">既存のスクリプト</span><span class="sxs-lookup"><span data-stu-id="d332d-203">Existing scripts</span></span>

<span data-ttu-id="d332d-204">ファイル システム上のスクリプトは、新しい選択したエンコードを再エンコードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d332d-204">Scripts already on the file system may need to be re-encoded to your new chosen encoding.</span></span> <span data-ttu-id="d332d-205">VSCode の下部にあるバーでは、utf-8 のラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d332d-205">In the bottom bar of VSCode, you'll see the label UTF-8.</span></span> <span data-ttu-id="d332d-206">クリックして、操作バーを開き、選択**エンコードで保存**します。</span><span class="sxs-lookup"><span data-stu-id="d332d-206">Click it to open the action bar and select **Save with encoding**.</span></span> <span data-ttu-id="d332d-207">そのファイルの新しいエンコードを選択することができますようになりました。</span><span class="sxs-lookup"><span data-stu-id="d332d-207">You can now pick a new encoding for that file.</span></span> <span data-ttu-id="d332d-208">参照してください[VSCode のエンコード][]詳しい手順についてはします。</span><span class="sxs-lookup"><span data-stu-id="d332d-208">See [VSCode's encoding][] for full instructions.</span></span>

<span data-ttu-id="d332d-209">複数のファイルを再エンコードする必要がある場合は、次のスクリプトを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d332d-209">If you need to re-encode multiple files, you can use the following script:</span></span>

```powershell
Get-ChildItem *.ps1 -Recurse | ForEach-Object {
    $content = Get-Content -Path $_
    Set-Content -Path $_.Fullname -Value $content -Encoding UTF8 -PassThru -Force
}
```

### <a name="the-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="d332d-210">PowerShell Integrated Scripting Environment (ISE)</span><span class="sxs-lookup"><span data-stu-id="d332d-210">The PowerShell Integrated Scripting Environment (ISE)</span></span>

<span data-ttu-id="d332d-211">PowerShell ISE を使用してスクリプトを編集する場合は、あるエンコード設定を同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d332d-211">If you also edit scripts using the PowerShell ISE, you need to synchronize your encoding settings there.</span></span>

<span data-ttu-id="d332d-212">ISE は、BOM を受け入れる必要があるが、またをするためにリフレクションを使用して[エンコードを設定する](https://bensonxion.wordpress.com/2012/04/25/powershell-ise-default-saveas-encoding/)します。</span><span class="sxs-lookup"><span data-stu-id="d332d-212">The ISE should honor a BOM, but it's also possible to use reflection to [set the encoding](https://bensonxion.wordpress.com/2012/04/25/powershell-ise-default-saveas-encoding/).</span></span>
<span data-ttu-id="d332d-213">これは新興企業間で保持することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d332d-213">Note that this wouldn't be persisted between startups.</span></span>

### <a name="source-control-software"></a><span data-ttu-id="d332d-214">ソース管理ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="d332d-214">Source control software</span></span>

<span data-ttu-id="d332d-215">Git など、いくつかのソース管理ツールは、エンコーディングを無視します。git は、バイト数を追跡するだけです。</span><span class="sxs-lookup"><span data-stu-id="d332d-215">Some source control tools, such as git, ignore encodings; git just tracks the bytes.</span></span>
<span data-ttu-id="d332d-216">、TFS、Mercurial、などがあります。</span><span class="sxs-lookup"><span data-stu-id="d332d-216">Others, like TFS or Mercurial, may not.</span></span> <span data-ttu-id="d332d-217">さらにいくつかの git ベースのツールは、テキストをデコードに依存します。</span><span class="sxs-lookup"><span data-stu-id="d332d-217">Even some git-based tools rely on decoding text.</span></span>

<span data-ttu-id="d332d-218">これが、大文字と小文字、ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d332d-218">When this is the case, make sure you:</span></span>

- <span data-ttu-id="d332d-219">VSCode 構成に合わせて、ソース管理にエンコードするテキストを構成します。</span><span class="sxs-lookup"><span data-stu-id="d332d-219">Configure the text encoding in your source control to match your VSCode configuration.</span></span>
- <span data-ttu-id="d332d-220">すべてのファイルが関連のエンコードでソース管理にチェックインされることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d332d-220">Ensure all your files are checked into source control in the relevant encoding.</span></span>
- <span data-ttu-id="d332d-221">ソース管理から受信したエンコードへの変更に注意します。</span><span class="sxs-lookup"><span data-stu-id="d332d-221">Be wary of changes to the encoding received through source control.</span></span> <span data-ttu-id="d332d-222">このキーの署名とは、差分変更が、(バイトは文字がない) ために変更されているような場所を示すです。</span><span class="sxs-lookup"><span data-stu-id="d332d-222">A key sign of this is a diff indicating changes but where nothing seems to have changed (because bytes have but characters have not).</span></span>

### <a name="collaborators-environments"></a><span data-ttu-id="d332d-223">コラボレーターの環境</span><span class="sxs-lookup"><span data-stu-id="d332d-223">Collaborators' environments</span></span>

<span data-ttu-id="d332d-224">ソース管理を構成するには、上には、PowerShell ファイルを再エンコードすることによって、エンコードをオーバーライドする設定を共有しているファイルをコラボレーターがないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d332d-224">On top of configuring source control, ensure that your collaborators on any files you share don't have settings that override your encoding by re-encoding PowerShell files.</span></span>

### <a name="other-programs"></a><span data-ttu-id="d332d-225">その他のプログラム</span><span class="sxs-lookup"><span data-stu-id="d332d-225">Other programs</span></span>

<span data-ttu-id="d332d-226">読み取りまたは書き込みの PowerShell スクリプトを他のプログラムは、再エンコード可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d332d-226">Any other program that reads or writes a PowerShell script may re-encode it.</span></span>

<span data-ttu-id="d332d-227">いくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d332d-227">Some examples are:</span></span>

- <span data-ttu-id="d332d-228">クリップボードを使用すると、スクリプトをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d332d-228">Using the clipboard to copy and paste a script.</span></span> <span data-ttu-id="d332d-229">これは、ようなシナリオで共通です。</span><span class="sxs-lookup"><span data-stu-id="d332d-229">This is common in scenarios like:</span></span>
  - <span data-ttu-id="d332d-230">VM にスクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d332d-230">Copying a script into a VM</span></span>
  - <span data-ttu-id="d332d-231">電子メールまたは web ページからスクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d332d-231">Copying a script out of an email or webpage</span></span>
  - <span data-ttu-id="d332d-232">Microsoft Word や PowerPoint のドキュメントの内外にスクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d332d-232">Copying a script into or out of a Microsoft Word or PowerPoint document</span></span>
- <span data-ttu-id="d332d-233">他のテキスト エディターなど。</span><span class="sxs-lookup"><span data-stu-id="d332d-233">Other text editors, such as:</span></span>
  - <span data-ttu-id="d332d-234">メモ帳</span><span class="sxs-lookup"><span data-stu-id="d332d-234">Notepad</span></span>
  - <span data-ttu-id="d332d-235">vim</span><span class="sxs-lookup"><span data-stu-id="d332d-235">vim</span></span>
  - <span data-ttu-id="d332d-236">その他の PowerShell スクリプト エディター</span><span class="sxs-lookup"><span data-stu-id="d332d-236">Any other PowerShell script editor</span></span>
- <span data-ttu-id="d332d-237">テキストのようなユーティリティを編集:</span><span class="sxs-lookup"><span data-stu-id="d332d-237">Text editing utilities, like:</span></span>
  - `Get-Content`/`Set-Content`/`Out-File`
  - <span data-ttu-id="d332d-238">などの PowerShell リダイレクト演算子`>`と `>>`</span><span class="sxs-lookup"><span data-stu-id="d332d-238">PowerShell redirection operators like `>` and `>>`</span></span>
  - `sed`/`awk`
- <span data-ttu-id="d332d-239">ようなファイルの転送プログラム。</span><span class="sxs-lookup"><span data-stu-id="d332d-239">File transfer programs, like:</span></span>
  - <span data-ttu-id="d332d-240">スクリプトをダウンロードするときに、web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="d332d-240">A web browser, when downloading scripts</span></span>
  - <span data-ttu-id="d332d-241">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="d332d-241">A file share</span></span>

<span data-ttu-id="d332d-242">テキストではなくバイトでこれらのツールのいくつかの処理が、エンコーディングの構成は、他のユーザー。</span><span class="sxs-lookup"><span data-stu-id="d332d-242">Some of these tools deal in bytes rather than text, but others offer encoding configurations.</span></span> <span data-ttu-id="d332d-243">エンコーディングを構成する必要があるような場合、問題を回避するエンコードのエディターとして同じする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d332d-243">In those cases where you need to configure an encoding, you need to make it the same as your editor encoding to prevent problems.</span></span>

## <a name="other-resources-on-encoding-in-powershell"></a><span data-ttu-id="d332d-244">PowerShell でのエンコードでは、その他のリソース</span><span class="sxs-lookup"><span data-stu-id="d332d-244">Other resources on encoding in PowerShell</span></span>

<span data-ttu-id="d332d-245">いくつか他の優れた投稿はエンコーディングと PowerShell でのエンコードを構成する読み取りでは、価値のあります。</span><span class="sxs-lookup"><span data-stu-id="d332d-245">There are a few other nice posts on encoding and configuring encoding in PowerShell that are worth a read:</span></span>

- <span data-ttu-id="d332d-246">[@mklement0][StackOverflow で PowerShell のエンコードの概要](https://stackoverflow.com/questions/40098771/changing-powershells-default-output-encoding-to-utf-8)</span><span class="sxs-lookup"><span data-stu-id="d332d-246">[@mklement0]'s [summary of PowerShell encoding on StackOverflow](https://stackoverflow.com/questions/40098771/changing-powershells-default-output-encoding-to-utf-8)</span></span>
- <span data-ttu-id="d332d-247">問題をエンコードするためには、vscode-PowerShell で以前の問題が開かれます。</span><span class="sxs-lookup"><span data-stu-id="d332d-247">Previous issues opened on vscode-PowerShell for encoding problems:</span></span>
  - [<span data-ttu-id="d332d-248">#1308</span><span class="sxs-lookup"><span data-stu-id="d332d-248">#1308</span></span>](https://github.com/PowerShell/vscode-powershell/issues/1308)
  - [<span data-ttu-id="d332d-249">#1628</span><span class="sxs-lookup"><span data-stu-id="d332d-249">#1628</span></span>](https://github.com/PowerShell/vscode-powershell/issues/1628)
  - [<span data-ttu-id="d332d-250">#1680</span><span class="sxs-lookup"><span data-stu-id="d332d-250">#1680</span></span>](https://github.com/PowerShell/vscode-powershell/issues/1680)
  - [<span data-ttu-id="d332d-251">#1744</span><span class="sxs-lookup"><span data-stu-id="d332d-251">#1744</span></span>](https://github.com/PowerShell/vscode-powershell/issues/1744)
  - [<span data-ttu-id="d332d-252">#1751</span><span class="sxs-lookup"><span data-stu-id="d332d-252">#1751</span></span>](https://github.com/PowerShell/vscode-powershell/issues/1751)
- [<span data-ttu-id="d332d-253">クラシック*Joel on Software* Unicode について記述</span><span class="sxs-lookup"><span data-stu-id="d332d-253">The classic *Joel on Software* write up about Unicode</span></span>](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)
- [<span data-ttu-id="d332d-254">.NET Standard でのエンコード</span><span class="sxs-lookup"><span data-stu-id="d332d-254">Encoding in .NET Standard</span></span>](https://github.com/dotnet/standard/issues/260#issuecomment-289549508)


[@mklement0]: https://github.com/mklement0
[@rkeithhill]: https://github.com/rkeithhill
[Windows-1252]: https://wikipedia.org/wiki/Windows-1252
[ラテン 1]: https://wikipedia.org/wiki/ISO/IEC_8859-1
[latin-1]: https://wikipedia.org/wiki/ISO/IEC_8859-1
[UTF-8]: https://wikipedia.org/wiki/UTF-8
[バイト オーダー マーク]: https://wikipedia.org/wiki/Byte_order_mark
[byte-order mark]: https://wikipedia.org/wiki/Byte_order_mark
[UTF-16]: https://wikipedia.org/wiki/UTF-16
[言語サーバー プロトコル]: https://microsoft.github.io/language-server-protocol/
[Language Server Protocol]: https://microsoft.github.io/language-server-protocol/
[VSCode のエンコード]: https://code.visualstudio.com/docs/editor/codebasics#_file-encoding-support
[VSCode's encoding]: https://code.visualstudio.com/docs/editor/codebasics#_file-encoding-support
