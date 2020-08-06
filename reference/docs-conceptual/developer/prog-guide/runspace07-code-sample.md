---
title: RunSpace07 コードサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 615bb237d26bf3a314ea7fb21e983ba2b000d105
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784709"
---
# <a name="runspace07-code-sample"></a><span data-ttu-id="b8d22-102">RunSpace07 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="b8d22-102">RunSpace07 Code Sample</span></span>

<span data-ttu-id="b8d22-103">[パイプラインにコマンドを追加するコンソールアプリケーションの作成](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e)に関するページで説明されている Runspace07 サンプルのソースコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b8d22-103">Here is the source code for the Runspace07 sample described in [Creating a Console Application That Adds Commands to a Pipeline](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e).</span></span>
<span data-ttu-id="b8d22-104">このサンプルアプリケーションでは、実行空間を作成し、パイプラインを作成して、パイプラインに2つのコマンドを追加してから、パイプラインを実行します。</span><span class="sxs-lookup"><span data-stu-id="b8d22-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, and then executes the pipeline.</span></span> <span data-ttu-id="b8d22-105">パイプラインに追加されるコマンドは、 `Get-Process` コマンド `Measure-Object` レットとコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="b8d22-105">The commands added to the pipeline are the `Get-Process` and `Measure-Object` cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="b8d22-106">C# ソースファイル (runspace07.cs) は、Windows Vista 用 Microsoft Windows ソフトウェア開発キットおよび Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用してダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="b8d22-106">You can download the C# source file (runspace07.cs) using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="b8d22-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8d22-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="b8d22-108">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="b8d22-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="b8d22-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="b8d22-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs" range="11-108":::

## <a name="see-also"></a><span data-ttu-id="b8d22-110">参照</span><span class="sxs-lookup"><span data-stu-id="b8d22-110">See Also</span></span>

[<span data-ttu-id="b8d22-111">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="b8d22-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="b8d22-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="b8d22-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
