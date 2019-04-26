---
title: VSCode と PowerShell でのファイルのエンコードの概要
description: VSCode と PowerShell でのファイルのエンコードの構成
ms.date: 02/28/2019
ms.openlocfilehash: 6a00e45b3700f72f78e2fbcdf6e317f3a17b53c0
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058439"
---
# <a name="understanding-file-encoding-in-vscode-and-powershell"></a><span data-ttu-id="f6b75-103">VSCode と PowerShell でのファイルのエンコードの概要</span><span class="sxs-lookup"><span data-stu-id="f6b75-103">Understanding file encoding in VSCode and PowerShell</span></span>

<span data-ttu-id="f6b75-104">VS Code を使用して PowerShell スクリプトを作成および編集するときは、正しい文字エンコード形式を使用してファイルを保存することが重要です。</span><span class="sxs-lookup"><span data-stu-id="f6b75-104">When using VS Code to create and edit PowerShell scripts, it is important that your files are saved using the correct character encoding format.</span></span>

## <a name="what-is-file-encoding-and-why-is-it-important"></a><span data-ttu-id="f6b75-105">ファイルのエンコードの概要とそれが重要な理由</span><span class="sxs-lookup"><span data-stu-id="f6b75-105">What is file encoding and why is it important?</span></span>

<span data-ttu-id="f6b75-106">VSCode により、人間が文字列をバッファーに入力することと、バイトのブロックをファイル システムに読み取りおよび書き込みすることの間のインターフェイスが管理されます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-106">VSCode manages the interface between a human entering strings of characters into a buffer and reading/writing blocks of bytes to the filesystem.</span></span> <span data-ttu-id="f6b75-107">VSCode によりファイルが保存されるときに、テキスト エンコードが保存に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-107">When VSCode saves a file, it uses a text encoding to do this.</span></span>

<span data-ttu-id="f6b75-108">同様に、PowerShell によりスクリプトが実行されるときは、ファイルを PowerShell プログラムに再構築するために、ファイル内のバイトを文字に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-108">Similarly, when PowerShell runs a script it must convert the bytes in a file to characters to reconstruct the file into a PowerShell program.</span></span> <span data-ttu-id="f6b75-109">VSCode によりファイルが書き込まれ、PowerShell によりファイルが読み取られるため、同じエンコード システムを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-109">Since VSCode writes the file and PowerShell reads the file, they need to use the same encoding system.</span></span> <span data-ttu-id="f6b75-110">PowerShell スクリプトを解析するこのプロセスは、*バイト* -> *文字* -> *トークン* -> *抽象構文木* -> *実行*の順に行われます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-110">This process of parsing a PowerShell script goes: *bytes* -> *characters* -> *tokens* -> *abstract syntax tree* -> *execution*.</span></span>

<span data-ttu-id="f6b75-111">VSCode と PowerShell のいずれも、実用的な既定のエンコード構成でインストールされています。</span><span class="sxs-lookup"><span data-stu-id="f6b75-111">Both VSCode and PowerShell are installed with a sensible default encoding configuration.</span></span> <span data-ttu-id="f6b75-112">ただし、PowerShell により使用される既定のエンコードは、PowerShell Core (v6.x) のリリースで変わりました。</span><span class="sxs-lookup"><span data-stu-id="f6b75-112">However, the default encoding used by PowerShell has changed with the release of PowerShell Core (v6.x).</span></span> <span data-ttu-id="f6b75-113">VSCode で PowerShell または PowerShell 拡張機能を使用しても確実に問題がないようにするには、VSCode と PowerShell の設定を正しく構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-113">To ensure you have no problems using PowerShell or the PowerShell extension in VSCode, you need to configure your VSCode and PowerShell settings properly.</span></span>

## <a name="common-causes-of-encoding-issues"></a><span data-ttu-id="f6b75-114">エンコード問題の一般的な原因</span><span class="sxs-lookup"><span data-stu-id="f6b75-114">Common causes of encoding issues</span></span>

<span data-ttu-id="f6b75-115">エンコードの問題は、VSCode またはスクリプト ファイルのエンコードが、想定される PowerShell のエンコードと一致しない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="f6b75-115">Encoding problems occur when the encoding of VSCode or your script file does not match the expected encoding of PowerShell.</span></span> <span data-ttu-id="f6b75-116">PowerShell でファイルのエンコードが自動的に決定される方法はありません。</span><span class="sxs-lookup"><span data-stu-id="f6b75-116">There is no way for PowerShell to automatically determine the file encoding.</span></span>

<span data-ttu-id="f6b75-117">[7 ビット ASCII 文字セット](https://ascii.cl/)以外の文字を使用している場合は、エンコードの問題が発生する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-117">You're more likely to have encoding problems when you're using characters not in the [7-bit ASCII character set](https://ascii.cl/).</span></span> <span data-ttu-id="f6b75-118">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f6b75-118">For example:</span></span>

- <span data-ttu-id="f6b75-119">アクセント付きラテン文字 (`É`、`ü`)</span><span class="sxs-lookup"><span data-stu-id="f6b75-119">Accented latin characters (`É`, `ü`)</span></span>
- <span data-ttu-id="f6b75-120">キリル文字などの非ラテン文字 (`Д`、`Ц`)</span><span class="sxs-lookup"><span data-stu-id="f6b75-120">Non-latin characters like Cyrillic (`Д`, `Ц`)</span></span>
- <span data-ttu-id="f6b75-121">漢字 (`脚`、`本`)</span><span class="sxs-lookup"><span data-stu-id="f6b75-121">Han Chinese (`脚`, `本`)</span></span>

<span data-ttu-id="f6b75-122">エンコードの問題の一般的な理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6b75-122">Common reasons for encoding issues are:</span></span>

- <span data-ttu-id="f6b75-123">VSCode と PowerShell のエンコードが既定から変更されていません。</span><span class="sxs-lookup"><span data-stu-id="f6b75-123">The encodings of VSCode and PowerShell have not been changed from their defaults.</span></span> <span data-ttu-id="f6b75-124">PowerShell 5.1 以下では、既定のエンコードは VSCode とは異なります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-124">For PowerShell 5.1 and below, the default encoding is different from VSCode's.</span></span>
- <span data-ttu-id="f6b75-125">別のエディターでファイルが開かれ、新しいエンコードで上書きされました。</span><span class="sxs-lookup"><span data-stu-id="f6b75-125">Another editor has opened and overwritten the file in a new encoding.</span></span> <span data-ttu-id="f6b75-126">多くの場合、これは ISE で発生します。</span><span class="sxs-lookup"><span data-stu-id="f6b75-126">This often happens with the ISE.</span></span>
- <span data-ttu-id="f6b75-127">VSCode または PowerShell で想定されているエンコードとは異なるエンコードでファイルがソース管理にチェックインされています。</span><span class="sxs-lookup"><span data-stu-id="f6b75-127">The file is checked into source control in an encoding that is different from what VSCode or PowerShell expects.</span></span> <span data-ttu-id="f6b75-128">これは、共同作業者が異なるエンコード構成のエディターを使用している場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-128">This can happen when collaborators use editors with different encoding configurations.</span></span>

### <a name="how-to-tell-when-you-have-encoding-issues"></a><span data-ttu-id="f6b75-129">エンコードの問題が発生したときの判断方法</span><span class="sxs-lookup"><span data-stu-id="f6b75-129">How to tell when you have encoding issues</span></span>

<span data-ttu-id="f6b75-130">多くの場合、エンコード エラーはスクリプト内の解析エラーとして現れます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-130">Often encoding errors present themselves as parse errors in scripts.</span></span> <span data-ttu-id="f6b75-131">スクリプト内に通常とは異なる文字シーケンスが見つかった場合は、それが問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-131">If you find strange character sequences in your script, this can be the problem.</span></span> <span data-ttu-id="f6b75-132">以下の例では、半角ダッシュ (`–`) が `â€“` という文字で表示されています。</span><span class="sxs-lookup"><span data-stu-id="f6b75-132">In the example below, an en-dash (`–`) appears as the characters `â€“`:</span></span>

```Output
Send-MailMessage : A positional parameter cannot be found that accepts argument 'Testing FuseMail SMTP...'.
At C:\Users\<User>\<OneDrive>\Development\PowerShell\Scripts\Send-EmailUsingSmtpRelay.ps1:6 char:1
+ Send-MailMessage â€“From $from â€“To $recipient1 â€“Subject $subject  ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Send-MailMessage], ParameterBindingException
    + FullyQualifiedErrorId : PositionalParameterNotFound,Microsoft.PowerShell.Commands.SendMailMessage
```

<span data-ttu-id="f6b75-133">この問題は、VSCode により UTF-8 の文字 `–` がバイト `0xE2 0x80 0x93` としてエンコードされるために発生します。</span><span class="sxs-lookup"><span data-stu-id="f6b75-133">This problem occurs because VSCode encodes the character `–` in UTF-8 as the bytes `0xE2 0x80 0x93`.</span></span>
<span data-ttu-id="f6b75-134">このようなバイトが Windows-1252 としてデコードされると、`â€“` という文字に解釈されます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-134">When these bytes are decoded as Windows-1252, they are interpreted as the characters `â€“`.</span></span>

<span data-ttu-id="f6b75-135">よく見られる通常とは異なる文字シーケンスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f6b75-135">Some strange character sequences that you might see include:</span></span>

<!-- markdownlint-disable MD038 -->
- <span data-ttu-id="f6b75-136">`–` の代わりに `â€“`</span><span class="sxs-lookup"><span data-stu-id="f6b75-136">`â€“` instead of `–`</span></span>
- <span data-ttu-id="f6b75-137">`—` の代わりに `â€”`</span><span class="sxs-lookup"><span data-stu-id="f6b75-137">`â€”` instead of `—`</span></span>
- <span data-ttu-id="f6b75-138">`Ä` の代わりに `Ã„2`</span><span class="sxs-lookup"><span data-stu-id="f6b75-138">`Ã„2` instead of `Ä`</span></span>
- <span data-ttu-id="f6b75-139">` ` の代わりに `Â` (改行なしスペース)</span><span class="sxs-lookup"><span data-stu-id="f6b75-139">`Â` instead of ` `  (a non-breaking space)</span></span>
- <span data-ttu-id="f6b75-140">`é` の代わりに `Ã©`</span><span class="sxs-lookup"><span data-stu-id="f6b75-140">`Ã©` instead of `é`</span></span>
<!-- markdownlint-enable MD038 -->

<span data-ttu-id="f6b75-141">こちらの便利な[関連ドキュメント](https://www.i18nqa.com/debug/utf8-debug.html)には、UTF-8/Windows-1252 エンコードの問題を示す一般的なパターンの一覧が掲載されています。</span><span class="sxs-lookup"><span data-stu-id="f6b75-141">This handy [reference](https://www.i18nqa.com/debug/utf8-debug.html) lists the common patterns that indicate a UTF-8/Windows-1252 encoding problem.</span></span>

## <a name="how-the-powershell-extension-in-vscode-interacts-with-encodings"></a><span data-ttu-id="f6b75-142">VSCode の PowerShell 拡張機能とエンコードの相互作用</span><span class="sxs-lookup"><span data-stu-id="f6b75-142">How the PowerShell extension in VSCode interacts with encodings</span></span>

<span data-ttu-id="f6b75-143">PowerShell 拡張機能は、さまざまな方法でスクリプトとやりとりします。</span><span class="sxs-lookup"><span data-stu-id="f6b75-143">The PowerShell extension interacts with scripts in a number of ways:</span></span>

1. <span data-ttu-id="f6b75-144">スクリプトが VSCode により編集されると、そのコンテンツは VSCode によって拡張機能に送信されます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-144">When scripts are edited in VSCode, the contents are sent by VSCode to the extension.</span></span> <span data-ttu-id="f6b75-145">[言語サーバー プロトコル][]では、このコンテンツを UTF-8 で転送することを義務付けています。</span><span class="sxs-lookup"><span data-stu-id="f6b75-145">The [Language Server Protocol][] mandates that this content is transferred in UTF-8.</span></span> <span data-ttu-id="f6b75-146">そのため、拡張機能が不適切なエンコードが取得されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f6b75-146">Therefore, it is not possible for the extension to get the wrong encoding.</span></span>
2. <span data-ttu-id="f6b75-147">統合されたコンソールでスクリプトを直接実行されると、PowerShell によってファイルから直接読み取られます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-147">When scripts are executed directly in the Integrated Console, they're read from the file by PowerShell directly.</span></span> <span data-ttu-id="f6b75-148">PowerShell のエンコードが VSCode のエンコードと異なる場合は、ここで何か問題が起こる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-148">If PowerShell's encoding differs from VSCode's, something can go wrong here.</span></span>
3. <span data-ttu-id="f6b75-149">VSCode で開かれているスクリプトにより VSCode で開かれていない別のスクリプトを参照されている場合、拡張機能によりそのスクリプトのコンテンツがファイル システムから読み込まれることになります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-149">When a script that is open in VSCode references another script that is not open in VSCode, the extension falls back to loading that script's content from the file system.</span></span> <span data-ttu-id="f6b75-150">PowerShell 拡張機能の既定は UTF-8 エンコードですが、[バイト オーダー マーク][] (BOM) 検出を使用して正しいエンコードが選択されます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-150">The PowerShell extension defaults to UTF-8 encoding, but uses [byte-order mark][], or BOM, detection to select the correct encoding.</span></span>

<span data-ttu-id="f6b75-151">問題は、BOM なしの形式 (BOM なしの [UTF-8][] や [Windows-1252][] など) のエンコードを想定しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="f6b75-151">The problem occurs when assuming the encoding of BOM-less formats (like [UTF-8][] with no BOM and [Windows-1252][]).</span></span>
<span data-ttu-id="f6b75-152">PowerShell 拡張機能の既定値は UTF-8 です。</span><span class="sxs-lookup"><span data-stu-id="f6b75-152">The PowerShell extension defaults to UTF-8.</span></span> <span data-ttu-id="f6b75-153">この拡張機能では VSCode のエンコード設定を変更できません。</span><span class="sxs-lookup"><span data-stu-id="f6b75-153">The extension cannot change VSCode's encoding settings.</span></span>
<span data-ttu-id="f6b75-154">詳細については、[問題番号 824](https://github.com/Microsoft/vscode/issues/824) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6b75-154">For more information, see [issue #824](https://github.com/Microsoft/vscode/issues/824).</span></span>

## <a name="choosing-the-right-encoding"></a><span data-ttu-id="f6b75-155">適切なエンコードの選択</span><span class="sxs-lookup"><span data-stu-id="f6b75-155">Choosing the right encoding</span></span>

<span data-ttu-id="f6b75-156">システムやアプリケーションごとに使用しているエンコードが異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-156">Different systems and applications can use different encodings:</span></span>

- <span data-ttu-id="f6b75-157">現在、.NET Standard、Web、Linux の世界では、UTF-8 が主流のエンコードです。</span><span class="sxs-lookup"><span data-stu-id="f6b75-157">In .NET Standard, on the web, and in the Linux world, UTF-8 is now the dominant encoding.</span></span>
- <span data-ttu-id="f6b75-158">多くの .NET Framework アプリケーションは [UTF-16][] を使用しています。</span><span class="sxs-lookup"><span data-stu-id="f6b75-158">Many .NET Framework applications use [UTF-16][].</span></span> <span data-ttu-id="f6b75-159">歴史的な理由から、これは "Unicode" と呼ばれることもあり、現在では UTF-8 と UTF-16 の両方を含む広範な[標準](https://en.wikipedia.org/wiki/Unicode)を指しています。</span><span class="sxs-lookup"><span data-stu-id="f6b75-159">For historical reasons, this is sometimes called "Unicode", a term that now refers to a broad [standard](https://en.wikipedia.org/wiki/Unicode) that includes both UTF-8 and UTF-16.</span></span>
- <span data-ttu-id="f6b75-160">Windows では、Unicode より前のネイティブ アプリケーションの多くが既定で Windows-1252 を使用し続けています。</span><span class="sxs-lookup"><span data-stu-id="f6b75-160">On Windows, many native applications that predate Unicode continue to use Windows-1252 by default.</span></span>

<span data-ttu-id="f6b75-161">Unicode エンコードには、バイト オーダー マーク (BOM) の概念もあります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-161">Unicode encodings also have the concept of a byte-order mark (BOM).</span></span> <span data-ttu-id="f6b75-162">BOM はテキストの先頭にあり、これによりテキストが使用しているエンコードがデコーダーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-162">BOMs occur at the beginning of text to tell a decoder which encoding the text is using.</span></span> <span data-ttu-id="f6b75-163">マルチバイト エンコードの場合、BOM によりエンコードの[エンディアン](https://en.wikipedia.org/wiki/Endianness)が示されます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-163">For multi-byte encodings, the BOM also indicates [endianness](https://en.wikipedia.org/wiki/Endianness) of the encoding.</span></span> <span data-ttu-id="f6b75-164">BOM は、Unicode 以外のテキストにはまず出現しないバイトになるように設計されているため、BOM が存在する場合、そのテキストは Unicode であると合理的に推測できます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-164">BOMs are designed to be bytes that rarely occur in non-Unicode text, allowing a reasonable guess that text is Unicode when a BOM is present.</span></span>

<span data-ttu-id="f6b75-165">BOM はオプションであり、Linux の世界ではそれほど採用されていません。UTF-8 の信頼性の高い規則があらゆるところで使用されているためです。</span><span class="sxs-lookup"><span data-stu-id="f6b75-165">BOMs are optional and their adoption isn't as popular in the Linux world because a dependable convention of UTF-8 is used everywhere.</span></span> <span data-ttu-id="f6b75-166">ほとんどの Linux アプリケーションでは、テキスト入力が UTF-8 でエンコードされていると想定されています。</span><span class="sxs-lookup"><span data-stu-id="f6b75-166">Most Linux applications presume that text input is encoded in UTF-8.</span></span> <span data-ttu-id="f6b75-167">多くの Linux アプリケーションは BOM を認識して正しく処理しますが、認識しないものもあります。そのため、そのようなアプリケーションで処理されたテキストにアーティファクトが生じます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-167">While many Linux applications will recognize and correctly handle a BOM, a number do not, leading to artifacts in text manipulated with those applications.</span></span>

<span data-ttu-id="f6b75-168">**したがって**:</span><span class="sxs-lookup"><span data-stu-id="f6b75-168">**Therefore**:</span></span>

- <span data-ttu-id="f6b75-169">主に Windows アプリケーションと Windows PowerShell を使用している場合は、BOM ありの UTF-8 または UTF-16 のようなエンコードをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6b75-169">If you work primarily with Windows applications and Windows PowerShell, you should prefer an encoding like UTF-8 with BOM or UTF-16.</span></span>
- <span data-ttu-id="f6b75-170">複数のプラットフォームにまたがって作業する場合は、BOM ありの UTF-8 をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6b75-170">If you work across platforms, you should prefer UTF-8 with BOM.</span></span>
- <span data-ttu-id="f6b75-171">主に Linux 関連のコンテキストで作業する場合は、BOM なしの UTF-8 をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6b75-171">If you work mainly in Linux-associated contexts, you should prefer UTF-8 without BOM.</span></span>
- <span data-ttu-id="f6b75-172">Windows-1252 とラテン-1 は基本的にレガシ エンコードであり、できれば避けてください。</span><span class="sxs-lookup"><span data-stu-id="f6b75-172">Windows-1252 and latin-1 are essentially legacy encodings that you should avoid if possible.</span></span>
  <span data-ttu-id="f6b75-173">ただし、一部の古い Windows アプリケーションではそれらに依存している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-173">However, some older Windows applications may depend on them.</span></span>
- <span data-ttu-id="f6b75-174">スクリプトの署名は[エンコードに依存している](https://github.com/PowerShell/PowerShell/issues/3466)点にも注意してください。つまり、署名されたスクリプトのエンコードを変更するには再署名が必要です。</span><span class="sxs-lookup"><span data-stu-id="f6b75-174">It's also worth noting that script signing is [encoding-dependent](https://github.com/PowerShell/PowerShell/issues/3466), meaning a change of encoding on a signed script will require resigning.</span></span>

## <a name="configuring-vscode"></a><span data-ttu-id="f6b75-175">VSCode の構成</span><span class="sxs-lookup"><span data-stu-id="f6b75-175">Configuring VSCode</span></span>

<span data-ttu-id="f6b75-176">VSCode の既定のエンコードは BOM なしの UTF-8 です。</span><span class="sxs-lookup"><span data-stu-id="f6b75-176">VSCode's default encoding is UTF-8 without BOM.</span></span>

<span data-ttu-id="f6b75-177">[VSCode のエンコード][]を設定するには、VSCode の設定に移動し (<kbd>Ctrl</kbd>+<kbd>、</kbd>)、`"files.encoding"` 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6b75-177">To set [VSCode's encoding][], go to the VSCode settings (<kbd>Ctrl</kbd>+<kbd>,</kbd>) and set the `"files.encoding"` setting:</span></span>

```json
"files.encoding": "utf8bom"
```

<span data-ttu-id="f6b75-178">次のような値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-178">Some possible values are:</span></span>

- <span data-ttu-id="f6b75-179">`utf8`:BOM なしの [UTF-8]</span><span class="sxs-lookup"><span data-stu-id="f6b75-179">`utf8`: [UTF-8] without BOM</span></span>
- <span data-ttu-id="f6b75-180">`utf8bom`:BOM ありの [UTF-8]</span><span class="sxs-lookup"><span data-stu-id="f6b75-180">`utf8bom`: [UTF-8] with BOM</span></span>
- <span data-ttu-id="f6b75-181">`utf16le`:リトル エンディアン [UTF-16]</span><span class="sxs-lookup"><span data-stu-id="f6b75-181">`utf16le`: Little endian [UTF-16]</span></span>
- <span data-ttu-id="f6b75-182">`utf16be`:ビッグ エンディアン [UTF-16]</span><span class="sxs-lookup"><span data-stu-id="f6b75-182">`utf16be`: Big endian [UTF-16]</span></span>
- <span data-ttu-id="f6b75-183">`windows1252`:[Windows-1252]</span><span class="sxs-lookup"><span data-stu-id="f6b75-183">`windows1252`: [Windows-1252]</span></span>

<span data-ttu-id="f6b75-184">GUI ビューでこのドロップダウンを表示するか、JSON ビューですべてを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-184">You should get a dropdown for this in the GUI view, or completions for it in the JSON view.</span></span>

<span data-ttu-id="f6b75-185">また、可能であれば、以下を追加してエンコードを自動検出することもできます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-185">You can also add the following to autodetect encoding when possible:</span></span>

```json
"files.autoGuessEncoding": true
```

<span data-ttu-id="f6b75-186">これらの設定がすべてのファイルの種類に影響しないようにする場合、VSCode では言語ごとに構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-186">If you don't want these settings to affect all files types, VSCode also allows per-language configurations.</span></span> <span data-ttu-id="f6b75-187">`[<language-name>]` フィールドに設定を指定して、言語固有の設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="f6b75-187">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="f6b75-188">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f6b75-188">For example:</span></span>

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

## <a name="configuring-powershell"></a><span data-ttu-id="f6b75-189">PowerShell の構成</span><span class="sxs-lookup"><span data-stu-id="f6b75-189">Configuring PowerShell</span></span>

<span data-ttu-id="f6b75-190">PowerShell の既定のエンコードはバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-190">PowerShell's default encoding varies depending on version:</span></span>

- <span data-ttu-id="f6b75-191">PowerShell 6 以降では、既定のエンコードはすべてのプラットフォームで BOM なしの UTF-8 です。</span><span class="sxs-lookup"><span data-stu-id="f6b75-191">In PowerShell 6+, the default encoding is UTF-8 without BOM on all platforms.</span></span>
- <span data-ttu-id="f6b75-192">Windows PowerShell では、既定のエンコードは通常 Windows-1252 (拡張子は [latin-1][]) であり、ISO 8859-1 とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-192">In Windows PowerShell, the default encoding is usually Windows-1252, an extension of [latin-1][], also known as ISO 8859-1.</span></span>

<span data-ttu-id="f6b75-193">PowerShell 5 以降では、以下のように既定のエンコードを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-193">In PowerShell 5+ you can find your default encoding with this:</span></span>

```powershell
[psobject].Assembly.GetTypes() | Where-Object { $_.Name -eq 'ClrFacade'} |
  ForEach-Object {
    $_.GetMethod('GetDefaultEncoding', [System.Reflection.BindingFlags]'nonpublic,static').Invoke($null, @())
  }
```

<span data-ttu-id="f6b75-194">次の[スクリプト](https://gist.github.com/rjmholt/3d8dd4849f718c914132ce3c5b278e0e)を使用して、PowerShell セッションが BOM なしのスクリプトに対して推測するエンコードを決定できます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-194">The following [script](https://gist.github.com/rjmholt/3d8dd4849f718c914132ce3c5b278e0e) can be used to determine what encoding your PowerShell session infers for a script without a BOM.</span></span>

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

<span data-ttu-id="f6b75-195">より一般的にはプロファイル設定を使用して、特定のエンコードを使用するように PowerShell を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-195">It's possible to configure PowerShell to use a given encoding more generally using profile settings.</span></span> <span data-ttu-id="f6b75-196">次の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f6b75-196">See the following articles:</span></span>

- <span data-ttu-id="f6b75-197">[@mklement0] の [StackOverflow 上の PowerShell エンコードに関する回答](https://stackoverflow.com/a/40098904)。</span><span class="sxs-lookup"><span data-stu-id="f6b75-197">[@mklement0]'s [answer about PowerShell encoding on StackOverflow](https://stackoverflow.com/a/40098904).</span></span>
- <span data-ttu-id="f6b75-198">[@rkeithhill] の [PowerShell での BOM なしの UTF-8 入力の処理に関するブログ投稿](https://rkeithhill.wordpress.com/2010/05/26/handling-native-exe-output-encoding-in-utf8-with-no-bom/)。</span><span class="sxs-lookup"><span data-stu-id="f6b75-198">[@rkeithhill]'s [blog post about dealing with BOM-less UTF-8 input in PowerShell](https://rkeithhill.wordpress.com/2010/05/26/handling-native-exe-output-encoding-in-utf8-with-no-bom/).</span></span>

<span data-ttu-id="f6b75-199">PowerShell に特定の入力エンコードの使用を強制することはできません。</span><span class="sxs-lookup"><span data-stu-id="f6b75-199">It's not possible to force PowerShell to use a specific input encoding.</span></span> <span data-ttu-id="f6b75-200">BOM がない場合、PowerShell 5.1 以前では既定で Windows-1252 エンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-200">PowerShell 5.1 and below default to Windows-1252 encoding when there's no BOM.</span></span> <span data-ttu-id="f6b75-201">相互運用性の理由から、BOM ありの Unicode 形式でスクリプトを保存することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6b75-201">For interoperability reasons, it's best to save scripts in a Unicode format with a BOM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6b75-202">PowerShell スクリプトに触れる他のツールがある場合、そのツールがエンコードの選択の影響を受ける場合や、ツールによってスクリプトが別のエンコードに再エンコードされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-202">Any other tools you have that touch PowerShell scripts may be affected by your encoding choices or re-encode your scripts to another encoding.</span></span>

### <a name="existing-scripts"></a><span data-ttu-id="f6b75-203">既存のスクリプト</span><span class="sxs-lookup"><span data-stu-id="f6b75-203">Existing scripts</span></span>

<span data-ttu-id="f6b75-204">既にファイル システム上にあるスクリプトは、必要に応じて新しく選択したエンコードに再エンコードします。</span><span class="sxs-lookup"><span data-stu-id="f6b75-204">Scripts already on the file system may need to be re-encoded to your new chosen encoding.</span></span> <span data-ttu-id="f6b75-205">VSCode の下部のバーに、UTF-8 というラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-205">In the bottom bar of VSCode, you'll see the label UTF-8.</span></span> <span data-ttu-id="f6b75-206">クリックしてアクション バーを開き、**[エンコード付きで保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6b75-206">Click it to open the action bar and select **Save with encoding**.</span></span> <span data-ttu-id="f6b75-207">ここで、そのファイル用に新しいエンコードを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-207">You can now pick a new encoding for that file.</span></span> <span data-ttu-id="f6b75-208">完全な手順については、[VSCode のエンコード][]に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6b75-208">See [VSCode's encoding][] for full instructions.</span></span>

<span data-ttu-id="f6b75-209">複数のファイルを再エンコードする必要がある場合は、次のスクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-209">If you need to re-encode multiple files, you can use the following script:</span></span>

```powershell
Get-ChildItem *.ps1 -Recurse | ForEach-Object {
    $content = Get-Content -Path $_
    Set-Content -Path $_.Fullname -Value $content -Encoding UTF8 -PassThru -Force
}
```

### <a name="the-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="f6b75-210">PowerShell Integrated Scripting Environment (ISE)</span><span class="sxs-lookup"><span data-stu-id="f6b75-210">The PowerShell Integrated Scripting Environment (ISE)</span></span>

<span data-ttu-id="f6b75-211">PowerShell ISE を使用してスクリプトも編集する場合は、そこでエンコード設定を同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-211">If you also edit scripts using the PowerShell ISE, you need to synchronize your encoding settings there.</span></span>

<span data-ttu-id="f6b75-212">ISE で BOM を尊重する必要がありますが、リフレクションを使用して[エンコードを設定](https://bensonxion.wordpress.com/2012/04/25/powershell-ise-default-saveas-encoding/)することもできます。</span><span class="sxs-lookup"><span data-stu-id="f6b75-212">The ISE should honor a BOM, but it's also possible to use reflection to [set the encoding](https://bensonxion.wordpress.com/2012/04/25/powershell-ise-default-saveas-encoding/).</span></span>
<span data-ttu-id="f6b75-213">これはスタートアップ後には保持されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f6b75-213">Note that this wouldn't be persisted between startups.</span></span>

### <a name="source-control-software"></a><span data-ttu-id="f6b75-214">ソース管理ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="f6b75-214">Source control software</span></span>

<span data-ttu-id="f6b75-215">git などの一部のソース管理ツールはエンコードを無視します (git は単にバイトを追跡します)。</span><span class="sxs-lookup"><span data-stu-id="f6b75-215">Some source control tools, such as git, ignore encodings; git just tracks the bytes.</span></span>
<span data-ttu-id="f6b75-216">他のもの (Azure DevOps や Mercurial など) はそうではない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-216">Others, like Azure DevOps or Mercurial, may not.</span></span> <span data-ttu-id="f6b75-217">一部の git ベースのツールでさえ、テキストのデコードに依存しています。</span><span class="sxs-lookup"><span data-stu-id="f6b75-217">Even some git-based tools rely on decoding text.</span></span>

<span data-ttu-id="f6b75-218">その場合は、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f6b75-218">When this is the case, make sure you:</span></span>

- <span data-ttu-id="f6b75-219">VSCode の構成と一致するように、ソース管理でテキスト エンコードを構成します。</span><span class="sxs-lookup"><span data-stu-id="f6b75-219">Configure the text encoding in your source control to match your VSCode configuration.</span></span>
- <span data-ttu-id="f6b75-220">すべてのファイルが適切なエンコードでソース管理に確実にチェックインされているようにします。</span><span class="sxs-lookup"><span data-stu-id="f6b75-220">Ensure all your files are checked into source control in the relevant encoding.</span></span>
- <span data-ttu-id="f6b75-221">ソース管理を介して受信したエンコードの変化に注意します。</span><span class="sxs-lookup"><span data-stu-id="f6b75-221">Be wary of changes to the encoding received through source control.</span></span> <span data-ttu-id="f6b75-222">これを示す主な兆候は変化を示す差異ですが、何も変わっていないように見えます (バイトは変わっていますが、文字は変わっていないため)。</span><span class="sxs-lookup"><span data-stu-id="f6b75-222">A key sign of this is a diff indicating changes but where nothing seems to have changed (because bytes have but characters have not).</span></span>

### <a name="collaborators-environments"></a><span data-ttu-id="f6b75-223">共同作業者の環境</span><span class="sxs-lookup"><span data-stu-id="f6b75-223">Collaborators' environments</span></span>

<span data-ttu-id="f6b75-224">ソース管理の構成に加え、共有するファイルの共同作業者が PowerShell ファイルを再エンコードしてエンコードをオーバーライドする設定を確実に保持していないようにします。</span><span class="sxs-lookup"><span data-stu-id="f6b75-224">On top of configuring source control, ensure that your collaborators on any files you share don't have settings that override your encoding by re-encoding PowerShell files.</span></span>

### <a name="other-programs"></a><span data-ttu-id="f6b75-225">その他のプログラム</span><span class="sxs-lookup"><span data-stu-id="f6b75-225">Other programs</span></span>

<span data-ttu-id="f6b75-226">PowerShell スクリプトの読み取りまたは書き込みを行う他のプログラムが、再エンコードする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-226">Any other program that reads or writes a PowerShell script may re-encode it.</span></span>

<span data-ttu-id="f6b75-227">いくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f6b75-227">Some examples are:</span></span>

- <span data-ttu-id="f6b75-228">クリップボードを使用してスクリプトをコピーして貼り付ける。</span><span class="sxs-lookup"><span data-stu-id="f6b75-228">Using the clipboard to copy and paste a script.</span></span> <span data-ttu-id="f6b75-229">これは次のようなシナリオで一般的です。</span><span class="sxs-lookup"><span data-stu-id="f6b75-229">This is common in scenarios like:</span></span>
  - <span data-ttu-id="f6b75-230">スクリプトを VM にコピーする</span><span class="sxs-lookup"><span data-stu-id="f6b75-230">Copying a script into a VM</span></span>
  - <span data-ttu-id="f6b75-231">電子メールまたは Web ページからスクリプトをコピーする</span><span class="sxs-lookup"><span data-stu-id="f6b75-231">Copying a script out of an email or webpage</span></span>
  - <span data-ttu-id="f6b75-232">Microsoft Word または PowerPoint ドキュメントとの間でスクリプトをコピーする</span><span class="sxs-lookup"><span data-stu-id="f6b75-232">Copying a script into or out of a Microsoft Word or PowerPoint document</span></span>
- <span data-ttu-id="f6b75-233">次のようなその他のテキスト エディター:</span><span class="sxs-lookup"><span data-stu-id="f6b75-233">Other text editors, such as:</span></span>
  - <span data-ttu-id="f6b75-234">メモ帳</span><span class="sxs-lookup"><span data-stu-id="f6b75-234">Notepad</span></span>
  - <span data-ttu-id="f6b75-235">vim</span><span class="sxs-lookup"><span data-stu-id="f6b75-235">vim</span></span>
  - <span data-ttu-id="f6b75-236">その他の PowerShell スクリプト エディター</span><span class="sxs-lookup"><span data-stu-id="f6b75-236">Any other PowerShell script editor</span></span>
- <span data-ttu-id="f6b75-237">次のようなテキスト編集ユーティリティ:</span><span class="sxs-lookup"><span data-stu-id="f6b75-237">Text editing utilities, like:</span></span>
  - `Get-Content`/`Set-Content`/`Out-File`
  - <span data-ttu-id="f6b75-238">PowerShell リダイレクト演算子 (`>`、`>>` など)</span><span class="sxs-lookup"><span data-stu-id="f6b75-238">PowerShell redirection operators like `>` and `>>`</span></span>
  - `sed`/`awk`
- <span data-ttu-id="f6b75-239">次のようなファイル転送プログラム:</span><span class="sxs-lookup"><span data-stu-id="f6b75-239">File transfer programs, like:</span></span>
  - <span data-ttu-id="f6b75-240">Web ブラウザー (スクリプトのダウンロード時)</span><span class="sxs-lookup"><span data-stu-id="f6b75-240">A web browser, when downloading scripts</span></span>
  - <span data-ttu-id="f6b75-241">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="f6b75-241">A file share</span></span>

<span data-ttu-id="f6b75-242">このようなツールの一部はテキストではなくバイトで処理しますが、エンコードの構成機能が用意されているツールもあります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-242">Some of these tools deal in bytes rather than text, but others offer encoding configurations.</span></span> <span data-ttu-id="f6b75-243">エンコードを構成する必要がある場合は、問題を防ぐために、それをエディターのエンコードと同じにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-243">In those cases where you need to configure an encoding, you need to make it the same as your editor encoding to prevent problems.</span></span>

## <a name="other-resources-on-encoding-in-powershell"></a><span data-ttu-id="f6b75-244">PowerShell でのエンコードに関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="f6b75-244">Other resources on encoding in PowerShell</span></span>

<span data-ttu-id="f6b75-245">PowerShell でのエンコードとエンコードの構成に関するお勧めの投稿が他にもいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="f6b75-245">There are a few other nice posts on encoding and configuring encoding in PowerShell that are worth a read:</span></span>

- <span data-ttu-id="f6b75-246">[@mklement0] の [StackOverflow 上の PowerShell エンコードの概要](https://stackoverflow.com/questions/40098771/changing-powershells-default-output-encoding-to-utf-8)</span><span class="sxs-lookup"><span data-stu-id="f6b75-246">[@mklement0]'s [summary of PowerShell encoding on StackOverflow](https://stackoverflow.com/questions/40098771/changing-powershells-default-output-encoding-to-utf-8)</span></span>
- <span data-ttu-id="f6b75-247">エンコードの問題について vscode-PowerShell で開かれた以前の問題:</span><span class="sxs-lookup"><span data-stu-id="f6b75-247">Previous issues opened on vscode-PowerShell for encoding problems:</span></span>
  - [<span data-ttu-id="f6b75-248">#1308</span><span class="sxs-lookup"><span data-stu-id="f6b75-248">#1308</span></span>](https://github.com/PowerShell/vscode-powershell/issues/1308)
  - [<span data-ttu-id="f6b75-249">#1628</span><span class="sxs-lookup"><span data-stu-id="f6b75-249">#1628</span></span>](https://github.com/PowerShell/vscode-powershell/issues/1628)
  - [<span data-ttu-id="f6b75-250">#1680</span><span class="sxs-lookup"><span data-stu-id="f6b75-250">#1680</span></span>](https://github.com/PowerShell/vscode-powershell/issues/1680)
  - [<span data-ttu-id="f6b75-251">#1744</span><span class="sxs-lookup"><span data-stu-id="f6b75-251">#1744</span></span>](https://github.com/PowerShell/vscode-powershell/issues/1744)
  - [<span data-ttu-id="f6b75-252">#1751</span><span class="sxs-lookup"><span data-stu-id="f6b75-252">#1751</span></span>](https://github.com/PowerShell/vscode-powershell/issues/1751)
- [<span data-ttu-id="f6b75-253">*Joel on Software* が Unicode について書いた以前の投稿</span><span class="sxs-lookup"><span data-stu-id="f6b75-253">The classic *Joel on Software* write up about Unicode</span></span>](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)
- [<span data-ttu-id="f6b75-254">.NET Standard のエンコード</span><span class="sxs-lookup"><span data-stu-id="f6b75-254">Encoding in .NET Standard</span></span>](https://github.com/dotnet/standard/issues/260#issuecomment-289549508)


[@mklement0]: https://github.com/mklement0
[@rkeithhill]: https://github.com/rkeithhill
[Windows-1252]: https://wikipedia.org/wiki/Windows-1252
[latin-1]: https://wikipedia.org/wiki/ISO/IEC_8859-1
[UTF-8]: https://wikipedia.org/wiki/UTF-8
[バイト オーダー マーク]: https://wikipedia.org/wiki/Byte_order_mark
[byte-order mark]: https://wikipedia.org/wiki/Byte_order_mark
[UTF-16]: https://wikipedia.org/wiki/UTF-16
[言語サーバー プロトコル]: https://microsoft.github.io/language-server-protocol/
[Language Server Protocol]: https://microsoft.github.io/language-server-protocol/
[VSCode のエンコード]: https://code.visualstudio.com/docs/editor/codebasics#_file-encoding-support
[VSCode's encoding]: https://code.visualstudio.com/docs/editor/codebasics#_file-encoding-support
