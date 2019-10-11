---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WindowsProcess リソース
ms.openlocfilehash: e168cdebb04f7ec83b73a537a5f188299f40d8b7
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71952839"
---
# <a name="dsc-windowsprocess-resource"></a>DSC WindowsProcess リソース

> 適用先:Windows PowerShell 4.0、Windows PowerShell 5.x

Windows PowerShell Desired State Configuration (DSC) の **WindowsProcess** リソースは、ターゲット ノードにプロセスを構成するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```Syntax
WindowsProcess [string] #ResourceName
{
    Arguments = [string]
    Path = [string]
    [ Credential = [PSCredential] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ StandardOutputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>プロパティ

|プロパティ |説明 |
|---|---|
|引数 |プロセスに渡す引数の文字列をそのまま示します。 複数の引数を渡す必要がある場合は、そのすべてをこの文字列内に配置します。 |
|パス |プロセスの実行可能ファイルのパス。 これが (完全修飾パスではなく) 実行可能ファイルの名前の場合、DSC リソースではその実行可能ファイルを見つけるために環境 `$env:Path` 変数が検索されます。 このプロパティの値が完全修飾パスの場合、DSC ではそのファイルを見つけるために `$env:Path` 変数は使用されず、パスが存在しない場合はエラーがスローされます。 相対パスは指定できません。 |
|Credential |プロセスを開始するための資格情報を示します。 |
|StandardErrorPath |標準エラーを書き込むディレクトリ パスを示します。 既存のファイルは上書きされます。 |
|StandardInputPath |標準入力の場所を示します。 |
|StandardOutputPath |標準出力の書き込み場所を示します。 既存のファイルは上書きされます。 |
|WorkingDirectory |プロセスの現在の作業ディレクトリとして使用される場所を示します。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|Ensure |プロセスが存在するかどうかを示します。 プロセスの存在を保証するには、このプロパティを **Present** に設定します。 それ以外の場合は、**Absent** に設定します。 既定値は **Present** です。 |
|PsDscRunAsCredential |リソース全体を実行するための資格情報を設定します。 |