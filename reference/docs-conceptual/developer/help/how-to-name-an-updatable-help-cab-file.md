---
title: 更新可能なヘルプ CAB ファイルに名前を指定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de302da0-c17a-4d31-a8ef-14a626738993
caps.latest.revision: 7
ms.openlocfilehash: a253f98d213f797a659affb1560907bb99a045d3
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811701"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="570a6-102">更新可能なヘルプ CAB ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="570a6-102">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="570a6-103">このトピックでは、更新可能なヘルプキャビネット () に必要な名前の形式について説明します。CAB) ファイル。</span><span class="sxs-lookup"><span data-stu-id="570a6-103">This topic explains the required name format for the Updatable Help cabinet (.CAB) files.</span></span>

## <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="570a6-104">更新可能なヘルプ CAB ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="570a6-104">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="570a6-105">更新可能なキャビネット (.CAB) ファイルの名前は、次の形式にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="570a6-105">A Updatable cabinet (.CAB) file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

<span data-ttu-id="570a6-106">名前の要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="570a6-106">The elements of the name are as follows.</span></span>

<span data-ttu-id="570a6-107">ModuleName コマンドレットが返す**Moduleinfo**オブジェクトの**Name**プロパティの値を[指定します](/powershell/module/Microsoft.PowerShell.Core/Get-Module)。</span><span class="sxs-lookup"><span data-stu-id="570a6-107">ModuleName The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

<span data-ttu-id="570a6-108">ModuleGUID モジュールマニフェスト内の**guid**キーの値。</span><span class="sxs-lookup"><span data-stu-id="570a6-108">ModuleGUID The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="570a6-109">UICulture CAB ファイル内のヘルプファイルの UI カルチャ。</span><span class="sxs-lookup"><span data-stu-id="570a6-109">UICulture The UI culture of the help files in the CAB file.</span></span> <span data-ttu-id="570a6-110">この値は、モジュールの HelpInfo XML ファイル内のいずれかの**UICulture**要素の値と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="570a6-110">This value must match the value of one of the **UICulture** elements in the HelpInfo XML file for the module.</span></span>

<span data-ttu-id="570a6-111">たとえば、モジュール名が "TestModule" で、モジュール GUID が 9cabb9ad-4914-a46b-bfc1bebf07f9 で、UI カルチャが "en-us" の場合、CAB ファイルの名前は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="570a6-111">For example, if the module name is "TestModule," the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, and the UI culture is "en-US", the name of the CAB file would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`
