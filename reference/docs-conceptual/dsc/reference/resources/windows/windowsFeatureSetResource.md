---
ms.date: 07/16/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WindowsFeatureSet リソース
ms.openlocfilehash: 856c56e0b35a26add729ef77db9dca71fdc0a4d0
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463858"
---
# <a name="dsc-windowsfeatureset-resource"></a>DSC WindowsFeatureSet リソース

> 適用先:Windows PowerShell 5.x

Windows PowerShell Desired State Configuration (DSC) の **WindowsFeatureSet** リソースは、役割と機能がターゲット ノードで追加または削除されることを保証するためのメカニズムを備えています。 このリソースは[複合リソース](../../../resources/authoringResourceComposite.md)であり、**Name** プロパティに指定されている機能ごとに [WindowsFeature リソース](windowsfeatureResource.md)を呼び出します。

Windows 機能の数を同じ状態に構成するときにこのリソースを使用します。

## <a name="syntax"></a>構文

```Syntax
WindowsFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ Source = [string] ]
    [ IncludeAllSubFeature = [Boolean] ]
    [ Credential = [PSCredential] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Properties

|  プロパティ  |  説明   |
|---|---|
|名前 |追加または削除する役割または機能の名前。 これは [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature?view=winserver2012r2-ps) コマンドレットの **Name** プロパティと同じものであり、役割または機能の表示名ではありません。 |
|source |必要に応じて、インストールに使用するソース ファイルの場所を示します。 |
|IncludeAllSubFeature |**Name** プロパティで指定した機能を使用して必要なすべてのサブ機能を含めるには、このプロパティを `$true` に設定します。 |
|資格情報 |役割または機能の追加や削除に使用する資格情報。 |
|LogPath |リソース プロバイダーの操作を記録するログ ファイルへのパス。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|Ensure |役割または機能を追加するかどうかを示します。 役割または機能を確実に追加するには、このプロパティを **Present** に設定します。 役割または機能を確実に削除するには、このプロパティを **Absent** に設定します。 既定値は **Present** です。 |
|PsDscRunAsCredential |リソース全体を実行するための資格情報を設定します。 |

> [!NOTE]
> **PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。 詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。

## <a name="example"></a>例

次の構成では、**Web-Server** (IIS) 機能、**SMTP Server** 機能、各機能のすべてのサブ機能がインストールされます。

```powershell
configuration FeatureSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        WindowsFeatureSet WindowsFeatureSetExample
        {
            Name                    = @("SMTP-Server", "Web-Server")
            Ensure                  = 'Present'
            IncludeAllSubFeature    = $true
        }
    }
}
```
