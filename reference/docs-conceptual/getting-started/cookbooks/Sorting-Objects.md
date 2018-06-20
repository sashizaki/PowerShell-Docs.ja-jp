---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: オブジェクトの並べ替え
ms.assetid: 8530caa8-3ed4-4c56-aed7-1295dd9ba199
ms.openlocfilehash: 272d550a67b206f9924ebe143eca2f5906c0a304
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
ms.locfileid: "30949980"
---
# <a name="sorting-objects"></a><span data-ttu-id="68b67-103">オブジェクトの並べ替え</span><span class="sxs-lookup"><span data-stu-id="68b67-103">Sorting Objects</span></span>

<span data-ttu-id="68b67-104">**Sort-Object** コマンドレットを使用すると、表示データを見やすく整理できます。</span><span class="sxs-lookup"><span data-stu-id="68b67-104">We can organize displayed data to make it easier to scan by using the **Sort-Object** cmdlet.</span></span> <span data-ttu-id="68b67-105">**Sort-Object** では、並べ替え条件としてプロパティ名 (複数可) を指定すると、そのプロパティ値で並べ替えられたデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="68b67-105">**Sort-Object** takes the name of one or more properties to sort on, and returns data sorted by the values of those properties.</span></span>

<span data-ttu-id="68b67-106">たとえば、Win32_SystemDriver のインスタンスを一覧表示する場合を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="68b67-106">Consider the problem of listing Win32_SystemDriver instances.</span></span> <span data-ttu-id="68b67-107">**State** で並べ替えた後、**Name** で並べ替えるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="68b67-107">If we want to sort by **State** and then by **Name**, we can do it by typing:</span></span>

```powershell
Get-WmiObject -Class Win32_SystemDriver | Sort-Object -Property State,Name | Format-Table -Property Name,State,Started,DisplayName -AutoSize -Wrap
```

<span data-ttu-id="68b67-108">多くの情報が表示されるものの、同じ状態の項目がグループ化されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="68b67-108">Although this is a lengthy display, you can see items with the same state grouped together:</span></span>

```output
Name           State   Started DisplayName
----           -----   ------- -----------
ACPI           Running    True Microsoft ACPI Driver
AFD            Running    True AFD
AmdK7          Running    True AMD K7 Processor Driver
AsyncMac       Running    True RAS Asynchronous Media Driver
...
Abiosdsk       Stopped   False Abiosdsk
ACPIEC         Stopped   False ACPIEC
aec            Stopped   False Microsoft Kernel Acoustic Echo Canceller
...
```

<span data-ttu-id="68b67-109">**Descending** パラメーターを指定して、オブジェクトを降順に並べ替えることもできます。</span><span class="sxs-lookup"><span data-stu-id="68b67-109">You can also sort the objects in reverse order by specifying the **Descending** parameter.</span></span> <span data-ttu-id="68b67-110">並べ替え順序が反転され、名前はアルファベットの最後から先に、数字は値の大きい方から先に表示されます。</span><span class="sxs-lookup"><span data-stu-id="68b67-110">This reverses the sort order so that names are sorted in reverse alphabetical order and numbers are sorted by descending size.</span></span>

```
PS> Get-WmiObject -Class Win32_SystemDriver | Sort-Object -Property State,Name -Descending | Format-Table -Property Name,State,Started,DisplayName -AutoSize -Wrap

Name           State   Started DisplayName
----           -----   ------- -----------
WS2IFSL        Stopped   False Windows Socket 2.0 Non-IFS Service Provider Supp
                               ort Environment
wceusbsh       Stopped   False Windows CE USB Serial Host Driver...
...
wdmaud         Running    True Microsoft WINMM WDM Audio Compatibility Driver
Wanarp         Running    True Remote Access IP ARP Driver
...
```