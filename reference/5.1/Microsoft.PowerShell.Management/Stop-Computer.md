---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: 8062210aa94cb46d5e5557ede1bac672cae39622
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218256"
---
# Stop-Computer

## 概要
ローカルとリモートのコンピューターを停止 (シャットダウン) します。

## SYNTAX

### All

```
Stop-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## Description

この `Stop-Computer` コマンドレットは、ローカルコンピューターとリモートコンピューターをシャットダウンします。

のパラメーターを使用し `Stop-Computer` て、バックグラウンドジョブとしてのシャットダウン操作の実行、認証レベルと代替資格情報の指定、コマンドを実行するために作成される同時接続の制限、および即時シャットダウンの強制を行うことができます。

このコマンドレットでは、 **AsJob** パラメーターを使用しない限り、PowerShell リモート処理は必要ありません。

## 例

### 例 1: ローカルコンピューターをシャットダウンする

この例では、ローカルコンピューターをシャットダウンします。

```powershell
Stop-Computer -ComputerName localhost
```

### 例 2: 2 台のリモートコンピューターとローカルコンピューターをシャットダウンする

この例では、2台のリモートコンピューターとローカルコンピューターを停止します。

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

`Stop-Computer`**ComputerName** パラメーターを使用して、2台のリモートコンピューターとローカルコンピューターを指定します。 各コンピューターがシャットダウンされます。

### 例 3: バックグラウンドジョブとしてリモートコンピューターをシャットダウンする

この例では、は `Stop-Computer` 2 台のリモートコンピューター上でバックグラウンドジョブとして実行されます。

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" -AsJob
$results = $j | Receive-Job
$results
```

`Stop-Computer`**ComputerName** パラメーターを使用して、2台のリモートコンピューターを指定します。 **AsJob** パラメーターは、コマンドをバックグラウンドジョブとして実行します。 ジョブオブジェクトは変数に格納され `$j` ます。

変数内のジョブオブジェクト `$j` は、にパイプラインから送信され、 `Receive-Job` ジョブの結果を取得します。 オブジェクトは変数に格納され `$results` ます。 変数は、 `$results` PowerShell コンソールにジョブ情報を表示します。

**AsJob** はローカルコンピューターにジョブを作成し、結果をローカルコンピューターに自動的に返すため、 `Receive-Job` ローカルコマンドとしてを実行できます。

### 例 4: リモートコンピューターをシャットダウンする

この例では、指定された認証を使用してリモートコンピューターをシャットダウンします。

```powershell
Stop-Computer -ComputerName "Server01" -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

`Stop-Computer`**ComputerName** パラメーターを使用して、リモートコンピューターを指定します。 **Impersonation** パラメーターはカスタマイズされた偽装を指定し、 **DcomAuthentication** パラメーターは認証レベルの設定を指定します。

### 例 5: ドメイン内のコンピューターをシャットダウンする

この例では、コマンドを実行すると、指定したドメイン内のすべてのコンピューターが即座にシャットダウンされます。

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -ThrottleLimit 10 -Credential $c
```

`Get-Content`**Path** パラメーターを使用して、現在のディレクトリにあるファイルをドメインコンピューターの一覧と共に取得します。 オブジェクトは変数に格納され `$s` ます。

`Get-Credential` は、 **Credential** パラメーターを使用して、ドメイン管理者の資格情報を指定します。 資格情報は変数に格納され `$c` ます。

`Stop-Computer` 変数内の **ComputerName** パラメーターのコンピューターの一覧で指定されたコンピューターをシャットダウンし `$s` ます。 **Force** パラメーターを指定すると、即時シャットダウンが強制されます。 **ThrottleLimit** パラメーターは、コマンドの同時接続数を10に制限します。 **Credential** パラメーターは、変数に保存されている資格情報を送信し `$c` ます。

## PARAMETERS

### -AsJob

このコマンドレットがバックグラウンドジョブとして実行されることを示します。

このパラメーターを使用するには、ローカルコンピューターとリモートコンピューターがリモート処理用に構成されている必要があります。 windows Vista 以降のバージョンの Windows オペレーティングシステムでは、[ **管理者として実行** ] オプションを使用して PowerShell を開く必要があります。 詳細については、「[about_Remote_Requirements](..//microsoft.powershell.core/about/about_remote_requirements.md)」を参照してください。

**AsJob** パラメーターを指定すると、コマンドは、バックグラウンドジョブを表すオブジェクトを直ちに返します。 ジョブが完了しても、引き続きセッションで作業できます。 ジョブは、ローカル コンピューターで作成され、リモート コンピューターでの結果は自動的にローカル コンピューターに返されます。 ジョブの結果を取得するには、`Receive-Job` コマンドレットを使用します。

PowerShell バックグラウンドジョブの詳細については、「 [about_Jobs](..//microsoft.powershell.core/about/about_jobs.md) 」および「 [about_Remote_Jobs](../microsoft.powershell.core/about/about_remote_jobs.md)」を参照してください。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

停止するコンピューターを指定します。 既定値はローカル コンピューターです。

コンマ区切りのリストで、1 台または複数のコンピューターの NETBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。 ローカルコンピューターを指定するには、コンピューター名または localhost を入力します。

このパラメーターは、PowerShell リモート処理に依存しません。 コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターを使用できます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Credential

このアクションを実行するアクセス許可を持つユーザーアカウントを指定します。 既定値は現在のユーザーです。

**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。 ユーザー名を入力すると、パスワードを入力するように求められます。

資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。

> [!NOTE]
> **SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -DcomAuthentication

このコマンドレットが WMI で使用する認証レベルを指定します。 `Stop-Computer` WMI を使用します。 既定値は **Packet** です。

このパラメーターの有効値は、次のとおりです。

- **既定値** は Windows 認証です。
- **None** : COM 認証なし。
- **接続** : 接続レベルの COM 認証。
- **呼び出し** : 呼び出しレベルの COM 認証。
- **パケット** : パケットレベルの COM 認証。
- **Packetintegrity** : パケットの整合性レベルの COM 認証。
- **Packetprivacy** : パケットプライバシーレベルの COM 認証。
- **Unchanged** : 前のコマンドと同じです。

このパラメーターの値の詳細については、「 [Authenticationlevel](/dotnet/api/system.management.authenticationlevel)」を参照してください。

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

コンピューターの即時シャットダウンを強制的に実行します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -偽装

このコマンドレットが WMI を呼び出すときに使用する偽装レベルを指定します。 既定値は **Impersonate** です。

`Stop-Computer` WMI を使用します。 このパラメーターの有効値は、次のとおりです。

- **既定** 値: 既定の偽装。
- **Anonymous** : 呼び出し元の id を非表示にします。
- **識別** : オブジェクトが呼び出し元の資格情報を照会できるようにします。
- **Impersonate** : オブジェクトが呼び出し元の資格情報を使用できるようにします。

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: Impersonate
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol

コンピューターの再起動にどのプロトコルを使用するかを指定します。 このパラメーターに指定できる値は、 **WSMan** と **DCOM** です。 既定値は **DCOM** です。

このパラメーターは、PowerShell 3.0 で導入されました。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: DCOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

このコマンドを実行するために確立できる最大コンカレント接続数を指定します。
このパラメーターを省略した場合、または値 0 を入力した場合は、既定値の 32 が使用されます。

スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WsmanAuthentication

このコマンドレットで WSMan プロトコルを使用するときに、ユーザー資格情報の認証に使用されるメカニズムを指定します。 既定値は **Default** です。

このパラメーターの有効値は、次のとおりです。

- Basic
- CredSSP
- Default
- ダイジェスト
- Kerberos
- Negotiate

このパラメーターの値の詳細については、「 [Authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。

> [!CAUTION]
> ユーザー資格情報が認証対象のリモートコンピューターに渡される Credential Security Service Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。 このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。 リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。

このパラメーターは、PowerShell 3.0 で導入されました。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

コマンドレットの実行時に発生する内容を示します。 コマンドレットは実行されません。

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

このコマンドレットに入力をパイプすることはできません。

## 出力

### None または System. Automation. RemotingJob

**AsJob** パラメーターを指定した場合、コマンドレットは、-. **Automation. remotingjob** オブジェクトを返します。 それ以外の場合、出力は生成されません。

## 注

このコマンドレットは、 **Win32_OperatingSystem** WMI クラスの **Win32Shutdown** メソッドを使用します。 この方法では、コンピューターの再起動に使用するユーザーアカウントに対して、 **Seshutdownprivilege** 特権を有効にする必要があります。

## 関連リンク

[Add-Computer](Add-Computer.md)

[Checkpoint-Computer](Checkpoint-Computer.md)

[Remove-Computer](Remove-Computer.md)

[Rename-Computer](Rename-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)

[Test-Connection](Test-Connection.md)
