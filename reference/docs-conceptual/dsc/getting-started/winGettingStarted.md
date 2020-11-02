---
ms.date: 08/15/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: Windows 用 Desired State Configuration (DSC) の概要
description: このトピックでは、Windows 用 PowerShell Desired State Configuration (DSC) の使用を開始する方法について説明します。
ms.openlocfilehash: 2b9ddba2023a3933e3ad70d7bfee798ff07f0484
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662814"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-windows"></a>Windows 用 Desired State Configuration (DSC) の概要

このトピックでは、Windows 用 PowerShell Desired State Configuration (DSC) の使用を開始する方法について説明します。 DSC に関する一般的な情報については、「[Windows PowerShell Desired State Configuration の概要](../overview/overview.md)」を参照してください。

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

[Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) のスタンドアロン製品 SKU には、Desired State Configuration の実装が含まれていないため、PowerShell DSC または Azure Automation State Configuration で管理することはできません。

## <a name="installing-dsc"></a>DSC のインストール

PowerShell Desired State Configuration は Windows に含まれており、Windows Management Framework を通じて更新されます。 最新バージョンは [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616) です。

> [!NOTE]
> DSC を使ってコンピューターを管理するために、Windows Server の 'DSC-Service' 機能を有効にする必要はありません。
> この機能は、Windows プル サーバー インスタンスを構築する場合にのみ必要です。

## <a name="using-dsc-for-windows"></a>Windows 用 DSC の使用

次のセクションでは、Windows コンピューター上で DSC 構成を作成し、実行する方法を説明します。

### <a name="creating-a-configuration-mof-document"></a>構成 MOF ドキュメントの作成

構成を作成するには、Windows PowerShell の `Configuration` キーワードを使用します。
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

```PowerShell
Install-Module 'PSDscResources' -Verbose
```

#### <a name="apply-the-configuration-to-the-machine"></a>構成をコンピューターに適用する

> [!NOTE]
> DSC が実行できるようにするには、`localhost` の構成を実行している場合でも PowerShell のリモート コマンドを受信するように、Windows を構成する必要があります。 環境を簡単に正しく構成するには、管理者特権の PowerShell ターミナルで `Set-WsManQuickConfig -Force` を実行するだけです。

[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットを使用して、構成ドキュメント (MOF ファイル) をコンピューターに適用できます。

```powershell
Start-DscConfiguration -Path 'C:\EnvironmentVariable_Path' -Wait -Verbose
```

#### <a name="get-the-current-state-of-the-configuration"></a>構成の現在の状態を取得する

[Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) コマンドレットを使うと、コンピューターの現在の状態が照会され、構成の現在の値が返されます。

```powershell
Get-DscConfiguration
```

[Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) コマンドレットを使うと、コンピューターに適用されている現在のメタ構成が返されます。

```powershell
Get-DscLocalConfigurationManager
```

#### <a name="remove-the-current-configuration-from-a-machine"></a>コンピューターから現在の構成を削除する

[Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)

```powershell
Remove-DscConfigurationDocument -Stage Current -Verbose
```

#### <a name="configure-settings-in-local-configuration-manager"></a>ローカル構成マネージャーで設定を構成する

[Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) コマンドレットを使って、コンピューターにメタ構成 MOF ファイルを適用します。 メタ構成 MOF へのパスが必要です。

```powershell
Set-DSCLocalConfigurationManager -Path 'c:\metaconfig\localhost.meta.mof' -Verbose
```

## <a name="windows-powershell-desired-state-configuration-log-files"></a>Windows PowerShell Desired State Configuration のログ ファイル

DSC のログは、パス `Microsoft-Windows-Dsc/Operational` にある Windows イベント ログに書き込まれます。
デバッグ用の追加のログを有効にするには、「[DSC イベント ログの場所](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs)」に記載されている手順に従ってください。
