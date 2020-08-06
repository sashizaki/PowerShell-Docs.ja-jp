---
title: GetProc04 のコードサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b90b7e96c1454e57df93863b526758f25d9be690
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771959"
---
# <a name="getproc04-code-samples"></a><span data-ttu-id="6f78d-102">GetProc04 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="6f78d-102">GetProc04 Code Samples</span></span>

<span data-ttu-id="6f78d-103">GetProc04 サンプルコマンドレットのコードサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="6f78d-103">Here are the code samples for the GetProc04 sample cmdlet.</span></span> <span data-ttu-id="6f78d-104">これは、 `Get-Process` 「[コマンドレットに終了しないエラー報告を追加](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)する」で説明されているコマンドレットのサンプルです。</span><span class="sxs-lookup"><span data-stu-id="6f78d-104">This is the `Get-Process` cmdlet sample described in [Adding Nonterminating Error Reporting to Your Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span></span> <span data-ttu-id="6f78d-105">この `Get-Process` コマンドレットは、プロセス情報の取得中に無効な操作の例外がスローされた場合に、 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6f78d-105">This `Get-Process` cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method whenever an invalid operation exception is thrown while retrieving process information.</span></span>

> [!NOTE]
> <span data-ttu-id="6f78d-106">この getprov04.cs コマンドレットの C# ソースファイル () をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f78d-106">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="6f78d-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f78d-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="6f78d-108">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="6f78d-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="6f78d-109">完全なサンプルコードについては、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f78d-109">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="6f78d-110">言語</span><span class="sxs-lookup"><span data-stu-id="6f78d-110">Language</span></span>|<span data-ttu-id="6f78d-111">トピック</span><span class="sxs-lookup"><span data-stu-id="6f78d-111">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="6f78d-112">C#</span><span class="sxs-lookup"><span data-stu-id="6f78d-112">C#</span></span>|[<span data-ttu-id="6f78d-113">GetProc04 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="6f78d-113">GetProc04 (C#) Sample Code</span></span>](./getproc04-csharp-sample-code.md)|
|<span data-ttu-id="6f78d-114">VB.NET</span><span class="sxs-lookup"><span data-stu-id="6f78d-114">VB.NET</span></span>|[<span data-ttu-id="6f78d-115">GetProc04 (VB.NET) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="6f78d-115">GetProc04 (VB.NET) Sample Code</span></span>](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="6f78d-116">参照</span><span class="sxs-lookup"><span data-stu-id="6f78d-116">See Also</span></span>

[<span data-ttu-id="6f78d-117">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="6f78d-117">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="6f78d-118">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="6f78d-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
