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
# <a name="understanding-file-encoding-in-vscode-and-powershell"></a>VSCode と PowerShell でのファイルのエンコードの概要

を作成および PowerShell スクリプトを編集する VS Code を使用する場合、正しい文字のエンコード形式を使用して、ファイルを保存することが重要です。

## <a name="what-is-file-encoding-and-why-is-it-important"></a>ファイルのエンコードと、重要である理由とは

VSCode では、バッファーに文字の人間の入力文字列とファイル システムにバイトの読み取り/書き込みブロック間のインターフェイスを管理します。 VSCode では、ファイルを保存、これを行うエンコード テキストが使用されます。

同様に、PowerShell スクリプトの実行時に、PowerShell のプログラムにファイルを再構築する文字をファイル内のバイトを変換する必要があります。 VSCode がファイルを書き込むし、PowerShell は、ファイルを読み取るために、同じエンコーディング システムを使用している必要があります。 このプロセスの PowerShell スクリプトの解析に:*バイト* -> *文字* -> *トークン* ->  *抽象構文ツリー* -> *実行*します。

VSCode と PowerShell の両方が、実用的な既定のエンコード構成と共にインストールされます。 ただし、PowerShell で使用される既定のエンコーディングは、PowerShell Core (v6.x) のリリースで変更されました。 VSCode での PowerShell または PowerShell の拡張機能の使用に関する問題がないことを確認するには、VSCode と PowerShell の設定を構成する必要があります適切です。

## <a name="common-causes-of-encoding-issues"></a>エンコーディングの問題の一般的な原因

VSCode またはスクリプト ファイルのエンコードしても PowerShell の必要なエンコードは一致しない場合、エンコーディングの問題が発生します。 PowerShell ファイルのエンコーディングを自動的に決定する方法はありません。

内にない文字を使用しているときに、問題をエンコードする可能性が高く、 [7 ビット ASCII 文字セット](https://ascii.cl/)します。 たとえば、次のように入力します。

- ラテン文字にアクセント記号 (`É`、 `ü`)
- キリル語などのラテン文字以外の文字 (`Д`、 `Ц`)
- Han 中国語 (`脚`、 `本`)

エンコーディングの問題の一般的な理由は次のとおりです。

- VSCode と PowerShell のエンコーディングがその既定値から変更されていません。 PowerShell 5.1 と下、既定値は、VSCode の異なるエンコードです。
- 別のエディターが開き、新しいエンコードでファイルを上書きします。 これは、多くの場合、ISE で発生します。
- ファイルは、どのような VSCode または PowerShell から期待とは別のエンコーディングをソース管理にチェックします。 これは、コラボレーターでさまざまなエンコード構成エディターを使用する場合に発生します。

### <a name="how-to-tell-when-you-have-encoding-issues"></a>エンコーディングの問題を作成するときに指定する方法

多くの場合、エンコーディング エラーが発生、スクリプトのエラーを解析します。 スクリプトに奇妙な文字のシーケンスがある場合、問題できます。 En dash を次の例で (`–`) 文字として表示される`â€“`:

```Output
Send-MailMessage : A positional parameter cannot be found that accepts argument 'Testing FuseMail SMTP...'.
At C:\Users\<User>\<OneDrive>\Development\PowerShell\Scripts\Send-EmailUsingSmtpRelay.ps1:6 char:1
+ Send-MailMessage â€“From $from â€“To $recipient1 â€“Subject $subject  ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Send-MailMessage], ParameterBindingException
    + FullyQualifiedErrorId : PositionalParameterNotFound,Microsoft.PowerShell.Commands.SendMailMessage
```

この問題は、VSCode、文字をエンコードするために発生します。 `–` utf-8 バイトとして`0xE2 0x80 0x93`します。
文字として解釈されるときに、これらのバイトは、Windows 1252 としてデコード、`â€“`します。

表示されるいくつかの奇妙な文字シーケンスは次のとおりです。

- `–` の代わりに `â€“`
- `—` の代わりに `â€”`
- `Ä` の代わりに `Ã„2`
- `Â` 代わりに` `(改行なしスペース)
- `é` の代わりに `Ã©`

この便利な[参照](https://www.i18nqa.com/debug/utf8-debug.html)UTF 8/Windows 1252 のエンコーディングの問題を示す一般的なパターンを示しています。

## <a name="how-the-powershell-extension-in-vscode-interacts-with-encodings"></a>VSCode での PowerShell の拡張機能がエンコーディングと対話する方法

PowerShell の拡張機能は、さまざまな方法でスクリプトを使用した操作します。

1. VSCode でスクリプトを編集した内容は、拡張機能に VSCode で送信されます。 [言語サーバー プロトコル][]を utf-8 でこのコンテンツが転送されることを義務付けています。 そのため、間違ったエンコーディングを取得する拡張機能のことはできません。
2. スクリプトが、統合されたコンソールで直接実行された、読み込まれるファイルから PowerShell によって直接します。 VSCode の PowerShell のエンコードと異なる場合、ものはここへ記述が正しくありません。
3. VSCode で開いているスクリプトでは、VSCode で開かれていない別のスクリプトを参照する、拡張機能は、ファイル システムからそのスクリプトのコンテンツの読み込みにフォールバックします。 PowerShell の拡張機能が既定では utf-8 がエンコーディングが使用[バイト オーダー マーク][]、または BOM 検出の正しいエンコーディングを選択します。

問題は、BOM なしの形式のエンコーディングを前提とする場合に発生します (など[utf-8][] BOM なしでと[Windows-1252][])。
PowerShell の拡張機能の既定値は utf-8 です。 拡張機能では、VSCode のエンコード設定を変更できません。
詳細については、次を参照してください。[発行 #824](https://github.com/Microsoft/vscode/issues/824)します。

## <a name="choosing-the-right-encoding"></a>適切なエンコードを選択します。

さまざまなシステムやアプリケーションは、さまざまなエンコーディングを使用できます。

- .NET standard では、web、および Linux の世界で utf-8 はここで主要なエンコーディングです。
- 多くの .NET Framework アプリケーションを使用して、 [utf-16][]します。 歴史的な理由から、これは、"Unicode"と呼ば、用語のようになりましたが、広範なを指す[標準](https://en.wikipedia.org/wiki/Unicode)utf-8 と utf-16 の両方が含まれています。
- Windows には、Unicode のためよりも多くのネイティブ アプリケーションは、既定では、Windows 1252 を使用する継続します。

Unicode エンコーディングでは、バイト順マーク (BOM) 概念もあります。 テキストを使用するエンコーディングをデコーダーに指示するテキストの先頭の Bom が発生します。 マルチ バイト エンコーディングでは、BOM も示されます[エンディアン](https://en.wikipedia.org/wiki/Endianness)のエンコーディングします。 Bom は、バイトのテキストが Unicode BOM が存在する場合、合理的に推測できるように、Unicode 以外のテキストではめったに設計されています。

Bom は省略可能で、utf-8 の信頼性の高い規則があらゆる場所で使用されるため、Linux の世界で一般的な導入ではありません。 ほとんどの Linux アプリケーションでは、テキスト入力は utf-8 でエンコードされていることを推測します。 多くの Linux アプリケーションでは、認識され、BOM を正しく処理することが、数値必要ありません、それらのアプリケーションを使用して操作するテキストの成果物に先行します。

**したがって**:

- Windows アプリケーションと Windows PowerShell で主に作業している場合、BOM または utf-16 と utf-8 エンコードを使用する必要があります。
- プラットフォーム間で作業している場合は、bom が付加された utf-8 を使用する必要があります。
- Linux に関連付けられているコンテキストで主に作業する場合は、BOM なしの utf-8 を使用する必要があります。
- Windows 1252、ラテン語-1 は、可能であれば避ける必要のあるレガシ エンコーディング基本的にです。
  ただし、一部の古い Windows アプリケーションは、それらに依存可能性があります。
- スクリプトの署名がある注目すべきも[エンコード依存](https://github.com/PowerShell/PowerShell/issues/3466)、つまり署名されたスクリプトのエンコードの変更が必要場合します。

## <a name="configuring-vscode"></a>VSCode を構成します。

VSCode の既定のエンコードは BOM なしの utf-8 です。

設定する[VSCode のエンコード][]VSCode 設定には、(<kbd>Ctrl<kbd>+</kbd>、</kbd>) を設定し、`"files.encoding"`設定。

```json
"files.encoding": "utf8bom"
```

いくつか使用可能な値は次のとおりです。

- `utf8`: [Utf-8] BOM なし
- `utf8bom`: [Utf-8] bom が付加されました。
- `utf16le`: リトル エンディアン[utf-16]
- `utf16be`: ビッグ エンディアン[utf-16]
- `windows1252`: [Windows-1252]

GUI ビューで、このドロップダウン リストを取得する必要があります。 または JSON での入力候補を表示します。

可能な場合のエンコードを自動検出に、次を追加することもできます。

```json
"files.autoGuessEncoding": true
```

これらの設定をすべてのファイルの種類に影響しない場合は、VSCode は言語ごとの構成もできます。 設定を配置することで、言語固有の設定を作成、`[<language-name>]`フィールド。 たとえば、次のように入力します。

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

## <a name="configuring-powershell"></a>PowerShell を構成します。

PowerShell の既定のエンコードのバージョンによって異なります。

- PowerShell 6 以降で既定のエンコーディング BOM なしの utf-8 すべてのプラットフォームでは。
- Windows PowerShell で、既定のエンコーディングは、通常、Windows 1252、拡張機能の[ラテン 1][]ISO 8859-1 とも呼ばれます。

PowerShell 5 以降では、この既定エンコーディングを確認できます。

```powershell
[psobject].Assembly.GetTypes() | Where-Object { $_.Name -eq 'ClrFacade'} |
  ForEach-Object {
    $_.GetMethod('GetDefaultEncoding', [System.Reflection.BindingFlags]'nonpublic,static').Invoke($null, @())
  }
```

次[スクリプト](https://gist.github.com/rjmholt/3d8dd4849f718c914132ce3c5b278e0e)BOM なしのスクリプトについては、PowerShell セッションのエンコードとは推測を判断するために使用できます。

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

一般的にはプロファイルの設定を使用して特定のエンコーディングを使用する PowerShell の構成を行うことができます。 次の記事をご覧ください。

- [@mklement0][StackOverflow で PowerShell のエンコードに関する回答](https://stackoverflow.com/a/40098904)します。
- [@rkeithhill][PowerShell で BOM なしの utf-8 入力に対処する方法のブログの投稿](https://rkeithhill.wordpress.com/2010/05/26/handling-native-exe-output-encoding-in-utf8-with-no-bom/)します。

PowerShell を使用して、特定の入力エンコードを強制することはできません。 PowerShell 5.1 であると、Windows 1252 エンコード BOM が存在しない場合に既定の下。 相互運用性の理由から、bom が付加された Unicode 形式でスクリプトを保存することをお勧めします。

> [!IMPORTANT]
> PowerShell スクリプトは、エンコード選択肢の影響を受ける可能性がありますまたは別のエンコードするようにスクリプトを再エンコードするタッチがある他のツール。

### <a name="existing-scripts"></a>既存のスクリプト

ファイル システム上のスクリプトは、新しい選択したエンコードを再エンコードする必要があります。 VSCode の下部にあるバーでは、utf-8 のラベルが表示されます。 クリックして、操作バーを開き、選択**エンコードで保存**します。 そのファイルの新しいエンコードを選択することができますようになりました。 参照してください[VSCode のエンコード][]詳しい手順についてはします。

複数のファイルを再エンコードする必要がある場合は、次のスクリプトを使用することができます。

```powershell
Get-ChildItem *.ps1 -Recurse | ForEach-Object {
    $content = Get-Content -Path $_
    Set-Content -Path $_.Fullname -Value $content -Encoding UTF8 -PassThru -Force
}
```

### <a name="the-powershell-integrated-scripting-environment-ise"></a>PowerShell Integrated Scripting Environment (ISE)

PowerShell ISE を使用してスクリプトを編集する場合は、あるエンコード設定を同期する必要があります。

ISE は、BOM を受け入れる必要があるが、またをするためにリフレクションを使用して[エンコードを設定する](https://bensonxion.wordpress.com/2012/04/25/powershell-ise-default-saveas-encoding/)します。
これは新興企業間で保持することに注意してください。

### <a name="source-control-software"></a>ソース管理ソフトウェア

Git など、いくつかのソース管理ツールは、エンコーディングを無視します。git は、バイト数を追跡するだけです。
、TFS、Mercurial、などがあります。 さらにいくつかの git ベースのツールは、テキストをデコードに依存します。

これが、大文字と小文字、ことを確認します。

- VSCode 構成に合わせて、ソース管理にエンコードするテキストを構成します。
- すべてのファイルが関連のエンコードでソース管理にチェックインされることを確認します。
- ソース管理から受信したエンコードへの変更に注意します。 このキーの署名とは、差分変更が、(バイトは文字がない) ために変更されているような場所を示すです。

### <a name="collaborators-environments"></a>コラボレーターの環境

ソース管理を構成するには、上には、PowerShell ファイルを再エンコードすることによって、エンコードをオーバーライドする設定を共有しているファイルをコラボレーターがないことを確認します。

### <a name="other-programs"></a>その他のプログラム

読み取りまたは書き込みの PowerShell スクリプトを他のプログラムは、再エンコード可能性があります。

いくつかの例を次に示します。

- クリップボードを使用すると、スクリプトをコピーして貼り付けます。 これは、ようなシナリオで共通です。
  - VM にスクリプトをコピーします。
  - 電子メールまたは web ページからスクリプトをコピーします。
  - Microsoft Word や PowerPoint のドキュメントの内外にスクリプトをコピーします。
- 他のテキスト エディターなど。
  - メモ帳
  - vim
  - その他の PowerShell スクリプト エディター
- テキストのようなユーティリティを編集:
  - `Get-Content`/`Set-Content`/`Out-File`
  - などの PowerShell リダイレクト演算子`>`と `>>`
  - `sed`/`awk`
- ようなファイルの転送プログラム。
  - スクリプトをダウンロードするときに、web ブラウザー
  - ファイル共有

テキストではなくバイトでこれらのツールのいくつかの処理が、エンコーディングの構成は、他のユーザー。 エンコーディングを構成する必要があるような場合、問題を回避するエンコードのエディターとして同じする必要があります。

## <a name="other-resources-on-encoding-in-powershell"></a>PowerShell でのエンコードでは、その他のリソース

いくつか他の優れた投稿はエンコーディングと PowerShell でのエンコードを構成する読み取りでは、価値のあります。

- [@mklement0][StackOverflow で PowerShell のエンコードの概要](https://stackoverflow.com/questions/40098771/changing-powershells-default-output-encoding-to-utf-8)
- 問題をエンコードするためには、vscode-PowerShell で以前の問題が開かれます。
  - [#1308](https://github.com/PowerShell/vscode-powershell/issues/1308)
  - [#1628](https://github.com/PowerShell/vscode-powershell/issues/1628)
  - [#1680](https://github.com/PowerShell/vscode-powershell/issues/1680)
  - [#1744](https://github.com/PowerShell/vscode-powershell/issues/1744)
  - [#1751](https://github.com/PowerShell/vscode-powershell/issues/1751)
- [クラシック*Joel on Software* Unicode について記述](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)
- [.NET Standard でのエンコード](https://github.com/dotnet/standard/issues/260#issuecomment-289549508)


[@mklement0]: https://github.com/mklement0
[@rkeithhill]: https://github.com/rkeithhill
[Windows-1252]: https://wikipedia.org/wiki/Windows-1252
[ラテン 1]: https://wikipedia.org/wiki/ISO/IEC_8859-1
[UTF-8]: https://wikipedia.org/wiki/UTF-8
[バイト オーダー マーク]: https://wikipedia.org/wiki/Byte_order_mark
[UTF-16]: https://wikipedia.org/wiki/UTF-16
[言語サーバー プロトコル]: https://microsoft.github.io/language-server-protocol/
[VSCode のエンコード]: https://code.visualstudio.com/docs/editor/codebasics#_file-encoding-support
