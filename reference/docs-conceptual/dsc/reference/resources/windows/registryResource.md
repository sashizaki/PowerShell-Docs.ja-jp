---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Registry リソース
ms.openlocfilehash: 9f65815cbe6a94831b88cb3425bf688e1a99a9c0
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83559904"
---
# <a name="dsc-registry-resource"></a>DSC Registry リソース

> 適用先:Windows PowerShell 4.0、Windows PowerShell 5.x

Windows PowerShell Desired State Configuration (DSC) の **Registry** リソースは、ターゲット ノードでレジストリ キーと値を管理するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```Syntax
Registry [string] #ResourceName
{
    Key = [string]
    ValueName = [string]
    [ Force =  [bool]   ]
    [ Hex = [bool] ]
    [ ValueData = [string[]] ]
    [ ValueType = [string] { Binary | Dword | ExpandString | MultiString | Qword | String }  ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Present | Absent }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Properties

|プロパティ |説明 |
|---|---|
|Key |特定の状態を確認するレジストリ キーのパスを示します。 このパスには、ハイブを含める必要があります。 |
|ValueName |レジストリ値の名前を示します。 レジストリ キーを追加または削除するには、**ValueType** または **ValueData** を指定せずに、このプロパティを空の文字列で指定します。 レジストリ キーの既定値を変更または削除するには、**ValueType** または **ValueData** を指定し、このプロパティを空の文字列で指定します。 |
|Force |指定のレジストリ キーが存在する場合、**Force** はそのキーを新しい値で上書きします。 レジストリ キーをサブキーと共に削除する場合は、これが `$true` である必要があります。 |
|Hex |16 進形式でデータを表現するかどうかを示します。 指定した場合、DWORD/QWORD 値データが 16 進形式で表示されます。 その他の種類に対しては無効です。 既定値は `$false` です。 |
|ValueData |レジストリ値のデータ。 |
|ValueType |値の種類を示します。 サポートされている型は次のとおりです。**String** (REG_SZ)、**Binary** (REG-BINARY)、**Dword** (32 ビット REG_DWORD)、**Qword** (64 ビット REG_QWORD)、**MultiString** (REG_MULTI_SZ)、**ExpandString** (REG_EXPAND_SZ)。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|Ensure |キーと値が存在するかどうかを示します。 それらが確実に実行されるようにするには、このプロパティを **Present** に設定します。 それらが存在しないことを保証するには、このプロパティを **Absent** に設定します。 既定値は **Present** です。 |
|PsDscRunAsCredential |リソース全体を実行するための資格情報を設定します。 |

> [!NOTE]
> **PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。 詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。

## <a name="example"></a>例

次の例では、"ExampleKey" という名前のキーが **HKEY\_LOCAL\_MACHINE** ハイブに存在していることを確認します。

```powershell
Configuration RegistryTest
{
    Registry RegistryExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Key         = "HKEY_LOCAL_MACHINE\SOFTWARE\ExampleKey"
        ValueName   = "TestValue"
        ValueData   = "TestData"
    }
}
```

> [!NOTE]
> `HKEY_CURRENT_USER` ハイブのレジストリ設定を変更するには、構成がシステムとしてではなく、ユーザーの資格情報を使用して実行されている必要があります。 **PsDscRunAsCredential** プロパティを使用すれば、構成に対してユーザー資格情報を指定できます。 例については、「[ユーザーの資格情報を指定して DSC を実行する](../../../configurations/runAsUser.md)」をご覧ください。
