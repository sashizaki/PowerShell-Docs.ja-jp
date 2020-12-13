---
ms.date: 09/12/2016
ms.topic: reference
title: 更新可能なヘルプ CAB ファイルに名前を付ける方法
description: 更新可能なヘルプ CAB ファイルに名前を付ける方法
ms.openlocfilehash: 57ea188d07a382d1a986a49c9ae22c5919dafa8e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658921"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="dc6c2-103">更新可能なヘルプ CAB ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="dc6c2-103">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="dc6c2-104">このトピックでは、更新可能なヘルプキャビネット () ファイルに必要な名前の形式について説明し `.CAB` ます。</span><span class="sxs-lookup"><span data-stu-id="dc6c2-104">This topic explains the required name format for the Updatable Help cabinet (`.CAB`) files.</span></span>

## <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="dc6c2-105">更新可能なヘルプ CAB ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="dc6c2-105">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="dc6c2-106">更新可能なキャビネット () ファイルには、 `.CAB` 次の形式の名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc6c2-106">A Updatable cabinet (`.CAB`) file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

<span data-ttu-id="dc6c2-107">名前の要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc6c2-107">The elements of the name are as follows.</span></span>

- <span data-ttu-id="dc6c2-108">`<ModuleName>`-[モジュール](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットが返す **Moduleinfo** オブジェクトの **Name** プロパティの値。</span><span class="sxs-lookup"><span data-stu-id="dc6c2-108">`<ModuleName>` -The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>
- <span data-ttu-id="dc6c2-109">`<ModuleGUID>` -モジュールマニフェスト内の **GUID** キーの値。</span><span class="sxs-lookup"><span data-stu-id="dc6c2-109">`<ModuleGUID>` - The value of the **GUID** key in the module manifest.</span></span>
- <span data-ttu-id="dc6c2-110">`<UICulture>` -CAB ファイル内のヘルプファイルの UI カルチャ。</span><span class="sxs-lookup"><span data-stu-id="dc6c2-110">`<UICulture>` - The UI culture of the help files in the CAB file.</span></span> <span data-ttu-id="dc6c2-111">この値は、モジュールの HelpInfo XML ファイル内のいずれかの **UICulture** 要素の値と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc6c2-111">This value must match the value of one of the **UICulture** elements in the HelpInfo XML file for the module.</span></span>

<span data-ttu-id="dc6c2-112">たとえば、モジュール名が "TestModule" で、モジュール GUID が 9cabb9ad-4914-a46b-bfc1bebf07f9 で、UI カルチャが "en-us" の場合、CAB ファイルの名前は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dc6c2-112">For example, if the module name is "TestModule," the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, and the UI culture is "en-US", the name of the CAB file would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`
