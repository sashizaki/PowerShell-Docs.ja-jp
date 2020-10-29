---
ms.date: 07/28/2020
keywords: powershell,コマンドレット
title: ファイル、フォルダー、レジストリ キーの操作
description: この記事では、PowerShell を使用してレジストリ キー操作タスクを処理する方法について説明します。
ms.openlocfilehash: 6f653c1fb409a238aa05658e89261a12e96f6fe1
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92499979"
---
# <a name="working-with-files-folders-and-registry-keys"></a>ファイル、フォルダー、レジストリ キーの操作

Windows PowerShell は、名詞の **Item** を使用して Windows PowerShell ドライブで検出された項目を参照します。
Windows PowerShell FileSystem プロバイダーを処理する場合、 **Item** は、ファイル、フォルダー、または Windows PowerShell ドライブである可能性があります。 これらの項目を一覧表示して操作することは、ほとんどの管理設定において重要で基本的なタスクであるため、これらのタスクについては詳細に説明します。

## <a name="enumerating-files-folders-and-registry-keys-get-childitem"></a>ファイル、フォルダー、およびレジストリ キーの列挙 (Get-ChildItem)

特定の場所から項目のコレクションを取得することは一般的なタスクであるため、`Get-ChildItem` コマンドレットは、特にフォルダーなどのコンテナー内で見つかったすべての項目を返すよう設計されています。

C:\\Windows フォルダー内に直接含まれるすべてのファイルとフォルダーを返す場合は、次のように入力します。

```
PS> Get-ChildItem -Path C:\Windows
    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2006-05-16   8:10 AM          0 0.log
-a---        2005-11-29   3:16 PM         97 acc1.txt
-a---        2005-10-23  11:21 PM       3848 actsetup.log
...
```

一覧は、 **Cmd.exe** で `dir` コマンドを入力したとき、または UNIX コマンド シェルで `ls` コマンドを入力したときに表示されるものと似ています。

`Get-ChildItem` コマンドレットのパラメーターを使用して、複雑な一覧表示を実行できます。 次に、いくつかのシナリオで見ていきます。 `Get-ChildItem` コマンドレットの構文を確認するには、次のように入力します。

```powershell
Get-Command -Name Get-ChildItem -Syntax
```

これらのパラメーターは混在して利用でき、詳細にカスタマイズされた出力を取得するのに適しています。

### <a name="listing-all-contained-items--recurse"></a>含まれるすべての項目の一覧表示 (-Recurse)

Windows フォルダー内の項目と、サブフォルダー内に含まれる項目の両方を表示するには、`Get-ChildItem` の **Recurse** パラメーターを使用します。 一覧には、Windows フォルダー内のすべて、およびそのサブフォルダー内の項目が表示されます。 次に例を示します。

```
PS> Get-ChildItem -Path C:\WINDOWS -Recurse

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\WINDOWS
    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\WINDOWS\AppPatch
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM    1852416 AcGenral.dll
...
```

### <a name="filtering-items-by-name--name"></a>名前で項目をフィルター処理する (-名前)

項目の名前のみを表示するには、`Get-Childitem` の **Name** パラメーターを使用します。

```
PS> Get-ChildItem -Path C:\WINDOWS -Name
addins
AppPatch
assembly
...
```

### <a name="forcibly-listing-hidden-items--force"></a>強制的に非表示のアイテムを一覧表示する (-Force)

ファイル エクスプローラーまたは Cmd.exe で通常は非表示の項目は、`Get-ChildItem` コマンドの出力に表示されません。 非表示の項目を表示するには、`Get-ChildItem` の **Force** パラメーターを使用します。
次に例を示します。

```powershell
Get-ChildItem -Path C:\Windows -Force
```

このパラメーターが Force と呼ばれるのは、`Get-ChildItem` コマンドの通常の動作を強制的にオーバーライドできるためです。 Force は、コマンドレットが通常は実行しないアクションを強制するために広く使用されるパラメーターですが、システムのセキュリティを侵害するアクションは実行しません。

### <a name="matching-item-names-with-wildcards"></a>ワイルドカードを使用した項目の名前のマッチング

`Get-ChildItem` コマンドは、一覧表示する項目のパスでワイルドカードを受け付けます。

ワイルドカードのマッチングは Windows PowerShell のエンジンによって処理されるため、ワイルドカードを受け入れるすべてのコマンドレットは、同じ表記法を使用し、マッチングの動作も同じになります。 Windows PowerShell のワイルドカードの表記法は、次のとおりです。

- アスタリスク (`*`) は、任意の文字の 0 個以上の出現と照合します。

- 疑問符 (`?`) は、厳密に 1 つの文字と照合します。

- 左角かっこ (`[`) 文字および右角かっこ (`]`) は、照合する文字のセットを囲みます。

ここでは、ワイルドカードを指定するとどのように機能するか、例を示します。

Windows ディレクトリでサフィックス `.log` が使用され、基本名が正確に 5 文字であるすべてのファイルを検索するには、次のコマンドを入力します。

```
PS> Get-ChildItem -Path C:\Windows\?????.log

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
...
-a---        2006-05-11   6:31 PM     204276 ocgen.log
-a---        2006-05-11   6:31 PM      22365 ocmsn.log
...
-a---        2005-11-11   4:55 AM         64 setup.log
-a---        2005-12-15   2:24 PM      17719 VxSDM.log
...
```

Windows ディレクトリで文字 `x` で始まるすべてのファイルを検索するには、次のように入力します。

```powershell
Get-ChildItem -Path C:\Windows\x*
```

名前が "x" または "z" で始まるすべてのファイルを検索するには、次のように入力します。

```powershell
Get-ChildItem -Path C:\Windows\[xz]*
```

ワイルドカードの詳細については、「[about_Wildcards](/powershell/module/microsoft.powershell.core/about/about_wildcards)」を参照してください。

### <a name="excluding-items--exclude"></a>項目の除外 (-Exclude)

`Get-ChildItem` の **Exclude** パラメーターを使用して、特定の項目を除外できます。 これにより、単一のステートメントで複雑なフィルター処理を実行できます。

たとえば、 **System32** フォルダーで Windows タイム サービスの DLL を検索しようとしていて、DLL の名前について覚えているのは、"W" で始まり "32" が含まれている、ということだけだとします。

`w*32*.dll` のような式によって、条件を満たすすべての DLL が検索されますが、さらにファイルをフィルターで除外し、win32 ファイルを省略したい場合もあります。 これらのファイルを省略するには、 **Exclude** パラメーターにパターン `win*` を指定します。

```
PS> Get-ChildItem -Path C:\WINDOWS\System32\w*32*.dll -Exclude win*

    Directory: C:\WINDOWS\System32

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           3/18/2019  9:43 PM         495616 w32time.dll
-a---           3/18/2019  9:44 PM          35328 w32topl.dll
-a---           1/24/2020  5:44 PM         401920 Wldap32.dll
-a---          10/10/2019  5:40 PM         442704 ws2_32.dll
-a---           3/18/2019  9:44 PM          66048 wsnmp32.dll
-a---           3/18/2019  9:44 PM          18944 wsock32.dll
-a---           3/18/2019  9:44 PM          64792 wtsapi32.dll
```

### <a name="mixing-get-childitem-parameters"></a>Get-ChildItem パラメーターの混在

同じコマンドの中で、`Get-ChildItem` コマンドレットのパラメーターを複数使用できます。 パラメーターを混在させる前に、ワイルドカードのマッチングを理解しておいてください。 たとえば、次のコマンドは、結果を返しません。

```powershell
Get-ChildItem -Path C:\Windows\*.dll -Recurse -Exclude [a-y]*.dll
```

Windows フォルダーに文字 "z" で始まる DLL が 2 つ存在しても、結果を返しません。

返される結果がないのは、パスの一部にワイルドカードを指定したためです。 コマンドが再帰的でも、`Get-ChildItem` コマンドレットは、Windows フォルダー内にあり、名前が `.dll` で終わる項目に制限しています。

名前が特殊なパターンに一致するファイルに対して再帰的な検索を指定するには、 **Include** パラメーターを使用します。

```
PS> Get-ChildItem -Path C:\Windows -Include *.dll -Recurse -Exclude [a-y]*.dll

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows\System32\Setup

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM       8261 zoneoc.dll

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows\System32

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM     337920 zipfldr.dll
```
