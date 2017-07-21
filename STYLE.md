# <a name="style-guide-for-powershell-docs"></a><span data-ttu-id="e1245-101">PowerShell ドキュメントのスタイル ガイド</span><span class="sxs-lookup"><span data-stu-id="e1245-101">Style guide for PowerShell-Docs</span></span>


## <a name="titlesheadings"></a><span data-ttu-id="e1245-102">タイトルと見出し</span><span class="sxs-lookup"><span data-stu-id="e1245-102">Titles/Headings</span></span>

* <span data-ttu-id="e1245-103">タイトルと見出し (\# によって先頭に追加されたものすべて) の後は必ず改行します</span><span class="sxs-lookup"><span data-stu-id="e1245-103">Titles/headings (anything preprended by \#) should be followed with a newline</span></span>
* <span data-ttu-id="e1245-104">タイトルの最初の文字やそのタイトル内の固有名詞のみを大文字にしてください。</span><span class="sxs-lookup"><span data-stu-id="e1245-104">Only the first letter of a title and any proper nouns in that title should be capitalized</span></span>
* <span data-ttu-id="e1245-105">1 つのドキュメントで使用する H1 は 1 つだけにしてください</span><span class="sxs-lookup"><span data-stu-id="e1245-105">Only 1 H1 per document</span></span>
* <span data-ttu-id="e1245-106">リファレンス コンテンツを編集するときは、ビルド エラーの原因となるため、H2 を platyPS で規定し、追加または削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="e1245-106">When editing reference content, the H2s are prescribed by platyPS and should not be added or removed as it will cause a build break</span></span>
* <span data-ttu-id="e1245-107">(= または \- スタイルヘッダではなく) \# スタイル ヘッダのみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="e1245-107">Only use \# style headers (as opposed to = or \- style headers)</span></span>

### <a name="correct"></a><span data-ttu-id="e1245-108">正</span><span class="sxs-lookup"><span data-stu-id="e1245-108">Correct</span></span>

```
# Header 1

## Header 2

### Header 3

```

### <a name="incorrect"></a><span data-ttu-id="e1245-109">誤</span><span class="sxs-lookup"><span data-stu-id="e1245-109">Incorrect</span></span>

```
Header 1
========

Header 2
--------

### Header 3
```

## <a name="syntax"></a><span data-ttu-id="e1245-110">構文</span><span class="sxs-lookup"><span data-stu-id="e1245-110">Syntax</span></span>

* <span data-ttu-id="e1245-111">段落でコマンドレットについて説明するときは、\\`を使用してコマンドレットを強調表示します</span><span class="sxs-lookup"><span data-stu-id="e1245-111">When talking about a cmdlet in paragraph, use \\` to highlight cmdlet names</span></span>
  * <span data-ttu-id="e1245-112">正しい例: この `Write-Host` コマンドレットで可能なのは ...</span><span class="sxs-lookup"><span data-stu-id="e1245-112">Correct Example: This `Write-Host` Cmdlet can ...</span></span>
  * <span data-ttu-id="e1245-113">正しくない例: この **Write-host** コマンドレットでは ... が可能で、out-file コマンドレットへのパイプラインを...</span><span class="sxs-lookup"><span data-stu-id="e1245-113">Incorrect Example: This **Write-Host** Cmdlet can ... and pipeline to out-file Cmdlet to ...</span></span>
* <span data-ttu-id="e1245-114">(参照コンテンツではなく) 記事を記述するときは、コマンドレット名の最初のインスタンスはコマンドレットのドキュメントにリンクにする必要があります</span><span class="sxs-lookup"><span data-stu-id="e1245-114">When writing an article (as opposed to reference content), the first instance of a cmdlet name should be a link to the cmdlet documentation</span></span>
* <span data-ttu-id="e1245-115">すべての PowerShell 構文のブロックは &#96;&#96;&#96;powershell を使用する必要があります</span><span class="sxs-lookup"><span data-stu-id="e1245-115">All PowerShell syntax blocks should use &#96;&#96;&#96;powershell</span></span>
* <span data-ttu-id="e1245-116">"`PS C:\>`" で PowerShell のコマンドを始めないでください。</span><span class="sxs-lookup"><span data-stu-id="e1245-116">Do not start PowerShell commands with "`PS C:\>`"</span></span>
  * <span data-ttu-id="e1245-117">正しい例:</span><span class="sxs-lookup"><span data-stu-id="e1245-117">Correct Example:</span></span>
  ```powershell
  Get-Process
  ```
  * <span data-ttu-id="e1245-118">正しくない例:</span><span class="sxs-lookup"><span data-stu-id="e1245-118">Incorrect Example:</span></span>
  ```powershell
  PS C:\> Get-Process
  ```
* <span data-ttu-id="e1245-119">PowerShell コマンドによって生成される出力は、構文の強調表示がされないようにコメントする必要があります</span><span class="sxs-lookup"><span data-stu-id="e1245-119">Output emitted by PowerShell commands should be commented to prevent it from recieving syntax highlighting</span></span>
* <span data-ttu-id="e1245-120">プロパティ名とパラメーター名は**太字**にする必要があります</span><span class="sxs-lookup"><span data-stu-id="e1245-120">Property names and parameter names should be in **bold**</span></span>
* <span data-ttu-id="e1245-121">PowerShell コマンドレットは "[Pascal Cased](https://en.wikipedia.org/wiki/PascalCase)" です。</span><span class="sxs-lookup"><span data-stu-id="e1245-121">PowerShell cmdlets are "[Pascal Cased](https://en.wikipedia.org/wiki/PascalCase)".</span></span> <span data-ttu-id="e1245-122">動詞と名詞はハイフンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="e1245-122">Verbs are seperated from nouns by a hyphen.</span></span>

## <a name="lists"></a><span data-ttu-id="e1245-123">リスト</span><span class="sxs-lookup"><span data-stu-id="e1245-123">Lists</span></span>

* <span data-ttu-id="e1245-124">リストの項目にピリオドをつけないでください。(リストの項目が複数の文を含む場合は除く)</span><span class="sxs-lookup"><span data-stu-id="e1245-124">Do not end list items with a period (unless they contain multiple sentences)</span></span>
* <span data-ttu-id="e1245-125">リストに複数の文が含まれている場合は、主要なアイデアの下にヘッダー 3/4/5 を使うことを (適用できる場合は) 検討してください</span><span class="sxs-lookup"><span data-stu-id="e1245-125">If your list contains multiple sentences, consider using a header 3/4/5 (as applicable) underneath your primary idea</span></span>

## <a name="links"></a><span data-ttu-id="e1245-126">リンク</span><span class="sxs-lookup"><span data-stu-id="e1245-126">Links</span></span>

* <span data-ttu-id="e1245-127">リンクは常にマークダウンの構文 `[friendlyname](url)` を使用してマークします</span><span class="sxs-lookup"><span data-stu-id="e1245-127">Links are always marked up using MarkDown syntax `[friendlyname](url)`</span></span>
* <span data-ttu-id="e1245-128">リンクはわかりやすい名称 (できれば最もふさわしいリンクページのタイトル) にする必要があります</span><span class="sxs-lookup"><span data-stu-id="e1245-128">Links should have a a friendly name when applicable, most likely the title of the linked page</span></span>
  * <span data-ttu-id="e1245-129">**例外**: マイクロソフト以外のサイトのリンクは、URL のみが必要です</span><span class="sxs-lookup"><span data-stu-id="e1245-129">**Exception**: Links going towards non-Microsoft sites should only have a URL</span></span>
* <span data-ttu-id="e1245-130">下部にある「関連リンク」セクションのすべての項目は、ハイパーリンクにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1245-130">All items in the "related links" section at the bottom should be hyperlinked.</span></span> 

## <a name="line-breaks"></a><span data-ttu-id="e1245-131">改行</span><span class="sxs-lookup"><span data-stu-id="e1245-131">Line breaks</span></span>

* <span data-ttu-id="e1245-132">セマンティックの改行を含める必要があります</span><span class="sxs-lookup"><span data-stu-id="e1245-132">You must include semantic line breaks</span></span>
* <span data-ttu-id="e1245-133">各行を 100 文字に制限する必要があります (項目を開く: これを検証するためのツール)</span><span class="sxs-lookup"><span data-stu-id="e1245-133">You should limit lines to 100char (Open item: tooling to help us validate this)</span></span>
* <span data-ttu-id="e1245-134">ps3 ではなく PS4 + の追加の改行を削除できます (検証が必要)</span><span class="sxs-lookup"><span data-stu-id="e1245-134">You CAN remove additional line breaks for PS4+, NOT ps3 (needs validation)</span></span>
