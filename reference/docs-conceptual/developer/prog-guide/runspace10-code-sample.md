---
title: RunSpace10 コードサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 976df6c36a5f95d17a76dcd31d287a3f064eff24
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784658"
---
# <a name="runspace10-code-sample"></a><span data-ttu-id="c44b1-102">RunSpace10 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="c44b1-102">RunSpace10 Code Sample</span></span>

<span data-ttu-id="c44b1-103">Runspace10 サンプルのソースコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c44b1-103">Here is the source code for the Runspace10 sample.</span></span> <span data-ttu-id="c44b1-104">このサンプルアプリケーションでは、 [Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration)にコマンドレットを追加し、変更された構成情報を使用して実行空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="c44b1-104">This sample application adds a cmdlet to [System.Management.Automation.Runspaces.Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) and then uses the modified configuration information to create the runspace.</span></span>

> [!NOTE]
> <span data-ttu-id="c44b1-105">C# ソースファイル (runspace10.cs) は、windows Vista 用 Windows ソフトウェア開発キットおよび Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用してダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="c44b1-105">You can download the C# source file (runspace10.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="c44b1-106">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c44b1-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="c44b1-107">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="c44b1-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="c44b1-108">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="c44b1-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace10/Runspace10.cs" range="11-118":::

## <a name="see-also"></a><span data-ttu-id="c44b1-109">参照</span><span class="sxs-lookup"><span data-stu-id="c44b1-109">See Also</span></span>

[<span data-ttu-id="c44b1-110">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="c44b1-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="c44b1-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="c44b1-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
