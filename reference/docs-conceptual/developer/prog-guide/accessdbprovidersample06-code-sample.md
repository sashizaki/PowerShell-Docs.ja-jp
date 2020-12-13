---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDbProviderSample06 コード サンプル
description: AccessDbProviderSample06 コード サンプル
ms.openlocfilehash: 401aca7fab86cfbf3fa8d671eab17412dd162a88
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647498"
---
# <a name="accessdbprovidersample06-code-sample"></a><span data-ttu-id="56178-103">AccessDbProviderSample06 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="56178-103">AccessDbProviderSample06 Code Sample</span></span>

<span data-ttu-id="56178-104">次のコードは、「 [Windows Powershell コンテンツプロバイダーの作成](./creating-a-windows-powershell-content-provider.md)」で説明されている windows powershell コンテンツプロバイダーの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="56178-104">The following code shows the implementation of the Windows PowerShell content provider described in [Creating a Windows PowerShell Content Provider](./creating-a-windows-powershell-content-provider.md).</span></span>
<span data-ttu-id="56178-105">このプロバイダーは、ユーザーがデータストア内の項目の内容を操作できるようにします。</span><span class="sxs-lookup"><span data-stu-id="56178-105">This provider enables the user to manipulate the contents of the items in a data store.</span></span>

> [!NOTE]
> <span data-ttu-id="56178-106">このプロバイダーの C# ソースファイル (AccessDBSampleProvider06.cs) をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="56178-106">You can download the C# source file (AccessDBSampleProvider06.cs) for this provider by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="56178-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56178-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="56178-108">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="56178-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span> <span data-ttu-id="56178-109">その他の Windows PowerShell プロバイダーの実装の詳細については、「 [Windows Powershell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56178-109">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="56178-110">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="56178-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="11-2399":::

## <a name="see-also"></a><span data-ttu-id="56178-111">参照</span><span class="sxs-lookup"><span data-stu-id="56178-111">See Also</span></span>

[<span data-ttu-id="56178-112">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="56178-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="56178-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="56178-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
