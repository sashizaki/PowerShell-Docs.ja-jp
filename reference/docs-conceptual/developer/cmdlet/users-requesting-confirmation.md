---
ms.date: 09/13/2016
ms.topic: reference
title: ユーザーの確認要求
description: ユーザーの確認要求
ms.openlocfilehash: 58dbe27635ca38886b728f585fec063645b3597e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646301"
---
# <a name="users-requesting-confirmation"></a><span data-ttu-id="96ced-103">ユーザーの確認要求</span><span class="sxs-lookup"><span data-stu-id="96ced-103">Users Requesting Confirmation</span></span>

<span data-ttu-id="96ced-104">コマンド `true` レットの属性宣言のパラメーターに値を指定すると `SupportsShouldProcess` 、ユーザーは `Confirm` コマンドプロンプトでパラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="96ced-104">When you specify a value of `true` for the `SupportsShouldProcess` parameter of the Cmdlet attribute declaration, users can specify the `Confirm` parameter at the command prompt.</span></span>

<span data-ttu-id="96ced-105">既定の環境では、ユーザーはパラメーターを指定することもできます。 `Confirm` `"-Confirm:$true` これにより、 [システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) のメソッドが呼び出されたときに確認が要求されます。</span><span class="sxs-lookup"><span data-stu-id="96ced-105">In the default environment, users can specify the `Confirm` parameter or `"-Confirm:$true` so that confirmation is requested when the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method is called.</span></span> <span data-ttu-id="96ced-106">これは、システムの管理をバイパス [します。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 影響の大きい操作の場合でも、確認要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="96ced-106">This bypasses [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) confirmation requests, even for high-impact operations.</span></span>

<span data-ttu-id="96ced-107">が指定されていない場合は、ユーザー `Confirm` [](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) `$ConfirmPreference` 設定変数が `ConfirmImpact` コマンドレットまたはプロバイダーの設定以上であるかどうかの確認を求めるメッセージが、システムによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="96ced-107">If `Confirm` is not specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation if the `$ConfirmPreference` preference variable is equal to or greater than the `ConfirmImpact` setting of the cmdlet or provider.</span></span> <span data-ttu-id="96ced-108">の既定の設定 `$ConfirmPreference` は High です。</span><span class="sxs-lookup"><span data-stu-id="96ced-108">The default setting of `$ConfirmPreference` is High.</span></span> <span data-ttu-id="96ced-109">そのため、既定の環境では、影響の大きいアクション要求の確認を指定するコマンドレットとプロバイダーのみが対象となります。</span><span class="sxs-lookup"><span data-stu-id="96ced-109">Therefore, in the default environment, only cmdlets and providers that specify a high-impact action request confirmation.</span></span>

<span data-ttu-id="96ced-110">が false の場合、またはが指定されている場合は、 `Confirm` `"-Confirm:$false` ユーザーからの確認要求が呼び出され、 [](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) `$ConfirmPreference` シェル変数は無視されます。</span><span class="sxs-lookup"><span data-stu-id="96ced-110">If `Confirm` is false or if `"-Confirm:$false` is specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation from the user, and the `$ConfirmPreference` shell variable is ignored.</span></span>

## <a name="remarks"></a><span data-ttu-id="96ced-111">解説</span><span class="sxs-lookup"><span data-stu-id="96ced-111">Remarks</span></span>

- <span data-ttu-id="96ced-112">を指定するコマンドレットとプロバイダーについては、 `SupportsShouldProcess` `ConfirmImpact` これらのアクションは "中程度の影響" アクションとして処理され、既定ではプロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="96ced-112">For cmdlets and providers that specify `SupportsShouldProcess`, but not `ConfirmImpact`, those actions are handled as "medium impact" actions, and they will not prompt by default.</span></span> <span data-ttu-id="96ced-113">影響レベルは、ユーザー設定変数の既定の設定よりも小さくなってい `$ConfirmPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="96ced-113">Their impact level is less than the default setting of the `$ConfirmPreference` preference variable.</span></span>

- <span data-ttu-id="96ced-114">ユーザーがパラメーターを指定すると `Verbose` 、確認メッセージが表示されない場合でも、操作が通知されます。</span><span class="sxs-lookup"><span data-stu-id="96ced-114">If the user specifies the `Verbose` parameter, they will be notified of the operation even if they are not prompted for confirmation.</span></span>

## <a name="see-also"></a><span data-ttu-id="96ced-115">参照</span><span class="sxs-lookup"><span data-stu-id="96ced-115">See Also</span></span>

[<span data-ttu-id="96ced-116">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="96ced-116">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
