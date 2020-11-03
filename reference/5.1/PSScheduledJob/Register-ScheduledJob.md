---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/register-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ScheduledJob
ms.openlocfilehash: 89887474142490a71d372577576fb0059b4ff12e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213416"
---
# Register-ScheduledJob

## 概要
スケジュールされたジョブを作成します。

## SYNTAX

### ScriptBlock (既定値)

```
Register-ScheduledJob [-ScriptBlock] <ScriptBlock> [-Name] <String>
 [-Trigger <ScheduledJobTrigger[]>] [-InitializationScript <ScriptBlock>] [-RunAs32]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-ScheduledJobOption <ScheduledJobOptions>] [-ArgumentList <Object[]>] [-MaxResultCount <Int32>]
 [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FilePath

```
Register-ScheduledJob [-FilePath] <String> [-Name] <String> [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-ArgumentList <Object[]>] [-MaxResultCount <Int32>] [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## Description

コマンドレットでは、 `Register-ScheduledJob` スケジュールされたジョブをローカルコンピューター上に作成します。

スケジュールされたジョブは、Windows PowerShell のバックグラウンドジョブであり、一度だけまたは定期的なスケジュールで自動的に開始できます。 スケジュールされたジョブはディスクに保存され、タスクスケジューラに登録されます。
ジョブは、タスクスケジューラまたは Windows PowerShell のスケジュールされたジョブコマンドレットを使用して管理できます。

スケジュールされたジョブが開始されると、スケジュールされたジョブのインスタンスが作成されます。 スケジュールされたジョブのインスタンスは、結果がディスクに保存される点を除き、Windows PowerShell のバックグラウンド ジョブと同じです。 、、などのジョブコマンドレットを使用して、 `Start-Job` `Get-Job` `Receive-Job` ジョブインスタンスの開始、表示、および結果の取得を行います。

を使用して `Register-ScheduledJob` 、スケジュールされた新しいジョブを作成します。 スケジュールされたジョブで実行するコマンドを指定するには、 **ScriptBlock** パラメーターを使用します。 ジョブによって実行されるスクリプトを指定するには、 **FilePath** パラメーターを使用します。

Windows PowerShell-スケジュールされたジョブでは、スケジュールされたタスクに使用タスクスケジューラ同じジョブトリガーとジョブオプションが使用されます。

の **Trigger** パラメーターでは `Register-ScheduledJob` 、ジョブを開始するジョブトリガーを1つ以上追加します。 **Trigger** パラメーターは省略可能であるため、スケジュールされたジョブを作成するときにトリガーを追加し、後でジョブトリガーを追加して、 **runnow** パラメーターを追加してジョブをすぐに開始します。また、コマンドレットを使用して、スケジュールされていない `Start-Job` ジョブを他のジョブのテンプレートとして保存します。

**Options** パラメーターを使用すると、スケジュールされたジョブのオプション設定をカスタマイズできます。 **Options** パラメーターはオプションであるため、スケジュールされたジョブを作成するときにジョブオプションを設定することも、いつでも変更することもできます。 ジョブ オプションの設定によっては、スケジュールされたジョブが実行されない場合があるため、ジョブ オプションを確認し、慎重に設定してください。

`Register-ScheduledJob` は、Windows PowerShell に含まれている **Psscheduledjob** モジュールのジョブスケジュールコマンドレットのコレクションの1つです。

スケジュールされたジョブの詳細については、 **Psscheduledjob** モジュールの概要に関する記事を参照してください。
**Psscheduledjob** モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または [about_Scheduled_Jobs](./about/about_scheduled_jobs.md)を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: スケジュールされたジョブを作成する

この例では、ローカルコンピューター上にスケジュールされたジョブを作成します。

```powershell
Register-ScheduledJob -Name "Archive-Scripts" -ScriptBlock {
  Get-ChildItem $home\*.ps1 -Recurse |
    Copy-Item -Destination "\\Server\Share\PSScriptArchive"
}
```

`Register-ScheduledJob`**Name** パラメーターを使用して、スケジュールされたジョブの **アーカイブスクリプト** を作成します。
**ScriptBlock** `Get-ChildItem` ファイルのディレクトリを再帰的に検索する ScriptBlock パラメーターが実行され `$home` `.ps1` ます。 `Copy-Item`コマンドレットは、 **Destination** パラメーターで指定されたディレクトリにファイルをコピーします。

スケジュールされたジョブにはトリガーが含まれていないため、自動的に開始されません。 ジョブトリガーをに追加するには `Add-JobTrigger` 、コマンドレットを使用して、 `Start-Job` 必要に応じてジョブを開始するか、スケジュールされたジョブを他のスケジュールされたジョブのテンプレートとして使用します。

### 例 2: トリガーとカスタムオプションを使用してスケジュールされたジョブを作成する

この例では、ジョブ トリガーとカスタムのジョブ オプションを指定して、スケジュールされたジョブを作成する方法を示します。

```powershell
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
$path = "\\Srv01\Scripts\UpdateVersion.ps1"
Register-ScheduledJob -Name "UpdateVersion" -FilePath $path -ScheduledJobOption $O -Trigger $T
```

変数には、 `$O` コマンドレットによって作成されたジョブオプションオブジェクトが格納 `New-ScheduledJobOption` されます。 オプションは、コンピューターがアイドル状態でない場合でもスケジュールされたジョブを開始し、必要に応じて、ジョブの複数のインスタンスを連続して実行できるようにコンピューターをスリープ解除します。

変数は、コマンドレットの結果を格納して、 `$T` `New-JobTrigger` 月曜日の午後9:00 にジョブを開始するジョブトリガーを作成します。

変数には、 `$path` スクリプトファイルへのパスが格納され `UpdateVersion.ps1` ます。

`Register-ScheduledJob` では、 **名前** パラメーターを使用して、スケジュールされたジョブ **updateversion** を作成します。
**FilePath** パラメーターでは、を使用して、 `$path` ジョブを実行するスクリプトを指定します。 **Get-scheduledjoboption** パラメーターは、に格納されているジョブオプションを使用し `$O` ます。 **トリガー** パラメーターは、に格納されているジョブトリガーを使用し `$T` ます。

### 例 3: ハッシュテーブルを使用してトリガーとスケジュールされたジョブのオプションを指定する

この例は、例2のコマンドと同じ効果があります。 この例では、ハッシュテーブルを使用して **トリガー** および **get-scheduledjoboption** パラメーターの値を指定する、スケジュールされたジョブを作成します。 `$O` `$T` 例2で定義されているとの変数は、ハッシュテーブルに置き換えられます。

```powershell
$T = @{
  Frequency="Weekly"
  At="9:00PM"
  DaysOfWeek="Monday"
  Interval=2
}
$O = @{
  WakeToRun=$true
  StartIfNotIdle=$false
  MultipleInstancePolicy="Queue"
}
Register-ScheduledJob -Trigger $T -ScheduledJobOption $O -Name UpdateVersion -FilePath "\\Srv01\Scripts\Update-Version.ps1"
```

### 例 4: リモートコンピューターにスケジュールされたジョブを作成する

この例では、スケジュールされたジョブ **energydata.ps1** を複数のリモートコンピューター上に作成します。 スケジュールされたジョブは、生データを収集し、リモートコンピューター上の実行中のログに保存するスクリプトを実行します。

```powershell
$Cred = Get-Credential
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Invoke-Command -ComputerName (Get-Content Servers.txt) -Credential $Cred -ScriptBlock {
  $params = @{
      Name = "Get-EnergyData"
      FilePath = "\\Srv01\Scripts\Get-EnergyData.ps1"
      ScheduledJobOption = $using:O
      Trigger = $using:T
  }
  Register-ScheduledJob @params
}
```

変数は、 `$Cred` スケジュールされたジョブを作成するアクセス許可を持つユーザーのために、 **PSCredential** オブジェクトに資格情報を格納します。 変数には、 `$O` で作成されたジョブオプションが格納され `New-ScheduledJobOption` ます。 変数は、 `$T` で作成されたジョブトリガーを格納し `New-JobTrigger` ます。

コマンドレットでは、 `Invoke-Command` **ComputerName** パラメーターを使用して、ファイルからサーバー名の一覧を取得し `Servers.txt` ます。 **Credential** パラメーターは、に格納されている資格情報オブジェクトを取得し `$Cred` ます。
**ScriptBlock** パラメーターは、 `Register-ScheduledJob` ファイル内のコンピューターでコマンドを実行し `Servers.txt` ます。

のパラメーターは、で定義されてい `Register-ScheduledJob` `$params` ます。 **Name** パラメーターは、各リモートコンピューターでジョブの名前を **energydata.ps1** に指定します。 **FilePath** は、スクリプトの場所を指定し `EnergyData.ps1` ます。 このスクリプトは、参加しているすべてのコンピューターで使用できるファイルサーバーにあります。ジョブは、のジョブトリガーによって指定されたスケジュールと、のジョブオプションで実行され `$T` `$O` ます。

この `Register-ScheduledJob @params` コマンドは、スクリプトブロックのパラメーターを使用して、スケジュールされたジョブを作成します。

### 例 5: リモートコンピューターでスクリプトを実行するスケジュールされたジョブを作成する

この例では、ローカルコンピューター上にスケジュールされたジョブ **CollectEnergyData** を作成します。 このジョブは、複数のリモートコンピューター上で実行されます。

```powershell
$Admin = Get-Credential
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Register-ScheduledJob -Name "CollectEnergyData" -Trigger $T -MaxResultCount 99 -ScriptBlock {
  $params = @{
    AsJob = $true
    ComputerName = (Get-Content Servers.txt)
    FilePath = '\\Srv01\Scripts\Get-EnergyData.ps1'
    Credential = $using:Admin
    Authentication = 'CredSSP'
  }
  Invoke-Command @params
}
```

変数には、 `$Admin` **PSCredential** オブジェクトでコマンドを実行するアクセス許可を持つユーザーの資格情報が格納されます。 変数は、 `$T` で作成されたジョブトリガーを格納し `New-JobTrigger` ます。

この `Register-ScheduledJob` コマンドレットでは、 **Name** パラメーターを使用して、ローカルコンピューター上のスケジュールされたジョブ **CollectEnergyData** を作成します。 **Trigger** パラメーターはのジョブトリガーを指定し、 `$T` **maxresultcount** パラメーターは保存される結果の数を99に増やします。

**ScriptBlock** パラメーターは、でパラメーターを定義し `Invoke-Command` `$params` ます。 **AsJob** パラメーターは、 `Energydata.ps1` スクリプトがリモートコンピューター上で実行されている場合でも、ローカルコンピューター上にバックグラウンドジョブオブジェクトを作成します。 **ComputerName** パラメーターは、ファイルからサーバー名の一覧を取得し `Servers.txt` ます。 **Credential** パラメーターは、リモートコンピューターでスクリプトを実行する権限を持つユーザーアカウントを指定します。 また、 **認証** パラメーターでは、委任された資格情報を許可する **CredSSP** の値を指定します。

は、 `Invoke-Command @params` スクリプトブロックのパラメーターを使用してコマンドを実行します。

## PARAMETERS

### -ArgumentList

**FilePath** パラメーターで指定されたスクリプトのパラメーター、または **ScriptBlock** パラメーターで指定されたコマンドの値を指定します。

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -認証

ユーザーの資格情報の認証に使用するメカニズムを指定します。 既定値は Default です。

このパラメーターの有効値は、次のとおりです。

- Default
- Basic
- Credssp
- ダイジェスト
- Kerberos
- ネゴシエート
- NegotiateWithImplicitCredential

このパラメーターの値の詳細については、「 [Authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。

> [!CAUTION]
> ユーザーの資格情報が認証対象のリモート コンピューターに渡される Credential Security Service Provider (CredSSP) 認証は、リモート ネットワーク共有にアクセスする場合など、複数のリソースの認証を必要とするコマンドを対象としています。 このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。 リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

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

### -Credential

スケジュールされたジョブを実行するアクセス許可を持つユーザー アカウントを指定します。 既定値は現在のユーザーです。

**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットのような **PSCredential** オブジェクトを入力し `Get-Credential` ます。 ユーザー名のみを入力した場合は、パスワードの入力を求められます。

資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。

> [!NOTE]
> **SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。

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

### -FilePath

スケジュールされたジョブで実行するスクリプトを指定します。 ローカルコンピューター上のファイルへのパスを入力し `.ps1` ます。 スクリプト パラメーターの既定値を指定するには、 **ArgumentList** パラメーターを使用します。
すべての `Register-ScheduledJob` コマンドで **ScriptBlock** パラメーターまたは **FilePath** パラメーターを使用する必要があります。

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitializationScript

Windows PowerShell スクリプト () への完全修飾パスを指定し `.ps1` ます。 初期化スクリプトは、 **ScriptBlock** パラメーターで指定されたコマンドまたは **FilePath** パラメーターで指定されスクリプトの前に、バックグラウンド ジョブ用に作成されたセッションで実行されます。 初期化スクリプトを使用すると、ファイル、関数、またはエイリアスの追加、ディレクトリの作成、前提条件の確認など、セッションを構成することができます。

プライマリ ジョブ コマンドを実行するスクリプトを指定するには、 **FilePath** パラメーターを使用します。

初期化スクリプトによってエラーが生成された場合、未終了エラーでも、スケジュールされたジョブの現在のインスタンスは実行されず、状態は **Failed** になります。

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxResultCount

スケジュールされたジョブに対して保持されるジョブの結果のエントリ数を指定します。 既定値は 32 です。

Windows PowerShell では、スケジュールされたジョブのトリガーされた各インスタンスの実行履歴と結果をディスクに保存します。 このパラメーターの値により、このスケジュールされたジョブに対して保存されるジョブ インスタンスの結果の数が決まります。 ジョブ インスタンスの結果の数がこの値を超えた場合は、最新のジョブ インスタンスの結果を保存するために、最も古いジョブ インスタンスの結果が削除されます。

ジョブの実行履歴とジョブの結果は、 `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\<JobName>\Output\<Timestamp>`
ジョブが作成されるコンピューター上のディレクトリ。 実行履歴を表示するには、 `Get-Job` コマンドレットを使用します。 ジョブの結果を取得するには、`Receive-Job` コマンドレットを使用します。

**MaxResultCount** パラメーターは、スケジュールされたジョブの ExecutionHistoryLength プロパティの値を設定します。

現在の実行履歴とジョブの結果を削除するには、コマンドレットの **ClearExecutionHistory** パラメーターを使用し `Set-ScheduledJob` ます。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

スケジュールされたジョブの名前を指定します。 この名前は、スケジュールされたジョブの開始されたすべてのインスタンスにも使用されます。 名前は、コンピューター上で一意である必要があります。 このパラメーターは必須です。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAs32

スケジュールされたジョブを 32 ビット プロセスで実行します。

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

### -RunEvery

ジョブを実行する頻度を指定するために使用します。 たとえば、15分ごとにジョブを実行するには、このオプションを使用します。

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunNow

コマンドレットが実行されるとすぐに、ジョブを直ちに開始し `Register-ScheduledJob` ます。 このパラメーターを指定すると、登録後すぐに Windows PowerShell スクリプトを実行するためにタスクスケジューラをトリガーする必要がなくなり、開始日時を指定するトリガーをユーザーが作成する必要がありません。

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

### -Get-scheduledjoboption

スケジュールされたジョブのオプションを設定します。 コマンドレットを使用して作成したオブジェクトやハッシュテーブルの値など、 **ScheduledJobOptions** オブジェクトを入力し `New-ScheduledJobOption` ます。

スケジュールジョブを登録するとき、 `Set-ScheduledJobOption` またはコマンドレットまたはコマンドレットを使用してオプションを変更するときに、スケジュールされたジョブのオプションを設定でき `Set-ScheduledJob` ます。

さまざまなオプションとその既定値により、スケジュールされたジョブが実行されるかどうかとそのタイミングが決まります。 ジョブをスケジュールする前に、必ずこれらのオプションを確認してください。 スケジュールされたジョブオプションの説明 (既定値を含む) については、「」を参照してください `New-ScheduledJobOption` 。

ハッシュ テーブルを渡すには、次のキーを使用します。 次のハッシュ テーブルには、キーとその既定値が示されています。

`@{StartIfOnBattery=$False; StopIfGoingOnBattery=$True; WakeToRun=$False; StartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False; ShowInTaskScheduler=$True; RunElevated=$False; RunWithoutNetwork=$False; DoNotAllowDemandStart=$False; MultipleInstancePolicy="IgnoreNew"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

スケジュールされたジョブで実行するコマンドを指定します。 コマンドを中かっこ () で囲み、 `{}` スクリプトブロックを作成します。 コマンド パラメーターの既定値を指定するには、 **ArgumentList** パラメーターを使用します。

すべての `Register-ScheduledJob` コマンドで **ScriptBlock** パラメーターまたは **FilePath** パラメーターを使用する必要があります。

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -トリガー

スケジュールされたジョブのトリガーを指定します。 コマンドレットが返すオブジェクトや、ジョブトリガーのキーと値のハッシュテーブルなど、1つまたは複数の **Scheduledjobtrigger** オブジェクトを入力し `New-JobTrigger` ます。

ジョブトリガーによってスケジュールジョブが開始されます。 トリガーでは、1 回だけ、定期的なスケジュール、またはイベント (ユーザーがログオンしたときや Windows が起動したときなど) を指定できます。

**Trigger** パラメーターは省略可能です。 スケジュールされたジョブを作成するときにトリガーを追加したり、、 `Add-JobTrigger` `Set-JobTrigger` 、またはコマンドレットを使用して `Set-ScheduledJob` ジョブトリガーを後で追加または変更したり、コマンドレットを使用してスケジュールされたジョブを直ちに開始することができ `Start-Job` ます。 また、テンプレートとして使用するために、トリガーのないスケジュールされたジョブを作成し、管理することもできます。

ハッシュテーブルを送信するには、次のキーを使用します。

- **頻度** : 毎日、毎週、atstartup、atstartup
- **At** : 任意の有効な時刻文字列
- **DaysOfWeek** -曜日名の任意の組み合わせ
- **Interval** -任意の有効な頻度の間隔
- **RandomDelay** : 任意の有効な timespan 文字列
- **User** : 任意の有効なユーザー。 AtLogon frequency 値と共にのみ使用されます。

次に例を示します。

`@{Frequency="Once"; At="3am"; DaysOfWeek="Monday", "Wednesday"; Interval=2; RandomDelay="30minutes"; User="Domain1\User01"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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

入力をパイプラインからこのコマンドレットに送信することはできません。

## 出力

### ScheduledJobDefinition (Microsoft PowerShell)

## 注

スケジュールされた各ジョブは、ローカルコンピューターのディレクトリのサブディレクトリに保存され `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` ます。
サブディレクトリには、スケジュールされたジョブの名前が付けられ、スケジュールされたジョブの XML ファイルとその実行履歴のレコードが含まれます。 ディスク上のスケジュールされたジョブの詳細については、「 [about_Scheduled_Jobs_Advanced](./about/about_scheduled_jobs_advanced.md)」を参照してください。

Windows PowerShell で作成したスケジュールされたジョブは、タスクスケジューラフォルダーのタスクスケジューラに表示され `Library\Microsoft\Windows\PowerShell\ScheduledJobs` ます。 タスク スケジューラを使用して、スケジュールされたジョブを表示および編集できます。

タスクスケジューラ、 **schtasks.exe** コマンドラインツール、およびタスクスケジューラコマンドレットを使用して、スケジュールされたジョブコマンドレットで作成したスケジュールされたジョブを管理できます。 ただし、スケジュールされたジョブのコマンドレットを使用してタスクスケジューラで作成したタスクを管理することはできません。

スケジュールされたジョブ コマンドが失敗した場合は、エラー メッセージが返されます。 ただし、タスクスケジューラによって実行が試行されたときにジョブが失敗した場合、Windows PowerShell でエラーを使用することはできません。

スケジュールされたジョブが実行されない場合は、次の方法で理由を確認してください。

- ジョブトリガーが適切に設定されていることを確認します。
  - ジョブオプションに設定されている条件が満たされていることを確認します。
- ジョブを実行するユーザーアカウントに、ジョブのコマンドまたはスクリプトを実行する権限があることを確認します。
- タスクスケジューラの履歴でエラーを確認します。
- タスクスケジューライベントログでエラーを確認します。

詳細については、「 [about_Scheduled_Jobs_Troubleshooting](./about/about_scheduled_jobs_troubleshooting.md)」を参照してください。

## 関連リンク

[Add-JobTrigger](Add-JobTrigger.md)

[Disable-JobTrigger](Disable-JobTrigger.md)

[Disable-ScheduledJob](Disable-ScheduledJob.md)

[Enable-JobTrigger](Enable-JobTrigger.md)

[Enable-ScheduledJob](Enable-ScheduledJob.md)

[Get-JobTrigger](Get-JobTrigger.md)

[Get-ScheduledJob](Get-ScheduledJob.md)

[Get-ScheduledJobOption](Get-ScheduledJobOption.md)

[New-JobTrigger](New-JobTrigger.md)

[New-ScheduledJobOption](New-ScheduledJobOption.md)

[Register-ScheduledJob](Register-ScheduledJob.md)

[Remove-JobTrigger](Remove-JobTrigger.md)

[Set-JobTrigger](Set-JobTrigger.md)

[Set-ScheduledJob](Set-ScheduledJob.md)

[Set-ScheduledJobOption](Set-ScheduledJobOption.md)

[Unregister-ScheduledJob](Unregister-ScheduledJob.md)
