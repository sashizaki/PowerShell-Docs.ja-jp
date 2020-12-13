---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc04 コード サンプル
description: GetProc04 コード サンプル
ms.openlocfilehash: db94eda2b3aa5fc88a3054df66f54628e1482f56
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659236"
---
# <a name="getproc04-code-samples"></a><span data-ttu-id="9a9e5-103">GetProc04 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="9a9e5-103">GetProc04 Code Samples</span></span>

<span data-ttu-id="9a9e5-104">GetProc04 サンプルコマンドレットのコードサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-104">Here are the code samples for the GetProc04 sample cmdlet.</span></span> <span data-ttu-id="9a9e5-105">これは、 `Get-Process` 「 [コマンドレットに終了しないエラー報告を追加](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)する」で説明されているコマンドレットのサンプルです。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-105">This is the `Get-Process` cmdlet sample described in [Adding Nonterminating Error Reporting to Your Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span></span> <span data-ttu-id="9a9e5-106">この `Get-Process` コマンドレットは、プロセス情報の取得中に無効な操作の例外がスローされた場合に、 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-106">This `Get-Process` cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method whenever an invalid operation exception is thrown while retrieving process information.</span></span>

> [!NOTE]
> <span data-ttu-id="9a9e5-107">この Get-Proc コマンドレットの C# ソースファイル (getprov04.cs) をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-107">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="9a9e5-108">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="9a9e5-109">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="9a9e5-110">完全なサンプルコードについては、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-110">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="9a9e5-111">言語</span><span class="sxs-lookup"><span data-stu-id="9a9e5-111">Language</span></span>|<span data-ttu-id="9a9e5-112">トピック</span><span class="sxs-lookup"><span data-stu-id="9a9e5-112">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="9a9e5-113">C#</span><span class="sxs-lookup"><span data-stu-id="9a9e5-113">C#</span></span>|[<span data-ttu-id="9a9e5-114">GetProc04 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="9a9e5-114">GetProc04 (C#) Sample Code</span></span>](./getproc04-csharp-sample-code.md)|
|<span data-ttu-id="9a9e5-115">VB.NET</span><span class="sxs-lookup"><span data-stu-id="9a9e5-115">VB.NET</span></span>|[<span data-ttu-id="9a9e5-116">GetProc04 (VB.NET) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="9a9e5-116">GetProc04 (VB.NET) Sample Code</span></span>](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="9a9e5-117">参照</span><span class="sxs-lookup"><span data-stu-id="9a9e5-117">See Also</span></span>

[<span data-ttu-id="9a9e5-118">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="9a9e5-118">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="9a9e5-119">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="9a9e5-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
