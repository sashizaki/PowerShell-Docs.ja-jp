---
ms.date: 06/12/2017
contributor: manikb
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: 互換性のある PowerShell エディションが含まれるスクリプト
ms.openlocfilehash: fcfe670a0a9ee71427b4a8adaaf3d612411941f7
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50002413"
---
# <a name="script-with-compatible-powershell-editions"></a><span data-ttu-id="f46e3-103">互換性のある PowerShell エディションが含まれるスクリプト</span><span class="sxs-lookup"><span data-stu-id="f46e3-103">Script with compatible PowerShell editions</span></span>

<span data-ttu-id="f46e3-104">バージョン 5.1 から、PowerShell はさまざまな機能セットとプラットフォーム互換性を備える別のエディションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f46e3-104">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="f46e3-105">**デスクトップ エディション:** .NET Framework 上に構築されており、Server Core や Windows Desktop などの Windows の完全エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="f46e3-105">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>

- <span data-ttu-id="f46e3-106">**コア エディション:** .NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="f46e3-106">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

<span data-ttu-id="f46e3-107">PowerShell の実行中のエディションが $PSVersionTable の PSEdition プロパティに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f46e3-107">The running edition of PowerShell is shown in the PSEdition property of $PSVersionTable.</span></span>

```powershell
$PSVersionTable

Name                           Value
----                           -----
PSVersion                      5.1.14300.1000
PSEdition                      Desktop
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
CLRVersion                     4.0.30319.42000
BuildVersion                   10.0.14300.1000
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
```

<span data-ttu-id="f46e3-108">スクリプト作成者は、`#requires` ステートメントで PSEdition パラメーターを使用することにより、PowerShell の互換性のあるエディションで実行されていない場合に、スクリプトの実行を回避できます。</span><span class="sxs-lookup"><span data-stu-id="f46e3-108">Script authors can prevent a script from executing unless it is run on a compatible edition of PowerShell using the PSEdition parameter on a `#requires` statement.</span></span>

```powershell
Set-Content C:\script.ps1 -Value "#requires -PSEdition Core
Get-Process -Name PowerShell"
Get-Content C:\script.ps1
#requires -PSEdition Core
Get-Process -Name PowerShell

C:\script.ps1
C:\script.ps1 : The script 'script.ps1' cannot be run because it contained a "#requires" statement for PowerShell editions 'Core'. The edition of PowerShell that is required by the script does not match the currently running PowerShell Desktop edition.
At line:1 char:1
+ C:\script.ps1
+ ~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (script.ps1:String) [], RuntimeException
    + FullyQualifiedErrorId : ScriptRequiresUnmatchedPSEdition
```

<span data-ttu-id="f46e3-109">PowerShell Gallery ユーザーは、PowerShell の特定のエディションでサポートされているスクリプトの一覧を検索できます。</span><span class="sxs-lookup"><span data-stu-id="f46e3-109">PowerShell Gallery users can find the list of scripts supported on a specific PowerShell Edition.</span></span>
<span data-ttu-id="f46e3-110">PSEdition_Desktop および PSEdition_Core タグがないスクリプトは、PowerShell Desktop エディションで正常に動作するものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="f46e3-110">Scripts without PSEdition_Desktop and PSEdition_Core tags are considered to work fine on PowerShell Desktop edition.</span></span>

```powershell
# Find scripts supported on PowerShell Desktop edition
Find-Script -Tag PSEdition_Desktop

# Find scripts supported on PowerShell Core edition
Find-Script -Tag PSEdition_Core
```

## <a name="more-details"></a><span data-ttu-id="f46e3-111">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f46e3-111">More details</span></span>

- [<span data-ttu-id="f46e3-112">PSEditions が含まれるモジュール</span><span class="sxs-lookup"><span data-stu-id="f46e3-112">Modules with PSEditions</span></span>](module-psedition-support.md)
- [<span data-ttu-id="f46e3-113">PowerShellGallery での PSEditions のサポート</span><span class="sxs-lookup"><span data-stu-id="f46e3-113">PSEditions support on PowerShellGallery</span></span>](../how-to/finding-packages/searching-by-psedition.md)
