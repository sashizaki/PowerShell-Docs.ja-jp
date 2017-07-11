---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "Linux 用 DSC の nxPackage リソース"
ms.openlocfilehash: 11019b1cd12f23b0b498b7cb9a06e02c46c3c279
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="dsc-for-linux-nxpackage-resource" class="xliff"></a>

# Linux 用 DSC の nxPackage リソース

PowerShell Desired State Configuration (DSC) の **nxPackage** リソースは、Linux ノード上でパッケージを管理するためのメカニズムを備えています。

<a id="syntax" class="xliff"></a>

## 構文

```
nxPackage <string> #ResourceName
{
    Name = <string>
    [ Ensure = <string> { Absent | Present }  ]
    [ PackageManager = <string> { Yum | Apt | Zypper } ]
    [ PackageGroup = <bool>]
    [ Arguments = <string> ]
    [ ReturnCode = <uint32> ]
    [ LogPath = <string> ]
    [ DependsOn = <string[]> ]
    
}
```

<a id="properties" class="xliff"></a>

## プロパティ

|  プロパティ |  説明 | 
|---|---|
| 名前| 特定の状態を保証するパッケージの名前。| 
| Ensure| パッケージが存在するかどうかを決定します。 パッケージが存在することを保証するには、このプロパティを "Present" に設定します。 パッケージが存在しないことを保証するには、"Absent" に設定します。 既定値は "Present" です。|  
| PackageManager| サポートされている値は、"yum"、"apt"、および "zypper" です。 パッケージのインストール時に使用するパッケージ マネージャーを指定します。 **FilePath** を指定した場合、その指定したパスを使用してパッケージがインストールされます。 それ以外の場合、パッケージ マネージャーを使用して、事前に構成されているリポジトリからパッケージがインストールされます。 **PackageManager** も **FilePath** も指定しない場合は、システムの既定のパッケージ マネージャーが使用されます。| 
| ファイル パス| パッケージが存在するファイル パス| 
| PackageGroup| **$true** の場合、**Name** は **PackageManager** で使用されるパッケージ グループの名前であるものとみなされます。 **PacakgeGroup** は、**FilePath** を指定したときには使用できません。| 
| 引数| 指定されたとおりにパッケージに渡される引数の文字列。| 
| ReturnCode| 想定されるリターン コード。 実際のリターン コードがここで指定される想定される値と一致しない場合、構成はエラーを返します。| 
| DependsOn | このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの **ID** が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。| 

<a id="example" class="xliff"></a>

## 例

次の例では、"Yum" パッケージ マネージャーを使用して、Linux コンピューターに "httpd" という名前のパッケージがインストールされるようにしています。

```
Import-DSCResource -Module nx 

Node $node {
nxPackage httpd
{
    Name = "httpd"
    Ensure = "Present"
    PackageManager = "Yum"
}
}
```

