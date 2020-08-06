---
title: StopProcessSample04 (C#) サンプルコード |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f7ee58ee8faa95bbd0d3ca2f01fd8e340e08beb6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786970"
---
# <a name="stopprocesssample04-c-sample-code"></a><span data-ttu-id="3bfce-102">StopProcessSample04 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="3bfce-102">StopProcessSample04 (C#) Sample Code</span></span>

<span data-ttu-id="3bfce-103">StopProc04 sample コマンドレットの完全な C# サンプルコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="3bfce-103">Here is the complete C# sample code for the StopProc04 sample cmdlet.</span></span> <span data-ttu-id="3bfce-104">これは、 `Stop-Process` 「[コマンドレットにパラメーターセットを追加する](../cmdlet/adding-parameter-sets-to-a-cmdlet.md)」で説明されているコマンドレットのコードです。</span><span class="sxs-lookup"><span data-stu-id="3bfce-104">This is the code for the `Stop-Process` cmdlet described in [Adding Parameter Sets to a Cmdlet](../cmdlet/adding-parameter-sets-to-a-cmdlet.md).</span></span> <span data-ttu-id="3bfce-105">`Stop-Process`コマンドレットは、Get Proc コマンドレットを使用して取得したプロセスを停止するように設計されています (「[最初のコマンドレットを作成](../cmdlet/creating-a-cmdlet-without-parameters.md)する」を参照)。</span><span class="sxs-lookup"><span data-stu-id="3bfce-105">The `Stop-Process` cmdlet is designed to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](../cmdlet/creating-a-cmdlet-without-parameters.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="3bfce-106">この Stop Proc コマンドレットの C# (stopprocesssample04.cs) ソースファイルをダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="3bfce-106">You can download the C# (stopprocesssample04.cs) source file for this Stop-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="3bfce-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bfce-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="3bfce-108">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="3bfce-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs" range="11-435":::

## <a name="see-also"></a><span data-ttu-id="3bfce-109">参照</span><span class="sxs-lookup"><span data-stu-id="3bfce-109">See Also</span></span>

[<span data-ttu-id="3bfce-110">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="3bfce-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="3bfce-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="3bfce-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
