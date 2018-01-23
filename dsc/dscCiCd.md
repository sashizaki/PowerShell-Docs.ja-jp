---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC を使用した継続的インテグレーションと継続的配置パイプラインの構築"
ms.openlocfilehash: 5f7583fb93b69bbe4103b34b79b3a859c9cee8a9
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="building-a-continuous-integration-and-continuous-deployment-pipeline-with-dsc"></a>DSC を使用した継続的インテグレーションと継続的配置パイプラインの構築

この例では、PowerShell、DSC、Pester、および Visual Studio Team Foundation Server (TFS) を使用して継続的インテグレーション/継続的配置 (CI/CD) パイプラインを構築する方法を示します。

パイプラインを構築して構成したら、それを使用してDNS サーバーおよび関連付けられたホスト レコードを完全に配置、構成、テストできます。 このプロセスでは、開発環境で使用されるパイプラインの最初の部分をシミュレートします。

自動の CI/CD パイプラインでは、ソフトウェアをより早く、より確実に更新できるため、すべてのコードをテストして、コードの最新のビルドを常に使用可能な状態にします。

## <a name="prerequisites"></a>前提条件

この例を使用するには、以下について理解している必要があります。

- CI/CD の概念。 『[The Release Pipeline Model (リリース パイプライン モデル)](http://aka.ms/thereleasepipelinemodelpdf)』が参考資料として役立ちます。
- [Git](https://git-scm.com/) ソース管理
- [Pester](https://github.com/pester/Pester) テスト フレームワーク
- [Team Foundation Server](https://www.visualstudio.com/tfs/)

## <a name="what-you-will-need"></a>必要なもの

この例をビルドして実行するには、コンピューター複数台と仮想マシン、またはそのいずれかを含む環境が必要です。

### <a name="client"></a>クライアント

この例を設定して実行する、すべての作業を行うコンピューターです。

クライアント コンピューターは Windows コンピューターで、以下がインストールされている必要があります。
- [Git](https://git-scm.com/)
- https://github.com/PowerShell/Demo_CI から複製したローカルの git リポジトリ
- [Visual Studio Code](https://code.visualstudio.com/) などのテキスト エディター

### <a name="tfssrv1"></a>TFSSrv1

TFS サーバーをホストするコンピューター。ビルドを定義してリリースします。
このコンピューターには、[Team Foundation Server 2017](https://www.visualstudio.com/tfs/) がインストールされている必要があります。

### <a name="buildagent"></a>BuildAgent

プロジェクトをビルドする Windows ビルド エージェントを実行するコンピューター。
このコンピューターには、Windows ビルド エージェントがインストールされ実行されている必要があります。
Windows ビルド エージェントをインストールし実行する方法については、「[Deploy an agent on Windows (Windows 上にエージェントを展開する)](https://www.visualstudio.com/en-us/docs/build/actions/agents/v2-windows)」をご覧ください。

また、このコンピューターには `xDnsServer` と `xNetworking` の両方の DSC モジュールをインストールする必要があります。

### <a name="testagent1"></a>TestAgent1

この例において、DSC 構成で DNS サーバーとして構成されるコンピューターです。
このコンピューターでは、[Windows Server 2016](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2016) が実行されている必要があります。

### <a name="testagent2"></a>TestAgent2

この例で構成する Web サイトをホストするコンピューターです。
このコンピューターでは、[Windows Server 2016](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2016) が実行されている必要があります。 

## <a name="add-the-code-to-tfs"></a>TFS にコードを追加する

まず TFS で Git リポジトリを作成し、クライアント コンピューターのローカル リポジトリからコードをインポートします。
クライアント コンピューターに Demo_CI リポジトリを複製済みでない場合は、この時点で次の git コマンドを実行してください。

`git clone https://github.com/PowerShell/Demo_CI`

1. クライアント コンピューターで、Web ブラウザーから TFS サーバーに移動します。
1. TFS で、[新しいチーム プロジェクトを作成](https://www.visualstudio.com/en-us/docs/setup-admin/create-team-project)し、Demo_CI という名前にします。

    **バージョン コントロール** が **Git** に設定されていることを確認します。
1. クライアント コンピューターで、次のコマンドを使用して、いま TFS で作成したリポジトリにリモートを追加します。

    `git remote add tfs <YourTFSRepoURL>`

    ここで `<YourTFSRepoURL>` は、前の手順で作成した TFS リポジトリのクローン URL です。

    この URL の場所がわからない場合は、「[Clone an existing Git repo (既存の Git リポジトリを複製する)](https://www.visualstudio.com/en-us/docs/git/tutorial/clone)」をご覧ください。
1. 次のコマンドで、ローカル リポジトリから TFS リポジトリにコードをプッシュします。

    `git push tfs --all`
1. TFS リポジトリが Demo_CI のコードで設定されます。

>**注:** この例では Git リポジトリの `ci-cd-example` ブランチのコードを使用しています。
>このブランチを TFS プロジェクトの既定ブランチとし、また作成する CI/CD トリガーに必ず指定してください。

## <a name="understanding-the-code"></a>コードを理解する

ビルドおよび配置パイプラインを作成する前に、コードの一部を見て何が起きているかを理解しましょう。
クライアント コンピューターで、使い慣れたテキスト エディターを開き、Demo_CI Git リポジトリのルートに移動します。

### <a name="the-dsc-configuration"></a>DSC 構成

ファイル `DNSServer.ps1` を開きます (ローカルの Demo_CI リポジトリのルート `./InfraDNS/Configs/DNSServer.ps1` から)。

このファイルには、DNS サーバーをセットアップする DSC 構成が含まれています。 その全体は以下の通りです。

```powershell
configuration DNSServer
{
    Import-DscResource -module 'xDnsServer','xNetworking', 'PSDesiredStateConfiguration'

    Node $AllNodes.Where{$_.Role -eq 'DNSServer'}.NodeName
    {
        WindowsFeature DNS
        {
            Ensure  = 'Present'
            Name    = 'DNS'
        }

        xDnsServerPrimaryZone $Node.zone
        {
            Ensure    = 'Present'
            Name      = $Node.Zone
            DependsOn = '[WindowsFeature]DNS'
        }

        foreach ($ARec in $Node.ARecords.keys) {
            xDnsRecord $ARec
            {
                Ensure    = 'Present'
                Name      = $ARec
                Zone      = $Node.Zone
                Type      = 'ARecord'
                Target    = $Node.ARecords[$ARec]
                DependsOn = '[WindowsFeature]DNS'
            }
        }

        foreach ($CName in $Node.CNameRecords.keys) {
            xDnsRecord $CName
            {
                Ensure    = 'Present'
                Name      = $CName
                Zone      = $Node.Zone
                Type      = 'CName'
                Target    = $Node.CNameRecords[$CName]
                DependsOn = '[WindowsFeature]DNS'
            }
        }
    }
}
```

`Node` ステートメントに着目しましょう。

```powershell
Node $AllNodes.Where{$_.Role -eq 'DNSServer'}.NodeName
```

これは、`DevEnv.ps1` スクリプトによって作成された[構成データ](configData.md)内で、`DNSServer` の役割を持つものとして定義されたすべてのノードを検索します。

CI を行う場合、ノード情報は環境によって変わることがあるため、ノードの定義に構成データを使用することは重要です。構成データを使用すれば、構成コードを変更することなく、ノード情報を簡単に変更できます。

最初のリソース ブロックでは、構成で [WindowsFeature](windowsFeatureResource.md) を呼び出し、DNS 機能が有効になっていることを確認します。 それに続くリソース ブロックでは、[xDnsServer](https://github.com/PowerShell/xDnsServer) モジュールからリソースを呼び出し、プライマリ ゾーンと DNS レコードを構成します。

2 つの `xDnsRecord` ブロックが、構成データの配列を反復処理する `foreach` ループ内にラップされていることに注意してください。
繰り返しますが、構成データは `DevEnv.ps1` スクリプトで作成されます。これは次に見ていきます。

### <a name="configuration-data"></a>構成データ

`DevEnv.ps1` ファイル (ローカルの Demo_CI リポジトリのルート `./InfraDNS/DevEnv.ps1` から) は、ハッシュ テーブル内の環境固有の構成データを指定し、そのハッシュ テーブルを `New-DscConfigurationDataDocument` 関数の呼び出しに渡します。これは `DscPipelineTools.psm`(`./Assets/DscPipelineTools/DscPipelineTools.psm1`) で定義されています。

`DevEnv.ps1` ファイルは以下の通りです。

```powershell
param(
    [parameter(Mandatory=$true)]
    [string]
    $OutputPath
)

Import-Module $PSScriptRoot\..\Assets\DscPipelineTools\DscPipelineTools.psd1 -Force

# Define Unit Test Environment
$DevEnvironment = @{
    Name                        = 'DevEnv';
    Roles = @(
        @{  Role                = 'DNSServer';
            VMName              = 'TestAgent1';
            Zone                = 'Contoso.com';
            ARecords            = @{'TFSSrv1'= '10.0.0.10';'Client'='10.0.0.15';'BuildAgent'='10.0.0.30';'TestAgent1'='10.0.0.40';'TestAgent2'='10.0.0.50'};
            CNameRecords        = @{'DNS' = 'TestAgent1.contoso.com'};
        }
    )
}

Return New-DscConfigurationDataDocument -RawEnvData $DevEnvironment -OutputPath $OutputPath
```

`New-DscConfigurationDataDocument` 関数 (`\Assets\DscPipelineTools\DscPipelineTools.psm1` で定義されている) は、`RawEnvData` パラメーターおよび `OtherEnvData` パラメーターとして渡されるハッシュ テーブル (ノードのデータ) および配列 (ノード以外のデータ) から、プログラムで構成データ ドキュメントを作成します。

ここでは、`RawEnvData` パラメーターのみを使用します。

### <a name="the-psake-build-script"></a>psake ビルド スクリプト

`Build.ps1` (Demo_CI リポジトリのルート `./InfraDNS/Build.ps1` から) で定義されている [psake](https://github.com/psake/psake) ビルド スクリプトでは、ビルドの一部となるタスクを定義します。
また、各タスクが依存する他のタスクも定義します。 psake スクリプトは、呼び出されると、指定されたタスク (またはタスクが指定されていない場合は `Default` という名前のタスク) が実行され、すべての依存関係も実行されること (これは再帰的で、依存関係の依存関係を実行する) を確認します。

この例では、`Default` タスクを以下のように定義します。

```powershell
Task Default -depends UnitTests
```

`Default` タスクにはそれ自体の実装はなく、`CompileConfigs` タスクに依存しています。
その結果、タスクの依存関係が連鎖することで、ビルド スクリプトのすべてのタスクが確実に実行されます。

この例では、psake スクリプトは、`Initiate.ps1` ファイル (Demo_CI リポジトリのルートにある) 内の `Invoke-PSake` の呼び出しによって呼び出されます。

```powershell
param(
    [parameter()]
    [ValidateSet('Build','Deploy')]
    [string]
    $fileName
)

#$Error.Clear()

Invoke-PSake $PSScriptRoot\InfraDNS\$fileName.ps1

<#if($Error.count)
{
    Throw "$fileName script failed. Check logs for failure details."
}
#>
```

TFS でこの例のビルド定義を作成する場合、psake スクリプト ファイルをこのスクリプトの `fileName` パラメーターとして提供します。

ビルド スクリプトでは、次のタスクを定義します。

#### <a name="generateenvironmentfiles"></a>GenerateEnvironmentFiles

`DevEnv.ps1` を実行し、構成データ ファイルを生成します。

#### <a name="installmodules"></a>InstallModules

`DNSServer.ps1` 構成に必要なモジュールをインストールします。

#### <a name="scriptanalysis"></a>ScriptAnalysis

[PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) を呼び出します。

#### <a name="unittests"></a>UnitTests

[Pester](https://github.com/pester/Pester/wiki) 単体テストを実行します。

#### <a name="compileconfigs"></a>CompileConfigs

`GenerateEnvironmentFiles` タスクによって生成された構成データを使用して、構成 (`DNSServer.ps1`) をコンパイルして MOF ファイルにします。

#### <a name="clean"></a>Clean

例に使用するフォルダーを作成し、以前の実行によるテスト結果、構成データ ファイル、およびモジュールを削除します。

### <a name="the-psake-deploy-script"></a>psake 配置スクリプト

`Deploy.ps1` (Demo_CI リポジトリのルート `./InfraDNS/Deploy.ps1` から) で定義されている [psake](https://github.com/psake/psake) 配置スクリプトでは、構成を配置して実行するタスクを定義します。

`Deploy.ps1` では以下のタスクを定義します。

#### <a name="deploymodules"></a>DeployModules

`TestAgent1` で PowerShell セッションを開始し、構成に必要な DSC リソースを含むモジュールをインストールします。

#### <a name="deployconfigs"></a>DeployConfigs

[Start-DscConfiguration](/reference/5.1/PSDesiredStateConfiguration/Start-DscConfiguration.md) コマンドレットを呼び出して、`TestAgent1` で構成を実行します。

#### <a name="integrationtests"></a>IntegrationTests

[Pester](https://github.com/pester/Pester/wiki) 統合テストを実行します。

#### <a name="acceptancetests"></a>AcceptanceTests

[Pester](https://github.com/pester/Pester/wiki) 受け入れテストを実行します。

#### <a name="clean"></a>Clean

以前の実行でインストールされたすべてのモジュールを削除し、テスト結果フォルダーが存在することを確認します。

### <a name="test-scripts"></a>テスト スクリプト

受け入れテスト、統合テスト、および単体テストは、`Tests` フォルダー (Demo_CI リポジトリのルート `./InfraDNS/Tests` から) 内のスクリプトで定義されており、それぞれのフォルダーにある `DNSServer.tests.ps1` という名前のファイル内にあります。

テスト スクリプトは [Pester](https://github.com/pester/Pester/wiki) 構文および [PoshSpec](https://github.com/Ticketmaster/poshspec/wiki/Introduction) 構文を使用しています。

#### <a name="unit-tests"></a>単体テスト

単体テストでは、DSC 構成自体をテストして、構成が実行時に期待通りに動作することを確認します。
単体テスト スクリプトは [Pester](https://github.com/pester/Pester/wiki) を使用しています。

#### <a name="integration-tests"></a>統合テスト

統合テストでは、システムの構成をテストして、他のコンポーネントと統合したときにシステムが期待通りに構成されることを確認します。 これらのテストは、DSC で構成した後、ターゲット ノードで実行します。
統合テスト スクリプトは [Pester](https://github.com/pester/Pester/wiki) 構文と [PoshSpec](https://github.com/Ticketmaster/poshspec/wiki/Introduction) 構文を組み合わせて使用しています。

#### <a name="acceptance-tests"></a>受け入れテスト

受け入れテストではシステムをテストして、期待通りに動作することを確認します。
たとえば、Web ページにクエリが実行されたときに、適切な情報が返されるかどうかをテストします。
実際のシナリオをテストするために、これらのテストはターゲット ノードからリモートで実行します。
統合テスト スクリプトは [Pester](https://github.com/pester/Pester/wiki) 構文と [PoshSpec](https://github.com/Ticketmaster/poshspec/wiki/Introduction) 構文を組み合わせて使用しています。

## <a name="define-the-build"></a>ビルドを定義する

コードを TFS にアップロードして内容を確認したので、ビルドを定義しましょう。

ここでは、ビルドに追加するビルド ステップのみを説明します。 TFS でビルド定義を作成する方法の手順については、[ビルド定義の作成とキュー](https://www.visualstudio.com/en-us/docs/build/define/create)に関するページをご覧ください。

新しいビルド定義を作成して (**空**のテンプレートを選択)、"InfraDNS" という名前を付けます。
ビルド定義に以下のステップを追加します。

- PowerShell スクリプト
- テスト結果の公開
- ファイルのコピー
- 成果物の公開

これらのビルド ステップを追加したら、各ステップのプロパティを次のように編集します。

### <a name="powershell-script"></a>PowerShell スクリプト

1. **[型]** プロパティを `File Path` に設定します。
1. **[スクリプト パス]** プロパティを `initiate.ps1` に設定します。
1. **[引数]** プロパティに `-fileName build` を追加します。

このビルド ステップは `initiate.ps1` ファイルを実行し、psake ビルド スクリプトを呼び出します。

### <a name="publish-test-results"></a>テスト結果の公開

1. **[テスト結果の形式]** を `NUnit` に設定します。
1. **[テスト結果ファイル]** を `InfraDNS/Tests/Results/*.xml` に設定します。
1. **[テスト実行のタイトル]** を `Unit` に設定します。
1. **[コントロール オプション]** **[有効]** と **[常に実行する]** が両方とも選択されていることを確認します。

このビルド ステップでは、先ほど確認した Pester スクリプトでの単体テストを実行し、その結果を `InfraDNS/Tests/Results/*.xml` フォルダーに格納します。

### <a name="copy-files"></a>ファイルのコピー

1. 以下の行すべてを、**[内容]** に追加します。

    ```
    initiate.ps1
    **\deploy.ps1
    **\Acceptance\**
    **\Integration\**
    ```

1. **TargetFolder** を `$(Build.ArtifactStagingDirectory)\` に設定します。

このステップでは、ビルドおよびテスト スクリプトをステージング ディレクトリにコピーし、次のステップでビルド成果物として公開できるようにします。

### <a name="publish-artifact"></a>成果物の公開

1. **[発行するためのパス]** を `$(Build.ArtifactStagingDirectory)\` に設定します。
1. **[成果物名]** を `Deploy` に設定します。
1. **[成果物の種類]** を `Server` に設定します。
1. **[コントロール オプション]** で `Enabled` を選択します。

## <a name="enable-continuous-integration"></a>継続的インテグレーションを有効にする

git リポジトリの `ci-cd-example` ブランチに変更がチェックインされたときにプロジェクトがビルドを開始するように、トリガーを設定します。

1. TFS で、**[ビルドとリリース]** タブをクリックします。
1. `DNS Infra` ビルド定義を選択して、**[編集]** をクリックします。
1. **[トリガー]** タブをクリックします。
1. **[継続的インテグレーション (CI)]** を選択して、ブランチのドロップダウン リストで `refs/heads/ci-cd-example` を選択します。
1. **[保存]** をクリックしてから **[OK]** をクリックします。

これで、TFS git リポジトリに何らかの変更があると、自動ビルドがトリガーされます。

## <a name="create-the-release-definition"></a>リリース定義を作成する

リリース定義を作成して、コードのチェックインが行われるたびにプロジェクトが開発環境に展開されるようにしてみましょう。

これを行うには、既に作成したビルド定義 `InfraDNS` に関連付けられた新しいリリース定義を追加します。
必ず **[継続的配置]** を選択し、新しいビルドが完了したらいつでも新しいリリースがトリガーされるようにして 
(「[How to: Work with release definitions」](https://www.visualstudio.com/en-us/docs/build/actions/work-with-release-definitions) (方法: リリース定義の作業) を参照)、次のように構成します。

リリース定義に以下のステップを追加します。

- PowerShell スクリプト
- テスト結果の公開
- テスト結果の公開

ステップを次のように編集します。

### <a name="powershell-script"></a>PowerShell スクリプト

1. **[スクリプト パス]** フィールドを `$(Build.DefinitionName)\Deploy\initiate.ps1"` に設定します。
1. **[引数]** フィールドを `-fileName Deploy` に設定します。

### <a name="first-publish-test-results"></a>1 つめのテスト結果の公開

1. **[テスト結果の形式]** フィールドとして `NUnit` を選択します。
1. **[テスト結果ファイル]** フィールドを `$(Build.DefinitionName)\Deploy\InfraDNS\Tests\Results\Integration*.xml` に設定します。
1. **[テスト実行のタイトル]** を `Integration` に設定します。
1. **[コントロール オプション]** で、**[常に実行する]** を選択します。

### <a name="second-publish-test-results"></a>2 つめのテスト結果の公開

1. **[テスト結果の形式]** フィールドとして `NUnit` を選択します。
1. **[テスト結果ファイル]** フィールドを `$(Build.DefinitionName)\Deploy\InfraDNS\Tests\Results\Acceptance*.xml` に設定します。
1. **[テスト実行のタイトル]** を `Acceptance` に設定します。
1. **[コントロール オプション]** で、**[常に実行する]** を選択します。

## <a name="verify-your-results"></a>結果を確認する

これで、`ci-cd-example` ブランチの変更を TFS にプッシュするたび、新しいビルドが開始されます。
ビルドが正常に完了すると、新しい配置がトリガーされます。

クライアント コンピューターでブラウザーを開いて `www.contoso.com` に移動して、配置結果を確認できます。

## <a name="next-steps"></a>次の手順

この例では、URL `www.contoso.com` が `TestAgent2` に解決されるように DNS サーバー `TestAgent1` を構成していますが、Web サイトの配置は実際には行いません。
それを行うためのスケルトンは、`WebApp` フォルダー下のリポジトリで提供されています。
提供されるスタブを使用して、psake スクリプト、Pester テスト、DSC 構成を作成し、自分の Web サイトを配置することができます。







