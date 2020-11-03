---
description: PowerShell ワークフロー機能の概要について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_workflows?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Workflows
ms.openlocfilehash: fbd8ee62b1e9c6969d489c5024c33f5cca883dc6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221848"
---
# <a name="about-workflows"></a>ワークフローについて

## <a name="short-description"></a>簡単な説明

PowerShell ワークフロー機能の概要について説明します。

## <a name="long-description"></a>長い説明

PowerShell ワークフローは、PowerShell に [Windows Workflow Foundation](/dotnet/framework/windows-workflow-foundation) の利点をもたらし、ワークフローの作成と実行を可能にします。

Powershell ワークフローは powershell 3.0 で導入され、PowerShell 5.1 で使用できるようになりました。 PowerShell ワークフローの詳細については、「 [ワークフローガイド](/previous-versions/powershell/scripting/components/workflows-guide) 」と「 [Windows Powershell ワークフローの作成](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)」を参照してください。

## <a name="about-workflows"></a>ワークフローについて

ワークフローは、一連の関連アクティビティで構成されるコマンドです。 通常、これらは長時間にわたって実行され、多数のコンピューターに対してデータを収集し、変更を加えることがあります (多くの場合、異種環境で)。

ワークフローは、XAML、Windows Workflow Foundation で使用される言語、または PowerShell 言語で記述できます。 ワークフローは通常、モジュールにパッケージ化され、ヘルプトピックが含まれます。 詳細については、[XAML の概要 (WPF)](/dotnet/framework/wpf/advanced/xaml-overview-wpf) に関する記事を参照してください。

ワークフローは、自動的に再起動され、一般的な障害から自動的に回復するため、IT 環境において重要です。 ワークフローの処理を中断することなく、ワークフローを実行しているセッションとコンピューターから切断して再接続できます。また、データを失うことなく、ワークフローを透過的に中断および再開できます。 ワークフロー内の各アクティビティは、参照用にログ記録および監査できます。
ワークフローはジョブとして実行でき、PowerShell のスケジュールされたジョブ機能を使用してスケジュールできます。

ワークフローの状態とデータは、ワークフローの開始時と終了時、および指定したポイントで保存または永続化されます。 ワークフローの永続化ポイントは、データベーススナップショットやプログラムチェックポイントと同様に動作し、中断や障害の影響からワークフローを保護します。 ワークフローが障害から復旧できない場合は、永続化されたデータを使用し、最初から広範なワークフローを再実行するのではなく、最後の永続性ポイントから再開できます。

## <a name="workflow-requirements-and-configuration"></a>ワークフローの要件と構成

PowerShell ワークフローの構成は、次の要素で構成されています。

- ワークフローを実行するクライアントコンピューター。
- クライアントコンピューター上またはリモートコンピューター上のワークフローセッション ( **PSSession** )。
- 管理ノード。ワークフローアクティビティの影響を受ける対象コンピューターです。

ワークフローセッションは必須ではありませんが、お勧めします。 **Pssessions** は、PowerShell の堅牢な回復と切断されたセッションの機能を利用して、接続されていないワークフローセッションを復旧できます。 詳細については、「」を参照してください [about_Remote_Disconnected_Sessions](../../Microsoft.PowerShell.Core/About/about_Remote_Disconnected_Sessions.md)

ワークフローセッションが実行されているクライアントコンピューターとコンピューターを管理ノードにすることができるので、すべてのロールを満たす1台のコンピューターでワークフローを実行できます。

クライアントコンピューターと、ワークフローセッションが実行されているコンピューターは、PowerShell 3.0 を実行している必要があります。 Windows Server オペレーティングシステムの Server Core インストールオプションを含む、対象となるすべてのシステムがサポートされます。

コマンドレットを含むワークフローを実行するには、管理対象ノードに Windows PowerShell 2.0 以降がインストールされている必要があります。 ワークフローにコマンドレットが含まれていない場合、管理対象ノードには PowerShell は必要ありません。 PowerShell がインストールされていないコンピューターでは、Windows Management Instrumentation (WMI) および Common Information Model (CIM) コマンドを含むワークフローを実行できます。

## <a name="how-to-get-workflows"></a>ワークフローを取得する方法

ワークフローは通常、モジュールにパッケージ化されます。 ワークフローを含むモジュールをインポートするには、モジュール内の任意のコマンドを使用するか、またはコマンドレットを使用し `Import-Module` ます。
モジュールは、モジュール内のコマンドを初めて使用するときに自動的にインポートされます。

コンピューターにインストールされているモジュール内のワークフローを検索するには、 `Get-Command` コマンドレットの **CommandType** パラメーターを使用します。

```powershell
Get-Command -CommandType Workflow
```

## <a name="how-to-run-workflows"></a>ワークフローを実行する方法

ワークフローを実行するには、次の手順を使用します。

1. 管理ノードがローカルコンピューターの場合、この手順は必要ありません。
   それ以外の場合は、クライアントコンピューターで、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。

   ```powershell
   Start-Process PowerShell -Verb RunAs
   ```

1. ワークフローセッションを実行するコンピューターと、コマンドレットを含むワークフローの影響を受ける管理対象ノードで、PowerShell リモート処理を有効にします。

   この手順は、参加しているコンピューターごとに1回だけ行う必要があります。

   この手順は、コマンドレットを含むワークフローを実行する場合にのみ必要です。 ワークフローセッションがクライアントコンピューターで実行されている場合、または PowerShell 3.0 を実行している管理対象ノード上で実行されている場合を除き、クライアントコンピューターでリモート処理を有効にする必要はありません。

   リモート処理を有効にするには、コマンドレットを使用し `Enable-PSRemoting` ます。

   ```powershell
   Enable-PSRemoting -Force
   ```

   リモート処理を有効にするには、 **[スクリプトの実行を有効に** する] グループポリシー設定を使用します。 詳細については、「 [about_Group_Policy_Settings](../../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md) 」および「 [about_Execution_Policies](../../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)」を参照してください。

1. またはコマンドレットを使用して、 `New-PSWorkflowSession` `New-PSSession` ワークフローセッションを作成します。

   コマンドレットでは、 `New-PSWorkflowSession` 対象のコンピューターで組み込みの **Microsoft. PowerShell ワークフロー** セッション構成を使用するセッションを開始します。 このセッション構成には、スクリプト、種類およびフォーマットファイル、およびワークフロー用に設計されたオプションが含まれています。

   または、コマンドレットを使用し `New-PSSession` ます。 ConfigurationName **のセッション構成** を指定するには、 **ConfigurationName** パラメーターを使用します。 このコマンドは、コマンドレットを使用した場合と同じです `New-PSWorkflowSession` 。

   別の方法として、コマンドレットを使用することも `New-PSSession` できます。 ConfigurationName **のセッション構成** を指定するには、 **ConfigurationName** パラメーターを使用します。

   ローカルコンピューターの場合:

   ```powershell
   $ws = New-PSWorkflowSession
   ```

   リモートコンピューターの場合:

   ```powershell
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

   ワークフローセッションコンピューターの管理者である場合は、コマンドレットを使用して、 `New-PSWorkflowExecutionOption` ワークフローセッション構成のカスタムオプション設定を作成できます。 また、コマンドレットを使用して、 `Set-PSSessionConfiguration` セッション構成を変更します。

   ```powershell
   $sto = New-PSWorkflowExecutionOption -MaxConnectedSessions 150
   Invoke-Command -ComputerName Server01 `
   {Set-PSSessionConfiguration Microsoft.PowerShell.Workflow `
   -SessionTypeOption $Using:sto}
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

1. ワークフローセッションでワークフローを実行します。 管理対象ノードの名前 (対象コンピューター) を指定するには、 **PSComputerName** workflow 共通パラメーターを使用します。

   次の例では、" **Test-workflow** " という名前のワークフローを実行します。

   ここで、管理ノードは、ワークフローセッションをホストするコンピューターです。

   ```powershell
   Invoke-Command -Session $ws {Test-Workflow}
   ```

   管理対象ノードがリモートコンピューターの場合。

   ```powershell
   Invoke-Command -Session $ws{
   Test-Workflow -PSComputerName Server01, Server02 }
   ```

   次の例では、数百のコンピューターで **テストワークフロー** を実行します。 `Get-Content`コマンドレットは、テキストファイルからコンピューター名を取得し、 `$Servers` ローカルコンピューター上の変数に保存します。

   `Invoke-Command` スコープ修飾子を使用して、 `$Using` `$Servers` ローカルセッションで変数を定義します。 スコープ修飾子の詳細については `$Using` 、「 [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)」を参照してください。

   ```powershell
   $Servers = Get-Content Servers.txt
   Invoke-Command -Session $ws {Test-Workflow -PSComputerName $Using:Servers }
   ```

## <a name="using-workflow-common-parameters"></a>ワークフロー共通パラメーターの使用

ワークフロー共通パラメーターは、PowerShell がすべてのワークフローに自動的に追加するパラメーターのセットです。 PowerShell では、ワークフローでコマンドレット **バインド** 属性が使用されていない場合でも、すべてのワークフローにコマンドレットの共通パラメーターが追加されます。

たとえば、次のワークフローではパラメーターが定義されていません。 ただし、ワークフローを実行すると、 **commonparameters** と **workflowcommonparameters** の両方が含まれます。

```powershell
workflow Test-Workflow {Get-Process}
Get-Command Test-Workflow -Syntax
```

```powershell
Test-Workflow [<WorkflowCommonParameters>] [<CommonParameters>]
```

ワークフロー共通パラメーターには、ワークフローを実行するために必要ないくつかのパラメーターが含まれています。 たとえば、 **PSComputerName** common パラメーターは、ワークフローが影響するマネージノードを指定します。

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02
}
```

**Pspersist** ワークフロー共通パラメーターは、ワークフローデータを永続化するタイミングを決定します。 永続化ポイントを定義しないワークフローに、アクティビティ間の永続化ポイントを追加することができます。

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPersist:$True
}
```

その他のワークフロー共通パラメーターを使用すると、管理対象ノードへのリモート接続の特性を指定できます。 これらの名前と機能は、などのリモート処理コマンドレットのパラメーターに似てい `Invoke-Command` ます。

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPort 443
}
```

ワークフローセッションの接続を定義するリモート処理パラメーターは、管理対象ノードへの接続を定義する、 **PS プレフィックス** が付けられたワークフロー共通パラメーターから区別するように注意してください。

```powershell
$ws = New-PSSession -ComputerName Server01 -ConfigurationName Microsoft.PowerShell.Workflow

Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSConfigurationName Microsoft.PowerShell.Workflow
}
```

ワークフロー共通パラメーターの中には、ワークフローに固有のものがあります。たとえば、 **PSParameterCollection** パラメーターを使用すると、さまざまなリモートノードに異なるワークフロー共通パラメーター値を指定できます。 ワークフロー共通パラメーターの一覧と説明については、「 [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Invoke-AsWorkflow](xref:PSWorkflowUtility.Invoke-AsWorkflow)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Psworkflow](xref:PSWorkflow) コマンドレット

[ワークフロー ガイド](/previous-versions/powershell/scripting/components/workflows-guide)

[Windows PowerShell ワークフローを記述する](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
