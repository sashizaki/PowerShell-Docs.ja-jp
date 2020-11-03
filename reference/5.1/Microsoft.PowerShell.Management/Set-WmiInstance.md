---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-wmiinstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WmiInstance
ms.openlocfilehash: 03288a2ffbef416937b2c92a7d08a5aed49ffb43
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214411"
---
# Set-WmiInstance

## 概要
既存の Windows Management Instrumentation (WMI) クラスのインスタンスを作成または更新します。

## SYNTAX

### クラス (既定値)

```
Set-WmiInstance [-Class] <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### object

```
Set-WmiInstance -InputObject <ManagementObject> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### path

```
Set-WmiInstance -Path <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WQLQuery

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### query

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### list

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
`Set-WmiInstance`コマンドレットでは、既存の Windows Management Instrumentation (WMI) クラスのインスタンスを作成または更新します。
作成または更新されたインスタンスは、WMI リポジトリに書き込まれます。

Windows PowerShell 3.0 で導入された新しい CIM コマンドレットは、WMI コマンドレットと同じタスクを実行します。
CIM コマンドレットは、WS-Management (WSMan) 標準と Common Information Model (CIM) 標準に準拠しています。
これにより、コマンドレットで同じ手法を使用して、Windows ベースのコンピューターと他のオペレーティングシステムを実行しているコンピューターを管理できます。
を使用する代わり `Set-WmiInstance` に、 [CimInstance](/powershell/module/cimcmdlets/set-ciminstance) または [CimInstance](/powershell/module/cimcmdlets/new-ciminstance) コマンドレットを使用することを検討してください。

## 例

### 例 1: WMI ログレベルを設定する

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2}
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
```

このコマンドは、WMI のログ レベルを 2 に設定します。
このコマンドは、設定するプロパティを渡し、値を引数パラメーターに値のペアとしてまとめて渡します。
このパラメーターは、@{property = value} という構造で定義されたハッシュ テーブルを受け取ります。
返されるクラス情報には、新しい値が反映されます。

### 例 2: 環境変数とその値を作成する

```
PS C:\> Set-WmiInstance -Class win32_environment -Argument @{Name="testvar";VariableValue="testvalue";UserName="<SYSTEM>"}
__GENUS          : 2
__CLASS          : Win32_Environment
__SUPERCLASS     : CIM_SystemResource
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Environment.Name="testvar",UserName="<SYSTEM>"
__PROPERTY_COUNT : 8
__DERIVATION     : {CIM_SystemResource, CIM_LogicalElement, CIM_ManagedSystemElement}
__SERVER         : SYSTEM01
__NAMESPACE      : root\cimv2
__PATH           : \\SYSTEM01\root\cimv2:Win32_Environment.Name="testvar",UserName="<SYSTEM>"
Caption          : <SYSTEM>\testvar
Description      : <SYSTEM>\testvar
InstallDate      :
Name             : testvar
Status           : OK
SystemVariable   : True
UserName         : <SYSTEM>
VariableValue    : testvalue
```

このコマンドは、持つ testvar という値を持つ持つ testvar 環境変数を作成します。
これを行うには、 **Win32_Environment** WMI クラスの新しいインスタンスを作成します。
この操作には適切な資格情報が必要であり、新しい環境変数を表示するには、Windows PowerShell を再起動する必要がある場合があります。

### 例 3: 複数のリモートコンピューターの WMI ログ記録レベルを設定する

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2} -Computername "system01", "system02", "system03"
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
...
```

このコマンドは、WMI のログ レベルを 2 に設定します。
このコマンドは、設定するプロパティを渡し、値を引数パラメーターに値のペアとしてまとめて渡します。
このパラメーターは、@{property = value} という構造で定義されたハッシュ テーブルを受け取ります。
返されるクラス情報には、新しい値が反映されます。

## PARAMETERS

### -Arguments
変更するプロパティの名前と、そのプロパティの新しい値を指定します。
名前と値は、名前と値のペアである必要があります。
名前と値のペアは、コマンドラインでハッシュテーブルとして渡されます。
次に例を示します。

`@{Setting1=1; Setting2=5; Setting3="test"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: class, object, path
Aliases: Args, Property

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
この cmdket がバックグラウンドジョブとして実行されることを示します。
完了に時間のかかるコマンドを実行するには、このパラメーターを使用します。

*AsJob* パラメーターを指定すると、バックグラウンドジョブを表すオブジェクトが返され、コマンドプロンプトが表示されます。
ジョブが完了しても、引き続きセッションで作業できます。
リモートコンピューターに対して設定された **設定のインスタンス** が使用されている場合、ジョブはローカルコンピューター上に作成され、リモートコンピューターからの結果は自動的にローカルコンピューターに返されます。
ジョブを管理するには **、ジョブの名詞を** 含むコマンドレット ( **job** コマンドレット) を使用します。
ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。

このパラメーターをリモートコンピューターと共に使用するには、ローカルコンピューターとリモートコンピューターをリモート処理用に構成する必要があります。
さらに、windows Vista 以降のバージョンの Windows オペレーティングシステムでは、[管理者として実行] オプションを使用して Windows PowerShell を起動する必要があります。
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
WMI 接続で使用する必要がある認証レベルを指定します。
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
WMI クラスの名前を指定します。

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
ユーザー名を入力すると、このコマンドレットによってパスワードが要求されます。

このパラメーターは、Windows PowerShell でインストールされたプロバイダーでサポートされていないパラメーターを指定してインストールされたプロバイダーではサポートされません。

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
このパラメーターを使用すると、 *Arguments* パラメーターを除く他のすべてのパラメーターは無視されます。

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
*Locale* パラメーターは、配列内の MS_ 形式で、 \<LCID\> 優先順位に従って指定します。

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
作成または更新するインスタンスの WMI オブジェクトパスを指定します。

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

### -PutType
WMI インスタンスを作成または更新するかどうかを示します。
このパラメーターの有効値は、次のとおりです。

- UpdateOnly.
既存の WMI インスタンスを更新します。
- CreateOnly.
新しい WMI インスタンスを作成します。
- UpdateOrCreate.
WMI インスタンスが存在する場合は更新し、存在しない場合には新しいインスタンスを作成します。

```yaml
Type: System.Management.PutType
Parameter Sets: (All)
Aliases:
Accepted values: None, UpdateOnly, CreateOnly, UpdateOrCreate

Required: False
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

### なし
このコマンドレットは入力を受け取りません。

## 出力

### なし
このコマンドレットは出力を生成しません。

## 注

## 関連リンク

[Get-WmiObject](Get-WmiObject.md)

[Invoke-WmiMethod](Invoke-WmiMethod.md)

[Remove-WmiObject](Remove-WmiObject.md)
