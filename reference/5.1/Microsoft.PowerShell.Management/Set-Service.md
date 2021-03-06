---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: df4fda68508e21700235d2b772c6dd43c8e1fe1e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214416"
---
# Set-Service

## 概要
サービスを開始、停止、および中断し、そのプロパティを変更します。

## SYNTAX

### 名前 (既定値)

```
Set-Service [-ComputerName <String[]>] [-Name] <String> [-DisplayName <String>]
 [-Description <String>] [-StartupType <ServiceStartMode>] [-Status <String>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObject

```
Set-Service [-ComputerName <String[]>] [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Status <String>] [-InputObject <ServiceController>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description

`Set-Service`コマンドレットは、 **Status** 、 **Description** 、 **DisplayName** 、 **startuptype** などのサービスのプロパティを変更します。 `Set-Service` サービスを開始、停止、一時停止、または一時停止できます。 サービスを識別するには、サービス名を入力するか、サービスオブジェクトを送信します。 または、サービス名またはサービスオブジェクトをパイプラインからに送信 `Set-Service` します。

## 例

### 例 1: 表示名を変更する

この例では、サービスの表示名が変更されています。 元の表示名を表示するには、を使用 `Get-Service` します。

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

`Set-Service`**name** パラメーターを使用して、サービスの名前 **LanmanWorkstation** を指定します。 **DisplayName** パラメーターでは、新しい表示名である **LanMan Workstation** を指定します。

### 例 2: サービスのスタートアップの種類を変更する

この例では、サービスのスタートアップの種類を変更する方法を示します。

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

`Set-Service`**name** パラメーターを使用して、サービスの名前 ( **ビット** ) を指定します。 **Startuptype** パラメーターを指定すると、サービスが **自動** に設定されます。

`Get-Service`**Name** パラメーターを使用して、 **BITS** サービスを指定し、オブジェクトをパイプラインの下に送信します。 `Select-Object`**Property** パラメーターを使用して、 **BITS** サービスの状態を表示します。

### 例 3: サービスの説明を変更する

この例では、BITS サービスの説明を変更し、結果を表示します。

`Get-CimInstance`コマンドレットは、サービスの **説明** を含む **Win32_Service** オブジェクトを返すために使用されます。

```powershell
Get-CimInstance Win32_Service -Filter 'Name = "BITS"'  | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth. If the service is
              disabled, then any applications that depend on BITS, such as Windows Update or MSN
              Explorer, will be unable to automatically download programs and other information.
```

```powershell
Set-Service -Name BITS -Description "Transfers files in the background using idle network bandwidth."
Get-CimInstance Win32_Service -Filter 'Name = "BITS"' | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth.
```

`Get-CimInstance` オブジェクトをパイプライン内でに送信 `Format-List` し、サービスの名前と説明を表示します。 比較のために、説明が更新される前と後にコマンドが実行されます。

`Set-Service`**Name** パラメーターを使用して、 **BITS** サービスを指定します。 **Description** パラメーターは、サービスの説明の更新されたテキストを指定します。

### 例 4: サービスを開始する

この例では、サービスが開始されています。

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

`Set-Service` では、 **Name** パラメーターを使用してサービス ( **WinRM** ) を指定しています。 **Status** パラメーターは、 **実行されている** 値を使用してサービスを開始します。 **PassThru** パラメーターは、結果を表示する **ServiceController** オブジェクトを出力します。

### 例 5: サービスを中断する

この例では、パイプラインを使用してサービスを一時停止します。

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

`Get-Service`**Name** パラメーターを使用して **Schedule** サービスを指定し、オブジェクトをパイプラインの下に送信します。 `Set-Service`**Status** パラメーターを使用して、サービスを **一時停止** に設定します。

### 例 6: サービスを停止する

この例では、変数を使用してサービスを停止します。

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

`Get-Service`**Name** パラメーターを使用して、サービス、 **スケジュール** を指定します。 オブジェクトは変数に格納され `$S` ます。 `Set-Service`**InputObject** パラメーターを使用し、格納されているオブジェクトを指定し `$S` ます。 **Status** パラメーターは、サービスを **Stopped** に設定します。

## PARAMETERS

### -ComputerName

1 台以上のコンピューターを指定します。 リモートコンピューターの場合は、NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。 **ComputerName** パラメーターが指定されていない場合、コマンドはローカルコンピューター上で実行されます。

このパラメーターは、PowerShell リモート処理に依存しません。 コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターを使用できます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

実行前に確認メッセージを表示 `Set-Service` します。

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

### -Description

サービスの新しい説明を指定します。

サービスの説明は **、[コンピューターの管理] の [サービス]** に表示されます。 **説明** は、 `Get-Service` **ServiceController** オブジェクトのプロパティではありません。 サービスの説明を表示するには、 `Get-CimInstance` サービスを表す **Win32_Service** オブジェクトを返すを使用します。

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

### -DisplayName

サービスの新しい表示名を指定します。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

変更するサービスを表す **ServiceController** オブジェクトを指定します。 オブジェクトを含む変数を入力するか、コマンドなど、オブジェクトを取得するコマンドまたは式を入力し `Get-Service` ます。 パイプラインを使用して、サービスオブジェクトをに送信でき `Set-Service` ます。

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

変更するサービスのサービス名を指定します。 ワイルドカード文字は使用できません。 パイプラインを使用して、サービス名をに送信でき `Set-Service` ます。

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru

変更されたサービスを表す **ServiceController** オブジェクトを返します。 既定では、は `Set-Service` 出力を生成しません。

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

### -StartupType

サービスのスタートアップの種類を設定します。 このパラメーターの有効値は、次のとおりです。

- **自動** -サービスが開始されているか、システムの起動時にオペレーティングシステムによって開始されました。
  自動的に開始されるサービスが手動で開始されるサービスに依存する場合は、手動で開始されるサービスもシステムの起動時に自動的に開始されます。
- [ **無効** ]-サービスは無効になっており、ユーザーまたはアプリケーションが開始することはできません。
- **手動** -サービスは、ユーザー、サービスコントロールマネージャー、またはアプリケーションによって手動でのみ開始されます。
- **ブート** -サービスがシステムローダーによって開始されたデバイスドライバーであることを示します。 この値は、デバイス ドライバーに対してのみ有効です。
- **システム** -サービスが、' IOInitSystem () ' 関数によって開始されたデバイスドライバーであることを示します。 この値は、デバイス ドライバーに対してのみ有効です。

 既定値は **Automatic** です。

```yaml
Type: System.ServiceProcess.ServiceStartMode
Parameter Sets: (All)
Aliases: StartMode, SM, ST
Accepted values: Boot, System, Automatic, Manual, Disabled

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### -状態

サービスの状態を指定します。

このパラメーターに指定できる値は次のとおりです。

- **一時停止** しました。 サービスを中断します。
- **実行中** 。 サービスを開始します。
- **停止済み** 。 サービスを停止します。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Paused, Running, Stopped

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

が実行された場合に何が起こるか `Set-Service` を示します。 コマンドレットは実行されません。

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

### ServiceController (System.string)、System.string

パイプラインを使用して、サービス名が含まれているサービスオブジェクトまたは文字列をに送信でき `Set-Service` ます。

## 出力

### System.ServiceProcess.ServiceController

既定では、は `Set-Service` オブジェクトを返しません。 **PassThru** パラメーターを使用して、 **ServiceController** オブジェクトを出力します。

## 注

`Set-Service` 昇格されたアクセス許可が必要です。 [ **管理者として実行** ] オプションを使用します。

`Set-Service` 現在のユーザーがサービスを管理するアクセス許可を持っている場合にのみ、サービスを制御できます。 コマンドが正常に動作しない場合は、必要なアクセス許可がない可能性があります。

サービスのサービス名または表示名を検索するには、を使用 `Get-Service` します。 サービス名は [ **名前** ] 列に、表示名は [ **DisplayName** ] 列に表示されます。

## 関連リンク

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)
