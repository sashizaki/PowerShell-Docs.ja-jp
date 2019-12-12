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
ms.openlocfilehash: 462cd7bd486a5924bb2bc43e0ac8d1558e30e657
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367201"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="c55a1-102">HelpInfo XML ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="c55a1-102">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="c55a1-103">このトピックでは、HelpInfo XML ファイルと呼ばれる、更新可能なヘルプ情報ファイルに必要な名前の形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="c55a1-103">This topic explains the required name format for the Updatable Help Information files, commonly known as HelpInfo XML files.</span></span>

## <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="c55a1-104">HelpInfo XML ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="c55a1-104">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="c55a1-105">HelpInfo XML ファイルには、次の形式の名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="c55a1-105">A HelpInfo XML file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

<span data-ttu-id="c55a1-106">名前の要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c55a1-106">The elements of the name are as follows.</span></span>

<span data-ttu-id="c55a1-107">ModuleName コマンドレットが返す**Moduleinfo**オブジェクトの**Name**プロパティの値を[指定します](/powershell/module/Microsoft.PowerShell.Core/Get-Module)。</span><span class="sxs-lookup"><span data-stu-id="c55a1-107">ModuleName The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

<span data-ttu-id="c55a1-108">ModuleGUID モジュールマニフェスト内の**guid**キーの値。</span><span class="sxs-lookup"><span data-stu-id="c55a1-108">ModuleGUID The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="c55a1-109">たとえば、モジュール名が "TestModule" で、モジュール GUID が 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 の場合、モジュールの HelpInfo XML ファイルの名前は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c55a1-109">For example, if the module name is "TestModule" and the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, the name of the HelpInfo XML file for the module would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`