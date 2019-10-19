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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369251"
---
# <a name="users-requesting-confirmation"></a><span data-ttu-id="c1631-102">ユーザーの確認要求</span><span class="sxs-lookup"><span data-stu-id="c1631-102">Users Requesting Confirmation</span></span>

<span data-ttu-id="c1631-103">コマンドレットの属性宣言の `SupportsShouldProcess` パラメーターに値 `true` を指定すると、ユーザーはコマンドプロンプトで `Confirm` パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c1631-103">When you specify a value of `true` for the `SupportsShouldProcess` parameter of the Cmdlet attribute declaration, users can specify the `Confirm` parameter at the command prompt.</span></span>

<span data-ttu-id="c1631-104">既定の環境では、ユーザーは `Confirm` パラメーターまたは `"-Confirm:$true` を指定できます。これにより、[システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)のメソッドが呼び出されたときに確認が要求されます。</span><span class="sxs-lookup"><span data-stu-id="c1631-104">In the default environment, users can specify the `Confirm` parameter or `"-Confirm:$true` so that confirmation is requested when the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method is called.</span></span> <span data-ttu-id="c1631-105">これは、システムの管理をバイパス[します。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)影響の大きい操作の場合でも、確認要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="c1631-105">This bypasses [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) confirmation requests, even for high-impact operations.</span></span>

<span data-ttu-id="c1631-106">@No__t-0 が指定されていない場合は、@no__t 2 つのユーザー設定変数が、コマンドレットまたはプロバイダーの `ConfirmImpact` の設定以上であるかどうかの確認を求めるメッセージ[が呼び出されます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)</span><span class="sxs-lookup"><span data-stu-id="c1631-106">If `Confirm` is not specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation if the `$ConfirmPreference` preference variable is equal to or greater than the `ConfirmImpact` setting of the cmdlet or provider.</span></span> <span data-ttu-id="c1631-107">@No__t-0 の既定の設定は High です。</span><span class="sxs-lookup"><span data-stu-id="c1631-107">The default setting of `$ConfirmPreference` is High.</span></span> <span data-ttu-id="c1631-108">そのため、既定の環境では、影響の大きいアクション要求の確認を指定するコマンドレットとプロバイダーのみが対象となります。</span><span class="sxs-lookup"><span data-stu-id="c1631-108">Therefore, in the default environment, only cmdlets and providers that specify a high-impact action request confirmation.</span></span>

<span data-ttu-id="c1631-109">@No__t-0 が false の場合、または `"-Confirm:$false` を指定した場合[は、ユーザー](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)からの確認が要求され、@no__t 3 つのシェル変数は無視されます。</span><span class="sxs-lookup"><span data-stu-id="c1631-109">If `Confirm` is false or if `"-Confirm:$false` is specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation from the user, and the `$ConfirmPreference` shell variable is ignored.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1631-110">コメント</span><span class="sxs-lookup"><span data-stu-id="c1631-110">Remarks</span></span>

- <span data-ttu-id="c1631-111">@No__t-1 ではなく `SupportsShouldProcess` を指定するコマンドレットとプロバイダーでは、これらのアクションは "中程度の影響" アクションとして処理され、既定ではプロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="c1631-111">For cmdlets and providers that specify `SupportsShouldProcess`, but not `ConfirmImpact`, those actions are handled as "medium impact" actions, and they will not prompt by default.</span></span> <span data-ttu-id="c1631-112">影響レベルは、@no__t のユーザー設定変数の既定の設定よりも小さくなっています。</span><span class="sxs-lookup"><span data-stu-id="c1631-112">Their impact level is less than the default setting of the `$ConfirmPreference` preference variable.</span></span>

- <span data-ttu-id="c1631-113">ユーザーが `Verbose` パラメーターを指定した場合、確認メッセージが表示されなくても操作が通知されます。</span><span class="sxs-lookup"><span data-stu-id="c1631-113">If the user specifies the `Verbose` parameter, they will be notified of the operation even if they are not prompted for confirmation.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1631-114">参照</span><span class="sxs-lookup"><span data-stu-id="c1631-114">See Also</span></span>

[<span data-ttu-id="c1631-115">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="c1631-115">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)