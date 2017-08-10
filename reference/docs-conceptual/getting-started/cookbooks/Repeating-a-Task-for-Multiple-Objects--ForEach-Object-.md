---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "複数のオブジェクトのタスクを繰り返す (ForEach-Object)"
ms.assetid: 6697a12d-2470-4ed6-b5bb-c35e5d525eb6
ms.openlocfilehash: 33ae2c76a512a651ba1b91d15d876608f0d43ccc
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="repeating-a-task-for-multiple-objects-foreach-object"></a><span data-ttu-id="7e3f6-103">複数のオブジェクトのタスクを繰り返す (ForEach-Object)</span><span class="sxs-lookup"><span data-stu-id="7e3f6-103">Repeating a Task for Multiple Objects (ForEach-Object)</span></span>
<span data-ttu-id="7e3f6-104">**ForEach-Object** コマンドレットは、現在のパイプライン オブジェクトのスクリプト ブロックと $_ 記述子を使用して、パイプライン内の各オブジェクトのコマンドを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7e3f6-104">The **ForEach-Object** cmdlet uses script blocks and the $_ descriptor for the current pipeline object to let you run a command on each object in the pipeline.</span></span> <span data-ttu-id="7e3f6-105">これは、いくつかの複雑なタスクを実行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="7e3f6-105">This can be used to perform some complicated tasks.</span></span>

<span data-ttu-id="7e3f6-106">これが有用な状況の 1 つは、データをさらに有効活用するよう操作する場合です。</span><span class="sxs-lookup"><span data-stu-id="7e3f6-106">One situation where this can be useful is manipulating data to make it more useful.</span></span> <span data-ttu-id="7e3f6-107">たとえば、WMI からの Win32_LogicalDisk クラスは、各ローカル ディスクの空き領域の情報を返すのに使用できます。</span><span class="sxs-lookup"><span data-stu-id="7e3f6-107">For example, the Win32_LogicalDisk class from WMI can be used to return free space information for each local disk.</span></span> <span data-ttu-id="7e3f6-108">データはバイト単位で返されますが、次のように、読み取るのは困難です。</span><span class="sxs-lookup"><span data-stu-id="7e3f6-108">The data is returned in terms of bytes, however, which makes it difficult to read:</span></span>

```
PS> Get-WmiObject -Class Win32_LogicalDisk

DeviceID     : C:
DriveType    : 3
ProviderName :
FreeSpace    : 50665070592
Size         : 203912880128
VolumeName   : Local Disk
```

<span data-ttu-id="7e3f6-109">FreeSpace の値を 1024 で 2 回割ると、メガバイト単位に変換できます。最初の除算の後、データはキロバイト単位になり、2 回目の除算の後、メガバイト単位になります。</span><span class="sxs-lookup"><span data-stu-id="7e3f6-109">We can convert the FreeSpace value to megabytes by dividing each value by 1024 twice; after the first division, the data is in kilobytes, and after the second division it is megabytes.</span></span> <span data-ttu-id="7e3f6-110">ForEach-Object のスクリプト ブロックでこのことを実行できます。次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7e3f6-110">You can do that in a ForEach-Object script block by typing:</span></span>

```
Get-WmiObject -Class Win32_LogicalDisk | ForEach-Object -Process {($_.FreeSpace)/1024.0/1024.0}
48318.01171875
```

<span data-ttu-id="7e3f6-111">残念ながら、出力はラベルとは関連付けられていないデータになります。</span><span class="sxs-lookup"><span data-stu-id="7e3f6-111">Unfortunately, the output is now data with no associated label.</span></span> <span data-ttu-id="7e3f6-112">この例のように、WMI プロパティは読み取り専用なので、FreeSpace を直接変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="7e3f6-112">Because WMI properties such as this are read-only, you cannot directly convert FreeSpace.</span></span> <span data-ttu-id="7e3f6-113">次のように入力するとします。</span><span class="sxs-lookup"><span data-stu-id="7e3f6-113">If you type this:</span></span>

```
Get-WmiObject -Class Win32_LogicalDisk | ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1024.0/1024.0}
```

<span data-ttu-id="7e3f6-114">次のようなエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e3f6-114">You get an error message:</span></span>

```
"FreeSpace" is a ReadOnly property.
At line:1 char:70
+ Get-WmiObject -Class Win32_LogicalDisk | ForEach-Object -Process {$_.F <<<< r
eeSpace = ($_.FreeSpace)/1024.0/1024.0}
```

<span data-ttu-id="7e3f6-115">高度な技法を幾つか使用してデータを再編成できますが、よりシンプルな方法は、**Select-Object** を使用して新しいオブジェクトを作成することです。</span><span class="sxs-lookup"><span data-stu-id="7e3f6-115">You could reorganize the data by using some advanced techniques, but a simpler approach is to create a new object, by using **Select-Object**.</span></span>

