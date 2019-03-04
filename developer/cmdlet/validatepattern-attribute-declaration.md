---
title: ValidatePattern 属性の宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidatePattern
- ValidatePattern attribute, described
- ValidatePattern attribute
ms.assetid: 87b811be-6d93-4e7d-b9d0-c567a19bb0ef
caps.latest.revision: 13
ms.openlocfilehash: 5edcb65a6fbe1cb2fe2d0efe3f763fb84628b049
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858878"
---
# <a name="validatepattern-attribute-declaration"></a>ValidatePattern 属性の宣言

ValidatePattern 属性には、コマンドレット パラメーターの引数を検証する正規表現パターンを指定します。 この属性は、Windows PowerShell 関数でも使用できます。

ValidatePattern がコマンドレット内で呼び出されると、Windows PowerShell ランタイムはコマンドレット パラメーターの引数を文字列に変換し、し、ValidatePattern 属性によって指定されたパターンには、その文字列を比較します。 コマンドレットは、引数を指定されたパターンの変換後の文字列表現に一致する場合にのみ実行されます。 一致しない場合は、Windows PowerShell ランタイムによってエラーがスローされます。

## <a name="syntax"></a>構文

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a>パラメーター

`RegexString` ([System.String](/dotnet/api/System.String)) が必要です。 パラメーターの引数を検証する正規表現を指定します。

オプション ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) という名前のパラメーター (省略可能)。 ビットごとの組み合わせを指定します[System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)正規表現のオプションを指定するフラグ。

## <a name="remarks"></a>コメント

- この属性は、パラメーターごと 1 回だけ使用できます。

- 使用することができます、`Option`さらに、パターンを定義する属性のパラメーター。 たとえば、行うことができます、パターン大文字小文字を区別します。

- この属性をコレクションに適用すると、コレクション内の各要素がパターンに一致する必要があります。

- ValidatePattern 属性を定義した、 [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)クラス。

## <a name="see-also"></a>参照

[System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
