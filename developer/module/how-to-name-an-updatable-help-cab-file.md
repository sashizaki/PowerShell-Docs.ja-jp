---
title: 更新可能なヘルプの CAB ファイルの名前を付ける方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de302da0-c17a-4d31-a8ef-14a626738993
caps.latest.revision: 7
ms.openlocfilehash: 23303489372cfe7e036fdea842ae75f7e47503c8
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861288"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="cfdb5-102">更新可能なヘルプ CAB ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="cfdb5-102">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="cfdb5-103">このトピックでは、更新可能なヘルプ キャビネットの必要な名前の形式を説明します (します。CAB) ファイル。</span><span class="sxs-lookup"><span data-stu-id="cfdb5-103">This topic explains the required name format for the Updatable Help cabinet (.CAB) files.</span></span>

## <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="cfdb5-104">更新可能なヘルプ CAB ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="cfdb5-104">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="cfdb5-105">更新可能なキャビネット (します。CAB) ファイルには、次の形式で名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="cfdb5-105">A Updatable cabinet (.CAB) file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

<span data-ttu-id="cfdb5-106">名前の要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cfdb5-106">The elements of the name are as follows.</span></span>

<span data-ttu-id="cfdb5-107">ModuleName、値の**名前**のプロパティ、 **ModuleInfo**オブジェクトを[Get-module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットを返します。</span><span class="sxs-lookup"><span data-stu-id="cfdb5-107">ModuleName The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>
<span data-ttu-id="cfdb5-108">値、**名前**のプロパティ、 **ModuleInfo**オブジェクトを[Get-module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットを返します。</span><span class="sxs-lookup"><span data-stu-id="cfdb5-108">The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

<span data-ttu-id="cfdb5-109">ModuleGUID 値の**GUID**モジュール マニフェストでキー。</span><span class="sxs-lookup"><span data-stu-id="cfdb5-109">ModuleGUID The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="cfdb5-110">CAB ファイルのヘルプ ファイルの UICulture UI カルチャ。</span><span class="sxs-lookup"><span data-stu-id="cfdb5-110">UICulture The UI culture of the help files in the CAB file.</span></span> <span data-ttu-id="cfdb5-111">この値は 1 つの値と一致する必要があります、 **UICulture**モジュールの HelpInfo XML ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="cfdb5-111">This value must match the value of one of the **UICulture** elements in the HelpInfo XML file for the module.</span></span>

<span data-ttu-id="cfdb5-112">たとえば、モジュール名が"TestModule"の場合は、モジュールの GUID は 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9、および UI カルチャが"EN-US"、CAB ファイルの名前になります。</span><span class="sxs-lookup"><span data-stu-id="cfdb5-112">For example, if the module name is "TestModule," the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, and the UI culture is "en-US", the name of the CAB file would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`