---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/reset-computermachinepassword?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-ComputerMachinePassword
ms.openlocfilehash: 1484bc83b9503ce43420b833a1b78b3c4215d98a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214488"
---
# Reset-ComputerMachinePassword

## 概要
コンピューターのアカウントのパスワードをリセットします。

## SYNTAX

```
Reset-ComputerMachinePassword [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## Description
コンピューターがドメイン内のドメインコントローラーに対する認証に使用するコンピューターアカウント **のパスワードを変更します** 。
ローカル コンピューターのパスワードをリセットするために使用できます。

## 例

### 例 1: ローカルコンピューターのパスワードをリセットする

```
PS C:\> Reset-ComputerMachinePassword
```

このコマンドは、ローカルコンピューターのコンピューターパスワードをリセットします。
コマンドは、現在のユーザーの資格情報で実行されます。

### 例 2: 指定したドメインコントローラーを使用してローカルコンピューターのパスワードをリセットする

```
PS C:\> Reset-ComputerMachinePassword -Server "DC01" -Credential Domain01\Admin01
```

このコマンドは、DC01 ドメインコントローラーを使用して、ローカルコンピューターのコンピューターパスワードをリセットします。
*Credential* パラメーターを使用して、ドメイン内のコンピューターパスワードをリセットするアクセス許可を持つユーザーアカウントを指定します。

### 例 3: リモートコンピューターのパスワードをリセットする

```
$cred = Get-Credential
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Reset-ComputerMachinePassword -Credential $using:cred}
```

このコマンドは、Invoke-Command コマンドレットを使用して、Server01 リモートコンピューター上で **Reset-ComputerMachinePassword** コマンドを実行します。

Windows PowerShell のリモート コマンドの詳細については、「about_Remote」および「 **Invoke-Command** 」を参照してください。

## PARAMETERS

### -Credential
この処理を実行するアクセス許可を持つユーザー アカウントを指定します。
既定値は現在のユーザーです。

User01 や Domain01\user01」などのユーザー名を入力するか、Get-Credential コマンドレットによって生成された **PSCredential** オブジェクトを入力します。
ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。

このパラメーターは Windows PowerShell 3.0 で導入されました。

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

### -Server
このコマンドレットでコンピューターアカウントのパスワードを設定するときに使用するドメインコントローラーの名前を指定します。

このパラメーターは省略可能です。
このパラメーターを省略した場合は、コマンドにサービスを提供するドメイン コントローラーが選択されます。

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

### なし
このコマンドレットは出力を生成しません。

## 注

## 関連リンク

## 関連リンク
