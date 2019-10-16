---
title: ValidatePattern 属性宣言 |Microsoft Docs
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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369161"
---
# <a name="validatepattern-attribute-declaration"></a>ValidatePattern 属性の宣言

ValidatePattern 属性は、コマンドレットパラメーターの引数を検証する正規表現パターンを指定します。 この属性は、Windows PowerShell の関数でも使用できます。

ValidatePattern がコマンドレット内で呼び出されると、Windows PowerShell ランタイムはコマンドレットパラメーターの引数を文字列に変換し、その文字列を ValidatePattern 属性によって指定されたパターンと比較します。 コマンドレットは、変換された引数の文字列形式と、指定されたパターンが一致する場合にのみ実行されます。 一致しない場合は、Windows PowerShell ランタイムによってエラーがスローされます。

## <a name="syntax"></a>構文

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a>パラメーター

`RegexString` ([system.string](/dotnet/api/System.String)) が必要です。 パラメーター引数を検証する正規表現を指定します。

オプション ([system.text.regularexpressions.regexoptions. Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) 省略可能な名前付きパラメーター。 正規表現オプションを指定する[system.text.regularexpressions.regexoptions の Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)フラグのビットごとの組み合わせを指定します。

## <a name="remarks"></a>コメント

- この属性は、パラメーターごとに1回だけ使用できます。

- 属性の `Option` パラメーターを使用して、パターンをさらに定義できます。 たとえば、パターンの大文字と小文字を区別することができます。

- この属性をコレクションに適用する場合は、コレクション内の各要素がパターンと一致する必要があります。

- ValidatePattern 属性は、system.servicemodel[属性](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)クラスによって定義されます。

## <a name="see-also"></a>参照

[システムの管理. Validatepattern 属性](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
