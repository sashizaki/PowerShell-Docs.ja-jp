---
ms.date: 09/12/2016
ms.topic: reference
title: HelpInfo XML ファイルに名前を付ける方法
description: HelpInfo XML ファイルに名前を付ける方法
ms.openlocfilehash: 55bc2ef9530fc457e4d9ddf18e79e7226c991663
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659038"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="3ac88-103">HelpInfo XML ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="3ac88-103">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="3ac88-104">このトピックでは、HelpInfo XML ファイルと呼ばれる、更新可能なヘルプ情報ファイルに必要な名前の形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ac88-104">This topic explains the required name format for the Updatable Help Information files, commonly known as HelpInfo XML files.</span></span>

## <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="3ac88-105">HelpInfo XML ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="3ac88-105">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="3ac88-106">HelpInfo XML ファイルには、次の形式の名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ac88-106">A HelpInfo XML file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

<span data-ttu-id="3ac88-107">名前の要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3ac88-107">The elements of the name are as follows.</span></span>

- <span data-ttu-id="3ac88-108">`<ModuleName>`-[モジュール](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットが返す **Moduleinfo** オブジェクトの **Name** プロパティの値。</span><span class="sxs-lookup"><span data-stu-id="3ac88-108">`<ModuleName>` - The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

- <span data-ttu-id="3ac88-109">`<ModuleGUID>` -モジュールマニフェスト内の **GUID** キーの値。</span><span class="sxs-lookup"><span data-stu-id="3ac88-109">`<ModuleGUID>` - The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="3ac88-110">たとえば、モジュール名が "TestModule" で、モジュール GUID が 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 の場合、モジュールの HelpInfo XML ファイルの名前は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3ac88-110">For example, if the module name is "TestModule" and the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, the name of the HelpInfo XML file for the module would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`
