---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC グループ リソース
ms.openlocfilehash: b71e66e09b0af0faf252ce85f8f8746d8489b4ff
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83559864"
---
# <a name="dsc-group-resource"></a>DSC グループ リソース

> 適用先:Windows PowerShell 4.0、Windows PowerShell 5.x

Windows PowerShell Desired State Configuration (DSC) の **Group** リソースは、ターゲット ノード上でローカル グループを管理するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```Syntax
Group [string] #ResourceName
{
    GroupName = [string]
    [ Credential = [PSCredential] ]
    [ Description = [string[]] ]
    [ Members = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ MembersToInclude = [string[]] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Properties

|プロパティ |説明 |
|---|---|
|GroupName |特定の状態を保証するグループの名前です。 |
|資格情報 |リモート リソースにアクセスするために必要な資格情報です このアカウントには、ローカルではないすべてのアカウントをグループに追加できる、Active Directory への適切なアクセス許可が必要です。このアクセス許可がない場合、ターゲット ノードで構成が実行されると、エラーが発生します。
|説明 |グループの説明です。 |
|メンバー |このプロパティは、現在のグループ メンバーシップを指定したメンバーで置き換えるために使用します。 このプロパティの値は、`Domain\UserName` 形式の文字列の配列です。 構成でこのプロパティを設定する場合、**MembersToExclude** プロパティおよび **MembersToInclude** プロパティは併用しないでください。 併用すると、エラーが発生します。 |
|MembersToExclude |このプロパティは、グループの既存のメンバーシップからメンバーを削除するために使用します。 このプロパティの値は、`Domain\UserName` 形式の文字列の配列です。 構成でこのプロパティを設定する場合、**Members** プロパティは使用しないでください。 併用すると、エラーが発生します。 |
|MembersToInclude |このプロパティは、グループの既存のメンバーシップにメンバーを追加するために使用します。 このプロパティの値は、`Domain\UserName` 形式の文字列の配列です。 構成でこのプロパティを設定する場合、**Members** プロパティは使用しないでください。 併用した場合、エラーが発生します。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|Ensure |グループが存在するかどうかを示します。 グループが存在しないことを保証するには、このプロパティを **Absent** に設定します。 グループが存在することを保証するには、このプロパティを **Present** に設定します。 既定値は **Present** です。 |
|PsDscRunAsCredential |リソース全体を実行するための資格情報を設定します。 |

> [!NOTE]
> **PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。 詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。

## <a name="example-1-ensure-group-is-not-present"></a>例 1:グループが存在しないことを保証する

次の例では、"TestGroup" という名前のグループが存在しないことを保証する方法を示します。

```powershell
Group GroupExample
{
    # This removes TestGroup, if present
    # To create a new group, set Ensure to "Present"
    Ensure = "Absent"
    GroupName = "TestGroup"
}
```

## <a name="example-2-add-domain-user-to-local-group"></a>例 2:ローカル グループにドメイン ユーザーを追加する

次の例では、Multi-Machine Lab ビルドの一部として Active Directory ユーザーをローカルの Administrators グループに追加する方法を示します。このビルドでは、ローカル管理者アカウントの PSCredential を既に使用しています。 また、これは (ドメインの昇格後に) ドメイン管理者アカウントにも使用されるため、この既存の PSCredential はドメインで利用しやすい資格情報に変換する必要があります。 その後、ドメイン ユーザーをメンバー サーバー上のローカルの Administrators グループに追加できるようになります。

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
Configuration SecureTigerTeamSource {
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
