---
title: RunSpace05 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9688cd69-07ea-4ea0-8822-0a4850bcf86c
caps.latest.revision: 7
ms.openlocfilehash: abf19d848f6150d005c63bb0fc2ffbe1de405e2a
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734959"
---
# <a name="runspace05-code-sample"></a><span data-ttu-id="a8858-102">RunSpace05 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="a8858-102">RunSpace05 Code Sample</span></span>

<span data-ttu-id="a8858-103">説明されている Runspace05 サンプルのソース コードを次に示します[構成、実行空間を使用して RunspaceConfiguration](https://msdn.microsoft.com/en-us/42681d19-2d05-4975-befd-afb1990e79b2)します。</span><span class="sxs-lookup"><span data-stu-id="a8858-103">Here is the source code for the Runspace05 sample that is described in [Configuring a Runspace Using RunspaceConfiguration](https://msdn.microsoft.com/en-us/42681d19-2d05-4975-befd-afb1990e79b2).</span></span> <span data-ttu-id="a8858-104">このサンプルでは、実行空間の構成情報を作成、実行空間を作成、1 つのコマンドでパイプラインを作成、およびパイプラインを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a8858-104">This sample shows how to create the runspace configuration information, create a runspace, create a pipeline with a single command, and then execute the pipeline.</span></span> <span data-ttu-id="a8858-105">実行されるコマンドは、`Get-Process`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="a8858-105">The command that is executed is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="a8858-106">ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用してソース ファイル (runspace05.cs)。</span><span class="sxs-lookup"><span data-stu-id="a8858-106">You can download the C# source file (runspace05.cs) by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="a8858-107">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="a8858-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="a8858-108">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="a8858-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="a8858-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="a8858-109">Code Sample</span></span>

[!code-csharp[Runspace05.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs#L11-L86 "Runspace05.cs")]

## <a name="see-also"></a><span data-ttu-id="a8858-110">参照</span><span class="sxs-lookup"><span data-stu-id="a8858-110">See Also</span></span>

[<span data-ttu-id="a8858-111">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="a8858-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="a8858-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="a8858-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)