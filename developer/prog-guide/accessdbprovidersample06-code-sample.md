---
title: AccessDbProviderSample06 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: baab6a56-c199-48d7-a03e-a904b1bb1baa
caps.latest.revision: 7
ms.openlocfilehash: 6e86318573df92b9ec84056631843e0efa096a3b
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57795608"
---
# <a name="accessdbprovidersample06-code-sample"></a><span data-ttu-id="14c31-102">AccessDbProviderSample06 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="14c31-102">AccessDbProviderSample06 Code Sample</span></span>

<span data-ttu-id="14c31-103">次のコードは、コンテンツ プロバイダーで説明されている Windows PowerShell の実装を示しています。 [Windows PowerShell コンテンツ プロバイダーを作成する](./creating-a-windows-powershell-content-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="14c31-103">The following code shows the implementation of the Windows PowerShell content provider described in [Creating a Windows PowerShell Content Provider](./creating-a-windows-powershell-content-provider.md).</span></span> <span data-ttu-id="14c31-104">このプロバイダーには、データ ストア内の項目の内容を操作するユーザーができるようにします。</span><span class="sxs-lookup"><span data-stu-id="14c31-104">This provider enables the user to manipulate the contents of the items in a data store.</span></span>

> [!NOTE]
> <span data-ttu-id="14c31-105">ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用して、このプロバイダーのソース ファイル (AccessDBSampleProvider06.cs)。</span><span class="sxs-lookup"><span data-stu-id="14c31-105">You can download the C# source file (AccessDBSampleProvider06.cs) for this provider by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="14c31-106">ダウンロードの手順については、[Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14c31-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="14c31-107">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="14c31-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>
>
> <span data-ttu-id="14c31-108">その他の Windows PowerShell プロバイダーの実装の詳細については、[Your Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14c31-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="14c31-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="14c31-109">Code Sample</span></span>

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L2399 "AccessDBProviderSample06.cs")]

## <a name="see-also"></a><span data-ttu-id="14c31-110">参照</span><span class="sxs-lookup"><span data-stu-id="14c31-110">See Also</span></span>

[<span data-ttu-id="14c31-111">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="14c31-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="14c31-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="14c31-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)