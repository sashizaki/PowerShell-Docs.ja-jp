---
ms.date: 06/09/2017
schema: 2.0.0
keywords: powershell
title: RequireLicenseAcceptanceScript
ms.openlocfilehash: 4a2dc39c2b6c380fb4ca94f9fd071ed9cdb35049
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="requiring-license-acceptance-for-scripts"></a>スクリプトでのライセンス同意の必須化

ライセンス同意は、スクリプトではサポートされていません。 ただし、ライセンスへの同意が必要なモジュールにスクリプトが依存するシナリオはサポートされています。

スクリプト コマンド (Install-Script/Save-Script/Update-Script) では、ユーザーがライセンスを確認する場合と同じ動作をする新パラメーター -AcceptLicense がサポートされます。 -AcceptLicense を指定しない場合、ユーザーには依存モジュールの license.txt が示され、このライセンスに同意するように求められます。

## <a name="examples"></a>例

### <a name="example-1-install-script-with-dependencies-requiring-license-acceptance"></a>例 1: ライセンスへの同意が必要な依存関係があるスクリプトをインストールする
スクリプト "ScriptRequireLicenseAcceptance" は、モジュール "ModuleRequireLicenseAcceptance" に依存しています。 ユーザーにはライセンスへの同意が求められます。
```PowerShell
PS C:\> Install-Script -Name ScriptRequireLicenseAcceptance

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

### <a name="example-2-install-script-with-dependencies-requiring-license-acceptance-and--acceptlicense"></a>例 2: -AcceptLicense を使用してライセンスへの同意が必要な依存関係があるスクリプトをインストールする
スクリプト "ScriptRequireLicenseAcceptance" は、モジュール "ModuleRequireLicenseAcceptance" に依存しています。 -AcceptLicense を指定したため、ライセンスへの同意は求められません。
```PowerShell
PS C:\> Install-Script -Name ScriptRequireLicenseAcceptance -AcceptLicense
```

## <a name="more-details"></a>詳細情報
### <a name="require-license-acceptance-support-for-modulesmodulerequirelicenseacceptancemd"></a>[モジュールに対するライセンス同意リクエストのサポート](../module/RequireLicenseAcceptance.md)

### <a name="require-license-acceptance-support-on-powershellgallerypsgallerypsgalleryrequireslicenseacceptancemd"></a>[PowerShellGallery でのライセンス同意リクエストのサポート](../../psgallery/psgallery_requires_license_acceptance.md)

### <a name="require-license-acceptance-on-deploy-to-azure-automationpsgallerypsgallerydeploytoazureautomationrequirelicenseacceptancemd"></a>[Azure Automation へのデプロイで表示されるライセンス同意リクエスト](../../psgallery/psgallery_deploy_to_azure_automation_requireLicenseAcceptance.md)