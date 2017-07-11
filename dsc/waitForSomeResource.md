---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC WaitForSome リソース"
ms.openlocfilehash: 5d67a9111f6358240590b651e627ffb96abc0896
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="dsc-waitforsome-resource" class="xliff"></a>

# DSC WaitForSome リソース

> 適用先: Windows PowerShell 5.0 以降

**WaitForAny** Desired State Configuration (DSC) リソースを [DSC 構成](configurations.md)のノード ブロック内で使用して、他のノードの構成の依存関係を指定できます。

このリソースは、 **ResourceName** プロパティで指定されたリソースが、**NodeName** プロパティで定義された最小数 (**NodeCount** で指定) のノードで目的の状態になった場合に成功します。 


<a id="syntax" class="xliff"></a>

## 構文

```
WaitForAll [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    NodeCount = [Uint32]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ] 
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
}
```

<a id="properties" class="xliff"></a>

## プロパティ

|  プロパティ  |  説明   | 
|---|---| 
| ResourceName| 依存するリソースの名前。| 
| NodeName| 依存するリソースのターゲット ノード。| 
| NodeCount| このリソースが成功するために、目的の状態にする必要があるノードの最小数。|
| RetryIntervalSec| 再試行するまでの秒数。 最小値は 1 です。| 
| RetryCount| 再試行の回数の最大数。| 
| ThrottleLimit| 同時に接続するコンピューターの数。 既定では、new-cimsession の既定値です。| 
| DependsOn | このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。|


<a id="example" class="xliff"></a>

## 例

このリソースを使用する方法の例は、「[ノードの相互依存関係の指定](crossNodeDependencies.md)」を参照してください。

