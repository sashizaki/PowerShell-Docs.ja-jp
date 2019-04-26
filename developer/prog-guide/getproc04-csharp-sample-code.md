---
title: GetProc04 (C#) サンプル コード |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 439ba3f3-91b1-46a4-8d07-9af6edb71bc4
caps.latest.revision: 5
ms.openlocfilehash: 936fb355be40b98136719ea929cf50b06705b687
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081633"
---
# <a name="getproc04-c-sample-code"></a><span data-ttu-id="a8123-102">GetProc04 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="a8123-102">GetProc04 (C#) Sample Code</span></span>

<span data-ttu-id="a8123-103">次のコードの実装を示しています、`Get-Process`終わらないエラーを報告するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="a8123-103">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="a8123-104">この実装を呼び出す、 [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)終了しないエラーを報告するメソッド。</span><span class="sxs-lookup"><span data-stu-id="a8123-104">This implementation calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="a8123-105">ダウンロードすることができます、C#この Get-proc コマンドレットは、Microsoft Windows ソフトウェア開発キットの Windows Vista と .NET Framework 3.0 ランタイム コンポーネントを使用してソース ファイル (getprov04.cs)。</span><span class="sxs-lookup"><span data-stu-id="a8123-105">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="a8123-106">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="a8123-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="a8123-107">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="a8123-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="a8123-108">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="a8123-108">Code Sample</span></span>

[!code-csharp[GetProcessSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample04/GetProcessSample04.cs#L11-L98 "GetProcessSample04.cs")]

## <a name="see-also"></a><span data-ttu-id="a8123-109">参照</span><span class="sxs-lookup"><span data-stu-id="a8123-109">See Also</span></span>

[<span data-ttu-id="a8123-110">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="a8123-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="a8123-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="a8123-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)