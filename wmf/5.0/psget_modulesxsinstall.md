---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: d4168640f67cb1dd44e91d1867e87fd7a6b7f549
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34218352"
---
# <a name="side-by-side-version-support-on-powershell-50-or-newer"></a><span data-ttu-id="f8900-102">PowerShell 5.0 以降の Side-by-Side バージョン サポート</span><span class="sxs-lookup"><span data-stu-id="f8900-102">Side-by-Side Version Support on PowerShell 5.0 or newer</span></span>

<span data-ttu-id="f8900-103">Windows PowerShell 5.0 以降で実行される Install-Module、Update-Module、および Publish-Module コマンドレットには、Side-by-Side (SxS) モジュール バージョン サポートがあります。</span><span class="sxs-lookup"><span data-stu-id="f8900-103">There is now side-by-side (SxS) module version support in Install-Module, Update-Module, and Publish-Module cmdlets that run in Windows PowerShell 5.0 or newer.</span></span>
<span data-ttu-id="f8900-104">また、発行するバージョンを指定する -RequiredVersion パラメーターを Publish-Module コマンドレットに追加しました。</span><span class="sxs-lookup"><span data-stu-id="f8900-104">Also, we have added a -RequiredVersion parameter to the Publish-Module cmdlet to specify the version to be published.</span></span> <span data-ttu-id="f8900-105">Path パラメーターは、モジュールのベース パスと、バージョン フォルダーをサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="f8900-105">The Path parameter now supports the module base path with the version folder.</span></span>

<span data-ttu-id="f8900-106">**Install-Module の例:**</span><span class="sxs-lookup"><span data-stu-id="f8900-106">**Install-Module examples:**</span></span>
```powershell
Install-Module -Name PSScriptAnalyzer -RequiredVersion 1.1.0 -Repository PSGallery
Get-Module -ListAvailable -Name PSScriptAnalyzer | Format-List Name,Version,ModuleBase

Name : PSScriptAnalyzer
Version : 1.1.0
ModuleBase : C:\Program Files\WindowsPowerShell\Modules\PSScriptAnalyzer\1.1.0

Install-Module -Name PSScriptAnalyzer -RequiredVersion 1.1.1 -Repository PSGallery
Get-Module -ListAvailable -Name PSScriptAnalyzer | Format-List Name,Version,ModuleBase

Name       : PSScriptAnalyzer
Version    : 1.1.1
ModuleBase : C:\Program Files\WindowsPowerShell\Modules\PSScriptAnalyzer\1.1.1
Name       : PSScriptAnalyzer
Version    : 1.1.0
ModuleBase : C:\Program Files\WindowsPowerShell\Modules\PSScriptAnalyzer\1.1.0

Get-InstalledModule -Name PSScriptAnalyzer -AllVersions

Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.1.0      PSScriptAnalyzer                    Module     PSGallery            PSScriptAnalyzer provides script analysis...
1.1.1      PSScriptAnalyzer                    Module     PSGallery            PSScriptAnalyzer provides script analysis...
```
