---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc01 (VB.NET) サンプル コード
description: GetProc01 (VB.NET) サンプル コード
ms.openlocfilehash: c042b926615e4c88004d50841f25795ceec9aa2d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654474"
---
# <a name="getproc01-vbnet-sample-code"></a><span data-ttu-id="45511-103">GetProc01 (VB.NET) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="45511-103">GetProc01 (VB.NET) Sample Code</span></span>

<span data-ttu-id="45511-104">次のコードは、GetProc01 サンプルコマンドレットの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="45511-104">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="45511-105">このコマンドレットは、実際にプロセスを取得する作業を、 [System. Getprocesses \*](/dotnet/api/System.Diagnostics.Process.GetProcesses) メソッドのままにすることによって簡略化されています。</span><span class="sxs-lookup"><span data-stu-id="45511-105">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="45511-106">この Get-Proc コマンドレットの C# ソースファイル (getproc01.cs) をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="45511-106">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="45511-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45511-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="45511-108">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="45511-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="45511-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="45511-109">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [msh_samplesgetproc01#getproc01vball](msh_samplesgetproc01#getproc01vball)]  -->

## <a name="see-also"></a><span data-ttu-id="45511-110">参照</span><span class="sxs-lookup"><span data-stu-id="45511-110">See Also</span></span>

[<span data-ttu-id="45511-111">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="45511-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="45511-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="45511-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
