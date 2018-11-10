---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: ギャラリーの ScriptAnalyzer 規則プロファイル
ms.openlocfilehash: d91a88981cc2f3269a1f8b6ee864f8333a2f097c
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50002498"
---
# <a name="scriptanalyzer-rule-profile-for-gallery"></a>ギャラリーの ScriptAnalyzer 規則プロファイル

PowerShell ギャラリーに公開されるパッケージの品質を確保するために、[PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) 規則を実行し、送信されたスクリプトに違反がないか確認します。

ScriptAnalyzer [GitHub ページ](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1)で実行されているルールの一覧を参照できます。
実行されている規則について懸念がある場合は、PowerShell ギャラリー管理者に問い合わせるか、ScriptAnalzyer の問題が未解決であるという設定をしてください。

今後リリースされるギャラリーでは、ScriptAnalyzer の結果が、個別のパッケージのページに表示されます。 パッケージの所有者が、公開されたパッケージ内に重大なエラーがないことを確認することをお勧めします。
