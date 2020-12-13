---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc04 (C#) サンプル コード
description: GetProc04 (C#) サンプル コード
ms.openlocfilehash: 80020b60a7ab34caec0c856b9b7d12021f4276b9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654373"
---
# <a name="getproc04-c-sample-code"></a><span data-ttu-id="de16d-103">GetProc04 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="de16d-103">GetProc04 (C#) Sample Code</span></span>

<span data-ttu-id="de16d-104">次のコードは、 `Get-Process` 終了しないエラーを報告するコマンドレットの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="de16d-104">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="de16d-105">この実装では、 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) メソッドを呼び出して、終了しないエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="de16d-105">This implementation calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="de16d-106">この Get-Proc コマンドレットの C# ソースファイル (getprov04.cs) をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="de16d-106">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="de16d-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de16d-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="de16d-108">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="de16d-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="de16d-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="de16d-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample04/GetProcessSample04.cs" range="11-98":::

## <a name="see-also"></a><span data-ttu-id="de16d-110">参照</span><span class="sxs-lookup"><span data-stu-id="de16d-110">See Also</span></span>

[<span data-ttu-id="de16d-111">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="de16d-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="de16d-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="de16d-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
