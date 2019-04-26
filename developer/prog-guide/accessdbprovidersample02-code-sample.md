---
title: AccessDbProviderSample02 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b89a4903-3efc-4b08-9b20-2baadf1d1b66
caps.latest.revision: 6
ms.openlocfilehash: 67a169bfac0b0fc90e6ccd276d3d3592d1b70bb0
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082032"
---
# <a name="accessdbprovidersample02-code-sample"></a><span data-ttu-id="cbe9b-102">AccessDbProviderSample02 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="cbe9b-102">AccessDbProviderSample02 Code Sample</span></span>

<span data-ttu-id="cbe9b-103">次のコードで説明されている Windows PowerShell プロバイダーの実装を示しています。 [Windows PowerShell ドライブ プロバイダーを作成する](./creating-a-windows-powershell-drive-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="cbe9b-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Drive Provider](./creating-a-windows-powershell-drive-provider.md).</span></span> <span data-ttu-id="cbe9b-104">この実装は、パスを作成し、Access データベースへの接続を確立して、ドライブを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9b-104">This implementation creates a path, makes a connection to an Access database, and then removes the drive.</span></span>

> [!NOTE]
> <span data-ttu-id="cbe9b-105">ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用して、このプロバイダーのソース ファイル (AccessDBSampleProvider02.cs)。</span><span class="sxs-lookup"><span data-stu-id="cbe9b-105">You can download the C# source file (AccessDBSampleProvider02.cs) for this provider using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="cbe9b-106">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="cbe9b-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="cbe9b-107">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="cbe9b-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>
>
> <span data-ttu-id="cbe9b-108">その他の Windows PowerShell プロバイダーの実装の詳細については、次を参照してください。 [Your Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="cbe9b-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="cbe9b-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="cbe9b-109">Code Sample</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L11-L154 "AccessDBProviderSample02.cs")]


## <a name="see-also"></a><span data-ttu-id="cbe9b-110">参照</span><span class="sxs-lookup"><span data-stu-id="cbe9b-110">See Also</span></span>

[<span data-ttu-id="cbe9b-111">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="cbe9b-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="cbe9b-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="cbe9b-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)