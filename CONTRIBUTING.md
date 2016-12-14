# <a name="contributing-to-powershell-documentation"></a>PowerShell ドキュメントへの投稿

PowerShell ドキュメントに興味をお持ちいただきありがとうございます。 ここでは、このサイトのテクニカル ドキュメントに投稿する方法について説明します。

>Git と GitHub を初めて使用する際の全般的な情報については、[GitHub のヘルプ](https://help.github.com/)を参照してください。 

## <a name="sign-a-cla"></a>CLA に署名する

PowerShell リポジトリに投稿する前に、[Microsoft Contribution Licensing Agreement (CLA)](https://cla.microsoft.com/) に署名する必要があります。 これまでに PowerShell リポジトリに投稿したことがある場合、 署名は既に完了しています。

## <a name="providing-feedback-on-powershell-documentation"></a>PowerShell ドキュメントにフィードバックを提供する

エラーの指摘、変更の提案、新しいトピックの依頼を行うには、[PowerShell-Docs リポジトリの問題に関するページ](https://github.com/PowerShell/PowerShell-Docs/issues)で[問題を作成](https://help.github.com/articles/creating-an-issue/)します。

問題は PowerShell ドキュメント チームのメンバーが定期的に確認し、重要度の判定、割り当て、対応を適宜行います。

## <a name="writing-powershell-documentation"></a>PowerShell ドキュメントを執筆する

PowerShell に貢献する最も簡単な方法の 1 つは、ドキュメントを執筆および編集することです。 GitHub でホストされているすべてのドキュメントは、[GitHub Flavored Markdown](https://help.github.com/articles/github-flavored-markdown/) を使用して執筆されています。

## <a name="making-minor-edits-to-existing-topics"></a>既存のトピックに関する軽微な編集

[既存のファイルを編集](https://help.github.com/articles/editing-files-in-another-user-s-repository/)するには、そのページを開き、[Edit] (編集) ボタンをクリックします。 GitHub では、変更を加えたリポジトリの変更者用のフォークが自動的に作成されます。 変更が完了したら、編集を保存し、[PowerShell-Docs リポジトリ](https://github.com/PowerShell/PowerShell-Docs)の*ステージング* ブランチに [pull 要求](https://help.github.com/articles/creating-a-pull-request/)を送信してください。 pull 要求を作成すると、PowerShell ドキュメント チームのメンバーが変更を確認してから、*ステージング* ブランチに結合します。

## <a name="making-major-edits-to-existing-topics"></a>既存のトピックに関する大幅な編集

既存の記事に対する大幅な編集、画像の追加または変更、または新しい記事の投稿には、GitHub フォークを手動で作成してから、ローカル コンピューターにフォークのクローンをダウンロードする必要があります。 フォークは、ユーザーの GitHub アカウントに作成されるメイン リポジトリの GitHub ベースのレプリカです。フォークによって、単独で使用できる作業用コピーが作成されます。 pull 要求は自分のフォークから作成します。 同様に、クローンは、リポジトリのローカルベースのレプリカです。この場合はフォークのクローンになります。 クローンによって、Git リポジトリをオフラインで使用できるようになります。また、より強力なネイティブ ソフトウェアやツールを使用できます。

既存のドキュメントに大幅な編集を加える場合のワークフローを次に示します。

1. [PowerShell-Docs リポジトリ](https://github.com/PowerShell/PowerShell-Docs)の[フォークを作成](https://help.github.com/articles/fork-a-repo/)します。
2. ローカル コンピューターに[フォークのクローンを作成](https://help.github.com/articles/cloning-a-repository/)します。
3. 複製されたリポジトリに新しいローカル ブランチを作成します。
4. マークダウン エディターで、更新するファイルに変更を加えます。 
   一般的に使用されているマークダウン エディターについては、以下を参照してください。
5. フォークに[ローカル ブランチをプッシュします](https://help.github.com/articles/pushing-to-a-remote/)。
6. [PowerShell-Docs](https://github.com/PowerShell/PowerShell-Docs) リポジトリの*ステージング* ブランチに [pull 要求を作成](https://help.github.com/articles/creating-a-pull-request/)します。

## <a name="creating-new-topics"></a>新しいトピックを作成する

新しいドキュメントを投稿する場合は、重複するドキュメントを投稿しないように、まず ["in progress" (進行中) とタグが付けられている問題](https://github.com/PowerShell/PowerShell-Docs/labels/in%20progress)を確認します。
投稿予定の内容で執筆中のユーザーがいないと考えられる場合:

* 新しい問題を開き、(PowerShell 組織のメンバーである場合は) "in progress" (進行中) とラベルを付けます。または、コメントとして "in progress" (進行中) と追加して、執筆中であることを他のユーザーに示します。
* 既存のトピックに大幅な編集を加える場合は、前述のワークフローに従います。
* `TOC.md` トピック (各ドキュメント セットのトップ レベル フォルダーにあります) を編集して、新しいトピックを目次に追加します。 
  目次に新しいトピックを追加する場所を決定し、適切なレベルの見出しを追加し、自分のトピック (`[My topic title](relative path to my topic)`) へのリンクを設定します。

## <a name="markdown-editors"></a>マークダウン エディター

次のようなマークダウン エディターを利用できます。

* [Visual Studio Code](https://code.visualstudio.com)
* [Markdown Pad](http://markdownpad.com/)
* [Atom](https://atom.io/)
* [Sublime Text](http://www.sublimetext.com/)


## <a name="github-flavored-markdown-gfm"></a>GitHub Flavored Markdown (GFM)

このリポジトリのすべての記事は、[GitHub Flavored Markdown (GFM)](https://help.github.com/articles/github-flavored-markdown/) を使用しています。

GFM には、次のような基本的な構文があります。

* **改行と段落:**マークダウンには、HTML の `<br />` または `<p />` 要素がありません。 新しい段落は、2 つのテキスト ブロック間に空行を挿入して指定します。

> **注**: 差分と履歴のコマンドライン出力を簡易化するために、各文末に 1 行を追加してください。
差分と履歴のコマンドライン出力はすべての PowerShell-Docs で採用されていませんが、時間をかけて取り組む予定です。 ご協力いただけると助かります。 

* **斜体:** HTML の `<em>some text</em>` 要素は `*some text*` と記述します。
* **太字:** HTML の `<strong>some text</strong>` 要素は `**some text**` と記述します。
* **見出し:** HTML の見出しは、行頭に `#` を使用して指定します。 
  `#` 文字の番号は、見出しの階層レベルに対応します (`#` = `<h1>`、`###` = ```<h3>``` など)。
* **番号付きリスト:** 番号付き (順序付き) リストを作成するには、行頭に `1. ` を指定します。  
  1 つの list 要素内に複数の要素が必要な場合は、list の形式を次のように指定します。
```        
1.  For the first element (like this one), insert a tab stop after the 1. 

    To include a second element (like this one), insert a line break after the first and align indentations.
```
この出力を取得する場合:

1.  (この例のように) 最初の要素の場合、1 の後にタブ ストップを挿入します。 

    (この例のように) 2 つ目の要素を含めるには、1 つ目の要素の後に改行を挿入し、インデントを合わせます。

* **箇条書きリスト:** 箇条書き (順序なし) リストは、`1. ` を `* `、`- `、または `+ ` と置き換える点を除き、順序付きリストとほぼ同じです。 複数要素のリストは、順序付きリストと同様に機能します。
* **リンク:** ハイパーリンクの構文は `[visible link text](link URL)` です。
* **同じドキュメントセット内の別のトピックへのリンク:** ドキュメントセットは、このリポジトリのトップ レベル フォルダーです ("dsc"、"scripting" など)。
    同じドキュメントセット内のトピックへのハイパーリンクを設定する構文は、`[topic title](relative path to topic)` です。 
    詳細については、「[Relative links in READMEs](https://help.github.com/articles/relative-links-in-readmes/)」(README の相対リンク) を参照してください。 
    別のトップ レベル フォルダーにあるトピックへのリンクを設定するには、前述のように、公開済みページの URL を使用します。
