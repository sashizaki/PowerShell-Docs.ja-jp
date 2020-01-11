---
title: RunSpace07 コードサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ad306d9-45c2-4d55-8e64-fdcba43402c5
caps.latest.revision: 6
ms.openlocfilehash: f40b24951c44c228d85524845045aea58f680f2e
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870610"
---
# <a name="runspace07-code-sample"></a><span data-ttu-id="99475-102">RunSpace07 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="99475-102">RunSpace07 Code Sample</span></span>

<span data-ttu-id="99475-103">[パイプラインにコマンドを追加するコンソールアプリケーションの作成](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e)に関するページで説明されている Runspace07 サンプルのソースコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="99475-103">Here is the source code for the Runspace07 sample described in [Creating a Console Application That Adds Commands to a Pipeline](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e).</span></span>
<span data-ttu-id="99475-104">このサンプルアプリケーションでは、実行空間を作成し、パイプラインを作成して、パイプラインに2つのコマンドを追加してから、パイプラインを実行します。</span><span class="sxs-lookup"><span data-stu-id="99475-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, and then executes the pipeline.</span></span> <span data-ttu-id="99475-105">パイプラインに追加されたコマンドは、`Get-Process` と `Measure-Object` のコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="99475-105">The commands added to the pipeline are the `Get-Process` and `Measure-Object` cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="99475-106">C#ソースファイル (runspace07.cs) は、windows Vista 用の Microsoft Windows ソフトウェア開発キットおよび Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用してダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="99475-106">You can download the C# source file (runspace07.cs) using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="99475-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99475-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="99475-108">ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="99475-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="99475-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="99475-109">Code Sample</span></span>

[!code-csharp[Runspace07.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs#L11-L108 "Runspace07.cs")]

## <a name="see-also"></a><span data-ttu-id="99475-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="99475-110">See Also</span></span>

[<span data-ttu-id="99475-111">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="99475-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="99475-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="99475-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
