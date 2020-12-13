---
ms.date: 09/13/2016
ms.topic: reference
title: RunSpace03 (C#) コード サンプル
description: RunSpace03 (C#) コード サンプル
ms.openlocfilehash: cdb08811de13f8bbf5cd91fcbef552c78594b788
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653838"
---
# <a name="runspace03-c-code-sample"></a><span data-ttu-id="68aa3-103">RunSpace03 (C#) コード サンプル</span><span class="sxs-lookup"><span data-stu-id="68aa3-103">RunSpace03 (C#) Code Sample</span></span>

<span data-ttu-id="68aa3-104">次に示すのは、「指定したスクリプトを実行するコンソールアプリケーションの作成」で説明されているコンソールアプリケーションの C# ソースコードです。</span><span class="sxs-lookup"><span data-stu-id="68aa3-104">Here is the C# source code for the console application described in "Creating a Console Application That Runs a Specified Script".</span></span> <span data-ttu-id="68aa3-105">このサンプルでは、 [Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) クラスを使用して、スクリプトに渡されたプロセス名のリストを使用してプロセス情報を取得するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="68aa3-105">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that retrieves process information by using the list of process names passed into the script.</span></span> <span data-ttu-id="68aa3-106">この例では、入力オブジェクトをスクリプトに渡す方法と、エラーオブジェクトおよび出力オブジェクトを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="68aa3-106">It shows how to pass input objects to a script and how to retrieve error objects as well as the output objects.</span></span>

> [!NOTE]
> <span data-ttu-id="68aa3-107">このサンプルの C# ソースファイル (runspace03.cs) をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および Microsoft .NET Framework 3.0 Runtime Components を使用します。</span><span class="sxs-lookup"><span data-stu-id="68aa3-107">You can download the C# source file (runspace03.cs) for this sample using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="68aa3-108">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68aa3-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="68aa3-109">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="68aa3-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="68aa3-110">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="68aa3-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs" range="11-88":::

## <a name="see-also"></a><span data-ttu-id="68aa3-111">参照</span><span class="sxs-lookup"><span data-stu-id="68aa3-111">See Also</span></span>

[<span data-ttu-id="68aa3-112">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="68aa3-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="68aa3-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="68aa3-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
