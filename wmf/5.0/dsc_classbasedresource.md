---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: d40e5475c4132d6377c9a4559262a41b4842180a
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="class-based-dsc-resources" class="xliff"></a>

# クラスベースの DSC リソース

<a id="defining-dsc-resources-with-classes" class="xliff"></a>

## クラスでの DSC リソースの定義

フィードバックに基づいて、クラスベースの DSC リソースのオーサリングを簡略化し、わかりやすくしました。 クラスベースの DSC リソースとコマンドレット DSC リソース プロバイダーの主な相違点は次のとおりです。

* スキーマの MOF ファイルは不要です。
* モジュール フォルダーの **DSCResource** サブフォルダーは不要です。
* PowerShell モジュールのファイルには、複数の DSC リソース クラスを含めることができます。

詳細については、「[PowerShell クラスを使用したカスタム DSC リソースの記述](https://msdn.microsoft.com/powershell/dsc/authoringresource)」を参照してください。

