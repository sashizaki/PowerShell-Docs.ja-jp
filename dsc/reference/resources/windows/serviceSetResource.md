---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC ServiceSet リソース
ms.openlocfilehash: 5694c2abc5c0caf0098670b629af464b35125583
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047559"
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
| StartupType| サービスのスタートアップの種類を示します。 このプロパティに許容される値は次のとおりです。**自動**、**無効**、および**手動**|
| BuiltInAccount| サービスに使用するサインイン アカウントを示します。 このプロパティに許容される値は次のとおりです。**LocalService**、 **LocalSystem**、および**NetworkService**します。|
| State| サービスに対して保証する状態を示します。**停止**または**を実行している**します。|
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
