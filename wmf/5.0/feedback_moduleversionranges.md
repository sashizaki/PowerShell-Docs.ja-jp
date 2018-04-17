---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 89e908969641afd9ad9541dcfedcc8eb6315d07c
ms.sourcegitcommit: ece1794c94be4880a2af5a2605ed4721593643b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="modules-support-for-declaring-version-ranges-1-etc"></a><span data-ttu-id="c5b90-102">バージョン範囲 (1. \* など) の宣言をサポートするモジュール</span><span class="sxs-lookup"><span data-stu-id="c5b90-102">Modules support for declaring version ranges (1.\*, etc)</span></span>
<span data-ttu-id="c5b90-103">**-MinimumVersion** と **-MaximumVersion** を組み合わせて使うと、特定の範囲のモジュールを取得/インポートできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c5b90-103">Combined with **-MinimumVersion**, **-MaximumVersion** now allows user to get/import module within specific range.</span></span> <span data-ttu-id="c5b90-104">パラメーターをサポートしても**.**\*.</span><span class="sxs-lookup"><span data-stu-id="c5b90-104">The parameter also support **.**\*.</span></span> <span data-ttu-id="c5b90-105">このパラメーターの動作を次の例で示します。</span><span class="sxs-lookup"><span data-stu-id="c5b90-105">The following example shows how it works:</span></span>

<span data-ttu-id="c5b90-106">組み合わせることができます、 **- MinimumVersion**と**-maximumversion**特定範囲のモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="c5b90-106">Now, you can combine **-MinimumVersion** and **-MaximumVersion** to import module within specific range:</span></span>

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
