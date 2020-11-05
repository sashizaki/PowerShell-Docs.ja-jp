---
title: VS Code と PowerShell でのファイルのエンコードの概要
description: VS Code と PowerShell でのファイルのエンコードの構成
ms.date: 02/28/2019
ms.openlocfilehash: afad189ff20a4e73d25f15c48d6c4982b18f29a3
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142550"
---
# <a name="understanding-file-encoding-in-vs-code-and-powershell"></a><span data-ttu-id="2d8c1-103">VS Code と PowerShell でのファイルのエンコードの概要</span><span class="sxs-lookup"><span data-stu-id="2d8c1-103">Understanding file encoding in VS Code and PowerShell</span></span>

<span data-ttu-id="2d8c1-104">VS Code を使用して PowerShell スクリプトを作成および編集するときは、正しい文字エンコード形式を使用してファイルを保存することが重要です。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-104">When using VS Code to create and edit PowerShell scripts, it is important that your files are saved using the correct character encoding format.</span></span>

## <a name="what-is-file-encoding-and-why-is-it-important"></a><span data-ttu-id="2d8c1-105">ファイルのエンコードの概要とそれが重要な理由</span><span class="sxs-lookup"><span data-stu-id="2d8c1-105">What is file encoding and why is it important?</span></span>

<span data-ttu-id="2d8c1-106">VS Code により、人間が文字列をバッファーに入力することと、バイトのブロックをファイル システムに読み取りおよび書き込みすることの間のインターフェイスが管理されます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-106">VS Code manages the interface between a human entering strings of characters into a buffer and reading/writing blocks of bytes to the filesystem.</span></span> <span data-ttu-id="2d8c1-107">VS Code では、ファイルを保存するとき、テキスト エンコードを使用して各文字がどのバイトになるかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-107">When VS Code saves a file, it uses a text encoding to decide what bytes each character becomes.</span></span> <span data-ttu-id="2d8c1-108">詳細については、「[about_Character_Encoding](/powershell/module/microsoft.powershell.core/about/about_character_encoding)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-108">For more information, see [about_Character_Encoding](/powershell/module/microsoft.powershell.core/about/about_character_encoding).</span></span>

<span data-ttu-id="2d8c1-109">同様に、PowerShell によりスクリプトが実行されるときは、ファイルを PowerShell プログラムに再構築するために、ファイル内のバイトを文字に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-109">Similarly, when PowerShell runs a script it must convert the bytes in a file to characters to reconstruct the file into a PowerShell program.</span></span> <span data-ttu-id="2d8c1-110">VS Code によりファイルが書き込まれ、PowerShell によりファイルが読み取られるため、これらでは同じエンコード システムを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-110">Since VS Code writes the file and PowerShell reads the file, they need to use the same encoding system.</span></span> <span data-ttu-id="2d8c1-111">PowerShell スクリプトを解析するこのプロセスは、 _バイト_ -> _文字_ -> _トークン_ -> _抽象構文木_ -> _実行_ の順に行われます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-111">This process of parsing a PowerShell script goes: _bytes_ -> _characters_ -> _tokens_ -> _abstract syntax tree_ -> _execution_.</span></span>

<span data-ttu-id="2d8c1-112">VS Code と PowerShell は両方とも、実用的な既定のエンコード構成でインストールされています。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-112">Both VS Code and PowerShell are installed with a sensible default encoding configuration.</span></span> <span data-ttu-id="2d8c1-113">ただし、PowerShell により使用される既定のエンコードは、PowerShell Core (v6.x) のリリースで変わりました。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-113">However, the default encoding used by PowerShell has changed with the release of PowerShell Core (v6.x).</span></span> <span data-ttu-id="2d8c1-114">VS Code で PowerShell または PowerShell 拡張機能を使用しても確実に問題がないようにするには、VS Code と PowerShell の設定を正しく構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-114">To ensure you have no problems using PowerShell or the PowerShell extension in VS Code, you need to configure your VS Code and PowerShell settings properly.</span></span>

## <a name="common-causes-of-encoding-issues"></a><span data-ttu-id="2d8c1-115">エンコード問題の一般的な原因</span><span class="sxs-lookup"><span data-stu-id="2d8c1-115">Common causes of encoding issues</span></span>

<span data-ttu-id="2d8c1-116">エンコードの問題は、VS Code またはスクリプト ファイルのエンコードが、想定される PowerShell のエンコードと一致しない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-116">Encoding problems occur when the encoding of VS Code or your script file does not match the expected encoding of PowerShell.</span></span> <span data-ttu-id="2d8c1-117">PowerShell でファイルのエンコードが自動的に決定される方法はありません。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-117">There is no way for PowerShell to automatically determine the file encoding.</span></span>

<span data-ttu-id="2d8c1-118">[7 ビット ASCII 文字セット](https://ascii.cl/)以外の文字を使用している場合は、エンコードの問題が発生する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-118">You're more likely to have encoding problems when you're using characters not in the [7-bit ASCII character set](https://ascii.cl/).</span></span> <span data-ttu-id="2d8c1-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-119">For example:</span></span>

<!-- markdownlint-disable MD038 -->
- <span data-ttu-id="2d8c1-120">em ダッシュ (`—`)、改行なしスペース (` `)、左二重引用符 (`"`) などのアルファベット以外の拡張文字</span><span class="sxs-lookup"><span data-stu-id="2d8c1-120">Extended non-letter characters like em-dash (`—`), non-breaking space (` `) or left double quotation mark (`"`)</span></span>
- <span data-ttu-id="2d8c1-121">アクセント付きラテン文字 (`É`、`ü`)</span><span class="sxs-lookup"><span data-stu-id="2d8c1-121">Accented latin characters (`É`, `ü`)</span></span>
- <span data-ttu-id="2d8c1-122">キリル文字などの非ラテン文字 (`Д`、`Ц`)</span><span class="sxs-lookup"><span data-stu-id="2d8c1-122">Non-latin characters like Cyrillic (`Д`, `Ц`)</span></span>
- <span data-ttu-id="2d8c1-123">CJK 文字 (`本`、`화`、`が`)</span><span class="sxs-lookup"><span data-stu-id="2d8c1-123">CJK characters (`本`, `화`, `が`)</span></span>

<span data-ttu-id="2d8c1-124">エンコードの問題の一般的な理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-124">Common reasons for encoding issues are:</span></span>

- <span data-ttu-id="2d8c1-125">VS Code と PowerShell のエンコードが既定値から変更されていません。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-125">The encodings of VS Code and PowerShell have not been changed from their defaults.</span></span> <span data-ttu-id="2d8c1-126">PowerShell 5.1 以下では、既定のエンコードは VS Code とは異なります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-126">For PowerShell 5.1 and below, the default encoding is different from VS Code's.</span></span>
- <span data-ttu-id="2d8c1-127">別のエディターでファイルが開かれ、新しいエンコードで上書きされました。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-127">Another editor has opened and overwritten the file in a new encoding.</span></span> <span data-ttu-id="2d8c1-128">多くの場合、これは ISE で発生します。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-128">This often happens with the ISE.</span></span>
- <span data-ttu-id="2d8c1-129">VS Code または PowerShell で想定されているエンコードとは異なるエンコードでファイルがソース管理にチェックインされています。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-129">The file is checked into source control in an encoding that is different from what VS Code or PowerShell expects.</span></span> <span data-ttu-id="2d8c1-130">これは、共同作業者が異なるエンコード構成のエディターを使用している場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-130">This can happen when collaborators use editors with different encoding configurations.</span></span>

### <a name="how-to-tell-when-you-have-encoding-issues"></a><span data-ttu-id="2d8c1-131">エンコードの問題が発生したときの判断方法</span><span class="sxs-lookup"><span data-stu-id="2d8c1-131">How to tell when you have encoding issues</span></span>

<span data-ttu-id="2d8c1-132">多くの場合、エンコード エラーはスクリプト内の解析エラーとして現れます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-132">Often encoding errors present themselves as parse errors in scripts.</span></span> <span data-ttu-id="2d8c1-133">スクリプト内に通常とは異なる文字シーケンスが見つかった場合は、それが問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-133">If you find strange character sequences in your script, this can be the problem.</span></span> <span data-ttu-id="2d8c1-134">以下の例では、半角ダッシュ (`–`) が `â&euro;"` という文字で表示されています。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-134">In the example below, an en-dash (`–`) appears as the characters `â&euro;"`:</span></span>

```Output
Send-MailMessage : A positional parameter cannot be found that accepts argument 'Testing FuseMail SMTP...'.
At C:\Users\<User>\<OneDrive>\Development\PowerShell\Scripts\Send-EmailUsingSmtpRelay.ps1:6 char:1
+ Send-MailMessage â&euro;"From $from â&euro;"To $recipient1 â&euro;"Subject $subject  ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Send-MailMessage], ParameterBindingException
    + FullyQualifiedErrorId : PositionalParameterNotFound,Microsoft.PowerShell.Commands.SendMailMessage
```

<span data-ttu-id="2d8c1-135">この問題は、VS Code により UTF-8 の文字 `–` がバイト `0xE2 0x80 0x93` としてエンコードされるために発生します。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-135">This problem occurs because VS Code encodes the character `–` in UTF-8 as the bytes `0xE2 0x80 0x93`.</span></span> <span data-ttu-id="2d8c1-136">このようなバイトが Windows-1252 としてデコードされると、`â&euro;"` という文字に解釈されます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-136">When these bytes are decoded as Windows-1252, they are interpreted as the characters `â&euro;"`.</span></span>

<span data-ttu-id="2d8c1-137">よく見られる通常とは異なる文字シーケンスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-137">Some strange character sequences that you might see include:</span></span>

<!-- markdownlint-disable MD038 -->
- <span data-ttu-id="2d8c1-138">`–` の代わりに `â&euro;"`</span><span class="sxs-lookup"><span data-stu-id="2d8c1-138">`â&euro;"` instead of `–`</span></span>
- <span data-ttu-id="2d8c1-139">`—` の代わりに `â&euro;"`</span><span class="sxs-lookup"><span data-stu-id="2d8c1-139">`â&euro;"` instead of `—`</span></span>
- <span data-ttu-id="2d8c1-140">`Ä` の代わりに `Ã„2`</span><span class="sxs-lookup"><span data-stu-id="2d8c1-140">`Ã„2` instead of `Ä`</span></span>
- <span data-ttu-id="2d8c1-141">` ` の代わりに `Â` (改行なしスペース)</span><span class="sxs-lookup"><span data-stu-id="2d8c1-141">`Â` instead of ` `  (a non-breaking space)</span></span>
- <span data-ttu-id="2d8c1-142">`é` の代わりに `Ã&copy;`</span><span class="sxs-lookup"><span data-stu-id="2d8c1-142">`Ã&copy;` instead of `é`</span></span>
<!-- markdownlint-enable MD038 -->

<span data-ttu-id="2d8c1-143">こちらの便利な[関連ドキュメント](https://www.i18nqa.com/debug/utf8-debug.html)には、UTF-8/Windows-1252 エンコードの問題を示す一般的なパターンの一覧が掲載されています。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-143">This handy [reference](https://www.i18nqa.com/debug/utf8-debug.html) lists the common patterns that indicate a UTF-8/Windows-1252 encoding problem.</span></span>

## <a name="how-the-powershell-extension-in-vs-code-interacts-with-encodings"></a><span data-ttu-id="2d8c1-144">VS Code の PowerShell 拡張機能とエンコードの相互作用</span><span class="sxs-lookup"><span data-stu-id="2d8c1-144">How the PowerShell extension in VS Code interacts with encodings</span></span>

<span data-ttu-id="2d8c1-145">PowerShell 拡張機能は、さまざまな方法でスクリプトとやりとりします。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-145">The PowerShell extension interacts with scripts in a number of ways:</span></span>

1. <span data-ttu-id="2d8c1-146">スクリプトが VS Code により編集されると、そのコンテンツは VS Code によって拡張機能に送信されます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-146">When scripts are edited in VS Code, the contents are sent by VS Code to the extension.</span></span> <span data-ttu-id="2d8c1-147">[言語サーバー プロトコル][]では、このコンテンツを UTF-8 で転送することを義務付けています。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-147">The [Language Server Protocol][] mandates that this content is transferred in UTF-8.</span></span> <span data-ttu-id="2d8c1-148">そのため、拡張機能が不適切なエンコードが取得されることはありません。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-148">Therefore, it is not possible for the extension to get the wrong encoding.</span></span>
1. <span data-ttu-id="2d8c1-149">統合されたコンソールでスクリプトを直接実行されると、PowerShell によってファイルから直接読み取られます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-149">When scripts are executed directly in the Integrated Console, they're read from the file by PowerShell directly.</span></span> <span data-ttu-id="2d8c1-150">PowerShell のエンコードが VS Code のエンコードと異なる場合は、ここで何か問題が起こる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-150">If PowerShell's encoding differs from VS Code's, something can go wrong here.</span></span>
1. <span data-ttu-id="2d8c1-151">VS Code で開かれているスクリプトにより VS Code で開かれていない別のスクリプトが参照されている場合、拡張機能はフォール バックして、そのスクリプトのコンテンツをファイル システムから読み込みます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-151">When a script that is open in VS Code references another script that is not open in VS Code, the extension falls back to loading that script's content from the file system.</span></span> <span data-ttu-id="2d8c1-152">PowerShell 拡張機能の既定は UTF-8 エンコードですが、[バイト オーダー マーク][] (BOM) 検出を使用して正しいエンコードが選択されます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-152">The PowerShell extension defaults to UTF-8 encoding, but uses [byte-order mark][], or BOM, detection to select the correct encoding.</span></span>

<span data-ttu-id="2d8c1-153">問題は、BOM なしの形式 (BOM なしの [UTF-8][] や [Windows-1252][] など) のエンコードを想定しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-153">The problem occurs when assuming the encoding of BOM-less formats (like [UTF-8][] with no BOM and [Windows-1252][]).</span></span> <span data-ttu-id="2d8c1-154">PowerShell 拡張機能の既定値は UTF-8 です。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-154">The PowerShell extension defaults to UTF-8.</span></span> <span data-ttu-id="2d8c1-155">この拡張機能では VS Code のエンコード設定を変更できません。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-155">The extension cannot change VS Code's encoding settings.</span></span> <span data-ttu-id="2d8c1-156">詳細については、[問題番号 824](https://github.com/Microsoft/VSCode/issues/824) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-156">For more information, see [issue #824](https://github.com/Microsoft/VSCode/issues/824).</span></span>

## <a name="choosing-the-right-encoding"></a><span data-ttu-id="2d8c1-157">適切なエンコードの選択</span><span class="sxs-lookup"><span data-stu-id="2d8c1-157">Choosing the right encoding</span></span>

<span data-ttu-id="2d8c1-158">システムやアプリケーションごとに使用しているエンコードが異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-158">Different systems and applications can use different encodings:</span></span>

- <span data-ttu-id="2d8c1-159">現在、.NET Standard、Web、Linux の世界では、UTF-8 が主流のエンコードです。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-159">In .NET Standard, on the web, and in the Linux world, UTF-8 is now the dominant encoding.</span></span>
- <span data-ttu-id="2d8c1-160">多くの .NET Framework アプリケーションは [UTF-16][] を使用しています。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-160">Many .NET Framework applications use [UTF-16][].</span></span> <span data-ttu-id="2d8c1-161">歴史的な理由から、これは "Unicode" と呼ばれることもあり、現在では UTF-8 と UTF-16 の両方を含む広範な[標準](https://en.wikipedia.org/wiki/Unicode)を指しています。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-161">For historical reasons, this is sometimes called "Unicode", a term that now refers to a broad [standard](https://en.wikipedia.org/wiki/Unicode) that includes both UTF-8 and UTF-16.</span></span>
- <span data-ttu-id="2d8c1-162">Windows では、Unicode より前のネイティブ アプリケーションの多くが既定で Windows-1252 を使用し続けています。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-162">On Windows, many native applications that predate Unicode continue to use Windows-1252 by default.</span></span>

<span data-ttu-id="2d8c1-163">Unicode エンコードには、バイト オーダー マーク (BOM) の概念もあります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-163">Unicode encodings also have the concept of a byte-order mark (BOM).</span></span> <span data-ttu-id="2d8c1-164">BOM はテキストの先頭にあり、これによりテキストが使用しているエンコードがデコーダーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-164">BOMs occur at the beginning of text to tell a decoder which encoding the text is using.</span></span> <span data-ttu-id="2d8c1-165">マルチバイト エンコードの場合、BOM によりエンコードの[エンディアン](https://en.wikipedia.org/wiki/Endianness)が示されます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-165">For multi-byte encodings, the BOM also indicates [endianness](https://en.wikipedia.org/wiki/Endianness) of the encoding.</span></span> <span data-ttu-id="2d8c1-166">BOM は、Unicode 以外のテキストにはまず出現しないバイトになるように設計されているため、BOM が存在する場合、そのテキストは Unicode であると合理的に推測できます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-166">BOMs are designed to be bytes that rarely occur in non-Unicode text, allowing a reasonable guess that text is Unicode when a BOM is present.</span></span>

<span data-ttu-id="2d8c1-167">BOM はオプションであり、Linux の世界ではそれほど採用されていません。UTF-8 の信頼性の高い規則があらゆるところで使用されているためです。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-167">BOMs are optional and their adoption isn't as popular in the Linux world because a dependable convention of UTF-8 is used everywhere.</span></span> <span data-ttu-id="2d8c1-168">ほとんどの Linux アプリケーションでは、テキスト入力が UTF-8 でエンコードされていると想定されています。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-168">Most Linux applications presume that text input is encoded in UTF-8.</span></span> <span data-ttu-id="2d8c1-169">多くの Linux アプリケーションは BOM を認識して正しく処理しますが、認識しないものもあります。そのため、そのようなアプリケーションで処理されたテキストにアーティファクトが生じます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-169">While many Linux applications will recognize and correctly handle a BOM, a number do not, leading to artifacts in text manipulated with those applications.</span></span>

<span data-ttu-id="2d8c1-170">**したがって** :</span><span class="sxs-lookup"><span data-stu-id="2d8c1-170">**Therefore** :</span></span>

- <span data-ttu-id="2d8c1-171">主に Windows アプリケーションと Windows PowerShell を使用している場合は、BOM ありの UTF-8 または UTF-16 のようなエンコードをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-171">If you work primarily with Windows applications and Windows PowerShell, you should prefer an encoding like UTF-8 with BOM or UTF-16.</span></span>
- <span data-ttu-id="2d8c1-172">複数のプラットフォームにまたがって作業する場合は、BOM ありの UTF-8 をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-172">If you work across platforms, you should prefer UTF-8 with BOM.</span></span>
- <span data-ttu-id="2d8c1-173">主に Linux 関連のコンテキストで作業する場合は、BOM なしの UTF-8 をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-173">If you work mainly in Linux-associated contexts, you should prefer UTF-8 without BOM.</span></span>
- <span data-ttu-id="2d8c1-174">Windows-1252 とラテン-1 は基本的にレガシ エンコードであり、できれば避けてください。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-174">Windows-1252 and latin-1 are essentially legacy encodings that you should avoid if possible.</span></span>
  <span data-ttu-id="2d8c1-175">ただし、一部の古い Windows アプリケーションではそれらに依存している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-175">However, some older Windows applications may depend on them.</span></span>
- <span data-ttu-id="2d8c1-176">スクリプトの署名は[エンコードに依存している](https://github.com/PowerShell/PowerShell/issues/3466)点にも注意してください。つまり、署名されたスクリプトのエンコードを変更するには再署名が必要です。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-176">It's also worth noting that script signing is [encoding-dependent](https://github.com/PowerShell/PowerShell/issues/3466), meaning a change of encoding on a signed script will require resigning.</span></span>

## <a name="configuring-vs-code"></a><span data-ttu-id="2d8c1-177">VS Code の構成</span><span class="sxs-lookup"><span data-stu-id="2d8c1-177">Configuring VS Code</span></span>

<span data-ttu-id="2d8c1-178">VS Code の既定のエンコードは BOM なしの UTF-8 です。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-178">VS Code's default encoding is UTF-8 without BOM.</span></span>

<span data-ttu-id="2d8c1-179">[VS Code のエンコード][]を設定するには、VS Code の設定に移動し (<kbd>Ctrl</kbd>+<kbd>、</kbd>)、`"files.encoding"` 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-179">To set [VS Code's encoding][], go to the VS Code settings (<kbd>Ctrl</kbd>+<kbd>,</kbd>) and set the `"files.encoding"` setting:</span></span>

```json
"files.encoding": "utf8bom"
```

<span data-ttu-id="2d8c1-180">次のような値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-180">Some possible values are:</span></span>

- <span data-ttu-id="2d8c1-181">`utf8`:BOM なしの [UTF-8]</span><span class="sxs-lookup"><span data-stu-id="2d8c1-181">`utf8`: [UTF-8] without BOM</span></span>
- <span data-ttu-id="2d8c1-182">`utf8bom`:BOM ありの [UTF-8]</span><span class="sxs-lookup"><span data-stu-id="2d8c1-182">`utf8bom`: [UTF-8] with BOM</span></span>
- <span data-ttu-id="2d8c1-183">`utf16le`:リトル エンディアン [UTF-16]</span><span class="sxs-lookup"><span data-stu-id="2d8c1-183">`utf16le`: Little endian [UTF-16]</span></span>
- <span data-ttu-id="2d8c1-184">`utf16be`:ビッグ エンディアン [UTF-16]</span><span class="sxs-lookup"><span data-stu-id="2d8c1-184">`utf16be`: Big endian [UTF-16]</span></span>
- <span data-ttu-id="2d8c1-185">`windows1252`:[Windows-1252]</span><span class="sxs-lookup"><span data-stu-id="2d8c1-185">`windows1252`: [Windows-1252]</span></span>

<span data-ttu-id="2d8c1-186">GUI ビューでこのドロップダウンを表示するか、JSON ビューですべてを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-186">You should get a dropdown for this in the GUI view, or completions for it in the JSON view.</span></span>

<span data-ttu-id="2d8c1-187">また、可能であれば、以下を追加してエンコードを自動検出することもできます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-187">You can also add the following to autodetect encoding when possible:</span></span>

```json
"files.autoGuessEncoding": true
```

<span data-ttu-id="2d8c1-188">これらの設定がすべてのファイルの種類に影響しないようにする場合、VS Code では言語ごとに構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-188">If you don't want these settings to affect all files types, VS Code also allows per-language configurations.</span></span> <span data-ttu-id="2d8c1-189">`[<language-name>]` フィールドに設定を指定して、言語固有の設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-189">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="2d8c1-190">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-190">For example:</span></span>

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="2d8c1-191">また、[Gremlins tracker][] for Visual Studio Code をインストールすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-191">You may also want to consider installing the [Gremlins tracker][] for Visual Studio Code.</span></span> <span data-ttu-id="2d8c1-192">この拡張機能により、目に見えないか他の通常の文字のように見えるため、文字化けしやすい特定の Unicode 文字が明らかになります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-192">This extension reveals certain Unicode characters that easily corrupted because they are invisible or look like other normal characters.</span></span>

## <a name="configuring-powershell"></a><span data-ttu-id="2d8c1-193">PowerShell の構成</span><span class="sxs-lookup"><span data-stu-id="2d8c1-193">Configuring PowerShell</span></span>

<span data-ttu-id="2d8c1-194">PowerShell の既定のエンコードはバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-194">PowerShell's default encoding varies depending on version:</span></span>

- <span data-ttu-id="2d8c1-195">PowerShell 6 以降では、既定のエンコードはすべてのプラットフォームで BOM なしの UTF-8 です。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-195">In PowerShell 6+, the default encoding is UTF-8 without BOM on all platforms.</span></span>
- <span data-ttu-id="2d8c1-196">Windows PowerShell では、既定のエンコードは通常 Windows-1252 (拡張子は [latin-1][]) であり、ISO 8859-1 とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-196">In Windows PowerShell, the default encoding is usually Windows-1252, an extension of [latin-1][], also known as ISO 8859-1.</span></span>

<span data-ttu-id="2d8c1-197">PowerShell 5 以降では、以下のように既定のエンコードを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-197">In PowerShell 5+ you can find your default encoding with this:</span></span>

```powershell
[psobject].Assembly.GetTypes() | Where-Object { $_.Name -eq 'ClrFacade'} |
  ForEach-Object {
    $_.GetMethod('GetDefaultEncoding', [System.Reflection.BindingFlags]'nonpublic,static').Invoke($null, @())
  }
```

<span data-ttu-id="2d8c1-198">次の[スクリプト](https://gist.github.com/rjmholt/3d8dd4849f718c914132ce3c5b278e0e)を使用して、PowerShell セッションが BOM なしのスクリプトに対して推測するエンコードを決定できます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-198">The following [script](https://gist.github.com/rjmholt/3d8dd4849f718c914132ce3c5b278e0e) can be used to determine what encoding your PowerShell session infers for a script without a BOM.</span></span>

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

<span data-ttu-id="2d8c1-199">より一般的にはプロファイル設定を使用して、特定のエンコードを使用するように PowerShell を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-199">It's possible to configure PowerShell to use a given encoding more generally using profile settings.</span></span>
<span data-ttu-id="2d8c1-200">次の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-200">See the following articles:</span></span>

- <span data-ttu-id="2d8c1-201">[@mklement0] の [StackOverflow 上の PowerShell エンコードに関する回答](https://stackoverflow.com/a/40098904)。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-201">[@mklement0]'s [answer about PowerShell encoding on StackOverflow](https://stackoverflow.com/a/40098904).</span></span>
- <span data-ttu-id="2d8c1-202">[@rkeithhill] の [PowerShell での BOM なしの UTF-8 入力の処理に関するブログ投稿](https://rkeithhill.wordpress.com/2010/05/26/handling-native-exe-output-encoding-in-utf8-with-no-bom/)。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-202">[@rkeithhill]'s [blog post about dealing with BOM-less UTF-8 input in PowerShell](https://rkeithhill.wordpress.com/2010/05/26/handling-native-exe-output-encoding-in-utf8-with-no-bom/).</span></span>

<span data-ttu-id="2d8c1-203">PowerShell に特定の入力エンコードの使用を強制することはできません。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-203">It's not possible to force PowerShell to use a specific input encoding.</span></span> <span data-ttu-id="2d8c1-204">ロケールが en-US に設定された Windows で実行される PowerShell 5.1 以前では、BOM がない場合、既定値は Windows-1252 エンコードです。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-204">PowerShell 5.1 and below, running on Windows with the locale set to en-US, defaults to Windows-1252 encoding when there's no BOM.</span></span> <span data-ttu-id="2d8c1-205">他のロケール設定では、別のエンコードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-205">Other locale settings may use a different encoding.</span></span> <span data-ttu-id="2d8c1-206">相互運用性を確保するには、BOM が含まれる Unicode 形式でスクリプトを保存することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-206">To ensure interoperability, it's best to save scripts in a Unicode format with a BOM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d8c1-207">PowerShell スクリプトに触れる他のツールがある場合、そのツールがエンコードの選択の影響を受ける場合や、ツールによってスクリプトが別のエンコードに再エンコードされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-207">Any other tools you have that touch PowerShell scripts may be affected by your encoding choices or re-encode your scripts to another encoding.</span></span>

### <a name="existing-scripts"></a><span data-ttu-id="2d8c1-208">既存のスクリプト</span><span class="sxs-lookup"><span data-stu-id="2d8c1-208">Existing scripts</span></span>

<span data-ttu-id="2d8c1-209">既にファイル システム上にあるスクリプトは、必要に応じて新しく選択したエンコードに再エンコードします。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-209">Scripts already on the file system may need to be re-encoded to your new chosen encoding.</span></span> <span data-ttu-id="2d8c1-210">VS Code の下部のバーに、UTF-8 というラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-210">In the bottom bar of VS Code, you'll see the label UTF-8.</span></span> <span data-ttu-id="2d8c1-211">クリックしてアクション バーを開き、 **[エンコード付きで保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-211">Click it to open the action bar and select **Save with encoding**.</span></span> <span data-ttu-id="2d8c1-212">ここで、そのファイル用に新しいエンコードを選択できます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-212">You can now pick a new encoding for that file.</span></span> <span data-ttu-id="2d8c1-213">完全な手順については、[VS Code のエンコード][]に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-213">See [VS Code's encoding][] for full instructions.</span></span>

<span data-ttu-id="2d8c1-214">複数のファイルを再エンコードする必要がある場合は、次のスクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-214">If you need to re-encode multiple files, you can use the following script:</span></span>

```powershell
Get-ChildItem *.ps1 -Recurse | ForEach-Object {
    $content = Get-Content -Path $_
    Set-Content -Path $_.Fullname -Value $content -Encoding UTF8 -PassThru -Force
}
```

### <a name="the-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="2d8c1-215">PowerShell Integrated Scripting Environment (ISE)</span><span class="sxs-lookup"><span data-stu-id="2d8c1-215">The PowerShell Integrated Scripting Environment (ISE)</span></span>

<span data-ttu-id="2d8c1-216">PowerShell ISE を使用してスクリプトも編集する場合は、そこでエンコード設定を同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-216">If you also edit scripts using the PowerShell ISE, you need to synchronize your encoding settings there.</span></span>

<span data-ttu-id="2d8c1-217">ISE で BOM を尊重する必要がありますが、リフレクションを使用して[エンコードを設定](https://bensonxion.wordpress.com/2012/04/25/powershell-ise-default-saveas-encoding/)することもできます。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-217">The ISE should honor a BOM, but it's also possible to use reflection to [set the encoding](https://bensonxion.wordpress.com/2012/04/25/powershell-ise-default-saveas-encoding/).</span></span>
<span data-ttu-id="2d8c1-218">これはスタートアップ後には保持されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-218">Note that this wouldn't be persisted between startups.</span></span>

### <a name="source-control-software"></a><span data-ttu-id="2d8c1-219">ソース管理ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="2d8c1-219">Source control software</span></span>

<span data-ttu-id="2d8c1-220">git などの一部のソース管理ツールはエンコードを無視します (git は単にバイトを追跡します)。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-220">Some source control tools, such as git, ignore encodings; git just tracks the bytes.</span></span> <span data-ttu-id="2d8c1-221">他のもの (Azure DevOps や Mercurial など) はそうではない場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-221">Others, like Azure DevOps or Mercurial, may not.</span></span> <span data-ttu-id="2d8c1-222">一部の git ベースのツールでさえ、テキストのデコードに依存しています。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-222">Even some git-based tools rely on decoding text.</span></span>

<span data-ttu-id="2d8c1-223">その場合は、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-223">When this is the case, make sure you:</span></span>

- <span data-ttu-id="2d8c1-224">VS Code の構成と一致するように、ソース管理でテキスト エンコードを構成します。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-224">Configure the text encoding in your source control to match your VS Code configuration.</span></span>
- <span data-ttu-id="2d8c1-225">すべてのファイルが適切なエンコードでソース管理に確実にチェックインされているようにします。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-225">Ensure all your files are checked into source control in the relevant encoding.</span></span>
- <span data-ttu-id="2d8c1-226">ソース管理を介して受信したエンコードの変化に注意します。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-226">Be wary of changes to the encoding received through source control.</span></span> <span data-ttu-id="2d8c1-227">これを示す主な兆候は変化を示す差異ですが、何も変わっていないように見えます (バイトは変わっていますが、文字は変わっていないため)。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-227">A key sign of this is a diff indicating changes but where nothing seems to have changed (because bytes have but characters have not).</span></span>

### <a name="collaborators-environments"></a><span data-ttu-id="2d8c1-228">共同作業者の環境</span><span class="sxs-lookup"><span data-stu-id="2d8c1-228">Collaborators' environments</span></span>

<span data-ttu-id="2d8c1-229">ソース管理の構成に加え、共有するファイルの共同作業者が PowerShell ファイルを再エンコードしてエンコードをオーバーライドする設定を確実に保持していないようにします。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-229">On top of configuring source control, ensure that your collaborators on any files you share don't have settings that override your encoding by re-encoding PowerShell files.</span></span>

### <a name="other-programs"></a><span data-ttu-id="2d8c1-230">その他のプログラム</span><span class="sxs-lookup"><span data-stu-id="2d8c1-230">Other programs</span></span>

<span data-ttu-id="2d8c1-231">PowerShell スクリプトの読み取りまたは書き込みを行う他のプログラムが、再エンコードする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-231">Any other program that reads or writes a PowerShell script may re-encode it.</span></span>

<span data-ttu-id="2d8c1-232">いくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-232">Some examples are:</span></span>

- <span data-ttu-id="2d8c1-233">クリップボードを使用してスクリプトをコピーして貼り付ける。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-233">Using the clipboard to copy and paste a script.</span></span> <span data-ttu-id="2d8c1-234">これは次のようなシナリオで一般的です。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-234">This is common in scenarios like:</span></span>
  - <span data-ttu-id="2d8c1-235">スクリプトを VM にコピーする</span><span class="sxs-lookup"><span data-stu-id="2d8c1-235">Copying a script into a VM</span></span>
  - <span data-ttu-id="2d8c1-236">電子メールまたは Web ページからスクリプトをコピーする</span><span class="sxs-lookup"><span data-stu-id="2d8c1-236">Copying a script out of an email or webpage</span></span>
  - <span data-ttu-id="2d8c1-237">Microsoft Word または PowerPoint ドキュメントとの間でスクリプトをコピーする</span><span class="sxs-lookup"><span data-stu-id="2d8c1-237">Copying a script into or out of a Microsoft Word or PowerPoint document</span></span>
- <span data-ttu-id="2d8c1-238">次のようなその他のテキスト エディター:</span><span class="sxs-lookup"><span data-stu-id="2d8c1-238">Other text editors, such as:</span></span>
  - <span data-ttu-id="2d8c1-239">メモ帳</span><span class="sxs-lookup"><span data-stu-id="2d8c1-239">Notepad</span></span>
  - <span data-ttu-id="2d8c1-240">vim</span><span class="sxs-lookup"><span data-stu-id="2d8c1-240">vim</span></span>
  - <span data-ttu-id="2d8c1-241">その他の PowerShell スクリプト エディター</span><span class="sxs-lookup"><span data-stu-id="2d8c1-241">Any other PowerShell script editor</span></span>
- <span data-ttu-id="2d8c1-242">次のようなテキスト編集ユーティリティ:</span><span class="sxs-lookup"><span data-stu-id="2d8c1-242">Text editing utilities, like:</span></span>
  - `Get-Content`/`Set-Content`/`Out-File`
  - <span data-ttu-id="2d8c1-243">PowerShell リダイレクト演算子 (`>`、`>>` など)</span><span class="sxs-lookup"><span data-stu-id="2d8c1-243">PowerShell redirection operators like `>` and `>>`</span></span>
  - `sed`/`awk`
- <span data-ttu-id="2d8c1-244">次のようなファイル転送プログラム:</span><span class="sxs-lookup"><span data-stu-id="2d8c1-244">File transfer programs, like:</span></span>
  - <span data-ttu-id="2d8c1-245">Web ブラウザー (スクリプトのダウンロード時)</span><span class="sxs-lookup"><span data-stu-id="2d8c1-245">A web browser, when downloading scripts</span></span>
  - <span data-ttu-id="2d8c1-246">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="2d8c1-246">A file share</span></span>

<span data-ttu-id="2d8c1-247">このようなツールの一部はテキストではなくバイトで処理しますが、エンコードの構成機能が用意されているツールもあります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-247">Some of these tools deal in bytes rather than text, but others offer encoding configurations.</span></span> <span data-ttu-id="2d8c1-248">エンコードを構成する必要がある場合は、問題を防ぐために、それをエディターのエンコードと同じにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-248">In those cases where you need to configure an encoding, you need to make it the same as your editor encoding to prevent problems.</span></span>

## <a name="other-resources-on-encoding-in-powershell"></a><span data-ttu-id="2d8c1-249">PowerShell でのエンコードに関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="2d8c1-249">Other resources on encoding in PowerShell</span></span>

<span data-ttu-id="2d8c1-250">PowerShell でのエンコードとエンコードの構成に関するお勧めの投稿が他にもいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="2d8c1-250">There are a few other nice posts on encoding and configuring encoding in PowerShell that are worth a read:</span></span>

- [<span data-ttu-id="2d8c1-251">about_Character_Encoding</span><span class="sxs-lookup"><span data-stu-id="2d8c1-251">about_Character_Encoding</span></span>](/powershell/module/microsoft.powershell.core/about/about_character_encoding)
- <span data-ttu-id="2d8c1-252">[@mklement0] の [StackOverflow 上の PowerShell エンコードの概要](https://stackoverflow.com/questions/40098771/changing-powershells-default-output-encoding-to-utf-8)</span><span class="sxs-lookup"><span data-stu-id="2d8c1-252">[@mklement0]'s [summary of PowerShell encoding on StackOverflow](https://stackoverflow.com/questions/40098771/changing-powershells-default-output-encoding-to-utf-8)</span></span>
- <span data-ttu-id="2d8c1-253">エンコードの問題について VS Code-PowerShell で開かれた以前の問題:</span><span class="sxs-lookup"><span data-stu-id="2d8c1-253">Previous issues opened on VS Code-PowerShell for encoding problems:</span></span>
  - [<span data-ttu-id="2d8c1-254">#1308</span><span class="sxs-lookup"><span data-stu-id="2d8c1-254">#1308</span></span>](https://github.com/PowerShell/VSCode-powershell/issues/1308)
  - [<span data-ttu-id="2d8c1-255">#1628</span><span class="sxs-lookup"><span data-stu-id="2d8c1-255">#1628</span></span>](https://github.com/PowerShell/VSCode-powershell/issues/1628)
  - [<span data-ttu-id="2d8c1-256">#1680</span><span class="sxs-lookup"><span data-stu-id="2d8c1-256">#1680</span></span>](https://github.com/PowerShell/VSCode-powershell/issues/1680)
  - [<span data-ttu-id="2d8c1-257">#1744</span><span class="sxs-lookup"><span data-stu-id="2d8c1-257">#1744</span></span>](https://github.com/PowerShell/VSCode-powershell/issues/1744)
  - [<span data-ttu-id="2d8c1-258">#1751</span><span class="sxs-lookup"><span data-stu-id="2d8c1-258">#1751</span></span>](https://github.com/PowerShell/VSCode-powershell/issues/1751)
- [<span data-ttu-id="2d8c1-259">_Joel on Software_ が Unicode について書いた以前の投稿</span><span class="sxs-lookup"><span data-stu-id="2d8c1-259">The classic _Joel on Software_ write up about Unicode</span></span>](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)
- [<span data-ttu-id="2d8c1-260">.NET Standard のエンコード</span><span class="sxs-lookup"><span data-stu-id="2d8c1-260">Encoding in .NET Standard</span></span>](https://github.com/dotnet/standard/issues/260#issuecomment-289549508)

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
[VS Code のエンコード]: https://code.visualstudio.com/docs/editor/codebasics#_file-encoding-support
[VS Code's encoding]: https://code.visualstudio.com/docs/editor/codebasics#_file-encoding-support
[Gremlins tracker]: https://marketplace.visualstudio.com/items?itemName=nhoizey.gremlins
