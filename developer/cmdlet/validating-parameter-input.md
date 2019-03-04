---
title: パラメーターの入力の検証 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parameters, validation rules
- validation, examples
- validation
ms.assetid: 3f15bf20-a068-4a7d-a170-bc43f755d1fe
caps.latest.revision: 14
ms.openlocfilehash: f7e5d4fb2f89bd6bc7036fdcff8f38e017d5d0e4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858848"
---
# <a name="validating-parameter-input"></a>パラメーター入力を検証する

Windows PowerShell には、いくつかの方法でコマンドレットのパラメーターに渡される引数を検証できます。 Windows PowerShell には、長さ、範囲、および引数の文字のパターンを検証できます。 使用可能な引数 (数) の数を検証できます。 これらの検証規則は、コマンドレット クラスのパブリック プロパティのパラメーターの属性で宣言されている検証属性によって定義されます。

パラメーターの引数を検証するには、Windows PowerShell ランタイムは、コマンドレットの実行前に、パラメーターの値を確認するのに検証属性によって提供される情報を使用します。 パラメーターの入力が有効でない場合、ユーザーは、エラー メッセージを受信します。 各検証パラメーターは、Windows PowerShell によって適用される検証規則を定義します。

Windows PowerShell では、次の属性に基づいて規則を適用します。

ValidateCount では、パラメーターを受け入れることができる引数の最小値と最大数を指定します。 この属性を宣言するために使用する構文の詳細については、次を参照してください。 [ValidateCount 属性宣言](./validatecount-attribute-declaration.md)します。

ValidateLength では、パラメーターの引数の最小値と最大文字数を指定します。 この属性を宣言するために使用する構文の詳細については、次を参照してください。 [ValidateLength 属性宣言](./validatelength-attribute-declaration.md)します。

ValidatePattern は、パラメーターの引数を検証する正規表現を指定します。 この属性を宣言するために使用する構文の詳細については、次を参照してください。 [ValidatePattern 属性宣言](./validatepattern-attribute-declaration.md)します。

ValidateRange では、パラメーターの引数の最小値と最大値を指定します。 この属性を宣言するために使用する構文の詳細については、次を参照してください。 [ValidateRange 属性宣言](./validaterange-attribute-declaration.md)します。

ValidateSet は、パラメーターの引数の有効な値を指定します。 この属性を宣言するために使用する構文の詳細については、次を参照してください。 [ValidateSet 属性宣言](./validateset-attribute-declaration.md)します。

## <a name="see-also"></a>参照

[パラメーターの入力を検証する方法](./how-to-validate-parameter-input.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
