---
title: GetProc01 (VB.NET) サンプルコード |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0d6573a41d627b18f1d577973450463f965d95f1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87778806"
---
# <a name="getproc01-vbnet-sample-code"></a><span data-ttu-id="09eb4-102">GetProc01 (VB.NET) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="09eb4-102">GetProc01 (VB.NET) Sample Code</span></span>

<span data-ttu-id="09eb4-103">次のコードは、GetProc01 サンプルコマンドレットの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="09eb4-103">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="09eb4-104">このコマンドレットは、実際にプロセスを取得する作業を、 [System. Getprocesses \*](/dotnet/api/System.Diagnostics.Process.GetProcesses)メソッドのままにすることによって簡略化されています。</span><span class="sxs-lookup"><span data-stu-id="09eb4-104">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="09eb4-105">この getproc01.cs コマンドレットの C# ソースファイル () をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="09eb4-105">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="09eb4-106">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09eb4-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="09eb4-107">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="09eb4-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="09eb4-108">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="09eb4-108">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [msh_samplesgetproc01#getproc01vball](msh_samplesgetproc01#getproc01vball)]  -->

## <a name="see-also"></a><span data-ttu-id="09eb4-109">参照</span><span class="sxs-lookup"><span data-stu-id="09eb4-109">See Also</span></span>

[<span data-ttu-id="09eb4-110">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="09eb4-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="09eb4-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="09eb4-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
