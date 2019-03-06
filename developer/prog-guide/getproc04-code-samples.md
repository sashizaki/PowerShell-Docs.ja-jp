---
title: GetProc04 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c00afd46-758a-4aec-b865-2c9d8f6a17ad
caps.latest.revision: 5
ms.openlocfilehash: b9b42c818981090496f7b14a1cb8bdec14a5d5bb
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429722"
---
# <a name="getproc04-code-samples"></a><span data-ttu-id="52277-102">GetProc04 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="52277-102">GetProc04 Code Samples</span></span>

<span data-ttu-id="52277-103">GetProc04 サンプル コマンドレットのコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="52277-103">Here are the code samples for the GetProc04 sample cmdlet.</span></span> <span data-ttu-id="52277-104">これは、`Get-Process`で説明されているコマンドレット サンプル[Your コマンドレットの終わらないエラー報告の追加](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)します。</span><span class="sxs-lookup"><span data-stu-id="52277-104">This is the `Get-Process` cmdlet sample described in [Adding Nonterminating Error Reporting to Your Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span></span> <span data-ttu-id="52277-105">これは、`Get-Process`コマンドレットの呼び出し、 [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)プロセス情報の取得中には無効操作例外がスローされるメソッド。</span><span class="sxs-lookup"><span data-stu-id="52277-105">This `Get-Process` cmdlet calls the [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method whenever an invalid operation exception is thrown while retrieving process information.</span></span>

> [!NOTE]
> <span data-ttu-id="52277-106">ダウンロードすることができます、C#この Get-proc コマンドレットは、Microsoft Windows ソフトウェア開発キットの Windows Vista と .NET Framework 3.0 ランタイム コンポーネントを使用してソース ファイル (getprov04.cs)。</span><span class="sxs-lookup"><span data-stu-id="52277-106">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="52277-107">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="52277-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="52277-108">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="52277-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="52277-109">完全なサンプル コードでは、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="52277-109">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="52277-110">Language</span><span class="sxs-lookup"><span data-stu-id="52277-110">Language</span></span>|<span data-ttu-id="52277-111">トピック</span><span class="sxs-lookup"><span data-stu-id="52277-111">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="52277-112">C#</span><span class="sxs-lookup"><span data-stu-id="52277-112">C#</span></span>|[<span data-ttu-id="52277-113">GetProc04 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="52277-113">GetProc04 (C#) Sample Code</span></span>](./getproc04-csharp-sample-code.md)|
|<span data-ttu-id="52277-114">VB.NET</span><span class="sxs-lookup"><span data-stu-id="52277-114">VB.NET</span></span>|[<span data-ttu-id="52277-115">GetProc04 (VB.NET) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="52277-115">GetProc04 (VB.NET) Sample Code</span></span>](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="52277-116">参照</span><span class="sxs-lookup"><span data-stu-id="52277-116">See Also</span></span>

[<span data-ttu-id="52277-117">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="52277-117">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="52277-118">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="52277-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)