---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: オブジェクトの並べ替え
description: Sort-Object コマンドレットを使用すると、オブジェクトのコレクションを 1 つまたは複数のプロパティで並べ替えることができます。
ms.openlocfilehash: 836207adfc566003e9714e45920d9b4e24a677e9
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501016"
---
# <a name="sorting-objects"></a>オブジェクトの並べ替え

`Sort-Object` コマンドレットを使用すると、表示データを見やすく整理できます。
`Sort-Object` では、並べ替え条件としてプロパティ名 (複数可) を指定すると、そのプロパティ値で並べ替えられたデータが返されます。

## <a name="basic-sorting"></a>基本的な並べ替え

現在のディレクトリ内のサブディレクトリとファイルを一覧表示する問題について考えます。
**LastWriteTime** で並べ替えた後、 **Name** で並べ替えるには、次のように入力します。

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

**Descending** スイッチ パラメーターを指定して、オブジェクトを降順に並べ替えることもできます。

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

## <a name="using-hash-tables"></a>ハッシュ テーブルを使用する

配列でハッシュ テーブルを使用することにより、異なるプロパティを異なる順序で並べ替えることができます。
各ハッシュ テーブルでは、 **Expression** キーを使用してプロパティ名を文字列として指定し、 **Ascending** または **Descending** キーを使用して `$true` または `$false` で並べ替え順序を指定します。
**Expression** キーは必須です。
**Ascending** キーまたは **Descending** キーは省略可能です。

次の例では、オブジェクトを **LastWriteTime** については降順に、 **Name** については昇順に並べ替えます。

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

**Expression** キーに対してスクリプトブロックを設定することもできます。
`Sort-Object` コマンドレットを実行すると、スクリプトブロックが実行されて、結果が並べ替えに使用されます。

次の例では、 **CreationTime** から **LastWriteTime** までの期間について、オブジェクトを降順に並べ替えます。

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

次のように、 **Property** パラメーター名は省略できます。

```powershell
Sort-Object LastWriteTime, Name
```

さらに、組み込みの別名 `sort` で `Sort-Object` を参照できます。

```powershell
sort LastWriteTime, Name
```

並べ替え用のハッシュ テーブル内のキーは、次のように省略できます。

```powershell
Sort-Object @{ e = 'LastWriteTime'; d = $true }, @{ e = 'Name'; a = $true }
```

この例では、 **e** は **Expression** を表し、 **d** は **Descending** を表し、 **a** は **Ascending** を表します。

読みやすさを向上させるため、ハッシュ テーブルを別の変数に配置できます。

```powershell
$order = @(
  @{ Expression = 'LastWriteTime'; Descending = $true }
  @{ Expression = 'Name'; Ascending = $true }
)

Get-ChildItem |
  Sort-Object $order |
  Format-Table LastWriteTime, Name
```
