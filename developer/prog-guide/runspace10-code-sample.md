---
title: RunSpace10 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5337dc40-c56e-458b-aedc-5f5d401dfd28
caps.latest.revision: 6
ms.openlocfilehash: 95b25746a8e99deb871905734700aba51cd7765e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854608"
---
# <a name="runspace10-code-sample"></a><span data-ttu-id="41f9b-102">RunSpace10 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="41f9b-102">RunSpace10 Code Sample</span></span>

<span data-ttu-id="41f9b-103">Runspace10 サンプルのソース コードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="41f9b-103">Here is the source code for the Runspace10 sample.</span></span> <span data-ttu-id="41f9b-104">このサンプル アプリケーションに追加するコマンドレット[System.Management.Automation.Runspaces.Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration)し、変更された構成情報を使用して、実行空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="41f9b-104">This sample application adds a cmdlet to [System.Management.Automation.Runspaces.Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) and then uses the modified configuration information to create the runspace.</span></span>

> [!NOTE]
> <span data-ttu-id="41f9b-105">ダウンロードすることができます、 C# Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用してソース ファイル (runspace10.cs)。</span><span class="sxs-lookup"><span data-stu-id="41f9b-105">You can download the C# source file (runspace10.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="41f9b-106">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="41f9b-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="41f9b-107">ダウンロードすることができます、 C# Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用してソース ファイル (runspace10.cs)。</span><span class="sxs-lookup"><span data-stu-id="41f9b-107">You can download the C# source file (runspace10.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="41f9b-108">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="41f9b-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="41f9b-109">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="41f9b-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="41f9b-110">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="41f9b-110">Code Sample</span></span>

[!code-csharp[Runspace10.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace10/Runspace10.cs#L11-L118 "Runspace10.cs")]

## <a name="see-also"></a><span data-ttu-id="41f9b-111">参照</span><span class="sxs-lookup"><span data-stu-id="41f9b-111">See Also</span></span>

[<span data-ttu-id="41f9b-112">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="41f9b-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="41f9b-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="41f9b-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)