---
title: 属性の種類 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b1026ad-f072-4fca-8052-a2d8eb491c2a
caps.latest.revision: 6
ms.openlocfilehash: 52c75b3ca73706da39029d5b3ead52ff7197a5f1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364581"
---
# <a name="attribute-types"></a>属性の種類

コマンドレットの属性は、機能によってグループ化できます。
次のセクションでは、使用可能な属性について説明し、属性が呼び出されたときのランタイムの動作について説明します。

## <a name="cmdlet-attributes"></a>コマンドレットの属性

### <a name="cmdlet"></a>コマンドレット

.NET Framework クラスをコマンドレットとして識別します。
これは必須の基本属性です。
詳細については、「[コマンドレット属性の宣言](./cmdlet-attribute-declaration.md)」を参照してください。

## <a name="parameter-attributes"></a>パラメーター属性

### <a name="parameter"></a>パラメーター

コマンドレットパラメーターとしてコマンドレットクラスのパブリックプロパティを識別します。
詳細については、「[パラメーター属性の宣言](./parameter-attribute-declaration.md)」を参照してください。

### <a name="alias"></a>エイリアス

パラメーターの1つ以上のエイリアスを指定します。
詳細については、「[エイリアス属性の宣言](./alias-attribute-declaration.md)」を参照してください。

## <a name="argument-validation-attributes"></a>引数の検証属性

### <a name="validatecount"></a>ValidateCount

コマンドレットパラメーターに使用できる引数の最小数と最大数を指定します。
詳細については、「 [Validatecount 属性の宣言](./validatecount-attribute-declaration.md)」を参照してください。

### <a name="validatelength"></a>ValidateLength

コマンドレットパラメーター引数の文字数の最小値と最大値を指定します。
詳細については、「 [ValidateLength Attribute 宣言](./validatelength-attribute-declaration.md)」を参照してください。

### <a name="validatepattern"></a>ValidatePattern

コマンドレットパラメーターの引数が一致する必要がある正規表現パターンを指定します。
詳細については、「 [Validatepattern 属性の宣言](./validatepattern-attribute-declaration.md)」を参照してください。

### <a name="validaterange"></a>ValidateRange

コマンドレットパラメーター引数の最小値と最大値を指定します。
詳細については、「 [ValidateRange Attribute 宣言](./validaterange-attribute-declaration.md)」を参照してください。

### <a name="validateset"></a>ValidateSet

コマンドレットパラメーター引数に有効な値のセットを指定します。
詳細については、「 [Validateset 属性の宣言](./validateset-attribute-declaration.md)」を参照してください。

## <a name="see-also"></a>参照

[Windows PowerShell SDK](../windows-powershell-reference.md)
