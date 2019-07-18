---
title: スクリプトにコメント ベースのヘルプを配置する |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49f8267c-d887-4d7d-b9b7-80dc624b1261
caps.latest.revision: 4
ms.openlocfilehash: d199c53a748ac57bb2a5f998b5056e39d3e80c0d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083231"
---
# <a name="placing-comment-based-help-in-scripts"></a>スクリプトにコメント ベースのヘルプを配置する

このトピックでは、スクリプトのコメント ベースのヘルプを配置する場所を説明しますように、`Get-Help`スクリプトとスクリプトで可能性のあるすべての関数ではなく、コマンドレットは、コメント ベースのヘルプ トピックを関連付けます。

## <a name="where-to-place-comment-based-help-for-a-script"></a>スクリプトのコメント ベースのヘルプを配置する場所

- スクリプト ファイルの先頭にします。 スクリプトでスクリプトのヘルプの前に、コメントや空白行のみです。

- スクリプト ファイルの末尾にあります。

  (ヘルプ) の後のスクリプトの本文の最初の項目が関数宣言の場合は、ヘルプ、スクリプトの末尾と関数の宣言の間に少なくとも 2 つの空白行が必要があります。 それ以外の場合、ヘルプは、関数、スクリプトのヘルプではないのヘルプとして解釈されます。

## <a name="examples-of-help-placement-in-a-script"></a>スクリプトでヘルプの例

 次の例は、各スクリプトのコメント ベースのヘルプの配置オプションを示します。

### <a name="help-at-the-beginning-of-a-script"></a>スクリプトの先頭にあるヘルプします。

 次の例を示しますスクリプトの先頭にコメント ベースします。

```
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a>スクリプトの末尾にあるヘルプします。

 次の例では、コメント ベースのスクリプトの末尾を示します。

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>

```