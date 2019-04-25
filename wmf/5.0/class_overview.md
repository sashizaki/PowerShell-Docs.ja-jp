---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 5919a68c87ae8827a1b97befc653bb74713f33fe
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085781"
---
# <a name="creating-custom-types-using-powershell-classes"></a><span data-ttu-id="f4927-102">PowerShell クラスを使用したカスタム型の作成</span><span class="sxs-lookup"><span data-stu-id="f4927-102">Creating Custom Types using PowerShell Classes</span></span>

<span data-ttu-id="f4927-103">他のオブジェクト指向プログラミング言語に似た、公式的な構文とセマンティクスを使用することによって、クラスと他のユーザー定義型を定義するための PowerShell 言語を改善しました。</span><span class="sxs-lookup"><span data-stu-id="f4927-103">We’ve improved the PowerShell language for defining classes and other user-defined types by using formal syntax and semantics that are similar to other object-oriented programming languages.</span></span> <span data-ttu-id="f4927-104">開発者や IT プロフェッショナルがより広範なユース ケースで PowerShell を採用できるようにし、PowerShell アーティファクト (DSC リソースなど) の開発を簡素化し、管理面の対応を促進することがその目標です。</span><span class="sxs-lookup"><span data-stu-id="f4927-104">The goal is to enable developers and IT professionals to embrace PowerShell for a wider range of use cases, simplify development of PowerShell artifacts (such as DSC resources), and accelerate coverage of management surfaces.</span></span>

## <a name="supported-scenarios-in-this-release"></a><span data-ttu-id="f4927-105">このリリースでサポートされるシナリオ</span><span class="sxs-lookup"><span data-stu-id="f4927-105">Supported scenarios in this release</span></span>

-   <span data-ttu-id="f4927-106">PowerShell 言語を使用して DSC リソースとその関連する型を定義する</span><span class="sxs-lookup"><span data-stu-id="f4927-106">Define DSC resources and their associated types by using the PowerShell language</span></span>
-   <span data-ttu-id="f4927-107">クラス、プロパティ、メソッドなどの使い慣れたオブジェクト指向プログラミングの構成要素を使用して PowerShell でカスタム型を定義する</span><span class="sxs-lookup"><span data-stu-id="f4927-107">Define custom types in PowerShell by using familiar object-oriented programming constructs, such as classes, properties, methods, etc.</span></span>
-   <span data-ttu-id="f4927-108">PowerShell のクラスおよびクラス ベース DSC リソースを使用した継承のサポート</span><span class="sxs-lookup"><span data-stu-id="f4927-108">Inheritance support with class in PowerShell and class base DSC resource</span></span>
-   <span data-ttu-id="f4927-109">PowerShell 言語を使用した型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="f4927-109">Debug types by using the PowerShell language</span></span>
-   <span data-ttu-id="f4927-110">公式的なメカニズムを適切なレベルで使用した例外の生成および処理</span><span class="sxs-lookup"><span data-stu-id="f4927-110">Generate and handle exceptions by using formal mechanisms, and at the right level</span></span>
