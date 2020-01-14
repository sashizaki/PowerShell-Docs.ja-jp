---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: オブジェクトの一部を選択する (Select-Object)
ms.openlocfilehash: 06b92c7c4c5098c707a7d9f9d9a96e6b6a897f80
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75737170"
---
# <a name="selecting-parts-of-objects-select-object"></a>オブジェクトの一部を選択する (Select-Object)

`Select-Object` コマンドレットを使用して、PowerShell のオブジェクトを新規作成、またはカスタマイズできます。それらのオブジェクトには、作成時に使用する元のオブジェクトから選択したプロパティを含めることができます。 次のコマンドを入力して、**Win32_LogicalDisk** WMI クラスの **Name** および **FreeSpace** プロパティのみを含む、新規オブジェクトを作成します。

```powershell
Get-CimInstance -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace
```

```Output
Name      FreeSpace
----      ---------
C:      50664845312
```

`Select-Object` では、計算されるプロパティを作成できます。 したがって、**FreeSpace** をバイト単位ではなくギガバイト単位で表示できます。

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  Select-Object -Property Name, @{
    label='FreeSpace'
    expression={($_.FreeSpace/1GB).ToString('F2')}
  }
```

```Output
Name    FreeSpace
----    ---------
C:      47.18
```
