---
title: PowerShell ドキュメントのスタイル ガイド
description: この記事では、PowerShell ドキュメントを記述するためのスタイル規則について説明します。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 964536c5195c3bb8abd98b5996a96fc7b9362489
ms.sourcegitcommit: c97dcf1e00ef540e7464c36c88f841474060044c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "79402579"
---
# <a name="powershell-docs-style-guide"></a>PowerShell ドキュメントのスタイル ガイド

この記事では、PowerShell ドキュメントのコンテンツに固有のスタイル ガイダンスについて説明します。 これは、[概要](overview.md#get-started-writing-docs)に記載されている情報に基づいています。

## <a name="product-terminology"></a>製品に関する用語

PowerShell にはいくつかのバリエーションがあります。
次の表に、PowerShell を説明するときに使用される用語の一部について、その定義を示します。

- **PowerShell** - これが既定値です。 PowerShell 7 以降のすべての PowerShell の総称として使用されます。

- **PowerShell Core** - .NET Core 上で構築される PowerShell です。 **Core** という用語の使用は、Windows PowerShell と区別する必要がある場合にのみ限定する必要があります。

- **Windows PowerShell** - .NET Framework 上で構築される PowerShell です。 Windows PowerShell は Windows にのみ付属しており、完全な Framework が必要です。

通常、ドキュメント内の "Windows PowerShell" は、"PowerShell" に読み替えることができます。
Windows 固有のテクノロジについて説明されている場合は、"Windows PowerShell" を読み替えるべきでは**ありません**。

## <a name="markdown-specifics"></a>Markdown の詳細

Microsoft のドキュメントを構築する Microsoft Open Publishing System (OPS) では、[markdig][] を使用して Markdown ドキュメントが処理されます。 markdig では、最新の [CommonMark][] 仕様の規則に基づいてドキュメントが解析されます。

新しい CommonMark 仕様では、いくつかの Markdown 要素の構築に関する規定が非常に厳密になっています。 このドキュメントの細部に、細心の注意を払ってください。

### <a name="blank-lines-spaces-and-tabs"></a>空白行、スペース、およびタブ

重複する空白行を削除します。 複数の空白行は HTML では単一の空白行として表示されるため、複数の空白行には目的がありません。

空白行は、Markdown 内のブロックが終わることも示します。 異なる種類の Markdown ブロックの間 (段落とリストの間や段落とヘッダーの間など) には、単一の空白行が必要です。

> [!NOTE]
> Markdown では、スペースが重要です。 常にハード タブではなくスペースを使用してください。 行の末尾の余分なスペースを削除してください。

### <a name="titles-and-headings"></a>タイトルと見出し

[ATX 見出し][atx]のみを使用します (`=` または `-` スタイルのヘッダーではなく # スタイルにします)。

- 文の先頭で大文字を使用する - 固有名詞、タイトル、ヘッダーの 1 文字目のみ大文字にします
- `#` と見出しの最初の文字の間には単一のスペースが必要
- 見出しの上下は単一の空白行にする
- ドキュメントごとの H1 は 1 つのみにする
- ヘッダーのレベルは 1 つずつ増分する。 レベルをスキップしないでください
- ヘッダーに太字またはその他のマークアップを使用しない

### <a name="limit-line-length-to-100-characters"></a>行の長さを 100 文字に制限する

これは、概念記事とコマンドレット リファレンスに適用されます。 About_topics の長さは 80 文字に制限されます。
行の長さを制限することで、git diff と履歴が読みやすくなります。 さらに、他の執筆者が投稿を簡単に行えるようにします。

Visual Studio Code の [Reflow Markdown][reflow] 拡張機能を使用すると、規定の行の長さに合うように段落が簡単にリフロ―されます。

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

### <a name="formatting-command-syntax-elements"></a>コマンド構文要素の書式設定

- コマンドレットとパラメーターには常に完全名を使用します。 別名について具体的に説明する場合を除いて、別名の使用は避けてください。

- 段落内では、言語キーワード、コマンドレット名、変数、およびファイル パスをバックティック (`` ` ``) 文字で囲む必要があります。 プロパティ、パラメーター、およびクラス名は、**太字**にする必要があります。

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

- 外部コマンド (EXE やスクリプトなど) を参照する場合は、コマンド名を太字かつすべて小文字 (文の先頭にある場合は大文字) にし、適切なファイル拡張子を含める必要があります。 次に例を示します。

  ```markdown
  For example, on Windows systems, you can use the `net start` and `net stop` commands
  to start and stop a service. **Sc.exe** is another service control tool for Windows.
  That name does not fit into the naming pattern for the **net.exe** service commands.
  ```

- 外部コマンドの使用例を示す場合は、例をバックティックで囲む必要があります。
  別名と名前が競合する場合は、コマンド例にファイル拡張子を含める必要があります。 次に例を示します。

  ```markdown
  To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
  ```

- (参照コンテンツではなく) 概念記事を記述する場合は、最初に出現するコマンドレットの名前に、コマンドレットのドキュメントにリンクされたハイパーリンクを設定する必要があります。 ハイパーリンクの角かっこ内で、バックティック、太字、またはその他のマークアップを使用しないでください。

  次に例を示します。

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  詳細については、この記事の「[ハイパーリンク](#hyperlinks)」セクションを参照してください。

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

[Microsoft Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack) には、Microsoft のパブリッシング システム固有の機能をサポートするツールが含まれています。 アラートは、docs.microsoft.com に表示されるブロック引用を、その内容の重要性を示す色とアイコンを使用して作成する Markdown 拡張機能です。 次のアラートの種類がサポートされています。

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

> [!NOTE]
> 流し読みする場合でも、ユーザーが注目する必要がある情報です。

> [!TIP]
> ユーザーの成果を向上させるために役立つオプションの情報です。

> [!IMPORTANT]
> ユーザーが目的を達成するために必要な、非常に重要な情報です。

> [!CAUTION]
> アクションの考えられる悪影響です。

> [!WARNING]
> アクションの避けられない危険な影響です。

## <a name="hyperlinks"></a>ハイパーリンク

- URL そのものの使用は避けてください。 リンクには Markdown 構文 `[friendlyname](url-or-path)` を使用する必要があります
- 必要に応じて URL そのものを使用できますが、バックティックで囲む必要があります。 次に例を示します。

  ```markdown
  By default, if you do not specify this parameter, the DMTF standard resource URI
  `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.
  ```

- 可能な場合は、URL リンクを HTTPS にする必要があります。
- リンクにはフレンドリ名が必要です。通常はリンク先のトピックのタイトルを使用します。
- 下部にある「関連リンク」セクションのすべての項目は、ハイパーリンクにする必要があります。
- ハイパーリンクの角かっこ内で、バックティック、太字、またはその他のマークアップを使用しないでください。

### <a name="linking-to-other-content"></a>他のコンテンツへのリンク

パブリッシング システムでサポートされるハイパーリンクには、URL リンクとファイル リンクの 2 種類があります。

URL リンクでは、docs.microsoft.com のルートに対する相対的な URL パスを使用できます。 または、完全な URL 構文を含む絶対 URL を使用することもできます (例: `https:/github.com/MicrosoftDocs/PowerShell-Docs`)。

- PowerShell ドキュメント以外のコンテンツにリンクする場合、または PowerShell ドキュメント内のコマンドレット リファレンスと概念記事の間にリンクを設定する場合は、URL リンクを使用します。
- 相対リンクを設定する最も簡単な方法は、ブラウザーから URL をコピーした後、Markdown に貼り付ける値から `https://docs.microsoft.com/en-us` を削除することです。
   - URL には Microsoft プロパティのロケールを含めないでください (例: URL から "/en-us" を削除します)。
- ターゲット サイトで無効な場合を除き、外部 Web サイトへのすべての URL には HTTPS を使用する必要があります。

ある参照記事から別の参照記事へのリンク、またはある概念記事から別の概念記事へのリンクを設定する場合は、ファイル リンクを使用します。 PowerShell の特定のバージョン用の参照記事にリンクする必要がある場合は、URL リンクを使用する必要があります。

- ファイル リンクには、相対ファイル パスを含めます (例: `../folder/file.md`)
- すべてのファイル パスにスラッシュ (`/`) 文字を使用します

## <a name="formatting-code-samples"></a>サンプル コードの書式設定

Markdown では、次の 2 つの異なるコード スタイルがサポートされています。

- コード スパン (インライン) - 単一のバックティック (`` ` ``) 文字でマークされます。 スタンドアロン ブロックとしてではなく、段落内で使用されます。
- コード ブロック - トリプル バックティック (`` ``` ``) 文字列で囲まれた複数行のまとまりです。 コード ブロックでは、バックティックの後ろに言語ラベルを付けることもできます。 言語ラベルを使用して、構文でコード ブロックの内容を強調できます。

### <a name="using-code-blocks"></a>コード ブロックの使用

Markdown では、コード ブロックであることを示すためにインデントすることができますが、このパターンは問題になる可能性があるため、回避する必要があります。 すべてのコード ブロックは、コード フェンスに含まれている必要があります。 コード フェンスは、トリプルバックティック (`` ``` ``) 文字列で囲まれたコードのまとまりです。 コード フェンス マーカーは、サンプル コードの前と後ろの専用の行に配置する必要があります。 コード ブロックの開始を示すマーカーには、言語ラベルを含めることができます (省略可能)。 Microsoft の Open Publishing System (OPS) では、言語ラベルを使用した構文の強調機能がサポートされています。

OPS では、コード ブロックの内容をクリップボードにコピーする **[コピー]** ボタンも追加されます。 これにより、コード例をテストするためのスクリプトにコードを簡単に貼り付けることができます。 ただし、ドキュメントのすべての例が実行されることを目的としているわけではありません。 一部のコード ブロックは、PowerShell の概念を簡単に説明するものです。

Microsoft のドキュメントでは、次の 2 種類のコード ブロックが使用されています。

1. 説明用の例
2. 実行可能な例

### <a name="syntax-code-blocks"></a>構文のコード ブロック

次の例は、`Get-Command` コマンドレットで使用できるすべてのパラメーターを示しています。

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo]
  [[-ArgumentList] <Object[]>] [-All] [-ListImported] [-ParameterName <String[]>]
  [-ParameterType <PSTypeName[]>] [<CommonParameters>]
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

説明用の例は、PowerShell の概念を説明するために使用されます。 これらは、クリップボードにコピーして実行するためのものではありません。 これらが最も一般的に使用されるのは、簡単に入力できる単純な例としてです。
また、コマンドの構文を示す構文の例としても使用されます。 説明されているコマンドからの出力例がコード ブロックに含まれている場合があります。

PowerShell の比較演算子の簡単な例を次に示します。

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

この例では PowerShell プロンプトが簡略化され、結果の出力が示されていることに注意してください。 この例では、読者がこの例をコピーして実行することは想定されていません。

### <a name="executable-examples"></a>実行可能な例

より複雑な例または、コピーして実行するために役立つ例では、次のブロックスタイルのマークアップを使用する必要があります。

~~~markdown
```powershell
<PowerShell code goes here>
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

別名について具体的に説明する場合を除いて、常にすべてのコマンドレットとパラメーターの完全名を使用する必要があります。 コマンドレットとパラメーターの名前では、コードに定義されている適切なスペルを使用する必要があります。

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
