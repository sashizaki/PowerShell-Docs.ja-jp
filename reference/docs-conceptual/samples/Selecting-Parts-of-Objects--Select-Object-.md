---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: オブジェクトの一部を選択する (Select-Object)
description: '`Select-Object` コマンドレットを使用して、パイプラインのオブジェクトから選択したプロパティが含まれるカスタム PowerShell オブジェクトを新しく作成することができます。'
ms.openlocfilehash: 92635ac54ea1469739bcb228c5e9a0a8dbfc648b
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501033"
---
# <a name="selecting-parts-of-objects-select-object"></a>オブジェクトの一部を選択する (Select-Object)

`Select-Object` コマンドレットを使用して、PowerShell のオブジェクトを新規作成、またはカスタマイズできます。それらのオブジェクトには、作成時に使用する元のオブジェクトから選択したプロパティを含めることができます。 次のコマンドを入力して、 **Win32_LogicalDisk** WMI クラスの **Name** および **FreeSpace** プロパティのみを含む、新規オブジェクトを作成します。

```powershell
Get-CimInstance -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace
```

```Output
Name      FreeSpace
----      ---------
C:      50664845312
```

`Select-Object` では、計算されるプロパティを作成できます。 したがって、 **FreeSpace** をバイト単位ではなくギガバイト単位で表示できます。

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
