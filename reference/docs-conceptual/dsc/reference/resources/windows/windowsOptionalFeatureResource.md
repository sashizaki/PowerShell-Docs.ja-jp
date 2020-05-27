---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WindowsOptionalFeature リソース
ms.openlocfilehash: bca6294db74c92a2c1940cfbe00305542a1c5d19
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83565368"
---
# <a name="dsc-windowsoptionalfeature-resource"></a>DSC WindowsOptionalFeature リソース

> 適用先:Windows PowerShell 5.x

Windows PowerShell Desired State Configuration (DSC) の **WindowsOptionalFeature** リソースは、オプション機能をターゲット ノードで有効にするためのメカニズムを備えています。

## <a name="syntax"></a>構文

```Syntax
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string]
    [ Source = [string[]] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Properties

|プロパティ |説明 |
|---|---|
|名前 |有効または無効にする機能の名前を示します。 |
|source |実装されていません。 |
|NoWindowsUpdateCheck |機能を有効にするソース ファイルを検索するとき、DISM が Windows Update (WU) を確認するかどうかを指定します。 `$true` の場合、DISM は WU に接続しません。 |
|RemoveFilesOnDisable |**Ensure** が **Absent** に設定されているときに、`$true` に設定すると、その機能に関連付けられているすべてのファイルが削除されます。 |
|LogLevel |ログに表示される最大の出力レベル。 有効な値は**ErrorsOnly**、**ErrorsAndWarning**、**ErrorsAndWarningAndInformation** です。 |
|LogPath |リソース プロバイダーの操作を記録するログ ファイルへのパス。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|Ensure |機能が有効かどうかを指定します。 機能を確実に有効にするには、このプロパティを _Enable_ に設定します。 機能を確実に無効にするには、このプロパティを _Disable_ に設定します。 既定値は _Enable_ です。 |
|PsDscRunAsCredential |リソース全体を実行するための資格情報を設定します。 |

> [!NOTE]
> **PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。 詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。
