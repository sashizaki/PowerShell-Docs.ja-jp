---
ms.date: 07/16/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WindowsOptionalFeatureSet リソース
ms.openlocfilehash: e4f88f1cae6d7ddb3596ab4f27eb3766259f1a31
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464164"
---
# <a name="dsc-windowsoptionalfeatureset-resource"></a>DSC WindowsOptionalFeatureSet リソース

> 適用先:Windows PowerShell 5.x

Windows PowerShell Desired State Configuration (DSC) の **WindowsOptionalFeatureSet** リソースは、オプション機能をターゲット ノードで有効にするためのメカニズムを備えています。 このリソースは[複合リソース](../../../resources/authoringResourceComposite.md)であり、**Name** プロパティに指定されている機能ごとに [WindowsOptionalFeature リソース](windowsOptionalFeatureResource.md)を呼び出します。

Windows のオプション機能の数を同じ状態に構成するときにこのリソースを使用します。

## <a name="syntax"></a>構文

```Syntax
WindowsOptionalFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogPath = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Properties

|プロパティ |説明 |
|---|---|
|名前 |有効または無効にする機能の名前を示します。 |
|NoWindowsUpdateCheck |機能を有効にするソース ファイルを検索するとき、DISM が Windows Update (WU) を確認するかどうかを指定します。 `$true` の場合、DISM は WU に接続しません。 |
|RemoveFilesOnDisable |**Ensure** が **Absent** に設定されているときに、`$true` に設定すると、その機能に関連付けられているすべてのファイルが削除されます。 |
|LogLevel |ログに表示される最大の出力レベル。 有効な値は**ErrorsOnly**、**ErrorsAndWarning**、**ErrorsAndWarningAndInformation** です。 |
|LogPath |リソース プロバイダーの操作を記録するログ ファイルへのパス。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|Ensure |機能が有効化かどうかを指定します。 機能を確実に有効にするには、このプロパティを **Enable** に設定します。 機能を確実に無効にするには、このプロパティを **Disable** に設定します。 既定値は **Enable** です。 |
|PsDscRunAsCredential |リソース全体を実行するための資格情報を設定します。 |

> [!NOTE]
> **PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。 詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。
