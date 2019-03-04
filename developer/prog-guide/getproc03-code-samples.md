---
title: GetProc03 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ad39c7d-2f64-49d1-9be0-d2295e4302b3
caps.latest.revision: 5
ms.openlocfilehash: 8cb02b9f2510b90f405651deaf551e9622f5a298
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857308"
---
# <a name="getproc03-code-samples"></a><span data-ttu-id="2f812-102">GetProc03 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="2f812-102">GetProc03 Code Samples</span></span>

<span data-ttu-id="2f812-103">GetProc03 サンプル コマンドレットのコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="2f812-103">Here are the code samples for the GetProc03 sample cmdlet.</span></span> <span data-ttu-id="2f812-104">これは、`Get-Process`コマンドレットのサンプルが記載[そのプロセス パイプラインの入力パラメーターを追加する](../cmdlet/adding-parameters-that-process-pipeline-input.md)します。</span><span class="sxs-lookup"><span data-stu-id="2f812-104">This is the `Get-Process` cmdlet sample described in [Adding Parameters that Process Pipeline Input](../cmdlet/adding-parameters-that-process-pipeline-input.md).</span></span> <span data-ttu-id="2f812-105">これは、`Get-Process`コマンドレットを使用して、`Name`パイプライン オブジェクトからの入力を受け付けるパラメーターは、指定された名前に基づいて、ローカル コンピューターからプロセス情報を取得し、コマンドラインでのプロセスに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="2f812-105">This `Get-Process` cmdlet uses a `Name` parameter that accepts input from a pipeline object, retrieves process information from the local computer based on the supplied names, and then displays information about the processes at the command line.</span></span>

> [!NOTE]
> <span data-ttu-id="2f812-106">ダウンロードすることができます、C#この Get-proc コマンドレットは、Microsoft Windows ソフトウェア開発キットの Windows Vista と .NET Framework 3.0 ランタイム コンポーネントを使用してソース ファイル (getprov03.cs)。</span><span class="sxs-lookup"><span data-stu-id="2f812-106">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="2f812-107">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="2f812-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="2f812-108">ダウンロードすることができます、C#この Get-proc コマンドレットは、Microsoft Windows ソフトウェア開発キットの Windows Vista と .NET Framework 3.0 ランタイム コンポーネントを使用してソース ファイル (getprov03.cs)。</span><span class="sxs-lookup"><span data-stu-id="2f812-108">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="2f812-109">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="2f812-109">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="2f812-110">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="2f812-110">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="2f812-111">完全なサンプル コードでは、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f812-111">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="2f812-112">Language</span><span class="sxs-lookup"><span data-stu-id="2f812-112">Language</span></span>|<span data-ttu-id="2f812-113">トピック</span><span class="sxs-lookup"><span data-stu-id="2f812-113">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="2f812-114">C#</span><span class="sxs-lookup"><span data-stu-id="2f812-114">C#</span></span>|[<span data-ttu-id="2f812-115">GetProc03 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="2f812-115">GetProc03 (C#) Sample Code</span></span>](./getproc03-csharp-sample-code.md)|
|<span data-ttu-id="2f812-116">VB.NET</span><span class="sxs-lookup"><span data-stu-id="2f812-116">VB.NET</span></span>|[<span data-ttu-id="2f812-117">GetProc03 (VB.NET) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="2f812-117">GetProc03 (VB.NET) Sample Code</span></span>](./getproc03-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="2f812-118">参照</span><span class="sxs-lookup"><span data-stu-id="2f812-118">See Also</span></span>

[<span data-ttu-id="2f812-119">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="2f812-119">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="2f812-120">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="2f812-120">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)