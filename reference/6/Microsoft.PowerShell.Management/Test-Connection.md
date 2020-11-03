---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: 54ba1d7db60db7b4bb64f3161bba9c1fba124219
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212195"
---
# Test-Connection

## 概要
ICMP エコー要求パケット (ping) を1台以上のコンピューターに送信します。

## SYNTAX

### Ping の回数 (既定値)

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Count <Int32>] [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### Ping の続行

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-Continues] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### DetectionOfMTUSize

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -MTUSizeDetect [-Quiet] [<CommonParameters>]
```

### TraceRoute

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-TimeoutSeconds <Int32>] [-TargetName] <String[]> -Traceroute [-Quiet] [<CommonParameters>]
```

### ConnectionByTCPPort

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -TCPPort <Int32> [-Quiet] [<CommonParameters>]
```

## Description

`Test-Connection`コマンドレットは、インターネット制御メッセージプロトコル (ICMP) エコー要求パケット (ping) を1つ以上のリモートコンピューターに送信し、エコー応答応答を返します。 このコマンドレットを使用すると、特定のコンピューターに IP ネットワーク経由で接続できるかどうかを判断できます。

のパラメーターを使用し `Test-Connection` て、送信側と受信側の両方のコンピューターの指定、バックグラウンドジョブとしてのコマンドの実行、タイムアウトと ping の回数の設定、および接続と認証の構成を行うことができます。

使い慣れた **ping** コマンドとは異なり、は、 `Test-Connection` PowerShell で調査できる **Testconnectioncommand + ping レポート** オブジェクトを返します。 **Quiet** パラメーターは、テストされた各接続の **ブール値を** **system.string オブジェクトで返します。** 複数の接続がテストされている場合は、 **ブール** 値の配列が返されます。

## 例

### 例 1: リモートコンピューターにエコー要求を送信する

この例では、エコー要求パケットをローカルコンピューターから Server01 コンピューターに送信します。

```powershell
Test-Connection -TargetName Server01 -IPv4
```

```Output
Pinging Server01 [10.59.137.44] with 32 bytes of data:
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Ping complete.

Source     Destination Replies
------     ----------- -------
Server01   Server01    {System.Net.NetworkInformation.PingReply, System.Net.NetworkInformation ...
```

`Test-Connection`**TargetName** パラメーターを使用して、Server01 コンピューターを指定します。 **IPv4** パラメーターでは、テスト用のプロトコルを指定します。

**Testconnectioncommand + Ping report** オブジェクトが **成功** ストリームに送信されるときに、Ping の出力が **情報** ストリームに送信されます。 出力ストリームの詳細については、「 [about_Redirection](../microsoft.powershell.core/about/about_redirection.md)」を参照してください。

### 例 2: 複数のコンピューターにエコー要求を送信する

この例では、ローカルコンピューターから複数のリモートコンピューターに ping を送信します。

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### 例 3: 複数のコンピューターからコンピューターにエコー要求を送信する

この例では、別のソースコンピューターから1台のリモートコンピューター Server01 に ping を送信します。

```powershell
Test-Connection -Source Server02, Server12, localhost -TargetName Server01
```

複数のポイントからの接続の待機時間をテストするには、このコマンド形式を使用します。

### 例 4: パラメーターを使用してテストコマンドをカスタマイズする

この例では、のパラメーターを使用し `Test-Connection` て、コマンドをカスタマイズします。 ローカルコンピューターからリモートコンピューターに ping テストが送信されます。

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

`Test-Connection`**TargetName** パラメーターを使用して Server01 を指定します。 **Count** パラメーターは、3秒間隔の **遅延** で Server01 コンピューターに送信される3つの ping を指定します。

これらのオプションは、ホップ数の増加またはトラフィックの多いネットワーク状態が原因で ping 応答が通常よりも長くかかることが予想される場合に使用できます。

### 例 5: バックグラウンドジョブとしてテストを実行する

この例では、 `Test-Connection` PowerShell バックグラウンドジョブとしてコマンドを実行する方法を示します。

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content "Servers.txt") }
if ($job.JobStateInfo.State -ne "Running") { $Results = Receive-Job $job }
```

このコマンドは、コマンド `Start-Job` レットを使用して、 `Test-Connection` 企業内の多くのコンピューターに ping を実行します。
**TargetName** パラメーターの値は、 `Get-Content` ファイルからコンピューター名の一覧を読み取るコマンドです `Servers.txt` 。 コマンドはコマンドレットを使用し `Start-Job` てバックグラウンドジョブとしてコマンドを実行し、変数にジョブを保存し `$job` ます。

コマンドは、 `if` ジョブがまだ実行されていないことを確認します。 ジョブが実行されていない場合は、 `Receive-Job` 結果を取得して変数に格納し `$Results` ます。

### 例 6: 接続テストが成功した場合にのみセッションを作成する

この例では、コンピューターに送信された ping の少なくとも1つが成功した場合にのみ、Server01 コンピューターでセッションを作成します。

```powershell
if (Test-Connection -TargetName Server01 -Quiet) {New-PSSession Server01}
```

このコマンドは、コマンド `if` レットを使用して `Test-Connection` 、Server01 コンピューターに ping を実行します。 このコマンドは、 **Testconnectioncommand + Ping report** オブジェクトではなく、 **ブール** 値を返す **Quiet** パラメーターを使用します。

`$True`4 つの ping のいずれかが成功した場合、値はになります。 Ping が成功しなかった場合、値はに `$False` なります。

コマンドが `Test-Connection` 値を返す場合 `$True` 、コマンドはコマンドレットを使用して `New-PSSession` **PSSession** を作成します。

### 例 7: Traceroute パラメーターを使用する

PowerShell 6.0 以降では、 **Traceroute** パラメーターを使用して、ローカルコンピューターと指定したリモートターゲットの間のルートを **TargetName** パラメーターでマップします。

```powershell
Test-Connection -TargetName www.microsoft.com -Traceroute | ForEach-Object {
  $_ | Format-Table Source, DestinationAddress, DestinationHost
  $_.Replies | ForEach-Object {
      $_ | Format-Table Hop, ReplyRouterAddress
      $_.PingReplies | Format-Table
  }
}
```

```Output
Tracing route to www.microsoft.com [96.6.27.90] over a maximum of 128 hops:
  1   0 ms   0 ms   0 ms   192.168.0.3 [192.168.0.3]
  2   0 ms   0 ms   0 ms   192.168.1.1 [192.168.1.1]
  3   3 ms   29 ms   4 ms   96.6.27.90 [96.6.27.90]
Trace complete.

Source      DestinationAddress DestinationHost   Replies
------      ------------------ ---------------   -------
SERVER01    96.6.27.90         www.microsoft.com {, , }

Hop ReplyRouterAddress
--- ------------------
  1 192.168.0.3

    Status Address      RoundtripTime Options Buffer
    ------ -------      ------------- ------- ------
TtlExpired 192.168.86.1             0         {}
TtlExpired 192.168.86.1             0         {}
TtlExpired 192.168.86.1             0         {}

Hop ReplyRouterAddress
--- ------------------
  2 192.168.1.1

    Status Address     RoundtripTime Options Buffer
    ------ -------     ------------- ------- ------
TtlExpired 192.168.1.1             0         {}
TtlExpired 192.168.1.1             0         {}
TtlExpired 192.168.1.1             0         {}

Hop ReplyRouterAddress
--- ------------------
  3 96.6.27.90

 Status Address    RoundtripTime Options                                   Buffer
 ------ -------    ------------- -------                                   ------
Success 96.6.27.90             3 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
Success 96.6.27.90             2 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
Success 96.6.27.90             4 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
```

この `Test-Connection` コマンドでは、 **Traceroute** パラメーターを使用します。 結果 (オブジェクト) は、パイプを使用して `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteResult]` コマンドレットに渡され `ForEach-Object` ます。 `ForEach-Object` 格納されているオブジェクトと後続のオブジェクトの構造化された出力を作成し `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteReply]` `[System.Net.NetworkInformation.PingReply]` ます。

## PARAMETERS

### -BufferSize

このコマンドで送信されるバッファーのサイズをバイト単位で指定します。 既定値は 32 です。

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -カウント

送信するエコー要求の数を指定します。 既定値は 4 ですが、

```yaml
Type: System.Int32
Parameter Sets: PingCount
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### -Delay

ping 間の間隔を秒単位で指定します。

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DontFragment

このパラメーターは、IP ヘッダーに don't **Fragment** フラグを設定します。 このパラメーターを **BufferSize** パラメーターと共に使用して、パスの MTU サイズをテストできます。 パス MTU の詳細については、wikipedia の [パス Mtu 検出](https://wikipedia.org/wiki/Path_MTU_Discovery) に関する記事を参照してください。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4

テストに IPv4 プロトコルを使用するようにコマンドレットを強制します。

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

### -IPv6

テストに IPv6 プロトコルを使用するようにコマンドレットを強制します。

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

### -MaxHops

ICMP 要求メッセージを送信できる最大ホップ数を設定します。 既定値は、オペレーティングシステムによって制御されます。 Windows 10 の既定値は128ホップです。

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues, TraceRoute
Aliases: Ttl, TimeToLive, Hops

Required: False
Position: Named
Default value: 128 hops in Windows 10
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ping

コマンドレットが ping テストを実行します。これは、既定のアクションです。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: Ping test
Accept pipeline input: False
Accept wildcard characters: False
```

### -非表示

**Quiet** パラメーター **は、boolean 値を** **system.string オブジェクトで返します。** このパラメーターを使用すると、すべてのエラーが抑制します。

テストされた各接続は、 **ブール** 値を返します。 **TargetName** パラメーターに複数のコンピューターが指定されている場合は、 **ブール** 値の配列が返されます。

Ping **any** が成功した場合 `$True` は、が返されます。

**すべて** の ping が失敗 `$False` した場合は、が返されます。

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

### -ResolveDestination

コマンドレットがターゲットの DNS 名を解決しようとします。

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

### -Source

ping の送信元コンピューターの名前を指定します。 コンピューター名のコンマ区切りのリストを入力します。 既定値はローカル コンピューターです。

```yaml
Type: System.String
Parameter Sets: PingCount, PingContinues, TraceRoute, ConnectionByTCPPort
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetName

テストするコンピューターを指定します。 コンピューター名を入力するか、IP アドレスを IPv4 または IPv6 形式で入力します。 ワイルドカード文字は使用できません。 このパラメーターは必須です。 **ComputerName** は、このパラメーターのエイリアスです。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ComputerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TCPPort

TCP 接続テストで使用するターゲットの TCP ポート番号を指定します。 コマンドレットは、ターゲットの指定されたポートへの TCP 接続を試行します。

```yaml
Type: System.Int32
Parameter Sets: ConnectionByTCPPort
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutSeconds

テストのタイムアウト値を設定します。 タイムアウトの期限が切れる前に応答を受信しなかった場合、テストは失敗します。 既定値は 5 秒です。

このパラメーターは、PowerShell 6.0 で導入されました。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5 seconds
Accept pipeline input: False
Accept wildcard characters: False
```

### -Traceroute

コマンドレットが traceroute テストを実行します。 このパラメーターを使用すると、コマンドレットは `TestConnectionCommand+TraceRouteResult` オブジェクトを返します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TraceRoute
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -続行

コマンドレットによって ping 要求が連続して送信されます。 このパラメーターは、 **Count** パラメーターと共に使用することはできません。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingContinues
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MTUSizeDetect

このパラメーターは、パスの MTU サイズを検出するために使用されます。 コマンドレットは、ターゲットにパスの MTU サイズを含む、 **ping # MTUSize** オブジェクトを返します。 パス MTU の詳細については、wikipedia の [パス Mtu 検出](https://wikipedia.org/wiki/Path_MTU_Discovery) に関する記事を参照してください。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DetectionOfMTUSize
Aliases:

Required: True
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

### TestConnectionCommand + Ping Report、TestConnectionCommand + TraceRouteResult、Boolean、Ping Reply # MTUSize

**Quiet** パラメーターを指定すると、 **ブール** 値が返されます。 複数の接続がテストされている場合は、 **ブール** 値の配列が返されます。 それ以外の場合は、 `Test-Connection` 各 ping に対して **Testconnectioncommand + ping report** オブジェクトを返します。

## 注

## 関連リンク

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
