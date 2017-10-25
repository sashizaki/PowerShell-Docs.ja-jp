---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "Linux 用 DSC の nxFileLine リソース"
ms.openlocfilehash: bde42bbe217fc9acf5a3f2ee0136d30e2b5f2415
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="dsc-for-linux-nxfileline-resource"></a>Linux 用 DSC の nxFileLine リソース

PowerShell Desired State Configuration (DSC) の **nxFileLine** リソースは、Linux ノード上で構成ファイルの行を管理するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```
nxFileLine <string> #ResourceName
{
    FilePath = <string>
    ContainsLine = <string>
    [ DoesNotContainPattern = <string> ]
    [ DependsOn = <string[]> ]

}
```

## <a name="properties"></a>プロパティ

|  プロパティ |  説明 | 
|---|---|
| ファイル パス| ターゲット ノード上の行を管理するファイルの完全パス。| 
| ContainsLine| ファイルに行が存在するようにします。 ファイルに行が存在しない場合、この行がファイルに追加されます。 **ContainsLine** は必須ですが、必要ない場合は空の文字列 (`ContainsLine = ‘’``) に設定することができます。| 
| DoesNotContainPattern| ファイルに存在することができない行の正規表現パターン。 ファイルに存在する行のうち、この正規表現に一致する行は、ファイルから削除されます。| 
| DependsOn | このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの **ID** が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。| 

## <a name="example"></a>例

この例では、**nxFileLine** リソースを使用して、ユーザー monuser が not requiretty に構成されるように `/etc/sudoers` ファイルを構成しています。

```
Import-DSCResource -Module nx 

nxFileLine DoNotRequireTTY
{
   FilePath = “/etc/sudoers”
   ContainsLine = 'Defaults:monuser !requiretty'
   DoesNotContainPattern = "Defaults:monuser[ ]+requiretty"
} 
```

