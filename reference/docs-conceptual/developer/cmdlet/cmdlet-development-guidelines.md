---
title: コマンドレットの開発ガイドライン |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- development guidelines [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], development guidelines
ms.openlocfilehash: 5dd83b12a9052ff5f146c4c4e077a9358907cbd0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784488"
---
# <a name="cmdlet-development-guidelines"></a><span data-ttu-id="da645-102">コマンドレット開発ガイドライン</span><span class="sxs-lookup"><span data-stu-id="da645-102">Cmdlet Development Guidelines</span></span>

<span data-ttu-id="da645-103">このセクションのトピックでは、整形式のコマンドレットを作成するために使用できる開発ガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="da645-103">The topics in this section provide development guidelines that you can use to produce well-formed cmdlets.</span></span> <span data-ttu-id="da645-104">Windows PowerShell ランタイムによって提供される共通の機能を利用し、これらのガイドラインに従うことにより、堅牢なコマンドレットを最小限の労力で開発し、ユーザーに一貫したエクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="da645-104">By leveraging the common functionality provided by the Windows PowerShell runtime and by following these guidelines, you can develop robust cmdlets with minimal effort and provide the user with a consistent experience.</span></span> <span data-ttu-id="da645-105">また、一般的な機能は再テストを必要としないため、テストの負荷が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="da645-105">Additionally, you will reduce the test burden because common functionality does not require retesting.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="da645-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="da645-106">In This Section</span></span>

- [<span data-ttu-id="da645-107">必要な開発ガイドライン</span><span class="sxs-lookup"><span data-stu-id="da645-107">Required Development Guidelines</span></span>](./required-development-guidelines.md)

- [<span data-ttu-id="da645-108">強くお勧めする開発ガイドライン</span><span class="sxs-lookup"><span data-stu-id="da645-108">Strongly Encouraged Development Guidelines</span></span>](./strongly-encouraged-development-guidelines.md)

- [<span data-ttu-id="da645-109">お勧めする開発ガイドライン</span><span class="sxs-lookup"><span data-stu-id="da645-109">Advisory Development Guidelines</span></span>](./advisory-development-guidelines.md)

## <a name="see-also"></a><span data-ttu-id="da645-110">参照</span><span class="sxs-lookup"><span data-stu-id="da645-110">See Also</span></span>

[<span data-ttu-id="da645-111">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="da645-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="da645-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="da645-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
