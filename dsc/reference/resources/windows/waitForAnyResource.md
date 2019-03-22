---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WaitForAny リソース
ms.openlocfilehash: 55869f665837b422c006f4cfb3e91366fac60362
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2019
ms.locfileid: "58058821"
---
# <a name="dsc-waitforany-resource"></a>DSC WaitForAny リソース

> 適用先:Windows PowerShell 5.1 以降

**WaitForAny** Desired State Configuration (DSC) リソースを [DSC 構成](../../../configurations/configurations.md)のノード ブロック内で使用して、他のノードの構成の依存関係を指定できます。

このリソースは、**ResourceName** プロパティで指定されたリソースが、**NodeName** プロパティで定義された任意のターゲット ノードで目的の状態になった場合に成功します。


## <a name="syntax"></a>構文

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

このリソースを使用する方法の例は、「[ノードの相互依存関係の指定](../../../configurations/crossNodeDependencies.md)」を参照してください。
