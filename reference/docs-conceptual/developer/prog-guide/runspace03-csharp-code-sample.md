---
title: RunSpace03 (C#) コードサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ac8ab99-1856-4d6f-b30d-c0a18b8dd1fc
caps.latest.revision: 6
ms.openlocfilehash: 49911f2779110c04c0e89f09fdf76ee9cd930edb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360211"
---
# <a name="runspace03-c-code-sample"></a><span data-ttu-id="cb886-102">RunSpace03 (C#) コード サンプル</span><span class="sxs-lookup"><span data-stu-id="cb886-102">RunSpace03 (C#) Code Sample</span></span>

<span data-ttu-id="cb886-103">「指定さC#れたスクリプトを実行するコンソールアプリケーションの作成」で説明されているコンソールアプリケーションのソースコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="cb886-103">Here is the C# source code for the console application described in "Creating a Console Application That Runs a Specified Script".</span></span> <span data-ttu-id="cb886-104">このサンプルでは、 [Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)クラスを使用して、スクリプトに渡されたプロセス名のリストを使用してプロセス情報を取得するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="cb886-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that retrieves process information by using the list of process names passed into the script.</span></span> <span data-ttu-id="cb886-105">この例では、入力オブジェクトをスクリプトに渡す方法と、エラーオブジェクトおよび出力オブジェクトを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cb886-105">It shows how to pass input objects to a script and how to retrieve error objects as well as the output objects.</span></span>

> [!NOTE]
> <span data-ttu-id="cb886-106">このサンプルのC#ソースファイル (runspace03.cs) をダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および Microsoft .NET Framework 3.0 Runtime Components を使用します。</span><span class="sxs-lookup"><span data-stu-id="cb886-106">You can download the C# source file (runspace03.cs) for this sample using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="cb886-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb886-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="cb886-108">ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="cb886-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="cb886-109">コードサンプル</span><span class="sxs-lookup"><span data-stu-id="cb886-109">Code Sample</span></span>

[!code-csharp[Runspace03.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs#L11-L88 "Runspace03.cs")]

## <a name="see-also"></a><span data-ttu-id="cb886-110">参照</span><span class="sxs-lookup"><span data-stu-id="cb886-110">See Also</span></span>

[<span data-ttu-id="cb886-111">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="cb886-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="cb886-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="cb886-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)