---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Package リソース
ms.openlocfilehash: 9285df71a303c9a53dd50d450272575a64e962e7
ms.sourcegitcommit: c3f1a83b59484651119630f3089aa51b6e7d4c3c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2018
ms.locfileid: "39268672"
---
# <a name="dsc-package-resource"></a>DSC Package リソース

_適用対象: Windows PowerShell 4.0、Windows PowerShell 5.0_

Windows PowerShell Desired State Configuration (DSC) の **Package** リソースは、Windows インストーラーや setup.exe パッケージなど、ターゲット ノードでパッケージをインストールまたはアンインストールするメカニズムを備えています。

## <a name="syntax"></a>構文

```
Package [string] #ResourceName
{
    Name = [string]
    Path = [string]
    ProductId = [string]
    [ Arguments = [string] ]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ ReturnCode = [UInt32[]] ]
}
```

## <a name="properties"></a>プロパティ

| プロパティ | 説明 |
| --- | --- |
| 名前| 特定の状態を保証するパッケージの名前を示します。|
| パス| パッケージが存在するパスを示します。|
| ProductId| パッケージを一意に識別する製品 ID を示します。|
| 引数| 指定されたとおりにパッケージに渡される引数の文字列を一覧表示します。|
| Credential| リモート ソースのパッケージへのアクセスを提供します。 このプロパティは、パッケージのインストールには使用されません。 パッケージは常に、ローカル システムにインストールされます。|
| Ensure| パッケージがインストールされるかどうかを示します。 このプロパティを "Absent" に設定すると、パッケージはインストールされません (またはパッケージがインストールされている場合はアンインストールされます)。 パッケージがインストールされるようにするには、"Present" に設定します (既定値)。|
| LogPath| プロバイダーがパッケージをインストールまたはアンインストールするためのログ ファイルを保存する場所の完全パスを示します。|
| DependsOn | このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。|
| ReturnCode| 想定されるリターン コードを示します。 実際のリターン コードがここで指定される想定される値と一致しない場合、構成はエラーを返します。|

## <a name="example"></a>例

この例では、指定されたパスに配置され、指定された製品 ID が割り当てられている .msi インストーラーを実行します。

```powershell
Configuration PackageTest
{
    Package PackageExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Path        = "$Env:SystemDrive\TestFolder\TestProject.msi"
        Name        = "TestPackage"
        ProductId   = "ACDDCDAF-80C6-41E6-A1B9-8ABD8A05027E"
    }
}
```