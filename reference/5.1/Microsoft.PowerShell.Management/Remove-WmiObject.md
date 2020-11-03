---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WmiObject
ms.openlocfilehash: 287eb02e7de2f4182e0ecfd7f6b6a7cafb66969e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214544"
---
# Remove-WmiObject

## 概要
既存の Windows Management Instrumentation (WMI) クラスのインスタンスを削除します。

## SYNTAX

### クラス (既定値)

```
Remove-WmiObject [-Class] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### object

```
Remove-WmiObject -InputObject <ManagementObject> [-AsJob] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### path

```
Remove-WmiObject -Path <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WQLQuery

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### query

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### list

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## Description
**Get-wmiobject** コマンドレットは、既存の WINDOWS MANAGEMENT INSTRUMENTATION (WMI) クラスのインスタンスを削除します。

## 例

### 例 1: Win32 プロセスのすべてのインスタンスを閉じる

```
PS C:\> notepad
PS C:\> $np = Get-WmiObject -Query "select * from win32_process where name='notepad.exe'"
PS C:\> $np | Remove-WmiObject
```

この例では、Notepad.exe のすべてのインスタンスを閉じます。

最初のコマンドは、メモ帳のインスタンスを起動します。

2番目のコマンドは、Get-WmiObject コマンドレットを使用して Notepad.exe に対応する Win32_Process のインスタンスを取得し、$np 変数に格納します。

3番目のコマンドは、$np 変数内のオブジェクトを **get-wmiobject** に渡して、Notepad.exe のすべてのインスタンスを削除します。

### 例 2: フォルダーを削除する

```
PS C:\> $a = Get-WMIObject -Query "Select * From Win32_Directory Where Name ='C:\\Test'"
PS C:\> $a | Remove-WMIObject
```

このコマンドは、C:\Test フォルダーを削除します。

最初のコマンドは、 **get-wmiobject** を使用して C:\Test フォルダーに対してクエリを実行し、そのオブジェクトを $a 変数に格納します。

2番目のコマンドは、$a 変数を **get-wmiobject** にパイプして、フォルダーを削除します。

## PARAMETERS

### -AsJob
このコマンドレットがバックグラウンドジョブとして実行されることを示します。
完了に時間のかかるコマンドを実行するには、このパラメーターを使用します。

Windows PowerShell 3.0 で導入された新しい CIM コマンドレットは、WMI コマンドレットと同じタスクを実行します。
CIM コマンドレットは、WS-Management (WSMan) 標準と Common Information Model (CIM) 標準に準拠しています。これにより、コマンドレットは、Windows オペレーティングシステムを実行しているコンピューターと他のオペレーティングシステムを実行しているコンピューターを管理するのと同じ手法を使用できます。
**Remove-WmiObject** を使用する代わりに、Remove-CimInstancehttps://go.microsoft.com/fwlink/?LinkId=227964 コマンドレットを使用することを検討してください。

*AsJob* パラメーターを使用すると、バックグラウンド ジョブを表すオブジェクトが返され、その後コマンド プロンプトが表示されます。
ジョブが完了しても、引き続きセッションで作業できます。
**Remove-WmiObject** がリモート コンピューターに対して使用された場合、ジョブはローカル コンピューターで作成され、リモート コンピューターでの結果は自動的にローカル コンピューターに返されます。
ジョブを管理するには **、ジョブの名詞を** 含むコマンドレット ( **job** コマンドレット) を使用します。
ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。

リモートコンピューターでこのパラメーターを使用するには、ローカルコンピューターとリモートコンピューターをリモート処理用に構成する必要があります。
[管理者として実行] オプションを使用して Windows PowerShell を起動します。
詳細については、「about_Remote_Requirements」を参照してください。

Windows PowerShell のバックグラウンドジョブの詳細については、「about_Jobs」および「about_Remote_Jobs」を参照してください。

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

### -認証
WMI 接続に使用する認証レベルを指定します。
このパラメーターの有効値は、次のとおりです。

- -1: 変更なし。
- 0: Default。
- 1: なし。
の認証は実行されません。
- 2: 接続します。
認証は、クライアントがアプリケーションとの関係を確立した場合にのみ実行されます。
- 3: を呼び出します。
認証は、アプリケーションが要求を受信したときに各呼び出しの開始時にのみ実行されます。
- 4: パケット。
認証は、クライアントから受信したすべてのデータに対して実行されます。
- 5: PacketIntegrity。
クライアントとアプリケーションの間で転送されるすべてのデータが認証され、検証されます。
- 6: PacketPrivacy。
他の認証レベルのプロパティが使用され、すべてのデータが暗号化されます。

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authority
WMI 接続の認証に使用する機関を指定します。
標準の NTLM 認証または Kerberos 認証を指定できます。
NTLM を使用するには、認証設定に「ntlmdomain:\<DomainName\>」と指定します。\<DomainName\> には、有効な NTLM ドメイン名を指定します。
Kerberos を使用するには、「kerberos:」と指定し \<DomainName\> \\ \<ServerName\> ます。
ローカル コンピューターへの接続時に認証設定を指定することもできます。

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -クラス
このコマンドレットが削除する WMI クラスの名前を指定します。

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
このコマンドレットが実行されるコンピューターの名前を指定します。
既定値はローカル コンピューターです。

1 台または複数のコンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。
ローカルコンピューターを指定するには、コンピューター名、ドット (.)、または localhost を入力します。

このパラメーターは、Windows PowerShell リモート処理に依存しません。
コンピューターがリモート コマンドを実行するように構成されていない場合でも、 *ComputerName* パラメーターを使用できます。

```yaml
Type: System.String[]
Parameter Sets: class, path, WQLQuery, query, list
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
この処理を実行するアクセス許可を持つユーザー アカウントを指定します。
既定値は現在のユーザーです。

User01 や Domain01\user01」などのユーザー名を入力するか、Get-Credential コマンドレットによって生成された **PSCredential** オブジェクトを入力します。
ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAllPrivileges
このコマンドレットが、WMI 呼び出しを行うコマンドの前に、現在のユーザーのすべてのアクセス許可を有効にすることを示します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -偽装
使用する偽装レベルを指定します。
このパラメーターの有効値は、次のとおりです。

- 0: Default。
既定の偽装レベルのローカルレジストリを読み取ります。これは通常、3: Impersonate に設定されています。
- 1: Anonymous。
呼び出し元の資格情報は非表示になります。
- 2: Identify。
オブジェクトによる呼び出し元の資格情報のクエリが許可されます。
- 3: Impersonate。
オブジェクトによる呼び出し元の資格情報の使用が許可されます。
- 4: Delegate。
オブジェクトが呼び出し元の資格情報の使用を他のオブジェクトに許可できるようにします。

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
入力として使用する **system.management.managementobject** オブジェクトを指定します。
このパラメーターを使用する場合、他のすべてのパラメーターが無視されます。

```yaml
Type: System.Management.ManagementObject
Parameter Sets: object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ロケール
WMI オブジェクトの優先ロケールを指定します。
*Locale* パラメーターは、MS_ 形式の配列として、優先順位に従って指定し \<LCID\> ます。

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace
*クラス* パラメーターと共に使用する場合に、参照先の wmi クラスが配置されている wmi リポジトリの名前空間を指定します。

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
削除する WMI クラスの WMI オブジェクト パス、または WMI クラスのインスタンスの WMI オブジェクト パスを指定します。

```yaml
Type: System.String
Parameter Sets: path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
このコマンドを実行するために確立できる最大コンカレント接続数を指定します。
このパラメーターは、 *AsJob* パラメーターと共に使用されます。
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

### System.management.managementobject
このコマンドレットには、管理オブジェクトをパイプすることができます。

## 出力

### なし、システムの管理. RemotingJob
*AsJob* パラメーターを指定した場合、このコマンドレットはジョブオブジェクトを返します。
それ以外の場合、出力は生成されません。

## 注

## 関連リンク

[Get-WmiObject](Get-WmiObject.md)

[Invoke-WmiMethod](Invoke-WmiMethod.md)

[Set-WmiInstance](Set-WmiInstance.md)
