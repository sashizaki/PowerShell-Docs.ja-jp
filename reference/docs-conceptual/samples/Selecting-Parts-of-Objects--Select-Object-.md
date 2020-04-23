---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: オブジェクトの一部を選択する (Select-Object)
ms.openlocfilehash: 06b92c7c4c5098c707a7d9f9d9a96e6b6a897f80
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "75737170"
---
# <a name="selecting-parts-of-objects-select-object"></a><span data-ttu-id="deb99-103">オブジェクトの一部を選択する (Select-Object)</span><span class="sxs-lookup"><span data-stu-id="deb99-103">Selecting Parts of Objects (Select-Object)</span></span>

<span data-ttu-id="deb99-104">`Select-Object` コマンドレットを使用して、PowerShell のオブジェクトを新規作成、またはカスタマイズできます。それらのオブジェクトには、作成時に使用する元のオブジェクトから選択したプロパティを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="deb99-104">You can use the `Select-Object` cmdlet to create new, custom PowerShell objects that contain properties selected from the objects you use to create them.</span></span> <span data-ttu-id="deb99-105">次のコマンドを入力して、**Win32_LogicalDisk** WMI クラスの **Name** および **FreeSpace** プロパティのみを含む、新規オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="deb99-105">Type the following command to create a new object that includes only the **Name** and **FreeSpace** properties of the **Win32_LogicalDisk** WMI class:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace
```

```Output
Name      FreeSpace
----      ---------
C:      50664845312
```

<span data-ttu-id="deb99-106">`Select-Object` では、計算されるプロパティを作成できます。</span><span class="sxs-lookup"><span data-stu-id="deb99-106">With `Select-Object` you can create calculated properties.</span></span> <span data-ttu-id="deb99-107">したがって、**FreeSpace** をバイト単位ではなくギガバイト単位で表示できます。</span><span class="sxs-lookup"><span data-stu-id="deb99-107">So you can display **FreeSpace** in gigabytes rather than bytes.</span></span>

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
