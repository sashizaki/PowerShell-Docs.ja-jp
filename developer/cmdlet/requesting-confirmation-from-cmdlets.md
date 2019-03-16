---
title: コマンドレットから確認を求める |Microsoft Docs
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
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057407"
---
# <a name="requesting-confirmation-from-cmdlets"></a><span data-ttu-id="509ef-102">コマンドレットからの確認を要求する</span><span class="sxs-lookup"><span data-stu-id="509ef-102">Requesting Confirmation from Cmdlets</span></span>

<span data-ttu-id="509ef-103">コマンドレットは、Windows PowerShell 環境の外であるシステムに変更を加えるとしているときに、確認を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="509ef-103">Cmdlets should request confirmation when they are about to make a change to the system that is outside of the Windows PowerShell environment.</span></span> <span data-ttu-id="509ef-104">たとえば、コマンドレットは、ユーザー アカウントを追加またはプロセスを停止するのには場合に進む前に、コマンドレットは、ユーザーから送信される確認必要があります。</span><span class="sxs-lookup"><span data-stu-id="509ef-104">For example, if a cmdlet is about to add a user account or stop a process, the cmdlet should require confirmation from the user before it proceeds.</span></span> <span data-ttu-id="509ef-105">これに対し、コマンドレットを Windows PowerShell 変数を変更する場合は、コマンドレットが、確認を要求する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="509ef-105">In contrast, if a cmdlet is about to change a Windows PowerShell variable, the cmdlet does not need to require confirmation.</span></span>

<span data-ttu-id="509ef-106">確認要求を行うために、コマンドレットを確認要求では、サポートを呼び出す必要があります示す必要があります、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)確認要求メッセージを表示する (省略可能) のメソッド。</span><span class="sxs-lookup"><span data-stu-id="509ef-106">In order to make a confirmation request, the cmdlet must indicate that it supports confirmation requests, and it must call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) (optional) methods to display a confirmation request message.</span></span>

## <a name="supporting-confirmation-requests"></a><span data-ttu-id="509ef-107">確認要求をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="509ef-107">Supporting Confirmation Requests</span></span>

<span data-ttu-id="509ef-108">確認要求をサポートするために、コマンドレットを設定する必要があります、`SupportsShouldProcess`コマンドレットの属性のパラメーター`true`します。</span><span class="sxs-lookup"><span data-stu-id="509ef-108">To support confirmation requests, the cmdlet must set the `SupportsShouldProcess` parameter of the Cmdlet attribute to `true`.</span></span> <span data-ttu-id="509ef-109">これにより、`Confirm`と`WhatIf`Windows PowerShell によって提供されるコマンドレットのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="509ef-109">This enables the `Confirm` and `WhatIf` cmdlet parameters that are provided by Windows PowerShell.</span></span> <span data-ttu-id="509ef-110">`Confirm`パラメーター、確認要求が表示されるかどうかをユーザーが管理を使用できます。</span><span class="sxs-lookup"><span data-stu-id="509ef-110">The `Confirm` parameter allows the user to control whether the confirmation request is displayed.</span></span> <span data-ttu-id="509ef-111">`WhatIf`パラメーターには、コマンドレットでメッセージを表示する必要があります、そのアクションを実行するかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="509ef-111">The `WhatIf` parameter allows the user to determine whether the cmdlet should display a message or perform its action.</span></span> <span data-ttu-id="509ef-112">手動で追加しないでください、`Confirm`と`WhatIf`コマンドレットのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="509ef-112">Do not manually add the `Confirm` and `WhatIf` parameters to a cmdlet.</span></span>

<span data-ttu-id="509ef-113">次の例では、確認要求をサポートするコマンドレットの属性宣言を示します。</span><span class="sxs-lookup"><span data-stu-id="509ef-113">The following example shows a Cmdlet attribute declaration that supports confirmation requests.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
        SupportsShouldProcess = true)]
```

## <a name="calling-the-confirmation-request-methods"></a><span data-ttu-id="509ef-114">確認要求のメソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="509ef-114">Calling the Confirmation request methods</span></span>

<span data-ttu-id="509ef-115">コマンドレットのコードで呼び出し、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッド、システムを変更する操作を実行する前にします。</span><span class="sxs-lookup"><span data-stu-id="509ef-115">In the cmdlet code, call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method before the operation that changes the system is performed.</span></span> <span data-ttu-id="509ef-116">場合の値が返され、呼び出し、コマンドレットを設計`false`操作は実行されず、およびコマンドレットは、次の操作を処理します。</span><span class="sxs-lookup"><span data-stu-id="509ef-116">Design the cmdlet so that if the call returns a value of `false`, the operation is not performed, and the cmdlet processes the next operation.</span></span>

## <a name="calling-the-shouldcontinue-method"></a><span data-ttu-id="509ef-117">ShouldContinue メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="509ef-117">Calling the ShouldContinue Method</span></span>

<span data-ttu-id="509ef-118">ほとんどのコマンドレットのみを使用して確認を要求する、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッド。</span><span class="sxs-lookup"><span data-stu-id="509ef-118">Most cmdlets request confirmation using only the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method.</span></span> <span data-ttu-id="509ef-119">ただし、場合によっては、追加の確認を必要があります。</span><span class="sxs-lookup"><span data-stu-id="509ef-119">However, some cases might require additional confirmation.</span></span> <span data-ttu-id="509ef-120">このような場合は、補完、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)への呼び出しで呼び出し、 [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッド。</span><span class="sxs-lookup"><span data-stu-id="509ef-120">For these cases, supplement the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call with a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method.</span></span> <span data-ttu-id="509ef-121">これにより、コマンドレットやプロバイダーのスコープをより細かく制御する、 **[すべてはい]** 確認プロンプトに応答します。</span><span class="sxs-lookup"><span data-stu-id="509ef-121">This allows the cmdlet or provider to more finely control the scope of the **Yes to all** response to the confirmation prompt.</span></span>

<span data-ttu-id="509ef-122">コマンドレットを呼び出す場合、 [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドでは、コマンドレットを提供する必要がありますも、`Force`スイッチ パラメーター。</span><span class="sxs-lookup"><span data-stu-id="509ef-122">If a cmdlet calls the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method, the cmdlet must also provide a `Force` switch parameter.</span></span> <span data-ttu-id="509ef-123">ユーザーが指定されている場合`Force`コマンドレットを呼び出す必要があります、ユーザーが、コマンドレットを呼び出すと[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)への呼び出しをバイパスする必要がありますが、 [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)します。</span><span class="sxs-lookup"><span data-stu-id="509ef-123">If the user specifies `Force` when the user invokes the cmdlet, the cmdlet should still call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess), but it should bypass the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span>

<span data-ttu-id="509ef-124">[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)ユーザーを求められますことはできません、非対話型環境から呼び出されたときに例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="509ef-124">[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) will throw an exception when it is called from a non-interactive environment where the user cannot be prompted.</span></span> <span data-ttu-id="509ef-125">追加、`Force`パラメーターにより非対話型環境で呼び出された場合は、コマンドを実行もできるようになります。</span><span class="sxs-lookup"><span data-stu-id="509ef-125">Adding a `Force` parameter ensures that the command can still be performed when it is invoked in a non-interactive environment.</span></span>

<span data-ttu-id="509ef-126">次の例は、呼び出す方法を示しています。 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)します。</span><span class="sxs-lookup"><span data-stu-id="509ef-126">The following example shows how to call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span>

```csharp
if (ShouldProcess (...) )
{
  if (Force || ShouldContinue(...))
  {
     // Add code that performs the operation.
  }
}
```

<span data-ttu-id="509ef-127">動作を[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出しは、コマンドレットが呼び出される環境によって異なります。</span><span class="sxs-lookup"><span data-stu-id="509ef-127">The behavior of a [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call can vary depending on the environment in which the cmdlet is invoked.</span></span> <span data-ttu-id="509ef-128">前のガイドラインを使用に役立つコマンドレットがホスト環境に関係なく、他のコマンドレットで一貫して動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="509ef-128">Using the previous guidelines will help ensure that the cmdlet behaves consistently with other cmdlets, regardless of the host environment.</span></span>

<span data-ttu-id="509ef-129">呼び出し元の例については、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッドを参照してください[依頼の確認方法](./how-to-request-confirmations.md)します。</span><span class="sxs-lookup"><span data-stu-id="509ef-129">For an example of calling the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method, see [How to Request Confirmations](./how-to-request-confirmations.md).</span></span>

## <a name="specify-the-impact-level"></a><span data-ttu-id="509ef-130">影響のレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="509ef-130">Specify the Impact Level</span></span>

<span data-ttu-id="509ef-131">コマンドレットを作成する場合は、変更の影響レベル (重要度) を指定します。</span><span class="sxs-lookup"><span data-stu-id="509ef-131">When you create the cmdlet, specify the impact level (the severity) of the change.</span></span> <span data-ttu-id="509ef-132">これを行うには、値を設定、`ConfirmImpact`高、中、低コマンドレットの属性のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="509ef-132">To do this, set the value of the `ConfirmImpact` parameter of the Cmdlet attribute to High, Medium, or Low.</span></span> <span data-ttu-id="509ef-133">値を指定する`ConfirmImpact`のみときに指定することも、`SupportsShouldProcess`コマンドレットのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="509ef-133">You can specify a value for `ConfirmImpact` only when you also specify the `SupportsShouldProcess` parameter for the cmdlet.</span></span>

<span data-ttu-id="509ef-134">ほとんどのコマンドレットには明示的に指定する必要はありません`ConfirmImpact`します。</span><span class="sxs-lookup"><span data-stu-id="509ef-134">For most cmdlets, you do not have to explicitly specify `ConfirmImpact`.</span></span>  <span data-ttu-id="509ef-135">代わりに、中であるパラメーターの既定の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="509ef-135">Instead, use the default setting of the parameter, which is Medium.</span></span> <span data-ttu-id="509ef-136">設定した場合`ConfirmImpact`高 に既定では、操作が確認されます。</span><span class="sxs-lookup"><span data-stu-id="509ef-136">If you set `ConfirmImpact` to High, the operation will be confirmed by default.</span></span> <span data-ttu-id="509ef-137">ハード ディスク ボリュームを再フォーマットなどの高度に破壊的な操作には、この設定を予約します。</span><span class="sxs-lookup"><span data-stu-id="509ef-137">Reserve this setting for highly disruptive actions, such as reformatting a hard-disk volume.</span></span>

## <a name="calling-non-confirmation-methods"></a><span data-ttu-id="509ef-138">非確認メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="509ef-138">Calling Non-Confirmation Methods</span></span>

<span data-ttu-id="509ef-139">コマンドレットまたはプロバイダーがメッセージを送信、確認を要求する必要がありますは、次の 3 つのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="509ef-139">If the cmdlet or provider must send a message but not request confirmation, it can call the following three methods.</span></span> <span data-ttu-id="509ef-140">使用しないでください、 [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)ため、これらの型のメッセージを送信するメソッド[System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)出力の混在コマンドレットまたはプロバイダーの通常の出力で困難スクリプトを記述します。</span><span class="sxs-lookup"><span data-stu-id="509ef-140">Avoid using the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method to send messages of these types because [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) output is intermingled with the normal output of your cmdlet or provider, which makes script writing difficult.</span></span>

- <span data-ttu-id="509ef-141">コマンドレットまたはプロバイダーを呼び出すことができます、ユーザーに警告して、操作を続行に、 [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning)メソッド。</span><span class="sxs-lookup"><span data-stu-id="509ef-141">To caution the user and continue with the operation, the cmdlet or provider can call the [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method.</span></span>

- <span data-ttu-id="509ef-142">追加の情報を使用して、ユーザーを取得できる、`Verbose`パラメーターでは、コマンドレット、プロバイダーが呼び出すことができます、 [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)メソッド。</span><span class="sxs-lookup"><span data-stu-id="509ef-142">To provide additional information that the user can retrieve using the `Verbose` parameter, the cmdlet or provider can call the [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method.</span></span>

- <span data-ttu-id="509ef-143">コマンドレットまたはプロバイダーを呼び出すことが他の開発者、または製品サポートについては、デバッグ レベルの詳細を提供するには[System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)メソッド。</span><span class="sxs-lookup"><span data-stu-id="509ef-143">To provide debugging-level detail for other developers or for product support, the cmdlet or provider can call the [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method.</span></span> <span data-ttu-id="509ef-144">ユーザーを使用してこの情報を取得することができます、`Debug`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="509ef-144">The user can retrieve this information using the `Debug` parameter.</span></span>

<span data-ttu-id="509ef-145">コマンドレットとプロバイダーは、まず Windows PowerShell の外部のシステムを変更する操作の実行を試みる前に、確認を要求する次のメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="509ef-145">Cmdlets and providers first call the following methods to request confirmation before they attempt to perform an operation that changes a system outside of Windows PowerShell:</span></span>

- [<span data-ttu-id="509ef-146">System.Management.Automation.Cmdlet.Shouldprocess</span><span class="sxs-lookup"><span data-stu-id="509ef-146">System.Management.Automation.Cmdlet.Shouldprocess</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)

- [<span data-ttu-id="509ef-147">System.Management.Automation.Provider.Cmdletprovider.Shouldprocess</span><span class="sxs-lookup"><span data-stu-id="509ef-147">System.Management.Automation.Provider.Cmdletprovider.Shouldprocess</span></span>](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)

<span data-ttu-id="509ef-148">呼び出すときは、 [System.Management.Automation.Cmdlet.Shouldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッドで、ユーザーが、ユーザーがコマンドを呼び出す方法に基づいて、操作を確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="509ef-148">They do so by calling the [System.Management.Automation.Cmdlet.Shouldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method, which prompts the user to confirm the operation based on how the user invoked the command.</span></span>

## <a name="see-also"></a><span data-ttu-id="509ef-149">参照</span><span class="sxs-lookup"><span data-stu-id="509ef-149">See Also</span></span>

[<span data-ttu-id="509ef-150">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="509ef-150">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
