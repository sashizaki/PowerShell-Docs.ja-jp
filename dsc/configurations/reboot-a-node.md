---
ms.date: 1/17/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: ノードを再起動する
ms.openlocfilehash: 33ecd98aa62c3dc94a8ff2213fd3e68bf0c05cb7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "55680741"
---
# <a name="reboot-a-node"></a>ノードを再起動する

> [!NOTE]
> このトピックでは、ノードを再起動する方法について説明します。 成功するために再起動するために、 **ActionAfterReboot**と**RebootNodeIfNeeded** LCM 設定が適切に構成する必要があります。
> 詳細については、ローカル構成マネージャー設定を参照してください。[ローカル構成マネージャーを構成する](../managing-nodes/metaConfig.md)、または[ローカル構成マネージャー (v4) の構成](../managing-nodes/metaConfig4.md)します。

ノードを再起動できるから、リソースを使用して、`$global:DSCMachineStatus`フラグ。 このフラグを設定`1`で、`Set-TargetResource`関数はすぐ後にノードを再起動するように LCM、**設定**現在のリソースのメソッド。 このフラグを使用して、 **xPendingReboot**かどうか、再起動が保留中にリソースが検出した DSC の外部でします。

[構成](configurations.md)を再起動するノードを必要とするための手順を実行することがあります。 これは、ことなどがあります。

- Windows: 更新プログラム
- ソフトウェアのインストール
- ファイルの名前を変更します。
- コンピューター名の変更

**XPendingReboot**リソースは、再起動が保留中であるかどうかを特定のコンピューターの場所を確認します。 ノードが、DSC の外部で再起動が必要な場合、 **xPendingReboot**リソース セット、`$global:DSCMachineStatus`フラグを`1`強制的に再起動して、保留中の条件を解決します。

> [!NOTE]
> すべての DSC リソースでこのフラグを設定してノードを再起動するように LCM を指示できます、`Set-TargetResource`関数。 詳細については、次を参照してください。 [MOF を使用したカスタム DSC リソースの記述](../resources/authoringResourceMOF.md)します。

## <a name="syntax"></a>構文

```
xPendingReboot [String] #ResourceName
{
    Name = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [SkipCcmClientSDK = [bool]]
    [SkipComponentBasedServicing = [bool]]
    [SkipPendingComputerRename = [bool]]
    [SkipPendingFileRename = [bool]]
    [SkipWindowsUpdate = [bool]]
}
```

## <a name="properties"></a>プロパティ

| プロパティ | 説明 |
| --- | --- |
| 名前| 必須のパラメーターです、構成内でリソースのインスタンスごとに一意である必要があります。|
| SkipComponentBasedServicing | コンポーネント ベース サービシング コンポーネントによってトリガーされるスキップ再起動します。 |
| SkipWindowsUpdate | Windows Update によってトリガーされるスキップ再起動します。|
| SkipPendingFileRename | 保留中のファイル名の変更の再起動をスキップします。 |
| SkipCcmClientSDK | ConfigMgr クライアントによってトリガーされるスキップ再起動します。 |
| SkipComputerRename | Skip は、コンピューター名の変更によってトリガーされたを再起動します。 |
| PsDscRunAsCredential | V5 でサポートされています。 指定したユーザーとしてリソースを実行します。 |
| DependsOn | このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 詳細については、次を参照してください[DependsOn の使用。](resource-depends-on.md)|

## <a name="example"></a>例

次の例は、Microsoft Exchange を使用してをインストール、 [xExchange](https://github.com/PowerShell/xExchange)リソース。
インストール全体にわたって、 **xPendingReboot**リソースを使用して、ノードを再起動します。

> [!NOTE]
> この例では、フォレストに Exchange サーバーを追加する権限を持つアカウントの資格情報が必要です。 DSC での資格情報の使用の詳細については、次を参照してください[DSC での資格情報の処理。](../configurations/configDataCredentials.md)

```powershell
$ConfigurationData = @{
    AllNodes = @(
        @{
            NodeName                    = '*'
            PSDSCAllowPlainTextPassword = $true
        },
        @{
            NodeName = 'DSCPULL-1'
        }
    )
}

Configuration Example
{
    param
    (
        [Parameter(Mandatory = $true)]
        [System.Management.Automation.PSCredential]
        $ExchangeAdminCredential
    )

    Import-DscResource -Module xExchange
    Import-DscResource -Module xPendingReboot

    Node $AllNodes.NodeName
    {
        # Copy the Exchange setup files locally
        File ExchangeBinaries
        {
            Ensure          = 'Present'
            Type            = 'Directory'
            Recurse         = $true
            SourcePath      = '\\rras-1\Binaries\E15CU6'
            DestinationPath = 'C:\Binaries\E15CU6'
        }

        # Check if a reboot is needed before installing Exchange
        xPendingReboot BeforeExchangeInstall
        {
            Name       = 'BeforeExchangeInstall'
            DependsOn  = '[File]ExchangeBinaries'
        }

        # Do the Exchange install
        xExchInstall InstallExchange
        {
            Path       = 'C:\Binaries\E15CU6\Setup.exe'
            Arguments  = '/mode:Install /role:Mailbox /Iacceptexchangeserverlicenseterms'
            Credential = $ExchangeAdminCredential
            DependsOn  = '[xPendingReboot]BeforeExchangeInstall'
        }

        # See if a reboot is required after installing Exchange
        xPendingReboot AfterExchangeInstall
        {
            Name      = 'AfterExchangeInstall'
            DependsOn = '[xExchInstall]InstallExchange'
        }
    }
}
```

> [!NOTE]
> この例では、再起動を許可し、再起動後に構成を続行する、ローカル構成マネージャーが構成されていることを前提としています。

## <a name="where-to-download"></a>ダウンロードする場所

または、PowerShell ギャラリーを使用して、次の場所では、このトピックで使用されるリソースをダウンロードすることができます。

- [xPendingReboot](https://github.com/PowerShell/xPendingReboot)
- [xExchange](https://github.com/PowerShell/xExchange)
