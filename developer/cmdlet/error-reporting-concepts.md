---
title: エラー レポートの概念 |Microsoft Docs
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
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054409"
---
# <a name="error-reporting-concepts"></a><span data-ttu-id="ed60e-102">エラー レポートの概念</span><span class="sxs-lookup"><span data-stu-id="ed60e-102">Error Reporting Concepts</span></span>

<span data-ttu-id="ed60e-103">Windows PowerShell がエラーを報告した 2 つのメカニズムを提供します: 1 つのメカニズム*終了エラー*と別のメカニズムの*未終了エラー*します。</span><span class="sxs-lookup"><span data-stu-id="ed60e-103">Windows PowerShell provides two mechanisms for reporting errors: one mechanism for *terminating errors* and another mechanism for *non-terminating errors*.</span></span> <span data-ttu-id="ed60e-104">正しく、コマンドレットを実行しているホスト アプリケーションが適切な方法で対応できるようにエラーを報告するコマンドレットの重要なです。</span><span class="sxs-lookup"><span data-stu-id="ed60e-104">It is important for your cmdlet to report errors correctly so that the host application that is running your cmdlets can react in an appropriate manner.</span></span>

<span data-ttu-id="ed60e-105">コマンドレットを呼び出す必要があります、 [System.Management.Automation.Cmdlet.Throwterminatingerror\*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)メソッドのエラーが発生する場合はまたはの入力オブジェクトの処理を続行するためのコマンドレットを許可しないでください。</span><span class="sxs-lookup"><span data-stu-id="ed60e-105">Your cmdlet should call the [System.Management.Automation.Cmdlet.Throwterminatingerror\*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) method when an error occurs that does not or should not allow the cmdlet to continue to process its input objects.</span></span> <span data-ttu-id="ed60e-106">コマンドレットを呼び出す必要があります、 [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)コマンドレットが入力オブジェクトの処理を続行することができる場合、未終了エラーを報告するメソッド。</span><span class="sxs-lookup"><span data-stu-id="ed60e-106">Your cmdlet should call the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report non-terminating errors when the cmdlet can continue processing the input objects.</span></span> <span data-ttu-id="ed60e-107">どちらの方法では、エラーの原因を調査するホスト アプリケーションが使用できるエラー レコードを提供します。</span><span class="sxs-lookup"><span data-stu-id="ed60e-107">Both methods provide an error record that the host application can use to investigate the cause of the error.</span></span>

<span data-ttu-id="ed60e-108">次のガイドラインを使用すると、エラーが終了するかどうか未終了エラーを判断します。</span><span class="sxs-lookup"><span data-stu-id="ed60e-108">Use the following guidelines to determine whether an error is a terminating or non-terminating error.</span></span>

- <span data-ttu-id="ed60e-109">エラーは、現在のオブジェクトの処理を継続から、またはそのコンテンツに関係なく、さらに入力オブジェクトはすべてを正常に処理から、コマンドレットを防ぐことが場合終端エラーです。</span><span class="sxs-lookup"><span data-stu-id="ed60e-109">An error is a terminating error if it prevents your cmdlet from continuing to process the current object or from successfully processing any further input objects, regardless of their content.</span></span>

- <span data-ttu-id="ed60e-110">エラーは、現在のオブジェクトまたはそのコンテンツに関係なく、さらに入力オブジェクトはすべての処理を続行する、コマンドレットを設定したくない場合、終了エラーです。</span><span class="sxs-lookup"><span data-stu-id="ed60e-110">An error is a terminating error if you do not want your cmdlet to continue processing the current object or any further input objects, regardless of their content.</span></span>

- <span data-ttu-id="ed60e-111">エラーは、受け付けられないか、オブジェクトを取得するコマンドレットで発生した場合、またはを受け入れるか 1 つだけオブジェクトを取得するコマンドレットで発生した場合、終了エラーです。</span><span class="sxs-lookup"><span data-stu-id="ed60e-111">An error is a terminating error if it occurs in a cmdlet that does not accept or return an object or if it occurs in a cmdlet that accepts or returns only one object.</span></span>

- <span data-ttu-id="ed60e-112">エラーは、コマンドレットを現在のオブジェクトとさらに入力オブジェクトの処理を続行する場合に、未終了エラーです。</span><span class="sxs-lookup"><span data-stu-id="ed60e-112">An error is a non-terminating error if you want your cmdlet to continue processing the current object and any further input objects.</span></span>

- <span data-ttu-id="ed60e-113">エラーは、特定の入力オブジェクトまたは入力オブジェクトのサブセットに関連している場合に、未終了エラーです。</span><span class="sxs-lookup"><span data-stu-id="ed60e-113">An error is a non-terminating error if it is related to a specific input object or subset of input objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed60e-114">参照</span><span class="sxs-lookup"><span data-stu-id="ed60e-114">See Also</span></span>

[<span data-ttu-id="ed60e-115">System.Management.Automation.Cmdlet.Throwterminatingerror\*</span><span class="sxs-lookup"><span data-stu-id="ed60e-115">System.Management.Automation.Cmdlet.Throwterminatingerror\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[<span data-ttu-id="ed60e-116">System.Management.Automation.Cmdlet.WriteError</span><span class="sxs-lookup"><span data-stu-id="ed60e-116">System.Management.Automation.Cmdlet.WriteError</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="ed60e-117">Windows PowerShell のエラー レコード</span><span class="sxs-lookup"><span data-stu-id="ed60e-117">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="ed60e-118">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="ed60e-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
