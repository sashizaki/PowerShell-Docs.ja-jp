---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: 複数のオブジェクトのタスクを繰り返す (ForEach-Object)
description: ForEach-Object を使用すると、パイプラインを通して渡された各オブジェクトに対して、コマンドのセットを繰り返すことができます。
ms.openlocfilehash: 7353be833dc8bf77dd18b7fc45bdd97e092ff6ef
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92499959"
---
# <a name="repeating-a-task-for-multiple-objects-foreach-object"></a>複数のオブジェクトのタスクを繰り返す (ForEach-Object)

`ForEach-Object` コマンドレットは、現在のパイプライン オブジェクトのスクリプト ブロックと `$_` 記述子を使用して、パイプライン内の各オブジェクトのコマンドを実行できるようにします。 これは、いくつかの複雑なタスクを実行するために使用できます。

これが有用な状況の 1 つは、データをさらに有効活用するよう操作する場合です。 たとえば、WMI からの **Win32_LogicalDisk** クラスは、各ローカル ディスクの空き領域の情報を返すのに使用できます。 データはバイト単位で返されますが、次のように、読み取るのは困難です。

```powershell
Get-CimInstance -Class Win32_LogicalDisk
```

```Output
DeviceID DriveType ProviderName VolumeName Size          FreeSpace
-------- --------- ------------ ---------- ----          ---------
C:       3                      Local Disk 203912880128  50665070592
```

**FreeSpace** の値を 1 MB で割ると、メガバイト単位に変換できます。 `ForEach-Object` のスクリプト ブロックでこのことを実行できます。次のように入力します。

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  ForEach-Object -Process {($_.FreeSpace)/1MB}
```

```Output
48318.01171875
```

残念ながら、出力はラベルとは関連付けられていないデータになります。 この例のように、WMI プロパティは読み取り専用なので、 **FreeSpace** を直接変換することはできません。 次のように入力するとします。

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1MB}
```

次のようなエラー メッセージが表示されます。

```Output
"FreeSpace" is a ReadOnly property.
At line:2 char:28
+   ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1MB}
+                            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : NotSpecified: (:) [], SetValueException
+ FullyQualifiedErrorId : ReadOnlyCIMProperty
```

高度な技法をいくつか使用してデータを再編成できますが、よりシンプルな方法は、`Select-Object` を使用して新しいオブジェクトを作成することです。
