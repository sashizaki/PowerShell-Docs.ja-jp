---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: bed1186c10082bbdac7249503bf623678f13fccd
ms.sourcegitcommit: c3f1a83b59484651119630f3089aa51b6e7d4c3c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2018
ms.locfileid: "39267941"
---
# <a name="unified-and-consistent-state-and-status-representation"></a><span data-ttu-id="14c24-102">統一された一貫性のある状態とステータスの表現</span><span class="sxs-lookup"><span data-stu-id="14c24-102">Unified and Consistent State and Status Representation</span></span>

<span data-ttu-id="14c24-103">今回のリリースでは、LCM 状態と DSC ステータスのビルドの自動化に対して、一連の拡張機能が加えられました。</span><span class="sxs-lookup"><span data-stu-id="14c24-103">A series of enhancements have been made in this release for automations built LCM state and DSC status.</span></span> <span data-ttu-id="14c24-104">これには、統一された一貫性のある状態とステータスの表現、`Get-DscConfigurationStatus` コマンドレットから返されるステータス オブジェクトの管理しやすい日時プロパティ、`Get-DscLocalConfigurationManager` コマンドレットから返される拡張された LCM 状態の詳細プロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="14c24-104">These include unified and consistent state and status representations, manageable datetime property of status objects returned by `Get-DscConfigurationStatus` cmdlet and enhanced LCM state details property returned by `Get-DscLocalConfigurationManager` cmdlet.</span></span>

<span data-ttu-id="14c24-105">LCM 状態と DSC 操作ステータスの形式を再検討し、次の規則に従って統合されました。</span><span class="sxs-lookup"><span data-stu-id="14c24-105">The representation of LCM state and DSC operation status are revisited and unified according to following rules:</span></span>

1. <span data-ttu-id="14c24-106">未処理のリソースは、LCM 状態と DSC ステータスに影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="14c24-106">Notprocessed resource does not impact LCM state and DSC status.</span></span>
2. <span data-ttu-id="14c24-107">LCM は、再起動を要求するリソースに到達すると、リソースの処理を停止します。</span><span class="sxs-lookup"><span data-stu-id="14c24-107">LCM stop processing further resources once it encounters a resource that requests reboot.</span></span>
3. <span data-ttu-id="14c24-108">再起動を要求するリソースは、再起動が実際に発生するまで、必要な状態になりません。</span><span class="sxs-lookup"><span data-stu-id="14c24-108">A resource that requests reboot is not in desired state until reboot actually happens.</span></span>
4. <span data-ttu-id="14c24-109">失敗したリソースを検出した場合は、そのリソースに依存していない限り、LCM は他のリソースの処理を続けます。</span><span class="sxs-lookup"><span data-stu-id="14c24-109">After encountering a resource that fails, LCM keeps processing further resources as long as they are not dependent on the failure one.</span></span>
5. <span data-ttu-id="14c24-110">`Get-DscConfigurationStatus` コマンドレットによって返される状態の全体は、すべてのリソースのステータスのスーパー セットです。</span><span class="sxs-lookup"><span data-stu-id="14c24-110">The overall status returned by `Get-DscConfigurationStatus` cmdlet is the super set of all resources' status.</span></span>
6. <span data-ttu-id="14c24-111">PendingReboot 状態は、PendingConfiguration 状態のスーパーセットです。</span><span class="sxs-lookup"><span data-stu-id="14c24-111">The PendingReboot state is a superset of PendingConfiguration state.</span></span>

<span data-ttu-id="14c24-112">次の表は、いくつかの一般的なシナリオでのプロパティに関連した状態とステータスの結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="14c24-112">The table below illustrates the resultant state and status related properties under a few typical scenarios.</span></span>

| <span data-ttu-id="14c24-113">シナリオ</span><span class="sxs-lookup"><span data-stu-id="14c24-113">Scenario</span></span>                        | <span data-ttu-id="14c24-114">LCMState</span><span class="sxs-lookup"><span data-stu-id="14c24-114">LCMState</span></span>             | <span data-ttu-id="14c24-115">状態</span><span class="sxs-lookup"><span data-stu-id="14c24-115">Status</span></span>     | <span data-ttu-id="14c24-116">Reboot Requested</span><span class="sxs-lookup"><span data-stu-id="14c24-116">Reboot Requested</span></span> | <span data-ttu-id="14c24-117">ResourcesInDesiredState</span><span class="sxs-lookup"><span data-stu-id="14c24-117">ResourcesInDesiredState</span></span>   | <span data-ttu-id="14c24-118">ResourcesNotInDesiredState</span><span class="sxs-lookup"><span data-stu-id="14c24-118">ResourcesNotInDesiredState</span></span> |
|---------------------------------|----------------------|------------|---------------|------------------------------|--------------------------------|
| <span data-ttu-id="14c24-119">S**^**</span><span class="sxs-lookup"><span data-stu-id="14c24-119">S**^**</span></span>                          | <span data-ttu-id="14c24-120">アイドル</span><span class="sxs-lookup"><span data-stu-id="14c24-120">Idle</span></span>                 | <span data-ttu-id="14c24-121">成功</span><span class="sxs-lookup"><span data-stu-id="14c24-121">Success</span></span>    | <span data-ttu-id="14c24-122">$false</span><span class="sxs-lookup"><span data-stu-id="14c24-122">$false</span></span>        | <span data-ttu-id="14c24-123">S</span><span class="sxs-lookup"><span data-stu-id="14c24-123">S</span></span>                            | <span data-ttu-id="14c24-124">$null</span><span class="sxs-lookup"><span data-stu-id="14c24-124">$null</span></span>                          |
| <span data-ttu-id="14c24-125">F**^**</span><span class="sxs-lookup"><span data-stu-id="14c24-125">F**^**</span></span>                          | <span data-ttu-id="14c24-126">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="14c24-126">PendingConfiguration</span></span> | <span data-ttu-id="14c24-127">障害</span><span class="sxs-lookup"><span data-stu-id="14c24-127">Failure</span></span>    | <span data-ttu-id="14c24-128">$false</span><span class="sxs-lookup"><span data-stu-id="14c24-128">$false</span></span>        | <span data-ttu-id="14c24-129">$null</span><span class="sxs-lookup"><span data-stu-id="14c24-129">$null</span></span>                        | <span data-ttu-id="14c24-130">F</span><span class="sxs-lookup"><span data-stu-id="14c24-130">F</span></span>                              |
| <span data-ttu-id="14c24-131">S、F</span><span class="sxs-lookup"><span data-stu-id="14c24-131">S,F</span></span>                             | <span data-ttu-id="14c24-132">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="14c24-132">PendingConfiguration</span></span> | <span data-ttu-id="14c24-133">障害</span><span class="sxs-lookup"><span data-stu-id="14c24-133">Failure</span></span>    | <span data-ttu-id="14c24-134">$false</span><span class="sxs-lookup"><span data-stu-id="14c24-134">$false</span></span>        | <span data-ttu-id="14c24-135">S</span><span class="sxs-lookup"><span data-stu-id="14c24-135">S</span></span>                            | <span data-ttu-id="14c24-136">F</span><span class="sxs-lookup"><span data-stu-id="14c24-136">F</span></span>                              |
| <span data-ttu-id="14c24-137">F、S</span><span class="sxs-lookup"><span data-stu-id="14c24-137">F,S</span></span>                             | <span data-ttu-id="14c24-138">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="14c24-138">PendingConfiguration</span></span> | <span data-ttu-id="14c24-139">障害</span><span class="sxs-lookup"><span data-stu-id="14c24-139">Failure</span></span>    | <span data-ttu-id="14c24-140">$false</span><span class="sxs-lookup"><span data-stu-id="14c24-140">$false</span></span>        | <span data-ttu-id="14c24-141">S</span><span class="sxs-lookup"><span data-stu-id="14c24-141">S</span></span>                            | <span data-ttu-id="14c24-142">F</span><span class="sxs-lookup"><span data-stu-id="14c24-142">F</span></span>                              |
| <span data-ttu-id="14c24-143">S<sub>1</sub>、F、S<sub>2</sub></span><span class="sxs-lookup"><span data-stu-id="14c24-143">S<sub>1</sub>, F, S<sub>2</sub></span></span> | <span data-ttu-id="14c24-144">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="14c24-144">PendingConfiguration</span></span> | <span data-ttu-id="14c24-145">障害</span><span class="sxs-lookup"><span data-stu-id="14c24-145">Failure</span></span>    | <span data-ttu-id="14c24-146">$false</span><span class="sxs-lookup"><span data-stu-id="14c24-146">$false</span></span>        | <span data-ttu-id="14c24-147">S<sub>1</sub>、S<sub>2</sub></span><span class="sxs-lookup"><span data-stu-id="14c24-147">S<sub>1</sub>, S<sub>2</sub></span></span> | <span data-ttu-id="14c24-148">F</span><span class="sxs-lookup"><span data-stu-id="14c24-148">F</span></span>                              |
| <span data-ttu-id="14c24-149">F<sub>1</sub>、S、F<sub>2</sub></span><span class="sxs-lookup"><span data-stu-id="14c24-149">F<sub>1</sub>, S, F<sub>2</sub></span></span> | <span data-ttu-id="14c24-150">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="14c24-150">PendingConfiguration</span></span> | <span data-ttu-id="14c24-151">障害</span><span class="sxs-lookup"><span data-stu-id="14c24-151">Failure</span></span>    | <span data-ttu-id="14c24-152">$false</span><span class="sxs-lookup"><span data-stu-id="14c24-152">$false</span></span>        | <span data-ttu-id="14c24-153">S</span><span class="sxs-lookup"><span data-stu-id="14c24-153">S</span></span>                            | <span data-ttu-id="14c24-154">F<sub>1</sub>、F<sub>2</sub></span><span class="sxs-lookup"><span data-stu-id="14c24-154">F<sub>1</sub>, F<sub>2</sub></span></span>   |
| <span data-ttu-id="14c24-155">S、r</span><span class="sxs-lookup"><span data-stu-id="14c24-155">S, r</span></span>                            | <span data-ttu-id="14c24-156">PendingReboot</span><span class="sxs-lookup"><span data-stu-id="14c24-156">PendingReboot</span></span>        | <span data-ttu-id="14c24-157">成功</span><span class="sxs-lookup"><span data-stu-id="14c24-157">Success</span></span>    | <span data-ttu-id="14c24-158">$true</span><span class="sxs-lookup"><span data-stu-id="14c24-158">$true</span></span>         | <span data-ttu-id="14c24-159">S</span><span class="sxs-lookup"><span data-stu-id="14c24-159">S</span></span>                            | <span data-ttu-id="14c24-160">r</span><span class="sxs-lookup"><span data-stu-id="14c24-160">r</span></span>                              |
| <span data-ttu-id="14c24-161">F、r</span><span class="sxs-lookup"><span data-stu-id="14c24-161">F, r</span></span>                            | <span data-ttu-id="14c24-162">PendingReboot</span><span class="sxs-lookup"><span data-stu-id="14c24-162">PendingReboot</span></span>        | <span data-ttu-id="14c24-163">障害</span><span class="sxs-lookup"><span data-stu-id="14c24-163">Failure</span></span>    | <span data-ttu-id="14c24-164">$true</span><span class="sxs-lookup"><span data-stu-id="14c24-164">$true</span></span>         | <span data-ttu-id="14c24-165">$null</span><span class="sxs-lookup"><span data-stu-id="14c24-165">$null</span></span>                        | <span data-ttu-id="14c24-166">F、r</span><span class="sxs-lookup"><span data-stu-id="14c24-166">F, r</span></span>                           |
| <span data-ttu-id="14c24-167">r、S</span><span class="sxs-lookup"><span data-stu-id="14c24-167">r, S</span></span>                            | <span data-ttu-id="14c24-168">PendingReboot</span><span class="sxs-lookup"><span data-stu-id="14c24-168">PendingReboot</span></span>        | <span data-ttu-id="14c24-169">成功</span><span class="sxs-lookup"><span data-stu-id="14c24-169">Success</span></span>    | <span data-ttu-id="14c24-170">$true</span><span class="sxs-lookup"><span data-stu-id="14c24-170">$true</span></span>         | <span data-ttu-id="14c24-171">$null</span><span class="sxs-lookup"><span data-stu-id="14c24-171">$null</span></span>                        | <span data-ttu-id="14c24-172">r</span><span class="sxs-lookup"><span data-stu-id="14c24-172">r</span></span>                              |
| <span data-ttu-id="14c24-173">r、F</span><span class="sxs-lookup"><span data-stu-id="14c24-173">r, F</span></span>                            | <span data-ttu-id="14c24-174">PendingReboot</span><span class="sxs-lookup"><span data-stu-id="14c24-174">PendingReboot</span></span>        | <span data-ttu-id="14c24-175">成功</span><span class="sxs-lookup"><span data-stu-id="14c24-175">Success</span></span>    | <span data-ttu-id="14c24-176">$true</span><span class="sxs-lookup"><span data-stu-id="14c24-176">$true</span></span>         | <span data-ttu-id="14c24-177">$null</span><span class="sxs-lookup"><span data-stu-id="14c24-177">$null</span></span>                        | <span data-ttu-id="14c24-178">r</span><span class="sxs-lookup"><span data-stu-id="14c24-178">r</span></span>                              |

- <span data-ttu-id="14c24-179">S<sub>i</sub>: 一連のリソースが正常に適用された</span><span class="sxs-lookup"><span data-stu-id="14c24-179">S<sub>i</sub>: A series of resources that applied successfully</span></span>
- <span data-ttu-id="14c24-180">F<sub>i</sub>: 一連のリソースの適用に失敗した</span><span class="sxs-lookup"><span data-stu-id="14c24-180">F<sub>i</sub>: A series of resources that applied unsuccessfully</span></span>
- <span data-ttu-id="14c24-181">r: 再起動が必要なリソース</span><span class="sxs-lookup"><span data-stu-id="14c24-181">r: A resource that requires reboot</span></span>

```powershell
$LCMState = (Get-DscLocalConfigurationManager).LCMState
$Status = (Get-DscConfigurationStatus).Status

$RebootRequested = (Get-DscConfigurationStatus).RebootRequested

$ResourcesInDesiredState = (Get-DscConfigurationStatus).ResourcesInDesiredState

$ResourcesNotInDesiredState = (Get-DscConfigurationStatus).ResourcesNotInDesiredState
```

## <a name="enhancement-in-get-dscconfigurationstatus-cmdlet"></a><span data-ttu-id="14c24-182">Get-DscConfigurationStatus コマンドレットの機能拡張</span><span class="sxs-lookup"><span data-stu-id="14c24-182">Enhancement in Get-DscConfigurationStatus cmdlet</span></span>

<span data-ttu-id="14c24-183">このリリースでは、`Get-DscConfigurationStatus` コマンドレットのいくつかの機能が拡張されました。</span><span class="sxs-lookup"><span data-stu-id="14c24-183">A few enhancements have been made to `Get-DscConfigurationStatus` cmdlet in this release.</span></span> <span data-ttu-id="14c24-184">以前は、コマンドレットによって返されるオブジェクトの StartDate プロパティは文字列型でした。</span><span class="sxs-lookup"><span data-stu-id="14c24-184">Previously, the StartDate property of objects returned by the cmdlet is of String type.</span></span> <span data-ttu-id="14c24-185">今では、Datetime 型になったため、Datetime オブジェクトに備わっているプロパティに基づいて複雑な選択やフィルター処理を実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="14c24-185">Now, it is of Datetime type, which enables complex selecting and filtering easier based on the intrinsic properties of a Datetime object.</span></span>

```powershell
(Get-DscConfigurationStatus).StartDate | Format-List *

DateTime    : Friday, November 13, 2015 1:39:44 PM
Date        : 11/13/2015 12:00:00 AM
Day         : 13
DayOfWeek   : Friday
DayOfYear   : 317
Hour        : 13
Kind        : Local
Millisecond : 886
Minute      : 39
Month       : 11
Second      : 44
Ticks       : 635830187848860000
TimeOfDay   : 13:39:44.8860000
Year        : 2015
```

<span data-ttu-id="14c24-186">今日と同じ曜日に発生したすべての DSC 操作レコードを返す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="14c24-186">The following example returns all DSC operation records that happened on the same day of week as the current day.</span></span>

```powershell
(Get-DscConfigurationStatus –All) | Where-Object { $_.startdate.dayofweek -eq (Get-Date).DayOfWeek }
```

<span data-ttu-id="14c24-187">ノードの構成を変更しない操作 (つまり、読み取り専用の操作) のレコードは除外されます。</span><span class="sxs-lookup"><span data-stu-id="14c24-187">Records of operations that do not make changes to node’s configuration (i.e. read only operations) are eliminated.</span></span> <span data-ttu-id="14c24-188">そのため、`Test-DscConfiguration` と `Get-DscConfiguration` は、`Get-DscConfigurationStatus` コマンドレットから返されるオブジェクトで効果的に操作できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="14c24-188">Therefore, `Test-DscConfiguration`, `Get-DscConfiguration` operations are no longer adulterated in returned objects from `Get-DscConfigurationStatus` cmdlet.</span></span> <span data-ttu-id="14c24-189">メタ構成の設定操作のレコードが `Get-DscConfigurationStatus` コマンドレットの戻り値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="14c24-189">Records of meta configuration setting operation is added to the return of `Get-DscConfigurationStatus` cmdlet.</span></span>

<span data-ttu-id="14c24-190">次の例では、`Get-DscConfigurationStatus –All` コマンドレットから返される結果を示します。</span><span class="sxs-lookup"><span data-stu-id="14c24-190">Following is an example of result returned from `Get-DscConfigurationStatus –All` cmdlet.</span></span>

```output
All configuration operations:

Status StartDate Type RebootRequested
------ --------- ---- ---------------
Success 11/13/2015 11:38:16 AM Consistency False
Success 11/13/2015 11:23:16 AM Reboot False
Success 11/13/2015 11:21:43 AM Reboot True
Success 11/13/2015 11:20:44 AM Initial True
Success 11/13/2015 11:20:44 AM LocalConfigurationManager False
```

## <a name="enhancement-in-get-dsclocalconfigurationmanager-cmdlet"></a><span data-ttu-id="14c24-191">Get-DscLocalConfigurationManager コマンドレットの機能拡張</span><span class="sxs-lookup"><span data-stu-id="14c24-191">Enhancement in Get-DscLocalConfigurationManager cmdlet</span></span>

<span data-ttu-id="14c24-192">`Get-DscLocalConfigurationManager` コマンドレットから返されるオブジェクトに、新しい LCMStateDetail フィールドが追加されました。</span><span class="sxs-lookup"><span data-stu-id="14c24-192">A new field of LCMStateDetail is added to the object returned from `Get-DscLocalConfigurationManager` cmdlet.</span></span> <span data-ttu-id="14c24-193">このフィールドは、LCMState が "ビジー" の時にデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="14c24-193">This field is populated when LCMState is "Busy".</span></span> <span data-ttu-id="14c24-194">これは、次のコマンドレットで取得できます。</span><span class="sxs-lookup"><span data-stu-id="14c24-194">It can be retrieved by following cmdlet:</span></span>

```powershell
(Get-DscLocalConfigurationManager).LCMStateDetail
```

<span data-ttu-id="14c24-195">リモート ノードで 2 回のリブートを必要とする構成を継続的に監視した場合の出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="14c24-195">Following is an example output of a continuous monitoring on a configuration that requires two reboots on a remote node.</span></span>

```output
Start a configuration that requires two reboots

Monitor LCM State:
LCM State: Busy, LCM is applying a new configuration.
LCM State: PendingReboot,
Machine is rebooting...
LCM State: Busy, LCM is continuing applying configuration after last reboot.
LCM State: PendingReboot,
Machine is rebooting...
LCM State: Busy, LCM is continuing applying configuration after last reboot.
LCM State: Idle,
LCM State: Busy, LCM is performing a consistency check.
LCM State: Idle,
```