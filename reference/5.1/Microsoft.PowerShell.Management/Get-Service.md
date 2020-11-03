---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: 0c007f1becd7364806cfd47e18cf05995b81e0f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215403"
---
# Get-Service

## 概要
ローカルまたはリモート コンピューター上のサービスを取得します。

## SYNTAX

### 既定値 (既定値)

```
Get-Service [[-Name] <String[]>] [-ComputerName <String[]>] [-DependentServices] [-RequiredServices]
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### DisplayName

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] -DisplayName <String[]>
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### InputObject

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## Description

**Get Service** コマンドレットは、サービスの実行と停止を含む、ローカルコンピューターまたはリモートコンピューター上のサービスを表すオブジェクトを取得します。

サービス名またはサービスの表示名を指定して、特定のサービスのみを取得するようにこのコマンドレットに指示することも、このコマンドレットにサービスオブジェクトをパイプ処理することもできます。

## 例

### 例 1: コンピューター上のすべてのサービスを取得する

```powershell
Get-Service
```

このコマンドは、コンピューター上のすべてのサービスを取得します。
入力した場合と同じように動作し `Get-Service *` ます。
既定では、各サービスの状態、サービス名、表示名が表示されます。

### 例 2: 検索文字列で始まるサービスを取得する

```powershell
Get-Service "wmi*"
```

このコマンドは、WMI で始まるサービス名 (Windows Management Instrumentation の頭字語) を使用してサービスを取得します。

### 例 3: 検索文字列を含むサービスを表示する

```powershell
Get-Service -Displayname "*network*"
```

このコマンドは、"network" という単語を含む表示名を持つサービスを表示します。
表示名を検索することにより、xmlprov (Network Provisioning Service) のようにサービス名に "Net" が含まれていない場合でも、ネットワーク関連のサービスを見つけることができます。

### 例 4: 検索文字列と除外で始まるサービスを取得する

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

これらのコマンドは、WinRM サービスを除き、サービス名が win で始まるサービスだけを取得します。

### 例 5: 現在アクティブなサービスを表示する

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

このコマンドは、現在アクティブなサービスのみを表示します。
この例では、 **Get Service** コマンドレットを使用して、コンピューター上のすべてのサービスを取得します。
パイプライン演算子 (|) は、結果を Where-Object コマンドレットに渡します。このコマンドレットは、Status プロパティが Running であるサービスのみを選択します。

Status は、サービス オブジェクトの 1 つのプロパティにすぎません。
すべてのプロパティを表示するには、「」と入力 `Get-Service | Get-Member` します。

### 例 6: リモートコンピューター上のサービスを取得する

```powershell
Get-Service -ComputerName "Server02"
```

このコマンドは、Server02 リモート コンピューター上のサービスを取得します。

**Get Service** の *ComputerName* パラメーターは windows powershell リモート処理を使用しないため、コンピューターが windows powershell のリモート処理用に構成されていない場合でも、このパラメーターを使用できます。

### 例 7: 依存サービスを持つローカルコンピューター上のサービスを一覧表示する

```powershell
Get-Service |
  Where-Object {$_.DependentServices} |
    Format-List -Property Name, DependentServices, @{
      Label="NoOfDependentServices"; Expression={$_.dependentservices.count}
    }
```

```Output
Name                  : AudioEndpointBuilder
DependentServices     : {AudioSrv}
NoOfDependentServices : 1

Name                  : Dhcp
DependentServices     : {WinHttpAutoProxySvc}
NoOfDependentServices : 1
...
```

最初のコマンドは、 **Get Service** コマンドレットを使用して、コンピューター上のサービスを取得します。
パイプライン演算子 (|) に **より** 、サービスが where-object コマンドレットに送信され、 **dependentservices** プロパティが null でないサービスが選択されます。

もう一つのパイプライン演算子は、結果を Format-List コマンドレットに渡します。
このコマンドは、 *Property* パラメーターを使用してサービスの名前、依存サービスの名前、および各サービスに依存するサービスの数を表示する計算されたプロパティを表示します。

### 例 8: プロパティ値によってサービスを並べ替える

```powershell
Get-Service "s*" | Sort-Object status
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  stisvc             Windows Image Acquisition (WIA)
Stopped  SwPrv              MS Software Shadow Copy Provider
Stopped  SysmonLog          Performance Logs and Alerts
Running  Spooler            Print Spooler
Running  srservice          System Restore Service
Running  SSDPSRV            SSDP Discovery Service
Running  ShellHWDetection   Shell Hardware Detection
Running  Schedule           Task Scheduler
Running  SCardSvr           Smart Card
Running  SamSs              Security Accounts Manager
Running  SharedAccess       Windows Firewall/Internet Connectio...
Running  SENS               System Event Notification
Running  seclogon           Secondary Logon
```

このコマンドは、 **Status** プロパティの値によってサービスを昇順に並べ替えると、サービスを実行する前に停止したサービスが表示されることを示しています。
これは、Status の値が列挙型であり、Stopped の値が1で、実行中の値が4であるために発生します。

最初に実行中のサービスを一覧表示するには、Sort-Object コマンドレットの *降順* のパラメーターを使用します。

### 例 9: 複数のコンピューター上のサービスを取得する

```powershell
Get-Service -Name "WinRM" -ComputerName "localhost", "Server01", "Server02" |
 Format-Table -Property MachineName, Status, Name, DisplayName -auto
```

```Output
MachineName    Status  Name  DisplayName
------------   ------  ----  -----------
localhost      Running WinRM Windows Remote Management (WS-Management)
Server01       Running WinRM Windows Remote Management (WS-Management)
Server02       Running WinRM Windows Remote Management (WS-Management)
```

このコマンドは、 **Get Service** コマンドレットを使用して、2台のリモートコンピューターとローカルコンピューター ("localhost") で Get-Service Winrm コマンドを実行します。

コマンドはリモートコンピューター上で実行され、結果はローカルコンピューターに返されます。
パイプライン演算子 (|) によって結果が **Format table** コマンドレットに送信され、サービスがテーブルとして書式設定されます。
**Format table** コマンドでは、 *property* パラメーターを使用して、 **MachineName** プロパティを含む、テーブルに表示されるプロパティを指定します。

### 例 10: サービスの依存サービスを取得する

```powershell
Get-Service "WinRM" -RequiredServices
```

このコマンドは、WinRM サービスが必要とするサービスを取得します。

このコマンドは、サービスの **ServicesDependedOn** プロパティの値を返します。

### 例 11: パイプライン演算子を使用してサービスを取得する

```powershell
"WinRM" | Get-Service
```

このコマンドは、ローカル コンピューター上の WinRM サービスを取得します。
この例では、サービス名の文字列 (引用符で囲まれている) を **Get service** にパイプすることができます。

## PARAMETERS

### -ComputerName

指定されたコンピューターで実行されているサービスを取得します。
既定値はローカル コンピューターです。

リモートコンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名 (FQDN) を入力します。
ローカルコンピューターを指定するには、コンピューター名、ドット (.)、または localhost を入力します。

このパラメーターは、Windows PowerShell リモート処理に依存しません。
コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **Get Service** の *ComputerName* パラメーターを使用できます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DependentServices

このコマンドレットが、指定されたサービスに依存するサービスのみを取得することを示します。

既定では、このコマンドレットはすべてのサービスを取得します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName

取得するサービスの表示名を文字列配列として指定します。
ワイルドカードを使用できます。
既定では、このコマンドレットは、コンピューター上のすべてのサービスを取得します。

```yaml
Type: System.String[]
Parameter Sets: DisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -除外

このコマンドレットによって操作から除外される1つ以上のサービスを、文字列配列として指定します。
このパラメーターの値は、 *Name* パラメーターを修飾します。
「s*」などの名前要素またはパターンを入力します。
ワイルドカードを使用できます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Include

このコマンドレットによって操作に含まれる1つ以上のサービスを文字列配列として指定します。
このパラメーターの値は、 *Name* パラメーターを修飾します。
「s*」などの名前要素またはパターンを入力します。
ワイルドカードを使用できます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -InputObject

取得するサービスを表す **ServiceController** オブジェクトを指定します。
オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。
このコマンドレットには、サービスオブジェクトをパイプ処理することもできます。

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

取得するサービスのサービス名を指定します。
ワイルドカードを使用できます。
既定では、このコマンドレットは、コンピューター上のすべてのサービスを取得します。

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -RequiredServices

このコマンドレットが、このサービスが必要とするサービスのみを取得することを示します。

このパラメーターは、サービスの **ServicesDependedOn** プロパティの値を取得します。
既定では、このコマンドレットはすべてのサービスを取得します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### ServiceController (System.string)、System.string

このコマンドレットには、サービスオブジェクトまたはサービス名をパイプすることができます。

## 出力

### System.ServiceProcess.ServiceController

このコマンドレットは、コンピューター上のサービスを表すオブジェクトを返します。

## 注

**Get Service** は、その組み込みエイリアスである "gsv" で参照することもできます。 詳細については、「about_Aliases」を参照してください。

このコマンドレットは、現在のユーザーがサービスを表示するアクセス許可を持っている場合にのみ、サービスを表示できます。
このコマンドレットでサービスが表示されない場合は、サービスを表示するアクセス許可がない可能性があります。

システム上の各サービスのサービス名と表示名を確認するには、「」と入力 `Get-Service` します。
サービス名は [Name] 欄に表示され、表示名は [DisplayName] 欄に表示されます。

Status の値により昇順に並べ替えると、状態が "Stopped (停止済み)" のサービスは "Running (実行中)" のサービスの前に表示されます。
サービスの Status プロパティは、状態の名前が整数値を表す列挙値です。
並べ替えは名前ではなく整数値に基づいて行われます。
"Stopped (停止済み)" の値は "1" であり、"Running (実行中)" の値は "4" であるため、"Running" は "Stopped" の前に表示されます。

## 関連リンク

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)
