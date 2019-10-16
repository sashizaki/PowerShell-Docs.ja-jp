---
title: RunSpace04 のコードサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb6fcc47-cf89-43e7-b686-3d60934ce3e7
caps.latest.revision: 6
ms.openlocfilehash: 2a3e7598c433027fdd96343829c0606fc7b1c37c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360161"
---
# <a name="runspace04-code-samples"></a><span data-ttu-id="541a1-102">RunSpace04 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="541a1-102">RunSpace04 Code Samples</span></span>

<span data-ttu-id="541a1-103">次に示すのは、 [Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)クラスを使用して、終了エラーを生成するスクリプトを実行する実行空間のコードサンプルです。</span><span class="sxs-lookup"><span data-stu-id="541a1-103">Here is a code sample for a runspace that uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that generates a terminating error.</span></span> <span data-ttu-id="541a1-104">ホストアプリケーションは、エラーをキャッチし、エラーレコードを解釈します。</span><span class="sxs-lookup"><span data-stu-id="541a1-104">The host application is responsible for catching the error and interpreting the error record.</span></span>

> [!NOTE]
> <span data-ttu-id="541a1-105">この実行空間の VB.NET ソースファイル (Runspace04) は、windows Vista 用 Windows ソフトウェア開発キットおよび Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用してダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="541a1-105">You can download the VB.NET source file (Runspace04.vb) for this runspace using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="541a1-106">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="541a1-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="541a1-107">ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="541a1-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="541a1-108">完全なサンプルコードについては、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="541a1-108">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="541a1-109">Language</span><span class="sxs-lookup"><span data-stu-id="541a1-109">Language</span></span>|<span data-ttu-id="541a1-110">トピック</span><span class="sxs-lookup"><span data-stu-id="541a1-110">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="541a1-111">VB.NET</span><span class="sxs-lookup"><span data-stu-id="541a1-111">VB.NET</span></span>|[<span data-ttu-id="541a1-112">Runspace01 (VB.NET) コードサンプル</span><span class="sxs-lookup"><span data-stu-id="541a1-112">Runspace01 (VB.NET) Code Sample</span></span>](./runspace01-vb-net-code-sample.md)|

## <a name="see-also"></a><span data-ttu-id="541a1-113">参照</span><span class="sxs-lookup"><span data-stu-id="541a1-113">See Also</span></span>

[<span data-ttu-id="541a1-114">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="541a1-114">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="541a1-115">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="541a1-115">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)