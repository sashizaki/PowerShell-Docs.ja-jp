---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: パイプラインからオブジェクトを削除する (Where-Object)
ms.openlocfilehash: 370e7745341b70c0794352a690d5750d21f53ac2
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "75737187"
---
# <a name="removing-objects-from-the-pipeline-where-object"></a>パイプラインからオブジェクトを削除する (Where-Object)

PowerShell では、考えていた数よりも多くのオブジェクトが生成され、パイプラインに渡されることがよくあります。 `Format-*` コマンドレットを使用して、特定のオブジェクトのプロパティを指定し、表示することができます。しかし、これはオブジェクト全体を表示から削除するという問題には役立ちません。 パイプラインの終了前に、オブジェクトをフィルタリングすることによって、最初に生成されたオブジェクトのサブセット上でのみアクションを実行できます。

PowerShell には、`Where-Object` コマンドレットがあります。これを使用すると、パイプラインの各オブジェクトをテストし、特定のテスト条件を満たしている場合にのみ、オブジェクトをパイプラインに沿って渡すことができます。 テストを通過しなかったオブジェクトは、パイプラインから削除されます。 テスト条件は、**FilterScript** パラメーターの値として指定します。

## <a name="performing-simple-tests-with-where-object"></a>Where-Object を使用して単純なテストを実行する

**FilterScript** の値は、true または false に評価される*スクリプト ブロック* - (中かっこ `{}` で囲まれた 1 つまたは複数の PowerShell コマンド) です。 これらのスクリプト ブロックはごく単純にすることができますが、作成するには別の PowerShell の概念である比較演算子について知っておく必要があります。 比較演算子は、演算子の両辺のアイテムを比較します。 比較演算子は、ハイフン文字 (`-`) 文字で始まり、名前が続きます。 基本的な比較演算子は、ほとんどの種類のオブジェクトで機能します。 より高度な比較演算子の中には、テキストまたは配列でのみ機能するものもあります。

> [!NOTE]
> 既定では、テキストで使用する場合、PowerShell の比較演算子は大文字小文字を区別しません。

解析の考慮事項のため、`<`、`>`、`=` などのシンボルは、比較演算子として使用されません。 代わりに、比較演算子は文字で構成されます。 基本的な比較演算子を次の表に挙げます。

| 比較演算子 |                  意味                   |    例 (true を返す)    |
| ------------------- | ------------------------------------------ | ---------------------------- |
| -eq                 | 次の値と等しい                                | 1 -eq 1                      |
| -ne                 | 次の値と等しくない                            | 1 -ne 2                      |
| -lt                 | 次の値未満                               | 1 -lt 2                      |
| -le                 | 次の値以下                   | 1 -le 2                      |
| -gt                 | 次の値より大きい                            | 2 -gt 1                      |
| -ge                 | 次の値以上                | 2 -ge 1                      |
| -like               | 次の文字列と類似 (テキストのワイルドカード比較)     | "file.doc" -like "f*.do?"    |
| -notlike            | 次の文字列と類似していない (テキストのワイルドカード比較) | "file.doc" -notlike "p*.doc" |
| -contains           | Contains                                   | 1,2,3 -contains 1            |
| -notcontains        | [次の値を含まない]                           | 1,2,3 -notcontains 4         |

`Where-Object` スクリプト ブロックは、パイプライン中の現在のオブジェクトを参照するために、特殊変数 `$_` を使用します。 次に挙げるのは、その働きを示す例です。 数値の一覧があり、3 未満の値だけを返したい場合、`Where-Object` を使用して、次のように入力して数値を抽出できます。

```
1,2,3,4 | Where-Object {$_ -lt 3}
1
2
```

## <a name="filtering-based-on-object-properties"></a>オブジェクトのプロパティに基づくフィルタリング

`$_` は、現在のパイプライン オブジェクトを参照するので、テストのためにそのプロパティにアクセスできます。

例として、WMI の **Win32_SystemDriver** クラスを取り上げます。 特定のシステムには、何百ものシステム ドライバーが存在する可能性がありますが、関心を向けるのは、現在実行中のシステム ドライバーなど、システム ドライバーの特定のセットだけの場合があります。 **Win32_SystemDriver** クラスの場合、関連するプロパティは **State** です。 システム ドライバーをフィルタリングして、次のように入力して実行中のドライバーのみを選択できます。

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq 'Running'}
```

生成されるのは、依然として長い一覧です。 **StartMode** 値を同様にテストして、自動的に起動されるドライバーのセットのみを選択するようフィルタリングすることにします。

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq "Running"} |
    Where-Object {$_.StartMode -eq "Auto"}
```

```Output
DisplayName : RAS Asynchronous Media Driver
Name        : AsyncMac
State       : Running
Status      : OK
Started     : True

DisplayName : Audio Stub Driver
Name        : audstub
State       : Running
Status      : OK
Started     : True
...
```

これにより、もう必要のない数多くの情報が与えられます。それらのドライバーが実行中なのはわかっています。
事実、この時点でおそらく必要とされる情報は、名前と表示名だけです。 次のコマンドには、それら 2 つのプロパティのみが含まれており、よりシンプルに結果を出力します。

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq "Running"} |
    Where-Object {$_.StartMode -eq "Manual"} |
      Format-Table -Property Name,DisplayName
```

```Output
Name              DisplayName
----              -----------
AsyncMac               RAS Asynchronous Media Driver
bindflt                Windows Bind Filter Driver
bowser                 Browser
CompositeBus           Composite Bus Enumerator Driver
condrv                 Console Driver
HdAudAddService        Microsoft 1.1 UAA Function Driver for High Definition Audio Service
HDAudBus               Microsoft UAA Bus Driver for High Definition Audio
HidUsb                 Microsoft HID Class Driver
HTTP                   HTTP Service
igfx                   igfx
IntcDAud               Intel(R) Display Audio
intelppm               Intel Processor Driver
...
```

上記のコマンドには `Where-Object` 要素が 2 つありますが、次のように `Where-Object` 論理演算子を使用して、`-and` 要素 1 つで表現することができます。

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {($_.State -eq 'Running') -and ($_.StartMode -eq 'Manual')} |
    Format-Table -Property Name,DisplayName
```

標準的な論理演算子を次の表に挙げます。

| 論理演算子 |                 意味                  |  例 (true を返す)  |
| ---------------- | ---------------------------------------- | ------------------------ |
| -and             | 論理積。両辺が true の場合は true | (1 -eq 1) -and (2 -eq 2) |
| -or              | 論理和。どちらかの辺が true の場合は true  | (1 -eq 1) -or (1 -eq 2)  |
| -not             | 論理否定。true と false を逆にする     | -not (1 -eq 2)           |
| \!               | 論理否定。true と false を逆にする     | \!(1 -eq 2)              |
