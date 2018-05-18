---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: f491e30859cbe6cbaa58f94389382ff231c52956
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="modules-support-for-declaring-version-ranges-1-etc"></a><span data-ttu-id="a3efb-102">バージョン範囲 (1. \* など) の宣言をサポートするモジュール</span><span class="sxs-lookup"><span data-stu-id="a3efb-102">Modules support for declaring version ranges (1.\*, etc)</span></span>
<span data-ttu-id="a3efb-103">**-MinimumVersion** と **-MaximumVersion** を組み合わせて使うと、特定の範囲のモジュールを取得/インポートできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a3efb-103">Combined with **-MinimumVersion**, **-MaximumVersion** now allows user to get/import module within specific range.</span></span> <span data-ttu-id="a3efb-104">パラメーターは **.**\* もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a3efb-104">The parameter also support **.**\*.</span></span> <span data-ttu-id="a3efb-105">このパラメーターの動作を次の例で示します。</span><span class="sxs-lookup"><span data-stu-id="a3efb-105">The following example shows how it works:</span></span>

<span data-ttu-id="a3efb-106">**-MinimumVersion** と **-maximumversion** を組み合わせることにより、特定の範囲内でモジュールをインポートすることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a3efb-106">Now, you can combine **-MinimumVersion** and **-MaximumVersion** to import module within specific range:</span></span>

```powershell
PS C:\> Import-Module psreadline -Verbose -MinimumVersion 1.0 -MaximumVersion 1.2.*

VERBOSE: Loading module from path 'C:\Program Files\WindowsPowerShell\Modules\psreadline\1.1\psreadline.psd1'.
VERBOSE: Importing cmdlet 'Get-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Get-PSReadlineOption'.
VERBOSE: Importing cmdlet 'Remove-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Set-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Set-PSReadlineOption'.
VERBOSE: Importing function 'PSConsoleHostReadline'.
```
