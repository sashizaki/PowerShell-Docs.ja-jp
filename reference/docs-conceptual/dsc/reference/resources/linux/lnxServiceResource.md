---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 DSC の nxService リソース
ms.openlocfilehash: 6bb58796c4deff1153f932f61c328d84f8c4d2ca
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954839"
---
# <a name="dsc-for-linux-nxservice-resource"></a>Linux 用 DSC の nxService リソース

PowerShell Desired State Configuration (DSC) の **nxService** リソースは、Linux ノード上でサービスを管理するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```Syntax
nxService <string> #ResourceName
{
    Name = <string>
    [ Controller = <string> { init | upstart | systemd } ]
    [ Enabled = <bool> ]
    [ State = <string> { Running | Stopped } ]
    [ DependsOn = <string[]> ]
}
```

## <a name="properties"></a>プロパティ

|プロパティ |説明 |
|---|---|
|名前 |構成するサービス/デーモンの名前。 |
|コントローラー |サービスを構成するときに使用するサービス コントローラーの種類。 |
|Enabled |ブート時にサービスを開始するかどうかを示します。 |
|State |サービスが実行されるかどうかを示します。 サービスが実行されないようにするには、このプロパティを **Stopped** に設定します。 サービスが確実に実行されるようにするには、このプロパティを **Running** に設定します。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |

## <a name="additional-information"></a>追加情報

**nxService** リソースでは、サービス定義やサービスのスクリプトが存在しない場合、これらは作成されません。 PowerShell Desired State Configuration の **nxFile** リソースを使用して、サービス定義ファイルやスクリプトの存在または内容を管理できます。

## <a name="example"></a>例

次の例では、**SystemD** サービス コントローラーを使用して登録された 'httpd' サービス (Apache HTTP Server の場合) の構成を示します。

```powershell
Import-DSCResource -Module nx

Node $node
{
    #Apache Service
    nxService ApacheService {
        Name = 'httpd'
        State = 'running'
        Enabled = $true
        Controller = 'systemd'
    }
}
```