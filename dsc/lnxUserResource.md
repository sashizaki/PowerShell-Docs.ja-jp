---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 DSC の nxUser リソース
ms.openlocfilehash: 222bd2191cf5c5f0a90ba947275ffde47d22ec86
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="dsc-for-linux-nxuser-resource"></a>Linux 用 DSC の nxUser リソース

PowerShell Desired State Configuration (DSC) の **nxUser** リソースは、Linux ノード上でローカル ユーザーを管理するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```
nxUser <string> #ResourceName
{
    UserName = <string>
    [ Ensure = <string> { Absent | Present }  ]
    [ FullName = <string> ]
    [ Description = <string> ]
    [ Password = <string> ]
    [ Disabled = <bool> ]
    [ PasswordChangeRequired = <bool> ]
    [ HomeDirectory = <string> ]
    [ GroupID = <string> ]
    [ DependsOn = <string[]> ]

}
```

## <a name="properties"></a>プロパティ

|  プロパティ |  特定の状態を保証するアカウント名を示します。 |
|---|---|
| UserName| ファイルまたはディレクトリの状態を保証する場所を指定します。|
| Ensure| アカウントが存在するかどうかを指定します。 このアカウントが存在することを保証するには、このプロパティを "Present" に設定し、アカウントが存在しないことを保証するには、"Absent" に設定します。|
| FullName| ユーザー アカウントに使用するフルネームを表す文字列。|
| 説明| ユーザー アカウントの説明。|
| Password| Linux コンピューターの適切な形式でのユーザー パスワードのハッシュ。 通常、これはソルト化ハッシュ SHA-256 または SHA-512 です。 Debian および Ubuntu Linux では、この値は、mkpasswd コマンドを使用して生成できます。 他の Linux ディストリビューションの場合は、Python の暗号ライブラリの crypt メソッドを使用してハッシュを生成できます。|
| 無効| アカウントが有効かどうかを示します。 このアカウントを無効にするには、このプロパティを **$true** に設定し、有効にするには **$false** に設定します。|
| PasswordChangeRequired| ユーザーがパスワードを変更できるかどうかを示します。 ユーザーがパスワードを変更できないようにするには、このプロパティを **$true** に設定し、ユーザーがパスワードを変更できるようにするには、**$false** に設定します。 既定値は **$false** です。 このプロパティは、以前存在しなかったユーザー アカウントを作成するときにのみ評価されます。|
| HomeDirectory| ユーザーのホーム ディレクトリ。|
| GroupID| ユーザーのプライマリ グループ ID。|
| DependsOn | このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が "ResourceName" で、そのタイプが "ResourceType" である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。|

## <a name="example"></a>例

次の例は、ユーザー "monuser" が存在し、グループ "DBusers" のメンバーであることを保証しています。

```
Import-DSCResource -Module nx

Node $node {
nxUser UserExample{
   UserName = "monuser"
   Description = "Monitoring user"
   Password  =    '$6$fZAne/Qc$MZejMrOxDK0ogv9SLiBP5J5qZFBvXLnDu8HY1Oy7ycX.Y3C7mGPUfeQy3A82ev3zIabhDQnj2ayeuGn02CqE/0'
   Ensure = "Present"
   HomeDirectory = "/home/monuser"
}

nxGroup GroupExample{
   GroupName = "DBusers"
   Ensure = "Present"
   MembersToInclude = "monuser"
   DependsOn = "[nxUser]UserExample"
}
}
```