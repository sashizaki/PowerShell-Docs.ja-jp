---
title: RunSpace06 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d71f86d5-eb62-4b16-aa95-5fd3f314ffd3
caps.latest.revision: 6
ms.openlocfilehash: 2874f9df3f5166fbe14deb5b128674540c0d6701
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854038"
---
# <a name="runspace06-code-sample"></a><span data-ttu-id="ad349-102">RunSpace06 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="ad349-102">RunSpace06 Code Sample</span></span>

<span data-ttu-id="ad349-103">記載されている Runspace06 サンプルのソース コードを次に示します[、Windows PowerShell スナップインを使用して、実行空間を構成する](http://msdn.microsoft.com/en-us/a7289ee8-9732-49ee-91c7-d533e9538b83)します。</span><span class="sxs-lookup"><span data-stu-id="ad349-103">Here is the source code for the Runspace06 sample described in [Configuring a Runspace Using a Windows PowerShell Snap-in](http://msdn.microsoft.com/en-us/a7289ee8-9732-49ee-91c7-d533e9538b83).</span></span> <span data-ttu-id="ad349-104">このサンプル アプリケーションは、Windows PowerShell スナップインを 1 つのコマンドを使用して、パイプラインの実行を使用して、これに基づいて、実行空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="ad349-104">This sample application creates a runspace based on a Windows PowerShell snap-in, which is then used to run a pipeline with a single command.</span></span> <span data-ttu-id="ad349-105">これを行うには、アプリケーション実行空間の構成情報を作成、実行空間を作成します、1 つのコマンドでパイプラインを作成しますおよびし、パイプラインを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad349-105">To do this, the application creates the runspace configuration information, creates a runspace, creates a pipeline with a single command, and then executes the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="ad349-106">ダウンロードすることができます、 C# Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用してソース ファイル (runspace06.cs)。</span><span class="sxs-lookup"><span data-stu-id="ad349-106">You can download the C# source file (runspace06.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="ad349-107">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="ad349-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="ad349-108">ダウンロードすることができます、 C# Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用してソース ファイル (runspace06.cs)。</span><span class="sxs-lookup"><span data-stu-id="ad349-108">You can download the C# source file (runspace06.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="ad349-109">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="ad349-109">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="ad349-110">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="ad349-110">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="ad349-111">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="ad349-111">Code Sample</span></span>

[!code-csharp[Runspace06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs#L11-L85 "Runspace06.cs")]

## <a name="see-also"></a><span data-ttu-id="ad349-112">参照</span><span class="sxs-lookup"><span data-stu-id="ad349-112">See Also</span></span>

[<span data-ttu-id="ad349-113">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="ad349-113">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="ad349-114">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="ad349-114">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)