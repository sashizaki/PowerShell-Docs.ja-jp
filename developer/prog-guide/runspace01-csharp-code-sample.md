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
ms.openlocfilehash: 59320365c4a35c3d71af10273eb21b1ce01e5c0c
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429705"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="1700c-102">Runspace01 (C#) コード サンプル</span><span class="sxs-lookup"><span data-stu-id="1700c-102">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="1700c-103">記載されている、実行空間のサンプル コードをここでは[コンソール アプリケーションを実行に指定されたコマンドを作成する](http://msdn.microsoft.com/en-us/793a6570-a072-4799-840b-172f28ce620e)します。</span><span class="sxs-lookup"><span data-stu-id="1700c-103">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](http://msdn.microsoft.com/en-us/793a6570-a072-4799-840b-172f28ce620e).</span></span> <span data-ttu-id="1700c-104">これを行うには、アプリケーションは、実行空間を指定するには、呼び出しをコマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1700c-104">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="1700c-105">(このアプリケーションは、実行空間の構成情報を指定しないもないは、明示的にパイプラインを作成することに注意してください。)</span><span class="sxs-lookup"><span data-stu-id="1700c-105">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="1700c-106">呼び出されるコマンドは、`Get-Process`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="1700c-106">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="1700c-107">ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用して、この実行空間のソース ファイル (runspace01.cs)。</span><span class="sxs-lookup"><span data-stu-id="1700c-107">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="1700c-108">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="1700c-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="1700c-109">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="1700c-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="1700c-110">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="1700c-110">Code Sample</span></span>

[!code-csharp[Runspace01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs#L11-L62 "Runspace01.cs")]

## <a name="see-also"></a><span data-ttu-id="1700c-111">参照</span><span class="sxs-lookup"><span data-stu-id="1700c-111">See Also</span></span>

[<span data-ttu-id="1700c-112">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="1700c-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="1700c-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="1700c-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)