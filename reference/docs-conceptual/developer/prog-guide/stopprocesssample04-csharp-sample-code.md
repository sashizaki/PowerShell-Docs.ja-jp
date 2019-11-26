---
title: StopProcessSample04 (C#) Sample Code |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 778ce1a2-e16d-4af5-b15b-77ca4326bdc4
caps.latest.revision: 5
ms.openlocfilehash: df5591e351790d18bf2a5b5554d792ab8175dcc6
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74416046"
---
# <a name="stopprocesssample04-c-sample-code"></a><span data-ttu-id="71686-102">StopProcessSample04 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="71686-102">StopProcessSample04 (C#) Sample Code</span></span>

<span data-ttu-id="71686-103">StopProc04 sample コマンドレットC#の完全なサンプルコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="71686-103">Here is the complete C# sample code for the StopProc04 sample cmdlet.</span></span> <span data-ttu-id="71686-104">これは、「[コマンドレットにパラメーターセットを追加する](../cmdlet/adding-parameter-sets-to-a-cmdlet.md)」で説明されている `Stop-Process` コマンドレットのコードです。</span><span class="sxs-lookup"><span data-stu-id="71686-104">This is the code for the `Stop-Process` cmdlet described in [Adding Parameter Sets to a Cmdlet](../cmdlet/adding-parameter-sets-to-a-cmdlet.md).</span></span> <span data-ttu-id="71686-105">`Stop-Process` コマンドレットは、Get Proc コマンドレットを使用して取得されたプロセスを停止するように設計されています ([最初のコマンドレットの作成](../cmdlet/creating-a-cmdlet-without-parameters.md)に関するページを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="71686-105">The `Stop-Process` cmdlet is designed to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](../cmdlet/creating-a-cmdlet-without-parameters.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="71686-106">この Stop Proc コマンドC#レットの (stopprocesssample04.cs) ソースファイルをダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="71686-106">You can download the C# (stopprocesssample04.cs) source file for this Stop-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="71686-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71686-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="71686-108">ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="71686-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

[!code-csharp[StopProcessSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs#L11-L435 "StopProcessSample04.cs")]

## <a name="see-also"></a><span data-ttu-id="71686-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="71686-109">See Also</span></span>

[<span data-ttu-id="71686-110">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="71686-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="71686-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="71686-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
