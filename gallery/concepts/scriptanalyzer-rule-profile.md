---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: ギャラリーの ScriptAnalyzer 規則プロファイル
ms.openlocfilehash: 54100f7a530cbc769e4a0e2dbff18dbc5de88fa6
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="scriptanalyzer-rule-profile-for-gallery"></a><span data-ttu-id="077c6-103">ギャラリーの ScriptAnalyzer 規則プロファイル</span><span class="sxs-lookup"><span data-stu-id="077c6-103">ScriptAnalyzer rule profile for Gallery</span></span>

<span data-ttu-id="077c6-104">PowerShell ギャラリーに公開されるアイテムの品質を確保するために、[PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) 規則を実行し、送信されたスクリプトに違反がないか確認します。</span><span class="sxs-lookup"><span data-stu-id="077c6-104">To ensure the quality of items published to PowerShell Gallery, we run [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) rules to determine if there are any violations in the scripts submitted.</span></span>

<span data-ttu-id="077c6-105">ScriptAnalyzer [GitHub ページ](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1)で実行されているルールの一覧を参照できます。</span><span class="sxs-lookup"><span data-stu-id="077c6-105">You can find the list of rules we are running on ScriptAnalyzer [GitHub page](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1).</span></span>
<span data-ttu-id="077c6-106">実行されている規則について懸念がある場合は、PowerShell ギャラリー管理者に問い合わせるか、ScriptAnalzyer の問題が未解決であるという設定をしてください。</span><span class="sxs-lookup"><span data-stu-id="077c6-106">If you have any concerns regarding the rules we are running, please contact PowerShell Gallery Administrators, or open an issue for ScriptAnalzyer.</span></span>

<span data-ttu-id="077c6-107">今後リリースされるギャラリーでは、ScriptAnalyzer の結果が、個別のアイテムのページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="077c6-107">ScriptAnalyzer results will be displayed on each individual item page in Gallery in the coming release.</span></span> <span data-ttu-id="077c6-108">アイテムの所有者が、公開されたアイテム内に重大なエラーがないことを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="077c6-108">We encourage item owners to check their items to make sure there are no severe errors in published items.</span></span>
