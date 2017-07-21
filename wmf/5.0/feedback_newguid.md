---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: bb2e7b99d14c790bdd3df2f5c729275b96a659fc
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="new-guid"></a><span data-ttu-id="83cc1-102">New-Guid</span><span class="sxs-lookup"><span data-stu-id="83cc1-102">New-Guid</span></span>
<span data-ttu-id="83cc1-103">スクリプトを記述しているときには (または、おそらく DSC リソースを記述しているときにも)、多くの場合、一意の識別子が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="83cc1-103">Often script (or perhaps writing a DSC resource), you have the need for a unique identifier.</span></span> <span data-ttu-id="83cc1-104">GUID はこの用途に適しており、.NET Framework の Guid クラスを呼び出せば、簡単に生成できます。しかし、これを実行するコマンドレットがあれば、.NET Framework クラスをまだ使い慣れていないエンド ユーザーに使ってもらえます。</span><span class="sxs-lookup"><span data-stu-id="83cc1-104">GUIDs work well, and it is easy to call the .NET Framework Guid class to generate one, but having a cmdlet makes this more discoverable for end users who are not already familiar with the .NET Framework class:</span></span>

<span data-ttu-id="83cc1-105">PS C:\\&gt; New-Guid</span><span class="sxs-lookup"><span data-stu-id="83cc1-105">PS C:\\&gt; New-Guid</span></span>

<span data-ttu-id="83cc1-106">GUID</span><span class="sxs-lookup"><span data-stu-id="83cc1-106">Guid</span></span>

----

<span data-ttu-id="83cc1-107">e19d6ea5-3cc2-4db9-8095-0cdaed5a703d</span><span class="sxs-lookup"><span data-stu-id="83cc1-107">e19d6ea5-3cc2-4db9-8095-0cdaed5a703d</span></span>

