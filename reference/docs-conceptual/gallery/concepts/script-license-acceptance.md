---
ms.date: 06/09/2017
schema: 2.0.0
keywords: powershell
title: スクリプトでのライセンス同意の必須化
ms.openlocfilehash: e7101eb6a480dd87965b7b9be9d49583042b603f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71328083"
---
# <a name="requiring-license-acceptance-for-scripts"></a><span data-ttu-id="f48f0-103">スクリプトでのライセンス同意の必須化</span><span class="sxs-lookup"><span data-stu-id="f48f0-103">Requiring license acceptance for scripts</span></span>

<span data-ttu-id="f48f0-104">ライセンス同意は、スクリプトではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f48f0-104">License Acceptance is not supported for scripts.</span></span> <span data-ttu-id="f48f0-105">ただし、ライセンスへの同意が必要なモジュールにスクリプトが依存するシナリオはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f48f0-105">However, the scenario where a script depends on a module that requires license acceptance is supported.</span></span>

<span data-ttu-id="f48f0-106">スクリプト コマンド (Install-Script/Save-Script/Update-Script) では、ユーザーがライセンスを確認する場合と同じ動作をする新パラメーター -AcceptLicense がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f48f0-106">Script commands(Install-Script/Save-Script/Update-Script) support a new parameter -AcceptLicense that behaves as though user saw the license.</span></span> <span data-ttu-id="f48f0-107">-AcceptLicense を指定しない場合、ユーザーには依存モジュールの license.txt が示され、このライセンスに同意するように求められます。</span><span class="sxs-lookup"><span data-stu-id="f48f0-107">If -AcceptLicense is not specified; the user will be shown license.txt for dependent module and prompted to accept the license.</span></span>

## <a name="examples"></a><span data-ttu-id="f48f0-108">例</span><span class="sxs-lookup"><span data-stu-id="f48f0-108">EXAMPLES</span></span>

### <a name="example-1-install-script-with-dependencies-requiring-license-acceptance"></a><span data-ttu-id="f48f0-109">例 1:ライセンスへの同意が必要な依存関係があるスクリプトをインストールする</span><span class="sxs-lookup"><span data-stu-id="f48f0-109">Example 1: Install Script with dependencies requiring license acceptance</span></span>

<span data-ttu-id="f48f0-110">スクリプト "ScriptRequireLicenseAcceptance" は、モジュール "ModuleRequireLicenseAcceptance" に依存しています。</span><span class="sxs-lookup"><span data-stu-id="f48f0-110">Script 'ScriptRequireLicenseAcceptance' depends on module 'ModuleRequireLicenseAcceptance'.</span></span> <span data-ttu-id="f48f0-111">ユーザーにはライセンスへの同意が求められます。</span><span class="sxs-lookup"><span data-stu-id="f48f0-111">User is prompted to Accept License.</span></span>

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

### <a name="example-2-install-script-with-dependencies-requiring-license-acceptance-and--acceptlicense"></a><span data-ttu-id="f48f0-112">例 2:-AcceptLicense を使用してライセンスへの同意が必要な依存関係があるスクリプトをインストールする</span><span class="sxs-lookup"><span data-stu-id="f48f0-112">Example 2: Install Script with dependencies requiring license acceptance and -AcceptLicense</span></span>

<span data-ttu-id="f48f0-113">スクリプト "ScriptRequireLicenseAcceptance" は、モジュール "ModuleRequireLicenseAcceptance" に依存しています。</span><span class="sxs-lookup"><span data-stu-id="f48f0-113">Script 'ScriptRequireLicenseAcceptance' depends on module 'ModuleRequireLicenseAcceptance'.</span></span> <span data-ttu-id="f48f0-114">-AcceptLicense を指定したため、ライセンスへの同意は求められません。</span><span class="sxs-lookup"><span data-stu-id="f48f0-114">User is not prompted to accept license as -AcceptLicense is specified.</span></span>

```PowerShell
PS> Install-Script -Name ScriptRequireLicenseAcceptance -AcceptLicense
```

## <a name="more-details"></a><span data-ttu-id="f48f0-115">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f48f0-115">More details</span></span>

- [<span data-ttu-id="f48f0-116">モジュールに対するライセンス同意リクエストのサポート</span><span class="sxs-lookup"><span data-stu-id="f48f0-116">Require License Acceptance support for Modules</span></span>](module-license-acceptance.md)
- [<span data-ttu-id="f48f0-117">PowerShellGallery でのライセンス同意リクエストのサポート</span><span class="sxs-lookup"><span data-stu-id="f48f0-117">Require License Acceptance support on PowerShellGallery</span></span>](../how-to/working-with-packages/packages-that-require-license-acceptance.md)
- [<span data-ttu-id="f48f0-118">Azure Automation へのデプロイで表示されるライセンス同意リクエスト</span><span class="sxs-lookup"><span data-stu-id="f48f0-118">Require License Acceptance on Deploy to Azure Automation</span></span>](../how-to/working-with-packages/deploy-to-azure-automation.md)
