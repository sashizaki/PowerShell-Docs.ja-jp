---
title: Windows PowerShell エラー報告 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7f7afcf5186732734976304c8e58e4d940156e1e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783961"
---
# <a name="windows-powershell-error-reporting"></a><span data-ttu-id="9cded-102">Windows PowerShell エラー レポート</span><span class="sxs-lookup"><span data-stu-id="9cded-102">Windows PowerShell Error Reporting</span></span>

<span data-ttu-id="9cded-103">このセクションのトピックでは、コマンドレットがエラーを報告する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9cded-103">The topics in this section discuss how cmdlets report errors.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="9cded-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9cded-104">In This Section</span></span>

<span data-ttu-id="9cded-105">[エラー報告の概念](./error-reporting-concepts.md)コマンドレットがエラーを報告するために使用できる2つのメカニズムについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9cded-105">[Error Reporting Concepts](./error-reporting-concepts.md) Describes the two mechanisms that cmdlets can use to report errors.</span></span>

<span data-ttu-id="9cded-106">[終了エラー](./terminating-errors.md)終了エラーを報告するために使用されるメソッドについて説明します。このメソッドは、コマンドレット内から呼び出すことができます。また、メソッドが呼び出されたときに Windows PowerShell ランタイムによって返される例外も報告します。</span><span class="sxs-lookup"><span data-stu-id="9cded-106">[Terminating Errors](./terminating-errors.md) Describes the method used to report terminating errors, where that method can be called from within the cmdlet, and exceptions that can be returned by the Windows PowerShell runtime when the method is called.</span></span>

<span data-ttu-id="9cded-107">[終了しないエラー](./non-terminating-errors.md)終了しないエラーを報告するために使用されるメソッドと、そのメソッドをコマンドレット内から呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9cded-107">[Non-Terminating Errors](./non-terminating-errors.md) Describes the method used to report non-terminating errors and where that method can be called from within the cmdlet.</span></span>

<span data-ttu-id="9cded-108">[カテゴリ別のエラー情報の表示](./displaying-error-information.md)ユーザーがエラーを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9cded-108">[Displaying Error Information by Category](./displaying-error-information.md) Discusses the ways that users can display error.</span></span>

<span data-ttu-id="9cded-109">[Windows PowerShell エラーレコード](./windows-powershell-error-records.md)エラーレコードのコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9cded-109">[Windows PowerShell Error Records](./windows-powershell-error-records.md) Describes the components of an error record.</span></span>

<span data-ttu-id="9cded-110">[ErrorRecord オブジェクトの解釈](./interpreting-errorrecord-objects.md)ErrorRecord オブジェクトがどのように解釈されるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9cded-110">[Interpreting ErrorRecord Objects](./interpreting-errorrecord-objects.md) Discusses how ErrorRecord objects are interpreted.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cded-111">参照</span><span class="sxs-lookup"><span data-stu-id="9cded-111">See Also</span></span>

[<span data-ttu-id="9cded-112">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="9cded-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
