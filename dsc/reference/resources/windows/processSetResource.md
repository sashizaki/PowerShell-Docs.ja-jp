---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC ProcessSet リソース
ms.openlocfilehash: 91a2d5b562864addcb8e11062916d291448bbf57
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077111"
---
# <a name="dsc-windowsprocess-resource"></a>DSC WindowsProcess リソース

_適用先:Windows PowerShell 5.0_

Windows PowerShell Desired State Configuration (DSC) の **ProcessSet** リソースは、ターゲット ノードにプロセスを構成するためのメカニズムを備えています。 このリソースは[複合リソース](../../../resources/authoringResourceComposite.md)であり、`GroupName` パラメーターに指定されているグループごとに [WindowsProcess リソース](windowsProcessResource.md)を呼び出します。

## <a name="syntax"></a>構文

```
WindowsProcess [string] #ResourceName
{
    Arguments = [string]
    Path = [string]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ StandardOutputPath = [string] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a>プロパティ

| プロパティ | 説明 |
| --- | --- |
| 引数| 現状のままプロセスに渡す引数の文字列。 複数の引数を渡す必要がある場合は、そのすべてをこの文字列内に配置します。|
| パス| プロセスの実行可能ファイルへのパス。 実行可能ファイルの名前がある場合 (完全修飾パスではない)、DSC リソースは環境**パス**変数 (`$env:Path`) を検索し、ファイルを見つけます。 このプロパティの値が完全修飾パスの場合、DSC は**パス**環境変数でファイルを探すことはせず、パスが存在しない場合はエラーをスローします。 相対パスは指定できません。|
| Credential| プロセスを開始するための資格情報を示します。|
| Ensure| プロセスが存在するかどうかを指定します。 プロセスが存在することを保証するには、このプロパティを "Present" に設定します。 それ以外の場合は、"Absent" に設定します。 既定は "Present" です。|
| StandardErrorPath| プロセスにより標準エラーが書き込まれるパス。 既存のファイルは上書きされます。|
| StandardInputPath| プロセスが標準入力を受け取るとき、その発信元となるストリーム。|
| StandardOutputPath| プロセスにより標準出力が書き込まれるファイルのパス。 既存のファイルは上書きされます。|
| WorkingDirectory| プロセスの現在の作業ディレクトリとして使用されている場所。|
| DependsOn | このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **_ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。|
