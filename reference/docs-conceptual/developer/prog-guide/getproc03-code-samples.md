---
title: GetProc03 のコードサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a31b17968c3a6066d2304f3029853c8d4e35e3f3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787140"
---
# <a name="getproc03-code-samples"></a><span data-ttu-id="dcf15-102">GetProc03 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="dcf15-102">GetProc03 Code Samples</span></span>

<span data-ttu-id="dcf15-103">GetProc03 サンプルコマンドレットのコードサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="dcf15-103">Here are the code samples for the GetProc03 sample cmdlet.</span></span> <span data-ttu-id="dcf15-104">これは、 `Get-Process` 「[パイプライン入力を処理するパラメーターの追加](../cmdlet/adding-parameters-that-process-pipeline-input.md)」で説明されているコマンドレットのサンプルです。</span><span class="sxs-lookup"><span data-stu-id="dcf15-104">This is the `Get-Process` cmdlet sample described in [Adding Parameters that Process Pipeline Input](../cmdlet/adding-parameters-that-process-pipeline-input.md).</span></span> <span data-ttu-id="dcf15-105">この `Get-Process` コマンドレットは、 `Name` パイプラインオブジェクトからの入力を受け入れ、指定された名前に基づいてローカルコンピューターからプロセス情報を取得し、コマンドラインでプロセスに関する情報を表示するパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="dcf15-105">This `Get-Process` cmdlet uses a `Name` parameter that accepts input from a pipeline object, retrieves process information from the local computer based on the supplied names, and then displays information about the processes at the command line.</span></span>

> [!NOTE]
> <span data-ttu-id="dcf15-106">この getprov03.cs コマンドレットの C# ソースファイル () をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="dcf15-106">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="dcf15-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcf15-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="dcf15-108">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="dcf15-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="dcf15-109">完全なサンプルコードについては、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcf15-109">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="dcf15-110">言語</span><span class="sxs-lookup"><span data-stu-id="dcf15-110">Language</span></span>|<span data-ttu-id="dcf15-111">トピック</span><span class="sxs-lookup"><span data-stu-id="dcf15-111">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="dcf15-112">C#</span><span class="sxs-lookup"><span data-stu-id="dcf15-112">C#</span></span>|[<span data-ttu-id="dcf15-113">GetProc03 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="dcf15-113">GetProc03 (C#) Sample Code</span></span>](./getproc03-csharp-sample-code.md)|
|<span data-ttu-id="dcf15-114">VB.NET</span><span class="sxs-lookup"><span data-stu-id="dcf15-114">VB.NET</span></span>|[<span data-ttu-id="dcf15-115">GetProc03 (VB.NET) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="dcf15-115">GetProc03 (VB.NET) Sample Code</span></span>](./getproc03-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="dcf15-116">参照</span><span class="sxs-lookup"><span data-stu-id="dcf15-116">See Also</span></span>

[<span data-ttu-id="dcf15-117">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="dcf15-117">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="dcf15-118">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="dcf15-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
