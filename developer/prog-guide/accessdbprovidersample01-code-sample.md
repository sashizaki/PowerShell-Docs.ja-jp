---
title: AccessDbProviderSample01 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35540d2a-c18f-4179-b869-1a3dc5a8c1bd
caps.latest.revision: 6
ms.openlocfilehash: 01b95e18794501c2aff13d1e51b7400ae6fb8730
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081990"
---
# <a name="accessdbprovidersample01-code-sample"></a><span data-ttu-id="520c6-102">AccessDbProviderSample01 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="520c6-102">AccessDbProviderSample01 Code Sample</span></span>

<span data-ttu-id="520c6-103">次のコードで説明されている Windows PowerShell プロバイダーの実装を示しています。[基本的な Windows PowerShell プロバイダーを作成する](./creating-a-basic-windows-powershell-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="520c6-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span> <span data-ttu-id="520c6-104">この実装は、の開始と停止、プロバイダーのメソッドを提供し、これは、データ ストアにアクセスするか、取得またはデータ ストアにデータを設定する手段を提供するものではありません、すべてのプロバイダーで必要とされる基本的な機能は提供します。</span><span class="sxs-lookup"><span data-stu-id="520c6-104">This implementation provides methods for starting and stopping the provider, and although it does not provide a means to access a data store or to get or set the data in the data store, it does provide the basic functionality that is required by all providers.</span></span>

> [!NOTE]
> <span data-ttu-id="520c6-105">ダウンロードすることができます、 C# Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用して、このプロバイダーのソース ファイル (AccessDBSampleProvider01.cs)。</span><span class="sxs-lookup"><span data-stu-id="520c6-105">You can download the C# source file (AccessDBSampleProvider01.cs) for this provider by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="520c6-106">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="520c6-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="520c6-107">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="520c6-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>
>
> <span data-ttu-id="520c6-108">その他の Windows PowerShell プロバイダーの実装の詳細については、次を参照してください。 [Your Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="520c6-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="520c6-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="520c6-109">Code Sample</span></span>

[!code-csharp[AccessDBProviderSample01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs#L11-L30 "AccessDBProviderSample01.cs")]

## <a name="see-also"></a><span data-ttu-id="520c6-110">参照</span><span class="sxs-lookup"><span data-stu-id="520c6-110">See Also</span></span>

[<span data-ttu-id="520c6-111">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="520c6-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="520c6-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="520c6-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)