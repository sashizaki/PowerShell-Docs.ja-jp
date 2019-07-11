---
title: Runspace01 (C#) コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d59f8b7c-e800-4633-aa5b-74d4c57e2706
caps.latest.revision: 6
ms.openlocfilehash: ab067485d70523a16493eb57170615ab300eaa98
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67735057"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="62147-102">Runspace01 (C#) コード サンプル</span><span class="sxs-lookup"><span data-stu-id="62147-102">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="62147-103">記載されている、実行空間のサンプル コードをここでは[コンソール アプリケーションを実行に指定されたコマンドを作成する](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program)します。</span><span class="sxs-lookup"><span data-stu-id="62147-103">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span></span> <span data-ttu-id="62147-104">これを行うには、アプリケーションは、実行空間を指定するには、呼び出しをコマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="62147-104">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="62147-105">(このアプリケーションは、実行空間の構成情報を指定しないもないは、明示的にパイプラインを作成することに注意してください。)</span><span class="sxs-lookup"><span data-stu-id="62147-105">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="62147-106">呼び出されるコマンドは、`Get-Process`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="62147-106">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="62147-107">ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用して、この実行空間のソース ファイル (runspace01.cs)。</span><span class="sxs-lookup"><span data-stu-id="62147-107">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="62147-108">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="62147-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="62147-109">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="62147-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="62147-110">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="62147-110">Code Sample</span></span>

[!code-csharp[Runspace01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs#L11-L62 "Runspace01.cs")]

## <a name="see-also"></a><span data-ttu-id="62147-111">参照</span><span class="sxs-lookup"><span data-stu-id="62147-111">See Also</span></span>

[<span data-ttu-id="62147-112">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="62147-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="62147-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="62147-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)