---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WaitForAll リソース
ms.openlocfilehash: 4413220bb0b5eeef5fd1599f794cd551f15a2925
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="dsc-waitforall-resource"></a>DSC WaitForAll リソース

> 適用先: Windows PowerShell 5.0 以降

**WaitForAll** Desired State Configuration (DSC) リソースを [DSC 構成](configurations.md)のノード ブロック内で使用して、他のノードの構成の依存関係を指定することができます。

このリソースは、**ResourceName** プロパティで指定されたリソースが、 **NodeName** プロパティで定義されたすべてのターゲット ノードで目的の状態になった場合に成功します。


## <a name="syntax"></a>構文

```
WaitForAll [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ]
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a>プロパティ

|  プロパティ  |  説明   |
|---|---|
| ResourceName| 依存するリソースの名前。 このリソースが別の構成に属している場合は、"[__リソースの種類__]__リソース名__::[__構成名__]::[__構成名__]" という形式で名前を指定してください。|
| NodeName| 依存するリソースのターゲット ノード。|
| RetryIntervalSec| 再試行するまでの秒数。 最小値は 1 です。|
| RetryCount| 再試行の回数の最大数。|
| ThrottleLimit| 同時に接続するコンピューターの数。 既定では、new-cimsession の既定値です。|
| DependsOn | このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。|


## <a name="example"></a>例

このリソースを使用する方法の例は、「[ノードの相互依存関係の指定](crossNodeDependencies.md)」を参照してください。