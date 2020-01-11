---
title: RunSpace05 コードサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9688cd69-07ea-4ea0-8822-0a4850bcf86c
caps.latest.revision: 7
ms.openlocfilehash: 8802e308712be93992ead5ef77b97d8c21b137f7
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870644"
---
# <a name="runspace05-code-sample"></a><span data-ttu-id="85f31-102">RunSpace05 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="85f31-102">RunSpace05 Code Sample</span></span>

<span data-ttu-id="85f31-103">「 [RunspaceConfiguration を使用した実行空間の構成](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2)」で説明されている Runspace05 サンプルのソースコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="85f31-103">Here is the source code for the Runspace05 sample that is described in [Configuring a Runspace Using RunspaceConfiguration](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2).</span></span>
<span data-ttu-id="85f31-104">このサンプルでは、実行空間の構成情報を作成する方法、実行空間を作成する方法、1つのコマンドを使用してパイプラインを作成する方法、パイプラインを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="85f31-104">This sample shows how to create the runspace configuration information, create a runspace, create a pipeline with a single command, and then execute the pipeline.</span></span> <span data-ttu-id="85f31-105">実行されるコマンドは、`Get-Process` コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="85f31-105">The command that is executed is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="85f31-106">C#ソースファイル (runspace05.cs) をダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="85f31-106">You can download the C# source file (runspace05.cs) by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="85f31-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85f31-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="85f31-108">ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="85f31-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="85f31-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="85f31-109">Code Sample</span></span>

[!code-csharp[Runspace05.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs#L11-L86 "Runspace05.cs")]

## <a name="see-also"></a><span data-ttu-id="85f31-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="85f31-110">See Also</span></span>

[<span data-ttu-id="85f31-111">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="85f31-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="85f31-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="85f31-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
