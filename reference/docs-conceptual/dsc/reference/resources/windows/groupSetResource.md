---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
description: ターゲット ノード上のローカル グループを管理するためのメカニズムを備えています。
title: DSC GroupSet リソース
ms.openlocfilehash: 90e0c3f0e09c6a300988869265dfdb432ed5d217
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464197"
---
# <a name="dsc-groupset-resource"></a>DSC GroupSet リソース

> 適用先:Windows PowerShell 5.x

PowerShell Desired State Configuration (DSC) の **GroupSet** リソースは、ターゲット ノード上でローカル グループを管理するためのメカニズムを備えています。 このリソースは[複合リソース](../../../resources/authoringResourceComposite.md)であり、`GroupName` パラメーターに指定されているグループごとに [Group リソース](groupResource.md)を呼び出します。

このリソースは、複数のグループに対して同じメンバー一覧の追加/削除を行うとき、複数のグループを削除するとき、同じメンバー一覧の複数のグループを追加するときに使用します。

## <a name="syntax"></a>構文

```Syntax
Group [string] #ResourceName
{
    GroupName = [string[]]
    [ MembersToInclude = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Properties

|プロパティ |説明 |
|---|---|
|GroupName |特定の状態を保証するグループの名前です。 |
|メンバー |このプロパティは、現在のグループ メンバーシップを指定したメンバーで置き換えるために使用します。 このプロパティの値は、`Domain\UserName` 形式の文字列の配列です。 構成でこのプロパティを設定する場合、**MembersToExclude** プロパティおよび **MembersToInclude** プロパティは併用しないでください。 併用した場合、エラーが発生します。 |
|MembersToInclude |このプロパティは、グループの既存のメンバーシップにメンバーを追加するために使用します。 このプロパティの値は、`Domain\UserName` 形式の文字列の配列です。 構成でこのプロパティを設定する場合、**Members** プロパティは使用しないでください。 併用した場合、エラーが発生します。 |
|MembersToExclude |このプロパティは、グループの既存のメンバーシップからメンバーを削除するために使用します。 このプロパティの値は、`Domain\UserName` 形式の文字列の配列です。 構成でこのプロパティを設定する場合、**Members** プロパティは使用しないでください。 併用した場合、エラーが発生します。 |
|資格情報 |リモート リソースにアクセスするために必要な資格情報です このアカウントには、ローカルではないすべてのアカウントをグループに追加できる、Active Directory への適切なアクセス許可が必要です。このアクセス許可がない場合、エラーが発生します。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|Ensure |グループが存在するかどうかを示します。 グループが存在していないことを保証するには、このプロパティを **Absent** に設定します。 グループが存在することを保証するには、このプロパティを **Present** に設定します。 既定値は **Present** です。 |
|PsDscRunAsCredential |リソース全体を実行するための資格情報を設定します。 |

> [!NOTE]
> **PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。 詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。

## <a name="example-1-ensuring-groups-are-present"></a>例 1: グループが存在することを確認する

次に、"myGroup" と "myOtherGroup" という 2 つのグループが存在することを保証する例を示します。

```powershell
configuration GroupSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {
        GroupSet GroupSetTest
        {
            GroupName        = @("myGroup", "myOtherGroup")
            Ensure           = "Present"
            MembersToInclude = @("contoso\alice", "contoso\bob")
            MembersToExclude = $("contoso\john")
            Credential       = Get-Credential
        }
    }
}
$cd = @{
    AllNodes = @(
        @{
            NodeName                    = 'localhost'
            PSDscAllowPlainTextPassword = $true
            PSDscAllowDomainUser        = $true
        }
    )
}

GroupSetTest -ConfigurationData $cd
```

> [!NOTE]
> この例では、わかりやすくするためにプレーンテキストの資格情報を使用しています。 構成 MOF ファイル内の資格情報を暗号化する方法の詳細については、「[MOF ファイルのセキュリティ保護](../../../pull-server/secureMOF.md)」を参照してください。
