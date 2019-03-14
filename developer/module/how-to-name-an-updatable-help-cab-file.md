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
ms.openlocfilehash: 0b58d5ee19a85bed26bc6549ced48b890cd62f64
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794759"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a>更新可能なヘルプ CAB ファイルに名前を付ける方法

このトピックでは、更新可能なヘルプ キャビネットの必要な名前の形式を説明します (します。CAB) ファイル。

## <a name="how-to-name-an-updatable-help-cab-file"></a>更新可能なヘルプ CAB ファイルに名前を付ける方法

更新可能なキャビネット (します。CAB) ファイルには、次の形式で名前が必要です。

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

名前の要素は次のとおりです。

ModuleName、値の**名前**のプロパティ、 **ModuleInfo**オブジェクトを[Get-module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットを返します。

ModuleGUID 値の**GUID**モジュール マニフェストでキー。

CAB ファイルのヘルプ ファイルの UICulture UI カルチャ。 この値は 1 つの値と一致する必要があります、 **UICulture**モジュールの HelpInfo XML ファイル内の要素。

たとえば、モジュール名が"TestModule"の場合は、モジュールの GUID は 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9、および UI カルチャが"EN-US"、CAB ファイルの名前になります。

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`