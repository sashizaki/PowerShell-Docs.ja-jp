---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 42f323590609319388e9a0a2c7c305dfa80c2d49
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34221852"
---
# <a name="class-based-dsc-resources"></a>クラスベースの DSC リソース

## <a name="defining-dsc-resources-with-classes"></a>クラスでの DSC リソースの定義

フィードバックに基づいて、クラスベースの DSC リソースのオーサリングを簡略化し、わかりやすくしました。
クラスベースの DSC リソースとコマンドレット DSC リソース プロバイダーの主な相違点は次のとおりです。

* スキーマの MOF ファイルは不要です。
* モジュール フォルダーの **DSCResource** サブフォルダーは不要です。
* PowerShell モジュールのファイルには、複数の DSC リソース クラスを含めることができます。

詳細については、「[PowerShell クラスを使用したカスタム DSC リソースの記述](https://msdn.microsoft.com/powershell/dsc/authoringresource)」を参照してください。
