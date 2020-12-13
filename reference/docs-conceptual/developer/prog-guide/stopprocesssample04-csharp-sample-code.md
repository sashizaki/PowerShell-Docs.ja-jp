---
ms.date: 09/13/2016
ms.topic: reference
title: StopProcessSample04 (C#) サンプル コード
description: StopProcessSample04 (C#) サンプル コード
ms.openlocfilehash: ecb3c5b8226a1a9a75b93d215e0579a155fe3662
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667455"
---
# <a name="stopprocesssample04-c-sample-code"></a><span data-ttu-id="d25c9-103">StopProcessSample04 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="d25c9-103">StopProcessSample04 (C#) Sample Code</span></span>

<span data-ttu-id="d25c9-104">StopProc04 sample コマンドレットの完全な C# サンプルコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d25c9-104">Here is the complete C# sample code for the StopProc04 sample cmdlet.</span></span> <span data-ttu-id="d25c9-105">これは、 `Stop-Process` 「 [コマンドレットにパラメーターセットを追加する](../cmdlet/adding-parameter-sets-to-a-cmdlet.md)」で説明されているコマンドレットのコードです。</span><span class="sxs-lookup"><span data-stu-id="d25c9-105">This is the code for the `Stop-Process` cmdlet described in [Adding Parameter Sets to a Cmdlet](../cmdlet/adding-parameter-sets-to-a-cmdlet.md).</span></span> <span data-ttu-id="d25c9-106">`Stop-Process`コマンドレットは、Get-Proc コマンドレットを使用して取得されたプロセスを停止するように設計されています ([最初のコマンドレットの作成](../cmdlet/creating-a-cmdlet-without-parameters.md)に関するページを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="d25c9-106">The `Stop-Process` cmdlet is designed to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](../cmdlet/creating-a-cmdlet-without-parameters.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="d25c9-107">この Stop-Proc コマンドレットの C# (stopprocesssample04.cs) ソースファイルをダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="d25c9-107">You can download the C# (stopprocesssample04.cs) source file for this Stop-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="d25c9-108">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d25c9-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="d25c9-109">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="d25c9-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs" range="11-435":::

## <a name="see-also"></a><span data-ttu-id="d25c9-110">参照</span><span class="sxs-lookup"><span data-stu-id="d25c9-110">See Also</span></span>

[<span data-ttu-id="d25c9-111">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="d25c9-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="d25c9-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="d25c9-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
