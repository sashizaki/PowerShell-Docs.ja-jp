---
title: HelpInfo XML ファイル名を指定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64e85b53-5aeb-4d6c-903c-af4ab62f11c1
caps.latest.revision: 7
ms.openlocfilehash: a3e8ae664d5c0e29d0f84174950bebe6a1da6a81
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857828"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="76944-102">HelpInfo XML ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="76944-102">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="76944-103">このトピックでは、一般的 HelpInfo XML ファイルと呼ばれる、更新可能なヘルプ情報ファイルの必要な名前の形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="76944-103">This topic explains the required name format for the Updatable Help Information files, commonly known as HelpInfo XML files.</span></span>

## <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="76944-104">HelpInfo XML ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="76944-104">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="76944-105">HelpInfo XML ファイルを次の形式で名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="76944-105">A HelpInfo XML file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

<span data-ttu-id="76944-106">名前の要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="76944-106">The elements of the name are as follows.</span></span>

<span data-ttu-id="76944-107">ModuleName、値の**名前**のプロパティ、 **ModuleInfo**オブジェクトを[Get-module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットを返します。</span><span class="sxs-lookup"><span data-stu-id="76944-107">ModuleName The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>
<span data-ttu-id="76944-108">値、**名前**のプロパティ、 **ModuleInfo**オブジェクトを[Get-module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットを返します。</span><span class="sxs-lookup"><span data-stu-id="76944-108">The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

<span data-ttu-id="76944-109">ModuleGUID 値の**GUID**モジュール マニフェストでキー。</span><span class="sxs-lookup"><span data-stu-id="76944-109">ModuleGUID The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="76944-110">たとえば、モジュール名が"TestModule"モジュールの GUID が 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 の場合、モジュールの HelpInfo XML ファイルの名前は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="76944-110">For example, if the module name is "TestModule" and the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, the name of the HelpInfo XML file for the module would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`