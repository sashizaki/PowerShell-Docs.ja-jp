---
title: RunSpace07 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ad306d9-45c2-4d55-8e64-fdcba43402c5
caps.latest.revision: 6
ms.openlocfilehash: 064e7d7ea2ee173bbcdd75a9f3a6c12582afe17b
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429642"
---
# <a name="runspace07-code-sample"></a><span data-ttu-id="8c51f-102">RunSpace07 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="8c51f-102">RunSpace07 Code Sample</span></span>

<span data-ttu-id="8c51f-103">記載されている Runspace07 サンプルのソース コードを次に示します[コマンドの作成、コンソール アプリケーションを追加しますパイプラインに](http://msdn.microsoft.com/en-us/01eb7808-e97b-4905-80be-9e2fa38c262e)します。</span><span class="sxs-lookup"><span data-stu-id="8c51f-103">Here is the source code for the Runspace07 sample described in [Creating a Console Application That Adds Commands to a Pipeline](http://msdn.microsoft.com/en-us/01eb7808-e97b-4905-80be-9e2fa38c262e).</span></span> <span data-ttu-id="8c51f-104">このサンプル アプリケーションを実行空間を作成、パイプラインを作成しますをパイプラインに 2 つのコマンドを追加しますし、パイプラインを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c51f-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, and then executes the pipeline.</span></span> <span data-ttu-id="8c51f-105">パイプラインに追加のコマンドは、`Get-Process`と`Measure-Object`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="8c51f-105">The commands added to the pipeline are the `Get-Process` and `Measure-Object` cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="8c51f-106">ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用してソース ファイル (runspace07.cs)。</span><span class="sxs-lookup"><span data-stu-id="8c51f-106">You can download the C# source file (runspace07.cs) using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="8c51f-107">ダウンロードの手順については、[Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c51f-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="8c51f-108">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="8c51f-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="8c51f-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="8c51f-109">Code Sample</span></span>

[!code-csharp[Runspace07.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs#L11-L108 "Runspace07.cs")]

## <a name="see-also"></a><span data-ttu-id="8c51f-110">参照</span><span class="sxs-lookup"><span data-stu-id="8c51f-110">See Also</span></span>

[<span data-ttu-id="8c51f-111">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="8c51f-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="8c51f-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="8c51f-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)