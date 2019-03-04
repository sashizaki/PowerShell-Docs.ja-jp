---
title: RunSpace09 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 136e451f-767b-42e0-bd6f-6486693abd5e
caps.latest.revision: 6
ms.openlocfilehash: e21ef8685598db9a1ae0fcd86051386af526f2a5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854048"
---
# <a name="runspace09-code-sample"></a><span data-ttu-id="5d3e7-102">RunSpace09 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="5d3e7-102">RunSpace09 Code Sample</span></span>

<span data-ttu-id="5d3e7-103">記載されている Runspace09 サンプルのソース コードを次に示します[作成、コンソール アプリケーションを呼び出す非同期をパイプライン](http://msdn.microsoft.com/en-us/198c1c94-2a06-457e-93ce-c0d910618e47)します。</span><span class="sxs-lookup"><span data-stu-id="5d3e7-103">Here is the source code for the Runspace09 sample described in [Creating a Console Application That Invokes a Pipeline Asynchronously](http://msdn.microsoft.com/en-us/198c1c94-2a06-457e-93ce-c0d910618e47).</span></span> <span data-ttu-id="5d3e7-104">このサンプル アプリケーションを作成しますと、実行空間が表示されます、作成、パイプラインを非同期的に起動し、スクリプトを非同期的に処理するイベントのパイプラインは。</span><span class="sxs-lookup"><span data-stu-id="5d3e7-104">This sample application creates and opens a runspace, creates and asynchronously invokes a pipeline, and then uses pipeline events to process the script asynchronously.</span></span> <span data-ttu-id="5d3e7-105">このアプリケーションで実行されるスクリプトは、0.5 秒の間隔 (500 ミリ秒) で、1 ~ 10 の整数を作成します。</span><span class="sxs-lookup"><span data-stu-id="5d3e7-105">The script that is run by this application creates the integers 1 through 10 in 0.5-second intervals (500 ms).</span></span>

## <a name="code-sample"></a><span data-ttu-id="5d3e7-106">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="5d3e7-106">Code Sample</span></span>

[!code-csharp[Runspace09.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs#L11-L113 "Runspace09.cs")]

## <a name="see-also"></a><span data-ttu-id="5d3e7-107">参照</span><span class="sxs-lookup"><span data-stu-id="5d3e7-107">See Also</span></span>

[<span data-ttu-id="5d3e7-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="5d3e7-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)