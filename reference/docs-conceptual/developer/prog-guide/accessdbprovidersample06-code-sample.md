---
title: AccessDbProviderSample06 コードサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: baab6a56-c199-48d7-a03e-a904b1bb1baa
caps.latest.revision: 7
ms.openlocfilehash: 90927917550ade695f32c6f763f8cc4a8b347275
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366941"
---
# <a name="accessdbprovidersample06-code-sample"></a><span data-ttu-id="dca7d-102">AccessDbProviderSample06 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="dca7d-102">AccessDbProviderSample06 Code Sample</span></span>

<span data-ttu-id="dca7d-103">次のコードは、「 [Windows Powershell コンテンツプロバイダーの作成](./creating-a-windows-powershell-content-provider.md)」で説明されている windows powershell コンテンツプロバイダーの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="dca7d-103">The following code shows the implementation of the Windows PowerShell content provider described in [Creating a Windows PowerShell Content Provider](./creating-a-windows-powershell-content-provider.md).</span></span> <span data-ttu-id="dca7d-104">このプロバイダーは、ユーザーがデータストア内の項目の内容を操作できるようにします。</span><span class="sxs-lookup"><span data-stu-id="dca7d-104">This provider enables the user to manipulate the contents of the items in a data store.</span></span>

> [!NOTE]
> <span data-ttu-id="dca7d-105">このプロバイダのC#ソースファイル (AccessDBSampleProvider06.cs) をダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および Microsoft .NET Framework 3.0 Runtime Components を使用します。</span><span class="sxs-lookup"><span data-stu-id="dca7d-105">You can download the C# source file (AccessDBSampleProvider06.cs) for this provider by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="dca7d-106">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dca7d-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="dca7d-107">ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="dca7d-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>
>
> <span data-ttu-id="dca7d-108">その他の Windows PowerShell プロバイダーの実装の詳細については、「 [Windows Powershell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dca7d-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="dca7d-109">コードサンプル</span><span class="sxs-lookup"><span data-stu-id="dca7d-109">Code Sample</span></span>

[!code-csharp[AccessDBProviderSample06.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L2399 "AccessDBProviderSample06.cs")]

## <a name="see-also"></a><span data-ttu-id="dca7d-110">参照</span><span class="sxs-lookup"><span data-stu-id="dca7d-110">See Also</span></span>

[<span data-ttu-id="dca7d-111">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="dca7d-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="dca7d-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="dca7d-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)