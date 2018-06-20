---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 1595a3e817fd711c35128f06927fd57df7a63fb8
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34218248"
---
# <a name="authoring-improvements-using-powershell-ise"></a><span data-ttu-id="07096-102">PowerShell ISE を使ったオーサリングの強化</span><span class="sxs-lookup"><span data-stu-id="07096-102">Authoring Improvements using PowerShell ISE</span></span>

<span data-ttu-id="07096-103">Windows PowerShell ISE での DSC 構成のオーサリングが、はるかに簡単になりました。強化された点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="07096-103">Authoring DSC configurations in Windows PowerShell ISE is much easier, thanks to the following improvements:</span></span>

- <span data-ttu-id="07096-104">**構成**ブロック内や**ノード** ブロック内の空白行に **Ctrl+Space** を入力して、DSC リソースをすべて一覧表示する。</span><span class="sxs-lookup"><span data-stu-id="07096-104">List all DSC resources within a **configuration** block or **node** block by entering **Ctrl+Space** on a blank line within it.</span></span>
- <span data-ttu-id="07096-105">**列挙**型のリソース プロパティにおけるオート コンプリート。</span><span class="sxs-lookup"><span data-stu-id="07096-105">Automatic completion on resource properties that are of the **enumeration** type.</span></span>
- <span data-ttu-id="07096-106">構成内の他のリソース インスタンスに応じた、DSC リソースの **DependsOn** プロパティにおけるオート コンプリート。</span><span class="sxs-lookup"><span data-stu-id="07096-106">Automatic completion on the **DependsOn** property of DSC resources, based on other resource instances in the configuration.</span></span>
- <span data-ttu-id="07096-107">リソース プロパティ値のタブ補完の強化。</span><span class="sxs-lookup"><span data-stu-id="07096-107">Better tab completion of resource property values.</span></span>

<span data-ttu-id="07096-108">**注:** Ctrl+Space を使ってオプションを一覧表示するには、リソース プロパティ値に空の文字列が必要です。</span><span class="sxs-lookup"><span data-stu-id="07096-108">**Note:** You must have an empty string for resource property values before you can use Ctrl+Space to list the options.</span></span> <span data-ttu-id="07096-109">**タブ**を押して、オプションを順番に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="07096-109">Pressing **Tab** cycles through options.</span></span>
