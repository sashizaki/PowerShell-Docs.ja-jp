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
ms.openlocfilehash: 462cd7bd486a5924bb2bc43e0ac8d1558e30e657
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082398"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="f5621-102">HelpInfo XML ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="f5621-102">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="f5621-103">このトピックでは、一般的 HelpInfo XML ファイルと呼ばれる、更新可能なヘルプ情報ファイルの必要な名前の形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="f5621-103">This topic explains the required name format for the Updatable Help Information files, commonly known as HelpInfo XML files.</span></span>

## <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="f5621-104">HelpInfo XML ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="f5621-104">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="f5621-105">HelpInfo XML ファイルを次の形式で名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="f5621-105">A HelpInfo XML file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

<span data-ttu-id="f5621-106">名前の要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f5621-106">The elements of the name are as follows.</span></span>

<span data-ttu-id="f5621-107">ModuleName、値の**名前**のプロパティ、 **ModuleInfo**オブジェクトを[Get-module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットを返します。</span><span class="sxs-lookup"><span data-stu-id="f5621-107">ModuleName The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

<span data-ttu-id="f5621-108">ModuleGUID 値の**GUID**モジュール マニフェストでキー。</span><span class="sxs-lookup"><span data-stu-id="f5621-108">ModuleGUID The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="f5621-109">たとえば、モジュール名が"TestModule"モジュールの GUID が 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 の場合、モジュールの HelpInfo XML ファイルの名前は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f5621-109">For example, if the module name is "TestModule" and the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, the name of the HelpInfo XML file for the module would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`