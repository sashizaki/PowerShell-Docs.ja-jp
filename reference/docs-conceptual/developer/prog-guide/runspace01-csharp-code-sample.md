---
title: Runspace01 (C#) コードサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 418162731b4a98989642e1c61c655fdb0f002698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787060"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="29326-102">Runspace01 (C#) コード サンプル</span><span class="sxs-lookup"><span data-stu-id="29326-102">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="29326-103">ここでは、「[指定されたコマンドを実行するコンソールアプリケーションの作成](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program)」で説明されている実行空間のコードサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="29326-103">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span></span>
<span data-ttu-id="29326-104">これを行うには、アプリケーションが実行空間を呼び出し、コマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="29326-104">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="29326-105">(このアプリケーションは実行空間の構成情報を指定せず、明示的にパイプラインを作成しないことに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="29326-105">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="29326-106">呼び出されるコマンドは、コマンド `Get-Process` レットです。</span><span class="sxs-lookup"><span data-stu-id="29326-106">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="29326-107">この実行空間の C# ソースファイル (runspace01.cs) をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および Microsoft .NET Framework 3.0 Runtime Components を使用します。</span><span class="sxs-lookup"><span data-stu-id="29326-107">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span>
> <span data-ttu-id="29326-108">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29326-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="29326-109">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="29326-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="29326-110">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="29326-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs" range="11-62":::

## <a name="see-also"></a><span data-ttu-id="29326-111">参照</span><span class="sxs-lookup"><span data-stu-id="29326-111">See Also</span></span>

[<span data-ttu-id="29326-112">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="29326-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="29326-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="29326-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
