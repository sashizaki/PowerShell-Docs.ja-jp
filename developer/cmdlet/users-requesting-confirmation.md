---
title: 確認を求めるユーザー |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f337498-c534-40ed-968a-09d4d9ca3849
caps.latest.revision: 8
ms.openlocfilehash: ed9ff9fc1668a89e1ac0ceac8f0800a15b349226
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059560"
---
# <a name="users-requesting-confirmation"></a><span data-ttu-id="c9bb9-102">ユーザーの確認要求</span><span class="sxs-lookup"><span data-stu-id="c9bb9-102">Users Requesting Confirmation</span></span>

<span data-ttu-id="c9bb9-103">値を指定すると`true`の`SupportsShouldProcess`コマンドレットの属性の宣言のパラメーターは、ユーザーを指定できます、`Confirm`コマンド プロンプト パラメーター。</span><span class="sxs-lookup"><span data-stu-id="c9bb9-103">When you specify a value of `true` for the `SupportsShouldProcess` parameter of the Cmdlet attribute declaration, users can specify the `Confirm` parameter at the command prompt.</span></span>

<span data-ttu-id="c9bb9-104">既定の環境でユーザーを指定できます、`Confirm`パラメーターまたは`"-Confirm:$true`するので、確認が要求されるときに、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c9bb9-104">In the default environment, users can specify the `Confirm` parameter or `"-Confirm:$true` so that confirmation is requested when the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method is called.</span></span> <span data-ttu-id="c9bb9-105">これをバイパスする[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)影響の大きい操作の場合でも、確認要求。</span><span class="sxs-lookup"><span data-stu-id="c9bb9-105">This bypasses [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) confirmation requests, even for high-impact operations.</span></span>

<span data-ttu-id="c9bb9-106">場合`Confirm`が指定されていない、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出し要求の確認の場合、`$ConfirmPreference`ユーザー設定変数が同じか、またはより大きい、`ConfirmImpact`の設定、コマンドレットまたはプロバイダー。</span><span class="sxs-lookup"><span data-stu-id="c9bb9-106">If `Confirm` is not specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation if the `$ConfirmPreference` preference variable is equal to or greater than the `ConfirmImpact` setting of the cmdlet or provider.</span></span> <span data-ttu-id="c9bb9-107">既定値の`$ConfirmPreference`高です。</span><span class="sxs-lookup"><span data-stu-id="c9bb9-107">The default setting of `$ConfirmPreference` is High.</span></span> <span data-ttu-id="c9bb9-108">そのため、既定の環境で唯一のコマンドレットとプロバイダー、影響の大きい操作を指定する要求の確認。</span><span class="sxs-lookup"><span data-stu-id="c9bb9-108">Therefore, in the default environment, only cmdlets and providers that specify a high-impact action request confirmation.</span></span>

<span data-ttu-id="c9bb9-109">場合`Confirm`が false の場合、または`"-Confirm:$false`が指定されている、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出しが、ユーザーに確認を要求、`$ConfirmPreference`シェル変数は無視されます。</span><span class="sxs-lookup"><span data-stu-id="c9bb9-109">If `Confirm` is false or if `"-Confirm:$false` is specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation from the user, and the `$ConfirmPreference` shell variable is ignored.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9bb9-110">コメント</span><span class="sxs-lookup"><span data-stu-id="c9bb9-110">Remarks</span></span>

- <span data-ttu-id="c9bb9-111">指定されているコマンドレットとプロバイダーの`SupportsShouldProcess`、なく`ConfirmImpact`「中程度の影響」アクションでは、これらのアクションの処理、および、既定では確認できません。</span><span class="sxs-lookup"><span data-stu-id="c9bb9-111">For cmdlets and providers that specify `SupportsShouldProcess`, but not `ConfirmImpact`, those actions are handled as "medium impact" actions, and they will not prompt by default.</span></span> <span data-ttu-id="c9bb9-112">その影響のレベルが既定の設定より小さい、`$ConfirmPreference`ユーザー設定変数。</span><span class="sxs-lookup"><span data-stu-id="c9bb9-112">Their impact level is less than the default setting of the `$ConfirmPreference` preference variable.</span></span>

- <span data-ttu-id="c9bb9-113">ユーザーが指定されている場合、`Verbose`パラメーター、確認を求められましていない場合でも、操作が通知されます。</span><span class="sxs-lookup"><span data-stu-id="c9bb9-113">If the user specifies the `Verbose` parameter, they will be notified of the operation even if they are not prompted for confirmation.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9bb9-114">参照</span><span class="sxs-lookup"><span data-stu-id="c9bb9-114">See Also</span></span>

[<span data-ttu-id="c9bb9-115">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="c9bb9-115">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
