---
title: 構文のコメント ベースのヘルプ |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8adc997-1a71-48e9-9383-513ef13da7cf
caps.latest.revision: 4
ms.openlocfilehash: 584e5923008e8369a83c699478844f0e0c295adc
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083214"
---
# <a name="syntax-of-comment-based-help"></a>コメント ベースのヘルプの構文

このセクションでは、コメント ベースのヘルプの構文について説明します。

## <a name="syntax-diagram"></a>構文ダイアグラム

 コメント ベースのヘルプの構文は次のとおりです。

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

 コメント ベースのヘルプは、一連のコメントとして書き込まれます。 各の行、コメントの前にコメント記号 (#) を入力するか、使用することができます、"\<#"と"#>"記号がコメント ブロックを作成します。 コメント ブロック内のすべての行はコメントとして解釈されます。

 コメント ベースのヘルプの各セクションではキーワードで定義され、各キーワードの前にドット (.)。 キーワードは、任意の順序で表示できます。 キーワード名は区別されません。

 コメント ブロックは、少なくとも 1 つのヘルプ キーワードを含める必要があります。 何度もは、コメント ブロックは同じで、キーワード、例などのいくつか表示できます。 各キーワードのヘルプ コンテンツのキーワードの後に始まり、行を複数の行にまたがることができます。

 すべてのコメント ベースのヘルプ トピック内の行が連続している必要があります。 コメント ベースのヘルプ トピックには、ヘルプ トピックの一部でないコメントが後ろに、ある場合は、ヘルプではないコメントの最後の行とコメント ベースのヘルプの先頭の間に少なくとも 1 つの空白行が必要があります。

 たとえば、次のコメント ベースのヘルプ トピックが含まれています、します。キーワードの説明とその値は、関数またはスクリプトの説明を示します。

```powershell
<#
    .Description
    The Get-Function function displays the name and syntax of all functions in the session.
#>
```