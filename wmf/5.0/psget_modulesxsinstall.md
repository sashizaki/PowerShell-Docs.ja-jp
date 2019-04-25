---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 0a481fb9d4f2aab89bc448c71b01f1d541cf24bc
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085084"
---
# <a name="side-by-side-version-support-on-powershell-50-or-newer"></a>PowerShell 5.0 以降の Side-by-Side バージョン サポート

Windows PowerShell 5.0 以降で実行される Install-Module、Update-Module、および Publish-Module コマンドレットには、Side-by-Side (SxS) モジュール バージョン サポートがあります。
また、発行するバージョンを指定する -RequiredVersion パラメーターを Publish-Module コマンドレットに追加しました。 Path パラメーターは、モジュールのベース パスと、バージョン フォルダーをサポートするようになりました。

**Install-Module の例:**
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
