---
title: モジュールを使用してコマンドレットをインポートする方法 |Microsoft Docs
ms.custom: ''
ms.date: 08/28/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41d9e5f-de6f-47b7-9601-c108609320d0
caps.latest.revision: 8
ms.openlocfilehash: 2f145795a57c988da0cb4ed294142aa141c53cae
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364461"
---
# <a name="how-to-import-cmdlets-using-modules"></a><span data-ttu-id="9bf75-102">モジュールを使用してコマンドレットをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="9bf75-102">How to Import Cmdlets Using Modules</span></span>

<span data-ttu-id="9bf75-103">この記事では、バイナリモジュールを使用して PowerShell セッションにコマンドレットをインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9bf75-103">This article describes how to import cmdlets to a PowerShell session by using a binary module.</span></span>

> [!NOTE]
> <span data-ttu-id="9bf75-104">モジュールのメンバーには、コマンドレット、プロバイダー、関数、変数、別名などを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9bf75-104">The members of modules can include cmdlets, providers, functions, variables, aliases, and much more.</span></span> <span data-ttu-id="9bf75-105">スナップインには、コマンドレットとプロバイダーのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9bf75-105">Snap-ins can contain only cmdlets and providers.</span></span>

## <a name="how-to-load-cmdlets-using-a-module"></a><span data-ttu-id="9bf75-106">モジュールを使用してコマンドレットを読み込む方法</span><span class="sxs-lookup"><span data-stu-id="9bf75-106">How to load cmdlets using a module</span></span>

1. <span data-ttu-id="9bf75-107">コマンドレットが実装されているアセンブリファイルと同じ名前のモジュールフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9bf75-107">Create a module folder that has the same name as the assembly file in which the cmdlets are implemented.</span></span> <span data-ttu-id="9bf75-108">この手順では、Windows の `system32` フォルダーにモジュールフォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9bf75-108">In this procedure, the module folder is created in the Windows `system32` folder.</span></span>

   `%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\mymodule`

1. <span data-ttu-id="9bf75-109">`PSModulePath` 環境変数に、新しいモジュールフォルダーへのパスが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9bf75-109">Make sure that the `PSModulePath` environment variable includes the path to your new module folder.</span></span> <span data-ttu-id="9bf75-110">既定では、システムフォルダーは `PSModulePath` 環境変数に既に追加されています。</span><span class="sxs-lookup"><span data-stu-id="9bf75-110">By default, the system folder is already added to the `PSModulePath` environment variable.</span></span> <span data-ttu-id="9bf75-111">`PSModulePath`を表示するには、「`$env:PSModulePath`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9bf75-111">To view the `PSModulePath`, type: `$env:PSModulePath`.</span></span>

1. <span data-ttu-id="9bf75-112">コマンドレットアセンブリをモジュールフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9bf75-112">Copy the cmdlet assembly into the module folder.</span></span>

1. <span data-ttu-id="9bf75-113">モジュールのルートフォルダーにモジュールマニフェストファイル (`.psd1`) を追加します。</span><span class="sxs-lookup"><span data-stu-id="9bf75-113">Add a module manifest file (`.psd1`) in the module's root folder.</span></span> <span data-ttu-id="9bf75-114">PowerShell はモジュールマニフェストを使用してモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="9bf75-114">PowerShell uses the module manifest to import your module.</span></span> <span data-ttu-id="9bf75-115">詳細については、「 [PowerShell モジュールマニフェストを記述する方法](../module/how-to-write-a-powershell-module-manifest.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bf75-115">For more information, see [How to Write a PowerShell Module Manifest](../module/how-to-write-a-powershell-module-manifest.md).</span></span>

1. <span data-ttu-id="9bf75-116">次のコマンドを実行して、コマンドレットをセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="9bf75-116">Run the following command to add the cmdlets to the session:</span></span>

   `Import-Module [Module_Name]`

   <span data-ttu-id="9bf75-117">この手順は、コマンドレットをテストするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="9bf75-117">This procedure can be used to test your cmdlets.</span></span> <span data-ttu-id="9bf75-118">これにより、アセンブリ内のすべてのコマンドレットがセッションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="9bf75-118">It adds all the cmdlets in the assembly to the session.</span></span> <span data-ttu-id="9bf75-119">モジュールの詳細については、「 [Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bf75-119">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9bf75-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bf75-120">See also</span></span>

[<span data-ttu-id="9bf75-121">PowerShell モジュールマニフェストを記述する方法</span><span class="sxs-lookup"><span data-stu-id="9bf75-121">How to Write a PowerShell Module Manifest</span></span>](../module/how-to-write-a-powershell-module-manifest.md)

[<span data-ttu-id="9bf75-122">PowerShell モジュールのインポート</span><span class="sxs-lookup"><span data-stu-id="9bf75-122">Importing a PowerShell Module</span></span>](../module/importing-a-powershell-module.md)

[<span data-ttu-id="9bf75-123">Import-Module</span><span class="sxs-lookup"><span data-stu-id="9bf75-123">Import-Module</span></span>](/powershell/module/Microsoft.PowerShell.Core/Import-Module)

[<span data-ttu-id="9bf75-124">モジュールのインストール</span><span class="sxs-lookup"><span data-stu-id="9bf75-124">Installing Modules</span></span>](../module/installing-a-powershell-module.md)

[<span data-ttu-id="9bf75-125">PSModulePath インストールパスの変更</span><span class="sxs-lookup"><span data-stu-id="9bf75-125">Modifying the PSModulePath Installation Path</span></span>](../module/modifying-the-psmodulepath-installation-path.md)

[<span data-ttu-id="9bf75-126">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="9bf75-126">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
