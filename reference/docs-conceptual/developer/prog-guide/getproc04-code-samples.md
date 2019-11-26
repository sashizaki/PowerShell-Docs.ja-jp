---
title: GetProc04 のコードサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c00afd46-758a-4aec-b865-2c9d8f6a17ad
caps.latest.revision: 5
ms.openlocfilehash: 8326d1f47ce07698f09ade9ba97154ecc358465a
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417461"
---
# <a name="getproc04-code-samples"></a><span data-ttu-id="e1f00-102">GetProc04 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="e1f00-102">GetProc04 Code Samples</span></span>

<span data-ttu-id="e1f00-103">GetProc04 サンプルコマンドレットのコードサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e1f00-103">Here are the code samples for the GetProc04 sample cmdlet.</span></span> <span data-ttu-id="e1f00-104">これは、「[コマンドレットに終了しないエラー報告を追加](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)する」で説明されている `Get-Process` コマンドレットのサンプルです。</span><span class="sxs-lookup"><span data-stu-id="e1f00-104">This is the `Get-Process` cmdlet sample described in [Adding Nonterminating Error Reporting to Your Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span></span> <span data-ttu-id="e1f00-105">この `Get-Process` コマンドレットは、プロセス情報の取得中に無効な操作の例外がスローされるたびに[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e1f00-105">This `Get-Process` cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method whenever an invalid operation exception is thrown while retrieving process information.</span></span>

> [!NOTE]
> <span data-ttu-id="e1f00-106">この getprov04.cs コマンドレットC#のソースファイル () をダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1f00-106">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="e1f00-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1f00-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="e1f00-108">ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="e1f00-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="e1f00-109">完全なサンプルコードについては、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1f00-109">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="e1f00-110">[言語]</span><span class="sxs-lookup"><span data-stu-id="e1f00-110">Language</span></span>|<span data-ttu-id="e1f00-111">トピック</span><span class="sxs-lookup"><span data-stu-id="e1f00-111">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="e1f00-112">C#</span><span class="sxs-lookup"><span data-stu-id="e1f00-112">C#</span></span>|[<span data-ttu-id="e1f00-113">GetProc04 (C#) サンプルコード</span><span class="sxs-lookup"><span data-stu-id="e1f00-113">GetProc04 (C#) Sample Code</span></span>](./getproc04-csharp-sample-code.md)|
|<span data-ttu-id="e1f00-114">VB.NET</span><span class="sxs-lookup"><span data-stu-id="e1f00-114">VB.NET</span></span>|[<span data-ttu-id="e1f00-115">GetProc04 (VB.NET) サンプルコード</span><span class="sxs-lookup"><span data-stu-id="e1f00-115">GetProc04 (VB.NET) Sample Code</span></span>](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="e1f00-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1f00-116">See Also</span></span>

[<span data-ttu-id="e1f00-117">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="e1f00-117">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="e1f00-118">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="e1f00-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
