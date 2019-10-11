---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 DSC の nxPackage リソース
ms.openlocfilehash: 4091cbbd5e34a84b9011870da4bda93281378347
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954819"
---
# <a name="dsc-for-linux-nxpackage-resource"></a>Linux 用 DSC の nxPackage リソース

PowerShell Desired State Configuration (DSC) の **nxPackage** リソースは、Linux ノード上でパッケージを管理するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```Syntax
nxPackage <string> #ResourceName
{
    Name = <string>
    [ PackageManager = <string> { Yum | Apt | Zypper } ]
    [ PackageGroup = <bool>]
    [ Arguments = <string> ]
    [ ReturnCode = <uint32> ]
    [ FilePath = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a>プロパティ

|プロパティ |説明 |
|---|---|
|名前 |特定の状態を保証するパッケージの名前。 |
|PackageManager |サポートされている値は、**yum**、**apt**、**zypper** です。 パッケージのインストール時に使用するパッケージ マネージャーを指定します。 **FilePath** を指定した場合、その指定したパスを使用してパッケージがインストールされます。 それ以外の場合、パッケージ マネージャーを使用して、事前に構成されているリポジトリからパッケージがインストールされます。 **PackageManager** も **FilePath** も指定しない場合は、システムの既定のパッケージ マネージャーが使用されます。 |
|PackageGroup |`$true` の場合、**Name** は **PackageManager** で使用されるパッケージ グループの名前であるものとみなされます。 **PackageGroup** は、**FilePath** を指定したときには使用できません。 |
|引数 |指定されたとおりにパッケージに渡される引数の文字列。 |
|ReturnCode |想定されるリターン コード。 実際のリターン コードがここで指定される想定される値と一致しない場合、構成はエラーを返します。 |
|ファイル パス |パッケージが存在するファイル パス。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|Ensure |パッケージが存在するかどうかを決定します。 パッケージの存在を保証するには、このプロパティを **Present** に設定します。 パッケージが存在しないことを保証するには、**Absent** に設定します。 既定値は **Present** です。 |

## <a name="example"></a>例

次の例では、"Yum" パッケージ マネージャーを使用して、Linux コンピューターに "httpd" という名前のパッケージが確実にインストールされるようにしています。

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxPackage httpd
    {
        Name = "httpd"
        Ensure = "Present"
        PackageManager = "Yum"
    }
}
```