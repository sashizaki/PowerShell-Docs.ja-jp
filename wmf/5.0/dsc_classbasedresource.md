---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 4def20aa95f66ab23c9eee575150bc3db02541d8
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="class-based-dsc-resources"></a>クラスベースの DSC リソース

## <a name="defining-dsc-resources-with-classes"></a>クラスでの DSC リソースの定義

フィードバックに基づいて、クラスベースの DSC リソースのオーサリングを簡略化し、わかりやすくしました。
クラスベースの DSC リソースとコマンドレット DSC リソース プロバイダーの主な相違点は次のとおりです。

* スキーマの MOF ファイルは不要です。
* モジュール フォルダーの **DSCResource** サブフォルダーは不要です。
* PowerShell モジュールのファイルには、複数の DSC リソース クラスを含めることができます。

詳細については、「[PowerShell クラスを使用したカスタム DSC リソースの記述](https://msdn.microsoft.com/powershell/dsc/authoringresource)」を参照してください。