---
ms.date: 08/28/2019
ms.topic: reference
title: モジュールを使用してコマンドレットをインポートする方法
description: モジュールを使用してコマンドレットをインポートする方法
ms.openlocfilehash: 485a4be4d2accaf050a6536e7f92a0673f62a30b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657280"
---
# <a name="how-to-import-cmdlets-using-modules"></a><span data-ttu-id="6907d-103">モジュールを使用してコマンドレットをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="6907d-103">How to Import Cmdlets Using Modules</span></span>

<span data-ttu-id="6907d-104">この記事では、バイナリモジュールを使用して PowerShell セッションにコマンドレットをインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6907d-104">This article describes how to import cmdlets to a PowerShell session by using a binary module.</span></span>

> [!NOTE]
> <span data-ttu-id="6907d-105">モジュールのメンバーには、コマンドレット、プロバイダー、関数、変数、別名などを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6907d-105">The members of modules can include cmdlets, providers, functions, variables, aliases, and much more.</span></span> <span data-ttu-id="6907d-106">スナップインには、コマンドレットとプロバイダーのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6907d-106">Snap-ins can contain only cmdlets and providers.</span></span>

## <a name="how-to-load-cmdlets-using-a-module"></a><span data-ttu-id="6907d-107">モジュールを使用してコマンドレットを読み込む方法</span><span class="sxs-lookup"><span data-stu-id="6907d-107">How to load cmdlets using a module</span></span>

1. <span data-ttu-id="6907d-108">コマンドレットが実装されているアセンブリファイルと同じ名前のモジュールフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6907d-108">Create a module folder that has the same name as the assembly file in which the cmdlets are implemented.</span></span> <span data-ttu-id="6907d-109">この手順では、Windows フォルダーにモジュールフォルダーが作成され `system32` ます。</span><span class="sxs-lookup"><span data-stu-id="6907d-109">In this procedure, the module folder is created in the Windows `system32` folder.</span></span>

   `%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\mymodule`

1. <span data-ttu-id="6907d-110">`PSModulePath`環境変数に新しいモジュールフォルダーへのパスが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6907d-110">Make sure that the `PSModulePath` environment variable includes the path to your new module folder.</span></span> <span data-ttu-id="6907d-111">既定では、システムフォルダーは環境変数に既に追加されてい `PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="6907d-111">By default, the system folder is already added to the `PSModulePath` environment variable.</span></span> <span data-ttu-id="6907d-112">を表示するには `PSModulePath` 、「」と入力 `$env:PSModulePath` します。</span><span class="sxs-lookup"><span data-stu-id="6907d-112">To view the `PSModulePath`, type: `$env:PSModulePath`.</span></span>

1. <span data-ttu-id="6907d-113">コマンドレットアセンブリをモジュールフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="6907d-113">Copy the cmdlet assembly into the module folder.</span></span>

1. <span data-ttu-id="6907d-114">モジュールのルートフォルダーにモジュールマニフェストファイル () を追加 `.psd1` します。</span><span class="sxs-lookup"><span data-stu-id="6907d-114">Add a module manifest file (`.psd1`) in the module's root folder.</span></span> <span data-ttu-id="6907d-115">PowerShell はモジュールマニフェストを使用してモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="6907d-115">PowerShell uses the module manifest to import your module.</span></span> <span data-ttu-id="6907d-116">詳細については、「 [PowerShell モジュールマニフェストを記述する方法](../module/how-to-write-a-powershell-module-manifest.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6907d-116">For more information, see [How to Write a PowerShell Module Manifest](../module/how-to-write-a-powershell-module-manifest.md).</span></span>

1. <span data-ttu-id="6907d-117">次のコマンドを実行して、コマンドレットをセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="6907d-117">Run the following command to add the cmdlets to the session:</span></span>

   `Import-Module [Module_Name]`

   <span data-ttu-id="6907d-118">この手順は、コマンドレットをテストするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="6907d-118">This procedure can be used to test your cmdlets.</span></span> <span data-ttu-id="6907d-119">これにより、アセンブリ内のすべてのコマンドレットがセッションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6907d-119">It adds all the cmdlets in the assembly to the session.</span></span> <span data-ttu-id="6907d-120">モジュールの詳細については、「 [Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6907d-120">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6907d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="6907d-121">See also</span></span>

[<span data-ttu-id="6907d-122">PowerShell モジュール マニフェストを記述する方法</span><span class="sxs-lookup"><span data-stu-id="6907d-122">How to Write a PowerShell Module Manifest</span></span>](../module/how-to-write-a-powershell-module-manifest.md)

[<span data-ttu-id="6907d-123">PowerShell モジュールをインポートする</span><span class="sxs-lookup"><span data-stu-id="6907d-123">Importing a PowerShell Module</span></span>](../module/importing-a-powershell-module.md)

[<span data-ttu-id="6907d-124">Import-Module</span><span class="sxs-lookup"><span data-stu-id="6907d-124">Import-Module</span></span>](/powershell/module/Microsoft.PowerShell.Core/Import-Module)

[<span data-ttu-id="6907d-125">モジュールのインストール</span><span class="sxs-lookup"><span data-stu-id="6907d-125">Installing Modules</span></span>](../module/installing-a-powershell-module.md)

[<span data-ttu-id="6907d-126">PSModulePath インストール パスを変更する</span><span class="sxs-lookup"><span data-stu-id="6907d-126">Modifying the PSModulePath Installation Path</span></span>](../module/modifying-the-psmodulepath-installation-path.md)

[<span data-ttu-id="6907d-127">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="6907d-127">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/cmdlet-overview.md)
