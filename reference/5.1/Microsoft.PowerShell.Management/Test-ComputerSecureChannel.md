---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-computersecurechannel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ComputerSecureChannel
ms.openlocfilehash: 20ea76e725a8ab53d7090078dc819a6297a639ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214344"
---
# Test-ComputerSecureChannel

## 概要
ローカル コンピューターとそのドメインの間のセキュリティで保護されたチャネルをテストして修復します。

## SYNTAX

```
Test-ComputerSecureChannel [-Repair] [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## Description
**Test ComputerSecureChannel** コマンドレットは、ローカルコンピューターとそのドメインの間のチャネルが、信頼関係の状態を確認することによって正常に動作していることを確認します。
接続に失敗した場合は、 *Repair* パラメーターを使用して復元を試みることができます。

**テスト-ComputerSecureChannel** は、チャネルが正常に機能している場合は $True を返し、そうでない場合は $False を返します。
この結果を受けて、コマンドレットを関数とスクリプトの条件ステートメントに使用できます。
詳細なテスト結果を取得するには、 *Verbose* パラメーターを使用します。

このコマンドレットは NetDom.exe と同様に機能します。
NetDom と **Test ComputerSecureChannel** はどちらも **NetLogon** サービスを使用してアクションを実行します。

## 例

### 例 1: ローカルコンピューターとそのドメインの間のチャネルをテストする

```
PS C:\> Test-ComputerSecureChannel
True
```

このコマンドは、ローカルコンピューターと、それが参加しているドメインとの間のチャネルをテストします。

### 例 2: ローカルコンピューターとドメインコントローラーの間でチャネルをテストする

```
PS C:\> Test-ComputerSecureChannel -Server "DCName.fabrikam.com"
True
```

このコマンドは、テストで優先的に使用するドメイン コントローラーを指定します。

### 例 3: ローカルコンピューターとそのドメインの間のチャネルをリセットする

```
PS C:\> Test-ComputerSecureChannel -Repair
True
```

このコマンドは、ローカルコンピューターとそのドメインの間のチャネルをリセットします。

### 例 4: テストに関する詳細情報を表示する

```
PS C:\> Test-ComputerSecureChannel -verbose
VERBOSE: Performing operation "Test-ComputerSecureChannel" on Target "SERVER01".
True
VERBOSE: "The secure channel between 'SERVER01' and 'net.fabrikam.com' is alive and working correctly."
```

このコマンドは、 *Verbose* 共通パラメーターを使用して、操作に関する詳細なメッセージを要求します。
詳細 *については、「* about_CommonParameters」を参照してください。

### 例 5: スクリプトを実行する前に接続をテストする

```
PS C:\> Set-Alias tcsc Test-ComputerSecureChannel
if (!(tcsc))
{Write-Host "Connection failed. Reconnect and retry."}
else { &(.\Get-Servers.ps1) }
```

この例では、接続を必要とするスクリプトを実行する前に、 **テスト用の ComputerSecureChannel** を使用して接続をテストする方法を示します。

最初のコマンドは、Set-Alias コマンドレットを使用してコマンドレット名のエイリアスを作成します。
これにより、領域を節約し、入力の間違いを防ぐことができます。

**If** ステートメントは、スクリプトを実行する前に、 **テストコンピューターの securechannel** が返す値をチェックします。

## PARAMETERS

### -Credential
この処理を実行するアクセス許可を持つユーザー アカウントを指定します。
User01 や Domain01\user01」などのユーザー名を入力するか、Get-Credential コマンドレットが返す **PSCredential** オブジェクトを入力します。
既定では、コマンドレットは現在のユーザーの資格情報を使用します。

*Credential* パラメーターは、 *repair* パラメーターを使用してコンピューターとドメイン間のチャネルを修復するコマンドで使用するように設計されています。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Repair
このコマンドレットによって、NetLogon サービスによって確立されたチャネルが削除され、再構築されることを示します。
テストに失敗した接続の復元を試みるには、このパラメーターを使用します。

このパラメーターを使用するには、現在のユーザーは、ローカル コンピューター上の Administrators グループのメンバーである必要があります。

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

### -Server
コマンドを実行するドメインコントローラーを指定します。
このパラメーターが指定されていない場合、このコマンドレットは操作の既定のドメインコントローラーを選択します。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### System.Boolean
このコマンドレットは、接続が正常に機能している場合は $True を返し、そうでない場合は $False を返します。

## 注

* Windows Vista 以降のバージョンの Windows オペレーティングシステムで **テスト用の ComputerSecureChannel** コマンドを実行するには、[管理者として実行] オプションを使用して windows PowerShell を開きます。
* **テスト-ComputerSecureChannel** は、Netlogon サービスのさまざまな側面を制御する **I_NetLogonControl2** 関数を使用して実装されます。

## 関連リンク

[Checkpoint-Computer](Checkpoint-Computer.md)

[Reset-ComputerMachinePassword](Reset-ComputerMachinePassword.md)

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
