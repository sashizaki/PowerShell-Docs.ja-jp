---
title: GetProc04 (VB.NET) サンプル コード |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d22f47b-3679-4587-a559-94454415d2dd
caps.latest.revision: 5
ms.openlocfilehash: 8de99247574de130b91eea78b9af81dafbab48eb
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429620"
---
# <a name="getproc04-vbnet-sample-code"></a><span data-ttu-id="7e272-102">GetProc04 (VB.NET) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="7e272-102">GetProc04 (VB.NET) Sample Code</span></span>

<span data-ttu-id="7e272-103">次のコードの実装を示しています、`Get-Process`終わらないエラーを報告するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="7e272-103">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="7e272-104">この実装を呼び出す、 [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)終了しないエラーを報告するメソッド。</span><span class="sxs-lookup"><span data-stu-id="7e272-104">This implementation calls the [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="7e272-105">ダウンロードすることができます、C#この Get-proc コマンドレットは、Microsoft Windows ソフトウェア開発キットの Windows Vista と .NET Framework 3.0 ランタイム コンポーネントを使用してソース ファイル (getprov04.cs)。</span><span class="sxs-lookup"><span data-stu-id="7e272-105">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="7e272-106">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="7e272-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="7e272-107">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="7e272-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="7e272-108">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="7e272-108">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc04#GetProc04vball](Msh_samplesgetproc04#GetProc04vball)]  -->

## <a name="see-also"></a><span data-ttu-id="7e272-109">参照</span><span class="sxs-lookup"><span data-stu-id="7e272-109">See Also</span></span>

[<span data-ttu-id="7e272-110">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="7e272-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="7e272-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="7e272-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)