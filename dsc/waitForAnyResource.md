---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC WaitForAny リソース"
ms.openlocfilehash: ba1873cc0ecfc4596cbad5b61b4a52b61ea4778a
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="dsc-waitforany-resource" class="xliff"></a>

# DSC WaitForAny リソース

> 適用先: Windows PowerShell 5.1 以降

**WaitForSome** Desired State Configuration (DSC) リソースを [DSC 構成](configurations.md)のノード ブロック内で使用して、他のノードの構成の依存関係を指定することができます。

このリソースは **ResourceName** プロパティで指定されたリソースが、 **NodeName** プロパティで定義された任意のターゲット ノードで目的の状態になった場合に成功します。


<a id="syntax" class="xliff"></a>

## 構文

```
WaitForAny [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
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
| RetryIntervalSec| 再試行するまでの秒数。 最小値は 1 です。| 
| RetryCount| 再試行の回数の最大数。| 
| ThrottleLimit| 同時に接続するコンピューターの数。 既定では、new-cimsession の既定値です。| 
| DependsOn | このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。|


<a id="example" class="xliff"></a>

## 例

このリソースを使用する方法の例は、「[ノードの相互依存関係の指定](crossNodeDependencies.md)」を参照してください。

