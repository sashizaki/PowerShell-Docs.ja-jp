---
ms.date: 06/09/2017
title: ライセンスへの同意が必要なモジュール
description: この記事では、PowerShell ギャラリーで公開されているモジュールのうち、エンド ユーザー ライセンスの受け入れを必要とするものの取り扱い方法について説明します。
ms.openlocfilehash: a9486e10b10569ce8bcde47d5c8acf0796a93851
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656123"
---
# <a name="modules-requiring-license-acceptance"></a><span data-ttu-id="82101-103">ライセンスへの同意が必要なモジュール</span><span class="sxs-lookup"><span data-stu-id="82101-103">Modules Requiring License Acceptance</span></span>

## <a name="synopsis"></a><span data-ttu-id="82101-104">概要</span><span class="sxs-lookup"><span data-stu-id="82101-104">SYNOPSIS</span></span>

<span data-ttu-id="82101-105">モジュールの発行元によっては、法務部門から顧客に対し、PowerShell ギャラリーのモジュールをインストールする前にライセンスに明示的に同意するよう求める場合があります。</span><span class="sxs-lookup"><span data-stu-id="82101-105">Legal departments for some module publishers require that customers must explicitly accept the license before installing their module from PowerShell Gallery.</span></span> <span data-ttu-id="82101-106">ユーザーが、直接的か別のパッケージとの依存関係としてかにかかわらず、PowerShellGet を使用してモジュールのインストール、更新、または保存を行うときに、そのモジュールでユーザーにライセンスへの同意が求められている場合、ユーザーはライセンスに同意することを示す必要があります。そうしないと、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="82101-106">If a user installs, updates, or saves a module using PowerShellGet, whether directly or as a dependency for another package, and that module requires the user to agree to a license, the user must indicate they accept the license or the operation fails.</span></span>

## <a name="publish-requirements-for-modules"></a><span data-ttu-id="82101-107">モジュールの発行要件</span><span class="sxs-lookup"><span data-stu-id="82101-107">Publish Requirements for Modules</span></span>

<span data-ttu-id="82101-108">ユーザーにライセンスへの同意を求めるモジュールでは、次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="82101-108">Modules that would like to require users to accept license should fulfill following requirements:</span></span>

- <span data-ttu-id="82101-109">モジュール マニフェストの PSData セクションに「RequireLicenseAcceptance = $True」と記載する。</span><span class="sxs-lookup"><span data-stu-id="82101-109">PSData section of module manifest should include RequireLicenseAcceptance = $True.</span></span>
- <span data-ttu-id="82101-110">モジュールのルート ディレクトリに license.txt ファイルを含める。</span><span class="sxs-lookup"><span data-stu-id="82101-110">Module should contain license.txt file in root directory.</span></span>
- <span data-ttu-id="82101-111">モジュール マニフェストにライセンス URI を記載する。</span><span class="sxs-lookup"><span data-stu-id="82101-111">Module manifest should contain License Uri.</span></span>
- <span data-ttu-id="82101-112">PowerShellGet のフォーマット バージョン 2.0 以降を使用してモジュールを公開する。</span><span class="sxs-lookup"><span data-stu-id="82101-112">Module should be published with PowerShellGet Format Version 2.0 and above.</span></span>

## <a name="impact-on-installsaveupdate-module"></a><span data-ttu-id="82101-113">Install/Save/Update-Module に対する影響</span><span class="sxs-lookup"><span data-stu-id="82101-113">Impact on Install/Save/Update-Module</span></span>

- <span data-ttu-id="82101-114">Install、Save、Update コマンドレットでは、ユーザーがライセンスを確認した場合と同じ動作をする新しいパラメーター **AcceptLicense** がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="82101-114">Install/Save/Update cmdlets support a new parameter **AcceptLicense** that behaves as though the user saw the license.</span></span>
- <span data-ttu-id="82101-115">**RequiredLicenseAcceptance** が True で、 **AcceptLicense** が指定されていない場合、ユーザーには `license.txt` が表示され、次のプロンプトが表示されます: `Do you accept these license terms
  (Yes/No/YesToAll/NoToAll)`。</span><span class="sxs-lookup"><span data-stu-id="82101-115">If **RequiredLicenseAcceptance** is True and **AcceptLicense** is not specified, the user is shown the `license.txt`, and prompted with: `Do you accept these license terms
  (Yes/No/YesToAll/NoToAll)`.</span></span>
  - <span data-ttu-id="82101-116">ライセンスに同意した場合:</span><span class="sxs-lookup"><span data-stu-id="82101-116">If the license is accepted</span></span>
    - <span data-ttu-id="82101-117">**Save-Module:** ユーザーのシステムにモジュールがコピーされます</span><span class="sxs-lookup"><span data-stu-id="82101-117">**Save-Module:** the module is copied to the user's system</span></span>
    - <span data-ttu-id="82101-118">**Install-Module:** (スコープに基づいて) ユーザーのシステムの適切なフォルダーにモジュールがコピーされます</span><span class="sxs-lookup"><span data-stu-id="82101-118">**Install-Module:** the module is copied to the user's system to the proper folder (based on scope)</span></span>
    - <span data-ttu-id="82101-119">**Update-Module:** モジュールが更新されます。</span><span class="sxs-lookup"><span data-stu-id="82101-119">**Update-Module:** the module is updated.</span></span>
  - <span data-ttu-id="82101-120">ライセンスを拒否した場合:</span><span class="sxs-lookup"><span data-stu-id="82101-120">If the license is declined.</span></span>
    - <span data-ttu-id="82101-121">操作は取り消されます。</span><span class="sxs-lookup"><span data-stu-id="82101-121">Operation is canceled.</span></span>
    - <span data-ttu-id="82101-122">すべてのコマンドレットで、ライセンスへの同意が必要であることを示すメタデータ ( **requireLicenseAcceptance** および形式のバージョン) が確認されます</span><span class="sxs-lookup"><span data-stu-id="82101-122">All cmdlets check for the metadata ( **requireLicenseAcceptance** and Format Version) that says a license acceptance is required</span></span>
    - <span data-ttu-id="82101-123">クライアントの形式のバージョンが 2.0 よりも前の場合、操作は失敗し、ユーザーはクライアントを更新するように求められます。</span><span class="sxs-lookup"><span data-stu-id="82101-123">If format version of client is older than 2.0, operation fails and asks the user to update the client.</span></span>
    - <span data-ttu-id="82101-124">2\.0 よりも前の形式のバージョンを使用してモジュールが発行されている場合、requireLicenseAcceptance フラグは無視されます。</span><span class="sxs-lookup"><span data-stu-id="82101-124">If module was published with format version older than 2.0, requireLicenseAcceptance flag is ignored.</span></span>

## <a name="module-dependencies"></a><span data-ttu-id="82101-125">モジュールの依存関係</span><span class="sxs-lookup"><span data-stu-id="82101-125">Module Dependencies</span></span>

- <span data-ttu-id="82101-126">インストール/保存/更新操作中に、依存モジュール (目的のモジュールに依存する別のモジュール) でライセンスへの同意が求められた場合、上記のライセンスへの同意が必要です。</span><span class="sxs-lookup"><span data-stu-id="82101-126">During Install/Save/Update operation, if a dependent module(something else depends on the module) requires license acceptance, then the license acceptance behavior (above) is required.</span></span>
- <span data-ttu-id="82101-127">該当するモジュールのバージョンがシステムへインストール済みであるとローカル カタログに記載されている場合、このライセンス チェックは省略されます。</span><span class="sxs-lookup"><span data-stu-id="82101-127">If the module version is already listed in the local catalog as being installed on the system, we would bypass the license checking.</span></span>
- <span data-ttu-id="82101-128">インストール/保存/更新操作中に、依存モジュールでライセンスが必要とされ、ライセンスへの同意が行われなかった場合、操作は失敗し、インストール/保存/更新が失敗したパッケージに対して通常の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="82101-128">During Install/Save/Update operation, if a dependent module requires a license, and the license acceptance does not occur, the operation fails and follows normal processes for the package failed to install/save/update.</span></span>

## <a name="impact-on--force"></a><span data-ttu-id="82101-129">-Force に対する影響</span><span class="sxs-lookup"><span data-stu-id="82101-129">Impact on -Force</span></span>

<span data-ttu-id="82101-130">`–Force` を指定しても、ライセンスへの同意は行われません。</span><span class="sxs-lookup"><span data-stu-id="82101-130">Specifying `–Force` is NOT sufficient to accept a license.</span></span> <span data-ttu-id="82101-131">インストールを行うには、`–AcceptLicense` を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82101-131">`–AcceptLicense` is required for permission to install.</span></span> <span data-ttu-id="82101-132">`–Force` を指定した場合に、RequiredLicenseAcceptance が True であり `–AcceptLicense` を指定していないと、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="82101-132">If `–Force` is specified, RequiredLicenseAcceptance is True, and `–AcceptLicense` is NOT specified, the operation fails.</span></span>

## <a name="examples"></a><span data-ttu-id="82101-133">例</span><span class="sxs-lookup"><span data-stu-id="82101-133">EXAMPLES</span></span>

### <a name="example-1-update-module-manifest-to-require-license-acceptance"></a><span data-ttu-id="82101-134">例 1: ライセンスへの同意を求めるようにモジュール マニフェストを更新する</span><span class="sxs-lookup"><span data-stu-id="82101-134">Example 1: Update Module Manifest to require license acceptance</span></span>

```powershell
Update-ModuleManifest -Path C:\modulemanifest.psd1 -RequireLicenseAcceptance -PrivateData @{
    PSData = @{
        # Flag to indicate whether the module requires explicit user acceptance
        RequireLicenseAcceptance = $true
    } # End of PSData hashtable

 } # End of PrivateData hashtable
```

<span data-ttu-id="82101-135">次のコマンドでは、マニフェスト ファイルを更新して RequireLicenseAcceptance フラグを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="82101-135">This command updates the manifest file and sets the RequireLicenseAcceptance flag to true.</span></span>

### <a name="example-2-install-module-requiring-license-acceptance"></a><span data-ttu-id="82101-136">例 2: ライセンスへの同意が必要なモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="82101-136">Example 2: Install Module requiring license acceptance</span></span>

```powershell
Install-Module -Name ModuleRequireLicenseAcceptance
```

```Output
License Acceptance

License 2.0
Copyright (c) 2016 PowerShell Team
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.

Do you accept the license terms for module 'ModuleRequireLicenseAcceptance'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="82101-137">次のコマンドでは、`license.txt` ファイルのライセンスが表示され、このライセンスへの同意がユーザーに求められます。</span><span class="sxs-lookup"><span data-stu-id="82101-137">This command shows the license from `license.txt` file and prompts the user to accept the license.</span></span>

### <a name="example-3-install-module-requiring-license-acceptance-with--acceptlicense"></a><span data-ttu-id="82101-138">例 3: -AcceptLicense を使用してライセンスへの同意が必要なモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="82101-138">Example 3: Install Module requiring license acceptance with -AcceptLicense</span></span>

```powershell
Install-Module -Name ModuleRequireLicenseAcceptance -AcceptLicense
```

<span data-ttu-id="82101-139">ライセンスへの同意を求めることなく、モジュールがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="82101-139">Module is installed without any prompt to accept license.</span></span>

### <a name="example-4-install-module-requiring-license-acceptance-with--force"></a><span data-ttu-id="82101-140">例 4: -Force を使用してライセンスへの同意が必要なモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="82101-140">Example 4: Install Module requiring license acceptance with -Force</span></span>

```powershell
Install-Module -Name ModuleRequireLicenseAcceptance -Force
```

```Output
PackageManagement\Install-Package : License Acceptance is required for module 'ModuleRequireLicenseAcceptance'. Please specify '-AcceptLicense' to perform this operation.
At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.1.3.3\PSModule.psm1:1837 char:21
+ ...          $null = PackageManagement\Install-Package @PSBoundParameters
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (Microsoft.Power....InstallPackage:InstallPackage) [Install-Package], E
   xception
    + FullyQualifiedErrorId : ForceAcceptLicense,Install-PackageUtility,Microsoft.PowerShell.PackageManagement.Cmdlets
   .InstallPackage
```

### <a name="example-5-install-module-with-dependencies-requiring-license-acceptance"></a><span data-ttu-id="82101-141">例 5: ライセンスへの同意が必要な依存関係があるモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="82101-141">Example 5: Install Module with dependencies requiring license acceptance</span></span>

<span data-ttu-id="82101-142">モジュール **ModuleWithDependency** はモジュール **ModuleRequireLicenseAcceptance** に依存しています。</span><span class="sxs-lookup"><span data-stu-id="82101-142">Module **ModuleWithDependency** depends on module **ModuleRequireLicenseAcceptance**.</span></span> <span data-ttu-id="82101-143">ユーザーにはライセンスへの同意が求められます。</span><span class="sxs-lookup"><span data-stu-id="82101-143">User is prompted to accept license.</span></span>

```powershell
Install-Module -Name ModuleWithDependency
```

```Output
License Acceptance
MIT License 2.0
Copyright (c) 2016 PowerShell Team
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.

Do you accept the license terms for module 'ModuleRequireLicenseAcceptance'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

### <a name="example-6-install-module-with-dependencies-requiring-license-acceptance-and--acceptlicense"></a><span data-ttu-id="82101-144">例 6: -AcceptLicense を使用してライセンスへの同意が必要な依存関係があるモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="82101-144">Example 6: Install Module with dependencies requiring license acceptance and -AcceptLicense</span></span>

<span data-ttu-id="82101-145">モジュール **ModuleWithDependency** はモジュール **ModuleRequireLicenseAcceptance** に依存しています。</span><span class="sxs-lookup"><span data-stu-id="82101-145">Module **ModuleWithDependency** depends on module **ModuleRequireLicenseAcceptance**.</span></span> <span data-ttu-id="82101-146">**AcceptLicense** を指定したため、ユーザーにライセンスへの同意は求められません。</span><span class="sxs-lookup"><span data-stu-id="82101-146">User is not prompted to accept license as **AcceptLicense** is specified.</span></span>

```powershell
Install-Module -Name ModuleWithDependency -AcceptLicense
```

### <a name="example-7-install-module-requiring-license-acceptance-on-a-client-older-than-psgetformatversion-20"></a><span data-ttu-id="82101-147">例 7: PSGetFormatVersion 2.0 以前のクライアントでライセンスへの同意が必要なモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="82101-147">Example 7: Install module requiring license acceptance on a client older than PSGetFormatVersion 2.0</span></span>

```powershell
Install-Module -Name ModuleRequireLicenseAcceptance
```

```Output
WARNING: The specified module 'ModuleRequireLicenseAcceptance' with PowerShellGetFormatVersion
'2.0' is not supported by the current version of PowerShellGet. Get the latest version of the
PowerShellGet module to install this module, 'ModuleRequireLicenseAcceptance'.
```

### <a name="example-8-save-module-requiring-license-acceptance"></a><span data-ttu-id="82101-148">例 8: ライセンスへの同意が必要なモジュールを保存する</span><span class="sxs-lookup"><span data-stu-id="82101-148">Example 8: Save Module requiring license acceptance</span></span>

```powershell
Save-Module -Name ModuleRequireLicenseAcceptance -Path C:\Saved
```

```Output
License Acceptance

License 2.0
Copyright (c) 2016 PowerShell Team
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.

Do you accept the license terms for module 'ModuleRequireLicenseAcceptance'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="82101-149">次のコマンドでは、`license.txt` ファイルのライセンスが表示され、このライセンスへの同意がユーザーに求められます。</span><span class="sxs-lookup"><span data-stu-id="82101-149">This command shows the license from `license.txt` file and prompts the user to accept the license.</span></span>

### <a name="example-9-save-module-requiring-license-acceptance-with--acceptlicense"></a><span data-ttu-id="82101-150">例 9: -AcceptLicense を使用してライセンスへの同意が必要なモジュールを保存する</span><span class="sxs-lookup"><span data-stu-id="82101-150">Example 9: Save Module requiring license acceptance with -AcceptLicense</span></span>

```powershell
Save-Module -Name ModuleRequireLicenseAcceptance -AcceptLicense -Path C:\Saved
```

<span data-ttu-id="82101-151">ライセンスへの同意を求めることなく、モジュールが保存されます。</span><span class="sxs-lookup"><span data-stu-id="82101-151">Module is saved without any prompt to accept license.</span></span>

### <a name="example-10-update-module-requiring-license-acceptance"></a><span data-ttu-id="82101-152">例 10: ライセンスへの同意が必要なモジュールを更新する</span><span class="sxs-lookup"><span data-stu-id="82101-152">Example 10: Update Module requiring license acceptance</span></span>

```powershell
Update-Module -Name ModuleRequireLicenseAcceptance
```

```Output
License Acceptance

License 2.0
Copyright (c) 2016 PowerShell Team
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.

Do you accept the license terms for module 'ModuleRequireLicenseAcceptance'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="82101-153">次のコマンドでは、`license.txt` ファイルのライセンスが表示され、このライセンスへの同意がユーザーに求められます。</span><span class="sxs-lookup"><span data-stu-id="82101-153">This command shows the license from `license.txt` file and prompts the user to accept the license.</span></span>

### <a name="example-11-update-module-requiring-license-acceptance-with--acceptlicense"></a><span data-ttu-id="82101-154">例 11: -AcceptLicense を使用してライセンスへの同意が必要なモジュールを更新する</span><span class="sxs-lookup"><span data-stu-id="82101-154">Example 11: Update Module requiring license acceptance with -AcceptLicense</span></span>

```powershell
Update-Module -Name ModuleRequireLicenseAcceptance -AcceptLicense
```

<span data-ttu-id="82101-155">ライセンスへの同意を求めることなく、モジュールが更新されます。</span><span class="sxs-lookup"><span data-stu-id="82101-155">Module is updated without any prompt to accept license.</span></span>

## <a name="more-details"></a><span data-ttu-id="82101-156">詳細</span><span class="sxs-lookup"><span data-stu-id="82101-156">More details</span></span>

[<span data-ttu-id="82101-157">スクリプトのライセンス同意リクエスト</span><span class="sxs-lookup"><span data-stu-id="82101-157">Require License Acceptance for Scripts</span></span>](./script-license-acceptance.md)

[<span data-ttu-id="82101-158">PowerShellGallery でのライセンス同意リクエストのサポート</span><span class="sxs-lookup"><span data-stu-id="82101-158">Require License Acceptance support on PowerShellGallery</span></span>](../how-to/working-with-packages/packages-that-require-license-acceptance.md)

[<span data-ttu-id="82101-159">Azure Automation へのデプロイに表示されるライセンス同意リクエスト</span><span class="sxs-lookup"><span data-stu-id="82101-159">Require License Acceptance on Deploy to Azure Automation</span></span>](../how-to/working-with-packages/deploy-to-azure-automation.md)
