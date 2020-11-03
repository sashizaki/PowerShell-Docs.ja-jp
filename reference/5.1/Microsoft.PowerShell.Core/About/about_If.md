---
description: 1つまたは複数の条件付きテストの結果に基づいてステートメントリストを実行するために使用できる言語コマンドについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_If
ms.openlocfilehash: 8b1be96167dab47e7e15e3e5b89c46126f117541
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223448"
---
# <a name="about-if"></a>について

## <a name="short-description"></a>概要
1つまたは複数の条件付きテストの結果に基づいてステートメントリストを実行するために使用できる言語コマンドについて説明します。

## <a name="long-description"></a>詳細説明
`If`指定した条件テストが true と評価された場合に、ステートメントを使用してコードブロックを実行できます。 前のテストがすべて false と評価された場合に実行する1つ以上の条件付きテストを指定することもできます。 最後に、他の条件付きテストが true と評価されなかった場合に実行される追加のコードブロックを指定できます。

### <a name="syntax"></a>構文

次の例は、ステートメントの構文を示してい `If` ます。

```powershell
if (<test1>)
    {<statement list 1>}
[elseif (<test2>)
    {<statement list 2>}]
[else
    {<statement list 3>}]
```

ステートメントを実行すると `If` 、PowerShell によっ `<test1>` て条件式が true または false として評価されます。 `<test1>`が true の場合、が実行され、 `<statement list 1>` PowerShell によってステートメントが終了し `If` ます。 `<test1>`が false の場合、PowerShell は条件付きステートメントによって指定された条件を評価し `<test2>` ます。

`<test2>`が true の場合、が実行され、 `<statement list 2>` PowerShell によってステートメントが終了し `If` ます。 との両方が false と評価された場合 `<test1>` `<test2>` 、 `<statement list 3`> コードブロックが実行され、PowerShell は If ステートメントを終了します。

複数の Elseif ステートメントを使用して、一連の条件付きテストをチェーンすることができます。 そのため、各テストは、前のすべてのテストが false の場合にのみ実行されます。
多くの Elseif ステートメントを含むステートメントを作成する必要がある場合は `If` 、代わりに Switch ステートメントを使用することを検討してください。

例 :

最も単純 `If` なステートメントには1つのコマンドが含まれており、Elseif ステートメントや Else ステートメントは含まれていません。 次の例は、ステートメントの最も単純な形式を示してい `If` ます。

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
```

この例では、$a 変数が2より大きい場合、条件は true に評価され、ステートメントリストが実行されます。 ただし、$a が2以下であるか、または既存の変数ではない場合、 `If` ステートメントはメッセージを表示しません。

Else ステートメントを追加すると、$a が2以下の場合にメッセージが表示されます。 次の例に示すように、次のようになります。

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
else {
    Write-Host ("The value $a is less than or equal to 2," +
        " is not created or is not initialized.")
}
```

この例をさらに絞り込むために、$a の値が2に等しい場合に、Elseif ステートメントを使用してメッセージを表示することができます。 次の例に示すように、次のようになります。

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
elseif ($a -eq 2) {
    Write-Host "The value $a is equal to 2."
}
else {
    Write-Host ("The value $a is less than 2 or" +
        " was not created or initialized.")
}
```

## <a name="see-also"></a>関連項目

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Switch](about_Switch.md)
