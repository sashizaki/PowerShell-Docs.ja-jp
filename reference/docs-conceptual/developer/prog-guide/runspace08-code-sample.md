---
title: RunSpace08 コードサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 67172a0f8d6daf2f5b9965d1a18f7698daddbe1a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784692"
---
# <a name="runspace08-code-sample"></a><span data-ttu-id="868ed-102">RunSpace08 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="868ed-102">RunSpace08 Code Sample</span></span>

<span data-ttu-id="868ed-103">次に示すのは、[コマンドにパラメーターを追加するコンソールアプリケーションの作成](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba)に関するページで説明されている Runspace08 サンプルのソースコードです。</span><span class="sxs-lookup"><span data-stu-id="868ed-103">Here is the source code for the Runspace08 sample described in [Creating a Console Application That Adds Parameters to a Command](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span></span>
<span data-ttu-id="868ed-104">このサンプルアプリケーションでは、実行空間を作成し、パイプラインを作成して、パイプラインに2つのコマンドを追加し、2つのパラメーターを2番目のコマンドに追加してから、パイプラインを実行します。</span><span class="sxs-lookup"><span data-stu-id="868ed-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, adds two parameters to the second command, and then executes the pipeline.</span></span> <span data-ttu-id="868ed-105">パイプラインに追加されるコマンドは、コマンド `Get-Process` レットとコマンド `Sort-Object` レットです。</span><span class="sxs-lookup"><span data-stu-id="868ed-105">The commands that are added to the pipeline are the `Get-Process` and `Sort-Object` cmdlets.</span></span>

## <a name="code-sample"></a><span data-ttu-id="868ed-106">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="868ed-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs" range="11-86":::

## <a name="see-also"></a><span data-ttu-id="868ed-107">参照</span><span class="sxs-lookup"><span data-stu-id="868ed-107">See Also</span></span>

[<span data-ttu-id="868ed-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="868ed-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
