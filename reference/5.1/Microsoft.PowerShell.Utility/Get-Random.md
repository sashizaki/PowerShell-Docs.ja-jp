---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: 6aa7d6db9e8c2fb8a3001c8ddb9593a7ceafe2ab
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213955"
---
# Get-Random

## 概要
乱数を取得するか、オブジェクトをコレクションからランダムに選択します。

## SYNTAX

### RandomNumberParameterSet (既定値)

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [<CommonParameters>]
```

### RandomListItemParameterSet

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

## Description

`Get-Random`コマンドレットでは、ランダムに選択された番号を取得します。 オブジェクトのコレクションをに送信すると `Get-Random` 、コレクションからランダムに選択された1つ以上のオブジェクトを取得します。

パラメーターまたは入力を指定しない場合、コマンドは、 `Get-Random` 0 (ゼロ) ~ int32.maxvalue (,) **Int32.MaxValue** の間でランダムに選択された32ビット符号なし整数を返し `0x7FFFFFFF` `2,147,483,647` ます。

のパラメーターを使用して、 `Get-Random` シード番号、最小値と最大値、および送信されたコレクションから返されるオブジェクトの数を指定できます。

## 例

### 例 1: ランダムな整数を取得する

このコマンド **は、0** (ゼロ) ~ int32.maxvalue のランダムな整数を取得します。

```powershell
Get-Random
```

```Output
3951433
```

### 例 2: 0 と99の間のランダムな整数を取得する

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### 例 3:-100 と99の間のランダムな整数を取得する

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### 例 4: ランダムな浮動小数点数を取得する

このコマンドは 10.7 以上 20.92 未満の浮動小数点乱数を取得します。

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### 例 5: 配列からランダムな整数を取得する

このコマンドは、指定された配列からランダムに選択された数値を取得します。

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### 例 6: 配列から複数のランダムな整数を取得する

このコマンドは、ランダムに選択された3つの数値を配列からランダムな順序で取得します。

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### 例 7: コレクション全体をランダム化する

このコマンドは、ランダムな順序でコレクション全体を返します。

**Count** パラメーターの値は、整数の **MaxValue** 静的プロパティです。

ランダムな順序でコレクション全体を返すには、コレクション内のオブジェクトの数以上の任意の数値を入力します。

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count ([int]::MaxValue)
```

```Output
2
3
5
1
8
13
```

### 例 8: ランダムな数値以外の値を取得する

このコマンドは、数値以外のコレクションから、乱数値を返します。

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### 例 9: SetSeed パラメーターを使用する

この例は、 **SetSeed** パラメーターを使用した場合の効果を示しています。

**Setseed** は、ランダムではない動作を生成するため、通常は、スクリプトのデバッグや分析などの結果を再現するためだけに使用されます。

```powershell
# Commands with the default seed are pseudorandom
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100
Get-Random -Maximum 100
Get-Random -Maximum 100
```

```Output
74
56
84
46
```

```powershell
# Commands with the same seed are not random
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100 -SetSeed 23
```

```Output
74
74
74
```

```powershell
# SetSeed results in a repeatable series
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100
Get-Random -Maximum 100
Get-Random -Maximum 100
```

```Output
74
56
84
46
```

### 例 10: ランダムファイルを取得する

これらのコマンドは、ローカルコンピューターのドライブからランダムに選択された50ファイルのサンプルを取得し `C:` ます。

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### 例 11: ロールフェアダイス

この例では、公正な1200回をロールし、結果をカウントします。 最初のコマンドは、 `For-EachObject` `Get-Random` パイプされた数 (1-6) からの呼び出しを繰り返します。 結果は、の値によってグループ化され、 `Group-Object` でテーブルとして書式設定され `Select-Object` ます。

```powershell
1..1200 | ForEach-Object {
    1..6 | Get-Random
} | Group-Object | Select-Object Name,Count
```

```Output
Name Count
---- -----
1      206
2      199
3      196
4      226
5      185
6      188
```

## PARAMETERS

### -カウント

ランダムに返されるオブジェクトまたは数値の数を指定します。 既定値は 1 です。

と共に使用する場合、 `InputObject` **Count** の値がコレクション内のオブジェクトの数を超えると、 `Get-Random` はランダムな順序ですべてのオブジェクトを返します。

```yaml
Type: System.Int32
Parameter Sets: RandomListItemParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

オブジェクトのコレクションを指定します。 `Get-Random` コレクションから、 **Count** で指定した数までランダムに選択されたオブジェクトをランダムな順序で取得します。 オブジェクト、オブジェクトを含む変数、またはオブジェクトを取得するコマンドまたは式を入力します。 パイプを使用してオブジェクトのコレクションをにパイプすることもでき `Get-Random` ます。

```yaml
Type: System.Object[]
Parameter Sets: RandomListItemParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -最大

乱数の最大値を指定します。 `Get-Random` は、最大値 (等しくない) より小さい値を返します。 整数、倍精度浮動小数点数、または数値文字列 ("100") などの整数または倍精度に変換できるオブジェクトを入力します。

**Maximum** の値は、 **Minimum** の値より大きくする必要があります (等しくない)。 **最大** 値または **最小** 値が浮動小数点数の場合、は `Get-Random` ランダムに選択された浮動小数点数を返します。

64ビットのコンピューターでは、[ **最小** ] の値が32ビットの整数の場合、[ **最大** 値] の既定値は int32.maxvalue. **MaxValue** です。

**Minimum** の値が double (浮動小数点数) の場合、 **Maximum** の既定値は **2 倍** です。 それ以外の場合、既定 **値は int32.maxvalue です。**

```yaml
Type: System.Object
Parameter Sets: RandomNumberParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -最小

乱数の最小値を指定します。 整数、倍精度浮動小数点数、または数値文字列 ("100") などの整数または倍精度に変換できるオブジェクトを入力します。 既定値は 0 (ゼロ) です。

**Minimum** の値は、 **Maximum** の値より小さくする必要があります (等しくない)。 **最大** 値または **最小** 値が浮動小数点数の場合、は `Get-Random` ランダムに選択された浮動小数点数を返します。

```yaml
Type: System.Object
Parameter Sets: RandomNumberParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SetSeed

乱数ジェネレーターのシード値を指定します。 このシード値は、現在のコマンドと、 `Get-Random` **setseed** を再度使用するかセッションを閉じるまで、現在のセッションの後続のすべてのコマンドに使用されます。 シードを既定値にリセットすることはできません。

**Setseed** パラメーターは必要ありません。 既定では、は `Get-Random` [RandomNumberGenerator ()](/dotnet/api/system.security.cryptography.randomnumbergenerator) メソッドを使用してシード値を生成します。 **Setseed** は、ランダムではない動作をするため、通常は、コマンドを含むスクリプトをデバッグまたは分析する場合など、動作を再現しようとした場合にのみ使用され `Get-Random` ます。

```yaml
Type: System.Nullable`1[System.Int32]
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

### System.Object

パイプを使用して1つ以上のオブジェクトをパイプ処理できます。 `Get-Random` パイプされたオブジェクトからランダムに値を選択します。

## 出力

### System.string, system.string, system.string, system.string

`Get-Random` 整数または浮動小数点数、または送信されたコレクションからランダムに選択されたオブジェクトを返します。

## 注

`Get-Random` セッションの開始時に、システム時刻のクロックに基づいて、各セッションの既定のシードを設定します。

`Get-Random` は、必ずしも入力値と同じデータ型を返すとは限りません。 次の表は、各数値入力型の出力の種類を示しています。

| 入力タイプ | 出力の種類 |
| :--------: | :---------: |
|   SByte    |   Double    |
|    Byte    |   Double    |
|   Int16    |   Double    |
|   UInt16   |   Double    |
|   Int32    |    Int32    |
|   UInt32   |   Double    |
|   Int64    |    Int64    |
|   UInt64   |   Double    |
|   Double   |   Double    |
|   Single   |   Double    |

Windows PowerShell 3.0 以降では、は `Get-Random` 64 ビット整数をサポートしています。 Windows PowerShell 2.0 では、すべての値が **system.string にキャストされます。**

## 関連リンク
