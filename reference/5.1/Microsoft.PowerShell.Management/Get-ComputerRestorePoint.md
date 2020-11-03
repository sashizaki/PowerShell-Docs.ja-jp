---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerrestorepoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerRestorePoint
ms.openlocfilehash: 73819aafee9ed1911354daf9af23eedff0a3e14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215480"
---
# Get-ComputerRestorePoint

## 概要
ローカル コンピューターで復元ポイントを取得します。

## SYNTAX

### ID (既定値)

```
Get-ComputerRestorePoint [[-RestorePoint] <Int32[]>] [<CommonParameters>]
```

### LastStatus

```
Get-ComputerRestorePoint -LastStatus [<CommonParameters>]
```

## Description

`Get-ComputerRestorePoint`コマンドレットは、ローカルコンピューターのシステムの復元ポイントを取得します。 また、コンピューターを復元するための最新の試行の状態を表示できます。

復元ポイントを選択するには、の情報を使用し `Get-ComputerRestorePoint` ます。 たとえば、コマンドレットの復元ポイントを識別するには、シーケンス番号を使用し `Restore-Computer` ます。

システムの復元ポイントと `Get-ComputerRestorePoint` コマンドレットは、windows 10、windows 7、Windows Vista、WINDOWS XP などのクライアントオペレーティングシステムでのみサポートされています。

## 例

### 例 1: すべてのシステム復元ポイントを取得する

この例では、は、 `Get-ComputerRestorePoint` すべてのローカルコンピューターのシステムの復元ポイントを取得します。

```powershell
Get-ComputerRestorePoint
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
8/7/2019  12:56:45     Installed PowerShell 6-x64     6                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

### 例 2: 特定のシーケンス番号を取得する

この例では、特定のシーケンス番号のシステム復元ポイントを取得します。

```powershell
Get-ComputerRestorePoint -RestorePoint 4, 5
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

`Get-ComputerRestorePoint`**Restorepoint** パラメーターを使用して、コンマで区切られたシーケンス番号の配列を指定します。

### 例 3: システムの復元の状態を表示する

この例では、ローカルコンピューターでの最新のシステム復元の状態を表示します。

```powershell
Get-ComputerRestorePoint -LastStatus
```

```Output
The last attempt to restore the computer failed.
```

`Get-ComputerRestorePoint`**Laststatus** パラメーターを使用して、最新のシステム復元の結果を表示します。

### 例 4: 式を使用して、変更前の時間を変換する

`Get-ComputerRestorePoint` Windows Management Instrumentation (WMI) の日付と時刻の文字列として、更新前の **時刻** を出力します。

この例では、変数には、日付/ **時刻** の文字列を **DateTime** オブジェクトに変換する式が格納されています。 変換前に、変更前の **時刻** の文字列を表示するには、のようなコマンドを使用し `((Get-ComputerRestorePoint).CreationTime)` ます。 WMI の日付と時刻の文字列の詳細については、「 [CIM_DATETIME](/windows/win32/wmisdk/cim-datetime)」を参照してください。

```powershell
$date = @{Label="Date"; Expression={$_.ConvertToDateTime($_.CreationTime)}}
Get-ComputerRestorePoint | Select-Object -Property SequenceNumber, $date, Description
```

```Output
SequenceNumber   Date                 Description
--------------   ----                 -----------
             4   7/30/2019 09:17:24   Windows Update
             5   8/5/2019  08:15:37   Installed PowerShell 7-preview-x64
             6   8/7/2019  12:56:45   Installed PowerShell 6-x64
```

変数は、 `$date` **Converttodatetime** メソッドを使用する式を使用してハッシュテーブルを格納します。 この式は、WMI 文字列から **DateTime** オブジェクトに対して、指定された値 **のプロパティの** 値を変換します。

`Get-ComputerRestorePoint` システムの復元ポイントオブジェクトをパイプラインの下に送信します。 `Select-Object`**Property** パラメーターを使用して、表示するプロパティを指定します。 パイプライン内の各オブジェクトについて、の式によって、 `$date` 更新 **後の時間** が変換され、 **Date** プロパティの結果が出力されます。

### 例 5: プロパティを使用してシーケンス番号を取得する

この例では、 **SequenceNumber** プロパティと配列インデックスを使用して、シーケンス番号を取得します。 出力には、シーケンス番号だけが含まれます。

```powershell
((Get-ComputerRestorePoint).SequenceNumber)[-1]
```

```Output
6
```

`Get-ComputerRestorePoint` 配列インデックスで **SequenceNumber** プロパティを使用します。 の配列インデックスは、 `-1` 配列内の最新のシーケンス番号を取得します。

## PARAMETERS

### -LastStatus

が `Get-ComputerRestorePoint` 最新のシステム復元操作の状態を取得することを示します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LastStatus
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestorePoint

システムの復元ポイントのシーケンス番号を指定します。 1つのシーケンス番号を指定することも、シーケンス番号のコンマ区切りの配列を指定することもできます。

**Restorepoint** パラメーターが指定されていない場合、は `Get-ComputerRestorePoint` すべてのローカルコンピューターのシステム復元ポイントを返します。

```yaml
Type: System.Int32[]
Parameter Sets: ID
Aliases:

Required: False
Position: 0
Default value: All restore points
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし

オブジェクトをパイプラインからに送信することはできません `Get-ComputerRestorePoint` 。

## 出力

### System.management.managementobject # root\default\SystemRestore または String

`Get-ComputerRestorePoint`**systemrestore** オブジェクトを返します。これは、WINDOWS MANAGEMENT INSTRUMENTATION (WMI) **systemrestore** クラスのインスタンスです。

**Laststatus** パラメーターを使用すると、は `Get-ComputerRestorePoint` 文字列を返します。

## 注

`Get-ComputerRestorePoint`Windows Vista 以降のバージョンの windows でコマンドを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を開きます。

`Get-ComputerRestorePoint` では、WMI **Systemrestore** クラスを使用します。

## 関連リンク

[about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[about_Arrays](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[Checkpoint-Computer](Checkpoint-Computer.md)

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)

[SystemRestore](/windows/win32/sr/systemrestore)
