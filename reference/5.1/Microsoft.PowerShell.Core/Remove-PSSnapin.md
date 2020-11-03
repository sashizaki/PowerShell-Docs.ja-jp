---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSnapin
ms.openlocfilehash: e74aff3e52c61f41a54664efbab9c0f195b0d409
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212779"
---
# Remove-PSSnapin

## 概要
現在のセッションから Windows PowerShell スナップインを削除します。

## SYNTAX

```
Remove-PSSnapin [-Name] <String[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**Add-pssnapin** コマンドレットは、Windows PowerShell スナップインを現在のセッションから削除します。
このコマンドレットを使用すると、windows PowerShell に追加したスナップインを削除できます。このコマンドレットを使用して、Windows PowerShell でインストールされているスナップインを削除することはできません。

現在のセッションからスナップインを削除すると、スナップインはまだ読み込まれていますが、スナップイン内のコマンドレットとプロバイダーはセッションで使用できなくなります。

## 例

### 例 1: スナップインを削除する

```
PS C:\> remove-pssnapin -Name Microsoft.Exchange
```

このコマンドは、現在のセッションから、 **Microsoft Exchange** のスナップインを削除します。
コマンドが完了すると、スナップインがサポートしていたコマンドレットとプロバイダーは、セッションで使用できなくなります。

### 例 2: パイプラインで名前を使用してスナップインを削除する

```
PS C:\> Get-PSSnapIn smp* | Remove-PSSnapIn
```

このコマンドは、現在のセッションから、smp で始まる名前を持つ Windows PowerShell スナップインを削除します。

このコマンドは、 **add-pssnapin** コマンドレットを使用して、スナップインを表すオブジェクトを取得します。パイプライン演算子 (|) により、結果が **add-pssnapin** コマンドレットに送信され、セッションから削除されます。
このスナップインがサポートするプロバイダーとコマンドレットは、セッションで使用できなくなります。

パイプを使用してオブジェクトを **add-pssnapin** に渡すと、オブジェクトの名前が *name* パラメーターに関連付けられます。このパラメーターは、 **name** プロパティを持つパイプラインからのオブジェクトを受け入れます。

### 例 3: 名前を使用してスナップインを削除する

```
PS C:\> Remove-PSSnapin -Name *event*
```

このコマンドは、イベントを含む名前を持つすべての Windows PowerShell スナップインを削除します。

## PARAMETERS

### -Name
現在のセッションから削除する Windows PowerShell スナップインの名前を指定します。
ワイルドカード文字 (*) が許可されます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
スナップインを表すオブジェクトを返します。
既定では、このコマンドレットによる出力はありません。

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

### システム管理. PSSnapInInfo
パイプを使用して、このコマンドレットにスナップインオブジェクトをパイプすることができます。

## 出力

### なし、システム管理. PSSnapInInfo
このコマンドレットは、 *PassThru* パラメーターを指定した場合に、スナップインを表す **system.string オブジェクトを** 生成します。
既定では、 **add-pssnapin** は出力を生成しません。

## 注

* **Add-pssnapin** は、セッションからスナップインを削除する前に、Windows PowerShell のバージョンを確認しません。 スナップインを削除できない場合は、警告が表示され、コマンドは失敗します。
* **Add-pssnapin** は、現在のセッションのみに影響します。 Add-PSSnapin コマンドを Windows PowerShell プロファイルに追加した場合は、コマンドを削除して、それ以降のセッションからスナップインを削除する必要があります。 手順については、「」と入力 `Get-Help about_Profiles` します。

## 関連リンク

[Add-PSSnapin](Add-PSSnapin.md)

[Get-PSSnapin](Get-PSSnapin.md)
