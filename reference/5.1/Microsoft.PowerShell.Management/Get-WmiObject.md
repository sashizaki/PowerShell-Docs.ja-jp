---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmiObject
ms.openlocfilehash: ed759ff3d0dd35cd55f9dac5a2d76e36eac4dc6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215392"
---
# Get-WmiObject

## 概要
Windows Management Instrumentation (WMI) クラスのインスタンスまたは使用可能なクラスに関する情報を取得します。

## SYNTAX

### query (既定値)

```
Get-WmiObject [-Class] <String> [[-Property] <String[]>] [-Filter <String>] [-Amended] [-DirectRead]
 [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### list

```
Get-WmiObject [[-Class] <String>] [-Recurse] [-Amended] [-List] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### WQLQuery

```
Get-WmiObject [-Amended] [-DirectRead] -Query <String> [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### class

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### path

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

## Description

PowerShell 3.0 以降では、このコマンドレットはに置き換えられてい `Get-CimInstance` ます。

この `Get-WmiObject` コマンドレットは、wmi クラスのインスタンス、または使用可能な wmi クラスに関する情報を取得します。 リモート コンピューターを指定するには、 **ComputerName** パラメーターを使用します。 **List** パラメーターを指定すると、指定された名前空間内で使用可能な WMI クラスに関する情報を取得できます。 **Query** パラメーターを指定すると、WMI Query Language (WQL) ステートメントが実行されます。

`Get-WmiObject`コマンドレットは、リモート操作を実行するために Windows PowerShell リモート処理を使用しません。
**ComputerName** `Get-WmiObject` コンピューターが windows powershell リモート処理の要件を満たしていない場合や、windows powershell のリモート処理用に構成されていない場合でも、コマンドレットの ComputerName パラメーターを使用できます。

Windows PowerShell 3.0 以降では、を返すオブジェクトの **__Server** プロパティには、 `Get-WmiObject` **PSComputerName** エイリアスがあります。 これにより、ソース コンピューター名を出力およびレポートに簡単に含められるようになりました。

## 例

### 例 1: ローカルコンピューター上のプロセスを取得する

この例では、ローカルコンピューター上のプロセスを取得します。

```powershell
Get-WmiObject -Class Win32_Process
```

### 例 2: リモートコンピューター上のサービスを取得する

この例では、リモートコンピューター上のサービスを取得します。 **ComputerName** パラメーターは、リモートコンピューターの IP アドレスを指定します。 既定では、現在のユーザーアカウントは、リモートコンピューターの **Administrators** グループのメンバーである必要があります。

```powershell
Get-WmiObject -Class Win32_Service -ComputerName 10.1.4.62
```

### 例 3: ローカルコンピューターのルートまたは既定の名前空間で WMI クラスを取得する

この例では、ローカルコンピューターのルートまたは既定の名前空間にある WMI クラスを取得します。

```powershell
Get-WmiObject -Namespace "root/default" -List
```

### 例 4: 複数のコンピューター上の名前付きサービスを取得する

この例では、 **ComputerName** パラメーターの値によって指定されたコンピューター上の WinRM サービスを取得します。

```powershell
Get-WmiObject -Query "select * from win32_service where name='WinRM'" -ComputerName Server01, Server02 |
  Format-List -Property PSComputerName, Name, ExitCode, Name, ProcessID, StartMode, State, Status
```

```Output
PSComputerName : SERVER01
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 844
StartMode      : Auto
State          : Running
Status         : OK

PSComputerName : SERVER02
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 932
StartMode      : Auto
State          : Running
Status         : OK
```

出力はパイプライン演算子 (|) によって `Format-List` コマンドレットに送られ、 **PSComputerName** プロパティが既定の出力に追加されます。 **PSComputerName** は、が返すオブジェクトの **__Server** プロパティのエイリアスです `Get-WmiObject` 。 このエイリアスは、PowerShell 3.0 で導入されました。

### 例 5: リモートコンピューター上のサービスを停止する

この例では、リモートコンピューター上の WinRM サービスを停止します。 `Get-WmiObject` Server01 上の WinRM サービスオブジェクトのインスタンスを取得します。 次に、そのオブジェクトの **Win32_Service** WMI クラスの **stopservice** メソッドを呼び出します。

```powershell
(Get-WmiObject -Class Win32_Service -Filter "name='WinRM'" -ComputerName Server01).StopService()
```

これは、コマンドレットを使用することと同じです `Stop-Service` 。

### 例 6: ローカルコンピューターの BIOS を取得する

この例では、ローカルコンピューターから BIOS 情報を取得します。 コマンドレットの **Property** パラメーターを使用して、 `Format-List` 返されたオブジェクトのすべてのプロパティを一覧に表示します。 既定では、構成ファイルで定義されているプロパティのサブセットのみ `Types.ps1xml` が表示されます。

```powershell
Get-WmiObject -Class Win32_Bios | Format-List -Property *
```

```Output
Status                : OK
Name                  : Phoenix ROM BIOS PLUS Version 1.10 A05
Caption               : Phoenix ROM BIOS PLUS Version 1.10 A05
SMBIOSPresent         : True
__GENUS               : 2
__CLASS               : Win32_BIOS
__SUPERCLASS          : CIM_BIOSElement
__DYNASTY             : CIM_ManagedSystemElement
__RELPATH             : Win32_BIOS.Name="Phoenix ROM BIOS PLUS Version 1.10
__PROPERTY_COUNT      : 27
__DERIVATION          : {CIM_BIOSElement, CIM_SoftwareElement, CIM_LogicalElement,
__SERVER              : Server01
__NAMESPACE           : root\cimv2
__PATH                : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
BiosCharacteristics   : {7, 9, 10, 11...}
BIOSVersion           : {DELL   - 15, Phoenix ROM BIOS PLUS Version 1.10 A05}
BuildNumber           :
CodeSet               :
CurrentLanguage       : en|US|iso8859-1
Description           : Phoenix ROM BIOS PLUS Version 1.10 A05
IdentificationCode    :
InstallableLanguages  : 1
InstallDate           :
LanguageEdition       :
ListOfLanguages       : {en|US|iso8859-1}
Manufacturer          : Dell Inc.
OtherTargetOS         :
PrimaryBIOS           : True
ReleaseDate           : 20101103000000.000000+000
SerialNumber          : 8VDM9P1
SMBIOSBIOSVersion     : A05
SMBIOSMajorVersion    : 2
SMBIOSMinorVersion    : 6
SoftwareElementID     : Phoenix ROM BIOS PLUS Version 1.10 A05
SoftwareElementState  : 3
TargetOperatingSystem : 0
Version               : DELL   - 15
Scope                 : System.Management.ManagementScope
Path                  : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
Options               : System.Management.ObjectGetOptions
ClassPath             : \\JUNE-PC\root\cimv2:Win32_BIOS
Properties            : {BiosCharacteristics, BIOSVersion, BuildNumber, Caption...}
SystemProperties      : {__GENUS, __CLASS, __SUPERCLASS, __DYNASTY...}
Qualifiers            : {dynamic, Locale, provider, UUID}
Site                  :
Container             :
```

### 例 7: リモートコンピューター上のサービスを取得する

この例では、コマンドレットの **Credential** パラメーターを使用して、 `Get-WmiObject` リモートコンピューター上のサービスを取得します。 **Credential** パラメーターの値は、ユーザー アカウント名です。 ユーザーにパスワードの入力を求めるメッセージが表示されます。

```powershell
Get-WmiObject Win32_Service -Credential FABRIKAM\administrator -ComputerName Fabrikam
```

> [!NOTE]
> ローカルコンピューターをターゲットにしている場合は、資格情報を使用できません。

## PARAMETERS

### -修正済み

変更された情報を WMI から返されるオブジェクトに含めるかどうかを指定する値を取得または設定します。 通常、変更された情報は、オブジェクトやプロパティの説明など、WMI オブジェクトに付属するローカライズ可能な情報です。

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

### -AsJob

バックグラウンド ジョブとしてコマンドを実行します。 完了に時間のかかるコマンドを実行するには、このパラメーターを使用します。

**AsJob** パラメーターを使用すると、バックグラウンド ジョブを表すオブジェクトが返され、その後コマンド プロンプトが表示されます。 ジョブが完了しても、引き続きセッションで作業できます。 `Get-WmiObject`がリモートコンピューターで使用されている場合、ジョブはローカルコンピューター上に作成され、リモートコンピューターからの結果は自動的にローカルコンピューターに返されます。 ジョブを管理するには、"Job" を含むコマンドレットを使用します。 ジョブの結果を取得するには、`Receive-Job` コマンドレットを使用します。

> [!NOTE]
> このパラメーターをリモート コンピューターで使用するには、ローカル コンピューターおよびリモート コンピューターをリモート処理用に構成する必要があります。 さらに、Windows Vista 以降のバージョンの Windows では、[管理者として実行] を使用して Windows PowerShell を起動する必要があります。 詳細については、「[about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md)」を参照してください。

Windows PowerShell のバックグラウンドジョブの詳細については、「 [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md) 」および「 [about_Remote_Jobs](../Microsoft.PowerShell.Core/about/about_Remote_Jobs.md)」を参照してください。

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
有効な値は次のとおりです。

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
Parameter Sets: (All)
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authority

WMI 接続の認証に使用する機関を指定します。 標準の NTLM 認証または Kerberos 認証を指定できます。 NTLM を使用するには、authority 設定をに設定し `ntlmdomain:<DomainName>` ます。ここで、は `<DomainName>` 有効な ntlm ドメイン名を示します。 Kerberos を使用するには、を指定し `kerberos:<DomainName>\<ServerName>` ます。 ローカル コンピューターへの接続時に認証設定を指定することもできます。

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

### -クラス

WMI クラスの名前を指定します。 このパラメーターを使用した場合は、WMI クラスのインスタンスが返されます。

```yaml
Type: System.String
Parameter Sets: query, list
Aliases: ClassName

Required: True (query), False (list)
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

管理操作のターゲット コンピューターを指定します。 完全修飾ドメイン名 (FQDN)、NetBIOS 名、または IP アドレスを入力します。 リモート コンピューターがローカル コンピューターとは異なるドメインにある場合は、完全修飾ドメイン名が必要です。

既定値はローカル コンピューターです。 コンピューター名の一覧などでローカル コンピューターを指定するには、「localhost」、ローカル コンピューター名、またはドット (.) を使用します。

このパラメーターは、WS-Management を使用する Windows PowerShell リモート処理に依存しません。 **ComputerName** `Get-WmiObject` コンピューターがリモートコマンド WS-Management 実行するように構成されていない場合でも、の ComputerName パラメーターを使用できます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

この処理を実行するアクセス許可を持つユーザー アカウントを指定します。 既定値は現在のユーザーです。 「User01」、「Domain01\user01」」、「」などのユーザー名を入力し User@Contoso.com ます。 または、  コマンドレットで返されるような `Get-Credential` オブジェクトを入力します。 ユーザー名を入力すると、パスワードの入力を促すメッセージが表示されます。 ローカルコンピューターをターゲットにしている場合は、資格情報を使用できません。

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

### -DirectRead

基底クラスまたは派生クラスに関係なく、指定したクラスには WMI プロバイダーへの直接アクセスが必要かどうかを指定します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: query, WQLQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAllPrivileges

コマンドが WMI 呼び出しを実行する前に、現在のユーザーのすべての特権を有効にします。

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

### -Filter

フィルターとして使用する **Where** 句を指定します。 WMI Query Language (WQL) の構文を使用します。

> [!IMPORTANT]
> パラメーターの値には **Where** キーワードを含めないでください。 たとえば、次のコマンドは、 **Where** キーワードを使用しないで、 **DeviceID** が "c:" の論理ディスクと名前が "WinRM" のサービスのみを返します。

`Get-WmiObject Win32_LogicalDisk -filter "DeviceID = 'c:' "`

`Get-WmiObject win32_service -filter "name='WinRM'"`

```yaml
Type: System.String
Parameter Sets: query
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

- 0: Default。 既定の偽装レベルのローカルレジストリを読み取ります。 既定値は、通常、 **Impersonate** に設定されています。
- 1: Anonymous。 呼び出し元の資格情報は非表示になります。
- 2: Identify。 オブジェクトによる呼び出し元の資格情報のクエリが許可されます。
- 3: Impersonate。 オブジェクトによる呼び出し元の資格情報の使用が許可されます。
- 4: Delegate。 オブジェクトが呼び出し元の資格情報の使用を他のオブジェクトに許可できるようにします。

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -List

**Namespace** パラメーターで指定された、WMI リポジトリ名前空間にある WMI クラスの名前を取得します。

**List** パラメーターを指定しても、 **Namespace** パラメーターを指定しない場合、では `Get-WmiObject` 既定で **Root\Cimv2** 名前空間が使用されます。 このコマンドレットは、既定の名前空間を決定するために、レジストリキーの既定の **名前空間** レジストリエントリを使用しません `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WBEM\Scripting` 。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ロケール

WMI オブジェクトの優先ロケールを指定します。
値を MS_\<LCID\> 形式で入力します。

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

### -Namespace

**Class** パラメーターと共に使用する場合、 **Namespace** パラメーターは、指定された WMI クラスがある WMI リポジトリ名前空間を指定します。 **List** パラメーターと共に使用する場合は、WMI クラス情報を収集する名前空間を指定します。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -プロパティ

このコマンドレットが情報を取得する WMI クラスのプロパティを指定します。 プロパティ名を入力します。

```yaml
Type: System.String[]
Parameter Sets: query
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Query

指定された WMI Query Language (WQL) のステートメントを実行します。 このパラメーターは、イベント クエリをサポートしていません。

```yaml
Type: System.String
Parameter Sets: WQLQuery
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -再帰

**Class** パラメーターで指定されたクラス名を現在の名前空間および他のすべての名前空間で検索します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

同時に実行できる WMI 操作の最大数を指定します。 このパラメーターは、 **AsJob** パラメーターがコマンドで使用されている場合にのみ有効です。

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

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし

入力をにパイプすることはできません `Get-WmiObject` 。

## 出力

### PSObject または system.servicemodel. RemotingJob

**AsJob** パラメーターを使用すると、コマンドレットはジョブ オブジェクトを返します。 それ以外の場合、 `Get-WmiObject` を返すオブジェクトは、 **Class** パラメーターの値によって異なります。

## 注

リモート コンピューターの WMI 情報にアクセスするには、リモート コンピューターのローカル管理者グループに属しているアカウントでこのコマンドレットを実行する必要があります。 また、リモート リポジトリの WMI 名前空間に対する既定のアクセス制御を変更して、他のアカウントにアクセス権を許可する方法もあります。

既定では、各 WMI クラスの一部のプロパティのみが表示されます。 各 WMI クラスで表示されるプロパティのセットは、構成ファイル Types.ps1xml で指定します。 WMI オブジェクトのすべてのプロパティを取得するに `Get-Member` は、 `Format-List` コマンドレットまたはコマンドレットを使用します。

## 関連リンク

[Invoke-WmiMethod](Invoke-WmiMethod.md)

[Remove-WmiObject](Remove-WmiObject.md)

[Set-WmiInstance](Set-WmiInstance.md)

[Get-WSManInstance](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[Invoke-WSManAction](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[New-WSManInstance](../Microsoft.WsMan.Management/New-WSManInstance.md)

[Remove-WSManInstance](../Microsoft.WsMan.Management/Remove-WSManInstance.md)
