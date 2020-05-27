---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
title: 新規および更新されたコマンドレット
ms.openlocfilehash: ffd5db2d4fc9bf8f67ef5e352633ad3209f72c87
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809118"
---
# <a name="new-and-updated-cmdlets"></a><span data-ttu-id="b1f16-103">新規および更新されたコマンドレット</span><span class="sxs-lookup"><span data-stu-id="b1f16-103">New and updated cmdlets</span></span>

<span data-ttu-id="b1f16-104">Microsoft では、コミュニティからのフィードバックに基づいて、コマンドレットの新たな追加、および既存のコマンドレットの更新を行いました。</span><span class="sxs-lookup"><span data-stu-id="b1f16-104">We have added new and updated existing cmdlets based on feedback from the community.</span></span>

## <a name="archive-cmdlets"></a><span data-ttu-id="b1f16-105">アーカイブのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="b1f16-105">Archive cmdlets</span></span>

<span data-ttu-id="b1f16-106">2 つの新しいコマンドレット、`Compress-Archive` と `Expand-Archive` では、ZIP ファイルを圧縮および展開できます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-106">Two new cmdlets, `Compress-Archive` and `Expand-Archive`, let you compress and expand ZIP files.</span></span>

<span data-ttu-id="b1f16-107">詳細については、[Microsoft.Powershell.Archive](/powershell/module/microsoft.powershell.archive/) モジュールに関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f16-107">For more information, see the [Microsoft.Powershell.Archive](/powershell/module/microsoft.powershell.archive/) module documentation.</span></span>

## <a name="catalog-cmdlets"></a><span data-ttu-id="b1f16-108">カタログ コマンドレット</span><span class="sxs-lookup"><span data-stu-id="b1f16-108">Catalog Cmdlets</span></span>

<span data-ttu-id="b1f16-109">Microsoft.PowerShell.Security モジュールに次の新しいコマンドレットが 2 つ追加されました。</span><span class="sxs-lookup"><span data-stu-id="b1f16-109">Two new cmdlets have been added in the Microsoft.PowerShell.Security module.</span></span>

- [<span data-ttu-id="b1f16-110">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="b1f16-110">New-FileCatalog</span></span>](/powershell/module/microsoft.powershell.security/New-FileCatalog)
- [<span data-ttu-id="b1f16-111">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="b1f16-111">Test-FileCatalog</span></span>](/powershell/module/microsoft.powershell.security/Test-FileCatalog)

<span data-ttu-id="b1f16-112">これらでは、Windows カタログ ファイルが生成および検証されます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-112">These generate and validate Windows catalog files.</span></span>

## <a name="clipboard-cmdlets"></a><span data-ttu-id="b1f16-113">クリップボードのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="b1f16-113">Clipboard cmdlets</span></span>

<span data-ttu-id="b1f16-114">`Get-Clipboard` と `Set-Clipboard` を使うと、Windows PowerShell セッションとの間でコンテンツを容易に転送できます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-114">`Get-Clipboard` and `Set-Clipboard` make it easier for you to transfer content to and from a Windows PowerShell session.</span></span> <span data-ttu-id="b1f16-115">クリップボードのコマンドレットは、画像、オーディオ ファイル、ファイルのリスト、およびテキストをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b1f16-115">The Clipboard cmdlets support images, audio files, file lists, and text.</span></span>

<span data-ttu-id="b1f16-116">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f16-116">For more information, see:</span></span>

- [<span data-ttu-id="b1f16-117">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="b1f16-117">Get-Clipboard</span></span>](/powershell/module/Microsoft.PowerShell.Management/Get-Clipboard)
- [<span data-ttu-id="b1f16-118">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="b1f16-118">Set-Clipboard</span></span>](/powershell/module/Microsoft.PowerShell.Management/Set-Clipboard)

## <a name="cryptographic-message-syntax-cms-cmdlets"></a><span data-ttu-id="b1f16-119">Cryptographic Message Syntax (CMS) コマンドレット</span><span class="sxs-lookup"><span data-stu-id="b1f16-119">Cryptographic Message Syntax (CMS) cmdlets</span></span>

<span data-ttu-id="b1f16-120">Cryptographic Message Syntax コマンドレットは、[RFC5652](https://tools.ietf.org/html/rfc5652.html) で説明されているように暗号によってメッセージを保護するための IETF 標準書式を使用して、コンテンツの暗号化と暗号化解除をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b1f16-120">The Cryptographic Message Syntax cmdlets support encryption and decryption of content using the IETF standard format for cryptographically protecting messages as documented by [RFC5652](https://tools.ietf.org/html/rfc5652.html).</span></span>

<span data-ttu-id="b1f16-121">CMS 暗号化標準では、公開キー暗号化が実装されます。公開キー暗号化では、コンテンツの暗号化に使用されるキー (*公開キー*) とコンテンツの暗号化解除に使用されるキー (*秘密キー*) は別です。</span><span class="sxs-lookup"><span data-stu-id="b1f16-121">The CMS encryption standard implements public key cryptography, where the key used to encrypt content (the *public key*) and the key used to decrypt content (the *private key*) are separate.</span></span>

<span data-ttu-id="b1f16-122">公開キーは広く共有でき、機密データではありません。</span><span class="sxs-lookup"><span data-stu-id="b1f16-122">Your public key can be shared widely and is not sensitive data.</span></span> <span data-ttu-id="b1f16-123">公開キーで暗号化したコンテンツは、秘密キーを使用してのみ暗号化解除できます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-123">Any content encrypted with the public key can only be decrypted using the private key.</span></span> <span data-ttu-id="b1f16-124">公開キー暗号化の詳細については、「[公開鍵暗号](https://en.wikipedia.org/wiki/Public-key_cryptography)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f16-124">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="b1f16-125">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b1f16-125">For more information see:</span></span>

- [<span data-ttu-id="b1f16-126">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="b1f16-126">Get-CmsMessage</span></span>](/powershell/module/Microsoft.PowerShell.Security/Get-CmsMessage)
- [<span data-ttu-id="b1f16-127">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="b1f16-127">Protect-CmsMessage</span></span>](/powershell/module/Microsoft.PowerShell.Security/Protect-CmsMessage)
- [<span data-ttu-id="b1f16-128">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="b1f16-128">Unprotect-CmsMessage</span></span>](/powershell/module/Microsoft.PowerShell.Security/unprotect-CmsMessage)

<span data-ttu-id="b1f16-129">証明書が PowerShell でデータ暗号化証明書として認識されるには、'Code Signing' または 'Encrypted Mail' のような一意のキー使用法識別子 (EKU) が必要です。</span><span class="sxs-lookup"><span data-stu-id="b1f16-129">Certificates require a unique key usage identifier (EKU), such as 'Code Signing' or 'Encrypted Mail', to identify them as data encryption certificates in PowerShell.</span></span> <span data-ttu-id="b1f16-130">証明書プロバイダーでドキュメントの暗号化証明書を表示するには、`Get-ChildItem` の **DocumentEncryptionCert** 動的パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1f16-130">To view document encryption certificates in the certificate provider, you can use the **DocumentEncryptionCert** dynamic parameter of `Get-ChildItem`:</span></span>

```powershell
Get-ChildItem Cert:\CurrentUser -DocumentEncryptionCert -Recurse
```

## <a name="extract-and-parse-structured-objects-from-string-content"></a><span data-ttu-id="b1f16-131">文字列コンテンツから構造化オブジェクトを抽出して分析する</span><span class="sxs-lookup"><span data-stu-id="b1f16-131">Extract and parse structured objects from string content</span></span>

### <a name="convertfrom-string"></a><span data-ttu-id="b1f16-132">ConvertFrom-String</span><span class="sxs-lookup"><span data-stu-id="b1f16-132">ConvertFrom-String</span></span>

<span data-ttu-id="b1f16-133">新しい `ConvertFrom-String` コマンドレットでは、次の 2 つのモードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b1f16-133">The new `ConvertFrom-String` cmdlet supports two modes:</span></span>

- <span data-ttu-id="b1f16-134">基本区切りの解析</span><span class="sxs-lookup"><span data-stu-id="b1f16-134">Basic delimited parsing</span></span>
- <span data-ttu-id="b1f16-135">自動生成されるサンプルによる解析</span><span class="sxs-lookup"><span data-stu-id="b1f16-135">Auto generated example-driven parsing</span></span>

<span data-ttu-id="b1f16-136">区切り記号による解析では、既定で、入力を空白の位置で分割し、生成されるグループにプロパティ名を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-136">Delimited parsing, by default, splits the input at white space, and assigns property names to the resulting groups.</span></span>

<span data-ttu-id="b1f16-137">**UpdateTemplate** パラメーターは、学習アルゴリズムの結果をテンプレート ファイル内のコメントに保存します。</span><span class="sxs-lookup"><span data-stu-id="b1f16-137">The **UpdateTemplate** parameter saves the results of the learning algorithm into a comment in the template file.</span></span> <span data-ttu-id="b1f16-138">これにより、学習プロセス (最も時間のかかる段階) が 1 回限りのコストになります。</span><span class="sxs-lookup"><span data-stu-id="b1f16-138">This makes the learning process (the slowest stage) a one-time cost.</span></span> <span data-ttu-id="b1f16-139">`ConvertFrom-String` をエンコードされた学習アルゴリズムを含むテンプレートを使って実行すると、ほぼ瞬時に完了します。</span><span class="sxs-lookup"><span data-stu-id="b1f16-139">Running `ConvertFrom-String` with a template that contains the encoded learning algorithm is now nearly instantaneous.</span></span>

<span data-ttu-id="b1f16-140">詳細については、「[ConvertFrom-String](/powershell/module/Microsoft.PowerShell.Utility/ConvertFrom-String)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f16-140">For more information, see [ConvertFrom-String](/powershell/module/Microsoft.PowerShell.Utility/ConvertFrom-String).</span></span>

### <a name="convert-string"></a><span data-ttu-id="b1f16-141">Convert-String</span><span class="sxs-lookup"><span data-stu-id="b1f16-141">Convert-String</span></span>

<span data-ttu-id="b1f16-142">`Convert-String` では、テキストをどのように表示するかのその前後の例を提供します。</span><span class="sxs-lookup"><span data-stu-id="b1f16-142">`Convert-String` allows you to provide before and after examples of how you want text to look.</span></span> <span data-ttu-id="b1f16-143">テキストは、コマンドレットによって自動的に書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-143">The cmdlet formats your text automatically.</span></span>

<span data-ttu-id="b1f16-144">詳細については、「[Convert-String](/powershell/module/Microsoft.PowerShell.Utility/Convert-String)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f16-144">For more information, see [Convert-String](/powershell/module/Microsoft.PowerShell.Utility/Convert-String).</span></span>

## <a name="updates-to-fileinfo-object"></a><span data-ttu-id="b1f16-145">FileInfo オブジェクトの更新</span><span class="sxs-lookup"><span data-stu-id="b1f16-145">Updates to FileInfo object</span></span>

<span data-ttu-id="b1f16-146">ファイルのバージョン情報は、特にファイルにパッチが適用された場合に、間違えやすいです。</span><span class="sxs-lookup"><span data-stu-id="b1f16-146">File version information can be misleading, especially in cases where the file was patched.</span></span> <span data-ttu-id="b1f16-147">WMF 5.0 では、**FileInfo** オブジェクトに新しいスクリプト プロパティとして **FileVersionRaw** と **ProductVersionRaw** が追加されています。</span><span class="sxs-lookup"><span data-stu-id="b1f16-147">WMF 5.0 adds new **FileVersionRaw** and **ProductVersionRaw** script properties to **FileInfo** objects.</span></span>
<span data-ttu-id="b1f16-148">powershell.exe に対して表示されるプロパティを次に示します ($pid は PowerShell プロセスの ID であるとします)。</span><span class="sxs-lookup"><span data-stu-id="b1f16-148">Here are the properties as displayed for powershell.exe (assuming $pid is the ID of the PowerShell process):</span></span>

```powershell
Get-Process -Id $pid -FileVersionInfo | Format-List *version*
```

```Output
FileVersionRaw    : 10.0.17763.1
ProductVersionRaw : 10.0.17763.1
FileVersion       : 10.0.17763.1 (WinBuild.160101.0800)
ProductVersion    : 10.0.17763.1
```

## <a name="format-hex"></a><span data-ttu-id="b1f16-149">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="b1f16-149">Format-Hex</span></span>

<span data-ttu-id="b1f16-150">`Format-Hex` を使用すると、テキスト データやバイナリ データを 16 進数形式で表示できます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-150">`Format-Hex` lets you view text or binary data in hexadecimal format.</span></span>

<span data-ttu-id="b1f16-151">詳細については、「[Format-Hex](/powershell/module/microsoft.powershell.utility/format-hex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f16-151">For more information, see [Format-Hex](/powershell/module/microsoft.powershell.utility/format-hex).</span></span>

## <a name="get-childitem-has--depth-parameter"></a><span data-ttu-id="b1f16-152">Get-ChildItem の -Depth パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1f16-152">Get-ChildItem has -Depth parameter</span></span>

<span data-ttu-id="b1f16-153">`Get-ChildItem` に、再帰を制限する **Recurse** で使用する **Depth** パラメーターが追加されました。</span><span class="sxs-lookup"><span data-stu-id="b1f16-153">`Get-ChildItem` now has a **Depth** parameter for use with **Recurse** to limit the recursion:</span></span>

## <a name="modules-support-for-declaring-version-ranges-1-etc"></a><span data-ttu-id="b1f16-154">バージョン範囲 (1. \* など) の宣言をサポートするモジュール</span><span class="sxs-lookup"><span data-stu-id="b1f16-154">Modules support for declaring version ranges (1.\*, etc)</span></span>

<span data-ttu-id="b1f16-155">**MinimumVersion** と **MaximumVersion** を組み合わせることにより、特定の範囲内でモジュールをインポートできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b1f16-155">You can now combine **MinimumVersion** and **MaximumVersion** to import module within specific range.</span></span> <span data-ttu-id="b1f16-156">このパラメーターでは、ワイルドカードもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b1f16-156">The parameters also support wildcards.</span></span>

```powershell
Import-Module psreadline -Verbose -MinimumVersion 1.0 -MaximumVersion 1.2.*
```

```Output
VERBOSE: Loading module from path 'C:\Program Files\WindowsPowerShell\Modules\psreadline\1.1\psreadline.psd1'.
VERBOSE: Importing cmdlet 'Get-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Get-PSReadlineOption'.
VERBOSE: Importing cmdlet 'Remove-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Set-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Set-PSReadlineOption'.
VERBOSE: Importing function 'PSConsoleHostReadline'.
```

## <a name="new-guid"></a><span data-ttu-id="b1f16-157">New-Guid</span><span class="sxs-lookup"><span data-stu-id="b1f16-157">New-Guid</span></span>

<span data-ttu-id="b1f16-158">一意の識別子が必要なシナリオは多数あります。</span><span class="sxs-lookup"><span data-stu-id="b1f16-158">There are many scenarios where youneed for unique identifier.</span></span> <span data-ttu-id="b1f16-159">`New-GUID` コマンドレットでは簡単に新しい GUID を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-159">The `New-GUID` cmdlet provides a simple way to create a new GUID.</span></span>

```powershell
New-Guid
```

```Output
Guid
----
e19d6ea5-3cc2-4db9-8095-0cdaed5a703d
```

## <a name="nonewline-parameter"></a><span data-ttu-id="b1f16-160">NoNewLine パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1f16-160">NoNewLine parameter</span></span>

<span data-ttu-id="b1f16-161">`Out-File`、`Add-Content`、および `Set-Content` に、出力後の改行を省略する新しい **NoNewline** スイッチが追加されました。</span><span class="sxs-lookup"><span data-stu-id="b1f16-161">`Out-File`, `Add-Content`, and `Set-Content` now have a new **NoNewline** switch which omits a new line after the output.</span></span> <span data-ttu-id="b1f16-162">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b1f16-162">For example:</span></span>

```powershell
"This is " | Out-File -FilePath Example.txt -NoNewline
"a single " | Add-Content -Path Example.txt -NoNewline
"sentence." | Add-Content -Path Example.txt -NoNewline
Get-Content .\Example.txt
```

```Output
This is a single sentence.
```

<span data-ttu-id="b1f16-163">**NoNewline** を指定しないと、各フラグメントが別個の行に出力されます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-163">Without **NoNewline** specified, each fragment would be on a separate line:</span></span>

```powershell
"This is " | Out-File -FilePath Example.txt
"a single " | Add-Content -Path Example.txt
"sentence." | Add-Content -Path Example.txt
Get-Content .\Example.txt
```

```Output
This is
a single
sentence.
```

## <a name="interact-with-symbolic-links-using-improved-item-cmdlets"></a><span data-ttu-id="b1f16-164">機能を強化された Item コマンドレットを使ってシンボリック リンクを操作する</span><span class="sxs-lookup"><span data-stu-id="b1f16-164">Interact with Symbolic links using improved Item cmdlets</span></span>

<span data-ttu-id="b1f16-165">シンボリック リンクをサポートする、Item コマンドレットや、関連するいくつかのコマンドレットが拡張されました。</span><span class="sxs-lookup"><span data-stu-id="b1f16-165">The Item cmdlet and a few related cmdlets have been extended to support symbolic links.</span></span>

### <a name="symbolic-link-files"></a><span data-ttu-id="b1f16-166">シンボリック リンク ファイル</span><span class="sxs-lookup"><span data-stu-id="b1f16-166">Symbolic link files</span></span>

<span data-ttu-id="b1f16-167">この例では、$pshome\profile.ps1 にリンクされる MySymLinkFile.txt という新しいシンボリック リンク ファイルを C:\Temp に作成します。</span><span class="sxs-lookup"><span data-stu-id="b1f16-167">In this example, we create a new symbolic link file named MySymLinkFile.txt in C:\Temp which links to $pshome\profile.ps1.</span></span> <span data-ttu-id="b1f16-168">結果は、3 つの例のいずれでも同じになります。</span><span class="sxs-lookup"><span data-stu-id="b1f16-168">All three examples produce the same result.</span></span>

```powershell
New-Item -ItemType SymbolicLink -Path C:\Temp -Name MySymLinkFile.txt -Value $pshome\profile.ps1
New-Item -ItemType SymbolicLink -Path C:\Temp\MySymLinkFile.txt -Value $pshome\profile.ps1
New-Item -ItemType SymbolicLink -Name C:\Temp\MySymLinkFile.txt -Value $pshome\profile.ps1
```

### <a name="symbolic-link-directories"></a><span data-ttu-id="b1f16-169">シンボリック リンク ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="b1f16-169">Symbolic link directories</span></span>

<span data-ttu-id="b1f16-170">この例では、$pshome フォルダーにリンクされる MySymLinkDir という新しいシンボリック リンク ディレクトリを C:\Temp に作成します。</span><span class="sxs-lookup"><span data-stu-id="b1f16-170">In this example, we create a new symbolic link directory named MySymLinkDir in C:\Temp which links to the $pshome folder.</span></span> <span data-ttu-id="b1f16-171">結果は、3 つの例のいずれでも同じになります。</span><span class="sxs-lookup"><span data-stu-id="b1f16-171">All three examples produce the same result.</span></span>

```powershell
New-Item -ItemType SymbolicLink -Path C:\Temp -Name MySymLinkDir -Value $pshome
New-Item -ItemType SymbolicLink -Path C:\Temp\MySymLinkDir -Value $pshome
New-Item -ItemType SymbolicLink -Name C:\Temp\MySymLinkDir -Value $pshome
```

### <a name="hard-links"></a><span data-ttu-id="b1f16-172">ハード リンク</span><span class="sxs-lookup"><span data-stu-id="b1f16-172">Hard links</span></span>

<span data-ttu-id="b1f16-173">**パス**と**名前**の同じ組み合わせが前述のように許可されています。</span><span class="sxs-lookup"><span data-stu-id="b1f16-173">The same combinations of **Path** and **Name** allowed as described above.</span></span>

```powershell
New-Item -ItemType HardLink -Path C:\Temp -Name MyHardLinkFile.txt -Value $pshome\profile.ps1
```

### <a name="directory-junctions"></a><span data-ttu-id="b1f16-174">ディレクトリ ジャンクション</span><span class="sxs-lookup"><span data-stu-id="b1f16-174">Directory junctions</span></span>

<span data-ttu-id="b1f16-175">**パス**と**名前**の同じ組み合わせが前述のように許可されています。</span><span class="sxs-lookup"><span data-stu-id="b1f16-175">The same combinations of **Path** and **Name** allowed as described above.</span></span>

```powershell
New-Item -ItemType Junction -Path C:\Temp\MyJunctionDir -Value $pshome
```

### <a name="get-childitem"></a><span data-ttu-id="b1f16-176">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="b1f16-176">Get-ChildItem</span></span>

<span data-ttu-id="b1f16-177">`Get-ChildItem` の **Mode** プロパティに、シンボリック リンク ファイルまたはディレクトリを示す 'l' が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b1f16-177">`Get-ChildItem` now displays an 'l' in the **Mode** property to indicate a symbolic link file or directory.</span></span>

```powershell
Get-ChildItem C:\Temp | sort LastWriteTime -Descending

Directory: C:\Temp

Mode       LastWriteTime Length Name
----       ------------- ------ ----
-a---- 6/13/2014 3:00 PM     16 File.txt
d----- 6/13/2014 3:00 PM        Directory
-a---l 6/13/2014 3:21 PM      0 MySymLinkFile.txt
d----l 6/13/2014 3:22 PM        MySymLinkDir
-a---l 6/13/2014 3:23 PM  23304 MyHardLinkFile.txt
d----l 6/13/2014 3:24 PM        MyJunctionDir
```

### <a name="remove-item"></a><span data-ttu-id="b1f16-178">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="b1f16-178">Remove-Item</span></span>

<span data-ttu-id="b1f16-179">シンボリック リンクの削除は、その他の任意のアイテムの種類の削除と同様に実行できます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-179">Removing symbolic links works like removing any other item type.</span></span>

```powershell
Remove-Item C:\Temp\MySymLinkFile.txt
Remove-Item C:\Temp\MySymLinkDir
```

<span data-ttu-id="b1f16-180">**Force** パラメーターを使用すると、ターゲット ディレクトリとシンボリック リンクのファイルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-180">Use the **Force** parameter to remove the files in the target directory and the symbolic link.</span></span>

```powershell
Remove-Item C:\Temp\MySymLinkDir -Force
```

## <a name="new-temporaryfile"></a><span data-ttu-id="b1f16-181">New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="b1f16-181">New-TemporaryFile</span></span>

<span data-ttu-id="b1f16-182">スクリプトでは、ときおり、一時ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1f16-182">Sometimes in your scripts, you must create a temporary file.</span></span> <span data-ttu-id="b1f16-183">これは、次のように `New-TemporaryFile` コマンドレットで実行できます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-183">You can now do this with the `New-TemporaryFile` cmdlet:</span></span>

```powershell
$tempFile = New-TemporaryFile
$tempFile.FullName
```

```Output
C:\Users\user1\AppData\Local\Temp\tmp375.tmp
```

## <a name="network-switch-management-with-powershell"></a><span data-ttu-id="b1f16-184">PowerShell を使用したネットワーク スイッチの管理</span><span class="sxs-lookup"><span data-stu-id="b1f16-184">Network Switch Management with PowerShell</span></span>

<span data-ttu-id="b1f16-185">WMF 5.0 で導入されたネットワーク スイッチのコマンドレットを使用すると、Windows Server 2012 R2 ロゴ認定を受けたネットワーク スイッチに、スイッチ、仮想 LAN (VLAN)、および基本的なレイヤー 2 ネットワーク スイッチ ポートの構成を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-185">The Network Switch cmdlets, introduced in WMF 5.0, enable you to apply switch, virtual LAN (VLAN), and basic Layer 2 network switch port configuration to Windows Server 2012 R2 logo-certified network switches.</span></span> <span data-ttu-id="b1f16-186">これらのコマンドレットを使用して、次のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-186">Using these cmdlets you can perform:</span></span>

- <span data-ttu-id="b1f16-187">次のようなグローバル スイッチ構成:</span><span class="sxs-lookup"><span data-stu-id="b1f16-187">Global switch configuration, such as:</span></span>
  - <span data-ttu-id="b1f16-188">ホスト名の設定</span><span class="sxs-lookup"><span data-stu-id="b1f16-188">Set host name</span></span>
  - <span data-ttu-id="b1f16-189">スイッチ バナーの設定</span><span class="sxs-lookup"><span data-stu-id="b1f16-189">Set switch banner</span></span>
  - <span data-ttu-id="b1f16-190">構成の保持</span><span class="sxs-lookup"><span data-stu-id="b1f16-190">Persist configuration</span></span>
  - <span data-ttu-id="b1f16-191">機能の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="b1f16-191">Enable or disable feature</span></span>

- <span data-ttu-id="b1f16-192">VLAN 構成:</span><span class="sxs-lookup"><span data-stu-id="b1f16-192">VLAN configuration:</span></span>
  - <span data-ttu-id="b1f16-193">VLAN の作成または削除</span><span class="sxs-lookup"><span data-stu-id="b1f16-193">Create or remove VLAN</span></span>
  - <span data-ttu-id="b1f16-194">VLAN の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="b1f16-194">Enable or disable VLAN</span></span>
  - <span data-ttu-id="b1f16-195">VLAN の列挙</span><span class="sxs-lookup"><span data-stu-id="b1f16-195">Enumerate VLAN</span></span>
  - <span data-ttu-id="b1f16-196">VLAN にわかりやすい名前を設定する</span><span class="sxs-lookup"><span data-stu-id="b1f16-196">Set friendly name to a VLAN</span></span>

- <span data-ttu-id="b1f16-197">レイヤー 2 ポート構成:</span><span class="sxs-lookup"><span data-stu-id="b1f16-197">Layer 2 port configuration:</span></span>
  - <span data-ttu-id="b1f16-198">ポートの列挙</span><span class="sxs-lookup"><span data-stu-id="b1f16-198">Enumerate ports</span></span>
  - <span data-ttu-id="b1f16-199">ポートの有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="b1f16-199">Enable or disable ports</span></span>
  - <span data-ttu-id="b1f16-200">ポートのモードおよびプロパティの設定</span><span class="sxs-lookup"><span data-stu-id="b1f16-200">Set port modes and properties</span></span>
  - <span data-ttu-id="b1f16-201">ポートのトランクまたはアクセスに VLAN を追加または関連付ける</span><span class="sxs-lookup"><span data-stu-id="b1f16-201">Add or associate VLAN to Trunk or Access on the port</span></span>

<span data-ttu-id="b1f16-202">詳細については、[NetworkSwitchManager](/powershell/module/networkswitchmanager/) に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f16-202">For more information, see the [NetworkSwitchManager](/powershell/module/networkswitchmanager/) documentation.</span></span>

## <a name="generate-powershell-cmdlets-based-on-an-odata-endpoint-with-odatautils"></a><span data-ttu-id="b1f16-203">ODataUtils を使用した OData エンドポイントに基づく PowerShell コマンドレットの生成</span><span class="sxs-lookup"><span data-stu-id="b1f16-203">Generate PowerShell cmdlets based on an OData endpoint with ODataUtils</span></span>

<span data-ttu-id="b1f16-204">ODataUtils モジュールでは、OData をサポートする REST エンドポイントから PowerShell コマンドレットを生成できます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-204">The ODataUtils module allows generation of PowerShell cmdlets from REST endpoints that support OData.</span></span> <span data-ttu-id="b1f16-205">Microsoft.PowerShell.ODataUtils モジュールには、次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="b1f16-205">The Microsoft.PowerShell.ODataUtils module includes the following features:</span></span>

- <span data-ttu-id="b1f16-206">サーバー側エンドポイントからクライアント側への追加情報のチャネル。</span><span class="sxs-lookup"><span data-stu-id="b1f16-206">Channel additional information from server-side endpoint to client side.</span></span>
- <span data-ttu-id="b1f16-207">クライアント側ページング サポート</span><span class="sxs-lookup"><span data-stu-id="b1f16-207">Client-side paging support</span></span>
- <span data-ttu-id="b1f16-208">-Select パラメーターを使用したサーバー側フィルタリング</span><span class="sxs-lookup"><span data-stu-id="b1f16-208">Server-side filtering by using the -Select parameter</span></span>
- <span data-ttu-id="b1f16-209">Web 要求のヘッダーのサポート</span><span class="sxs-lookup"><span data-stu-id="b1f16-209">Support for web request headers</span></span>

<span data-ttu-id="b1f16-210">`Export-ODataEndPointProxy` コマンドレットで生成されるプロキシ コマンドレットは、サーバー側の OData エンドポイントからの**情報**ストリームの追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b1f16-210">The proxy cmdlets generated by the `Export-ODataEndPointProxy` cmdlet provide additional information from the server-side OData endpoint on the **Information** stream.</span></span>

```powershell
Import-Module Microsoft.PowerShell.ODataUtils -Force
$generatedProxyModuleDir = Join-Path -Path $env:SystemDrive -ChildPath 'ODataDemoProxy'
$uri = "http://services.odata.org/V3/(S(fhleiief23wrm5a5nhf542q5))/OData/OData.svc/"
Export-ODataEndpointProxy -Uri $uri -OutputModule $generatedProxyModuleDir -Force -AllowUnSecureConnection -Verbose -AllowClobber
```

<span data-ttu-id="b1f16-211">次の例では、上位の製品を取得してその出力を `$infoStream` 変数にキャプチャしています。</span><span class="sxs-lookup"><span data-stu-id="b1f16-211">In the following example, we are retrieving top product and capturing the output in the `$infoStream` variable.</span></span>

<span data-ttu-id="b1f16-212">**IncludeTotalResponseCount** パラメーターを指定することにより、サーバー上のすべての **Product** レコードの総数を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-212">By specifying **IncludeTotalResponseCount** parameter, we get the total count of all the **Product** records available on the server.</span></span>

```powershell
Import-Module $generatedProxyModuleDir -Force
$product = Get-Product -Top 1 -AllowUnsecureConnection -AllowAdditionalData -IncludeTotalResponseCount -InformationVariable infoStream
$additionalInfo = $infoStream.GetEnumerator() | % MessageData
$additionalInfo['odata.count']
```

<span data-ttu-id="b1f16-213">クライアント側ページング サポートを使用して、サーバーからレコードをバッチで取得できます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-213">You can get the records from the server in batches using client-side paging support.</span></span> <span data-ttu-id="b1f16-214">これは、ネットワーク経由でサーバーから大量のデータを取得する必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-214">This is useful when you must get a large amount of data from the server over the network.</span></span>

```powershell
$skipCount = 0
$batchSize = 3
while($skipCount -le $additionalInfo['odata.count'])
{
  Get-Product -AllowUnsecureConnection -AllowAdditionalData -Top $batchSize -Skip $skipCount
  $skipCount += $batchSize
}
```

<span data-ttu-id="b1f16-215">生成されたプロキシ コマンドレットは、クライアントが必要なレコード プロパティのみを受信するフィルターとして使用できる **Select** パラメーターをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b1f16-215">The generated proxy cmdlets support the **Select** parameter that is used as a filter to receive only the record properties that the client needs.</span></span> <span data-ttu-id="b1f16-216">フィルター処理はサーバー側で行われるため、ネットワーク経由で転送されるデータの量が削減されます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-216">The filtering occurs on the server, which reduces the amount of data that is transferred over the network.</span></span>

```powershell
Get-Product -Top 2 -AllowUnsecureConnection -AllowAdditionalData -Select Name
```

<span data-ttu-id="b1f16-217">`Export-ODataEndpointProxy` コマンドレットとそれによって生成されるプロキシ コマンドレットで、**Header** パラメーターがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b1f16-217">The `Export-ODataEndpointProxy` cmdlet, and the proxy cmdlets generated by it, now support the **Headers** parameter.</span></span> <span data-ttu-id="b1f16-218">このヘッダーを使用すると、OData エンドポイントで必要な追加情報をチャネルできます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-218">The header can be used to channel additional information expected by the OData endpoint.</span></span>

<span data-ttu-id="b1f16-219">次の例では、サブスクリプション キーを含むハッシュ テーブルが **Headers** パラメーターに提供されます。</span><span class="sxs-lookup"><span data-stu-id="b1f16-219">In the following example, a hash table containing a Subscription key is provided to the **Headers** parameter.</span></span> <span data-ttu-id="b1f16-220">これは、認証にサブスクリプション キーを必要とするサービスの典型例です。</span><span class="sxs-lookup"><span data-stu-id="b1f16-220">This is a typical example for services that are expecting a Subscription key for authentication.</span></span>

```powershell
Export-ODataEndpointProxy -Uri $endPointUri -OutputModule $generatedProxyModuleDir -Force -AllowUnSecureConnection -Verbose -Headers @{'subscription-key'='XXXX'}
```
