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
# <a name="repeating-a-task-for-multiple-objects-foreach-object"></a><span data-ttu-id="8f942-104">複数のオブジェクトのタスクを繰り返す (ForEach-Object)</span><span class="sxs-lookup"><span data-stu-id="8f942-104">Repeating a Task for Multiple Objects (ForEach-Object)</span></span>

<span data-ttu-id="8f942-105">`ForEach-Object` コマンドレットは、現在のパイプライン オブジェクトのスクリプト ブロックと `$_` 記述子を使用して、パイプライン内の各オブジェクトのコマンドを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8f942-105">The `ForEach-Object` cmdlet uses script blocks and the `$_` descriptor for the current pipeline object to let you run a command on each object in the pipeline.</span></span> <span data-ttu-id="8f942-106">これは、いくつかの複雑なタスクを実行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f942-106">This can be used to perform some complicated tasks.</span></span>

<span data-ttu-id="8f942-107">これが有用な状況の 1 つは、データをさらに有効活用するよう操作する場合です。</span><span class="sxs-lookup"><span data-stu-id="8f942-107">One situation where this can be useful is manipulating data to make it more useful.</span></span> <span data-ttu-id="8f942-108">たとえば、WMI からの **Win32_LogicalDisk** クラスは、各ローカル ディスクの空き領域の情報を返すのに使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f942-108">For example, the **Win32_LogicalDisk** class from WMI can be used to return free space information for each local disk.</span></span> <span data-ttu-id="8f942-109">データはバイト単位で返されますが、次のように、読み取るのは困難です。</span><span class="sxs-lookup"><span data-stu-id="8f942-109">The data is returned in terms of bytes, however, which makes it difficult to read:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk
```

```Output
DeviceID DriveType ProviderName VolumeName Size          FreeSpace
-------- --------- ------------ ---------- ----          ---------
C:       3                      Local Disk 203912880128  50665070592
```

<span data-ttu-id="8f942-110">**FreeSpace** の値を 1 MB で割ると、メガバイト単位に変換できます。</span><span class="sxs-lookup"><span data-stu-id="8f942-110">We can convert the **FreeSpace** value to megabytes by dividing each value by 1MB.</span></span> <span data-ttu-id="8f942-111">`ForEach-Object` のスクリプト ブロックでこのことを実行できます。次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8f942-111">You can do that in a `ForEach-Object` script block by typing:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  ForEach-Object -Process {($_.FreeSpace)/1MB}
```

```Output
48318.01171875
```

<span data-ttu-id="8f942-112">残念ながら、出力はラベルとは関連付けられていないデータになります。</span><span class="sxs-lookup"><span data-stu-id="8f942-112">Unfortunately, the output is now data with no associated label.</span></span> <span data-ttu-id="8f942-113">この例のように、WMI プロパティは読み取り専用なので、 **FreeSpace** を直接変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="8f942-113">Because WMI properties such as this are read-only, you cannot directly convert **FreeSpace** .</span></span> <span data-ttu-id="8f942-114">次のように入力するとします。</span><span class="sxs-lookup"><span data-stu-id="8f942-114">If you type this:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1MB}
```

<span data-ttu-id="8f942-115">次のようなエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f942-115">You get an error message:</span></span>

```Output
"FreeSpace" is a ReadOnly property.
At line:2 char:28
+   ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1MB}
+                            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : NotSpecified: (:) [], SetValueException
+ FullyQualifiedErrorId : ReadOnlyCIMProperty
```

<span data-ttu-id="8f942-116">高度な技法をいくつか使用してデータを再編成できますが、よりシンプルな方法は、`Select-Object` を使用して新しいオブジェクトを作成することです。</span><span class="sxs-lookup"><span data-stu-id="8f942-116">You could reorganize the data by using some advanced techniques, but a simpler approach is to create a new object, by using `Select-Object`.</span></span>
