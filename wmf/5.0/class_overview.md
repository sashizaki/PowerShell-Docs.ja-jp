---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 8b414331bbfb7dc71d960241a6bc83b0b22641db
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="creating-custom-types-using-powershell-classes"></a><span data-ttu-id="0a159-102">PowerShell クラスを使用したカスタム型の作成</span><span class="sxs-lookup"><span data-stu-id="0a159-102">Creating Custom Types using PowerShell Classes</span></span>

<span data-ttu-id="0a159-103">他のオブジェクト指向プログラミング言語に似た、公式的な構文とセマンティクスを使用することによって、クラスと他のユーザー定義型を定義するための PowerShell 言語を改善しました。</span><span class="sxs-lookup"><span data-stu-id="0a159-103">We’ve improved the PowerShell language for defining classes and other user-defined types by using formal syntax and semantics that are similar to other object-oriented programming languages.</span></span> <span data-ttu-id="0a159-104">開発者や IT プロフェッショナルがより広範なユース ケースで PowerShell を採用できるようにし、PowerShell アーティファクト (DSC リソースなど) の開発を簡素化し、管理面の対応を促進することがその目標です。</span><span class="sxs-lookup"><span data-stu-id="0a159-104">The goal is to enable developers and IT professionals to embrace PowerShell for a wider range of use cases, simplify development of PowerShell artifacts (such as DSC resources), and accelerate coverage of management surfaces.</span></span>

## <a name="supported-scenarios-in-this-release"></a><span data-ttu-id="0a159-105">このリリースでサポートされるシナリオ</span><span class="sxs-lookup"><span data-stu-id="0a159-105">Supported scenarios in this release</span></span>

-   <span data-ttu-id="0a159-106">PowerShell 言語を使用して DSC リソースとその関連する型を定義する</span><span class="sxs-lookup"><span data-stu-id="0a159-106">Define DSC resources and their associated types by using the PowerShell language</span></span>
-   <span data-ttu-id="0a159-107">クラス、プロパティ、メソッドなどの使い慣れたオブジェクト指向プログラミングの構成要素を使用して PowerShell でカスタム型を定義する</span><span class="sxs-lookup"><span data-stu-id="0a159-107">Define custom types in PowerShell by using familiar object-oriented programming constructs, such as classes, properties, methods, etc.</span></span>
-   <span data-ttu-id="0a159-108">PowerShell のクラスおよびクラス ベース DSC リソースを使用した継承のサポート</span><span class="sxs-lookup"><span data-stu-id="0a159-108">Inheritance support with class in PowerShell and class base DSC resource</span></span>
-   <span data-ttu-id="0a159-109">PowerShell 言語を使用した型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="0a159-109">Debug types by using the PowerShell language</span></span>
-   <span data-ttu-id="0a159-110">公式的なメカニズムを適切なレベルで使用した例外の生成および処理</span><span class="sxs-lookup"><span data-stu-id="0a159-110">Generate and handle exceptions by using formal mechanisms, and at the right level</span></span>

