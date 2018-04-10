---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: psgallery_scriptanalyzer_rule_profile
ms.openlocfilehash: ff575ab56f07312658d111bccd7793b64ac071ea
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="scriptanazlyer-rule-profile-for-gallery"></a><span data-ttu-id="94ab9-103">ギャラリーの ScriptAnazlyer 規則プロファイル</span><span class="sxs-lookup"><span data-stu-id="94ab9-103">ScriptAnazlyer Rule Profile for Gallery</span></span>
<span data-ttu-id="94ab9-104">PowerShell ギャラリーに公開されるアイテムの品質を確保するために、[PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) 規則を実行し、送信されたスクリプトに違反がないか確認します。</span><span class="sxs-lookup"><span data-stu-id="94ab9-104">To ensure the quality of items published to PowerShell Gallery, we run [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) rules to determine if there are any violations in the scripts submitted.</span></span>

<span data-ttu-id="94ab9-105">ScriptAnalyzer [GitHub ページ](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1)で実行されているルールの一覧を参照できます。</span><span class="sxs-lookup"><span data-stu-id="94ab9-105">You can find the list of rules we are running on ScriptAnalyzer [GitHub page](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1).</span></span>
<span data-ttu-id="94ab9-106">実行されている規則について懸念がある場合は、PowerShell ギャラリー管理者に問い合わせるか、ScriptAnalzyer の問題が未解決であるという設定をしてください。</span><span class="sxs-lookup"><span data-stu-id="94ab9-106">If you have any concerns regarding the rules we are running, please contact PowerShell Gallery Administrators, or open an issue for ScriptAnalzyer.</span></span>

<span data-ttu-id="94ab9-107">今後リリースされるギャラリーでは、ScriptAnalyzer の結果が、個別のアイテムのページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="94ab9-107">ScriptAnalyzer results will be displayed on each individual item page in Gallery in the coming release.</span></span> <span data-ttu-id="94ab9-108">アイテムの所有者が、公開されたアイテム内に重大なエラーがないことを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="94ab9-108">We encourage item owners to check their items to make sure there are no severe errors in published items.</span></span>