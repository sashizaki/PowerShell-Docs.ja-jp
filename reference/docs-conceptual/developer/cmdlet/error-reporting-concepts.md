---
title: エラー報告の概念 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- non-terminating errors [PowerShell SDK]
- errors [PowerShell SDK], described
- terminating errors [PowerShell SDK]
- errors [PowerShell SDK]
ms.assetid: 0dce97c0-bd9a-4691-8ca3-e8d5dea902c5
caps.latest.revision: 11
ms.openlocfilehash: 2f185e415e3effc2cf09a282ca1167e3bcfb7d6a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364621"
---
# <a name="error-reporting-concepts"></a><span data-ttu-id="c9f2d-102">エラー レポートの概念</span><span class="sxs-lookup"><span data-stu-id="c9f2d-102">Error Reporting Concepts</span></span>

<span data-ttu-id="c9f2d-103">Windows PowerShell には、エラーを報告するためのメカニズムが2つ用意されています。エラーを*終了*するメカニズムと、*終了しないエラー*のためのメカニズムがあります。</span><span class="sxs-lookup"><span data-stu-id="c9f2d-103">Windows PowerShell provides two mechanisms for reporting errors: one mechanism for *terminating errors* and another mechanism for *non-terminating errors*.</span></span> <span data-ttu-id="c9f2d-104">コマンドレットを実行しているホストアプリケーションが適切な方法で応答できるように、コマンドレットでエラーを正しく報告することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c9f2d-104">It is important for your cmdlet to report errors correctly so that the host application that is running your cmdlets can react in an appropriate manner.</span></span>

<span data-ttu-id="c9f2d-105">コマンドレットでは、入力オブジェクトの処理を続行しない、または許可しないというエラーが発生した場合に、 [Throwterminatingerror \*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9f2d-105">Your cmdlet should call the [System.Management.Automation.Cmdlet.Throwterminatingerror\*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) method when an error occurs that does not or should not allow the cmdlet to continue to process its input objects.</span></span> <span data-ttu-id="c9f2d-106">コマンドレットは、 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドを呼び出して、コマンドレットが入力オブジェクトの処理を続行できるときに、終了しないエラーを報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9f2d-106">Your cmdlet should call the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report non-terminating errors when the cmdlet can continue processing the input objects.</span></span> <span data-ttu-id="c9f2d-107">どちらの方法でも、ホストアプリケーションでエラーの原因を調査するために使用できるエラーレコードが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c9f2d-107">Both methods provide an error record that the host application can use to investigate the cause of the error.</span></span>

<span data-ttu-id="c9f2d-108">エラーが終了または終了しないエラーであるかどうかを判断するには、次のガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="c9f2d-108">Use the following guidelines to determine whether an error is a terminating or non-terminating error.</span></span>

- <span data-ttu-id="c9f2d-109">エラーは、コマンドレットが現在のオブジェクトの処理を続行できないようにする場合、またはコンテンツに関係なく、他の入力オブジェクトを正常に処理しない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="c9f2d-109">An error is a terminating error if it prevents your cmdlet from continuing to process the current object or from successfully processing any further input objects, regardless of their content.</span></span>

- <span data-ttu-id="c9f2d-110">エラーは、内容に関係なく、現在のオブジェクトまたはその他の入力オブジェクトの処理をコマンドレットで続行しない場合に発生するエラーです。</span><span class="sxs-lookup"><span data-stu-id="c9f2d-110">An error is a terminating error if you do not want your cmdlet to continue processing the current object or any further input objects, regardless of their content.</span></span>

- <span data-ttu-id="c9f2d-111">オブジェクトを受け入れたり返したりしないコマンドレットで発生した場合、または1つのオブジェクトのみを受け入れるか返すコマンドレットで発生した場合は、エラーが終了エラーになります。</span><span class="sxs-lookup"><span data-stu-id="c9f2d-111">An error is a terminating error if it occurs in a cmdlet that does not accept or return an object or if it occurs in a cmdlet that accepts or returns only one object.</span></span>

- <span data-ttu-id="c9f2d-112">コマンドレットで現在のオブジェクトとその他の入力オブジェクトの処理を続行する場合は、エラーが終了しないエラーです。</span><span class="sxs-lookup"><span data-stu-id="c9f2d-112">An error is a non-terminating error if you want your cmdlet to continue processing the current object and any further input objects.</span></span>

- <span data-ttu-id="c9f2d-113">エラーは、特定の入力オブジェクトまたは入力オブジェクトのサブセットに関連付けられている場合は、終了しないエラーです。</span><span class="sxs-lookup"><span data-stu-id="c9f2d-113">An error is a non-terminating error if it is related to a specific input object or subset of input objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9f2d-114">参照</span><span class="sxs-lookup"><span data-stu-id="c9f2d-114">See Also</span></span>

[<span data-ttu-id="c9f2d-115">Throwterminatingerror \* のようになります。</span><span class="sxs-lookup"><span data-stu-id="c9f2d-115">System.Management.Automation.Cmdlet.Throwterminatingerror\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[<span data-ttu-id="c9f2d-116">WriteError (システム管理)</span><span class="sxs-lookup"><span data-stu-id="c9f2d-116">System.Management.Automation.Cmdlet.WriteError</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="c9f2d-117">Windows PowerShell エラーレコード</span><span class="sxs-lookup"><span data-stu-id="c9f2d-117">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="c9f2d-118">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="c9f2d-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
