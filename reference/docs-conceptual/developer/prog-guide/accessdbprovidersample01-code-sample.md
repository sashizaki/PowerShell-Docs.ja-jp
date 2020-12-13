---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDbProviderSample01 コード サンプル
description: AccessDbProviderSample01 コード サンプル
ms.openlocfilehash: 5be593b9e86347b2f55de156fe4d9b44cfab5b78
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659421"
---
# <a name="accessdbprovidersample01-code-sample"></a><span data-ttu-id="481b3-103">AccessDbProviderSample01 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="481b3-103">AccessDbProviderSample01 Code Sample</span></span>

<span data-ttu-id="481b3-104">次のコードは、「 [基本的な Windows Powershell プロバイダーの作成](./creating-a-basic-windows-powershell-provider.md)」で説明されている windows powershell プロバイダーの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="481b3-104">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span>
<span data-ttu-id="481b3-105">この実装には、プロバイダーを起動および停止するためのメソッドが用意されています。また、データストアにアクセスしたり、データストア内のデータを取得または設定したりするための手段は提供されませんが、すべてのプロバイダーが必要とする基本的な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="481b3-105">This implementation provides methods for starting and stopping the provider, and although it does not provide a means to access a data store or to get or set the data in the data store, it does provide the basic functionality that is required by all providers.</span></span>

> [!NOTE]
> <span data-ttu-id="481b3-106">このプロバイダーの C# ソースファイル (AccessDBSampleProvider01.cs) は、windows Vista 用 Windows ソフトウェア開発キットおよび Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用してダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="481b3-106">You can download the C# source file (AccessDBSampleProvider01.cs) for this provider by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="481b3-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="481b3-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="481b3-108">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="481b3-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span> <span data-ttu-id="481b3-109">その他の Windows PowerShell プロバイダーの実装の詳細については、「 [Windows Powershell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="481b3-109">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="481b3-110">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="481b3-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="11-30":::

## <a name="see-also"></a><span data-ttu-id="481b3-111">参照</span><span class="sxs-lookup"><span data-stu-id="481b3-111">See Also</span></span>

[<span data-ttu-id="481b3-112">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="481b3-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="481b3-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="481b3-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
