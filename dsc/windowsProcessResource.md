---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WindowsProcess リソース
ms.openlocfilehash: cee93ab283ded407d6e032161125aa6d6ac98827
ms.sourcegitcommit: c3f1a83b59484651119630f3089aa51b6e7d4c3c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2018
ms.locfileid: "39267959"
---
# <a name="dsc-windowsprocess-resource"></a>DSC WindowsProcess リソース

_適用対象: Windows PowerShell 4.0、Windows PowerShell 5.0_

Windows PowerShell Desired State Configuration (DSC) の **WindowsProcess** リソースは、ターゲット ノードにプロセスを構成するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```
WindowsProcess [string] #ResourceName
{
    Arguments = [string]
    Path = [string]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ DependsOn = [string[]] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ StandardOutputPath = [string] ]
    [ WorkingDirectory = [string] ]
}
```

## <a name="properties"></a>プロパティ

| プロパティ | 説明 |
| --- | --- |
| 引数| プロセスに渡す引数の文字列をそのまま示します。 複数の引数を渡す必要がある場合は、そのすべてをこの文字列内に配置します。|
| パス| プロセスの実行可能ファイルのパス。 これが実行可能ファイルの名前の場合 (完全修飾パスではない)、DSC リソースは環境**パス**変数 (`$env:Path`) を検索し、ファイルを見つけます。 このプロパティの値が完全修飾パスの場合、DSC は**パス**環境変数でファイルを探すことはせず、パスが存在しない場合はエラーをスローします。 相対パスは指定できません。|
| Credential| プロセスを開始するための資格情報を示します。|
| Ensure| プロセスが存在するかどうかを示します。 プロセスが存在することを保証するには、このプロパティを "Present" に設定します。 それ以外の場合は、"Absent" に設定します。 既定は "Present" です。|
| DependsOn | このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。|
| StandardErrorPath| 標準エラーを書き込むディレクトリ パスを示します。 既存のファイルは上書きされます。|
| StandardInputPath| 標準入力の場所を示します。|
| StandardOutputPath| 標準出力の書き込み場所を示します。 既存のファイルは上書きされます。|
| WorkingDirectory| プロセスの現在の作業ディレクトリとして使用される場所を示します。|