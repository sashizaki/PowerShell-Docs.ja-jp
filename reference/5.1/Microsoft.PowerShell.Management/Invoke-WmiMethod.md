---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-wmimethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WmiMethod
ms.openlocfilehash: e9743488e86429e5cc3252162e51268a7978b79d
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "93217992"
---
# Invoke-WmiMethod

## 概要
WMI メソッドを呼び出します。

## SYNTAX

### クラス (既定値)

```
Invoke-WmiMethod [-Class] <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### object

```
Invoke-WmiMethod -InputObject <ManagementObject> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### path

```
Invoke-WmiMethod -Path <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WQLQuery

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### query

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### list

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description

この `Invoke-WmiMethod` コマンドレットは、Windows Management Instrumentation (WMI) オブジェクトのメソッドを呼び出します。

Windows PowerShell 3.0 で導入された新しい Common Information Model (CIM) コマンドレットは、WMI コマンドレットと同じタスクを実行します。 CIM コマンドレットは、WS-Management (WSMan) 標準と CIM 標準に準拠しています。これにより、コマンドレットは、Windows コンピューターや他のオペレーティングシステムを実行しているものと同じ手法を使用して管理できます。 を使用する代わり `Invoke-WmiMethod` に、 [invoke-cimmethod](../cimcmdlets/invoke-cimmethod.md)の使用を検討してください。

## 例

### 例 1: WMI オブジェクトの必要な順序を一覧表示する

```powershell
([wmiclass]'Win32_Volume').GetMethodParameters('Format')
```

```Output
__GENUS           : 2
__CLASS           : __PARAMETERS
__SUPERCLASS      :
__DYNASTY         : __PARAMETERS
__RELPATH         :
__PROPERTY_COUNT  : 6
__DERIVATION      : {}
__SERVER          :
__NAMESPACE       :
__PATH            :
ClusterSize       : 0
EnableCompression : False
FileSystem        : NTFS
Label             :
QuickFormat       : False
Version           : 0
PSComputerName    :
```

このコマンドは、必要なオブジェクトの順序を一覧表示します。 PowerShell 3.0 での WMI の呼び出しは他の方法とは異なり、オブジェクト値を特定の順序で入力する必要があります。

### 例 2: アプリケーションのインスタンスを起動する

```powershell
([Wmiclass]'Win32_Process').GetMethodParameters('Create')
```

```Output
__GENUS                   : 2
__CLASS                   : __PARAMETERS
__SUPERCLASS              :
__DYNASTY                 : __PARAMETERS
__RELPATH                 :
__PROPERTY_COUNT          : 3
__DERIVATION              : {}
__SERVER                  :
__NAMESPACE               :
__PATH                    :
CommandLine               :
CurrentDirectory          :
ProcessStartupInformation :
PSComputerName            :
```

```powershell
Invoke-WmiMethod -Path win32_process -Name create -ArgumentList notepad.exe
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 2
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ProcessId        : 11312
ReturnValue      : 0
PSComputerName   :
```

このコマンドは、Win32_Process クラスのメソッドを呼び出すことによって、メモ帳のインスタンスを起動 `Create` します。 **Win32_Process**

**戻り** 値のプロパティに0が設定され、 **ProcessId** プロパティに整数 (次のプロセス ID 番号) が設定されます (コマンドが完了した場合)。

### 例 3: ファイル名を変更する

```powershell
Invoke-WmiMethod -Path "CIM_DataFile.Name='C:\scripts\test.txt'" -Name Rename -ArgumentList "C:\scripts\test_bu.txt"
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ReturnValue      : 0
```

このコマンドは、ファイル名を変更します。 **Path** パラメーターを使用して、 **CIM_DataFile** クラスのインスタンスを参照します。 次に、その特定のインスタンスに対して Rename メソッドを適用します。

コマンドが完了すると、 **戻り** 値のプロパティに0が設定されます。

### 例 4: を使用して値の配列を渡す `-ArgumentList`

オブジェクトの配列を使用し、 `$binSD` その後に `$null` 値を指定する例。

```powershell
$acl = get-acl test.txt
$binSD = $acl.GetSecurityDescriptorBinaryForm()
Invoke-WmiMethod -class Win32_SecurityDescriptorHelper -Name BinarySDToSDDL -ArgumentList $binSD, $null
```

## PARAMETERS

### -ArgumentList

呼び出したメソッドに渡すパラメーターを指定します。 このパラメーターの値は、オブジェクトの配列である必要があり、呼び出されたメソッドによって要求された順序で表示される必要があります。 `Invoke-CimCommand`コマンドレットには、これらの制限はありません。

これらのオブジェクトを一覧表示する順序を決定するには、 `GetMethodParameters()` このトピックの最後にある例1に示すように、WMI クラスでメソッドを実行します。

> [!IMPORTANT]
> 最初の値が複数の要素を含む配列である場合は、2 つ目の値を $null にする必要があります。 これを指定しないと、"型 'System.Byte' のオブジェクトを型 'System.Array' にキャストできません" などのエラーがコマンドで生成されます。 上記の例4を参照してください。

```yaml
Type: System.Object[]
Parameter Sets: class, object, path
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob

このコマンドレットによってコマンドがバックグラウンドジョブとして実行されることを示します。 完了に時間のかかるコマンドを実行するには、このパラメーターを使用します。

**AsJob** パラメーターを使用すると、バックグラウンド ジョブを表すオブジェクトが返され、その後コマンド プロンプトが表示されます。 ジョブが完了しても、引き続きセッションで作業できます。 `Invoke-WmiMethod`がリモートコンピューターに対して使用されている場合、ジョブはローカルコンピューター上に作成され、リモートコンピューターからの結果は自動的にローカルコンピューターに返されます。 ジョブを管理するには、Job という名詞を含むコマンドレット (Job コマンドレット) を使用します。 ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。

このパラメーターをリモート コンピューターで使用するには、ローカル コンピューターおよびリモート コンピューターをリモート処理用に構成する必要があります。 さらに、windows Vista 以降のバージョンの Windows で [管理者として実行] オプションを使用して Windows PowerShell を起動する必要があります。 詳細については、「about_Remote_Requirements」を参照してください。

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

WMI 接続に使用する認証レベルを指定します。 このパラメーターの有効値は、次のとおりです。

- -1: Unchanged
- 0: Default
- 1: None (認証は行われません)
- 2: Connect (認証は、クライアントとアプリケーションの関係が確立されるときのみ実行されます)
- 3: Call (認証は、アプリケーションが要求を受信するときに各呼び出しの始めにだけ実行されます)
- 4: Packet (認証はクライアントから受信されるすべてのデータで実行されます)
- 5: PacketIntegrity (クライアントとアプリケーション間で転送されるすべてのデータが認証および検証されます)。
- 6: PacketPrivacy (他の認証レベルのプロパティが使用され、すべてのデータが暗号化されます)

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

WMI 接続の認証に使用する機関を指定します。 標準の Windows NT LAN Manager (NTLM) 認証または Kerberos 認証を指定できます。 NTLM を使用するには、認証設定に「ntlmdomain:\<DomainName\>」と指定します。\<DomainName\> には、有効な NTLM ドメイン名を指定します。 Kerberos を使用するには、「kerberos:\<DomainName\ServerName\>」と指定します。 ローカル コンピューターへの接続時に認証設定を指定することもできます。

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

静的な呼び出しメソッドが含まれている WMI クラスを指定します。

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

文字列配列として、このコマンドレットでコマンドを実行するコンピューターを指定します。 既定値はローカル コンピューターです。

1 台または複数のコンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。 ローカルコンピューターを指定するには、コンピューター名、ドット (.)、または localhost を入力します。

このパラメーターは、Windows PowerShell リモート処理に依存しません。 コンピューターがリモート コマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターを使用できます。

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

この処理を実行するアクセス許可を持つユーザー アカウントを指定します。 既定値は現在のユーザーです。 、、などのユーザー名を入力し `User01` `Domain01\User01` `User@Contoso.com` ます。 または、Get-Credential コマンドレットによって返されるオブジェクトなどの **PSCredential** オブジェクトを入力します。 ユーザー名を入力すると、パスワードの入力を促すメッセージが表示されます。

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

コマンドが WMI 呼び出しを行う前に、このコマンドレットによって現在のユーザーのすべての特権が有効になることを示します。

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

使用する偽装レベルを指定します。 このパラメーターの有効値は、次のとおりです。

- 0: Default (既定の偽装レベルのローカル レジストリを読み取ります。通常は "3: Impersonate" に設定されます)
- 1: Anonymous (呼び出し元の資格情報は非表示になります)
- 2: Identify (オブジェクトによる呼び出し元の資格情報のクエリが許可されます)
- 3: Impersonate (オブジェクトによる呼び出し元の資格情報の使用が許可されます)
- 4: Delegate (オブジェクトが呼び出し元の資格情報の使用を他のオブジェクトに許可できるようにします)

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

入力として使用する **system.management.managementobject** オブジェクトを指定します。 このパラメーターを使用すると、 **フラグ** と **引数** のパラメーターを除く他のすべてのパラメーターは無視されます。

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

WMI オブジェクトの優先ロケールを指定します。 **ロケール** パラメーターの値は、形式の配列として `MS_<LCID>` 適切な順序で指定します。

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

### -Name

呼び出すメソッドの名前を指定します。 このパラメーターは必須です。Null や空にはできません。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

このパラメーターを **class** パラメーターと共に使用すると、参照先の wmi クラスまたはオブジェクトが配置されている wmi リポジトリの名前空間を指定します。

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

WMI クラスの WMI オブジェクト パス、または WMI クラスのインスタンスの WMI オブジェクト パスを指定します。 指定するクラスまたはインスタンスには、 **Name** パラメーターに指定されているメソッドが含まれている必要があります。

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

同時に実行できる WMI 操作の数のスロットル値を指定します。
このパラメーターは、 **AsJob** パラメーターと共に使用されます。 スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。

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

### なし

このコマンドレットは入力を受け取りません。

## 出力

### なし

このコマンドレットは出力を生成しません。

## 注

## 関連リンク

[Get-WSManInstance](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[Invoke-WSManAction](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[New-WSManInstance](../Microsoft.WsMan.Management/New-WSManInstance.md)

[Remove-WSManInstance](../Microsoft.WsMan.Management/Remove-WSManInstance.md)

[Get-WmiObject](Get-WmiObject.md)

[Remove-WmiObject](Remove-WmiObject.md)

[Set-WmiInstance](Set-WmiInstance.md)
