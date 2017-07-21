---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 8c6a7d55e40f64bde6c2a2074ca3adb9cd210322
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="nonewline-parameter"></a><span data-ttu-id="79e08-102">NoNewLine パラメーター</span><span class="sxs-lookup"><span data-stu-id="79e08-102">NoNewLine parameter</span></span>
<span data-ttu-id="79e08-103">**Out-File**、**Add-Content**、および **Set-Content** に新しい **–NoNewline** スイッチが追加されました。これを指定すると、出力後の新しい行が省略されます。</span><span class="sxs-lookup"><span data-stu-id="79e08-103">**Out-File**, **Add-Content**, and **Set-Content** now have a new **–NoNewline** switch which simply omits a new line after the output.</span></span>
```PowerShell
PS C:\> "This is " | Out-File -FilePath Example.txt -NoNewline

PS C:\>; "a single " | Add-Content -Path Example.txt -NoNewline

PS C:\> "sentence." | Add-Content -Path Example.txt -NoNewline

PS C:\> Get-Content .\Example.txt

This is a single sentence.
```
<span data-ttu-id="79e08-104">**–NoNewline** を指定しないと、各フラグメントが別個の行に出力されます。</span><span class="sxs-lookup"><span data-stu-id="79e08-104">Without **–NoNewline** specified, each fragment would be on a separate line:</span></span>
```PowerShell
PS C:\> "This is " | Out-File -FilePath Example.txt

PS C:\> "a single " | Add-Content -Path Example.txt

PS C:\> "sentence." | Add-Content -Path Example.txt

PS C:\> Get-Content .\Example.txt

This is

a single

sentence.
```

