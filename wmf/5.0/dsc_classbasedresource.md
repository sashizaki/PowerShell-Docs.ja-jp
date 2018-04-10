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
# <a name="class-based-dsc-resources"></a><span data-ttu-id="4e1e9-102">クラスベースの DSC リソース</span><span class="sxs-lookup"><span data-stu-id="4e1e9-102">Class-based DSC Resources</span></span>

## <a name="defining-dsc-resources-with-classes"></a><span data-ttu-id="4e1e9-103">クラスでの DSC リソースの定義</span><span class="sxs-lookup"><span data-stu-id="4e1e9-103">Defining DSC resources with classes</span></span>

<span data-ttu-id="4e1e9-104">フィードバックに基づいて、クラスベースの DSC リソースのオーサリングを簡略化し、わかりやすくしました。</span><span class="sxs-lookup"><span data-stu-id="4e1e9-104">Based on feedback, we’ve made authoring class-based DSC resources simpler and easier to understand.</span></span>
<span data-ttu-id="4e1e9-105">クラスベースの DSC リソースとコマンドレット DSC リソース プロバイダーの主な相違点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4e1e9-105">The major differences between a class-based DSC resource and a cmdlet DSC resource provider are:</span></span>

* <span data-ttu-id="4e1e9-106">スキーマの MOF ファイルは不要です。</span><span class="sxs-lookup"><span data-stu-id="4e1e9-106">A MOF file for the schema is not required.</span></span>
* <span data-ttu-id="4e1e9-107">モジュール フォルダーの **DSCResource** サブフォルダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="4e1e9-107">A **DSCResource** subfolder in the module folder is not required.</span></span>
* <span data-ttu-id="4e1e9-108">PowerShell モジュールのファイルには、複数の DSC リソース クラスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4e1e9-108">A PowerShell module file can contain multiple DSC resource classes.</span></span>

<span data-ttu-id="4e1e9-109">詳細については、「[PowerShell クラスを使用したカスタム DSC リソースの記述](https://msdn.microsoft.com/powershell/dsc/authoringresource)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e1e9-109">For more information, see [Writing a custom DSC resource with PowerShell classes](https://msdn.microsoft.com/powershell/dsc/authoringresource).</span></span>