---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "Linux 用 DSC の nxArchive リソース"
ms.openlocfilehash: da647432e14d2a4a3ceb2a36c7dee2dbfd350116
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="dsc-for-linux-nxarchive-resource" class="xliff"></a>

# Linux 用 DSC の nxArchive リソース

PowerShell Desired State Configuration (DSC) の **nxArchive** リソースは、Linux ノード上の特定のパスでアーカイブ (.tar、.zip) ファイルをアンパックするメカニズムを備えています。

<a id="syntax" class="xliff"></a>

## 構文

```
nxArchive <string> #ResourceName
{
    SourcePath = <string>
    DestinationPath = <string>
    [ Checksum = <string> { ctime | mtime | md5 }  ]
    [ Force = <bool> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

<a id="properties" class="xliff"></a>

## プロパティ

|  プロパティ |  説明 | 
|---|---|
| SourcePath| アーカイブ ファイルのソース パスを指定します。 これは .tar、.zip、または .tar.gz ファイルである必要があります。 | 
| DestinationPath| アーカイブ コンテンツが抽出されることを保証する場所を指定します。| 
| チェックサム| ソース アーカイブが更新されたかどうかを確認するときに使用するタイプを定義します。 値は、"ctime"、"mtime"、または "md5" です。 既定値は "md5" です。| 
| Force| 特定のファイル操作 (ファイルの上書き、空でないディレクトリの削除など) によって、エラーが発生します。 **Force** プロパティを使用すると、このようなエラーが上書きされます。 既定値は **$false** です。| 
| DependsOn | このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの **ID** が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。| 
| Ensure| アーカイブのコンテンツが **Destination** に存在するかどうかを決定します。 コンテンツが存在することを保証するには、このプロパティを "Present" に設定します。 コンテンツが存在しないことを保証するには、"Absent" に設定します。 既定値は "Present" です。| 

<a id="example" class="xliff"></a>

## 例

次の例は、**nxArchive** リソースを使用して、`website.tar` というアーカイブ ファイルのコンテンツが指定した宛先に存在し、抽出されていることを保証する方法を示します。

```
Import-DSCResource -Module nx 

nxFile SyncArchiveFromWeb
{
   Ensure = "Present"
   SourcePath = “http://release.contoso.com/releases/website.tar”
   DestinationPath = "/usr/release/staging/website.tar"
   Type = "File"
   Checksum = “mtime”
}

nxArchive SyncWebDir
{
   SourcePath = “/usr/release/staging/website.tar”
   DestinationPath = “/usr/local/apache2/htdocs/”
   Force = $false
   DependsOn = "[nxFile]SyncArchiveFromWeb"
} 
```

