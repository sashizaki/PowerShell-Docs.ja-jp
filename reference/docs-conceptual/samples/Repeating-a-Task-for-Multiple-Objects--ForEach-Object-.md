---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: 複数のオブジェクトのタスクを繰り返す (ForEach-Object)
ms.openlocfilehash: bf89070fd9b006fa9b0b262ab63ffadd81072ecc
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736881"
---
# <a name="repeating-a-task-for-multiple-objects-foreach-object"></a><span data-ttu-id="d69e5-103">複数のオブジェクトのタスクを繰り返す (ForEach-Object)</span><span class="sxs-lookup"><span data-stu-id="d69e5-103">Repeating a Task for Multiple Objects (ForEach-Object)</span></span>

<span data-ttu-id="d69e5-104">`ForEach-Object` コマンドレットは、現在のパイプライン オブジェクトのスクリプト ブロックと `$_` 記述子を使用して、パイプライン内の各オブジェクトのコマンドを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d69e5-104">The `ForEach-Object` cmdlet uses script blocks and the `$_` descriptor for the current pipeline object to let you run a command on each object in the pipeline.</span></span> <span data-ttu-id="d69e5-105">これは、いくつかの複雑なタスクを実行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d69e5-105">This can be used to perform some complicated tasks.</span></span>

<span data-ttu-id="d69e5-106">これが有用な状況の 1 つは、データをさらに有効活用するよう操作する場合です。</span><span class="sxs-lookup"><span data-stu-id="d69e5-106">One situation where this can be useful is manipulating data to make it more useful.</span></span> <span data-ttu-id="d69e5-107">たとえば、WMI からの **Win32_LogicalDisk** クラスは、各ローカル ディスクの空き領域の情報を返すのに使用できます。</span><span class="sxs-lookup"><span data-stu-id="d69e5-107">For example, the **Win32_LogicalDisk** class from WMI can be used to return free space information for each local disk.</span></span> <span data-ttu-id="d69e5-108">データはバイト単位で返されますが、次のように、読み取るのは困難です。</span><span class="sxs-lookup"><span data-stu-id="d69e5-108">The data is returned in terms of bytes, however, which makes it difficult to read:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk
```

```Output
DeviceID DriveType ProviderName VolumeName Size          FreeSpace
-------- --------- ------------ ---------- ----          ---------
C:       3                      Local Disk 203912880128  50665070592
```

<span data-ttu-id="d69e5-109">**FreeSpace** の値を 1 MB で割ると、メガバイト単位に変換できます。</span><span class="sxs-lookup"><span data-stu-id="d69e5-109">We can convert the **FreeSpace** value to megabytes by dividing each value by 1MB.</span></span> <span data-ttu-id="d69e5-110">`ForEach-Object` のスクリプト ブロックでこのことを実行できます。次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d69e5-110">You can do that in a `ForEach-Object` script block by typing:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  ForEach-Object -Process {($_.FreeSpace)/1MB}
```

```Output
48318.01171875
```

<span data-ttu-id="d69e5-111">残念ながら、出力はラベルとは関連付けられていないデータになります。</span><span class="sxs-lookup"><span data-stu-id="d69e5-111">Unfortunately, the output is now data with no associated label.</span></span> <span data-ttu-id="d69e5-112">この例のように、WMI プロパティは読み取り専用なので、**FreeSpace** を直接変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="d69e5-112">Because WMI properties such as this are read-only, you cannot directly convert **FreeSpace**.</span></span> <span data-ttu-id="d69e5-113">次のように入力するとします。</span><span class="sxs-lookup"><span data-stu-id="d69e5-113">If you type this:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1MB}
```

<span data-ttu-id="d69e5-114">次のようなエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d69e5-114">You get an error message:</span></span>

```Output
"FreeSpace" is a ReadOnly property.
At line:2 char:28
+   ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1MB}
+                            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : NotSpecified: (:) [], SetValueException
+ FullyQualifiedErrorId : ReadOnlyCIMProperty
```

<span data-ttu-id="d69e5-115">高度な技法をいくつか使用してデータを再編成できますが、よりシンプルな方法は、`Select-Object` を使用して新しいオブジェクトを作成することです。</span><span class="sxs-lookup"><span data-stu-id="d69e5-115">You could reorganize the data by using some advanced techniques, but a simpler approach is to create a new object, by using `Select-Object`.</span></span>
