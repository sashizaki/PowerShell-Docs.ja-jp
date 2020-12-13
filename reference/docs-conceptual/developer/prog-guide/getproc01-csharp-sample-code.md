---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc01 (C#) サンプル コード
description: GetProc01 (C#) サンプル コード
ms.openlocfilehash: 79509ff12afb32c907058f4ddb0c707f3823857a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654490"
---
# <a name="getproc01-c-sample-code"></a><span data-ttu-id="88c17-103">GetProc01 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="88c17-103">GetProc01 (C#) Sample Code</span></span>

<span data-ttu-id="88c17-104">次のコードは、GetProc01 サンプルコマンドレットの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="88c17-104">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="88c17-105">このコマンドレットは、実際にプロセスを取得する作業を、 [System. Getprocesses \*](/dotnet/api/System.Diagnostics.Process.GetProcesses) メソッドのままにすることによって簡略化されています。</span><span class="sxs-lookup"><span data-stu-id="88c17-105">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="88c17-106">この Get-Proc コマンドレットの C# ソースファイル (getproc01.cs) をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="88c17-106">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="88c17-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88c17-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="88c17-108">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="88c17-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="88c17-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="88c17-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs" range="11-126":::

## <a name="see-also"></a><span data-ttu-id="88c17-110">参照</span><span class="sxs-lookup"><span data-stu-id="88c17-110">See Also</span></span>

[<span data-ttu-id="88c17-111">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="88c17-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="88c17-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="88c17-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
