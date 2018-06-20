---
ms.date: 06/09/2017
schema: 2.0.0
keywords: powershell
title: ライセンスへの同意が必要なモジュール
ms.openlocfilehash: fe197ea271e18580a221ad4d5245b685bd81775b
ms.sourcegitcommit: e9ad4d85fd7eb72fb5bc37f6ca3ae1282ae3c6d7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
ms.locfileid: "34048476"
---
# <a name="modules-requiring-license-acceptance"></a>ライセンスへの同意が必要なモジュール

## <a name="synopsis"></a>概要

モジュールの発行元によっては、法務部門から顧客に対し、PowerShell ギャラリーのモジュールをインストールする前にライセンスに明示的に同意するよう求める場合があります。 ユーザーが直接的か別のアイテムとの依存関係としてかにかかわらず、PowerShellGet を使用してモジュールのインストール、更新、または保存を行うときに、そのモジュールでユーザーにライセンスへの同意が求められている場合、ユーザーはライセンスに同意することを明示的に指定する必要があります。この指定を行わない場合、操作は失敗します。

## <a name="publish-requirements-for-modules"></a>モジュールの発行要件

ユーザーにライセンスへの同意を求めるモジュールでは、次の要件を満たす必要があります。

- モジュール マニフェストの PSData セクションに「RequireLicenseAcceptance = $True」と記載する。
- モジュールのルート ディレクトリに license.txt ファイルを含める。
- モジュール マニフェストにライセンス URI を記載する。
- PowerShellGet のフォーマット バージョン 2.0 以降を使用してモジュールを公開する。

## <a name="impact-on-installsaveupdate-module"></a>Install/Save/Update-Module に対する影響

- Install、Save、Update コマンドレットでは、ユーザーがライセンスを確認する場合と同じ動作をする -AcceptLicense という新パラメーターがサポートされます。
- RequiredLicenseAcceptance が True である場合に -AcceptLicense が指定されていない場合、ユーザーには license.txt が示され、"&quot;ライセンス条項に同意しますか? (はい/いいえ/すべてにはい/すべてにいいえ)&quot;" というメッセージが表示されます。
  - ライセンスに同意した場合:
    - **Save-Module:** ユーザーのシステムにモジュールがコピーされます。
    - **Install-Module:** (スコープに基づいて) ユーザーのシステムの適切なフォルダーにモジュールがコピーされます。
    - **Update-Module:** モジュールが更新されます。
  - ライセンスを拒否した場合:
    - 操作は取り消されます。
- すべてのコマンドレットで、ライセンスへの同意が必要であることを示すメタデータ (requireLicenseAcceptance およびフォーマット バージョン) があるか確認されます。
  - クライアントのフォーマット バージョンが 2.0 よりも前の場合、操作は失敗し、クライアントを更新するように求められます。
  - 2.0 以前のフォーマット バージョンを使用してモジュールが発行されている場合、requireLicenseAcceptance フラグは無視されます。


 ## <a name="module-dependencies"></a>モジュールの依存関係
- インストール/保存/更新操作中、依存モジュール (目的のモジュールに依存する別のモジュール) でライセンスへの同意が求められる場合、上記のライセンスへの同意が必要になります。
- 該当するモジュールのバージョンがシステムへインストール済みであるとローカル カタログに記載されている場合、このライセンス チェックは省略されます。
- インストール/保存/更新操作中、依存モジュールでライセンスが必要とされ、ライセンスへの同意が行われなかった場合、操作は失敗し、インストール/保存/更新が失敗したアイテムに対して通常の処理が行われます。

 ## <a name="impact-on--force"></a>-Force に対する影響

-Force を指定しても、ライセンスへの同意は行われません。 インストールを行うには、-AcceptLicense を指定する必要があります。 -Force を指定した場合に、RequiredLicenseAcceptance が True であり -AcceptLicense を指定していないと、操作は失敗します。

## <a name="examples"></a>例

### <a name="example-1-update-module-manifest-to-require-license-acceptance"></a>例 1: ライセンスへの同意を求めるようにモジュール マニフェストを更新する

```PowerShell
PS> Update-ModuleManifest -Path C:\modulemanifest.psd1 -RequireLicenseAcceptance

PrivateData = @{

    PSData = @{
        # Flag to indicate whether the module requires explicit user acceptance
        RequireLicenseAcceptance = $true
    } # End of PSData hashtable

 } # End of PrivateData hashtable
```

次のコマンドでは、マニフェスト ファイルを更新して RequireLicenseAcceptance フラグを True に設定します。

### <a name="example-2-install-module-requiring-license-acceptance"></a>例 2: ライセンスへの同意が必要なモジュールをインストールする

```PowerShell
PS> Install-Module -Name ModuleRequireLicenseAcceptance

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

次のコマンドでは、license.txt ファイルのライセンスが表示され、このライセンスに同意するように求められます。

### <a name="example-3-install-module-requiring-license-acceptance-with--acceptlicense"></a>例 3: -AcceptLicense を使用してライセンスへの同意が必要なモジュールをインストールする

```PowerShell
PS> Install-Module -Name ModuleRequireLicenseAcceptance -AcceptLicense
```

ライセンスへの同意を求めることなく、モジュールがインストールされます。

### <a name="example-4-install-module-requiring-license-acceptance-with--force"></a>例 4: -Force を使用してライセンスへの同意が必要なモジュールをインストールする

```PowerShell
PS> Install-Module -Name ModuleRequireLicenseAcceptance -Force
PackageManagement\Install-Package : License Acceptance is required for module 'ModuleRequireLicenseAcceptance'. Please specify '-AcceptLicense' to perform this operation.
At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.1.3.3\PSModule.psm1:1837 char:21
+ ...          $null = PackageManagement\Install-Package @PSBoundParameters
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (Microsoft.Power....InstallPackage:InstallPackage) [Install-Package], E
   xception
    + FullyQualifiedErrorId : ForceAcceptLicense,Install-PackageUtility,Microsoft.PowerShell.PackageManagement.Cmdlets
   .InstallPackage
```

### <a name="example-5-install-module-with-dependencies-requiring-license-acceptance"></a>例 5: ライセンスへの同意が必要な依存関係があるモジュールをインストールする

モジュール "ModuleWithDependency" はモジュール "ModuleRequireLicenseAcceptance" に依存しています。 ユーザーにはライセンスへの同意が求められます。

```PowerShell
PS> Install-Module -Name ModuleWithDependency

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

### <a name="example-6-install-module-with-dependencies-requiring-license-acceptance-and--acceptlicense"></a>例 6: -AcceptLicense を使用してライセンスへの同意が必要な依存関係があるモジュールをインストールする

モジュール "ModuleWithDependency" はモジュール "ModuleRequireLicenseAcceptance" に依存しています。 -AcceptLicense を指定したため、ライセンスへの同意は求められません。

```PowerShell
PS>  Install-Module -Name ModuleWithDependency -AcceptLicense
```

### <a name="example-7-install-module-requiring-license-acceptance-on-a-client-older-than-psgetformatversion-20"></a>例 7: PSGetFormatVersion 2.0 以前のクライアントでライセンスへの同意が必要なモジュールをインストールする

```PowerShell
PS C:\windows\system32> Install-Module -Name ModuleRequireLicenseAcceptance

WARNING: The specified module 'ModuleRequireLicenseAcceptance' with PowerShellGetFormatVersion '2.0' is not supported by the current version of PowerShellGet. Get the latest version of the PowerShellGet module to install this module, 'ModuleRequireLicenseAcceptance'.

```

### <a name="example-8-save-module-requiring-license-acceptance"></a>例 8: ライセンスへの同意が必要なモジュールを保存する

```PowerShell
PS> Save-Module -Name ModuleRequireLicenseAcceptance -Path C:\Saved

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

次のコマンドでは、license.txt ファイルのライセンスが表示され、このライセンスに同意するように求められます。

### <a name="example-9-save-module-requiring-license-acceptance-with--acceptlicense"></a>例 9: -AcceptLicense を使用してライセンスへの同意が必要なモジュールを保存する

```PowerShell
PS> Save-Module -Name ModuleRequireLicenseAcceptance -AcceptLicense -Path C:\Saved
```

ライセンスへの同意を求めることなく、モジュールが保存されます。

### <a name="example-10-update-module-requiring-license-acceptance"></a>例 10: ライセンスへの同意が必要なモジュールを更新する

```PowerShell
PS> Update-Module -Name ModuleRequireLicenseAcceptance

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

次のコマンドでは、license.txt ファイルのライセンスが表示され、このライセンスに同意するように求められます。

### <a name="example-11-update-module-requiring-license-acceptance-with--acceptlicense"></a>例 11: -AcceptLicense を使用してライセンスへの同意が必要なモジュールを更新する

```PowerShell
PS> Update-Module -Name ModuleRequireLicenseAcceptance -AcceptLicense
```

ライセンスへの同意を求めることなく、モジュールが更新されます。

## <a name="more-details"></a>詳細情報

### <a name="require-license-acceptance-for-scriptsscript-license-acceptancemd"></a>[スクリプトのライセンス同意リクエスト](./script-license-acceptance.md)

### <a name="require-license-acceptance-support-on-powershellgalleryhow-toworking-with-itemsitems-that-require-license-acceptancemd"></a>[PowerShellGallery でのライセンス同意リクエストのサポート](../how-to/working-with-items/items-that-require-license-acceptance.md)

### <a name="require-license-acceptance-on-deploy-to-azure-automationhow-toworking-with-itemsdeploy-to-azure-automationmd"></a>[Azure Automation へのデプロイで表示されるライセンス同意リクエスト](../how-to/working-with-items/deploy-to-azure-automation.md)