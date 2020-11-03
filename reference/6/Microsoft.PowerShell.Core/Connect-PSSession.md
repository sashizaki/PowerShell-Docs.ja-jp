---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/connect-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-PSSession
ms.openlocfilehash: a6a0f0f4778cad3b3f55d408b67f456e3152c83e
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218483"
---
# Connect-PSSession

## 概要
切断されたセッションに再接続します。

## SYNTAX

### 名前 (既定値)

```
Connect-PSSession -Name <String[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Session

```
Connect-PSSession [-Session] <PSSession[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### コンピューター名 Guid

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### [ComputerName]

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ConnectionUriGuid

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ConnectionUri

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceId

```
Connect-PSSession -InstanceId <Guid[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Id

```
Connect-PSSession [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description

接続が切断されたユーザー管理の PowerShell **セッション (** **PSSession** ) に再接続します。
これは意図的に切断されたセッションで機能します。たとえば、Disconnect-PSSession コマンドレットや、Invoke-Command コマンドレットの *Indisconnectedsession* パラメーターを使用したり、一時的なネットワークの停止などによって誤って切断されたセッションを使用したりします。

**接続 PSSession** は、同じユーザーによって開始された切断されたセッションに接続できます。
これには、他のコンピューター上の他のセッションによって開始または切断されたものが含まれます。

ただし、 **接続が** 切断されているか閉じられているセッション、または Enter-PSSession コマンドレットを使用して開始された対話型セッションに接続することはできません。
このほか、別のユーザーが開始したセッションには接続できません。ただし、そのセッションを作成したユーザーの資格情報がある場合には、このコマンドレットを使用した再接続が可能です。

切断されたセッションの機能の詳細については、「about_Remote_Disconnected_Sessions」を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: セッションに再接続する

```
PS C:\> Connect-PSSession -ComputerName Server01 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Opened        ITTasks                  Available
```

このコマンドは、Server01 コンピューターの ITTask セッションに再接続するものです。

出力は、コマンドが成功したことを示しています。
セッションの **状態** が開かれ、 **可用性** が利用可能になっています。これは、セッションでコマンドを実行できることを示しています。

### 例 2: 切断と再接続の影響

```
PS C:\> Get-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available


PS C:\> Get-PSSession | Disconnect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Disconnected  Microsoft.PowerShell          None


PS C:\> Get-PSSession | Connect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available
```

この例では、セッションを切断した後で、改めて同じセッションに接続する効果を示しています。

最初のコマンドは、Get-PSSession コマンドレットを使用します。
*ComputerName* パラメーターを指定しなかった場合には、コマンドは現在のセッションで作成されたセッションのみを取得します。

出力は、ローカル コンピューターの Backups セッションを取得したことを示しています。
セッションの **状態** が開かれ、 **可用性** が使用可能になっています。

2番目のコマンドは、 **Get PSSession** コマンドレットを使用して、現在のセッションで作成された **pssession** オブジェクトを取得します。また、 **pssession** コマンドレットを使用してセッションを切断します。
出力は、Backups セッションが切断されたことを示しています。
セッションの **状態** は Disconnected であり、 **Availability** は None です。

3番目のコマンドは、 **Get PSSession** コマンドレットを使用して、現在のセッションで作成された **PSSession** オブジェクトを取得し、 **接続 pssession** コマンドレットを使用してセッションを再接続します。
出力は、Backups セッションに再接続したことを示しています。
セッションの **状態** が開かれ、 **可用性** が使用可能になっています。

切断されていないセッションで **接続の PSSession** コマンドレットを使用すると、このコマンドはセッションに影響を与えず、エラーも生成されません。

### 例 3: エンタープライズシナリオにおける一連のコマンド

```
The administrator starts by creating a sessions on a remote computer and running a script in the session.The first command uses the **New-PSSession** cmdlet to create the ITTask session on the Server01 remote computer. The command uses the *ConfigurationName* parameter to specify the ITTasks session configuration. The command saves the sessions in the $s variable.
PS C:\> $s = New-PSSession -ComputerName Server01 -Name ITTask -ConfigurationName ITTasks

 The second command **Invoke-Command** cmdlet to start a background job in the session in the $s variable. It uses the *FilePath* parameter to run the script in the background job.
PS C:\> Invoke-Command -Session $s {Start-Job -FilePath \\Server30\Scripts\Backup-SQLDatabase.ps1}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Running       True            Server01             \\Server30\Scripts\Backup...

The third command uses the Disconnect-PSSession cmdlet to disconnect from the session in the $s variable. The command uses the *OutputBufferingMode* parameter with a value of Drop to prevent the script from being blocked by having to deliver output to the session. It uses the *IdleTimeoutSec* parameter to extend the session time-out to 15 hours.When the command is completed, the administrator locks her computer and goes home for the evening.
PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None

Later that evening, the administrator starts her home computer, logs on to the corporate network, and starts PowerShell. The fourth command uses the Get-PSSession cmdlet to get the sessions on the Server01 computer. The command finds the ITTask session.The fifth command uses the **Connect-PSSession** cmdlet to connect to the ITTask session. The command saves the session in the $s variable.
PS C:\> Get-PSSession -ComputerName Server01 -Name ITTask

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None


PS C:\> $s = Connect-PSSession -ComputerName Server01 -Name ITTask


Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Opened        ITTasks               Available

The sixth command uses the **Invoke-Command** cmdlet to run a Get-Job command in the session in the $s variable. The output shows that the job finished successfully.The seventh command uses the **Invoke-Command** cmdlet to run a Receive-Job command in the session in the $s variable in the session. The command saves the results in the $BackupSpecs variable.The eighth command uses the **Invoke-Command** cmdlet to runs another script in the session. The command uses the value of the $BackupSpecs variable in the session as input to the script.


PS C:\> Invoke-Command -Session $s {Get-Job}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Completed     True            Server01             \\Server30\Scripts\Backup...

PS C:\> Invoke-Command -Session $s {$BackupSpecs = Receive-Job -JobName Job2}

PS C:\> Invoke-Command -Session $s {\\Server30\Scripts\New-SQLDatabase.ps1 -InitData $BackupSpecs.Initialization}

The ninth command disconnects from the session in the $s variable.The administrator closes PowerShell and closes the computer. She can reconnect to the session on the next day and check the script status from her work computer.
PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None
```

この一連のコマンドは、エンタープライズで **Connect-PSSession** コマンドレットを使用する方法の一例を示したものです。
この例では、システム管理者がリモート コンピューター上のセッションで、実行時間の長いジョブを開始します。
管理者はジョブを開始した後、セッションを切断し、帰宅します。
その後、管理者が自宅のコンピューターにログオンし、ジョブが完了するまで実行されたことを確認します。

## PARAMETERS

### -AllowRedirection

このコマンドレットがこの接続を代替 URI にリダイレクトできることを示します。

*ConnectionURI* パラメーターを使用すると、リモートの送信先は別の URI にリダイレクトするように指示を返すことができます。
既定では、PowerShell は接続をリダイレクトしませんが、このパラメーターを使用して接続をリダイレクトすることができます。

また、 **MaximumConnectionRedirectionCount** セッション オプション値を変更することで、接続をリダイレクトする回数を制限することもできます。
New-PSSessionOption コマンドレットの *Maximumredirection* パラメーターを使用するか、 **$PSSessionOption** ユーザー設定変数の **MaximumConnectionRedirectionCount** プロパティを設定します。
既定値は 5 です。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName

アプリケーションの名前を指定します。
このコマンドレットは、指定されたアプリケーションを使用するセッションにのみ接続します。

接続 URI のアプリケーション名セグメントを入力します。
たとえば、次の接続 URI では、アプリケーション名は WSMan: `http://localhost:5985/WSMAN` です。
セッションのアプリケーション名は、セッションの **Runspace.ConnectionInfo.AppName** プロパティに保存されています。

このパラメーター値は、セッションを選択してフィルター処理するために使用されます。
セッションが使用するアプリケーションが変更されることはありません。

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -認証

切断されたセッションに再接続するためにコマンドでユーザー資格情報を認証するために使用するメカニズムを指定します。 このパラメーターの有効値は、次のとおりです。

- Default
- Basic
- Credssp
- ダイジェスト
- Kerberos
- ネゴシエート
- NegotiateWithImplicitCredential

既定値は Default です。

このパラメーターの値の詳細については、MSDN ライブラリの「 [Authenticationmechanism 列挙型](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) 」を参照してください。

注意: ユーザーの資格情報が認証対象のリモートコンピューターに渡される Credential Security Support Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。
このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。
リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

切断されたセッションに接続するためのアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。 証明書の拇印を入力します。

証明書は、クライアント証明書ベースの認証で使用されます。
ローカルユーザーアカウントにのみマップできます。
ドメインアカウントでは機能しません。

証明書の拇印を取得するには、PowerShell Cert: ドライブで Get-Item または Get-ChildItem コマンドを使用します。

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

切断されたセッションが格納されているコンピューターを指定します。
セッションは、接続のサーバー側または受信側のコンピューターに格納されます。
既定値はローカル コンピューターです。

コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。
ワイルドカード文字は使用できません。
ローカルコンピューターを指定するには、コンピューター名、localhost、またはドット (.) を入力します。

```yaml
Type: System.String[]
Parameter Sets: ComputerNameGuid, ComputerName
Aliases: Cn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationName

指定したセッション構成を使用するセッションにのみ接続します。

セッション構成の構成名または完全修飾リソース URI を入力します。
構成名だけを指定した場合は、次のスキーマ URI が付加され `http://schemas.microsoft.com/powershell` ます。
セッションの構成名は、セッションの **ConfigurationName** プロパティに保存されています。

このパラメーター値は、セッションを選択してフィルター処理するために使用されます。
セッションが使用するセッション構成が変更されることはありません。

セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionUri

切断されたセッションの接続エンドポイントの Uri を指定します。

URI は完全修飾名にする必要があります。
この文字列の形式は次のとおりです。

`\<Transport\>://\<ComputerName\>:\<Port\>/\<ApplicationName\>`

既定値は、次のとおりです。

`http://localhost:5985/WSMAN`

接続 URI を指定しない場合は、 *UseSSL* パラメーターと *Port* パラメーターを使用して接続 uri の値を指定できます。

URI の **Transport** セグメントの有効な値は、HTTP および HTTPS です。
トランスポートセグメントを使用して接続 URI を指定し、ポートを指定しない場合、セッションは標準ポート80で HTTP 用および 443 (HTTPS 用) で作成されます。
PowerShell リモート処理に既定のポートを使用するには、HTTP の場合はポート5985、HTTPS の場合は5986を指定します。

対象のコンピューターが接続を別の URI にリダイレクトする場合、コマンドで *Allowredirection* パラメーターを使用しない限り、PowerShell によってリダイレクトが禁止されます。

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUri, ConnectionUriGuid
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

切断されたセッションに接続するためのアクセス許可を持つユーザー アカウントを指定します。
既定値は現在のユーザーです。

**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。 ユーザー名を入力すると、パスワードを入力するように求められます。

資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。

> [!NOTE]
> **SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

切断されたセッションの ID を指定します。
*Id* パラメーターは、切断されたセッションが現在のセッションに既に接続されている場合にのみ機能します。

このパラメーターは、セッションがローカル コンピューター上に保存されているものの、現在のセッションに接続されていなかった場合には、有効でありながら効力を発揮しません。

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

切断されたセッションのインスタンス ID を指定します。

インスタンス ID は、ローカルコンピューターまたはリモートコンピューター上の **PSSession** を一意に識別する GUID です。

インスタンス ID は、 **PSSession** の **InstanceID** プロパティに格納されます。

```yaml
Type: System.Guid[]
Parameter Sets: ComputerNameGuid, ConnectionUriGuid, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

切断されたセッションのフレンドリ名を指定します。

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri
Aliases:

Required: True (Name), False (ComputerName, ConnectionUri)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

セッションに再接続するときに使用するリモート コンピューターのネットワーク ポートを指定します。
リモート コンピューターに接続するには、リモート コンピューターで、接続に使用されるポートをリッスンすることが必要です。
既定のポートは5985で、これは HTTP 用の WinRM ポート、および HTTPS 用の WinRM ポートである5986です。

代替ポートを使用する前に、そのポートでリッスンするようにリモート コンピューター上の WinRM リスナーを構成する必要があります。
リスナーを構成するには、PowerShell プロンプトで次の2つのコマンドを入力します。

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

必要な場合を除き、 *Port* パラメーターを使用しないでください。
コマンドに設定されているポートは、コマンドが実行されるすべてのコンピューターまたはセッションに適用されます。
代替ポートの設定によっては、コマンドがすべてのコンピューターで実行されない場合があります。

```yaml
Type: System.Int32
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -セッション

切断されたセッションを指定します。
**Pssession** オブジェクトを含む変数、または Get-PSSession コマンドなどの **pssession** オブジェクトを作成または取得するコマンドを入力します。

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SessionOption

セッションの詳細オプションを指定します。
New-PSSessionOption コマンドレットを使用して作成する **sessionoption** オブジェクト、またはキーがセッションオプションの名前で、値がセッションオプションの値であるハッシュテーブルを入力します。

オプションの既定値は、$PSSessionOption ユーザー設定変数が設定されている場合は、その値によって決まります。
それ以外の場合、既定値はセッション構成で設定されたオプションによって決まります。

セッション オプションの値は、$PSSessionOption ユーザー設定変数およびセッション構成で設定されたセッションの既定値よりも優先されます。
ただし、セッション構成で設定された最大値、クォータ、または制限よりも優先されることはありません。

既定値を含むセッションオプションの説明については、「New-PSSessionOption」を参照してください。
**$PSSessionOption** ユーザー設定変数の詳細については、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。
セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
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

### -UseSSL

このコマンドレットが、切断されたセッションに接続するために Secure Sockets Layer (SSL) プロトコルを使用することを示します。 既定では、SSL は使用されません。

WS-Management は、ネットワーク経由で送信されるすべての PowerShell コンテンツを暗号化します。
*UseSSL* パラメーターは、HTTP 接続ではなく HTTPS 接続を介してデータを送信する追加の保護です。

このパラメーターを使用しても、コマンドに使用されているポートで SSL を使用できない場合、コマンドは失敗します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameGuid, ComputerName
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

### システム管理. 実行空間

パイプを使用してセッション ( **PSSession** ) をこのコマンドレットに送ることができます。

## 出力

### システム管理. 実行空間

このコマンドレットは、再接続先のセッションを表すオブジェクトを返します。

## 注

* **接続** が切断されているセッション、つまり **State** プロパティの値が disconnected のセッションにのみ再接続します。 Windows PowerShell 3.0 以降のバージョンを実行しているコンピューターに接続されている、または終了したセッションのみを切断し、再接続することができます。
* 切断されていないセッションで **接続-PSSession** を使用すると、このコマンドはセッションに影響を与えず、エラーを生成しません。
* *EnableNetworkAccess* パラメーターを使用して作成された対話型トークンを使用して切断されたループバックセッションは、セッションが作成されたコンピューターからのみ再接続できます。 この制約は、悪意のあるアクセスからコンピューターを保護するためのものです。
* **PSSession** の **State** プロパティの値は、現在のセッションを基準としています。
したがって、値が **Disconnected** の場合は、 **PSSession** が現在のセッションに接続されていないことを意味します。 ただし、 **PSSession** がすべてのセッションから切断されているわけではありません。 別のセッションに接続されている可能性があるためです。 セッションに接続または再接続できるかどうかを確認するには、 **Availability** プロパティを使用します。

  **Availability** の値が None の場合は、セッションに接続できることを示します。
値が Busy の場合は、PSSession が別のセッションに接続されているため、 **PSSession** に接続できないことを示します。

  セッションの **State** プロパティの値の詳細については、MSDN ライブラリの「 [RunspaceState 列挙型](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) 」を参照してください。

  セッションの **Availability** プロパティの値の詳細については、MSDN ライブラリの「 [RunspaceAvailability 列挙型](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) 」を参照してください。

* Pssession に接続するときに、 **pssession** のアイドルタイムアウト値を変更することはできませ **ん。** *Connect-PSSession* の **SessionOption** パラメーターは、 **IdleTimeout** の値が設定されている **SessionOption** オブジェクトを受け取ります。 ただし、 **Sessionoption** オブジェクトの **idletimeout** 値と $PSSessionOption 変数の **idletimeout** 値は、 **PSSession** に接続するときには無視されます。

  Pssession の **作成時に pssession の** アイドル **タイムアウトを設定** および変更するには、pssession コマンドレットまたは **コマンド** レットを使用 **するか、** **pssession** から切断します。

  **PSSession** の **IdleTimeout** プロパティは、切断されたセッションをリモートコンピューターで保持する期間を決定するため、切断されたセッションにとって重要です。
セッションが切断されると、その時点からアイドル状態であると判断されます。これは、そのセッションでコマンドを実行している場合であっても同じです。

## 関連リンク

[Disconnect-PSSession](Disconnect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSession](New-PSSession.md)

[New-PSSessionOption](New-PSSessionOption.md)

[New-PSSessionOption](New-PSTransportOption.md)

[Receive-PSSession](Receive-PSSession.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Remove-PSSession](Remove-PSSession.md)
