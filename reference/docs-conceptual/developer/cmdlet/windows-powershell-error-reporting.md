---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell エラー レポート
description: Windows PowerShell エラー レポート
ms.openlocfilehash: 438e3d96bf52d8ac1f770c0550ae49b356d616eb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650106"
---
# <a name="windows-powershell-error-reporting"></a><span data-ttu-id="ed35b-103">Windows PowerShell エラー レポート</span><span class="sxs-lookup"><span data-stu-id="ed35b-103">Windows PowerShell Error Reporting</span></span>

<span data-ttu-id="ed35b-104">このセクションのトピックでは、コマンドレットがエラーを報告する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed35b-104">The topics in this section discuss how cmdlets report errors.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ed35b-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ed35b-105">In This Section</span></span>

<span data-ttu-id="ed35b-106">[エラー報告の概念](./error-reporting-concepts.md) コマンドレットがエラーを報告するために使用できる2つのメカニズムについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ed35b-106">[Error Reporting Concepts](./error-reporting-concepts.md) Describes the two mechanisms that cmdlets can use to report errors.</span></span>

<span data-ttu-id="ed35b-107">[終了エラー](./terminating-errors.md) 終了エラーを報告するために使用されるメソッドについて説明します。このメソッドは、コマンドレット内から呼び出すことができます。また、メソッドが呼び出されたときに Windows PowerShell ランタイムによって返される例外も報告します。</span><span class="sxs-lookup"><span data-stu-id="ed35b-107">[Terminating Errors](./terminating-errors.md) Describes the method used to report terminating errors, where that method can be called from within the cmdlet, and exceptions that can be returned by the Windows PowerShell runtime when the method is called.</span></span>

<span data-ttu-id="ed35b-108">[終了しないエラー](./non-terminating-errors.md) 終了しないエラーを報告するために使用されるメソッドと、そのメソッドをコマンドレット内から呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed35b-108">[Non-Terminating Errors](./non-terminating-errors.md) Describes the method used to report non-terminating errors and where that method can be called from within the cmdlet.</span></span>

<span data-ttu-id="ed35b-109">[カテゴリ別のエラー情報の表示](./displaying-error-information.md) ユーザーがエラーを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed35b-109">[Displaying Error Information by Category](./displaying-error-information.md) Discusses the ways that users can display error.</span></span>

<span data-ttu-id="ed35b-110">[Windows PowerShell エラーレコード](./windows-powershell-error-records.md) エラーレコードのコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ed35b-110">[Windows PowerShell Error Records](./windows-powershell-error-records.md) Describes the components of an error record.</span></span>

<span data-ttu-id="ed35b-111">[ErrorRecord オブジェクトの解釈](./interpreting-errorrecord-objects.md) ErrorRecord オブジェクトがどのように解釈されるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ed35b-111">[Interpreting ErrorRecord Objects](./interpreting-errorrecord-objects.md) Discusses how ErrorRecord objects are interpreted.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed35b-112">参照</span><span class="sxs-lookup"><span data-stu-id="ed35b-112">See Also</span></span>

[<span data-ttu-id="ed35b-113">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="ed35b-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
