---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: ギャラリーの ScriptAnalyzer 規則プロファイル
ms.openlocfilehash: 939f01dece56b283dbe6e03c888f42ff866707af
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71328473"
---
# <a name="scriptanalyzer-rule-profile-for-gallery"></a><span data-ttu-id="fd94d-103">ギャラリーの ScriptAnalyzer 規則プロファイル</span><span class="sxs-lookup"><span data-stu-id="fd94d-103">ScriptAnalyzer rule profile for Gallery</span></span>

<span data-ttu-id="fd94d-104">PowerShell ギャラリーに公開されるパッケージの品質を確保するために、[PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) 規則を実行し、送信されたスクリプトに違反がないか確認します。</span><span class="sxs-lookup"><span data-stu-id="fd94d-104">To ensure the quality of packages published to PowerShell Gallery, we run [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) rules to determine if there are any violations in the scripts submitted.</span></span>

<span data-ttu-id="fd94d-105">ScriptAnalyzer [GitHub ページ](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1)で実行されているルールの一覧を参照できます。</span><span class="sxs-lookup"><span data-stu-id="fd94d-105">You can find the list of rules we are running on ScriptAnalyzer [GitHub page](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1).</span></span>
<span data-ttu-id="fd94d-106">実行されている規則について懸念がある場合は、PowerShell ギャラリー管理者に問い合わせるか、ScriptAnalyzer の問題が未解決であるという設定をしてください。</span><span class="sxs-lookup"><span data-stu-id="fd94d-106">If you have any concerns regarding the rules we are running, please contact PowerShell Gallery Administrators, or open an issue for ScriptAnalyzer.</span></span>

<span data-ttu-id="fd94d-107">今後リリースされるギャラリーでは、ScriptAnalyzer の結果が、個別のパッケージのページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd94d-107">ScriptAnalyzer results will be displayed on each individual package page in Gallery in the coming release.</span></span> <span data-ttu-id="fd94d-108">パッケージの所有者が、公開されたパッケージ内に重大なエラーがないことを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fd94d-108">We encourage package owners to check their packages to make sure there are no severe errors in published packages.</span></span>
