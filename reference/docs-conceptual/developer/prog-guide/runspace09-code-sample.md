---
title: RunSpace09 コードサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: fc5d8d4d182cca6bfc42d63c68a14a7a5e5f9c97
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784675"
---
# <a name="runspace09-code-sample"></a><span data-ttu-id="c96be-102">RunSpace09 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="c96be-102">RunSpace09 Code Sample</span></span>

<span data-ttu-id="c96be-103">次に示すのは、「[パイプラインを非同期に呼び出すコンソールアプリケーションの作成](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47)」で説明されている Runspace09 サンプルのソースコードです。</span><span class="sxs-lookup"><span data-stu-id="c96be-103">Here is the source code for the Runspace09 sample described in [Creating a Console Application That Invokes a Pipeline Asynchronously](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).</span></span>
<span data-ttu-id="c96be-104">このサンプルアプリケーションは、実行空間を作成して開き、パイプラインを作成して非同期的に呼び出し、パイプラインイベントを使用してスクリプトを非同期的に処理します。</span><span class="sxs-lookup"><span data-stu-id="c96be-104">This sample application creates and opens a runspace, creates and asynchronously invokes a pipeline, and then uses pipeline events to process the script asynchronously.</span></span> <span data-ttu-id="c96be-105">このアプリケーションによって実行されるスクリプトでは、1 ~ 10 の整数が0.5 秒間隔 (500 ミリ秒) で作成されます。</span><span class="sxs-lookup"><span data-stu-id="c96be-105">The script that is run by this application creates the integers 1 through 10 in 0.5-second intervals (500 ms).</span></span>

## <a name="code-sample"></a><span data-ttu-id="c96be-106">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="c96be-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs" range="11-113":::

## <a name="see-also"></a><span data-ttu-id="c96be-107">参照</span><span class="sxs-lookup"><span data-stu-id="c96be-107">See Also</span></span>

[<span data-ttu-id="c96be-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="c96be-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
