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
ms.locfileid: "34225744"
---
# <a name="scriptanalyzer-rule-profile-for-gallery"></a>ギャラリーの ScriptAnalyzer 規則プロファイル

PowerShell ギャラリーに公開されるアイテムの品質を確保するために、[PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) 規則を実行し、送信されたスクリプトに違反がないか確認します。

ScriptAnalyzer [GitHub ページ](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1)で実行されているルールの一覧を参照できます。
実行されている規則について懸念がある場合は、PowerShell ギャラリー管理者に問い合わせるか、ScriptAnalzyer の問題が未解決であるという設定をしてください。

今後リリースされるギャラリーでは、ScriptAnalyzer の結果が、個別のアイテムのページに表示されます。 アイテムの所有者が、公開されたアイテム内に重大なエラーがないことを確認することをお勧めします。
