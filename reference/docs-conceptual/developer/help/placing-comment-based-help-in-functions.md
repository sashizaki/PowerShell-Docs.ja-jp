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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367781"
---
# <a name="placing-comment-based-help-in-functions"></a>関数にコメント ベースのヘルプを配置する

このトピックでは、`Get-Help` コマンドレットによってコメントベースのヘルプトピックが適切な関数に関連付けられるように、関数のコメントベースのヘルプを配置する場所について説明します。

## <a name="where-to-place-comment-based-help-for-a-function"></a>関数のコメントベースのヘルプを配置する場所

- 関数本体の先頭にあります。

- 関数本体の末尾にあります。

- `Function` キーワードの前。 関数がスクリプトモジュールまたはスクリプトモジュール内にある場合は、コメントベースのヘルプの最後の行と `Function` キーワードの間に複数の空白行を入れることはできません。 それ以外の場合、`Get-Help` は、関数ではなく、スクリプトにヘルプを関連付けます。

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