---
title: コメントベースのヘルプ | の構文Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8adc997-1a71-48e9-9383-513ef13da7cf
caps.latest.revision: 4
ms.openlocfilehash: 584e5923008e8369a83c699478844f0e0c295adc
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367761"
---
# <a name="syntax-of-comment-based-help"></a>コメント ベースのヘルプの構文

ここでは、コメントベースのヘルプの構文について説明します。

## <a name="syntax-diagram"></a>構文ダイアグラム

 コメントベースのヘルプの構文は次のとおりです。

```
# .< help keyword>
# <help content>

-or -

<#
.< help keyword>
< help content>
#>
```

## <a name="syntax-description"></a>構文の説明

 コメントベースのヘルプは、一連のコメントとして書かれています。 コメントの各行の前にコメント記号 (#) を入力するか、"\< #" と "# >" の記号を使用してコメントブロックを作成することができます。 コメントブロック内のすべての行は、コメントとして解釈されます。

 コメントベースのヘルプの各セクションは、キーワードによって定義され、各キーワードの前にドット (.) が付きます。 キーワードは任意の順序で表示できます。 キーワード名の大文字と小文字は区別されません。

 コメントブロックには、少なくとも1つのヘルプキーワードを含める必要があります。 たとえば、いくつかのキーワードは、同じコメントブロック内で何度も出現する可能性があります。 各キーワードのヘルプコンテンツは、キーワードの後の行から開始され、複数の行にまたがることができます。

 コメントベースのヘルプトピック内のすべての行は、連続している必要があります。 コメントベースのヘルプトピックがヘルプトピックに含まれていないコメントの後に続く場合は、ヘルプ以外の最後のコメント行とコメントベースのヘルプの先頭の間に、少なくとも1つの空白行がある必要があります。

 たとえば、次のコメントベースのヘルプトピックにはが含まれています。Description キーワードとその値 (関数またはスクリプトの説明)。

```powershell
<#
    .Description
    The Get-Function function displays the name and syntax of all functions in the session.
#>
```