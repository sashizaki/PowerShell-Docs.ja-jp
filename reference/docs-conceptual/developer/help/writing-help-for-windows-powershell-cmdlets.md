---
title: PowerShell コマンドレットのヘルプを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55908d67-7cbe-482a-a105-5a6da93c5311
caps.latest.revision: 4
ms.openlocfilehash: 8d692cf88d1d356886ef973f0989294d6b51ee6d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361071"
---
# <a name="writing-help-for-powershell-cmdlets"></a>PowerShell コマンドレットのヘルプの作成

PowerShell コマンドレットは役に立ちますが、コマンドレットの動作と使用方法をヘルプトピックで明確に説明していない限り、コマンドレットが使用されないか、またはユーザーに不満が生じる可能性があります。
XML ベースのコマンドレットヘルプファイル形式では一貫性が向上しますが、優れたヘルプではさらに多くのことが必要になります。

コマンドレットのヘルプを記述したことがない場合は、次のガイドラインを確認してください。
コマンドレットのヘルプトピックを作成するために必要な XML スキーマについては、次のセクションで説明します。
まず[、コマンドレットのヘルプファイルを作成](./how-to-create-the-cmdlet-help-file.md)します。
このトピックには、最上位レベルの XML ノードの説明が含まれています。

## <a name="writing-guidelines-for-cmdlet-help"></a>コマンドレットヘルプの記述に関するガイドライン

### <a name="write-well"></a>適切な書き込み
適切に記述されたトピックに代わるものはありません。
プロの執筆者でない場合は、参考になるライターまたはエディターを見つけてください。
別の方法としては、Microsoft Word にヘルプテキストをコピーし、文法とスペルチェックを使用して作業を改善する方法があります。

### <a name="write-simply"></a>書き込みのみ
単純な語句と語句を使用します。
専門用語を避けてください。
多くの読者が、外部言語の辞書とヘルプトピックのみを装備していることを考慮してください。

### <a name="write-consistently"></a>一貫した書き込み
関連するコマンドレットのヘルプが似ている必要があります (例: get-x と set-x)。
標準パラメーターの標準の説明 ( **Force** 、 **InputObject**など) を使用します。
(コアコマンドレットのヘルプからコピーします)。標準の使用条件を使用します。
たとえば、"argument" ではなく "parameter" を使用し、"command" または "command-let" ではなく "コマンドレット" を使用します。

### <a name="start-the-synopsis-with-a-verb"></a>動詞を使用して、概要を開始します。
[概要] フィールドは、コマンドレットがどのように実行されているか、またどのように動作するかをユーザーに通知します。
動詞このコマンドレットが要件を満たしているかどうかをユーザーに通知するタスクベースのステートメントを作成します。
"Get"、"create"、"change" などの単純な動詞を使用します。
"Set" は避けてください。 "modify" のように、あいまいで凝った言葉にすることができます。

### <a name="focus-on-objects"></a>オブジェクトにフォーカスする
ほとんどの "get" コマンドレットは何かを表示しますが、その主な機能はオブジェクトを取得することです。
ヘルプでは、オブジェクトに焦点を当てることによって、既定の表示が多くなることをユーザーが理解できるようにし、さまざまな方法で取得したオブジェクトのメソッドとプロパティを使用できるようにします。

### <a name="write-detailed-descriptions"></a>詳細な説明の書き込み
コマンドレットが実行できるすべての詳細な説明を簡単に示します。
Main 関数が1つのプロパティを変更する場合でも、コマンドレットですべてのプロパティを変更できる場合は、詳細な説明でこれを一覧表示します。

### <a name="use-conventional-syntax"></a>従来の構文を使用する
標準のバッカスナウア記法-Backus-naur 形式を使用します。これは、Windows および UNIX のコマンドラインヘルプでよく使用されます。

### <a name="use-microsoft-net-framework-types-for-parameter-values"></a>パラメーター値に Microsoft .NET Framework 型を使用する
パラメーター値のプレースホルダー (構文とパラメーターの説明) には、パラメーターが受け入れるオブジェクトの .NET Framework 型が表示されます。
PowerShell チームは、.NET Framework についてユーザーに教えるために、この規則を開発しました。

### <a name="write-complete-parameter-descriptions"></a>完全なパラメーターの説明の書き込み
パラメーターの説明は、パラメーターの動作 (その効果) と、パラメーター値に対して入力する必要があることをユーザーに通知する必要があります。

### <a name="write-practical-examples"></a>実用的な例を書く
この例では、すべてのパラメーターを使用する方法を示していますが、最も重要なのは、実際のタスクでコマンドレットを使用する方法を示すことです。
単純な例から始めて、徐々に複雑な例を記述します。
最後の例では、パイプラインでコマンドレットを使用する方法を示します。

### <a name="use-the-notes-field"></a>[メモ] フィールドの使用
[メモ] フィールドは、ユーザーがコマンドレットを理解するために必要な概念を説明するために使用します。
また、ユーザーが一般的なエラーを回避できるように、メモを使用することもできます。
Url の変更は避けてください。
代わりに、検索するユーザーの条件を指定します。

### <a name="test-your-help"></a>ヘルプをテストする
コードをテストするのと同じようにヘルプをテストします。
友人や同僚がヘルプコンテンツを読んで、フィードバックを提供します。
また、ニュースグループからフィードバックを送信することもできます。

## <a name="see-also"></a>参照

 [コマンドレットのヘルプファイルを作成する方法](./how-to-create-the-cmdlet-help-file.md)

 [コマンドレットの名前と概要をコマンドレットのヘルプトピックに追加する方法](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [詳細な説明をコマンドレットヘルプトピックに追加する方法](./how-to-add-a-cmdlet-description.md)

 [コマンドレットヘルプトピックに構文を追加する方法](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [コマンドレットにパラメーターを追加する方法に関するヘルプトピック](./how-to-add-parameter-information.md)

 [コマンドレットのヘルプトピックに入力の種類を追加する方法](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [コマンドレットヘルプトピックに戻り値を追加する方法](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [コマンドレットヘルプトピックにメモを追加する方法](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [コマンドレットのヘルプトピックに例を追加する方法](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [コマンドレットヘルプトピックに関連リンクを追加する方法](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [Windows PowerShell SDK](../windows-powershell-reference.md)