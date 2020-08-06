---
title: AccessDbProviderSample01 コードサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 2e9f81b3011ea1b27bafd9e02ea7e0faf7903a62
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784828"
---
# <a name="accessdbprovidersample01-code-sample"></a><span data-ttu-id="9b1cc-102">AccessDbProviderSample01 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="9b1cc-102">AccessDbProviderSample01 Code Sample</span></span>

<span data-ttu-id="9b1cc-103">次のコードは、「[基本的な Windows Powershell プロバイダーの作成](./creating-a-basic-windows-powershell-provider.md)」で説明されている windows powershell プロバイダーの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="9b1cc-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span>
<span data-ttu-id="9b1cc-104">この実装には、プロバイダーを起動および停止するためのメソッドが用意されています。また、データストアにアクセスしたり、データストア内のデータを取得または設定したりするための手段は提供されませんが、すべてのプロバイダーが必要とする基本的な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="9b1cc-104">This implementation provides methods for starting and stopping the provider, and although it does not provide a means to access a data store or to get or set the data in the data store, it does provide the basic functionality that is required by all providers.</span></span>

> [!NOTE]
> <span data-ttu-id="9b1cc-105">このプロバイダーの C# ソースファイル (AccessDBSampleProvider01.cs) は、windows Vista 用 Windows ソフトウェア開発キットおよび Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用してダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="9b1cc-105">You can download the C# source file (AccessDBSampleProvider01.cs) for this provider by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="9b1cc-106">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b1cc-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="9b1cc-107">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="9b1cc-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span> <span data-ttu-id="9b1cc-108">その他の Windows PowerShell プロバイダーの実装の詳細については、「 [Windows Powershell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b1cc-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="9b1cc-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="9b1cc-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="11-30":::

## <a name="see-also"></a><span data-ttu-id="9b1cc-110">参照</span><span class="sxs-lookup"><span data-stu-id="9b1cc-110">See Also</span></span>

[<span data-ttu-id="9b1cc-111">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="9b1cc-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="9b1cc-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="9b1cc-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
