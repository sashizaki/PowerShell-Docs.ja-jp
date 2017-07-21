---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 69188738333a853a16e6ea68689ecba5dc632225
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="side-by-side-version-support-on-powershell-50-or-newer"></a><span data-ttu-id="cd50c-102">PowerShell 5.0 以降の Side-by-Side バージョン サポート</span><span class="sxs-lookup"><span data-stu-id="cd50c-102">Side-by-Side Version Support on PowerShell 5.0 or newer</span></span>

<span data-ttu-id="cd50c-103">Windows PowerShell 5.0 以降で実行される Install-Module、Update-Module、および Publish-Module コマンドレットには、Side-by-Side (SxS) モジュール バージョン サポートがあります。</span><span class="sxs-lookup"><span data-stu-id="cd50c-103">There is now side-by-side (SxS) module version support in Install-Module, Update-Module, and Publish-Module cmdlets that run in Windows PowerShell 5.0 or newer.</span></span>
<span data-ttu-id="cd50c-104">また、発行するバージョンを指定する -RequiredVersion パラメーターを Publish-Module コマンドレットに追加しました。</span><span class="sxs-lookup"><span data-stu-id="cd50c-104">Also, we have added a -RequiredVersion parameter to the Publish-Module cmdlet to specify the version to be published.</span></span> <span data-ttu-id="cd50c-105">Path パラメーターは、モジュールのベース パスと、バージョン フォルダーをサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="cd50c-105">The Path parameter now supports the module base path with the version folder.</span></span>

<span data-ttu-id="cd50c-106">**Install-Module の例:**</span><span class="sxs-lookup"><span data-stu-id="cd50c-106">**Install-Module examples:**</span></span>
```powershell
PS C:\\windows\\system32&gt; Install-Module -Name PSScriptAnalyzer -RequiredVersion 1.1.0 -Repository PSGallery
PS C:\\windows\\system32&gt; Get-Module -ListAvailable -Name PSScriptAnalyzer | Format-List Name,Version,ModuleBase
Name : PSScriptAnalyzer
Version : 1.1.0
ModuleBase : C:\Program Files\WindowsPowerShell\Modules\PSScriptAnalyzer\1.1.0

PS C:\\windows\\system32&gt; Install-Module -Name PSScriptAnalyzer -RequiredVersion 1.1.1 -Repository PSGallery
PS C:\\windows\\system32&gt; Get-Module -ListAvailable -Name PSScriptAnalyzer | Format-List Name,Version,ModuleBase
Name       : PSScriptAnalyzer 
Version    : 1.1.1
ModuleBase : C:\Program Files\WindowsPowerShell\Modules\PSScriptAnalyzer\1.1.1
Name       : PSScriptAnalyzer
Version    : 1.1.0
ModuleBase : C:\Program Files\WindowsPowerShell\Modules\PSScriptAnalyzer\1.1.0

PS C:\\windows\\system32&gt; Get-InstalledModule -Name PSScriptAnalyzer -AllVersions
Version    Name                                Type       Repository           Description            
-------    ----                                ----       ----------           -----------            
1.1.0      PSScriptAnalyzer                    Module     PSGallery            PSScriptAnalyzer provides script analysis... 
1.1.1      PSScriptAnalyzer                    Module     PSGallery            PSScriptAnalyzer provides script analysis...
```

