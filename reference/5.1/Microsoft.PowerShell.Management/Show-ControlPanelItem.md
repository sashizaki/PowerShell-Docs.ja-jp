---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-ControlPanelItem
ms.openlocfilehash: 368e385d51437f9ac93b700c929b185dce30a644
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214403"
---
# Show-ControlPanelItem

## 概要
コントロール パネル項目を開きます。

## SYNTAX

### RegularName (既定値)

```
Show-ControlPanelItem [-Name] <String[]> [<CommonParameters>]
```

### CanonicalName

```
Show-ControlPanelItem -CanonicalName <String[]> [<CommonParameters>]
```

### Get-controlpanelitem

```
Show-ControlPanelItem [[-InputObject] <ControlPanelItem[]>] [<CommonParameters>]
```

## Description

コマンドレットにより、 `Show-ControlPanelItem` ローカルコンピューター上のコントロールパネル項目が開きます。 これを使用すると、ユーザーインターフェイスを持たないシステムであっても、名前、カテゴリ、または説明でコントロールパネル項目を開くことができます。 パイプを使用して、コントロールパネルの項目をコマンドレットからに送ることができ `Get-ControlPanelItem` `Show-ControlPanelItem` ます。

`Show-ControlPanelItem` システムで開くことができるコントロールパネル項目だけを検索します。 **コントロールパネル** または **エクスプローラー** がインストールされていないコンピューターでは、は、 `Show-ControlPanelItem` これらのコンポーネントなしで開くことができるコントロールパネル項目だけを検索します。

このコマンドレットは、windows PowerShell 3.0 で導入され、Windows 8、Windows Server 2012、およびそれ以降のバージョンで動作します。

## 例

### 例 1: コントロールパネル項目を表示する

この例では、[ **自動再生** ] コントロールパネル項目を起動します。

```powershell
Show-ControlPanelItem -Name "AutoPlay"
```

### 例 2: パイプを使用してコントロールパネル項目をこのコマンドレットにする

この例では、ローカルコンピューターの [ **Windows Defender ファイアウォール** ] コントロールパネル項目を開きます。
Windows ファイアウォールのコントロールパネル項目の名前が、Windows のバージョンによって変更されました。 この例では、ワイルドカードパターンを使用して、コントロールパネル項目を検索します。

```powershell
Get-ControlPanelItem -Name "*Firewall" | Show-ControlPanelItem
```

`Get-ControlPanelItem` コントロールパネル項目を取得し、 `Show-ControlPanelItem` コマンドレットでそれを開きます。

### 例 3: ファイル名を使用してコントロール パネル項目を開く

この例では、[ **プログラムと機能** ] コントロールパネル項目をアプリケーション名を使用して開きます。

```powershell
appwiz.cpl
```

このメソッドは、コマンドを使用する代わりに使用し `Show-ControlPanelItem` ます。

> [!NOTE]
> PowerShell では、コントロールパネルファイルの .cpl ファイル拡張子を省略できます。これは、環境変数の値に含まれているためです `$env:PathExt` 。

## PARAMETERS

### -CanonicalName

指定された正規名または名前パターンを使用して、コントロールパネル項目を指定します。 ワイルドカード文字を使用できます。 複数の名前を入力すると、このコマンドレットは、名前リストの項目が **or** 演算子で区切られた場合と同様に、任意の名前に一致するコントロールパネル項目を開きます。

```yaml
Type: System.String[]
Parameter Sets: CanonicalName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -InputObject

コントロールパネル項目オブジェクトを送信することによって開くコントロールパネル項目を指定します。 コントロールパネル項目オブジェクトが格納されている変数を入力するか、などのコントロールパネル項目オブジェクトを取得するコマンドまたは式を入力し `Get-ControlPanelItem` ます。

```yaml
Type: Microsoft.PowerShell.Commands.ControlPanelItem[]
Parameter Sets: ControlPanelItem
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

コントロールパネル項目の名前を指定します。 ワイルドカード文字を使用できます。 複数の名前を入力すると、このコマンドレットは、名前リストの項目が **or** 演算子で区切られた場合と同様に、任意の名前に一致するコントロールパネル項目を開きます。

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### System.string、Microsoft. PowerShell. Controloffice

パイプを使用して、名前またはコントロールパネルの項目オブジェクトをこのコマンドレットに渡します。

## 出力

### なし

このコマンドレットによる戻り値はありません。

## 注

## 関連リンク

[Get-ControlPanelItem](Get-ControlPanelItem.md)
