---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/04/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Computer
ms.openlocfilehash: 89e43220a8d5ac675ea232db09cf3edec2ca2b97
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214560"
---
# Remove-Computer

## 概要
ドメインからローカル コンピューターを削除します。

## SYNTAX

### Local (既定値)

```
Remove-Computer [[-UnjoinDomainCredential] <PSCredential>] [-Restart] [-Force] [-PassThru]
 [-WorkgroupName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### リモート

```
Remove-Computer -UnjoinDomainCredential <PSCredential> [-LocalCredential <PSCredential>] [-Restart]
 [-ComputerName <String[]>] [-Force] [-PassThru] [-WorkgroupName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## Description

コマンドレットでは、 `Remove-Computer` ローカルコンピューターとリモートコンピューターを現在のドメインから削除します。

ドメインからコンピューターを削除すると、によって、 `Remove-Computer` コンピューターのドメインアカウントも無効になります。 現在のユーザーの資格情報であっても、ドメインからコンピューターを切断するには、明示的な資格情報を指定する必要があります。 変更を有効にするには、コンピューターを再起動する必要があります。 ドメインからコンピューターを削除する際に、コンピューターをワークグループに移動する必要もあります。 **WorkgroupName** パラメーターを使用して、ワークグループを指定します。

ワークグループからドメイン、あるワークグループから別のワークグループ、またはあるドメインから別のドメインにコンピューターを移動するには、`Add-Computer` コマンドレットを使用します。

コマンドの結果を取得するには、 **Verbose** パラメーターと **PassThru** パラメーターを使用します。 ユーザー プロンプトが表示されないようにするには、 **Force** パラメーターを使用します。

`Remove-Computer` ローカルコンピューターとリモートコンピューターをドメインから削除します。 このコマンドレットには、リモート コンピューターに接続してドメインから削除するための代替資格情報を指定する資格情報パラメーター、影響を受けたコンピューターを再起動する **Restart** パラメーター、コンピューターの追加先のワークグループ名を指定する **WorkgroupName** パラメーターなどのパラメーターがあります。

## 例

### 例 1: ローカルコンピューターをドメインから削除する

この例では、ローカルコンピューターが参加先のドメインから削除されます。

```powershell
Remove-Computer -UnjoinDomaincredential Domain01\Admin01 -PassThru -Verbose -Restart
```

**UnjoinDomainCredential** パラメーターは、ドメイン管理者の資格情報を提供します。 **PassThru** および **Verbose** 共通パラメーターには、コマンドの成功または失敗に関する情報が表示されます。 **Restart** パラメーターを指定すると、コンピューターが再起動され、削除操作が完了します。

ワークグループ名が指定されていない場合、コンピューターはドメインから削除された後、という名前のワークグループに移動されます。

### 例 2: 従来のワークグループに複数のコンピューターを移動する

この例では、ファイルに一覧表示されているすべてのコンピューターを `OldServers.txt` ドメインから削除し、 **従来** のワークグループに移動します。

```powershell
Remove-Computer -ComputerName (Get-Content OldServers.txt) -LocalCredential Domain01\Admin01 -UnJoinDomainCredential Domain01\Admin01 -WorkgroupName "Legacy" -Force -Restart
```

**Localcredential** パラメーターは、リモートコンピューターに接続するアクセス許可を持つユーザーの資格情報を提供します。 **UnjoinDomainCredential** パラメーターは、ドメインからコンピューターを削除するアクセス許可を持つユーザーの資格情報を提供します。 **Force** パラメーターを指定すると、各コンピューターの確認プロンプトが表示されなくなります。 **Restart** パラメーターを指定すると、各コンピューターがドメインから削除された後に再起動されます。

### 例 3: 確認せずにワークグループからコンピューターを削除する

この例では、リモートコンピューター、Server01、およびローカルコンピューターをドメインから削除し、 **ローカル** ワークグループに追加します。

```powershell
Remove-Computer -ComputerName "Server01", "localhost" -UnjoinDomainCredential Domain01\Admin01 -WorkgroupName "Local" -Restart -Force
```

**Force** パラメーターを指定すると、各コンピューターの確認プロンプトが表示されなくなります。 **Restart** パラメーターを使用すると、コンピューターが再起動され、変更が有効になります。

## PARAMETERS

### -ComputerName

ドメインから削除するコンピューターを指定します。 既定値はローカル コンピューターです。

リモートコンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名 (FQDN) を入力します。 ローカルコンピューターを指定するには、コンピューター名、ドット (.)、または localhost を入力します。

このパラメーターは、PowerShell リモート処理に依存しません。 **ComputerName** `Remove-Computer` コンピューターがリモートコマンドを実行するように構成されていない場合でも、の ComputerName パラメーターを使用できます。

このパラメーターは、PowerShell 3.0 で導入されました。

```yaml
Type: System.String[]
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Force

ユーザー プロンプトが表示されないようにします。 既定では、 `Remove-Computer` 各コンピューターを削除する前に、確認を求めるメッセージが表示されます。

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

### -LocalCredential

**ComputerName** パラメーターによって指定されたコンピューターに接続するためのアクセス許可を持つユーザーアカウントを指定します。 既定値は現在のユーザーです。

またはなどのユーザー名を入力する `User01` `Domain01\User01` か、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。 ユーザー名を入力すると、コマンドレットによってパスワードの入力が求められます。 コンピューターを現在のドメインから削除するアクセス許可を持つユーザー アカウントを指定するには、 **UnjoinDomainCredential** パラメーターを使用します。

このパラメーターは、PowerShell 3.0 で導入されました。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

コマンドの結果を返します。 それ以外の場合、このコマンドレットによる出力はありません。

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

### -Restart

このコマンドレットにより、削除されているコンピューターが再起動されることを示します。 多くの場合、変更を有効にするには再起動が必要です。

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

### -UnjoinDomainCredential

コンピューターを現在のドメインから削除するアクセス許可を持つユーザー アカウントを指定します。
ドメインからリモート コンピューターを削除するには、このパラメーターに資格情報を、それが現在のユーザーの資格情報であっても明示的に指定する必要があります。

User01 や Domain01\user01」などのユーザー名を入力するか、によって生成された **PSCredential** オブジェクトを入力し `Get-Credential` ます。 ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。

リモート コンピューターに接続するアクセス許可を持つユーザー アカウントを指定するには、 **LocalCredential** パラメーターを使用します。

このパラメーターは、PowerShell 3.0 で導入されました。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Local, Remote
Aliases: Credential

Required: False (Local), True (Remote)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ワークスペース

ドメインから削除したコンピューターの追加先ワークグループの名前を指定します。 既定値は **WORKGROUP** です。 ドメインからコンピューターを削除する際に、コンピューターをワークグループに追加する必要があります。

このパラメーターは、PowerShell 3.0 で導入されました。

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

コマンドレットの実行時に発生する内容を示します。 このコマンドレットは実行されません。

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

### System.String

パイプを使用してコンピューター名を thiscmdlet に送ることができます。

## 出力

### Microsoft. PowerShell. ComputerChangeInfo

**PassThru** パラメーターを使用すると、は `Remove-Computer` **computerchangeinfo** オブジェクトを返します。
それ以外の場合、このコマンドレットによる出力はありません。

## 注

このコマンドレットは、コンピューターをワークグループから削除しません。

## 関連リンク

[Add-Computer](Add-Computer.md)

[Checkpoint-Computer](Checkpoint-Computer.md)

[Remove-Computer](Remove-Computer.md)

[Rename-Computer](Rename-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)

[Stop-Computer](Stop-Computer.md)

[Test-Connection](Test-Connection.md)
