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
ms.openlocfilehash: 898225a582c7ed25f746dec7f84012db1ae60b98
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557068"
---
# <a name="placing-comment-based-help-in-functions"></a>関数にコメント ベースのヘルプを配置する

このトピックでは、コマンドレットによって `Get-Help` コメントベースのヘルプトピックが適切な関数に関連付けられるように、関数のコメントベースのヘルプを配置する場所について説明します。

## <a name="where-to-place-comment-based-help-for-a-function"></a>関数のコメントベースのヘルプを配置する場所

- 関数本体の先頭にあります。

- 関数本体の末尾にあります。

- キーワードの前 `Function` 。 関数がスクリプトまたはスクリプトモジュール内にある場合は、コメントベースのヘルプとキーワードの最後の行の間に複数の空白行を入れることはできません `Function` 。 それ以外の場合は、 `Get-Help` 関数ではなく、スクリプトにヘルプを関連付けます。

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
