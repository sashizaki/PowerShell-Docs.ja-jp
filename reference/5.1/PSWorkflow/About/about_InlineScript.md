---
description: '`InlineScript`ワークフローで PowerShell コマンドを実行するアクティビティについて説明します。'
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_inlinescript?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_InlineScript
ms.openlocfilehash: 2eaeb02c6441865551b586e27a39c4000826752b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221904"
---
# <a name="about-inlinescript"></a>InlineScript の概要

## <a name="short-description"></a>簡単な説明

`InlineScript`ワークフローで PowerShell コマンドを実行するアクティビティについて説明します。

## <a name="long-description"></a>長い説明

アクティビティは、 `InlineScript` 共有 PowerShell セッションのワークフローでコマンドを実行します。 `InlineScript` は、ワークフローでのみ有効です。

## <a name="syntax"></a>構文

```
InlineScript {<script block>} <ActivityCommonParameters>
```

## <a name="detailed-description"></a>詳しい説明

アクティビティは、 `InlineScript` 共有 PowerShell セッションでコマンドを実行します。 これをワークフローに含めて、ワークフロー内で有効ではないデータとコマンドを共有するコマンドを実行できます。

スクリプトブロックには、 `InlineScript` すべての有効な PowerShell コマンドと式を含めることができます。 スクリプトブロック内のコマンドと式は同じセッションで実行されるので、インポートされた `InlineScript` モジュールと変数の値を含むすべての状態とデータを共有します。

アクティビティは、 `InlineScript` ワークフローまたは入れ子になったワークフロー内の任意の場所に配置できます。これには、ループまたは制御ステートメントの内部、並列またはシーケンスのスクリプトブロックが含まれます。

`InlineScript`アクティビティには、 **pspersist** などのアクティビティ共通パラメーターがあります。 ただし、スクリプトブロック内のコマンドと式には、 `InlineScript` チェックポイント処理、永続化、ワークフローまたはアクティビティ共通パラメーターなどのワークフロー機能がありません。 詳細については、「 [about_ActivityCommonParameters](about_ActivityCommonParameters.md)」を参照してください。

## <a name="inlinescript-variables"></a>InlineScript 変数

既定では、ワークフローで定義されている変数は、スクリプトブロック内のコマンドには表示されません `InlineScript` 。 ワークフロー変数がに表示されるようにするには、 `InlineScript` スコープ修飾子を使用し `$Using` ます。 `$Using`スコープ修飾子は、の変数ごとに1回だけ指定する必要が `InlineScript` あります。

スコープ修飾子の詳細については `$Using` 、「 [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)」を参照してください。

次の例では、 `$Using` スコープ修飾子によって、 `$a` 最上位レベルのワークフロー変数の値をスクリプトブロック内のコマンドで使用できるようにして `InlineScript` います。

```powershell
workflow Test-Workflow {
  $a = 3

  ## Without $Using, the $a workflow variable isn't visible
  ## in inline script.
  InlineScript {"Inline A0 = $a"}

  ## $Using imports the variable and its current value.
  InlineScript {"Inline A1 = $Using:a"}
}

Test-Workflow
```

```output
Inline A0 =
Inline A1 = 3
```

## <a name="returning-variables-in-inlinescript"></a>InlineScript で変数を返す

`InlineScript` コマンドは、ワークフロースコープからインポートされた変数の値を変更できますが、変更はワークフロースコープには表示されません。 表示されるようにするには、次の例に示すように、変更した値をワークフロー スコープに返します。

```powershell
workflow Test-Workflow {
  $a = 3

  ##  Changes to the InlineScript variable value don't
  ##  change the workflow variable.
  InlineScript {
    $a = $Using:a+1;
    "Inline A = $a"
  }
  "Workflow A = $a"

  ##  To change the variable in workflow scope, return the
  ##  new value.
  $a = InlineScript {$b = $Using:a+1; $b}
  "Workflow New A = $a"
}

Test-Workflow
```

```output
Inline A = 4
Workflow A = 3
Workflow New A = 4
```

> [!NOTE]
> スコープ修飾子を持つステートメントは、 `$Using` スクリプトブロック内の変数を使用する前に記述する必要があり `InlineScript` ます。

## <a name="running-in-process"></a>インプロセスでの実行

信頼性を高めるために、スクリプトブロック内のコマンドは、 `InlineScript` ワークフローを実行するプロセスとは別に、独自のプロセスで実行され、その出力がワークフロープロセスに返されます。

ワークフロープロセスでアクティビティを実行するように PowerShell に指示するには、 `InlineScript` `InlineScript` コマンドレットを使用してなど、セッション構成の **OutOfProcessActivity** プロパティから値を削除し `New-PSWorkflowExecutionOption` ます。

### <a name="example"></a>例

次のワークフローのには、 `InlineScript` PowerShell で有効であるものの、ワークフローでは有効ではないコマンドが含まれています。 たとえば、 `New-Object` コマンドレットには、 **ComObject** パラメーターを指定します。

```powershell
workflow Test-Workflow
{
  $ie = InlineScript {
    $ie = New-Object -ComObject InternetExplorer.Application -Property @{navigate2="www.microsoft.com"}

    $ie.Visible = $true
  }

  $ie
}

Test-Workflow
```

## <a name="see-also"></a>関連項目

[about_ActivityCommonParameters](about_ActivityCommonParameters.md)

[about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)

[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)

[Psworkflow](xref:PSWorkflow) コマンドレット

[ワークフロー ガイド](/previous-versions/powershell/scripting/components/workflows-guide)

[Windows PowerShell ワークフローを記述する](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
