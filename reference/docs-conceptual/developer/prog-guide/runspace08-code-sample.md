---
ms.date: 09/13/2016
ms.topic: reference
title: RunSpace08 コード サンプル
description: RunSpace08 コード サンプル
ms.openlocfilehash: f8d08e5b6bbd98d0901abe5b05c8b9ee682b8e04
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654222"
---
# <a name="runspace08-code-sample"></a><span data-ttu-id="3f7f1-103">RunSpace08 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="3f7f1-103">RunSpace08 Code Sample</span></span>

<span data-ttu-id="3f7f1-104">次に示すのは、 [コマンドにパラメーターを追加するコンソールアプリケーションの作成](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba)に関するページで説明されている Runspace08 サンプルのソースコードです。</span><span class="sxs-lookup"><span data-stu-id="3f7f1-104">Here is the source code for the Runspace08 sample described in [Creating a Console Application That Adds Parameters to a Command](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span></span>
<span data-ttu-id="3f7f1-105">このサンプルアプリケーションでは、実行空間を作成し、パイプラインを作成して、パイプラインに2つのコマンドを追加し、2つのパラメーターを2番目のコマンドに追加してから、パイプラインを実行します。</span><span class="sxs-lookup"><span data-stu-id="3f7f1-105">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, adds two parameters to the second command, and then executes the pipeline.</span></span> <span data-ttu-id="3f7f1-106">パイプラインに追加されるコマンドは、コマンド `Get-Process` レットとコマンド `Sort-Object` レットです。</span><span class="sxs-lookup"><span data-stu-id="3f7f1-106">The commands that are added to the pipeline are the `Get-Process` and `Sort-Object` cmdlets.</span></span>

## <a name="code-sample"></a><span data-ttu-id="3f7f1-107">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="3f7f1-107">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs" range="11-86":::

## <a name="see-also"></a><span data-ttu-id="3f7f1-108">参照</span><span class="sxs-lookup"><span data-stu-id="3f7f1-108">See Also</span></span>

[<span data-ttu-id="3f7f1-109">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="3f7f1-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
