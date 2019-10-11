---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC 環境リソース
ms.openlocfilehash: d6d3b4a2086be28fbfa2bf200acef9b13b7b7825
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954719"
---
# <a name="dsc-environment-resource"></a>DSC 環境リソース

> 適用先:Windows PowerShell 4.0、Windows PowerShell 5.x

Windows PowerShell Desired State Configuration (DSC) の **Environment** リソースは、システム環境変数を管理するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```Syntax
Environment [string] #ResourceName
{
    Name = [string]
    [ Path = [bool] ]
    [ Value = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>プロパティ

|プロパティ |説明 |
|---|---|
|名前 |特定の状態を保証する環境変数の名前を示します。 |
|パス |構成されている環境変数を定義します。 変数が **Path** 変数である場合は、このプロパティを `$true` に設定します。それ以外の場合は、`$false` に設定します。 既定値は `$false` です。 構成されている変数が **Path** 変数である場合は、**Value** プロパティによって提供される値が既存の値に追加されます。 |
|値 |環境変数に割り当てる値。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|Ensure |変数が存在するかどうかを示します。 環境変数が存在しない場合に作成する場合、または環境変数が既に存在する場合にその値が **Value** プロパティによって提供される値と一致することを保証するには、このプロパティを **Present** に設定します。 環境変数が存在する場合に削除するには、**Absent** に設定します。 |
|PsDscRunAsCredential |リソース全体を実行するための資格情報を設定します。 |

> [!NOTE]
> **PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。 詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。

## <a name="example"></a>例

次の例では、TestEnvironmentVariable が存在し、その値が _TestValue_ であることを保証します。 この環境変数が存在しない場合は、作成されます。

```powershell
Environment EnvironmentExample
{
    Ensure = "Present"  # You can also set Ensure to "Absent"
    Name = "TestEnvironmentVariable"
    Value = "TestValue"
}
```