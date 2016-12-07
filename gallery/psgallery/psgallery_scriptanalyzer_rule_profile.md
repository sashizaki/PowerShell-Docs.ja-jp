---
description: 
manager: carolz
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "powershell,コマンドレット,ギャラリー"
ms.date: 2016-10-14
contributor: manikb
title: psgallery_scriptanalyzer_rule_profile
ms.technology: powershell
ms.openlocfilehash: 3274b66203044c0ed9fc1135cea7472428eb753e
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
translationtype: HT
---
# <a name="scriptanazlyer-rule-profile-for-gallery"></a>ギャラリーの ScriptAnazlyer 規則プロファイル
PowerShell ギャラリーに公開されるアイテムの品質を確保するために、[PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) 規則を実行し、送信されたスクリプトに違反がないか確認します。

ScriptAnalyzer [GitHub ページ](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1)で実行されているルールの一覧を参照できます。
実行されている規則について懸念がある場合は、PowerShell ギャラリー管理者に問い合わせるか、ScriptAnalzyer の問題が未解決であるという設定をしてください。

今後リリースされるギャラリーでは、ScriptAnalyzer の結果が、個別のアイテムのページに表示されます。 アイテムの所有者が、公開されたアイテム内に重大なエラーがないことを確認することをお勧めします。

