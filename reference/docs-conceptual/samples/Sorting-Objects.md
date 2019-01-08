---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: オブジェクトの並べ替え
ms.assetid: 8530caa8-3ed4-4c56-aed7-1295dd9ba199
ms.openlocfilehash: 06aa15d89888f1ecbe60b8e1dfb4efebb1d73673
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402230"
---
# <a name="sorting-objects"></a>オブジェクトの並べ替え

表示されているデータを使用してスキャンするが容易に整理できます、`Sort-Object`コマンドレット。 `Sort-Object` 並べ替えには、使用する 1 つまたは複数のプロパティの名前を受け取り、これらのプロパティの値で並べ替えられたデータを返します。

## <a name="basic-sorting"></a>基本的な並べ替え

サブディレクトリと現在のディレクトリにファイルを一覧表示の問題を検討してください。
並べ替えたい場合**LastWriteTime** 、まず**名前**、」と入力して実行できます。

```powershell
Get-ChildItem |
  Sort-Object -Property LastWriteTime, Name |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
11/6/2017 10:10:11 AM  .localization-config
11/6/2017 10:10:11 AM  .openpublishing.build.ps1
11/6/2017 10:10:11 AM  appveyor.yml
11/6/2017 10:10:11 AM  LICENSE
11/6/2017 10:10:11 AM  LICENSE-CODE
11/6/2017 10:10:11 AM  ThirdPartyNotices
11/6/2017 10:10:15 AM  tests
6/6/2018 7:58:59 PM    CONTRIBUTING.md
6/6/2018 7:58:59 PM    README.md
...
```

並べ替えることができますも、オブジェクトを逆の順序を指定して、**降順**スイッチ パラメーター。

```powershell
Get-ChildItem |
  Sort-Object -Property LastWriteTime, Name -Descending |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
12/1/2018 10:13:50 PM  reference
12/1/2018 10:13:50 PM  dsc
...
6/6/2018 7:58:59 PM    README.md
6/6/2018 7:58:59 PM    CONTRIBUTING.md
11/6/2017 10:10:15 AM  tests
11/6/2017 10:10:11 AM  ThirdPartyNotices
11/6/2017 10:10:11 AM  LICENSE-CODE
11/6/2017 10:10:11 AM  LICENSE
11/6/2017 10:10:11 AM  appveyor.yml
11/6/2017 10:10:11 AM  .openpublishing.build.ps1
11/6/2017 10:10:11 AM  .localization-config
```

## <a name="using-hash-tables"></a>ハッシュ テーブルを使用します。

配列のハッシュ テーブルを使用して、異なる順序でさまざまなプロパティを並べ替えることができます。
各ハッシュ テーブルを使用して、**式**キー プロパティ名を文字列として指定して、**昇順**または**降順**キーによって並べ替え順序を指定する`$true`または`$false`.
**式**キーは必須です。
**昇順**または**降順**キーは省略可能です。

次の例は、降順でオブジェクトを並べ替えます**LastWriteTime**順序、昇順**名前**順序。

```powershell
Get-ChildItem |
  Sort-Object -Property @{ Expression = 'LastWriteTime'; Descending = $true }, @{ Expression = 'Name'; Ascending = $true } |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
12/1/2018 10:13:50 PM  dsc
12/1/2018 10:13:50 PM  reference
11/29/2018 6:56:01 PM  .openpublishing.redirection.json
11/29/2018 6:56:01 PM  gallery
11/24/2018 10:33:22 AM developer
11/20/2018 7:22:19 PM  .markdownlint.json
...
```

スクリプト ブロックを設定することも、**式**キー。
実行するときに、`Sort-Object`コマンドレットは、スクリプト ブロックが実行され、結果の並べ替えに使用します。

次の例は、間の時間の降順でオブジェクトを並べ替えます**CreationTime**と**LastWriteTime**します。

```powershell
Get-ChildItem |
  Sort-Object -Property @{ Expression = { $_.LastWriteTime - $_.CreationTime }; Descending = $true } |
  Format-Table -Property LastWriteTime, CreationTime
```

```output
LastWriteTime          CreationTime
-------------          ------------
12/1/2018 10:13:50 PM  11/6/2017 10:10:11 AM
12/1/2018 10:13:50 PM  11/6/2017 10:10:11 AM
11/7/2018 6:52:24 PM   11/6/2017 10:10:11 AM
11/7/2018 6:52:24 PM   11/6/2017 10:10:15 AM
11/3/2018 9:58:17 AM   11/6/2017 10:10:11 AM
10/26/2018 4:50:21 PM  11/6/2017 10:10:11 AM
11/17/2018 1:10:57 PM  11/29/2017 5:48:30 PM
11/12/2018 6:29:53 PM  12/7/2017 7:57:07 PM
...
```

## <a name="tips"></a>ヒント

省略することができます、**プロパティ**として次のパラメーター名。

```powershell
Sort-Object LastWriteTime, Name
```

参照する以外にも、`Sort-Object`その組み込みエイリアスで`sort`:

```powershell
sort LastWriteTime, Name
```

次のように、ハッシュ テーブル内の並べ替えのキーを省略できます。

```powershell
Sort-Object @{ e = 'LastWriteTime'; d = $true }, @{ e = 'Name'; a = $true }
```

この例で、 **e**略**式**、 **d**略**降順**、および **、** 略**昇順**します。

読みやすさを向上させるのには、別個の変数に、ハッシュ テーブルを配置できます。

```powershell
$order = @(
  @{ Expression = 'LastWriteTime'; Descending = $true }
  @{ Expression = 'Name'; Ascending = $true }
)

Get-ChildItem |
  Sort-Object $order |
  Format-Table LastWriteTime, Name
```