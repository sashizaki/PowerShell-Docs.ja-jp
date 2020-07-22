---
title: HelpInfo XML ファイルに名前を付ける方法
ms.date: 09/12/2016
ms.openlocfilehash: 9505a7f66852a569d25ac0c1be86e68f870a7930
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892933"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="9e2ce-102">HelpInfo XML ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="9e2ce-102">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="9e2ce-103">このトピックでは、HelpInfo XML ファイルと呼ばれる、更新可能なヘルプ情報ファイルに必要な名前の形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e2ce-103">This topic explains the required name format for the Updatable Help Information files, commonly known as HelpInfo XML files.</span></span>

## <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="9e2ce-104">HelpInfo XML ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="9e2ce-104">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="9e2ce-105">HelpInfo XML ファイルには、次の形式の名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e2ce-105">A HelpInfo XML file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

<span data-ttu-id="9e2ce-106">名前の要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9e2ce-106">The elements of the name are as follows.</span></span>

- <span data-ttu-id="9e2ce-107">`<ModuleName>`-[モジュール](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットが返す**Moduleinfo**オブジェクトの**Name**プロパティの値。</span><span class="sxs-lookup"><span data-stu-id="9e2ce-107">`<ModuleName>` - The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

- <span data-ttu-id="9e2ce-108">`<ModuleGUID>`-モジュールマニフェスト内の**GUID**キーの値。</span><span class="sxs-lookup"><span data-stu-id="9e2ce-108">`<ModuleGUID>` - The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="9e2ce-109">たとえば、モジュール名が "TestModule" で、モジュール GUID が 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 の場合、モジュールの HelpInfo XML ファイルの名前は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9e2ce-109">For example, if the module name is "TestModule" and the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, the name of the HelpInfo XML file for the module would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`
