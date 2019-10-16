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
ms.openlocfilehash: 0b58d5ee19a85bed26bc6549ced48b890cd62f64
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367161"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a>更新可能なヘルプ CAB ファイルに名前を付ける方法

このトピックでは、更新可能なヘルプキャビネット () に必要な名前の形式について説明します。CAB) ファイル。

## <a name="how-to-name-an-updatable-help-cab-file"></a>更新可能なヘルプ CAB ファイルに名前を付ける方法

更新可能なキャビネット (.CAB) ファイルの名前は、次の形式にする必要があります。

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

名前の要素は次のとおりです。

ModuleName コマンドレットが返す**Moduleinfo**オブジェクトの**Name**プロパティの値を[指定します](/powershell/module/Microsoft.PowerShell.Core/Get-Module)。

ModuleGUID モジュールマニフェスト内の**guid**キーの値。

UICulture CAB ファイル内のヘルプファイルの UI カルチャ。 この値は、モジュールの HelpInfo XML ファイル内のいずれかの**UICulture**要素の値と一致する必要があります。

たとえば、モジュール名が "TestModule" で、モジュール GUID が 9cabb9ad-4914-a46b-bfc1bebf07f9 で、UI カルチャが "en-us" の場合、CAB ファイルの名前は次のようになります。

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`