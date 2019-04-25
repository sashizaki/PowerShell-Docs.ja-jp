---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: a1e90a0b96f74decb55343292b97befaf1a85f8a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058116"
---
# <a name="class-based-dsc-resources"></a>クラスベースの DSC リソース

## <a name="defining-dsc-resources-with-classes"></a>クラスでの DSC リソースの定義

フィードバックに基づいて、クラスベースの DSC リソースのオーサリングを簡略化し、わかりやすくしました。
クラスベースの DSC リソースとコマンドレット DSC リソース プロバイダーの主な相違点は次のとおりです。

* スキーマの MOF ファイルは不要です。
* モジュール フォルダーの **DSCResource** サブフォルダーは不要です。
* PowerShell モジュールのファイルには、複数の DSC リソース クラスを含めることができます。

詳細については、「[PowerShell クラスを使用したカスタム DSC リソースの記述](https://msdn.microsoft.com/powershell/dsc/authoringresource)」を参照してください。
