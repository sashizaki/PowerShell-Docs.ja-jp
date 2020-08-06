---
title: RunSpace06 コードサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c8767ac8dc3a3d9253c2a53a4754d9bd54304abb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784726"
---
# <a name="runspace06-code-sample"></a><span data-ttu-id="effbc-102">RunSpace06 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="effbc-102">RunSpace06 Code Sample</span></span>

<span data-ttu-id="effbc-103">次に示すのは、「 [Windows PowerShell スナップインを使用して実行空間を構成](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83)する」で説明されている Runspace06 サンプルのソースコードです。</span><span class="sxs-lookup"><span data-stu-id="effbc-103">Here is the source code for the Runspace06 sample described in [Configuring a Runspace Using a Windows PowerShell Snap-in](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83).</span></span>
<span data-ttu-id="effbc-104">このサンプルアプリケーションでは、Windows PowerShell スナップインに基づいて実行空間を作成します。これは、1つのコマンドでパイプラインを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="effbc-104">This sample application creates a runspace based on a Windows PowerShell snap-in, which is then used to run a pipeline with a single command.</span></span> <span data-ttu-id="effbc-105">これを行うために、アプリケーションは実行空間の構成情報を作成し、実行空間を作成し、1つのコマンドを使用してパイプラインを作成してから、パイプラインを実行します。</span><span class="sxs-lookup"><span data-stu-id="effbc-105">To do this, the application creates the runspace configuration information, creates a runspace, creates a pipeline with a single command, and then executes the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="effbc-106">C# ソースファイル (runspace06.cs) は、windows Vista 用 Windows ソフトウェア開発キットおよび Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用してダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="effbc-106">You can download the C# source file (runspace06.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="effbc-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="effbc-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="effbc-108">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="effbc-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="effbc-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="effbc-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs" range="11-85":::

## <a name="see-also"></a><span data-ttu-id="effbc-110">参照</span><span class="sxs-lookup"><span data-stu-id="effbc-110">See Also</span></span>

[<span data-ttu-id="effbc-111">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="effbc-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="effbc-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="effbc-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
