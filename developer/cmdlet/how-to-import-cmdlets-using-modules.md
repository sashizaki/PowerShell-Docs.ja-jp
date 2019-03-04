---
title: モジュールを使用してコマンドレットをインポートする方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41d9e5f-de6f-47b7-9601-c108609320d0
caps.latest.revision: 8
ms.openlocfilehash: c007bb11324e10ffd100797dccd9e6ab0d09a73e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859148"
---
# <a name="how-to-import-cmdlets-using-modules"></a><span data-ttu-id="fc69c-102">モジュールを使用してコマンドレットをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="fc69c-102">How to Import Cmdlets Using Modules</span></span>

<span data-ttu-id="fc69c-103">このトピックでは、バイナリ モジュールを使用して Windows PowerShell セッションにコマンドレットをインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc69c-103">This topic describes how to import cmdlets to a Windows PowerShell session by using a binary module.</span></span>

> [!NOTE]
> <span data-ttu-id="fc69c-104">モジュールのメンバーには、コマンドレット、プロバイダー、関数、変数、エイリアス、およびその他を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="fc69c-104">The members of modules can include cmdlets, providers, functions, variables, aliases, and much more.</span></span> <span data-ttu-id="fc69c-105">スナップインには、コマンドレットとプロバイダーのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="fc69c-105">Snap-ins can contain only cmdlets and providers.</span></span>

## <a name="how-to-load-cmdlets-using-a-module"></a><span data-ttu-id="fc69c-106">モジュールを使用してコマンドレットを読み込む方法</span><span class="sxs-lookup"><span data-stu-id="fc69c-106">How to load cmdlets using a module</span></span>

1. <span data-ttu-id="fc69c-107">コマンドレットが実装されているアセンブリ ファイルと同じ名前を持つモジュール フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fc69c-107">Create a module folder that has the same name as the assembly file in which the cmdlets are implemented.</span></span> <span data-ttu-id="fc69c-108">この手順でモジュール フォルダーを作成、`system32`フォルダー。</span><span class="sxs-lookup"><span data-stu-id="fc69c-108">In this procedure, the module folder is created in the `system32` folder.</span></span>

   `%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\mymodule`

2. <span data-ttu-id="fc69c-109">必ず、`PSModulePath`環境変数には、新しいモジュール フォルダーへのパスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fc69c-109">Make sure that the `PSModulePath` environment variable includes the path to your new module folder.</span></span> <span data-ttu-id="fc69c-110">既定では、システム フォルダーは既にに追加、`PSModulePath`環境変数。</span><span class="sxs-lookup"><span data-stu-id="fc69c-110">By default, the system folder is already added to the `PSModulePath` environment variable.</span></span>

3. <span data-ttu-id="fc69c-111">モジュール フォルダーには、コマンドレットのアセンブリをコピーします。</span><span class="sxs-lookup"><span data-stu-id="fc69c-111">Copy the cmdlet assembly into the module folder.</span></span>

4. <span data-ttu-id="fc69c-112">コマンドレットをセッションに追加するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fc69c-112">Run the following command to add the cmdlets to the session:</span></span>

   `import-module [Module_Name]`

   <span data-ttu-id="fc69c-113">この手順は、テスト、コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fc69c-113">This procedure can be used to test your cmdlets.</span></span> <span data-ttu-id="fc69c-114">セッションにアセンブリ内のすべてのコマンドレットを追加します。</span><span class="sxs-lookup"><span data-stu-id="fc69c-114">It adds all the cmdlets in the assembly to the session.</span></span> <span data-ttu-id="fc69c-115">モジュールの詳細については、モジュール、モジュール、およびエクスポートされるモジュールの要素を制限する方法を読み込むためのさまざまな方法のさまざまな種類を参照してください[Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)します。</span><span class="sxs-lookup"><span data-stu-id="fc69c-115">For more information about modules, the different types of modules, the different ways to load modules, and how to restrict the elements of a module that are exported, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fc69c-116">参照</span><span class="sxs-lookup"><span data-stu-id="fc69c-116">See Also</span></span>

[<span data-ttu-id="fc69c-117">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="fc69c-117">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="fc69c-118">モジュールのインストール</span><span class="sxs-lookup"><span data-stu-id="fc69c-118">Installing Modules</span></span>](../module/installing-a-powershell-module.md)