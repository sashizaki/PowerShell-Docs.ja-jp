---
ms.date: 09/13/2016
ms.topic: reference
title: RunSpace10 コード サンプル
description: RunSpace10 コード サンプル
ms.openlocfilehash: d9219ca29ec85b8dd2af19c9eba3ddb49050c25c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659135"
---
# <a name="runspace10-code-sample"></a><span data-ttu-id="86fe8-103">RunSpace10 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="86fe8-103">RunSpace10 Code Sample</span></span>

<span data-ttu-id="86fe8-104">Runspace10 サンプルのソースコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="86fe8-104">Here is the source code for the Runspace10 sample.</span></span> <span data-ttu-id="86fe8-105">このサンプルアプリケーションでは、 [Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) にコマンドレットを追加し、変更された構成情報を使用して実行空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="86fe8-105">This sample application adds a cmdlet to [System.Management.Automation.Runspaces.Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) and then uses the modified configuration information to create the runspace.</span></span>

> [!NOTE]
> <span data-ttu-id="86fe8-106">C# ソースファイル (runspace10.cs) は、windows Vista 用 Windows ソフトウェア開発キットおよび Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用してダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="86fe8-106">You can download the C# source file (runspace10.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="86fe8-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86fe8-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="86fe8-108">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="86fe8-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="86fe8-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="86fe8-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace10/Runspace10.cs" range="11-118":::

## <a name="see-also"></a><span data-ttu-id="86fe8-110">参照</span><span class="sxs-lookup"><span data-stu-id="86fe8-110">See Also</span></span>

[<span data-ttu-id="86fe8-111">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="86fe8-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="86fe8-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="86fe8-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
