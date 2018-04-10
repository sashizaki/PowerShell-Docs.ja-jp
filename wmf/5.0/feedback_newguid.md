---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 91c115c7f0553cd5edf7fecf04e6a5c71c0a1aa2
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="new-guid"></a><span data-ttu-id="f3f43-102">New-Guid</span><span class="sxs-lookup"><span data-stu-id="f3f43-102">New-Guid</span></span>
<span data-ttu-id="f3f43-103">スクリプトを記述しているときには (または、おそらく DSC リソースを記述しているときにも)、多くの場合、一意の識別子が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="f3f43-103">Often script (or perhaps writing a DSC resource), you have the need for a unique identifier.</span></span> <span data-ttu-id="f3f43-104">GUID はこの用途に適しており、.NET Framework の Guid クラスを呼び出せば、簡単に生成できます。しかし、これを実行するコマンドレットがあれば、.NET Framework クラスをまだ使い慣れていないエンド ユーザーに使ってもらえます。</span><span class="sxs-lookup"><span data-stu-id="f3f43-104">GUIDs work well, and it is easy to call the .NET Framework Guid class to generate one, but having a cmdlet makes this more discoverable for end users who are not already familiar with the .NET Framework class:</span></span>

<span data-ttu-id="f3f43-105">PS C:\\&gt; New-Guid</span><span class="sxs-lookup"><span data-stu-id="f3f43-105">PS C:\\&gt; New-Guid</span></span>

<span data-ttu-id="f3f43-106">GUID</span><span class="sxs-lookup"><span data-stu-id="f3f43-106">Guid</span></span>

----

<span data-ttu-id="f3f43-107">e19d6ea5-3cc2-4db9-8095-0cdaed5a703d</span><span class="sxs-lookup"><span data-stu-id="f3f43-107">e19d6ea5-3cc2-4db9-8095-0cdaed5a703d</span></span>