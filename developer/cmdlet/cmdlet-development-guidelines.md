---
title: コマンドレットの開発のガイドライン |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- development guidelines [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], development guidelines
ms.assetid: c30cc3c0-e958-4a8f-b81f-1e38de772f13
caps.latest.revision: 14
ms.openlocfilehash: 89c7682e87fa6f389349fc44275be0d2ffc83957
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857608"
---
# <a name="cmdlet-development-guidelines"></a><span data-ttu-id="68732-102">コマンドレット開発ガイドライン</span><span class="sxs-lookup"><span data-stu-id="68732-102">Cmdlet Development Guidelines</span></span>

<span data-ttu-id="68732-103">このセクションのトピックでは、適切な形式でコマンドレットを生成するために使用できる開発のガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="68732-103">The topics in this section provide development guidelines that you can use to produce well-formed cmdlets.</span></span> <span data-ttu-id="68732-104">これらのガイドラインに従うと、Windows PowerShell ランタイムによって提供される共通の機能を活用することでは、最小限の労力で堅牢なコマンドレットの開発し、一貫したエクスペリエンスをユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="68732-104">By leveraging the common functionality provided by the Windows PowerShell runtime and by following these guidelines, you can develop robust cmdlets with minimal effort and provide the user with a consistent experience.</span></span> <span data-ttu-id="68732-105">さらに、共通の機能で、再テストが必要ないために、テストの負荷を減らすためされます。</span><span class="sxs-lookup"><span data-stu-id="68732-105">Additionally, you will reduce the test burden because common functionality does not require retesting.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="68732-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="68732-106">In This Section</span></span>

- [<span data-ttu-id="68732-107">必要な開発のガイドライン</span><span class="sxs-lookup"><span data-stu-id="68732-107">Required Development Guidelines</span></span>](./required-development-guidelines.md)

- [<span data-ttu-id="68732-108">強くお勧めします開発のガイドライン</span><span class="sxs-lookup"><span data-stu-id="68732-108">Strongly Encouraged Development Guidelines</span></span>](./strongly-encouraged-development-guidelines.md)

- [<span data-ttu-id="68732-109">アドバイザリ開発のガイドライン</span><span class="sxs-lookup"><span data-stu-id="68732-109">Advisory Development Guidelines</span></span>](./advisory-development-guidelines.md)

## <a name="see-also"></a><span data-ttu-id="68732-110">参照</span><span class="sxs-lookup"><span data-stu-id="68732-110">See Also</span></span>

[<span data-ttu-id="68732-111">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="68732-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="68732-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="68732-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
