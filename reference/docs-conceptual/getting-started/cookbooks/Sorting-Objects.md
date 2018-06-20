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
# <a name="sorting-objects"></a>オブジェクトの並べ替え

**Sort-Object** コマンドレットを使用すると、表示データを見やすく整理できます。 **Sort-Object** では、並べ替え条件としてプロパティ名 (複数可) を指定すると、そのプロパティ値で並べ替えられたデータが返されます。

たとえば、Win32_SystemDriver のインスタンスを一覧表示する場合を考えてみます。 **State** で並べ替えた後、**Name** で並べ替えるには、次のように入力します。

```powershell
Get-WmiObject -Class Win32_SystemDriver | Sort-Object -Property State,Name | Format-Table -Property Name,State,Started,DisplayName -AutoSize -Wrap
```

多くの情報が表示されるものの、同じ状態の項目がグループ化されていることがわかります。

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

**Descending** パラメーターを指定して、オブジェクトを降順に並べ替えることもできます。 並べ替え順序が反転され、名前はアルファベットの最後から先に、数字は値の大きい方から先に表示されます。

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