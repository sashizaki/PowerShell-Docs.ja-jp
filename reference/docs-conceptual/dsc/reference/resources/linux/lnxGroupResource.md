---
ms.date: 07/17/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 DSC の nxGroup リソース
ms.openlocfilehash: f196c74b94ec27818d58b59d1e489facd8ab0a65
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464436"
---
# <a name="dsc-for-linux-nxgroup-resource"></a>Linux 用 DSC の nxGroup リソース

PowerShell Desired State Configuration (DSC) の **nxGroup** リソースは、Linux ノード上でローカル グループを管理するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```Syntax
nxGroup <string> #ResourceName
{
    GroupName = <string>
    [ Members = <string[]> ]
    [ MembersToInclude = <string[]> ]
    [ MembersToExclude = <string[]> ]
    [ PreferredGroupID = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present } ]
}
```

## <a name="properties"></a>Properties

|プロパティ |説明 |
|---|---|
|GroupName |特定の状態を保証するグループの名前を指定します。 |
|メンバー |グループを形成するメンバーを指定します。 |
|MembersToInclude |グループのメンバーであることを保証するユーザーを指定します。 |
|MembersToExclude |グループのメンバーでないことを保証するユーザーを指定します。 |
|PreferredGroupID |可能であれば、グループ id を指定の値に設定します。 そのグループ id が現在使用中である場合は、次に使用可能なグループ id が使用されます。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|Ensure |グループが存在するかどうかを決定します。 グループの存在を保証するには、このプロパティを **Present** に設定します。 グループが存在しないことを保証するには、**Absent** に設定します。 既定値は **Present** です。 |

## <a name="example"></a>例

次の例では、ユーザー 'monuser' が存在し、グループ 'DBusers' のメンバーであることを保証しています。

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxUser UserExample {
       UserName = 'monuser'
       Description = 'Monitoring user'
       Password = '$6$fZAne/Qc$MZejMrOxDK0ogv9SLiBP5J5qZFBvXLnDu8HY1Oy7ycX.Y3C7mGPUfeQy3A82ev3zIabhDQnj2ayeuGn02CqE/0'
       Ensure = 'Present'
       HomeDirectory = '/home/monuser'
    }

    nxGroup GroupExample {
       GroupName = 'DBusers'
       Ensure = 'Present'
       MembersToInclude = 'monuser'
       DependsOn = '[nxUser]UserExample'
    }
}
```
