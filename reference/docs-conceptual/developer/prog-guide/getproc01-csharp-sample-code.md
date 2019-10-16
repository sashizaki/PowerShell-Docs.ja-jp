---
title: GetProc01 (C#) Sample Code |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65094bb7-1972-44b3-b8b0-5f639860b58c
caps.latest.revision: 5
ms.openlocfilehash: 06a24266eb8fda6e4f138f1f77ae702f7454e525
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366801"
---
# <a name="getproc01-c-sample-code"></a><span data-ttu-id="36197-102">GetProc01 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="36197-102">GetProc01 (C#) Sample Code</span></span>

<span data-ttu-id="36197-103">次のコードは、GetProc01 サンプルコマンドレットの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="36197-103">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="36197-104">このコマンドレットは、実際にプロセスを取得する作業を、 [System. Getprocesses \*](/dotnet/api/System.Diagnostics.Process.GetProcesses)メソッドのままにすることによって簡略化されています。</span><span class="sxs-lookup"><span data-stu-id="36197-104">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="36197-105">この getproc01.cs コマンドレットC#のソースファイル () をダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="36197-105">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="36197-106">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36197-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="36197-107">ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="36197-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="36197-108">コードサンプル</span><span class="sxs-lookup"><span data-stu-id="36197-108">Code Sample</span></span>

[!code-csharp[GetProcessSample01.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs#L11-L126 "GetProcessSample01.cs")]

## <a name="see-also"></a><span data-ttu-id="36197-109">参照</span><span class="sxs-lookup"><span data-stu-id="36197-109">See Also</span></span>

[<span data-ttu-id="36197-110">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="36197-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="36197-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="36197-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
