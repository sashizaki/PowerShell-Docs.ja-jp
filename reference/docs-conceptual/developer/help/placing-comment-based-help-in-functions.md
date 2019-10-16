---
title: 関数にコメントベースのヘルプを配置する |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ec7159e-e4e9-4b21-95df-94244432f679
caps.latest.revision: 5
ms.openlocfilehash: a663bd69be7825b1685f64ff8d3068bdd8ca3265
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367781"
---
# <a name="placing-comment-based-help-in-functions"></a>関数にコメント ベースのヘルプを配置する

このトピックでは、関数のコメントベースのヘルプを配置する場所について説明します。これにより、@no__t 0 のコマンドレットは、コメントベースのヘルプトピックと正しい関数を関連付けます。

## <a name="where-to-place-comment-based-help-for-a-function"></a>関数のコメントベースのヘルプを配置する場所

- 関数本体の先頭にあります。

- 関数本体の末尾にあります。

- @No__t-0 キーワードの前。 関数がスクリプトまたはスクリプトモジュール内にある場合は、コメントベースのヘルプの最後の行と `Function` キーワードの間に複数の空白行を入れることはできません。 それ以外の場合、`Get-Help` を指定すると、ヘルプが関数ではなくスクリプトに関連付けられます。

## <a name="examples-of-help-placement-in-a-function"></a>関数内のヘルプの配置例

 次の例では、関数のコメントベースのヘルプの3つの配置オプションについて説明します。

### <a name="help-at-the-beginning-of-a-function-body"></a>関数本体の先頭のヘルプ

 次の例では、関数本体の先頭にあるコメントに基づいています。

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

### <a name="help-at-the-end-of-a-function-body"></a>関数本体の最後のヘルプ

 次の例では、関数本体の最後にコメントを使用してコメントを示しています。

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

### <a name="help-before-the-function-keyword"></a>Function キーワードの前のヘルプ

 次の例では、関数キーワードの前の行に基づいてコメントを示しています。

```powershell

<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}

```