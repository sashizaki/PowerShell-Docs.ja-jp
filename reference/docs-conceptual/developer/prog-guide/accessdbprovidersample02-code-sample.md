---
title: AccessDbProviderSample02 コードサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: ca7674ba5cff601394af4df20f0dda8794c14d22
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784811"
---
# <a name="accessdbprovidersample02-code-sample"></a><span data-ttu-id="15318-102">AccessDbProviderSample02 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="15318-102">AccessDbProviderSample02 Code Sample</span></span>

<span data-ttu-id="15318-103">次のコードは、「 [Windows Powershell ドライブプロバイダーの作成](./creating-a-windows-powershell-drive-provider.md)」で説明されている windows powershell プロバイダーの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="15318-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Drive Provider](./creating-a-windows-powershell-drive-provider.md).</span></span>
<span data-ttu-id="15318-104">この実装では、パスを作成し、Access データベースへの接続を確立してから、ドライブを削除します。</span><span class="sxs-lookup"><span data-stu-id="15318-104">This implementation creates a path, makes a connection to an Access database, and then removes the drive.</span></span>

> [!NOTE]
> <span data-ttu-id="15318-105">このプロバイダーの C# ソースファイル (AccessDBSampleProvider02.cs) は、Windows Vista 用 Microsoft Windows ソフトウェア開発キットおよび Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用してダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="15318-105">You can download the C# source file (AccessDBSampleProvider02.cs) for this provider using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="15318-106">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15318-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="15318-107">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="15318-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span> <span data-ttu-id="15318-108">その他の Windows PowerShell プロバイダーの実装の詳細については、「 [Windows Powershell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15318-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="15318-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="15318-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="11-154":::

## <a name="see-also"></a><span data-ttu-id="15318-110">参照</span><span class="sxs-lookup"><span data-stu-id="15318-110">See Also</span></span>

[<span data-ttu-id="15318-111">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="15318-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="15318-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="15318-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
