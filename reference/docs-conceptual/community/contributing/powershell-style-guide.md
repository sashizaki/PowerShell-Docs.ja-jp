---
title: PowerShell ドキュメントのスタイル ガイド
description: この記事では、PowerShell ドキュメントを記述するためのスタイル規則について説明します。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 32df641f7cafa2a5bfcf1bcbf94be594aa77c7d0
ms.sourcegitcommit: 105c69ecedfe5180d8c12e8015d667c5f1a71579
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85837445"
---
# <a name="powershell-docs-style-guide"></a>PowerShell ドキュメントのスタイル ガイド

この記事では、PowerShell ドキュメントのコンテンツに固有のスタイル ガイダンスについて説明します。 これは、[概要](overview.md#get-started-writing-docs)に記載されている情報に基づいています。

## <a name="product-terminology"></a>製品に関する用語

PowerShell にはいくつかのバリエーションがあります。

- **PowerShell** - これが既定値です。 PowerShell 7 以降のすべての PowerShell の総称として使用されます。
- **PowerShell Core** - .NET Core 上で構築される PowerShell です。 **Core** という用語の使用は、Windows PowerShell と区別する必要がある場合にのみ限定する必要があります。
- **Windows PowerShell** - .NET Framework 上で構築される PowerShell です。 Windows PowerShell は Windows にのみ付属しており、完全な Framework が必要です。

  通常、ドキュメント内の "Windows PowerShell" は、"PowerShell" に読み替えることができます。
  "Windows PowerShell" 固有の動作について説明する場合は、"Windows PowerShell" を使用する必要があります。

関連製品

- **Visual Studio Code (VS Code)** - これは Microsoft の無料のオープン ソース エディターです。 最初のメンションでは、完全な名前を使用する必要があります。 その後で、**VS Code** を使用できます。 "VSCode" は使用しないでください。
- **Visual Studio Code 用の PowerShell 拡張機能** - この拡張機能によって VS Code が PowerShell 用の推奨 IDE に切り替えられます。 最初のメンションでは、完全な名前を使用する必要があります。 その後で、**PowerShell 拡張機能**を使用できます。
- **Azure PowerShell** - これは、Azure サービスを管理するために使用される PowerShell モジュールのコレクションです。
- **Azure Stack PowerShell** - これは、Microsoft のハイブリッド クラウド ソリューションを管理するために使用される PowerShell モジュールのコレクションです。

## <a name="markdown-specifics"></a>Markdown の詳細

Microsoft のドキュメントを構築する Microsoft Open Publishing System (OPS) では、[markdig][] を使用して Markdown ドキュメントが処理されます。 markdig では、最新の [CommonMark][] 仕様の規則に基づいてドキュメントが解析されます。

新しい CommonMark 仕様では、いくつかの Markdown 要素の構築に関する規定が非常に厳密になっています。 このドキュメントの細部に、細心の注意を払ってください。

### <a name="blank-lines-spaces-and-tabs"></a>空白行、スペース、およびタブ

空白行は、Markdown 内のブロックが終わることも示します。 異なる種類の Markdown ブロックの間 (段落とリストの間や段落とヘッダーの間など) には、単一の空白行が必要です。

重複する空白行を削除します。 複数の空白行は HTML では単一の空白行として表示されるため、複数の空白行には目的がありません。 コード ブロック内に複数の空白行があると、コード ブロックが分割されてしまいます。

行の末尾の余分なスペースを削除してください。

> [!NOTE]
> Markdown では、スペースが重要です。 常にハード タブではなくスペースを使用してください。 Markdown のレンダリング方法は、末尾のスペースによって変更できます。

### <a name="titles-and-headings"></a>タイトルと見出し

[ATX 見出し][atx]のみを使用します (`=` または `-` スタイルのヘッダーではなく # スタイルにします)。

- 文の先頭で大文字を使用する - 固有名詞、タイトル、ヘッダーの 1 文字目のみ大文字にします
- `#` と見出しの最初の文字の間には単一のスペースが必要
- 見出しの上下は単一の空白行にする
- ドキュメントごとの H1 は 1 つのみにする
- ヘッダーのレベルは 1 つずつ増分する。 レベルをスキップしないでください
- ヘッダーに太字またはその他のマークアップを使用しない

### <a name="limit-line-length-to-100-characters"></a>行の長さを 100 文字に制限する

これは、概念記事とコマンドレット リファレンスに適用されます。 行の長さを制限することで、git diff と履歴が読みやすくなります。 さらに、他の執筆者が投稿を簡単に行えるようにします。

Visual Studio Code の [Reflow Markdown][reflow] 拡張機能を使用すると、規定の行の長さに合うように段落が簡単にリフロ―されます。

About_topics の長さは 80 文字に制限されます。 詳細については、「[参照記事の編集](./editing-cmdlet-ref.md#formatting-about_-files)」を参照してください。

### <a name="lists"></a>リスト

リストに複数の文または段落が含まれている場合は、リストではなくサブレベルのヘッダーを使用することを検討してください。

リストの上下は単一の空白行にします。

#### <a name="unordered-lists"></a>箇条書きリスト

リスト項目に複数の文が含まれていない限り、リスト項目にはピリオドをつけないでください。 リスト項目の箇条書き記号には、ハイフン文字 (`-`) を使用します。 これにより、アスタリスク [`*`] を使用する、太字または斜体のマークアップとの混同を回避できます。 段落またはその他の要素を箇条書き項目の下に含めるには、改行を挿入し、インデントを箇条書き記号の後ろの最初の文字に揃えます。

次に例を示します。

```markdown
This is a list that contain sub-elements under a bullet item.

- First bullet item

  Sentence explaining the first bullet.

  - Sub-bullet item

    Sentence explaining the sub-bullet.

- Second bullet item
- Third bullet item
```

これは、箇条書き項目の下にサブ要素が含まれているリストです。

- 最初の箇条書き項目

  最初の箇条書きの内容文。

  - サブ箇条書き項目

    サブ箇条書きの内容文。

- 2 番目の箇条書き項目
- 3 番目の箇条書き項目

#### <a name="ordered-lists"></a>番号付きリスト

段落またはその他の要素を番号付き項目の下に含めるには、インデントを項目番号の後ろの最初の文字に揃えます。 番号付きリストのすべての項目では、項目ごとに増分される番号ではなく、番号 `1.` を使用する必要があります。 この値は、Markdown によって自動的に増分されて表示されます。 これにより、項目を簡単に並べ替えることができ、下位コンテンツのインデントが統一されます。

次に例を示します。

```markdown
1. For the first element, insert a single space after the 1. Long sentences should be
   wrapped to the next line and must line up with the first character after the numbered
   list marker.

   To include a second element (like this one), insert a line break after the first
   and align indentations. The indentation of the second element must line up with
   the first character after the numbered list marker. For single digit items, like
   this one, you indent to column 4. For double digits items, for example item number
   10, you indent to column 5.

1. The next numbered item starts here.
```

結果の Markdown は次のように表示されます。

1. 最初の要素では、1. の後ろに単一のスペースを挿入します。 長い文は次の行に折り返す必要があり、次の行の先頭は番号付きリスト マーカーの後ろの最初の文字と揃える必要があります。

   (この例のように) 2 つ目の要素を含めるには、1 つ目の要素の後に改行を挿入し、インデントを合わせます。 2 つ目の要素のインデントは、番号付きリスト マーカーの後ろの最初の文字と揃える必要があります。 このような 1 桁の番号の項目では、列 4 にインデントします。 2 桁の番号の項目 (項目番号 10 など) では、列 5 にインデントします。

1. 次の番号付き項目は、ここから始まります。

### <a name="images"></a>イメージ

画像を含める構文は次のとおりです。

```markdown
![[alt text]](<folderPath>)

Example:
![Introduction](./media/overview/Introduction.png)
```

`alt text` は画像の簡単な説明であり、`<folder path>` は画像の相対パスです。 代替テキストは、視覚障碍がある読者のために必要です。 サイトのバグで画像を表示できない場合にも役立ちます。

画像は、記事が含まれているフォルダー内の `media/<article-name>` フォルダーに格納されている必要があります。
複数の記事で画像を共有することはできません。 `media` フォルダーの下に、記事のファイル名と一致するフォルダーを作成します。 記事のための画像を、その新しいフォルダーにコピーします。 画像が複数の記事で使用される場合は、各画像フォルダーにその画像ファイルのコピーが含まれている必要があります。 ある記事内の画像の変更が他の記事に影響するのを防ぐことができます。

次の種類の画像ファイルがサポートされています。`*.png`、`*.gif`、`*.jpeg`、`*.jpg`、`*.svg`

### <a name="markdown-extensions-supported-by-open-publishing"></a>Open Publishing でサポートされる Markdown 拡張機能

[Microsoft Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack) には、Microsoft のパブリッシング システム固有の機能をサポートするツールが含まれています。 アラートは、docs.microsoft.com に表示されるブロック引用を、その内容の重要性を強調表示する色とアイコンを使用して作成する Markdown 拡張機能です。 次のアラートの種類がサポートされています。

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

これらのアラートは、docs.microsoft.com に次のように表示されます。

注意ブロック

> [!NOTE]
> 流し読みする場合でも、ユーザーが注目する必要がある情報です。

ヒント ブロック

> [!TIP]
> ユーザーの成果を向上させるために役立つオプションの情報です。

重要ブロック

> [!IMPORTANT]
> ユーザーが目的を達成するために必要な、非常に重要な情報です。

注意事項ブロック

> [!CAUTION]
> アクションの考えられる悪影響です。

警告ブロック

> [!WARNING]
> アクションの避けられない危険な影響です。

### <a name="hyperlinks"></a>ハイパーリンク

- ハイパーリンクには Markdown 構文を使用する必要があります `[friendlyname](url-or-path)`
- 可能な場合は、リンクを HTTPS にする必要があります。
- リンクにはフレンドリ名が必要です。通常はリンク先のトピックのタイトルを使用します。
- 下部にある「関連リンク」セクションのすべての項目は、ハイパーリンクにする必要があります
- ハイパーリンクの角かっこ内で、バックティック、太字、またはその他のマークアップを使用しないでください。
- 特定の URI について述べている場合は、URL そのものを使用できます。 その URI はバックティックで囲む必要があります。 次に例を示します。

  ```markdown
  By default, if you do not specify this parameter, the DMTF standard resource URI
  `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.
  ```

#### <a name="linking-to-other-content"></a>他のコンテンツへのリンク

パブリッシング システムでサポートされるハイパーリンクには、

**URL リンク**では、docs.microsoft.com のルートに対する相対的な URL パスを使用できます。 または、完全な URL 構文を含む絶対 URL を使用することもできます 例: `https:/github.com/MicrosoftDocs/PowerShell-Docs`

- PowerShell ドキュメント以外のコンテンツにリンクする場合、または PowerShell ドキュメント内のコマンドレット リファレンスと概念記事の間にリンクを設定する場合は、URL リンクを使用します。相対リンクを作成する最も簡単な方法は、ブラウザーから URL をコピーした後、Markdown に貼り付ける値から `https://docs.microsoft.com/en-us` を削除することです。
- URL には Microsoft プロパティのロケールを含めないでください (例: URL から `/en-us` を削除する)。
- 記事の特定のバージョンにリンクする必要がない限り、URL から不要なクエリ パラメーターは削除します。 例 :
  - `?view=powershell-5.1` - PowerShell の特定のバージョンにリンクするために使用されます。
  - `?redirectedfrom=MSDN` - これは、古い記事からその新しい場所にリダイレクトされると、URL に追加されます。
- ターゲット サイトで無効な場合を除き、外部 Web サイトへのすべての URL には HTTPS を使用する必要があります。

ある参照記事から別の参照記事へのリンク、またはある概念記事から別の概念記事へのリンクを設定する場合は、**ファイル リンク**を使用します。 PowerShell の特定のバージョン用の参照記事にリンクする必要がある場合は、URL リンクを使用する必要があります。

- ファイル リンクには、相対ファイル パスを含めます (例: `../folder/file.md`)
- すべてのファイル パスにスラッシュ (`/`) 文字を使用します

ディープ リンクは、URL リンクとファイルリンクの両方で使用できます。 ターゲット パスの末尾にアンカーを追加します。
次に例を示します。

- `[about_Splatting](about_Splatting.md#splatting-with-arrays)`
- `[custom key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)`

詳細については、「[ドキュメントでリンクを使用する](/contribute/how-to-write-links)」を参照してください。

## <a name="formatting-command-syntax-elements"></a>コマンド構文要素の書式設定

- コマンドレットとパラメーターには常に完全名を使用します。 別名について具体的に説明する場合を除いて、別名の使用は避けてください。

- プロパティ、パラメーター、オブジェクト、型名、クラス名、クラス メソッドは**太字**にする必要があります。
  - プロパティとパラメーターの値は、バックティック (`` ` ``) でラップする必要があります。
  - かっこで囲まれたスタイルを使用して型を参照する場合は、バックティックを使用します。 例: `[System.Io.FileInfo]`

- 言語キーワード、コマンドレット名、関数、変数、ネイティブ EXE、ファイル パス、インライン構文の例は、バックティック (`` ` ``) 文字でラップする必要があります。

  次に例を示します。

  ~~~markdown
  The following code uses `Get-ChildItem` to list the contents of `C:\Windows` and assigns
  the output to the `$files` variable.

  ```powershell
  $files = Get-ChildItem C:\Windows
  ```
  ~~~

  - パラメーターを名前で参照する場合は、名前を**太字**にする必要があります。 ハイフン プレフィックス付きのパラメーターの使用を示す場合は、パラメーターをバックティックで囲む必要があります。 次に例を示します。

    ```markdown
    The parameter's name is **Name**, but it is typed as `-Name` when used on the command
    line as a parameter.
    ```

  - 外部コマンドの使用例を示す場合は、例をバックティックで囲む必要があります。
    ネイティブ コマンドには、常にファイル拡張子を含めます。 次に例を示します。

    ```markdown
    To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
    ```

    ファイル拡張子を含めると、PowerShell のコマンドの優先順位に従って適切なコマンドが確実に実行されます。

- (参照コンテンツではなく) 概念記事を記述する場合は、最初に出現するコマンドレットの名前に、コマンドレットのドキュメントにリンクされたハイパーリンクを設定する必要があります。 ハイパーリンクの角かっこ内で、バックティック、太字、またはその他のマークアップを使用しないでください。

  次に例を示します。

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  詳細については、この記事の「[ハイパーリンク](#hyperlinks)」セクションを参照してください。

## <a name="markdown-for-code-samples"></a>コード サンプルの Markdown

Markdown では、次の 2 つの異なるコード スタイルがサポートされています。

- **コード スパン (インライン)** - 単一のバックティック (`` ` ``) 文字でマークされます。 スタンドアロン ブロックとしてではなく、段落内で使用されます。
- **コード ブロック** - トリプル バックティック (`` ``` ``) 文字列で囲まれた複数行のまとまりです。 コード ブロックでは、バックティックの後ろに言語ラベルを付けることもできます。 言語ラベルを使用して、構文でコード ブロックの内容を強調できます。

すべてのコード ブロックは、コード フェンスに含まれている必要があります。 コード ブロックにはインデントを使用しないでください。 Markdown ではこのパターンを使用できますが、問題になる可能性があるため、回避する必要があります。

コード ブロックは、3 つのバックティック (`` ``` ``) コード フェンスで囲まれた 1 行または複数行のコードです。
コード フェンス マーカーは、サンプル コードの前と後ろの専用の行に配置する必要があります。 コード ブロックの開始を示すマーカーには、言語ラベルを含めることができます (省略可能)。 Microsoft の Open Publishing System (OPS) では、言語ラベルを使用した構文の強調機能がサポートされています。

サポートされている言語タグの完全な一覧については、一元化された共同作成者ガイドの「[フェンスされたコード ブロック](/contribute/code-in-docs#fenced-code-blocks)」を参照してください。

OPS では、コード ブロックの内容をクリップボードにコピーする **[コピー]** ボタンも追加されます。 これにより、コード サンプルをテストするためのスクリプトにコードを簡単に貼り付けることができます。 ただし、ドキュメントのすべての例がそのとおりに実行されることを目的としているわけではありません。 一部のコード ブロックは、PowerShell の概念を簡単に説明するものです。

Microsoft のドキュメントでは、次の 3 種類のコード ブロックが使用されています。

1. 構文ブロック
1. 説明用の例
1. 実行可能な例

### <a name="syntax-code-blocks"></a>構文のコード ブロック

構文のコード ブロックは、コマンドの構文構造を記述するために使用されます。 コード フェンスに対して言語タグを使用しないでください。 次の例は、`Get-Command` コマンドレットで使用できるすべてのパラメーターを示しています。

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax]
  [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
  [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```
~~~

次の例は、`for` ステートメントについて、一般的な用語で説明しています。

~~~markdown
```
for (<init>; <condition>; <repeat>)
{<statement list>}
```
~~~

### <a name="illustrative-examples"></a>説明用の例

説明用の例は、PowerShell の概念を説明するために使用されます。 これらは、クリップボードにコピーして実行するためのものではありません。 これらは、入力が簡単で理解しやすいシンプルな例として最も一般的に使用されています。 コード ブロックには、PowerShell プロンプトと出力例を含めることができます。

PowerShell の比較演算子のシンプルな例を次に示します。 この例では、読者がこの例をコピーして実行することは想定されていません。

~~~markdown
```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS>  1,2,3 -eq 2
2

PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```
~~~

### <a name="executable-examples"></a>実行可能な例

複雑な例または、コピーして実行することを目的とした例では、次のブロックスタイルのマークアップを使用する必要があります。

~~~markdown
```powershell
<Your PowerShell code goes here>
```
~~~

構文の強調を防ぐために、PowerShell コマンドによって表示される出力を **Output** コード ブロックに含める必要があります。 次に例を示します。

~~~markdown
```powershell
Get-Command -Module Microsoft.PowerShell.Security
```

```Output
CommandType  Name                        Version    Source
-----------  ----                        -------    ------
Cmdlet       ConvertFrom-SecureString    3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       ConvertTo-SecureString      3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-CmsMessage              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Credential              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-PfxCertificate          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       New-FileCatalog             3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Protect-CmsMessage          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Test-FileCatalog            3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Unprotect-CmsMessage        3.0.0.0    Microsoft.PowerShell.Security
```
~~~

**Output** コード ラベルは、構文強調システムでサポートされている公式の "言語" ではありません。
ただし、このラベルが有用なのは、これを使用すると、OPS によって、Web ページ上のコード ボックス フレームに "Output" ラベルが追加されるためです。 "Output" コード ボックスでは、構文の強調は行われません。

## <a name="coding-style-rules"></a>コーディング スタイルの規則

### <a name="avoid-line-continuation-in-code-samples"></a>サンプル コードでは行を連結しないようにする

PowerShell のコード例では、行連結文字 (`` ` ``) の使用は避けてください。 これらは見えにくく、行末に余分なスペースがあると問題が発生する可能性があります。

- PowerShell のスプラッティングを使用して、多数のパラメーターを使用するコマンドレットの行の長さを短くします。
- パイプ (`|`) 文字、左中かっこ、左丸かっこ、左角かっこなどの PowerShell 本来の改行を活用します。

### <a name="avoid-using-powershell-prompts-in-examples"></a>例の中で PowerShell プロンプトを使用しないようにする

プロンプト文字列の使用は推奨されていません。コマンド ラインの使い方を示すシナリオに限定して使用する必要があります。 これらの例の大半では、プロンプト文字列を `PS>` にする必要があります。 このプロンプトは OS 固有のインジケーターに依存しません。

プロンプトが必要なのは、プロンプトを変更するコマンドを例をあげて説明する場合、または説明しているシナリオでパスの表示に意味がある場合です。 次の例では、レジストリ プロバイダーの使用時にプロンプトがどのように変化するかを示しています。

```powershell
PS C:\> cd HKCU:\System\
PS HKCU:\System\> dir

    Hive: HKEY_CURRENT_USER\System

Name                   Property
----                   --------
CurrentControlSet
GameConfigStore        GameDVR_Enabled                       : 1
                       GameDVR_FSEBehaviorMode               : 2
                       Win32_AutoGameModeDefaultProfile      : {2, 0, 1, 0...}
                       Win32_GameModeRelatedProcesses        : {1, 0, 1, 0...}
                       GameDVR_HonorUserFSEBehaviorMode      : 0
                       GameDVR_DXGIHonorFSEWindowsCompatible : 0
```

### <a name="do-not-use-aliases-in-examples"></a>例の中で別名を使用しない

別名について具体的に説明する場合を除いて、常にすべてのコマンドレットとパラメーターの完全名を使用する必要があります。 コマンドレットとパラメーターの名前では、パスカル ケースの適切な名前を使用する必要があります。

### <a name="using-parameters-in-examples"></a>例でのパラメーターの使用

位置パラメーターの使用は避けてください。 通常は、パラメーターが位置パラメーターの場合でも、例では常にパラメーターの名前を含めるようにしてください。 これにより、例の中で混同が発生する機会が減少します。

## <a name="next-steps"></a>次のステップ

[コマンドレット編集リファレンス](editing-cmdlet-ref.md)

<!-- External URLs -->
[platyPS]: https://github.com/PowerShell/platyPS
[markdig]: https://github.com/lunet-io/markdig
[CommonMark]: https://spec.commonmark.org/
[atx]: https://github.github.com/gfm/#atx-headings
[pascal-case]: https://en.wikipedia.org/wiki/PascalCase
[reflow]: https://marketplace.visualstudio.com/items?itemName=marvhen.reflow-markdown
