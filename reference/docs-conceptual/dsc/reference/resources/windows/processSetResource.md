---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC ProcessSet リソース
ms.openlocfilehash: 72925d3a9516f5c0040427773a3b1d66034667bb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953129"
---
# <a name="dsc-processset-resource"></a>DSC ProcessSet リソース

> 適用先:Windows PowerShell 5.x

Windows PowerShell Desired State Configuration (DSC) の **ProcessSet** リソースは、ターゲット ノードにプロセスを構成するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```Syntax
ProcessSet [string] #ResourceName
{
    Path = [string]
    [ Credential = [PSCredential] ]
    [ StandardOutputPath = [string] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>プロパティ

|プロパティ |説明 |
|---|---|
|パス |プロセスの実行可能ファイルのパス。 実行可能ファイルの名前がある場合 (完全修飾パスではない)、DSC リソースは環境 `$env:Path` 変数を検索し、ファイルを見つけます。 このプロパティの値が完全修飾パスの場合、DSC は `$env:Path` 環境変数でファイルを探すことはせず、パスが存在しない場合はエラーをスローします。 相対パスは指定できません。 |
|Credential |プロセスを開始するための資格情報を示します。 |
|StandardErrorPath |プロセスにより標準エラーが書き込まれるパス。 既存のファイルは上書きされます。 |
|StandardInputPath |プロセスが標準入力を受け取るとき、その発信元となるストリーム。 |
|StandardOutputPath |プロセスにより標準出力が書き込まれるファイルのパス。 既存のファイルは上書きされます。 |
|WorkingDirectory |プロセスの現在の作業ディレクトリとして使用されている場所。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|Ensure |プロセスが存在するかどうかを指定します。 プロセスの存在を保証するには、このプロパティを **Present** に設定します。 それ以外の場合は、**Absent** に設定します。 既定値は **Present** です。 |
|PsDscRunAsCredential |リソース全体を実行するための資格情報を設定します。 |

> [!NOTE]
> **PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。 詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。