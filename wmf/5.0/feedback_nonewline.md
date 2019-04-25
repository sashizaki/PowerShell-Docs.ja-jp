---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: e01f6ceea361f5a9b3de645346d0652986b6267d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057232"
---
# <a name="nonewline-parameter"></a><span data-ttu-id="710d0-102">NoNewLine パラメーター</span><span class="sxs-lookup"><span data-stu-id="710d0-102">NoNewLine parameter</span></span>
<span data-ttu-id="710d0-103">**Out-File**、**Add-Content**、および **Set-Content** に新しい **–NoNewline** スイッチが追加されました。これを指定すると、出力後の新しい行が省略されます。</span><span class="sxs-lookup"><span data-stu-id="710d0-103">**Out-File**, **Add-Content**, and **Set-Content** now have a new **–NoNewline** switch which simply omits a new line after the output.</span></span>
```powershell
PS C:\> "This is " | Out-File -FilePath Example.txt -NoNewline

PS C:\>; "a single " | Add-Content -Path Example.txt -NoNewline

PS C:\> "sentence." | Add-Content -Path Example.txt -NoNewline

PS C:\> Get-Content .\Example.txt

This is a single sentence.
```
<span data-ttu-id="710d0-104">**–NoNewline** を指定しないと、各フラグメントが別個の行に出力されます。</span><span class="sxs-lookup"><span data-stu-id="710d0-104">Without **–NoNewline** specified, each fragment would be on a separate line:</span></span>
```powershell
PS C:\> "This is " | Out-File -FilePath Example.txt

PS C:\> "a single " | Add-Content -Path Example.txt

PS C:\> "sentence." | Add-Content -Path Example.txt

PS C:\> Get-Content .\Example.txt

This is

a single

sentence.
```
