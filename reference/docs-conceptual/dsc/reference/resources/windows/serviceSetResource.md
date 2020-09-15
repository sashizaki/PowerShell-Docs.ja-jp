---
ms.date: 07/16/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC ServiceSet リソース
ms.openlocfilehash: b51cfa86aa6d2114553a0eee681cb88ea93e213f
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464402"
---
# <a name="dsc-serviceset-resource"></a>DSC ServiceSet リソース

> 適用先:Windows PowerShell 4.0、Windows PowerShell 5.x

PowerShell Desired State Configuration (DSC) の **ServiceSet** リソースは、ターゲット ノード上でサービスを管理するためのメカニズムを備えています。 このリソースは[複合リソース](../../../resources/authoringResourceComposite.md)であり、**Name** プロパティに指定されているサービスごとに [Service リソース](serviceResource.md)を呼び出します。

サービスの数を同じ状態に構成するときにこのリソースを使用します。

## <a name="syntax"></a>構文

```Syntax
ServiceSet [string] #ResourceName
{
    Name = [string[]]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Properties

|プロパティ |説明 |
|---|---|
|名前 |サービス名を示します。 これは表示名とは異なることがあります。 `Get-Service` コマンドレットを使用すると、サービスとその現在の状態の一覧を取得できます。 |
|StartupType |サービスのスタートアップの種類を示します。 このプロパティで有効な値は、**Automatic**、**Disabled**、**Manual** です。 |
|BuiltInAccount |サービスに使用するサインイン アカウントを示します。 このプロパティで有効な値は、**LocalService**、**LocalSystem**、**NetworkService** です。 |
|State |サービスに対して保証する状態を次のように示します。**Stopped** または **Running**。 |
|資格情報 |サービス リソースを実行するアカウントの資格情報を示します。 このプロパティおよび **BuiltinAccount** プロパティを同時に使用することはできません。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|Ensure |サービスがシステムに存在するかどうかを示します。 サービスが存在しないようにするには、このプロパティを **[Absent]** に設定します。 対象サービスの存在を保証するには、これを **Present** に設定します 既定値は **Present** です。 |
|PsDscRunAsCredential |リソース全体を実行するための資格情報を設定します。 |

> [!NOTE]
> **PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。 詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。

## <a name="example"></a>例

次の構成で "Windows オーディオ" サービスと "リモート デスクトップ サービス" サービスが開始します。

```powershell
configuration ServiceSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {
        ServiceSet ServiceSetExample
        {
            Name        = @("TermService", "Audiosrv")
            StartupType = "Manual"
            State       = "Running"
        }
    }
}
```
