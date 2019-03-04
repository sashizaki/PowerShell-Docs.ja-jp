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
ms.openlocfilehash: 2f1839d1ba578cdfe97f60c741c84b0a57f1d8f6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854218"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="de9d7-102">Runspace01 (C#) コード サンプル</span><span class="sxs-lookup"><span data-stu-id="de9d7-102">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="de9d7-103">記載されている、実行空間のサンプル コードをここでは[コンソール アプリケーションを実行に指定されたコマンドを作成する](http://msdn.microsoft.com/en-us/793a6570-a072-4799-840b-172f28ce620e)します。</span><span class="sxs-lookup"><span data-stu-id="de9d7-103">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](http://msdn.microsoft.com/en-us/793a6570-a072-4799-840b-172f28ce620e).</span></span> <span data-ttu-id="de9d7-104">これを行うには、アプリケーションは、実行空間を指定するには、呼び出しをコマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="de9d7-104">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="de9d7-105">(このアプリケーションは、実行空間の構成情報を指定しないもないは、明示的にパイプラインを作成することに注意してください。)</span><span class="sxs-lookup"><span data-stu-id="de9d7-105">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="de9d7-106">呼び出されるコマンドは、`Get-Process`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="de9d7-106">The command that is invoked is the `Get-Process` cmdlet.</span></span>
<span data-ttu-id="de9d7-107">記載されている、実行空間のサンプル コードをここでは[コンソール アプリケーションを実行に指定されたコマンドを作成する](http://msdn.microsoft.com/en-us/793a6570-a072-4799-840b-172f28ce620e)します。</span><span class="sxs-lookup"><span data-stu-id="de9d7-107">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](http://msdn.microsoft.com/en-us/793a6570-a072-4799-840b-172f28ce620e).</span></span> <span data-ttu-id="de9d7-108">これを行うには、アプリケーションは、実行空間を指定するには、呼び出しをコマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="de9d7-108">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="de9d7-109">(このアプリケーションは、実行空間の構成情報を指定しないもないは、明示的にパイプラインを作成することに注意してください。)</span><span class="sxs-lookup"><span data-stu-id="de9d7-109">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="de9d7-110">呼び出されるコマンドは、`Get-Process`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="de9d7-110">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="de9d7-111">ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用して、この実行空間のソース ファイル (runspace01.cs)。</span><span class="sxs-lookup"><span data-stu-id="de9d7-111">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="de9d7-112">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="de9d7-112">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="de9d7-113">ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用して、この実行空間のソース ファイル (runspace01.cs)。</span><span class="sxs-lookup"><span data-stu-id="de9d7-113">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="de9d7-114">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="de9d7-114">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="de9d7-115">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="de9d7-115">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="de9d7-116">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="de9d7-116">Code Sample</span></span>

[!code-csharp[Runspace01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs#L11-L62 "Runspace01.cs")]

## <a name="see-also"></a><span data-ttu-id="de9d7-117">参照</span><span class="sxs-lookup"><span data-stu-id="de9d7-117">See Also</span></span>

[<span data-ttu-id="de9d7-118">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="de9d7-118">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="de9d7-119">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="de9d7-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)