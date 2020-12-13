---
ms.date: 09/13/2016
ms.topic: reference
title: RunSpace09 コード サンプル
description: RunSpace09 コード サンプル
ms.openlocfilehash: 52ebfa5dcfd6c12d2ded78a41a6090caa5087149
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654199"
---
# <a name="runspace09-code-sample"></a><span data-ttu-id="02051-103">RunSpace09 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="02051-103">RunSpace09 Code Sample</span></span>

<span data-ttu-id="02051-104">次に示すのは、「 [パイプラインを非同期に呼び出すコンソールアプリケーションの作成](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47)」で説明されている Runspace09 サンプルのソースコードです。</span><span class="sxs-lookup"><span data-stu-id="02051-104">Here is the source code for the Runspace09 sample described in [Creating a Console Application That Invokes a Pipeline Asynchronously](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).</span></span>
<span data-ttu-id="02051-105">このサンプルアプリケーションは、実行空間を作成して開き、パイプラインを作成して非同期的に呼び出し、パイプラインイベントを使用してスクリプトを非同期的に処理します。</span><span class="sxs-lookup"><span data-stu-id="02051-105">This sample application creates and opens a runspace, creates and asynchronously invokes a pipeline, and then uses pipeline events to process the script asynchronously.</span></span> <span data-ttu-id="02051-106">このアプリケーションによって実行されるスクリプトでは、1 ~ 10 の整数が0.5 秒間隔 (500 ミリ秒) で作成されます。</span><span class="sxs-lookup"><span data-stu-id="02051-106">The script that is run by this application creates the integers 1 through 10 in 0.5-second intervals (500 ms).</span></span>

## <a name="code-sample"></a><span data-ttu-id="02051-107">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="02051-107">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs" range="11-113":::

## <a name="see-also"></a><span data-ttu-id="02051-108">参照</span><span class="sxs-lookup"><span data-stu-id="02051-108">See Also</span></span>

[<span data-ttu-id="02051-109">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="02051-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
