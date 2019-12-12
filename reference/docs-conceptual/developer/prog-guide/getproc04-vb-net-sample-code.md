---
title: GetProc04 (VB.NET) サンプルコード |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d22f47b-3679-4587-a559-94454415d2dd
caps.latest.revision: 5
ms.openlocfilehash: f2164b97e4f3b3346e66d00834aa299659b62b33
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74416097"
---
# <a name="getproc04-vbnet-sample-code"></a><span data-ttu-id="8d60e-102">GetProc04 (VB.NET) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="8d60e-102">GetProc04 (VB.NET) Sample Code</span></span>

<span data-ttu-id="8d60e-103">次のコードは、終了しないエラーを報告する `Get-Process` コマンドレットの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="8d60e-103">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="8d60e-104">この実装では、 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドを呼び出して、終了しないエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="8d60e-104">This implementation calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="8d60e-105">この getprov04.cs コマンドレットC#のソースファイル () をダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d60e-105">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="8d60e-106">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d60e-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="8d60e-107">ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="8d60e-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="8d60e-108">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="8d60e-108">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc04#GetProc04vball](Msh_samplesgetproc04#GetProc04vball)]  -->

## <a name="see-also"></a><span data-ttu-id="8d60e-109">参照</span><span class="sxs-lookup"><span data-stu-id="8d60e-109">See Also</span></span>

[<span data-ttu-id="8d60e-110">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="8d60e-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="8d60e-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="8d60e-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
