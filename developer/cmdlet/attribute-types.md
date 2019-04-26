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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068661"
---
# <a name="attribute-types"></a>属性の種類

コマンドレットの属性は、機能のグループ化することができます。
次のセクションでは、使用可能な属性を記述し、ランタイムが、属性が呼び出されたときにを説明します。

## <a name="cmdlet-attributes"></a>コマンドレットの属性

### <a name="cmdlet"></a>コマンドレット

コマンドレットとしては、.NET Framework クラスを識別します。
これは、必要な基本属性です。
詳細については、次を参照してください。[コマンドレット属性宣言](./cmdlet-attribute-declaration.md)します。

## <a name="parameter-attributes"></a>パラメーター属性

### <a name="parameter"></a>パラメーター

コマンドレット パラメーターとしてコマンドレット クラスのパブリック プロパティを識別します。
詳細については、次を参照してください。[パラメーター属性宣言](./parameter-attribute-declaration.md)します。

### <a name="alias"></a>エイリアス

パラメーターの 1 つまたは複数のエイリアスを指定します。
詳細については、次を参照してください。[エイリアス属性宣言](./alias-attribute-declaration.md)します。

## <a name="argument-validation-attributes"></a>引数の検証属性

### <a name="validatecount"></a>ValidateCount

コマンドレット パラメーターに使用できる引数の最小値と最大数を指定します。
詳細については、次を参照してください。 [ValidateCount 属性宣言](./validatecount-attribute-declaration.md)します。

### <a name="validatelength"></a>ValidateLength

コマンドレット パラメーターの引数の文字の最小値と最大数を指定します。
詳細については、次を参照してください。 [ValidateLength 属性宣言](./validatelength-attribute-declaration.md)します。

### <a name="validatepattern"></a>ValidatePattern

コマンドレットのパラメーターの引数と一致する正規表現パターンを指定します。
詳細については、次を参照してください。 [ValidatePattern 属性宣言](./validatepattern-attribute-declaration.md)します。

### <a name="validaterange"></a>ValidateRange

コマンドレット パラメーターの引数の最小値と最大値を指定します。
詳細については、次を参照してください。 [ValidateRange 属性宣言](./validaterange-attribute-declaration.md)します。

### <a name="validateset"></a>ValidateSet

一連のコマンドレット パラメーターの引数の有効な値を指定します。
詳細については、次を参照してください。 [ValidateSet 属性宣言](./validateset-attribute-declaration.md)します。

## <a name="see-also"></a>参照

[Windows PowerShell SDK](../windows-powershell-reference.md)
