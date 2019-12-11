---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 DSC の nxSshAuthorizedKeys リソース
ms.openlocfilehash: 6e008efcbff2e679650d0bc3d5b8b573f6ef83e0
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953259"
---
# <a name="dsc-for-linux-nxsshauthorizedkeys-resource"></a>Linux 用 DSC の nxSshAuthorizedKeys リソース

PowerShell Desired State Configuration (DSC) の **nxAuthorizedKeys** リソースは、特定のユーザーの承認された ssh キーを管理するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```Syntax
nxAuthorizedKeys <string> #ResourceName
{
    KeyComment = <string>
    [ Username = <string> ]
    [ Key = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a>プロパティ

|プロパティ |説明 |
|---|---|
|KeyComment |キーの一意のコメント。 これは、キーを一意に識別するために使用されます。 |
|Username |承認された ssh キーを管理するユーザー名。 定義されていない場合、既定のユーザーは **root** です。 |
|キー |キーの内容。 **Ensure** を **Present** に設定する場合、これは必須になります。|

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|Ensure |キーが定義されるかどうかを指定します。 ユーザーの認定キー ファイルにキーが確実に存在しないようにするには、このプロパティを **Absent** に設定します。 ユーザーの承認されたキー ファイルにキーが確実に定義されるようにするには、このプロパティに **Present** を設定します。 |

## <a name="example"></a>例

次の例では、ユーザー "monuser" の公開 ssh 承認済みキーを定義しています。

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxSshAuthorizedKeys myKey
    {
        KeyComment = "myKey"
        Ensure = "Present"
        Key = 'ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEA0b+0xSd07QXRifm3FXj7Pn/DblA6QI5VAkDm6OivFzj3U6qGD1VJ6AAxWPCyMl/qhtpRtxZJDu/TxD8AyZNgc8aN2CljN1hOMbBRvH2q5QPf/nCnnJRaGsrxIqZjyZdYo9ZEEzjZUuMDM5HI1LA9B99k/K6PK2Bc1NLivpu7nbtVG2tLOQs+GefsnHuetsRMwo/+c3LtwYm9M0XfkGjYVCLO4CoFuSQpvX6AB3TedUy6NZ0iuxC0kRGg1rIQTwSRcw+McLhslF0drs33fw6tYdzlLBnnzimShMuiDWiT37WqCRovRGYrGCaEFGTG2e0CN8Co8nryXkyWc6NSDNpMzw== rsa-key-20150401'
        UserName = "monuser"
    }
}
```