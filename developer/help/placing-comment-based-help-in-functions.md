---
title: 関数のコメント ベースのヘルプを配置する |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ec7159e-e4e9-4b21-95df-94244432f679
caps.latest.revision: 5
ms.openlocfilehash: a663bd69be7825b1685f64ff8d3068bdd8ca3265
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857948"
---
# <a name="placing-comment-based-help-in-functions"></a>関数にコメント ベースのヘルプを配置する

このトピックでは、関数のコメント ベースのヘルプを配置する場所を説明しますように、`Get-Help`コマンドレットは、適切な関数をコメント ベースのヘルプ トピックを関連付けます。

## <a name="where-to-place-comment-based-help-for-a-function"></a>関数のコメント ベースのヘルプを配置する場所

- 関数本体の先頭にします。

- 関数本体の末尾にあります。

- 前に、`Function`キーワード。 コメント ベースのヘルプの最後の行の間で 1 つ以上の空白行が存在することはできません、関数は、スクリプトまたはスクリプト モジュールが、および`Function`キーワード。 それ以外の場合、`Get-Help`スクリプトを使用して、関数ではなく、ヘルプを関連付けます。

## <a name="examples-of-help-placement-in-a-function"></a>関数でヘルプの例

 次の例は、各関数のコメント ベースのヘルプの次の 3 つの配置オプションを示します。

### <a name="help-at-the-beginning-of-a-function-body"></a>関数本体の先頭のヘルプします。

 次の例を示します関数本体の先頭にコメント ベースします。

```powershell

function MyProcess
{
    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>

    Get-Process powershell
}

```

### <a name="help-at-the-end-of-a-function-body"></a>関数本体の末尾にあるヘルプします。

 次の例では、コメント ベースの関数本体の末尾を示します。

```powershell

function MyFunction
{
    Get-Process powershell

    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>
}

```

### <a name="help-before-the-function-keyword"></a>関数キーワードの前にヘルプします。

 次の例を示します関数キーワードの前に行のコメント ベースします。

```powershell

<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}

```