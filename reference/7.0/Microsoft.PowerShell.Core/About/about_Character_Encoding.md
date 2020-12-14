---
description: PowerShell が文字列データの入力と出力に文字エンコーディングを使用する方法について説明します。
Locale: en-US
ms.date: 10/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_character_encoding?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Character_Encoding
ms.openlocfilehash: f383b985baeae059565f61c700df7a76346497d8
ms.sourcegitcommit: cc72c40315fd2981d3009b335accbfa52d57640c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2020
ms.locfileid: "96349850"
---
# <a name="about_character_encoding"></a><span data-ttu-id="6c7b1-103">about_Character_Encoding</span><span class="sxs-lookup"><span data-stu-id="6c7b1-103">about_Character_Encoding</span></span>

## <a name="short-description"></a><span data-ttu-id="6c7b1-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="6c7b1-104">Short description</span></span>
<span data-ttu-id="6c7b1-105">PowerShell が文字列データの入力と出力に文字エンコーディングを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-105">Describes how PowerShell uses character encoding for input and output of string data.</span></span>

## <a name="long-description"></a><span data-ttu-id="6c7b1-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="6c7b1-106">Long description</span></span>

<span data-ttu-id="6c7b1-107">Unicode は世界中の文字エンコード標準です。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-107">Unicode is a worldwide character-encoding standard.</span></span> <span data-ttu-id="6c7b1-108">システムは、文字および文字列の操作に Unicode のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-108">The system uses Unicode exclusively for character and string manipulation.</span></span> <span data-ttu-id="6c7b1-109">Unicode のすべての側面の詳細については、 [Unicode 標準](https://www.unicode.org/standard/standard.html)に関する説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-109">For a detailed description of all aspects of Unicode, refer to [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>

<span data-ttu-id="6c7b1-110">Windows では、Unicode および従来の文字セットがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-110">Windows supports Unicode and traditional character sets.</span></span> <span data-ttu-id="6c7b1-111">Windows コードページなどの従来の文字セットでは、8ビット値または8ビット値の組み合わせを使用して、特定の言語または地理的地域の設定で使用される文字を表します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-111">Traditional character sets, such as Windows code pages, use 8-bit values or combinations of 8-bit values to represent the characters used in a specific language or geographical region settings.</span></span>

<span data-ttu-id="6c7b1-112">PowerShell では、既定で Unicode 文字セットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-112">PowerShell uses a Unicode character set by default.</span></span> <span data-ttu-id="6c7b1-113">ただし、いくつかのコマンドレットには、別の文字セットのエンコードを指定できる **encoding** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-113">However, several cmdlets have an **Encoding** parameter that can specify encoding for a different character set.</span></span> <span data-ttu-id="6c7b1-114">このパラメーターを使用すると、他のシステムやアプリケーションとの相互運用性を確保するために必要な、特定の文字エンコードを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-114">This parameter allows you to choose the specific the character encoding you need for interoperability with other systems and applications.</span></span>

<span data-ttu-id="6c7b1-115">次のコマンドレットには **Encoding** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-115">The following cmdlets have the **Encoding** parameter:</span></span>

- <span data-ttu-id="6c7b1-116">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="6c7b1-116">Microsoft.PowerShell.Management</span></span>
  - <span data-ttu-id="6c7b1-117">Add-Content</span><span class="sxs-lookup"><span data-stu-id="6c7b1-117">Add-Content</span></span>
  - <span data-ttu-id="6c7b1-118">Get-Content</span><span class="sxs-lookup"><span data-stu-id="6c7b1-118">Get-Content</span></span>
  - <span data-ttu-id="6c7b1-119">Set-Content</span><span class="sxs-lookup"><span data-stu-id="6c7b1-119">Set-Content</span></span>
- <span data-ttu-id="6c7b1-120">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="6c7b1-120">Microsoft.PowerShell.Utility</span></span>
  - <span data-ttu-id="6c7b1-121">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="6c7b1-121">Export-Clixml</span></span>
  - <span data-ttu-id="6c7b1-122">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="6c7b1-122">Export-Csv</span></span>
  - <span data-ttu-id="6c7b1-123">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="6c7b1-123">Export-PSSession</span></span>
  - <span data-ttu-id="6c7b1-124">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="6c7b1-124">Format-Hex</span></span>
  - <span data-ttu-id="6c7b1-125">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="6c7b1-125">Import-Csv</span></span>
  - <span data-ttu-id="6c7b1-126">Out-File</span><span class="sxs-lookup"><span data-stu-id="6c7b1-126">Out-File</span></span>
  - <span data-ttu-id="6c7b1-127">Select-String</span><span class="sxs-lookup"><span data-stu-id="6c7b1-127">Select-String</span></span>
  - <span data-ttu-id="6c7b1-128">Send-MailMessage</span><span class="sxs-lookup"><span data-stu-id="6c7b1-128">Send-MailMessage</span></span>

## <a name="the-byte-order-mark"></a><span data-ttu-id="6c7b1-129">バイト順マーク</span><span class="sxs-lookup"><span data-stu-id="6c7b1-129">The byte-order-mark</span></span>

<span data-ttu-id="6c7b1-130">バイト順マーク (BOM) は、ファイルまたはテキストストリームの最初の数バイトの _unicode 署名_ で、データに使用される unicode エンコーディングを示します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-130">The byte-order-mark (BOM) is a _Unicode signature_ in the first few bytes of a file or text stream that indicate which Unicode encoding used for the data.</span></span> <span data-ttu-id="6c7b1-131">詳細については、 [バイトオーダーマーク](/globalization/encoding/byte-order-mark) のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-131">For more information, see the [Byte order mark](/globalization/encoding/byte-order-mark) documentation.</span></span>

<span data-ttu-id="6c7b1-132">Windows PowerShell では、以外のすべての Unicode エンコーディングでは、 `UTF7` 常に BOM が作成されます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-132">In Windows PowerShell, any Unicode encoding, except `UTF7`, always creates a BOM.</span></span> <span data-ttu-id="6c7b1-133">PowerShell Core では、 `utf8NoBOM` すべてのテキスト出力で既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-133">PowerShell Core defaults to `utf8NoBOM` for all text output.</span></span>

<span data-ttu-id="6c7b1-134">全体的な互換性を最大限に高めるには、UTF-8 ファイルで Bom を使用しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-134">For best overall compatibility, avoid using BOMs in UTF-8 files.</span></span> <span data-ttu-id="6c7b1-135">Windows プラットフォームでも使用されている unix プラットフォームおよび Unix の保護ユーティリティでは、Bom はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-135">Unix platforms and Unix-heritage utilities also used on Windows Platforms don't support BOMs.</span></span>

<span data-ttu-id="6c7b1-136">同様に、 `UTF7` エンコードを避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-136">Similarly, `UTF7` encoding should be avoided.</span></span> <span data-ttu-id="6c7b1-137">UTF-7 は標準の Unicode エンコードではなく、すべてのバージョンの PowerShell に BOM なしで記述されます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-137">UTF-7 is not a standard Unicode encoding and is written without a BOM in all versions of PowerShell.</span></span>

<span data-ttu-id="6c7b1-138">Unix のようなプラットフォームで PowerShell スクリプトを作成したり、Windows のクロスプラットフォームエディター (Visual Studio Code など) を使用したりすると、を使用してエンコードされたファイルが生成さ `UTF8NoBOM` れます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-138">Creating PowerShell scripts on a Unix-like platform or using a cross-platform editor on Windows, such as Visual Studio Code, results in a file encoded using `UTF8NoBOM`.</span></span> <span data-ttu-id="6c7b1-139">これらのファイルは PowerShell Core では正常に動作しますが、ファイルに Ascii 以外の文字が含まれていると、Windows PowerShell では機能しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-139">These files work fine on PowerShell Core, but may break in Windows PowerShell if the file contains non-Ascii characters.</span></span>

<span data-ttu-id="6c7b1-140">スクリプトで Ascii 以外の文字を使用する必要がある場合は、BOM を使用して UTF-8 として保存します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-140">If you need to use non-Ascii characters in your scripts, save them as UTF-8 with BOM.</span></span> <span data-ttu-id="6c7b1-141">BOM がない場合、Windows PowerShell はスクリプトを従来の "ANSI" コードページでエンコードされたものとして misinterprets します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-141">Without the BOM, Windows PowerShell misinterprets your script as being encoded in the legacy "ANSI" codepage.</span></span> <span data-ttu-id="6c7b1-142">逆に、UTF-8 BOM を持つファイルは、Unix のようなプラットフォームでは問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-142">Conversely, files that do have the UTF-8 BOM can be problematic on Unix-like platforms.</span></span> <span data-ttu-id="6c7b1-143">、、、などの多くの Unix ツール `cat` は、 `sed` BOM を `awk` `gedit` 扱う方法がわからない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-143">Many Unix tools such as `cat`, `sed`, `awk`, and some editors such as `gedit` don't know how to treat the BOM.</span></span>

## <a name="character-encoding-in-windows-powershell"></a><span data-ttu-id="6c7b1-144">Windows PowerShell での文字エンコード</span><span class="sxs-lookup"><span data-stu-id="6c7b1-144">Character encoding in Windows PowerShell</span></span>

<span data-ttu-id="6c7b1-145">PowerShell 5.1 では、 **Encoding** パラメーターは次の値をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-145">In PowerShell 5.1, the **Encoding** parameter supports the following values:</span></span>

- <span data-ttu-id="6c7b1-146">`Ascii` Ascii (7 ビット) 文字セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-146">`Ascii` Uses Ascii (7-bit) character set.</span></span>
- <span data-ttu-id="6c7b1-147">`BigEndianUnicode` は、ビッグエンディアンのバイト順で UTF-16 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-147">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="6c7b1-148">`BigEndianUTF32` は、ビッグエンディアンのバイト順で 32 UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-148">`BigEndianUTF32` Uses UTF-32 with the big-endian byte order.</span></span>
- <span data-ttu-id="6c7b1-149">`Byte` 文字のセットをバイトシーケンスにエンコードします。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-149">`Byte` Encodes a set of characters into a sequence of bytes.</span></span>
- <span data-ttu-id="6c7b1-150">`Default` は、システムのアクティブなコードページ (通常は ANSI) に対応するエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-150">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="6c7b1-151">`Oem` は、システムの現在の OEM コードページに対応するエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-151">`Oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="6c7b1-152">`String``Unicode` と同じです。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-152">`String` Same as `Unicode`.</span></span>
- <span data-ttu-id="6c7b1-153">`Unicode` は、リトルエンディアンのバイト順で UTF-16 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-153">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="6c7b1-154">`Unknown``Unicode` と同じです。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-154">`Unknown` Same as `Unicode`.</span></span>
- <span data-ttu-id="6c7b1-155">`UTF32` は、リトルエンディアンのバイト順で 32 UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-155">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>
- <span data-ttu-id="6c7b1-156">`UTF7` UTF-7 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-156">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="6c7b1-157">`UTF8` UTF-8 (BOM 付き) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-157">`UTF8` Uses UTF-8 (with BOM).</span></span>

<span data-ttu-id="6c7b1-158">一般に、Windows PowerShell では、既定で Unicode [utf-8](https://wikipedia.org/wiki/UTF-16) エンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-158">In general, Windows PowerShell uses the Unicode [UTF-16LE](https://wikipedia.org/wiki/UTF-16) encoding by default.</span></span> <span data-ttu-id="6c7b1-159">ただし、Windows PowerShell のコマンドレットで使用される既定のエンコードには一貫性がありません。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-159">However, the default encoding used by cmdlets in Windows PowerShell is not consistent.</span></span>

> [!NOTE]
> <span data-ttu-id="6c7b1-160">以外の Unicode エンコーディングを使用する場合は、 `UTF7` 常に BOM が作成されます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-160">Using any Unicode encoding, except `UTF7`, always creates a BOM.</span></span>

<span data-ttu-id="6c7b1-161">出力をファイルに書き込むコマンドレットの場合:</span><span class="sxs-lookup"><span data-stu-id="6c7b1-161">For cmdlets that write output to files:</span></span>

- <span data-ttu-id="6c7b1-162">`Out-File` また、リダイレクト演算子 `>` とは `>>` 16LE を作成します。これは特に `Set-Content` およびとは異なり `Add-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-162">`Out-File` and the redirection operators `>` and `>>` create UTF-16LE, which notably differs from `Set-Content` and `Add-Content`.</span></span>

- <span data-ttu-id="6c7b1-163">`New-ModuleManifest``Export-CliXml`また、16LE ファイルも作成します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-163">`New-ModuleManifest` and `Export-CliXml` also create UTF-16LE files.</span></span>

- <span data-ttu-id="6c7b1-164">ターゲットファイルが空であるか存在しない場合、 `Set-Content` および `Add-Content` エンコードを使用し `Default` ます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-164">When the target file is empty or doesn't exist, `Set-Content` and `Add-Content` use `Default` encoding.</span></span> <span data-ttu-id="6c7b1-165">`Default` は、アクティブシステムロケールの ANSI レガシコードページによって指定されたエンコーディングです。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-165">`Default` is the encoding specified by the active system locale's ANSI legacy code page.</span></span>

- <span data-ttu-id="6c7b1-166">`Export-Csv` で `Ascii` は、 **Append** パラメーター (下記参照) を使用するときに、ファイルを作成しますが、別のエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-166">`Export-Csv` creates `Ascii` files but uses different encoding when using **Append** parameter (see below).</span></span>

- <span data-ttu-id="6c7b1-167">`Export-PSSession` 既定で、BOM を使用して UTF-8 ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-167">`Export-PSSession` creates UTF-8 files with BOM by default.</span></span>

- <span data-ttu-id="6c7b1-168">`New-Item -Type File -Value` BOM のない UTF-8 ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-168">`New-Item -Type File -Value` creates a BOM-less UTF-8 file.</span></span>

- <span data-ttu-id="6c7b1-169">`Send-MailMessage``Default`既定ではエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-169">`Send-MailMessage` uses `Default` encoding by default.</span></span>

- <span data-ttu-id="6c7b1-170">`Start-Transcript``Utf8`BOM を使用してファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-170">`Start-Transcript` creates `Utf8` files with a BOM.</span></span> <span data-ttu-id="6c7b1-171">**Append** パラメーターを使用する場合は、エンコードが異なる場合があります (下記参照)。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-171">When the **Append** parameter is used, the encoding can be different (see below).</span></span>

<span data-ttu-id="6c7b1-172">既存のファイルに追加するコマンドの場合:</span><span class="sxs-lookup"><span data-stu-id="6c7b1-172">For commands that append to an existing file:</span></span>

- <span data-ttu-id="6c7b1-173">`Out-File -Append` また、 `>>` リダイレクト演算子は、既存のターゲットファイルのコンテンツのエンコードと一致しません。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-173">`Out-File -Append` and the `>>` redirection operator make no attempt to match the encoding of the existing target file's content.</span></span> <span data-ttu-id="6c7b1-174">代わりに、 **encoding** パラメーターが使用されない限り、既定のエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-174">Instead, they use the default encoding unless the **Encoding** parameter is used.</span></span> <span data-ttu-id="6c7b1-175">コンテンツを追加するときは、ファイルの元のエンコードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-175">You must use the files original encoding when appending content.</span></span>

- <span data-ttu-id="6c7b1-176">明示的な **encoding** パラメーターがない場合、は `Add-Content` 既存のエンコーディングを検出し、新しいコンテンツに自動的に適用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-176">In the absence of an explicit **Encoding** parameter, `Add-Content` detects the existing encoding and automatically applies it to the new content.</span></span> <span data-ttu-id="6c7b1-177">既存のコンテンツに BOM がない場合は、 `Default` ANSI エンコーディングが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-177">If the existing content has no BOM, `Default` ANSI encoding is used.</span></span> <span data-ttu-id="6c7b1-178">の動作は、既定のエンコードがであることを除いて、 `Add-Content` PowerShell Core (v6 以降) で同じです `Utf8` 。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-178">The behavior of `Add-Content` is the same in PowerShell Core (v6 and higher) except the default encoding is `Utf8`.</span></span>

- <span data-ttu-id="6c7b1-179">`Export-Csv -Append` ターゲットファイルに BOM が含まれている場合に、既存のエンコードと一致します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-179">`Export-Csv -Append` matches the existing encoding when the target file contains a BOM.</span></span> <span data-ttu-id="6c7b1-180">BOM がない場合、エンコードが使用さ `Utf8` れます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-180">In the absence of a BOM, it uses `Utf8` encoding.</span></span>

- <span data-ttu-id="6c7b1-181">`Start-Transcript -Append` BOM を含むファイルの既存のエンコードと一致します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-181">`Start-Transcript -Append` matches the existing encoding of files that include a BOM.</span></span> <span data-ttu-id="6c7b1-182">BOM がない場合、既定でエンコードが設定さ `Ascii` れます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-182">In the absence of a BOM, it defaults to `Ascii` encoding.</span></span> <span data-ttu-id="6c7b1-183">このエンコードにより、トランスクリプト内のデータにマルチバイト文字が含まれている場合に、データの損失や文字の破損が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-183">This encoding can result in data loss or character corruption when the data in the transcript contains multibyte characters.</span></span>

<span data-ttu-id="6c7b1-184">BOM がない場合に文字列データを読み取るコマンドレットの場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-184">For cmdlets that read string data in the absence of a BOM:</span></span>

- <span data-ttu-id="6c7b1-185">`Get-Content` と `Import-PowerShellDataFile` は、 `Default` ANSI エンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-185">`Get-Content` and `Import-PowerShellDataFile` uses the `Default` ANSI encoding.</span></span> <span data-ttu-id="6c7b1-186">ANSI は、ファイルからソースコードを読み取るときに PowerShell エンジンが使用するものでもあります。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-186">ANSI is also what the PowerShell engine uses when it reads source code from files.</span></span>

- <span data-ttu-id="6c7b1-187">`Import-Csv`、、およびは、BOM がないことを想定して `Import-CliXml` `Select-String` `Utf8` います。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-187">`Import-Csv`, `Import-CliXml`, and `Select-String` assume `Utf8` in the absence of a BOM.</span></span>

## <a name="character-encoding-in-powershell-core"></a><span data-ttu-id="6c7b1-188">PowerShell Core での文字エンコード</span><span class="sxs-lookup"><span data-stu-id="6c7b1-188">Character encoding in PowerShell Core</span></span>

<span data-ttu-id="6c7b1-189">PowerShell Core (v6 以降) では、 **Encoding** パラメーターは次の値をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-189">In PowerShell Core (v6 and higher), the **Encoding** parameter supports the following values:</span></span>

- <span data-ttu-id="6c7b1-190">`ascii`: ASCII (7 ビット) 文字セットのエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-190">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="6c7b1-191">`bigendianunicode`: ビッグエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-191">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="6c7b1-192">`oem`: MS-DOS およびコンソールプログラムの既定のエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-192">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="6c7b1-193">`unicode`: リトルエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-193">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="6c7b1-194">`utf7`: UTF-7 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-194">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="6c7b1-195">`utf8`: UTF-8 形式 (BOM なし) でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-195">`utf8`: Encodes in UTF-8 format (no BOM).</span></span>
- <span data-ttu-id="6c7b1-196">`utf8BOM`: バイト順マーク (BOM) を使用して UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-196">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="6c7b1-197">`utf8NoBOM`: バイトオーダーマーク (BOM) を使用せずに UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-197">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="6c7b1-198">`utf32`:32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-198">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="6c7b1-199">PowerShell Core では、 `utf8NoBOM` すべての出力で既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-199">PowerShell Core defaults to `utf8NoBOM` for all output.</span></span>

<span data-ttu-id="6c7b1-200">PowerShell 6.2 以降では、 **Encoding** パラメーターを使用して、登録されているコードページの数値 id (など) `-Encoding 1251` や、登録されているコードページの文字列名 (など) を使用することもでき `-Encoding "windows-1251"` ます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-200">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="6c7b1-201">詳細については、 [コードページ](/dotnet/api/system.text.encoding.codepage)の .net ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-201">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage).</span></span>

## <a name="changing-the-default-encoding"></a><span data-ttu-id="6c7b1-202">既定のエンコードの変更</span><span class="sxs-lookup"><span data-stu-id="6c7b1-202">Changing the default encoding</span></span>

<span data-ttu-id="6c7b1-203">PowerShell には、既定のエンコーディング動作を変更するために使用できる既定の変数が2つあります。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-203">PowerShell has two default variables that can be used to change the default encoding behavior.</span></span>

- `$PSDefaultParameterValues`
- `$OutputEncoding`

<span data-ttu-id="6c7b1-204">詳細については、「 [about_Preference_Variables](about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-204">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="6c7b1-205">PowerShell 5.1 以降では、リダイレクト演算子 ( `>` と) によって `>>` コマンドレットが呼び出され `Out-File` ます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-205">Beginning in PowerShell 5.1, the redirection operators (`>` and `>>`) call the `Out-File` cmdlet.</span></span> <span data-ttu-id="6c7b1-206">そのため、 `$PSDefaultParameterValues` 次の例に示すように、ユーザー設定変数を使用して、これらの既定のエンコーディングを設定できます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-206">Therefore, you can set the default encoding of them using the `$PSDefaultParameterValues` preference variable as shown in this example:</span></span>

```powershell
$PSDefaultParameterValues['Out-File:Encoding'] = 'utf8'
```

<span data-ttu-id="6c7b1-207">**Encoding** パラメーターを持つすべてのコマンドレットの既定のエンコードを変更するには、次のステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-207">Use the following statement to change the default encoding for all cmdlets that have the **Encoding** parameter.</span></span>

```powershell
$PSDefaultParameterValues['*:Encoding'] = 'utf8'
```

> [!IMPORTANT]
> <span data-ttu-id="6c7b1-208">このコマンドを PowerShell プロファイルに含めると、エンコードを明示的に指定していないすべてのコマンドとスクリプトに影響を与えるセッショングローバル設定が設定されます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-208">Putting this command in your PowerShell profile makes the preference a session-global setting that affects all commands and scripts that do not explicitly specify an encoding.</span></span>
>
> <span data-ttu-id="6c7b1-209">同様に、同じように動作させるスクリプトまたはモジュールにこのようなコマンドを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-209">Similarly, you should include such commands in your scripts or modules that you want to behave the same way.</span></span> <span data-ttu-id="6c7b1-210">これらのコマンドを使用すると、他のユーザー、別のコンピューター、または別のバージョンの PowerShell で実行されている場合でも、コマンドレットの動作が同じになります。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-210">Using these commands ensure that cmdlets behave the same way even when run by another user, on a different computer, or in a different version of PowerShell.</span></span>

<span data-ttu-id="6c7b1-211">自動変数は、 `$OutputEncoding` PowerShell による外部プログラムとの通信に使用されるエンコーディングに影響します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-211">The automatic variable `$OutputEncoding` affects the encoding PowerShell uses to communicate with external programs.</span></span> <span data-ttu-id="6c7b1-212">出力リダイレクト演算子と PowerShell コマンドレットがファイルに保存するために使用するエンコーディングには影響しません。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-212">It has no effect on the encoding that the output redirection operators and PowerShell cmdlets use to save to files.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c7b1-213">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c7b1-213">See also</span></span>

- [<span data-ttu-id="6c7b1-214">.NET での文字エンコードの概要</span><span class="sxs-lookup"><span data-stu-id="6c7b1-214">Introduction to character encoding in .NET</span></span>](/dotnet/standard/base-types/character-encoding-introduction)
- [<span data-ttu-id="6c7b1-215">コードページ-Win32 アプリ</span><span class="sxs-lookup"><span data-stu-id="6c7b1-215">Code Pages - Win32 apps</span></span>](/windows/win32/intl/code-pages)
- [<span data-ttu-id="6c7b1-216">Unicode 標準</span><span class="sxs-lookup"><span data-stu-id="6c7b1-216">The Unicode Standard</span></span>](https://www.unicode.org/standard/standard.html)
- [<span data-ttu-id="6c7b1-217">Encoding. コードページ</span><span class="sxs-lookup"><span data-stu-id="6c7b1-217">Encoding.CodePage</span></span>](/dotnet/api/system.text.encoding.codepage)
- [<span data-ttu-id="6c7b1-218">UTF-16LE</span><span class="sxs-lookup"><span data-stu-id="6c7b1-218">UTF-16LE</span></span>](https://wikipedia.org/wiki/UTF-16)
- [<span data-ttu-id="6c7b1-219">バイト順マーク</span><span class="sxs-lookup"><span data-stu-id="6c7b1-219">Byte order mark</span></span>](https://wikipedia.org/wiki/Byte_order_mark)
- [<span data-ttu-id="6c7b1-220">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="6c7b1-220">about_Preference_Variables</span></span>](about_Preference_Variables.md)
