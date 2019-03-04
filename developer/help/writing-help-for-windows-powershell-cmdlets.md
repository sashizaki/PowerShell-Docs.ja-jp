---
title: PowerShell コマンドレットのヘルプの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55908d67-7cbe-482a-a105-5a6da93c5311
caps.latest.revision: 4
ms.openlocfilehash: 8d692cf88d1d356886ef973f0989294d6b51ee6d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857858"
---
# <a name="writing-help-for-powershell-cmdlets"></a>PowerShell コマンドレットについては、書き込み

PowerShell コマンドレットが役に立ちますが、コマンドレットが使われませんか、ユーザーはストレスを感じる可能性があります、さらに悪いことに、ヘルプ トピックは、コマンドレットの機能とその使用方法を明確に説明、しない限り、します。
XML ベースのコマンドレットのヘルプ ファイルの形式の一貫性が向上し、非常に役立ちますがはるかに必要です。

決してコマンドレットのヘルプを記述した場合は、次のガイドラインを確認します。
コマンドレットのヘルプ トピックを作成するために必要な XML スキーマは、次のセクションで説明します。
始まり[コマンドレットのヘルプ ファイルを作成する](./how-to-create-the-cmdlet-help-file.md)します。
そのトピックには、最上位の XML ノードの説明が含まれています。

## <a name="writing-guidelines-for-cmdlet-help"></a>コマンドレットのヘルプのガイドライン

### <a name="write-well"></a>書き込み
何も適切に記述されたトピックが置き換えられません。
プロフェッショナル ライターでない場合は、するためには、ライターまたはエディターを検索します。
別の方法としては、Microsoft Word にヘルプ テキストをコピーし、文法の使用して、作業を向上させるためにスペルを確認します。

### <a name="write-simply"></a>単純に書き込む
単純な単語や語句を使用します。
専門用語を回避します。
外国語ディクショナリと、ヘルプ トピックでのみ、多くの読者が搭載されていることを検討してください。

### <a name="write-consistently"></a>書き込み操作
ヘルプ関連コマンドレットは (例、get x セット x 用) のようになります。
などの標準的なパラメーターは、標準的な説明を使用して**Force**と**InputObject**します。
(コピーしてヘルプからのコア コマンドレット)。標準の条件を使用します。
たとえば、「パラメーター」の使用、いない「引数」と「コマンドレット」を使用しない「コマンド」または「コマンドとします」

### <a name="start-the-synopsis-with-a-verb"></a>動詞を使用して、概要を開始します。
概要フィールドは、どのようなコマンドレットが、いない何がまたはしくみにユーザーを通知します。
動詞は、このコマンドレットは、その要件を満たしている場合は、ユーザーに通知するタスク ベースのステートメントを作成します。
"Get"、「作成」、「変更」などの単純な動詞を使用して、
回避"set"、「変更」のような漠然と手の込んだの単語があることができます。

### <a name="focus-on-objects"></a>オブジェクトに集中します。
ほとんど"get"コマンドレットの表示、何かが、その主な機能は、オブジェクトを取得します。
ヘルプでは、オブジェクト、焦点、既定の表示が、次のいずれかであると、メソッドとそれらのさまざまな方法で取得したオブジェクトのプロパティを使用できるユーザーが理解できるように。

### <a name="write-detailed-descriptions"></a>詳細な説明を記述します。
簡単に詳細な説明で、コマンドレットを実行できるすべての一覧を表示します。
Main 関数は、1 つのプロパティを変更するのには、コマンドレットは、すべてのプロパティを変更できますが場合、は、これを一覧表示について詳しく説明します。

### <a name="use-conventional-syntax"></a>従来の構文を使用します。
これは、Windows と UNIX のコマンドライン ヘルプの一般的な標準のバッカスナウア記法形式を使用します。

### <a name="use-microsoft-net-framework-types-for-parameter-values"></a>Microsoft .NET Framework の型を使用してパラメーター値
(構文とパラメーターの説明) でパラメーター値のプレース ホルダーをパラメーターを受け入れるオブジェクトの .NET Framework の型を表示します。
PowerShell チームは、.NET Framework についてユーザーに教えるためには、この規則を開発しました。

### <a name="write-complete-parameter-descriptions"></a>完全なパラメーターの説明を記述します。
パラメーターの説明を次の 2 つのユーザーに通知する必要があります。 どのようなパラメーターは (効果) と、パラメーター値を入力する必要があります。

### <a name="write-practical-examples"></a>実際の例を書き込む
すべてのパラメーターを使用する方法を例示する必要がありますが、最も重要な点は、実際のタスクでコマンドレットを使用する方法について説明します。
簡単な例を起動し、ますます複雑化のサンプルを記述します。
最後の例では、パイプラインでコマンドレットを使用する方法を説明します。

### <a name="use-the-notes-field"></a>[メモ] フィールドを使用して、
[メモ] フィールドを使用して、ユーザーは、コマンドレットを理解する必要がある概念について説明します。
ユーザーが一般的なエラーを回避するのにノートを使用することもできます。
Url は、変更しないでください。
代わりに、ユーザーの検索条件を提供します。

### <a name="test-your-help"></a>ご協力をテストします。
コードをテストするのと同じように、ヘルプをテストします。
フレンドを指定し、同僚は、ヘルプ コンテンツの読み取りや、フィードバックを提供します。
またニュースグループからのフィードバックを集めることができます。

## <a name="see-also"></a>参照

 [コマンドレットのヘルプ ファイルを作成する方法](./how-to-create-the-cmdlet-help-file.md)

 [概要とコマンドレットの名前をコマンドレットのヘルプ トピックを追加する方法](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [コマンドレットのヘルプ トピックの詳細な説明を追加する方法](./how-to-add-a-cmdlet-description.md)

 [コマンドレットのヘルプ トピックに構文を追加する方法](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [コマンドレットのヘルプ トピックにパラメーターを追加する方法](./how-to-add-parameter-information.md)

 [コマンドレットのヘルプ トピックへの入力型を追加する方法](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [コマンドレットのヘルプ トピックに戻り値を追加する方法](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [コマンドレットのヘルプ トピックにノートを追加する方法](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [コマンドレットのヘルプ トピックの例を追加する方法](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [コマンドレットのヘルプ トピックに関連するリンクを追加する方法](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [Windows PowerShell SDK](../windows-powershell-reference.md)