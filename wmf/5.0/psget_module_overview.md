---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 2c7e718bc518b332cb4303ef73b1bf5c924ca471
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="powershell-module-discovery-install-and-inventory-with-powershellget"></a>PowerShellGet による PowerShell モジュールの検出、インストール、およびインベントリ
 
このリリースの WMF には PowerShellGet が含まれています。
-   Find-Module では、-Tag パラメーターを使用してモジュールのメタデータをフィルター処理できます。
-   Find-Module では、-Filter パラメーターを使用してリポジトリ固有の検索言語をフィルター処理できます。
-   Find-Module では、-Command、-DscResource、および -Includes パラメーターを使用してモジュールのコンテンツに基づいてフィルター処理できます。
-   Find-DscResource では、リポジトリ内の個々の DSC リソースを検出できます。
-   NuGet によるファイル共有からのインストールおよびファイル共有への発行のサポート

## <a name="example-commands"></a>コマンド例
```powershell
\# Find all modules with tags Azure or DSC
Find-Module -Tag Azure, DSC

\# Find modules with a specific DscResource
Find-Module -DscResource xFirewall

\#Find modules with specific commands
Find-Module -Command Get-ScriptAnalyzerRule, Invoke-ScriptAnalyzer

\# Find all modules with Dsc resources
Find-Module -Includes DscResource

\# Find all modules with cmdlets
Find-Module -Includes Cmdlet

\# Find all modules with functions
Find-Module -Includes Function

\# Find all DSC resources
Find-DscResource

\# Find all DSC resources contained within a specific module
Find-DscResource -ModuleName xNetworking

\# Find all DSC resources in modules with DSCResourceKit or DesiredStateConfiguration
Find-DscResource -Tag DesiredStateConfiguration, DSCResourceKit

\# Find modules using -Filter parameter
\# Specified filter value is searched in Name and Description properties
Find-Module -Filter Cookbook -Repository PSGallery
Find-Module -Filter RBAC -Repository PSGallery
```

## <a name="new-features-in-powershellget"></a>PowerShellGet の新機能
-   Windows PowerShell 5.0 以降の Side-by-Side バージョン サポート
-   モジュールの依存関係のインストール サポート
-   次の 3 つの新しいコマンドレット
    -   Get-InstalledModule
    -   Uninstall-Module
    -   Save-Module
    
