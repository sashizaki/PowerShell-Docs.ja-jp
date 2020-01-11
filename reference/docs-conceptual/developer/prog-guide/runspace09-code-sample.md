---
title: RunSpace09 コードサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 136e451f-767b-42e0-bd6f-6486693abd5e
caps.latest.revision: 6
ms.openlocfilehash: 2f447fd0ce21c5bca8abe1fddb4e3c7025b70ef1
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870585"
---
# <a name="runspace09-code-sample"></a><span data-ttu-id="013f7-102">RunSpace09 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="013f7-102">RunSpace09 Code Sample</span></span>

<span data-ttu-id="013f7-103">次に示すのは、「[パイプラインを非同期に呼び出すコンソールアプリケーションの作成](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47)」で説明されている Runspace09 サンプルのソースコードです。</span><span class="sxs-lookup"><span data-stu-id="013f7-103">Here is the source code for the Runspace09 sample described in [Creating a Console Application That Invokes a Pipeline Asynchronously](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).</span></span>
<span data-ttu-id="013f7-104">このサンプルアプリケーションは、実行空間を作成して開き、パイプラインを作成して非同期的に呼び出し、パイプラインイベントを使用してスクリプトを非同期的に処理します。</span><span class="sxs-lookup"><span data-stu-id="013f7-104">This sample application creates and opens a runspace, creates and asynchronously invokes a pipeline, and then uses pipeline events to process the script asynchronously.</span></span> <span data-ttu-id="013f7-105">このアプリケーションによって実行されるスクリプトでは、1 ~ 10 の整数が0.5 秒間隔 (500 ミリ秒) で作成されます。</span><span class="sxs-lookup"><span data-stu-id="013f7-105">The script that is run by this application creates the integers 1 through 10 in 0.5-second intervals (500 ms).</span></span>

## <a name="code-sample"></a><span data-ttu-id="013f7-106">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="013f7-106">Code Sample</span></span>

[!code-csharp[Runspace09.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs#L11-L113 "Runspace09.cs")]

## <a name="see-also"></a><span data-ttu-id="013f7-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="013f7-107">See Also</span></span>

[<span data-ttu-id="013f7-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="013f7-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
