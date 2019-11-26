---
title: Runspace01 (C#) コードサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d59f8b7c-e800-4633-aa5b-74d4c57e2706
caps.latest.revision: 6
ms.openlocfilehash: 607113ed566fc1e08e5b1d7092c83da2a22366ca
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74418024"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="aea72-102">Runspace01 (C#) コード サンプル</span><span class="sxs-lookup"><span data-stu-id="aea72-102">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="aea72-103">ここでは、「[指定されたコマンドを実行するコンソールアプリケーションの作成](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program)」で説明されている実行空間のコードサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="aea72-103">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span></span> <span data-ttu-id="aea72-104">これを行うには、アプリケーションが実行空間を呼び出し、コマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="aea72-104">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="aea72-105">(このアプリケーションは実行空間の構成情報を指定せず、明示的にパイプラインを作成しないことに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="aea72-105">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="aea72-106">呼び出されるコマンドは、`Get-Process` コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="aea72-106">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="aea72-107">この実行空間のC#ソースファイル (runspace01.cs) は、windows Vista 用 Microsoft Windows ソフトウェア開発キットおよび Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用してダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="aea72-107">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="aea72-108">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aea72-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="aea72-109">ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="aea72-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="aea72-110">コードサンプル</span><span class="sxs-lookup"><span data-stu-id="aea72-110">Code Sample</span></span>

[!code-csharp[Runspace01.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs#L11-L62 "Runspace01.cs")]

## <a name="see-also"></a><span data-ttu-id="aea72-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="aea72-111">See Also</span></span>

[<span data-ttu-id="aea72-112">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="aea72-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="aea72-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="aea72-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
