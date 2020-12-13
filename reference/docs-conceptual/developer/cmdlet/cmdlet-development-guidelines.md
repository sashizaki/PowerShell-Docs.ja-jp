---
ms.date: 09/13/2016
ms.topic: reference
title: コマンドレット開発ガイドライン
description: コマンドレット開発ガイドライン
ms.openlocfilehash: 8c31f64da0a3f6d8f03f09539c053fe6c61b9a9c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653485"
---
# <a name="cmdlet-development-guidelines"></a><span data-ttu-id="5604a-103">コマンドレット開発ガイドライン</span><span class="sxs-lookup"><span data-stu-id="5604a-103">Cmdlet Development Guidelines</span></span>

<span data-ttu-id="5604a-104">このセクションのトピックでは、整形式のコマンドレットを作成するために使用できる開発ガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5604a-104">The topics in this section provide development guidelines that you can use to produce well-formed cmdlets.</span></span> <span data-ttu-id="5604a-105">Windows PowerShell ランタイムによって提供される共通の機能を利用し、これらのガイドラインに従うことにより、堅牢なコマンドレットを最小限の労力で開発し、ユーザーに一貫したエクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="5604a-105">By leveraging the common functionality provided by the Windows PowerShell runtime and by following these guidelines, you can develop robust cmdlets with minimal effort and provide the user with a consistent experience.</span></span> <span data-ttu-id="5604a-106">また、一般的な機能は再テストを必要としないため、テストの負荷が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="5604a-106">Additionally, you will reduce the test burden because common functionality does not require retesting.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="5604a-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5604a-107">In This Section</span></span>

- [<span data-ttu-id="5604a-108">必要な開発ガイドライン</span><span class="sxs-lookup"><span data-stu-id="5604a-108">Required Development Guidelines</span></span>](./required-development-guidelines.md)

- [<span data-ttu-id="5604a-109">強くお勧めする開発ガイドライン</span><span class="sxs-lookup"><span data-stu-id="5604a-109">Strongly Encouraged Development Guidelines</span></span>](./strongly-encouraged-development-guidelines.md)

- [<span data-ttu-id="5604a-110">お勧めする開発ガイドライン</span><span class="sxs-lookup"><span data-stu-id="5604a-110">Advisory Development Guidelines</span></span>](./advisory-development-guidelines.md)

## <a name="see-also"></a><span data-ttu-id="5604a-111">参照</span><span class="sxs-lookup"><span data-stu-id="5604a-111">See Also</span></span>

[<span data-ttu-id="5604a-112">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="5604a-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="5604a-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="5604a-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
