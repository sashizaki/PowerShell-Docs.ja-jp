---
title: スクリプトにコメントベースのヘルプを配置する |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49f8267c-d887-4d7d-b9b7-80dc624b1261
caps.latest.revision: 4
ms.openlocfilehash: d199c53a748ac57bb2a5f998b5056e39d3e80c0d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361181"
---
# <a name="placing-comment-based-help-in-scripts"></a>スクリプトにコメント ベースのヘルプを配置する

このトピックでは、`Get-Help` コマンドレットがコメントベースのヘルプトピックをスクリプトに関連付け、スクリプト内に存在する可能性のある関数を使用しないように、スクリプトのコメントベースのヘルプを配置する場所について説明します。

## <a name="where-to-place-comment-based-help-for-a-script"></a>スクリプトのコメントベースのヘルプを配置する場所

- スクリプトファイルの先頭にあります。 スクリプトのヘルプは、コメントと空白行によってのみスクリプトの先頭に配置できます。

- スクリプトファイルの末尾にあります。

  スクリプト本体の最初の項目 (ヘルプの後) が関数宣言の場合、スクリプトヘルプの末尾と関数宣言の間には、少なくとも2つの空白行が必要です。 それ以外の場合、ヘルプは、スクリプトのヘルプではなく、関数のヘルプとして解釈されます。

## <a name="examples-of-help-placement-in-a-script"></a>スクリプト内のヘルプの配置例

 次の例は、スクリプトのコメントベースのヘルプの各配置オプションを示しています。

### <a name="help-at-the-beginning-of-a-script"></a>スクリプトの先頭のヘルプ

 次の例では、スクリプトの先頭にあるコメントに基づいています。

```
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a>スクリプトの最後のヘルプ

 次の例では、スクリプトの最後にコメントを使用してコメントを示します。

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>

```