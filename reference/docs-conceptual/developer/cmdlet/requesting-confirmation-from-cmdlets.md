---
title: コマンドレットからの確認を要求する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ConfirmImpact [PowerShell Programmer's Guide], described
- ShouldContinue [PowerShell Programmer's Guide], described
- user feedback [PowerShell Programmer's Guide], requesting
- ShouldProcess [PowerShell Programmer's Guide], described
- ConfirmPreference [PowerShell Programmer's Guide], described
ms.assetid: 37d6e87f-57b7-40bd-b645-392cf0b6e88e
caps.latest.revision: 13
ms.openlocfilehash: 0c0517ef7fbd5ae6434773a2dfe276f3a8c35f39
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369531"
---
# <a name="requesting-confirmation-from-cmdlets"></a><span data-ttu-id="de924-102">コマンドレットからの確認を要求する</span><span class="sxs-lookup"><span data-stu-id="de924-102">Requesting Confirmation from Cmdlets</span></span>

<span data-ttu-id="de924-103">コマンドレットは、Windows PowerShell 環境の外部にあるシステムを変更しようとしているときに確認を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de924-103">Cmdlets should request confirmation when they are about to make a change to the system that is outside of the Windows PowerShell environment.</span></span> <span data-ttu-id="de924-104">たとえば、コマンドレットを使用してユーザーアカウントを追加しようとしたり、プロセスを停止したりする場合は、コマンドレットを実行する前に、ユーザーからの確認が必要になります。</span><span class="sxs-lookup"><span data-stu-id="de924-104">For example, if a cmdlet is about to add a user account or stop a process, the cmdlet should require confirmation from the user before it proceeds.</span></span> <span data-ttu-id="de924-105">これに対して、コマンドレットが Windows PowerShell 変数を変更しようとしている場合、コマンドレットで確認が必要になることはありません。</span><span class="sxs-lookup"><span data-stu-id="de924-105">In contrast, if a cmdlet is about to change a Windows PowerShell variable, the cmdlet does not need to require confirmation.</span></span>

<span data-ttu-id="de924-106">確認要求を行うには、コマンドレットで確認要求がサポートされていることを示す必要があります。また、このコマンドレットは、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) .............. [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)(省略可能) 確認要求メッセージを表示するメソッド。</span><span class="sxs-lookup"><span data-stu-id="de924-106">In order to make a confirmation request, the cmdlet must indicate that it supports confirmation requests, and it must call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) (optional) methods to display a confirmation request message.</span></span>

## <a name="supporting-confirmation-requests"></a><span data-ttu-id="de924-107">確認要求のサポート</span><span class="sxs-lookup"><span data-stu-id="de924-107">Supporting Confirmation Requests</span></span>

<span data-ttu-id="de924-108">確認要求をサポートするには、コマンドレットで、コマンドレット属性の `SupportsShouldProcess` パラメーターを `true` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de924-108">To support confirmation requests, the cmdlet must set the `SupportsShouldProcess` parameter of the Cmdlet attribute to `true`.</span></span> <span data-ttu-id="de924-109">これにより、Windows PowerShell によって提供される `Confirm` および `WhatIf` コマンドレットパラメーターが有効になります。</span><span class="sxs-lookup"><span data-stu-id="de924-109">This enables the `Confirm` and `WhatIf` cmdlet parameters that are provided by Windows PowerShell.</span></span> <span data-ttu-id="de924-110">@No__t_0 パラメーターを使用すると、確認要求を表示するかどうかをユーザーが制御できます。</span><span class="sxs-lookup"><span data-stu-id="de924-110">The `Confirm` parameter allows the user to control whether the confirmation request is displayed.</span></span> <span data-ttu-id="de924-111">@No__t_0 パラメーターを使用すると、コマンドレットでメッセージを表示するかどうか、またはそのアクションを実行するかどうかをユーザーが決定できます。</span><span class="sxs-lookup"><span data-stu-id="de924-111">The `WhatIf` parameter allows the user to determine whether the cmdlet should display a message or perform its action.</span></span> <span data-ttu-id="de924-112">コマンドレットに `Confirm` パラメーターと `WhatIf` パラメーターを手動で追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="de924-112">Do not manually add the `Confirm` and `WhatIf` parameters to a cmdlet.</span></span>

<span data-ttu-id="de924-113">次の例は、確認要求をサポートするコマンドレット属性の宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="de924-113">The following example shows a Cmdlet attribute declaration that supports confirmation requests.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
        SupportsShouldProcess = true)]
```

## <a name="calling-the-confirmation-request-methods"></a><span data-ttu-id="de924-114">確認要求メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="de924-114">Calling the Confirmation request methods</span></span>

<span data-ttu-id="de924-115">コマンドレットのコードで、システムを変更する操作を実行する前に、 [system.string メソッドを呼び出します。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)</span><span class="sxs-lookup"><span data-stu-id="de924-115">In the cmdlet code, call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method before the operation that changes the system is performed.</span></span> <span data-ttu-id="de924-116">呼び出しが `false` の値を返す場合、操作は実行されず、コマンドレットは次の操作を処理するようにコマンドレットを設計します。</span><span class="sxs-lookup"><span data-stu-id="de924-116">Design the cmdlet so that if the call returns a value of `false`, the operation is not performed, and the cmdlet processes the next operation.</span></span>

## <a name="calling-the-shouldcontinue-method"></a><span data-ttu-id="de924-117">"メソッドの続行" メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="de924-117">Calling the ShouldContinue Method</span></span>

<span data-ttu-id="de924-118">ほとんどのコマンドレットでは、 [System.](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) .......................</span><span class="sxs-lookup"><span data-stu-id="de924-118">Most cmdlets request confirmation using only the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method.</span></span> <span data-ttu-id="de924-119">ただし、場合によっては、追加の確認が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="de924-119">However, some cases might require additional confirmation.</span></span> <span data-ttu-id="de924-120">このような場合は、 [system.](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) [.](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) .......................................</span><span class="sxs-lookup"><span data-stu-id="de924-120">For these cases, supplement the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call with a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method.</span></span> <span data-ttu-id="de924-121">これにより、コマンドレットまたはプロバイダーは、確認プロンプトに対する **[はい] のすべて**の応答のスコープをより細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="de924-121">This allows the cmdlet or provider to more finely control the scope of the **Yes to all** response to the confirmation prompt.</span></span>

<span data-ttu-id="de924-122">コマンドレットで[system.servicemodel メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)呼び出す場合は、コマンドレットで `Force` スイッチパラメーターも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de924-122">If a cmdlet calls the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method, the cmdlet must also provide a `Force` switch parameter.</span></span> <span data-ttu-id="de924-123">ユーザーがコマンドレットを呼び出したときに、ユーザーが `Force` を指定した場合、コマンドレットは引き続き system.object を[呼び出す必要](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)がありますが、このコマンドレットでは、system.object の呼び出しをバイパスする必要があり[ます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)</span><span class="sxs-lookup"><span data-stu-id="de924-123">If the user specifies `Force` when the user invokes the cmdlet, the cmdlet should still call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess), but it should bypass the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span>

<span data-ttu-id="de924-124">ユーザーにプロンプトが表示されない非対話型環境から呼び出された場合は、例外が[スローされ](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)ます ()。</span><span class="sxs-lookup"><span data-stu-id="de924-124">[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) will throw an exception when it is called from a non-interactive environment where the user cannot be prompted.</span></span> <span data-ttu-id="de924-125">@No__t_0 パラメーターを追加すると、非対話型環境で呼び出された場合でも、コマンドを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="de924-125">Adding a `Force` parameter ensures that the command can still be performed when it is invoked in a non-interactive environment.</span></span>

<span data-ttu-id="de924-126">次の例では、.............................. コマンド[レット](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)[を呼び出す方法](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)を示します。</span><span class="sxs-lookup"><span data-stu-id="de924-126">The following example shows how to call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span>

```csharp
if (ShouldProcess (...) )
{
  if (Force || ShouldContinue(...))
  {
     // Add code that performs the operation.
  }
}
```

<span data-ttu-id="de924-127">コマンドレットの呼び出しの動作は、コマンドレットが呼び出される環境によって[異なる場合があります](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)。</span><span class="sxs-lookup"><span data-stu-id="de924-127">The behavior of a [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call can vary depending on the environment in which the cmdlet is invoked.</span></span> <span data-ttu-id="de924-128">前のガイドラインを使用すると、ホスト環境に関係なく、コマンドレットを他のコマンドレットと一貫して動作させることができます。</span><span class="sxs-lookup"><span data-stu-id="de924-128">Using the previous guidelines will help ensure that the cmdlet behaves consistently with other cmdlets, regardless of the host environment.</span></span>

<span data-ttu-id="de924-129">System.servicemodel メソッドの呼び出しの例については、「確認[を要求する方法](./how-to-request-confirmations.md)」を参照して[ください。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)</span><span class="sxs-lookup"><span data-stu-id="de924-129">For an example of calling the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method, see [How to Request Confirmations](./how-to-request-confirmations.md).</span></span>

## <a name="specify-the-impact-level"></a><span data-ttu-id="de924-130">影響レベルを指定します</span><span class="sxs-lookup"><span data-stu-id="de924-130">Specify the Impact Level</span></span>

<span data-ttu-id="de924-131">コマンドレットを作成するときに、変更の影響レベル (重大度) を指定します。</span><span class="sxs-lookup"><span data-stu-id="de924-131">When you create the cmdlet, specify the impact level (the severity) of the change.</span></span> <span data-ttu-id="de924-132">これを行うには、コマンドレット属性の `ConfirmImpact` パラメーターの値を High、Medium、または Low に設定します。</span><span class="sxs-lookup"><span data-stu-id="de924-132">To do this, set the value of the `ConfirmImpact` parameter of the Cmdlet attribute to High, Medium, or Low.</span></span> <span data-ttu-id="de924-133">@No__t_0 の値は、コマンドレットの `SupportsShouldProcess` パラメーターも指定する場合にのみ指定できます。</span><span class="sxs-lookup"><span data-stu-id="de924-133">You can specify a value for `ConfirmImpact` only when you also specify the `SupportsShouldProcess` parameter for the cmdlet.</span></span>

<span data-ttu-id="de924-134">ほとんどのコマンドレットでは、`ConfirmImpact` を明示的に指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="de924-134">For most cmdlets, you do not have to explicitly specify `ConfirmImpact`.</span></span>  <span data-ttu-id="de924-135">代わりに、[中] のパラメーターの既定の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="de924-135">Instead, use the default setting of the parameter, which is Medium.</span></span> <span data-ttu-id="de924-136">@No__t_0 を [高] に設定すると、既定で操作が確認されます。</span><span class="sxs-lookup"><span data-stu-id="de924-136">If you set `ConfirmImpact` to High, the operation will be confirmed by default.</span></span> <span data-ttu-id="de924-137">ハードディスクボリュームの再フォーマットなど、非常に破壊的な操作を行う場合は、この設定を予約します。</span><span class="sxs-lookup"><span data-stu-id="de924-137">Reserve this setting for highly disruptive actions, such as reformatting a hard-disk volume.</span></span>

## <a name="calling-non-confirmation-methods"></a><span data-ttu-id="de924-138">確認以外のメソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="de924-138">Calling Non-Confirmation Methods</span></span>

<span data-ttu-id="de924-139">コマンドレットまたはプロバイダーがメッセージを送信する必要があるが、確認を要求しない場合は、次の3つのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="de924-139">If the cmdlet or provider must send a message but not request confirmation, it can call the following three methods.</span></span> <span data-ttu-id="de924-140">[WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッドを使用してこれらの型のメッセージを送信するのは避けてください。 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)出力は、コマンドレットまたはプロバイダーの通常の出力と混在しているためです。これにより、スクリプトの書き込みが困難になります。</span><span class="sxs-lookup"><span data-stu-id="de924-140">Avoid using the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method to send messages of these types because [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) output is intermingled with the normal output of your cmdlet or provider, which makes script writing difficult.</span></span>

- <span data-ttu-id="de924-141">ユーザーに注意して操作を続行するには、コマンドレットまたはプロバイダー[が、system.string メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning)呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="de924-141">To caution the user and continue with the operation, the cmdlet or provider can call the [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method.</span></span>

- <span data-ttu-id="de924-142">@No__t_0 パラメーターを使用してユーザーが取得できる追加情報を提供するために、コマンドレットまたはプロバイダー[は、system.servicemodel メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="de924-142">To provide additional information that the user can retrieve using the `Verbose` parameter, the cmdlet or provider can call the [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method.</span></span>

- <span data-ttu-id="de924-143">他の開発者や製品サポートに関するデバッグレベルの詳細を提供するために、コマンドレットまたはプロバイダーは、system.servicemodel[デバッグ](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="de924-143">To provide debugging-level detail for other developers or for product support, the cmdlet or provider can call the [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method.</span></span> <span data-ttu-id="de924-144">ユーザーは、`Debug` パラメーターを使用してこの情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="de924-144">The user can retrieve this information using the `Debug` parameter.</span></span>

<span data-ttu-id="de924-145">コマンドレットとプロバイダーは、まず次のメソッドを呼び出して、Windows PowerShell の外部でシステムを変更する操作の実行を試みる前に、確認を要求します。</span><span class="sxs-lookup"><span data-stu-id="de924-145">Cmdlets and providers first call the following methods to request confirmation before they attempt to perform an operation that changes a system outside of Windows PowerShell:</span></span>

- [<span data-ttu-id="de924-146">System.... コマンドレット</span><span class="sxs-lookup"><span data-stu-id="de924-146">System.Management.Automation.Cmdlet.Shouldprocess</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)

- [<span data-ttu-id="de924-147">システムの管理..........</span><span class="sxs-lookup"><span data-stu-id="de924-147">System.Management.Automation.Provider.Cmdletprovider.Shouldprocess</span></span>](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)

<span data-ttu-id="de924-148">これを行うには、ユーザーがコマンドを呼び出した方法に基づいて操作を確認するように求めるメッセージを表示して、[このメソッドを呼び出します。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)</span><span class="sxs-lookup"><span data-stu-id="de924-148">They do so by calling the [System.Management.Automation.Cmdlet.Shouldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method, which prompts the user to confirm the operation based on how the user invoked the command.</span></span>

## <a name="see-also"></a><span data-ttu-id="de924-149">参照</span><span class="sxs-lookup"><span data-stu-id="de924-149">See Also</span></span>

[<span data-ttu-id="de924-150">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="de924-150">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
