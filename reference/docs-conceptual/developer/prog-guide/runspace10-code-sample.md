---
title: RunSpace10 コードサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5337dc40-c56e-458b-aedc-5f5d401dfd28
caps.latest.revision: 6
ms.openlocfilehash: da8455a72f6a50b8ab17650541cde8cc9c98a8fd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366471"
---
# <a name="runspace10-code-sample"></a><span data-ttu-id="8a87e-102">RunSpace10 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="8a87e-102">RunSpace10 Code Sample</span></span>

<span data-ttu-id="8a87e-103">Runspace10 サンプルのソースコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="8a87e-103">Here is the source code for the Runspace10 sample.</span></span> <span data-ttu-id="8a87e-104">このサンプルアプリケーションでは、 [Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration)にコマンドレットを追加し、変更された構成情報を使用して実行空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="8a87e-104">This sample application adds a cmdlet to [System.Management.Automation.Runspaces.Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) and then uses the modified configuration information to create the runspace.</span></span>

> [!NOTE]
> <span data-ttu-id="8a87e-105">C#ソースファイル (runspace10.cs) は、windows Vista 用 Windows ソフトウェア開発キットおよび Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用してダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="8a87e-105">You can download the C# source file (runspace10.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="8a87e-106">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a87e-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="8a87e-107">ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="8a87e-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="8a87e-108">コードサンプル</span><span class="sxs-lookup"><span data-stu-id="8a87e-108">Code Sample</span></span>

[!code-csharp[Runspace10.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace10/Runspace10.cs#L11-L118 "Runspace10.cs")]

## <a name="see-also"></a><span data-ttu-id="8a87e-109">参照</span><span class="sxs-lookup"><span data-stu-id="8a87e-109">See Also</span></span>

[<span data-ttu-id="8a87e-110">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="8a87e-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="8a87e-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="8a87e-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)