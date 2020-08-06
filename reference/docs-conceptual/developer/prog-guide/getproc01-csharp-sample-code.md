---
title: GetProc01 (C#) サンプルコード |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 883beb9dd1328a1897b9b61656a98cf515a21be7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87778892"
---
# <a name="getproc01-c-sample-code"></a><span data-ttu-id="b374e-102">GetProc01 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="b374e-102">GetProc01 (C#) Sample Code</span></span>

<span data-ttu-id="b374e-103">次のコードは、GetProc01 サンプルコマンドレットの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="b374e-103">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="b374e-104">このコマンドレットは、実際にプロセスを取得する作業を、 [System. Getprocesses \*](/dotnet/api/System.Diagnostics.Process.GetProcesses)メソッドのままにすることによって簡略化されています。</span><span class="sxs-lookup"><span data-stu-id="b374e-104">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="b374e-105">この getproc01.cs コマンドレットの C# ソースファイル () をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="b374e-105">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="b374e-106">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b374e-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="b374e-107">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="b374e-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="b374e-108">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="b374e-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs" range="11-126":::

## <a name="see-also"></a><span data-ttu-id="b374e-109">参照</span><span class="sxs-lookup"><span data-stu-id="b374e-109">See Also</span></span>

[<span data-ttu-id="b374e-110">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="b374e-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="b374e-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="b374e-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
