---
title: HelpInfo XML ファイルに名前を指定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64e85b53-5aeb-4d6c-903c-af4ab62f11c1
caps.latest.revision: 7
ms.openlocfilehash: 45e8a5bb0066f38c82cd3be8ec881383befd9c85
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560578"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="5e67c-102">HelpInfo XML ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="5e67c-102">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="5e67c-103">このトピックでは、HelpInfo XML ファイルと呼ばれる、更新可能なヘルプ情報ファイルに必要な名前の形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e67c-103">This topic explains the required name format for the Updatable Help Information files, commonly known as HelpInfo XML files.</span></span>

## <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="5e67c-104">HelpInfo XML ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="5e67c-104">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="5e67c-105">HelpInfo XML ファイルには、次の形式の名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e67c-105">A HelpInfo XML file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

<span data-ttu-id="5e67c-106">名前の要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5e67c-106">The elements of the name are as follows.</span></span>

<span data-ttu-id="5e67c-107">ModuleName コマンドレットが返す**Moduleinfo**オブジェクトの**Name**プロパティの値を[指定します](/powershell/module/Microsoft.PowerShell.Core/Get-Module)。</span><span class="sxs-lookup"><span data-stu-id="5e67c-107">ModuleName The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

<span data-ttu-id="5e67c-108">ModuleGUID モジュールマニフェスト内の**guid**キーの値。</span><span class="sxs-lookup"><span data-stu-id="5e67c-108">ModuleGUID The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="5e67c-109">たとえば、モジュール名が "TestModule" で、モジュール GUID が 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 の場合、モジュールの HelpInfo XML ファイルの名前は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5e67c-109">For example, if the module name is "TestModule" and the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, the name of the HelpInfo XML file for the module would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`
