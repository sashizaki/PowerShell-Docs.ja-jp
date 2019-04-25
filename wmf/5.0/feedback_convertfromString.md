---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: fcf2adf67f36edb534df3e2a849459fb20e1c2de
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085356"
---
# <a name="extract-and-parse-structured-objects-out-of-string"></a>文字列から構造化オブジェクトを抽出して分析する

また、`ConvertFrom-String` コマンドレットの追加機能についても説明します。

- 既定では、エクステント テキスト プロパティを削除します。 これを含めるには、-IncludeExtent パラメーターを指定します。

- MVP やコミュニティのフィードバックから多くの学習アルゴリズムのバグを修正します。

- 新しい -UpdateTemplate パラメーターを使って、学習アルゴリズムの結果をテンプレート ファイル内のコメントに保存します。 これにより、学習プロセス (最も時間のかかる段階) が 1 回限りのコストになります。 エンコードされた学習アルゴリズムを含むテンプレートを使って Convert-String を実行すると、ほぼ瞬時に完了します。

## <a name="extract-and-parse-structured-objects-out-of-string-content"></a>文字列コンテンツから構造化オブジェクトを抽出して分析する

[Microsoft Research](https://www.microsoft.com/en-us/research/?from=http%3A%2F%2Fresearch.microsoft.com%2F) とのコラボレーションにより、新しい `ConvertFrom-String` コマンドレットが追加されました。

このコマンドレットは、基本的な区切り記号による解析と、自動生成したサンプルに基づく解析という 2 つのモードをサポートしています。

区切り記号による解析では、既定で、入力を空白の位置で分割し、生成されるグループにプロパティ名を割り当てます。 区切り記号は、カスタマイズできます。

```powershell
"Hello World" | ConvertFrom-String | Format-Table -Auto
```

```output
P1     P2
--     --
Hello  World
```

このコマンドレットは、[Microsoft Research](https://www.microsoft.com/en-us/research/?from=http%3A%2F%2Fresearch.microsoft.com%2F) による [FlashExtract](https://www.microsoft.com/en-us/research/publication/flashextract-framework-data-extraction-examples/?from=http%3A%2F%2Fresearch.microsoft.com%2Fen-us%2Fum%2Fpeople%2Fsumitg%2Fflashextract.html) の研究成果に基づく、自動生成したサンプルによる解析もサポートしています。

まず手始めに、テキスト ベースのアドレス帳を考えてみましょう。

```
    Ana Trujillo

    Redmond, WA

    Antonio Moreno

    Renton, WA

    Thomas Hardy

    Seattle, WA

    Christina Berglund

    Redmond, WA

    Hanna Moos

    Puyallup, WA
```

テンプレートとして使ういくつかの例をファイルにコピーします。

```
    Ana Trujillo

    Redmond, WA

    Antonio Moreno

    Renton, WA
```

抽出するデータを中かっこで囲み、それに任意の名前を付けます。 **Name** プロパティ (およびそれに関連付けられている他のプロパティ) は複数回出現するので、アスタリスク (\*) を使って、この結果を (1 つのレコードに一連のプロパティを抽出するのではなく) 複数のレコードに抽出することを指定します。

```
    {Name\*:Ana Trujillo}

    {City:Redmond}, {State:WA}

    {Name\*:Antonio Moreno}

    {City:Renton}, {State:WA}
```

この一連の例から、`ConvertFrom-String` で、同様の構造を持つ入力ファイルからオブジェクト ベースの出力を自動的に抽出できるようになりました。

```powershell
Get-Content .\addresses.output.txt | ConvertFrom-String -TemplateFile .\addresses.template.txt | Format-Table -Auto
```

```output
ExtentText                     Name               City     State
----------                     ----               ----     -----
Ana Trujillo...                Ana Trujillo       Redmond  WA
Antonio Moreno...              Antonio Moreno     Renton   WA
Thomas Hardy...                Thomas Hardy       Seattle  WA
Christina Berglund...          Christina Berglund Redmond  WA
Hanna Moos...                  Hanna Moos         Puyallup WA
```

抽出されたテキストに追加のデータ操作を行う目的で、**ExtentText** プロパティに、レコードの抽出元から未加工のテキストがキャプチャされます。 この機能にフィードバックを提供したり、例を書き出すのが難しいコンテンツについて相談したりするには、<psdmfb@microsoft.com> までメールでお知らせください。