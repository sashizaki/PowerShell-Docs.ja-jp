---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC ServiceSet リソース
ms.openlocfilehash: 5694c2abc5c0caf0098670b629af464b35125583
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076836"
---
# <a name="dsc-serviceset-resource"></a>DSC ServiceSet リソース

> 適用先:Windows PowerShell 4.0、Windows PowerShell 5.0

PowerShell Desired State Configuration (DSC) の **ServiceSet** リソースは、ターゲット ノード上でサービスを管理するためのメカニズムを備えています。 このリソースは[複合リソース](../../../resources/authoringResourceComposite.md)であり、`Name` プロパティに指定されているサービスごとに [Service リソース](serviceResource.md)を呼び出します。

サービスの数を同じ状態に構成するときにこのリソースを使用します。

## <a name="syntax"></a>構文

```
Service [string] #ResourceName
{
    Name = [string[]]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Ensure = [string] { Absent | Present }  ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]

}
```

## <a name="properties"></a>プロパティ

|  プロパティ  |  説明   |
|---|---|
| 名前| サービス名を示します。 これは表示名とは異なることがあります。 [Get-Service](https://technet.microsoft.com/library/hh849804.aspx) コマンドレットを使用すると、サービスとその現在の状態の一覧を取得できます。|
| StartupType| サービスのスタートアップの種類を示します。 このプロパティで有効な値は、**Automatic**、**Disabled**、**Manual** です|
| BuiltInAccount| サービスに使用するサインイン アカウントを示します。 このプロパティで有効な値は、**LocalService**、**LocalSystem**、**NetworkService** です。|
| State| サービスに対して保証する状態を次のように示します。**Stopped** または **Running**。|
| Ensure| サービスがシステムに存在するかどうかを示します。 サービスが存在しないようにするには、このプロパティを **[Absent]** に設定します。 ターゲットが存在するようにするには、**[Present]** (既定値) に設定します。|
| Credential| サービス リソースを実行するアカウントの資格情報を示します。 このプロパティおよび **BuiltinAccount** プロパティを同時に使用することはできません。|
| DependsOn| このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が *ResourceName* で、そのタイプが *ResourceType* である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。|



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
