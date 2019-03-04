---
title: Windows PowerShell のエラーが報告 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 61b7773a-c346-4835-a928-7212dc4c85bc
caps.latest.revision: 7
ms.openlocfilehash: 259de341fd2fcce2b0c4629f806b4348cba1ff2c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856158"
---
# <a name="windows-powershell-error-reporting"></a><span data-ttu-id="c77ce-102">Windows PowerShell エラー レポート</span><span class="sxs-lookup"><span data-stu-id="c77ce-102">Windows PowerShell Error Reporting</span></span>

<span data-ttu-id="c77ce-103">このセクションのトピックでは、コマンドレットがエラーを報告する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c77ce-103">The topics in this section discuss how cmdlets report errors.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c77ce-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c77ce-104">In This Section</span></span>

<span data-ttu-id="c77ce-105">[エラー報告の概念](./error-reporting-concepts.md)コマンドレットは、エラーの報告に使用できる 2 つのメカニズムについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c77ce-105">[Error Reporting Concepts](./error-reporting-concepts.md) Describes the two mechanisms that cmdlets can use to report errors.</span></span>

<span data-ttu-id="c77ce-106">[終了エラー](./terminating-errors.md)終了、そのメソッドは、コマンドレット内から呼び出すことが、エラーと、メソッドが呼び出されたときに、Windows PowerShell ランタイムによって返される例外を報告するために使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c77ce-106">[Terminating Errors](./terminating-errors.md) Describes the method used to report terminating errors, where that method can be called from within the cmdlet, and exceptions that can be returned by the Windows PowerShell runtime when the method is called.</span></span>

<span data-ttu-id="c77ce-107">[未終了エラー](./non-terminating-errors.md)未終了エラーあり、コマンドレットからそのメソッドに呼び出すことを報告するために使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c77ce-107">[Non-Terminating Errors](./non-terminating-errors.md) Describes the method used to report non-terminating errors and where that method can be called from within the cmdlet.</span></span>

<span data-ttu-id="c77ce-108">[カテゴリ別のエラー情報を表示する](./displaying-error-information.md)ユーザーがエラーを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c77ce-108">[Displaying Error Information by Category](./displaying-error-information.md) Discusses the ways that users can display error.</span></span>

<span data-ttu-id="c77ce-109">[Windows PowerShell のエラー レコード](./windows-powershell-error-records.md)エラー レコードのコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c77ce-109">[Windows PowerShell Error Records](./windows-powershell-error-records.md) Describes the components of an error record.</span></span>

<span data-ttu-id="c77ce-110">[ErrorRecord オブジェクトを解釈する](./interpreting-errorrecord-objects.md)ErrorRecord オブジェクトを解釈する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c77ce-110">[Interpreting ErrorRecord Objects](./interpreting-errorrecord-objects.md) Discusses how ErrorRecord objects are interpreted.</span></span>

## <a name="see-also"></a><span data-ttu-id="c77ce-111">参照</span><span class="sxs-lookup"><span data-stu-id="c77ce-111">See Also</span></span>

[<span data-ttu-id="c77ce-112">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="c77ce-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
