---
ms.date: 06/12/2017
author: rpsqrd
ms.topic: conceptual
keywords: JEA, PowerShell, セキュリティ
title: JEA の構成の登録
ms.openlocfilehash: 7b0a3f0bac26bf62989fecdf60388bbebd6fa756
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="registering-jea-configurations"></a>JEA の構成の登録

> 適用先: Windows PowerShell 5.0

[ロール機能](role-capabilities.md)と[セッション構成ファイル](session-configurations.md)を作成した後、JEA を使用できるようにする前の最後のステップは、JEA エンドポイントを登録することです。
このプロセスでは、セッション構成情報をシステムに適用し、ユーザーおよび自動化エンジンがエンドポイントを使用できるようにします。

## <a name="single-machine-configuration"></a>単一コンピューターの構成

小規模な環境の場合、[Register-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/register-pssessionconfiguration) コマンドレットを使ってセッション構成ファイルを登録することにより、JEA を展開できます。

作業を開始する前に、次の前提条件を満たしていることを確認してください。
- 1 つ以上のロールが作成されて、有効な PowerShell モジュールの "RoleCapabilities" フォルダーに配置されていること。
- セッション構成ファイルの作成とテストが済んでいること。
- JEA 構成を登録するユーザーに、システムに対する管理者権限があること。

JEA エンドポイントの名前を選ぶ必要もあります。
ユーザーが JEA を使ってシステムに接続するときに、JEA エンドポイントの名前が必要になります。
[Get-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/get-pssessionconfiguration) コマンドレットを使って、システム上の既存のエンドポイントの名前を確認できます。
"microsoft" で始まるエンドポイントは、通常、Windows に付属しています。
"microsoft.powershell" エンドポイントは、リモート PowerShell エンドポイントに接続するときに使われる既定のエンドポイントです。

```powershell
PS C:\> Get-PSSessionConfiguration | Select-Object Name

Name
----
microsoft.powershell
microsoft.powershell.workflow
microsoft.powershell32
```

JEA エンドポイントに対して適切な名前を決定した後、次のコマンドを実行してエンドポイントを登録します。

```powershell
Register-PSSessionConfiguration -Path .\MyJEAConfig.pssc -Name 'JEAMaintenance' -Force
```

> [!WARNING]
> 上記のコマンドは、システム上の WinRM サービスを再起動します。
> これにより、すべての PowerShell リモート処理セッションおよび実行中の DSC 構成が終了されます。
> 業務の中断を防ぐため、コマンドを実行する前に、運用環境のコンピューターをオフラインにすることをお勧めします。

登録が成功すると、[JEA を使用](using-jea.md)できる状態になります。
セッション構成ファイルは、登録後は使用されないので、いつでも削除できます。

## <a name="multi-machine-configuration-with-dsc"></a>DSC での複数コンピューター構成

JEA を複数のコンピューターに展開する場合、最も簡単な展開モデルである JEA の [Desired State Configuration](https://msdn.microsoft.com/en-us/powershell/dsc/overview) リソースを使うと、各コンピューターに JEA を迅速かつ一貫して展開できます。

DSC で JEA を展開するには、次の前提条件が満たされていることを確認する必要があります。
- 1 つまたは複数のロール機能が作成され、有効な PowerShell モジュールに追加されていること。
- ロールを含む PowerShell モジュールが、各コンピューターからアクセスできる (読み取り専用の) ファイル共有に格納されていること。
- セッション構成の設定が決定されていること。 JEA DSC リソースを使うときは、セッション構成ファイルを作成する必要はありません。
- 各コンピューターで管理操作を実行できる資格情報があること、またはコンピューターの管理に使われる DSC プル サーバーにアクセスできること。
- [JEA DSC リソース](https://github.com/PowerShell/JEA/tree/master/DSC%20Resource)をダウンロードしてあること。

ターゲット コンピューター (または、プル サーバーを使っている場合はプル サーバー) 上で、JEA エンドポイント用の DSC 構成を作成します。
この構成では、JustEnoughAdministration DSC リソースを使って、ファイル共有からロール機能経由でコピーするセッション構成ファイルと File リソースを設定します。

DSC リソースを使って次のプロパティを構成できます。
- ロールの定義
- 仮想アカウント グループ
- グループ管理されたサービス アカウント名
- トランスクリプト ディレクトリ
- ユーザー ドライブ
- 条件付きアクセス規則
- JEA セッションのスタートアップ スクリプト

DSC 構成でのこれらの各プロパティの構文は、PowerShell セッションの構成ファイルと一致しています。

一般的なサーバー メンテナンス モジュールの DSC 構成の例を以下に示します。

ここで、"RoleCapabilities" サブフォルダー内のロール機能を含む有効な PowerShell モジュールは "\\\\myfileshare\\JEA" ファイル共有にあるものと想定しています。


```powershell
Configuration JEAMaintenance
{
    Import-DscResource -Module JustEnoughAdministration, PSDesiredStateConfiguration

    File MaintenanceModule
    {
        SourcePath = "\\myfileshare\JEA\ContosoMaintenance"
        DestinationPath = "C:\Program Files\WindowsPowerShell\Modules\ContosoMaintenance"
        Checksum = "SHA-256"
        Ensure = "Present"
        Type = "Directory"
        Recurse = $true
    }

    JeaEndpoint JEAMaintenanceEndpoint
    {
        EndpointName = "JEAMaintenance"
        RoleDefinitions = "@{ 'CONTOSO\JEAMaintenanceAuditors' = @{ RoleCapabilities = 'GeneralServerMaintenance-Audit' }; 'CONTOSO\JEAMaintenanceAdmins' = @{ RoleCapabilities = 'GeneralServerMaintenance-Audit', 'GeneralServerMaintenance-Admin' } }"
        TranscriptDirectory = 'C:\ProgramData\JEAConfiguration\Transcripts'
        DependsOn = '[File]MaintenanceModule'
    }
}
```

その後、[ローカル構成マネージャーを直接呼び出す](https://msdn.microsoft.com/en-us/powershell/dsc/metaconfig)ことにより、または[プル サーバーの構成](https://msdn.microsoft.com/en-us/powershell/dsc/pullserver)を更新することにより、この構成をシステムに適用できます。

DSC リソースを使うと、既定の Microsoft.PowerShell リモート処理エンドポイントを置き換えることもできます。
これを行うと、リソースは、既定の WinRM ACL (リモート管理ユーザーとローカル管理者グループのメンバーにアクセスを許可します) を持つ "Microsoft.PowerShell.Restricted" という名前のバックアップ非制約エンドポイントを自動的に登録します。

## <a name="unregistering-jea-configurations"></a>JEA の構成の登録解除

システムの JEA エンドポイントを削除するには、[Unregister-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/Unregister-PSSessionConfiguration) コマンドレットを使います。
JEA エンドポイントの登録を解除すると、新しいユーザーがシステムに新しい JEA セッションを作成できなくなります。
また、同じエンドポイント名を使って更新されたセッション構成ファイルを再登録することで、JEA 構成を更新することもできます。

```powershell
# Unregister the JEA endpoint called "ContosoMaintenance"
Unregister-PSSessionConfiguration -Name 'ContosoMaintenance' -Force
```

> [!WARNING]
> JEA エンドポイントの登録を解除すると、WinRM サービスが再起動されます。
> これにより、他の PowerShell セッション、WMI 呼び出し、一部の管理ツールなど、実行中のほとんどのリモート管理操作が中断されます。
> 計画されたメンテナンス期間中にのみ、PowerShell エンドポイントの登録を解除してください。

## <a name="next-steps"></a>次の手順

- [JEA エンドポイントをテストする](using-jea.md)