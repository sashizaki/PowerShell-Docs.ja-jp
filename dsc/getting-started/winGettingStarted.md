---
ms.date: 08/15/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: Windows 用 Desired State Configuration (DSC) の概要
ms.openlocfilehash: a4f9db481afda65fc4ac5e553230dbba3037ac9a
ms.sourcegitcommit: 5a004064f33acc0145ccd414535763e95f998c89
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988888"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-windows"></a>Windows 用 Desired State Configuration (DSC) の概要

このトピックでは、Windows 用 PowerShell Desired State Configuration (DSC) の使用を開始する方法について説明します。
DSC に関する一般的な情報については、「[Windows PowerShell Desired State Configuration の概要](../overview/overview.md)」を参照してください。

## <a name="supported-windows-operation-system-versions"></a>サポートされている Windows オペレーティング システムのバージョン

次のバージョンがサポートされています。

- Windows Server 2019
- Windows Server 2016
- Windows Server 2012R2
- Windows Server 2012
- Windows Server 2008 R2 SP1
- Windows 10
- Windows 8.1
- Windows 7

[Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) のスタンドアロン製品 SKU には Desired State Configuraion の実装が含まれていないため、これを PowerShell DSC または Azure Automation State Configuration によって管理することはできません。

## <a name="installing-dsc"></a>DSC のインストール

PowerShell Desired State Configuration は Windows に含まれており、Windows Management Framework を通じて更新されます。
最新バージョンは [Windows Management Framework 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616) です。

> [!NOTE]
> DSC を使ってコンピューターを管理するために、Windows Server の 'DSC-Service' 機能を有効にする必要はありません。
> この機能は、Windows プル サーバー インスタンスを構築する場合にのみ必要です。

## <a name="using-dsc-for-windows"></a>Windows 用 DSC の使用

次のセクションでは、Windows コンピューター上で DSC 構成を作成し、実行する方法を説明します。

### <a name="creating-a-configuration-mof-document"></a>構成 MOF ドキュメントの作成

構成を作成するには、Windows PowerShell 構成キーワードを使用します。
以下の手順では、Windows PowerShell を使って構成ドキュメントを作成する方法について説明します。

#### <a name="define-a-configuration-and-generate-the-configuration-document"></a>構成を定義し、構成ドキュメントを生成します。

```powershell
Configuration EnvironmentVariable_Path
{
    param ()

    Import-DscResource -ModuleName 'PSDscResources'

    Node localhost
    {
        Environment CreatePathEnvironmentVariable
        {
            Name = 'TestPathEnvironmentVariable'
            Value = 'TestValue'
            Ensure = 'Present'
            Path = $true
            Target = @('Process', 'Machine')
        }
    }
}

EnvironmentVariable_Path -OutputPath:"C:\EnvironmentVariable_Path"
```
#### <a name="install-a-module-containing-dsc-resources"></a>DSC リソースを含むモジュールをインストールする

Windows PowerShell Desired State Configuration には、DSC リソースを含んだ組み込みモジュールが含まれています。
PowerShellGet コマンドレットを使って、PowerShell ギャラリーなどの外部ソースからモジュールを読み込むこともできます。

`Install-Module 'PSDscResources' -Verbose`

#### <a name="apply-the-configuration-to-the-machine"></a>構成をコンピューターに適用する

構成ドキュメント (MOF ファイル) をコンピューターに適用するには、[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットを使います。

`Start-DscConfiguration -Path 'C:\EnvironmentVariable_Path' -Wait -Verbose`

#### <a name="get-the-current-state-of-the-configuration"></a>構成の現在の状態を取得する

[Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) コマンドレットを使うと、コンピューターの現在の状態が照会され、構成の現在の値が返されます。

`Get-DscConfiguration`

[Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) コマンドレットを使うと、コンピューターに適用されている現在のメタ構成が返されます。

`Get-DscLocalConfigurationManager`

#### <a name="remove-the-current-configuration-from-a-machine"></a>コンピューターから現在の構成を削除する

[Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)

`Remove-DscConfigurationDocument -Stage Current -Verbose`

#### <a name="configure-settings-in-local-configuration-manager"></a>ローカル構成マネージャーで設定を構成する

[Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) コマンドレットを使って、コンピューターにメタ構成 MOF ファイルを適用します。
メタ構成 MOF へのパスが必要です。

`Set-DSCLocalConfigurationManager -Path 'c:\metaconfig\localhost.meta.mof' -Verbose`

## <a name="windows-powershell-desired-state-configuration-log-files"></a>Windows PowerShell Desired State Configuration のログ ファイル

DSC のログは、パス `Microsoft-Windows-Dsc/Operational` にある Windows イベント ログに書き込まれます。
デバッグ用の追加のログを有効にするには、「[DSC イベント ログの場所](/powershell/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs)」に記載されている手順に従ってください。
