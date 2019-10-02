---
ms.date: 06/09/2017
schema: 2.0.0
keywords: powershell
title: スクリプトでのライセンス同意の必須化
ms.openlocfilehash: e7101eb6a480dd87965b7b9be9d49583042b603f
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71328083"
---
# <a name="requiring-license-acceptance-for-scripts"></a>スクリプトでのライセンス同意の必須化

ライセンス同意は、スクリプトではサポートされていません。 ただし、ライセンスへの同意が必要なモジュールにスクリプトが依存するシナリオはサポートされています。

スクリプト コマンド (Install-Script/Save-Script/Update-Script) では、ユーザーがライセンスを確認する場合と同じ動作をする新パラメーター -AcceptLicense がサポートされます。 -AcceptLicense を指定しない場合、ユーザーには依存モジュールの license.txt が示され、このライセンスに同意するように求められます。

## <a name="examples"></a>例

### <a name="example-1-install-script-with-dependencies-requiring-license-acceptance"></a>例 1:ライセンスへの同意が必要な依存関係があるスクリプトをインストールする

スクリプト "ScriptRequireLicenseAcceptance" は、モジュール "ModuleRequireLicenseAcceptance" に依存しています。 ユーザーにはライセンスへの同意が求められます。

```PowerShell
PS> Install-Script -Name ScriptRequireLicenseAcceptance

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

### <a name="example-2-install-script-with-dependencies-requiring-license-acceptance-and--acceptlicense"></a>例 2:-AcceptLicense を使用してライセンスへの同意が必要な依存関係があるスクリプトをインストールする

スクリプト "ScriptRequireLicenseAcceptance" は、モジュール "ModuleRequireLicenseAcceptance" に依存しています。 -AcceptLicense を指定したため、ライセンスへの同意は求められません。

```PowerShell
PS> Install-Script -Name ScriptRequireLicenseAcceptance -AcceptLicense
```

## <a name="more-details"></a>詳細情報

- [モジュールに対するライセンス同意リクエストのサポート](module-license-acceptance.md)
- [PowerShellGallery でのライセンス同意リクエストのサポート](../how-to/working-with-packages/packages-that-require-license-acceptance.md)
- [Azure Automation へのデプロイで表示されるライセンス同意リクエスト](../how-to/working-with-packages/deploy-to-azure-automation.md)
