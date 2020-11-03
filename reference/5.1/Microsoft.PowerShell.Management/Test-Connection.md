---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: a8d3923db69a20cfada58391944b592cf999e6ef
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214336"
---
# Test-Connection

## 概要
ICMP エコー要求パケット (ping) を1台以上のコンピューターに送信します。

## SYNTAX

### 既定値 (既定値)

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-TimeToLive <Int32>]
 [-Delay <Int32>] [<CommonParameters>]
```

### source

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Credential <PSCredential>] [-Source] <String[]> [-Impersonation <ImpersonationLevel>]
 [-ThrottleLimit <Int32>] [-TimeToLive <Int32>] [-Delay <Int32>] [<CommonParameters>]
```

### 静的

```
Test-Connection [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-TimeToLive <Int32>] [-Delay <Int32>] [-Quiet]
 [<CommonParameters>]
```

## Description

`Test-Connection`コマンドレットは、インターネット制御メッセージプロトコル (ICMP) エコー要求パケット (ping) を1つ以上のリモートコンピューターに送信し、エコー応答応答を返します。 このコマンドレットを使用すると、特定のコンピューターに IP ネットワーク経由で接続できるかどうかを判断できます。

のパラメーターを使用し `Test-Connection` て、送信側と受信側の両方のコンピューターの指定、バックグラウンドジョブとしてのコマンドの実行、タイムアウトと ping の回数の設定、および接続と認証の構成を行うことができます。

使い慣れた **ping** コマンドとは異なり、は `Test-Connection` PowerShell で調査できる **Win32_PingStatus** オブジェクトを返します。 **Quiet** パラメーターは、テストされた各接続の **ブール値を** **system.string オブジェクトで返します。** 複数の接続がテストされている場合は、 **ブール** 値の配列が返されます。

## 例

### 例 1: リモートコンピューターにエコー要求を送信する

この例では、エコー要求パケットをローカルコンピューターから Server01 コンピューターに送信します。

```powershell
Test-Connection -ComputerName Server01
```

```Output
Source        Destination     IPV4Address     IPV6Address  Bytes    Time(ms)
------        -----------     -----------     -----------  -----    --------
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       1
```

`Test-Connection`**ComputerName** パラメーターを使用して、Server01 コンピューターを指定します。

### 例 2: 複数のコンピューターにエコー要求を送信する

この例では、ローカルコンピューターから複数のリモートコンピューターに ping を送信します。

```powershell
Test-Connection -ComputerName Server01, Server02, Server12
```

### 例 3: 複数のコンピューターからコンピューターにエコー要求を送信する

この例では、別のソースコンピューターから1台のリモートコンピューター Server01 に ping を送信します。

```powershell
Test-Connection -Source Server02, Server12, localhost -ComputerName Server01 -Credential Domain01\Admin01
```

`Test-Connection` は、 **Credential** パラメーターを使用して、ソースコンピューターから ping 要求を送信するアクセス許可を持つユーザーの資格情報を指定します。 複数のポイントからの接続の待機時間をテストするには、このコマンド形式を使用します。

### 例 4: パラメーターを使用してテストコマンドをカスタマイズする

この例では、のパラメーターを使用し `Test-Connection` て、コマンドをカスタマイズします。 ローカルコンピューターからリモートコンピューターに ping テストが送信されます。

```powershell
Test-Connection -ComputerName Server01 -Count 3 -Delay 2 -TTL 255 -BufferSize 256 -ThrottleLimit 32
```

`Test-Connection`**ComputerName** パラメーターを使用して Server01 を指定します。 **Count** パラメーターは、3秒間隔の **遅延** で Server01 コンピューターに送信される3つの ping を指定します。

これらのオプションは、ホップ数の増加またはトラフィックの多いネットワーク状態が原因で ping 応答が通常よりも長くかかることが予想される場合に使用できます。

### 例 5: バックグラウンドジョブとしてテストを実行する

この例では、 `Test-Connection` PowerShell バックグラウンドジョブとしてコマンドを実行する方法を示します。

```powershell
$job = Test-Connection -ComputerName (Get-Content Servers.txt) -AsJob
if ($job.JobStateInfo.State -ne "Running") {$Results = Receive-Job $job}
```

コマンドは、 `Test-Connection` 企業内の多くのコンピューターに ping を実行します。 **ComputerName** パラメーターの値は `Get-Content` 、からコンピューター名の一覧を読み取るコマンドです `Servers.txt file` 。 このコマンドは、 **AsJob** パラメーターを使用して、バックグラウンドジョブとしてコマンドを実行し、そのジョブを変数に保存し `$job` ます。

コマンドは、 `if` ジョブがまだ実行されていないことを確認します。 ジョブが実行されていない場合は、 `Receive-Job` 結果を取得して変数に格納し `$Results` ます。

### 例 6: 資格情報を使用してリモートコンピューターに Ping を実行する

このコマンドは、 `Test-Connection` コマンドレットを使用してリモートコンピューターに ping を実行します。

```powershell
Test-Connection Server55 -Credential Domain55\User01 -Impersonation Identify
```

このコマンドは、 **Credential** パラメーターを使用して、リモートコンピューターに ping を実行するアクセス許可を持つユーザーアカウントを指定し、 **impersonation** パラメーターを使用して偽装レベルを **識別** するように変更します。

### 例 7: 接続テストが成功した場合にのみセッションを作成する

この例では、コンピューターに送信された ping の少なくとも1つが成功した場合にのみ、Server01 コンピューターでセッションを作成します。

```powershell
if (Test-Connection -ComputerName Server01 -Quiet) {New-PSSession Server01}
```

このコマンドは、コマンド `if` レットを使用して `Test-Connection` 、Server01 コンピューターに ping を実行します。 このコマンドは、 **Win32_PingStatus** オブジェクトではなく **ブール** 値を返す **Quiet** パラメーターを使用します。 `$True`4 つの ping のいずれかが成功した場合、値はになります。それ以外の場合はです `$False` 。

コマンドが `Test-Connection` 値を返す場合 `$True` 、コマンドはコマンドレットを使用して `New-PSSession` **PSSession** を作成します。

## PARAMETERS

### -AsJob

このコマンドレットがバックグラウンドジョブとして実行されることを示します。

このパラメーターを使用するには、ローカルコンピューターとリモートコンピューターがリモート処理用に構成されている必要があります。 windows Vista 以降のバージョンの Windows オペレーティングシステムでは、[ **管理者として実行** ] オプションを使用して PowerShell を開く必要があります。 詳細については、「[about_Remote_Requirements](../microsoft.powershell.core/about/about_remote_requirements.md)」を参照してください。

**AsJob** パラメーターを指定すると、コマンドは、バックグラウンドジョブを表すオブジェクトを直ちに返します。 ジョブが完了しても、引き続きセッションで作業できます。 ジョブは、ローカル コンピューターで作成され、リモート コンピューターでの結果は自動的にローカル コンピューターに返されます。 ジョブの結果を取得するには、`Receive-Job` コマンドレットを使用します。

PowerShell バックグラウンドジョブの詳細については、「 [about_Jobs](../Microsoft.PowerShell.Core/About/about_jobs.md) 」および「 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_remote_jobs.md)」を参照してください。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -BufferSize

このコマンドで送信されるバッファーのサイズをバイト単位で指定します。 既定値は 32 です。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

ping するコンピューターを指定します。 コンピューター名を入力するか、IP アドレスを IPv4 または IPv6 形式で入力します。 ワイルドカード文字は使用できません。 このパラメーターは必須です。

このパラメーターは、PowerShell リモート処理に依存しません。 コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターを使用できます。

> [!NOTE]
> **ComputerName** パラメーターは、PowerShell 6.0 以降では **TargetName** に名前が変更されました。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, IPAddress, __SERVER, Server, Destination

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -カウント

送信するエコー要求の数を指定します。 既定値は 4 ですが、

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

送信元コンピューターから ping 要求を送信するアクセス許可を持つユーザー アカウントを指定します。 User01 や Domain01\user01」などのユーザー名を入力するか、コマンドレットのような **PSCredential** オブジェクトを入力し `Get-Credential` ます。

**Credential** パラメーターは、 **Source** パラメーターがコマンドで使用されている場合にのみ有効です。 資格情報は、対象のコンピューターには影響しません。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Source
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -DcomAuthentication

このコマンドレットが WMI で使用する認証レベルを指定します。
`Test-Connection` WMI を使用します。
このパラメーターの有効値は、次のとおりです。

- **Default** 。 Windows 認証
- **なし** 。 COM 認証なし
- **接続** します。 接続レベルの COM 認証
- を **呼び出し** ます。 呼び出しレベルの COM 認証
- **パケット** 。 パケットレベルの COM 認証
- **Packetintegrity** 。 パケット整合性レベルの COM 認証
- **Packetprivacy** 。 パケットのプライバシーレベルの COM 認証
- **変更なし** 。 前のコマンドと同じ

既定値は、列挙値が **4** の **パケット** です。 このパラメーターの値の詳細については、「 [Authenticationlevel](/dotnet/api/system.management.authenticationlevel) 列挙型」を参照してください。

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet (enumerated value of 4)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Delay

ping 間の間隔を秒単位で指定します。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1 (second)
Accept pipeline input: False
Accept wildcard characters: False
```

### -偽装

このコマンドレットが WMI を呼び出すときに使用する偽装レベルを指定します。 `Test-Connection` WMI を使用します。

このパラメーターに指定できる値は次のとおりです。

- **Default** 。 既定の偽装。
- **匿名** 。 呼び出し元の ID は非表示になります。
- を **識別** します。 オブジェクトによる呼び出し元の資格情報のクエリが許可されます。
- **Impersonate** 。 オブジェクトによる呼び出し元の資格情報の使用が許可されます。

既定値は **Impersonate** です。

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

プロトコルを指定します。 このパラメーターに指定できる値は、DCOM および WSMan です。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -非表示

**Quiet** パラメーター **は、boolean 値を** **system.string オブジェクトで返します。** このパラメーターを使用すると、すべてのエラーが抑制します。

テストされた各接続は、 **ブール** 値を返します。 **ComputerName** パラメーターに複数のコンピューターが指定されている場合は、 **ブール** 値の配列が返されます。

Ping **any** が成功した場合 `$True` は、が返されます。

**すべて** の ping が失敗 `$False` した場合は、が返されます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Quiet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

ping の送信元コンピューターの名前を指定します。 コンピューター名のコンマ区切りのリストを入力します。 既定値はローカル コンピューターです。

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: FCN, SRC

Required: True
Position: 1
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

このコマンドを実行するために確立できる最大コンカレント接続数を指定します。
このパラメーターを省略した場合、または値 0 を入力した場合は、既定値の 32 が使用されます。

スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。

```yaml
Type: System.Int32
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeToLive

パケットを転送できる最大回数を指定します。 ゲートウェイやルーターなどのホップごとに、 **TimeToLive** 値が1つ減少します。 0の場合、パケットは破棄され、エラーが返されます。
**Windows** では、既定値は **128** です。 **TimeToLive** パラメーターのエイリアスは **TTL** です。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TTL

Required: False
Position: Named
Default value: 128 in Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### -WsmanAuthentication

このコマンドレットで WSMan プロトコルを使用するときに、ユーザー資格情報の認証に使用されるメカニズムを指定します。
このパラメーターの有効値は、次のとおりです。

- Basic
- CredSSP
- Default
- ダイジェスト
- Kerberos
- Negotiate

既定値は Default です。

このパラメーターの値の詳細については、「 [Authenticationmechanism 列挙型](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?view=powershellsdk-1.1.0)」を参照してください。

注意: ユーザーの資格情報が認証対象のリモートコンピューターに渡される Credential Security Service Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。
このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。
リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。

このパラメーターは Windows PowerShell 3.0 で導入されました。

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

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし

このコマンドレットに入力をパイプすることはできません。

## 出力

### System.management.managementobject # Win32_PingStatus root\cimv2\、、system.--... RemotingJob、system.string

**AsJob** パラメーターを指定した場合、このコマンドレットはジョブオブジェクトを返します。

**Quiet** パラメーターを指定すると、 **ブール** 値が返されます。 複数の接続がテストされている場合は、 **ブール** 値の配列が返されます。 それ以外の場合は、 `Test-Connection` 各 ping の **Win32_PingStatus** オブジェクトを返します。

## 注

このコマンドレットは、 **Win32_PingStatus** クラスを使用します。 コマンドは `Get-WMIObject Win32_PingStatus` 、コマンドに相当 `Test-Connection` します。

**ソース** パラメーターセットは、PowerShell 3.0 で導入されました。

## 関連リンク

[Add-Computer](Add-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
