---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc03 コード サンプル
description: GetProc03 コード サンプル
ms.openlocfilehash: 2866f3652072e1d89780c818543dbfc72a0606f0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659269"
---
# <a name="getproc03-code-samples"></a><span data-ttu-id="9d86a-103">GetProc03 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="9d86a-103">GetProc03 Code Samples</span></span>

<span data-ttu-id="9d86a-104">GetProc03 サンプルコマンドレットのコードサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9d86a-104">Here are the code samples for the GetProc03 sample cmdlet.</span></span> <span data-ttu-id="9d86a-105">これは、 `Get-Process` 「 [パイプライン入力を処理するパラメーターの追加](../cmdlet/adding-parameters-that-process-pipeline-input.md)」で説明されているコマンドレットのサンプルです。</span><span class="sxs-lookup"><span data-stu-id="9d86a-105">This is the `Get-Process` cmdlet sample described in [Adding Parameters that Process Pipeline Input](../cmdlet/adding-parameters-that-process-pipeline-input.md).</span></span> <span data-ttu-id="9d86a-106">この `Get-Process` コマンドレットは、 `Name` パイプラインオブジェクトからの入力を受け入れ、指定された名前に基づいてローカルコンピューターからプロセス情報を取得し、コマンドラインでプロセスに関する情報を表示するパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d86a-106">This `Get-Process` cmdlet uses a `Name` parameter that accepts input from a pipeline object, retrieves process information from the local computer based on the supplied names, and then displays information about the processes at the command line.</span></span>

> [!NOTE]
> <span data-ttu-id="9d86a-107">この Get-Proc コマンドレットの C# ソースファイル (getprov03.cs) をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d86a-107">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="9d86a-108">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d86a-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="9d86a-109">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="9d86a-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="9d86a-110">完全なサンプルコードについては、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d86a-110">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="9d86a-111">言語</span><span class="sxs-lookup"><span data-stu-id="9d86a-111">Language</span></span>|<span data-ttu-id="9d86a-112">トピック</span><span class="sxs-lookup"><span data-stu-id="9d86a-112">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="9d86a-113">C#</span><span class="sxs-lookup"><span data-stu-id="9d86a-113">C#</span></span>|[<span data-ttu-id="9d86a-114">GetProc03 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="9d86a-114">GetProc03 (C#) Sample Code</span></span>](./getproc03-csharp-sample-code.md)|
|<span data-ttu-id="9d86a-115">VB.NET</span><span class="sxs-lookup"><span data-stu-id="9d86a-115">VB.NET</span></span>|[<span data-ttu-id="9d86a-116">GetProc03 (VB.NET) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="9d86a-116">GetProc03 (VB.NET) Sample Code</span></span>](./getproc03-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="9d86a-117">参照</span><span class="sxs-lookup"><span data-stu-id="9d86a-117">See Also</span></span>

[<span data-ttu-id="9d86a-118">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="9d86a-118">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="9d86a-119">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="9d86a-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
