---
title: StopProcessSample04 (C#) サンプル コード |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 778ce1a2-e16d-4af5-b15b-77ca4326bdc4
caps.latest.revision: 5
ms.openlocfilehash: a09efae487dd34238289a6c13dd7786020f15c7d
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429501"
---
# <a name="stopprocesssample04-c-sample-code"></a><span data-ttu-id="76a82-102">StopProcessSample04 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="76a82-102">StopProcessSample04 (C#) Sample Code</span></span>

<span data-ttu-id="76a82-103">ここでは、完全なC#StopProc04 サンプルのコマンドレットのサンプル コード。</span><span class="sxs-lookup"><span data-stu-id="76a82-103">Here is the complete C# sample code for the StopProc04 sample cmdlet.</span></span> <span data-ttu-id="76a82-104">これは、コードの`Stop-Process`で説明されているコマンドレット[コマンドレットにパラメーター セットを追加する](../cmdlet/adding-parameter-sets-to-a-cmdlet.md)します。</span><span class="sxs-lookup"><span data-stu-id="76a82-104">This is the code for the `Stop-Process` cmdlet described in [Adding Parameter Sets to a Cmdlet](../cmdlet/adding-parameter-sets-to-a-cmdlet.md).</span></span> <span data-ttu-id="76a82-105">`Stop-Process` Get-proc コマンドレットを使用して取得されるプロセスを停止するコマンドレットは設計されています (で説明されている[最初のコマンドレットを作成](../cmdlet/creating-a-cmdlet-without-parameters.md))。</span><span class="sxs-lookup"><span data-stu-id="76a82-105">The `Stop-Process` cmdlet is designed to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](../cmdlet/creating-a-cmdlet-without-parameters.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="76a82-106">ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と .NET Framework 3.0 ランタイム コンポーネントを使用してこの停止 Proc コマンドレット (stopprocesssample04.cs) ソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="76a82-106">You can download the C# (stopprocesssample04.cs) source file for this Stop-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="76a82-107">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="76a82-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="76a82-108">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="76a82-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

[!code-csharp[StopProcessSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs#L11-L435 "StopProcessSample04.cs")]

## <a name="see-also"></a><span data-ttu-id="76a82-109">参照</span><span class="sxs-lookup"><span data-stu-id="76a82-109">See Also</span></span>

[<span data-ttu-id="76a82-110">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="76a82-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="76a82-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="76a82-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)