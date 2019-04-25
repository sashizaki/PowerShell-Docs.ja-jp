---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: e2c9233734a6ede04e8ec2bbad05950cbb31cbba
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057511"
---
# <a name="modules-support-for-declaring-version-ranges-1-etc"></a><span data-ttu-id="dd18c-102">バージョン範囲 (1. \* など) の宣言をサポートするモジュール</span><span class="sxs-lookup"><span data-stu-id="dd18c-102">Modules support for declaring version ranges (1.\*, etc)</span></span>
<span data-ttu-id="dd18c-103">**-MinimumVersion** と **-MaximumVersion** を組み合わせて使うと、特定の範囲のモジュールを取得/インポートできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="dd18c-103">Combined with **-MinimumVersion**, **-MaximumVersion** now allows user to get/import module within specific range.</span></span> <span data-ttu-id="dd18c-104">パラメーターは **.**\* もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dd18c-104">The parameter also support **.**\*.</span></span> <span data-ttu-id="dd18c-105">このパラメーターの動作を次の例で示します。</span><span class="sxs-lookup"><span data-stu-id="dd18c-105">The following example shows how it works:</span></span>

<span data-ttu-id="dd18c-106">**-MinimumVersion** と **-maximumversion** を組み合わせることにより、特定の範囲内でモジュールをインポートすることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="dd18c-106">Now, you can combine **-MinimumVersion** and **-MaximumVersion** to import module within specific range:</span></span>

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
