---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC グループ リソース
ms.openlocfilehash: 68e0840eaeb116b92260ca697acd5796460a2909
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="dsc-group-resource"></a>DSC グループ リソース

> 適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

PowerShell Desired State Configuration (DSC) の Group リソースは、ターゲット ノード上でローカル グループを管理するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```
Group [string] #ResourceName
{
    GroupName          = [string]
    [ Credential       = [PSCredential] ]
    [ Description      = [string[]] ]
    [ Ensure           = [string] { Absent | Present }  ]
    [ Members          = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ MembersToInclude = [string[]] ]
    [ DependsOn        = [string[]] ]
}
```

## <a name="properties"></a>プロパティ

|  プロパティ  |  説明   |
|---|---|
| GroupName| 特定の状態を保証するグループの名前です。|
| Credential| リモート リソースにアクセスするために必要な資格情報です **注**: このアカウントには、ローカル以外のすべてのアカウントをグループに追加する適切な Active Directory アクセス許可が必要です。このアクセス許可がない場合、ターゲット ノードで構成が実行されると、エラーが発生します。
| 説明| グループの説明です。|
| Ensure| グループが存在するかどうかを示します。 グループが存在しないことを保証するには、このプロパティを "Absent" に設定します。 グループが存在することを保証するには、"Present" (既定値) に設定します。|
| [メンバー]| このプロパティは、現在のグループ メンバーシップを指定したメンバーで置き換えるために使用します。 このプロパティの値は、*Domain*\\*UserName* 形式の文字列の配列です。 構成でこのプロパティを設定する場合、**MembersToExclude** プロパティおよび **MembersToInclude** プロパティは併用しないでください。 併用すると、エラーが発生します。|
| MembersToExclude| このプロパティは、グループの既存のメンバーシップからメンバーを削除するために使用します。 このプロパティの値は、*Domain*\\*UserName* 形式の文字列の配列です。 構成でこのプロパティを設定する場合、**Members** プロパティは使用しないでください。 併用すると、エラーが発生します。|
| MembersToInclude| このプロパティは、グループの既存のメンバーシップにメンバーを追加するために使用します。 このプロパティの値は、*Domain*\\*UserName* 形式の文字列の配列です。 構成でこのプロパティを設定する場合、**Members** プロパティは使用しないでください。 併用した場合、エラーが発生します。|
| DependsOn | このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は DependsOn = "[ResourceType]ResourceName" になります。|

## <a name="example-1"></a>例 1

次の例では、"TestGroup" という名前のグループが存在しないことを保証する方法を示します。

```powershell
Group GroupExample
{
    # This removes TestGroup, if present
    # To create a new group, set Ensure to "Present“
    Ensure = "Absent"
    GroupName = "TestGroup"
}
```

## <a name="example-2"></a>例 2

次の例では、Multi-Machine Lab ビルドの一部として Active Directory ユーザーをローカルの Administrators グループに追加する方法を示します。このビルドでは、ローカル管理者アカウントの PSCredential を既に使用しています。
また、これは (ドメインの昇格後に) ドメイン管理者アカウントにも使用されるため、この既存の PSCredential はドメインで利用しやすい資格情報に変換する必要があります。
その後、ドメイン ユーザーをメンバー サーバー上のローカルの Administrators グループに追加できるようになります。

```powershell
@{
    AllNodes = @(
        @{
            NodeName = '*';
            DomainName = 'SubTest.contoso.com';
         }
        @{
            NodeName = 'Box2';
            AdminAccount = 'Admin-Dave_Alexanderson'
        }
    )
}

$domain = $node.DomainName.split('.')[0]
$DCredential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList ("$domain\$($credential.Username)", $Credential.Password)

Group AddADUserToLocalAdminGroup {
    GroupName='Administrators'
    Ensure= 'Present'
    MembersToInclude= "$domain\$($Node.AdminAccount)"
    Credential = $dCredential
    PsDscRunAsCredential = $DCredential
}
```

## <a name="example-3"></a>例 3

サーバー TigerTeamSource.Contoso.Com 上のローカル グループ TigerTeamAdmins に、特定のドメイン アカウント Contoso\JerryG が含まれないようにする例を次に示します。

```powershell
Configuration SecureTigerTeamSrouce {
  Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

  Node TigerTeamSource.Contoso.Com {
    Group TigerTeamAdmins {
       GroupName        = 'TigerTeamAdmins'
       Ensure           = 'Present'
       MembersToExclude = "Contoso\JerryG"
    }
  }
}
```