---
title: RunSpace08 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f286201-8a02-4b00-9a2c-1b833ccdbdbf
caps.latest.revision: 7
ms.openlocfilehash: ec6aae544eafea1dedc1379dab00beeed2c7c436
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734921"
---
# <a name="runspace08-code-sample"></a><span data-ttu-id="95e36-102">RunSpace08 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="95e36-102">RunSpace08 Code Sample</span></span>

<span data-ttu-id="95e36-103">記載されている Runspace08 サンプルのソース コードを次に示します[、コンソール アプリケーションを追加するパラメーターを作成コマンド](https://msdn.microsoft.com/en-us/848b2b46-60f1-4a86-b448-cfc7c0cccfba)します。</span><span class="sxs-lookup"><span data-stu-id="95e36-103">Here is the source code for the Runspace08 sample described in [Creating a Console Application That Adds Parameters to a Command](https://msdn.microsoft.com/en-us/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span></span> <span data-ttu-id="95e36-104">このサンプル アプリケーション、実行空間を作成します、パイプラインを作成、パイプラインに 2 つのコマンドを追加します、2 番目のコマンドを 2 つのパラメーターを追加します。 およびし、パイプラインを実行します。</span><span class="sxs-lookup"><span data-stu-id="95e36-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, adds two parameters to the second command, and then executes the pipeline.</span></span> <span data-ttu-id="95e36-105">パイプラインに追加されるコマンドは、`Get-Process`と`Sort-Object`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="95e36-105">The commands that are added to the pipeline are the `Get-Process` and `Sort-Object` cmdlets.</span></span>

## <a name="code-sample"></a><span data-ttu-id="95e36-106">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="95e36-106">Code Sample</span></span>

[!code-csharp[Runspace08.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs#L11-L86 "Runspace08.cs")]

## <a name="see-also"></a><span data-ttu-id="95e36-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="95e36-107">See Also</span></span>

[<span data-ttu-id="95e36-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="95e36-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)