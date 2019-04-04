---
title: RunSpace04 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb6fcc47-cf89-43e7-b686-3d60934ce3e7
caps.latest.revision: 6
ms.openlocfilehash: 2a3e7598c433027fdd96343829c0606fc7b1c37c
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429467"
---
# <a name="runspace04-code-samples"></a><span data-ttu-id="e7304-102">RunSpace04 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="e7304-102">RunSpace04 Code Samples</span></span>

<span data-ttu-id="e7304-103">使用する実行空間用のコード サンプルを次に示します、 [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)終了エラーを生成するスクリプトを実行するクラス。</span><span class="sxs-lookup"><span data-stu-id="e7304-103">Here is a code sample for a runspace that uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that generates a terminating error.</span></span> <span data-ttu-id="e7304-104">ホスト アプリケーションは、エラーをキャッチし、エラー レコードを解釈する責任を負います。</span><span class="sxs-lookup"><span data-stu-id="e7304-104">The host application is responsible for catching the error and interpreting the error record.</span></span>

> [!NOTE]
> <span data-ttu-id="e7304-105">Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用して、この実行空間には、VB.NET のソース ファイル (Runspace04.vb) をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="e7304-105">You can download the VB.NET source file (Runspace04.vb) for this runspace using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="e7304-106">ダウンロードの手順については、[Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7304-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="e7304-107">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="e7304-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="e7304-108">完全なサンプル コードでは、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7304-108">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="e7304-109">Language</span><span class="sxs-lookup"><span data-stu-id="e7304-109">Language</span></span>|<span data-ttu-id="e7304-110">トピック</span><span class="sxs-lookup"><span data-stu-id="e7304-110">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="e7304-111">VB.NET</span><span class="sxs-lookup"><span data-stu-id="e7304-111">VB.NET</span></span>|[<span data-ttu-id="e7304-112">Runspace01 (VB.NET) コード サンプル</span><span class="sxs-lookup"><span data-stu-id="e7304-112">Runspace01 (VB.NET) Code Sample</span></span>](./runspace01-vb-net-code-sample.md)|

## <a name="see-also"></a><span data-ttu-id="e7304-113">参照</span><span class="sxs-lookup"><span data-stu-id="e7304-113">See Also</span></span>

[<span data-ttu-id="e7304-114">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="e7304-114">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="e7304-115">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="e7304-115">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)