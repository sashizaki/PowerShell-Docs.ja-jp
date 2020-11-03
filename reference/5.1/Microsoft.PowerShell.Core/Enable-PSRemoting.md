---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: 0c8c386ab376afde3d15fcd29b3f653b3f738f63
ms.sourcegitcommit: 0e0f45d0d8deb8c9088a4f4a32218edde052b686
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2020
ms.locfileid: "93218040"
---
# Enable-PSRemoting

## 概要
リモート コマンドを受信するようにコンピューターを構成します。

## SYNTAX

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description

`Enable-PSRemoting`コマンドレットは、WS-Management テクノロジを使用して送信される PowerShell リモートコマンドを受信するようにコンピューターを構成します。

PowerShell リモート処理は、Windows Server 2012 では既定で有効になっています。 を使用し `Enable-PSRemoting` て、サポートされている他のバージョンの windows で PowerShell リモート処理を有効にしたり、Windows Server 2012 が無効になった場合にリモート処理を再び有効にすることができます。

このコマンドは、コマンドを受信する各コンピューターで1回だけ実行する必要があります。 コマンドを送信するだけのコンピューターで実行する必要はありません。 構成はリスナーを開始するため、必要な場合にのみ実行することをお勧めします。

PowerShell 3.0 以降では、 `Enable-PSRemoting` コンピューターがパブリックネットワーク上にある場合、コマンドレットを使用して、クライアントバージョンの Windows で PowerShell リモート処理を有効にすることができます。 詳細については、 **SkipNetworkProfileCheck** パラメーターの説明を参照してください。

`Enable-PSRemoting`コマンドレットでは、次の操作を実行します。

- 次のタスクを実行する [set-wsmanquickconfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) コマンドレットを実行します。
  - WinRM サービスを開始します。
  - WinRM サービスのスタートアップの種類を自動に設定します。
  - 任意の IP アドレスで要求を受け入れるリスナーを作成します。
  - WS-Management 通信に対してファイアウォールの例外を有効にします。
  - まだ登録されていない場合は、 **Microsoft powershell** および **microsoft の powershell** セッション構成を登録します。
  - **Microsoft.powershell32** セッション構成がまだ登録されていない場合は、64ビットコンピューターに登録します。
  - すべてのセッション構成を有効にします。
  - リモートアクセスを許可するように、すべてのセッション構成のセキュリティ記述子を変更します。
- WinRM サービスを再起動して、上記の変更を有効にします。

Windows プラットフォームでこのコマンドレットを実行するには、[管理者として実行] オプションを使用して PowerShell を起動します。 これは、Linux または MacOS バージョンの PowerShell には適用されません。

> [!CAUTION]
> Powershell 3.0 と PowerShell 2.0 の両方がインストールされているシステムでは、PowerShell 2.0 を使用して、 `Enable-PSRemoting` `Disable-PSRemoting` コマンドレットとコマンドレットを実行しないでください。 コマンドが正常に完了したように見えても、リモート処理が正しく構成されません。 リモートコマンドを使用してリモート処理を有効または無効にしようとすると、失敗する可能性があります。

## 例

### 例 1: リモートコマンドを受信するようにコンピューターを構成する

このコマンドは、リモート コマンドを受信するようにコンピューターを構成します。

```powershell
Enable-PSRemoting
```

### 例 2: 確認プロンプトを表示せずにリモートコマンドを受信するようにコンピューターを構成する

このコマンドは、リモート コマンドを受信するようにコンピューターを構成します。
**Force** パラメーターを指定すると、ユーザーにプロンプトが表示されません。

```powershell
Enable-PSRemoting -Force
```

### 例 3: クライアントでリモートアクセスを許可する

この例では、Windows オペレーティングシステムのクライアントバージョンでパブリックネットワークからのリモートアクセスを許可する方法を示します。 ファイアウォール規則の名前は、Windows のバージョンによって異なる場合があります。
を使用し `Get-NetFirewallRule` て、ルールの一覧を表示します。 ファイアウォール規則を有効にする前に、規則のセキュリティ設定を表示して、構成が環境に適していることを確認します。

```powershell
Get-NetFirewallRule -Name 'WINRM*' | Select-Object Name
```

```Output
Name
----
WINRM-HTTP-In-TCP-NoScope
WINRM-HTTP-In-TCP
WINRM-HTTP-Compat-In-TCP-NoScope
WINRM-HTTP-Compat-In-TCP
```

```powershell
Enable-PSRemoting -SkipNetworkProfileCheck -Force
Set-NetFirewallRule -Name 'WINRM-HTTP-In-TCP' -RemoteAddress Any
```

既定では、は、 `Enable-PSRemoting` プライベートネットワークとドメインネットワークからのリモートアクセスを許可するネットワークルールを作成します。 このコマンドでは、 **SkipNetworkProfileCheck** パラメーターを使用して、同じローカル サブネット内のパブリック ネットワークからのリモート アクセスを許可しています。 このコマンドは、確認メッセージを抑制する **Force** パラメーターを指定します。

**SkipNetworkProfileCheck** パラメーターは、既定で同じローカルサブネット内のパブリックネットワークからのリモートアクセスを許可する Windows オペレーティングシステムのサーバーバージョンには影響しません。

`Set-NetFirewallRule` **Netsecurity** モジュールのコマンドレットは、任意のリモートの場所からのパブリックネットワークからのリモートアクセスを許可するファイアウォール規則を追加します。 これには、異なるサブネット内の場所が含まれます。

> [!NOTE]
> ファイアウォール規則の名前は、Windows のバージョンによって異なります。 コマンドレットを使用して、 `Get-NetFirewallRule` システム上のルールの名前を一覧表示します。

## PARAMETERS

### -Confirm

コマンドレットの実行前に確認を求めるメッセージが表示されます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

ユーザーに確認せずに、直ちにコマンドを実行します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipNetworkProfileCheck

コンピューターがパブリックネットワーク上にある場合に、Windows オペレーティングシステムのクライアントバージョンでリモート処理を有効にすることを示します。 このパラメーターは、同じローカル サブネット内のコンピューターに対してのみリモート アクセスを許可する、パブリック ネットワークのファイアウォール規則を有効にします。

このパラメーターは、Windows オペレーティングシステムのサーバーバージョンには影響しません。既定では、パブリックネットワーク用のローカルサブネットファイアウォール規則があります。 サーバーのバージョンでローカルサブネットファイアウォールルールが無効になっている場合は、 `Enable-PSRemoting` このパラメーターの値に関係なく、再度有効にします。

ローカルサブネットの制限を削除し、パブリックネットワーク上のすべての場所からのリモートアクセスを有効にするには、 `Set-NetFirewallRule` **netsecurity** モジュールのコマンドレットを使用します。

このパラメーターは、PowerShell 3.0 で導入されました。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

コマンドレットの実行時に発生する内容を示します。
このコマンドレットは実行されません。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし

パイプを使用してこのコマンドレットに入力を渡すことはできません。

## 出力

### System.String

このコマンドレットは、結果を説明する文字列を返します。

## 注

PowerShell 3.0 では、は `Enable-PSRemoting` WS-Management 通信に対して次のファイアウォール例外を作成します。

Windows オペレーティングシステムのサーバーバージョンでは、は、 `Enable-PSRemoting` リモートアクセスを許可するプライベートネットワークとドメインネットワーク用のファイアウォール規則を作成し、同じローカルサブネット内のコンピューターからのみリモートアクセスを許可するパブリックネットワーク用のファイアウォール規則を作成します。

Windows オペレーティングシステムのクライアントバージョンでは、 `Enable-PSRemoting` PowerShell 3.0 で、無制限のリモートアクセスを許可するプライベートネットワークとドメインネットワークのファイアウォール規則が作成されます。 パブリック ネットワークに対して同じローカル サブネットからのリモート アクセスを許可するファイアウォール規則を作成するには、 **SkipNetworkProfileCheck** パラメーターを使用します。

Windows オペレーティングシステムのクライアントまたはサーバーバージョンで、ローカルサブネットの制限を削除し、リモートアクセスを許可するパブリックネットワーク用のファイアウォール規則を作成するには、NetSecurity モジュールのコマンドレットを使用して `Set-NetFirewallRule` 次のコマンドを実行します。 `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`

PowerShell 2.0 では、は `Enable-PSRemoting` WS-Management 通信に対して次のファイアウォール例外を作成します。

Windows オペレーティングシステムのサーバーバージョンでは、リモートアクセスを許可するすべてのネットワークに対してファイアウォール規則が作成されます。

Windows オペレーティングシステムのクライアントバージョンでは、 `Enable-PSRemoting` PowerShell 2.0 では、ドメインとプライベートネットワークの場所に対してのみファイアウォールの例外が作成されます。 セキュリティ上のリスクを最小限に抑えるため、で `Enable-PSRemoting` は、クライアントバージョンの Windows にパブリックネットワークのファイアウォール規則は作成されません。 現在のネットワークの場所がパブリックの場合、は `Enable-PSRemoting` 次のメッセージを返します: ファイアウォールの状態を確認できません。

PowerShell 3.0 以降では、すべて `Enable-PSRemoting` のセッション構成の **Enabled** プロパティの値をに設定することによって、すべてのセッション構成を有効にし `$True` ます。

PowerShell 2.0 で、は、 `Enable-PSRemoting` セッション構成のセキュリティ記述子から **Deny_All** 設定を削除します。 PowerShell 3.0 では、 `Enable-PSRemoting` **Deny_All** と **Network_Deny_All** の設定を削除します。 これにより、ローカルでの使用のために予約されているセッション構成へのリモートアクセスが可能になります。

## 関連リンク

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Disable-PSRemoting](Disable-PSRemoting.md)

[WSMan プロバイダー](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Remote](About/about_Remote.md)

[about_Session_Configurations](About/about_Session_Configurations.md)
