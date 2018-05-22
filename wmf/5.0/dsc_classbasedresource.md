---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 42f323590609319388e9a0a2c7c305dfa80c2d49
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="class-based-dsc-resources"></a><span data-ttu-id="96419-102">クラスベースの DSC リソース</span><span class="sxs-lookup"><span data-stu-id="96419-102">Class-based DSC Resources</span></span>

## <a name="defining-dsc-resources-with-classes"></a><span data-ttu-id="96419-103">クラスでの DSC リソースの定義</span><span class="sxs-lookup"><span data-stu-id="96419-103">Defining DSC resources with classes</span></span>

<span data-ttu-id="96419-104">フィードバックに基づいて、クラスベースの DSC リソースのオーサリングを簡略化し、わかりやすくしました。</span><span class="sxs-lookup"><span data-stu-id="96419-104">Based on feedback, we’ve made authoring class-based DSC resources simpler and easier to understand.</span></span>
<span data-ttu-id="96419-105">クラスベースの DSC リソースとコマンドレット DSC リソース プロバイダーの主な相違点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="96419-105">The major differences between a class-based DSC resource and a cmdlet DSC resource provider are:</span></span>

* <span data-ttu-id="96419-106">スキーマの MOF ファイルは不要です。</span><span class="sxs-lookup"><span data-stu-id="96419-106">A MOF file for the schema is not required.</span></span>
* <span data-ttu-id="96419-107">モジュール フォルダーの **DSCResource** サブフォルダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="96419-107">A **DSCResource** subfolder in the module folder is not required.</span></span>
* <span data-ttu-id="96419-108">PowerShell モジュールのファイルには、複数の DSC リソース クラスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="96419-108">A PowerShell module file can contain multiple DSC resource classes.</span></span>

<span data-ttu-id="96419-109">詳細については、「[PowerShell クラスを使用したカスタム DSC リソースの記述](https://msdn.microsoft.com/powershell/dsc/authoringresource)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96419-109">For more information, see [Writing a custom DSC resource with PowerShell classes](https://msdn.microsoft.com/powershell/dsc/authoringresource).</span></span>
