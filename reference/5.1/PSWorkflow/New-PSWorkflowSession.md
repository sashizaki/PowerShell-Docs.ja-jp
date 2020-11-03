---
external help file: Microsoft.Powershell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSWorkflow
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/psworkflow/new-psworkflowsession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSWorkflowSession
ms.openlocfilehash: 995dd8a6df3ac8ebd7a204d2aefef3fa6aa71e14
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213363"
---
# New-PSWorkflowSession

## 概要
ワークフロー セッションを作成します。

## SYNTAX

```
New-PSWorkflowSession [[-ComputerName] <String[]>] [-Credential <Object>] [-Name <String[]>] [-Port <Int32>]
 [-UseSSL] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-EnableNetworkAccess]
 [<CommonParameters>]
```

## Description

`New-PSWorkflowSession`コマンドレットは、Windows PowerShell ワークフローを実行するために特に設計されているユーザー管理セッション ( **PSSession** ) を作成します。 スクリプト、型と書式設定ファイル、およびワークフローに必要なオプションが含まれている Microsoft.PowerShell.Workflow セッション構成を使用します。

`New-PSWorkflowSession`またはそのエイリアスであるを使用でき `nwsn` ます。

このコマンドにワークフロー共通パラメーターを追加することもできます。 ワークフロー共通パラメーターの詳細については、「」を参照してください [about_WorkflowCommonParameters](./about/about_WorkflowCommonParameters.md)

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: リモートコンピューターにワークフローセッションを作成する

この例では、ServerNode01 リモートコンピューターに **Workflowtests** セッションを作成します。

```powershell
$params = @{
    ComputerName = "ServerNode01"
    Name = "WorkflowTests"
    SessionOption = (New-PSSessionOption -OutputBufferingMode Drop)
}
New-PSWorkflowSession @params
```

**Sessionoption** パラメーターの値は、セッションの `New-PSSessionOption` 出力バッファーモードを **Drop** に設定するコマンドです。

### 例 2: 複数のリモートコンピューターにワークフローセッションを作成する

この例では、ServerNode01 コンピューターと Server12 コンピューター上にワークフローセッションを作成します。 このコマンドでは、 **Credential** パラメーターを使用して、ドメイン管理者のアクセス権で実行します。

```powershell
"ServerNode01", "Server12" |
    New-PSWorkflowSession -Name WorkflowSession -Credential Domain01\Admin01 -ThrottleLimit 150
```

**ThrottleLimit** パラメーターを使用して、コマンドごとのスロットル制限を 150 に増やします。
この値は、 **Microsoft の PowerShell** のセッション構成で設定されている既定のスロットル制限100よりも優先されます。

## PARAMETERS

### -ApplicationName

接続 URI のアプリケーション名セグメントを指定します。

既定値は、 `$PSSessionApplicationName` ローカルコンピューター上のユーザー設定変数の値です。 このユーザー設定変数が定義されていない場合、既定値は WSMAN です。 この値はほとんどの用途に適しています。 詳細については、「 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)」を参照してください。

WinRM サービスは、アプリケーション名を使用して、接続要求を処理するリスナーを選択します。
このパラメーターの値は、リモート コンピューター上のリスナーの **URLPrefix** プロパティの値に一致している必要があります。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -認証

ユーザー資格情報の認証に使用するメカニズムを指定します。
このパラメーターの有効値は、次のとおりです。

- Default
- Basic
- Credssp
- ダイジェスト
- Kerberos
- ネゴシエート
- NegotiateWithImplicitCredential

既定値は Default です。

CredSSP 認証は、windows Vista、Windows Server 2008、およびそれ以降のバージョンの Windows オペレーティングシステムでのみ使用できます。

このパラメーターの値の詳細については、「 [Authenticationmechanism 列挙型](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。

> [!CAUTION]
> ユーザー資格情報が認証対象のリモートコンピューターに渡される Credential Security Service Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。 このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。 リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。 証明書の拇印を入力します。

証明書は、クライアント証明書ベースの認証で使用されます。 これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。

証明書の拇印を取得するに `Get-Item` は、コマンドレットまたは `Get-ChildItem` Windows PowerShell Cert: ドライブのコマンドレットを使用します。

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

### -ComputerName

指定されたコンピューターへの永続的な接続 ( **PSSession** ) を作成します。 複数のコンピューター名を入力すると、Windows PowerShell は、コンピューターごとに1つ **ずつ、複数の pssession を作成** します。 既定値はローカル コンピューターです。

1 台または複数のリモート コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。 ローカルコンピューターを指定するには、コンピューター名、localhost、またはドット (.) を入力します。 コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名が必要です。 パイプを使用してコンピューター名をに引用符で囲むこともでき `New-PSWorkflowSession` ます。

**ComputerName** パラメーターの値に IP アドレスを使用するには、コマンドに **Credential** パラメーターを含める必要があります。 また、HTTPS トランスポート用にコンピューターを構成するか、リモート コンピューターの IP アドレスをローカル コンピューター上の WinRM TrustedHosts 一覧に含める必要があります。 TrustedHosts の一覧にコンピューター名を追加する手順については、 [about_Remote_Troubleshooting](../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md)の「信頼されたホストの一覧にコンピューターを追加する方法」を参照してください。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Credential

この処理を実行するアクセス許可を持つユーザー アカウントを指定します。 既定値は現在のユーザーです。 User01、Domain01\user01」、などのユーザー名を入力する User@Domain.com か、コマンドレットによって返されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。

ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableNetworkAccess

このコマンドレットが、ループバックセッションに対話型セキュリティトークンを追加することを示します。 対話型トークンを使用すると、他のコンピューターからデータを取得するコマンドをループバック セッションで実行できます。 たとえば、リモート コンピューターからローカル コンピューターに XML ファイルをコピーするコマンドをセッションで実行できます。

ループバックセッションは、同じコンピューター上で発生して終了する **PSSession** です。 ループバックセッションを作成するには、 **ComputerName** パラメーターを指定しないようにするか、値をドット、localhost、またはローカルコンピューターの名前に設定します。

既定では、ネットワークトークンを持つループバックセッションが作成されます。これにより、リモートコンピューターに対して認証を行うための十分なアクセス許可が得られない場合があります。

**EnableNetworkAccess** パラメーターは、ループバック セッションでのみ有効です。 リモートコンピューターでセッションを作成するときに **EnableNetworkAccess** パラメーターを指定すると、コマンドは成功しますが、パラメーターは無視されます。

**Authentication** パラメーターの **CredSSP** 値を使用して、ループバック セッションでリモート アクセスを許可することもできます。その場合、セッションの資格情報が他のコンピューターに委任されます。

悪意のあるアクセスからコンピューターを保護するために、 **EnableNetworkAccess** パラメーターを使用して作成された、対話型トークンを持つ切断されたループバックセッションは、セッションが作成されたコンピューターからのみ再接続することができます。 CredSSP 認証を使用するセッションが切断された場合には、他のコンピューターから再接続することができます。 詳細については、`Disconnect-PSSession` コマンドレットを参照してください。

このパラメーターは Windows PowerShell 3.0 で導入されました。

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

### -Name

ワークフロー セッションのフレンドリ名を指定します。 この名前は、やなどの他のコマンドレットと共に使用でき `Get-PSSession` `Enter-PSSession` ます。 名前は、コンピューターや現在のセッションで一意である必要ありません。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Session#
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

この接続に使用するリモート コンピューター上のネットワーク ポートを指定します。 リモート コンピューターに接続するには、リモート コンピューターで、接続に使用されるポートをリッスンすることが必要です。 既定のポートは 5985 (HTTP の場合は WinRM ポート)、5986 (HTTPS の場合は WinRM ポート) です。

別のポートを使用する前に、そのポートでリッスンするようにリモートコンピューター上の WinRM リスナーを構成する必要があります。 リスナーを構成するには、次のコマンドを使用します。

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

必要な場合を除き、 **Port** パラメーターを使用しないでください。 コマンドのポート設定は、コマンドが実行されるすべてのコンピューターまたはセッションに適用されます。 代替ポートの設定によっては、コマンドがすべてのコンピューターで実行されない場合があります。

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

### -SessionOption

セッションの詳細オプションを指定します。 コマンドレットを使用して作成したものなど、 **Sessionoption** オブジェクトを入力し `New-PSSessionOption` ます。

オプションの既定値は、設定されている場合は、ユーザー設定変数の値によって決まり `$PSSessionOption` ます。 それ以外の場合、既定値はセッション構成で設定されたオプションによって決まります。

セッションオプションの値は、ユーザー設定変数およびセッション構成で設定されたセッションの既定値よりも優先され `$PSSessionOption` ます。 ただし、セッション構成で設定された最大値、クォータ、または制限よりも優先されることはありません。 セッション構成の詳細については、「 [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md)」を参照してください。

既定値を含む、セッションオプションの説明については、「」を参照してください `New-PSSessionOption` 。
ユーザー設定変数の詳細については `$PSSessionOption` 、「 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)」を参照してください。

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

このコマンドを実行するために確立できる最大コンカレント接続数を指定します。
このパラメーターを省略した場合、または値 0 (ゼロ) を入力した場合は、 **Microsoft の PowerShellWorkflow** セッション構成100の既定値が使用されます。

スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSL

このコマンドレットが、リモートコンピューターへの接続を確立するために Secure Sockets Layer (SSL) プロトコルを使用することを示します。 既定では、SSL は使用されません。

WS-Management は、ネットワークを介して転送されるすべての Windows PowerShell コンテンツを暗号化します。 **UseSSL** パラメーターは、HTTP 接続ではなく HTTPS 接続を介してデータを送信する追加の保護です。

このパラメーターを指定しても、コマンドに使用されるポートで SSL を使用できない場合、コマンドは失敗します。

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

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### System...--[], System.string

このコマンドレットには、セッションまたはコンピューター名をパイプすることができます。

## 出力

### システム管理. 実行空間

## 注

`New-PSWorkflowSession`コマンドは、次のコマンドと同等です。

`New-PSSession -ConfigurationName Microsoft.PowerShell.Workflow`

## 関連リンク

[Disconnect-PSSession](../Microsoft.PowerShell.Core/Disconnect-PSSession.md)

[New-PSSession](../Microsoft.PowerShell.Core/New-PSSession.md)

[New-PSSessionOption](../Microsoft.PowerShell.Core/New-PSTransportOption.md)

[Register-PSSessionConfiguration](../Microsoft.PowerShell.Core/Register-PSSessionConfiguration.md)

[about_PSSessions](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md)

[about_Workflows](../PSWorkflow/About/about_Workflows.md)

[about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md)
