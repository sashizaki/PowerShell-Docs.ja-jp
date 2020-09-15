---
ms.date: 07/17/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 DSC の nxScript リソース
ms.openlocfilehash: e39808e110d5ee4bf9d0ccd418ca3b15ac9fe420
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463654"
---
# <a name="dsc-for-linux-nxscript-resource"></a>Linux 用 DSC の nxScript リソース

PowerShell Desired State Configuration (DSC) の **nxScript** リソースは、Linux ノード上で Linux スクリプトを実行するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```Syntax
nxScript <string> #ResourceName
{
    GetScript = <string>
    SetScript = <string>
    TestScript = <string>
    [ User = <string> ]
    [ Group = <string> ]
    [ DependsOn = <string[]> ]
}
```

## <a name="properties"></a>Properties

|プロパティ |説明 |
|---|---|
|GetScript |コンピューターの現在の状態を返すスクリプトを指定します。 このスクリプトは、[GetDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) スクリプトを呼び出したときに実行されます。 スクリプトは、`#!/bin/bash` などのシバンで開始する必要があります。 |
|SetScript |コンピューターを正しい状態にするスクリプトを指定します。 [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) スクリプトを呼び出すと、**TestScript** が最初に実行されます。 **TestScript** ブロックが 0 以外の終了コードを返した場合は、**SetScript** ブロックが実行されます。 **TestScript** が終了コード 0 を返した場合は、**SetScript** が実行されません。 スクリプトは、`#!/bin/bash` などのシバンで開始する必要があります。 |
|TestScript |ノードが現在正しい状態であるかどうかを評価するスクリプトを指定します。 [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) スクリプトを呼び出すと、このスクリプトが実行されます。 0 以外の終了コードが返された場合、**SetScript** が実行されます。 終了コード 0 が返された場合、**SetScript** は実行されません。 [TestDscConfiguration](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) スクリプトを呼び出すと、**TestScript** も実行されます。 ただし、この場合、**TestScript** からどのような終了コードが返されるに関係なく、**SetScript** は実行されません。 実際の構成が現在の必要な状態の構成と一致する場合、**TestScript** はコンテンツを含み、かつ終了コード 0 を返す必要があります。一致しない場合は、0 以外の終了コードを返す必要があります。 現在の Desired State Configuration は DSC を使用しているノードに適用された最後の構成です。 スクリプトは、`#!/bin/bash` などのシバンで開始する必要があります。 |
|User |スクリプトを実行するユーザー。 |
|Group |スクリプトを実行するグループ。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |

## <a name="example"></a>例

次の例では、追加の構成管理を実行するための **nxScript** リソースの使用を示します。

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxScript KeepDirEmpty {

    GetScript = @"
#!/bin/bash
ls /tmp/mydir/ | wc -l
"@

    SetScript = @"
#!/bin/bash
rm -rf /tmp/mydir/*
"@

    TestScript = @'
#!/bin/bash
filecount=`ls /tmp/mydir | wc -l`
if [ $filecount -gt 0 ]
then
    exit 1
else
    exit 0
fi
'@
    }
}
```
