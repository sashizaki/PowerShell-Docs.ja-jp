---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 555e01e88647b40717417360fb74bb6554a9c122
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="authoring-improvements-using-powershell-ise"></a><span data-ttu-id="18116-102">PowerShell ISE を使ったオーサリングの強化</span><span class="sxs-lookup"><span data-stu-id="18116-102">Authoring Improvements using PowerShell ISE</span></span>

<span data-ttu-id="18116-103">Windows PowerShell ISE での DSC 構成のオーサリングが、はるかに簡単になりました。強化された点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="18116-103">Authoring DSC configurations in Windows PowerShell ISE is much easier, thanks to the following improvements:</span></span>

- <span data-ttu-id="18116-104">**構成**ブロック内や**ノード** ブロック内の空白行に **Ctrl+Space** を入力して、DSC リソースをすべて一覧表示する。</span><span class="sxs-lookup"><span data-stu-id="18116-104">List all DSC resources within a **configuration** block or **node** block by entering **Ctrl+Space** on a blank line within it.</span></span>
- <span data-ttu-id="18116-105">**列挙**型のリソース プロパティにおけるオート コンプリート。</span><span class="sxs-lookup"><span data-stu-id="18116-105">Automatic completion on resource properties that are of the **enumeration** type.</span></span>
- <span data-ttu-id="18116-106">構成内の他のリソース インスタンスに応じた、DSC リソースの **DependsOn** プロパティにおけるオート コンプリート。</span><span class="sxs-lookup"><span data-stu-id="18116-106">Automatic completion on the **DependsOn** property of DSC resources, based on other resource instances in the configuration.</span></span>
- <span data-ttu-id="18116-107">リソース プロパティ値のタブ補完の強化。</span><span class="sxs-lookup"><span data-stu-id="18116-107">Better tab completion of resource property values.</span></span>

<span data-ttu-id="18116-108">**注:** Ctrl+Space を使ってオプションを一覧表示するには、リソース プロパティ値に空の文字列が必要です。</span><span class="sxs-lookup"><span data-stu-id="18116-108">**Note:** You must have an empty string for resource property values before you can use Ctrl+Space to list the options.</span></span> <span data-ttu-id="18116-109">**タブ**を押して、オプションを順番に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="18116-109">Pressing **Tab** cycles through options.</span></span>

