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
ms.openlocfilehash: 171e3e974619e197a0bcc9dfc759297005e34568
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429841"
---
# <a name="validating-parameter-input"></a>パラメーター入力を検証する

PowerShell では、いくつかの方法でコマンドレットのパラメーターに渡される引数を検証できます。
PowerShell には、長さ、範囲、および引数の文字のパターンを検証できます。
使用可能な引数 (数) の数を検証できます。
これらの検証規則は、コマンドレット クラスのパブリック プロパティのパラメーターの属性で宣言されている検証属性によって定義されます。

パラメーターの引数を検証するには、PowerShell のランタイムは、コマンドレットの実行前に、パラメーターの値を確認するのに検証属性によって提供される情報を使用します。
パラメーターの入力が有効でない場合、ユーザーは、エラー メッセージを受信します。
各検証パラメーターは、PowerShell によって適用される検証規則を定義します。

PowerShell では、次の属性に基づいて規則を適用します。

### <a name="validatecount"></a>ValidateCount

パラメーターを受け入れることができる引数の最小値と最大数を指定します。
詳細については、[ValidateCount 属性宣言](./validatecount-attribute-declaration.md)を参照してください。

### <a name="validatelength"></a>ValidateLength

パラメーターの引数では、最小値と最大文字数を指定します。
詳細については、[ValidateLength 属性宣言](./validatelength-attribute-declaration.md)を参照してください。

### <a name="validatepattern"></a>ValidatePattern

パラメーターの引数を検証する正規表現を指定します。
詳細については、[ValidatePattern 属性宣言](./validatepattern-attribute-declaration.md)を参照してください。

### <a name="validaterange"></a>ValidateRange

パラメーターの引数の最小値と最大値を指定します。
詳細については、[ValidateRange 属性宣言](./validaterange-attribute-declaration.md)を参照してください。

### <a name="validateset"></a>ValidateSet

パラメーターの引数の有効な値を指定します。
詳細については、[ValidateSet 属性宣言](./validateset-attribute-declaration.md)を参照してください。

## <a name="see-also"></a>参照

[パラメーターの入力を検証する方法](./how-to-validate-parameter-input.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
