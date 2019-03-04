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
# <a name="how-to-name-a-helpinfo-xml-file"></a>HelpInfo XML ファイルに名前を付ける方法

このトピックでは、一般的 HelpInfo XML ファイルと呼ばれる、更新可能なヘルプ情報ファイルの必要な名前の形式について説明します。

## <a name="how-to-name-a-helpinfo-xml-file"></a>HelpInfo XML ファイルに名前を付ける方法

HelpInfo XML ファイルを次の形式で名前が必要です。

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

名前の要素は次のとおりです。

ModuleName、値の**名前**のプロパティ、 **ModuleInfo**オブジェクトを[Get-module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットを返します。
値、**名前**のプロパティ、 **ModuleInfo**オブジェクトを[Get-module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットを返します。

ModuleGUID 値の**GUID**モジュール マニフェストでキー。

たとえば、モジュール名が"TestModule"モジュールの GUID が 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 の場合、モジュールの HelpInfo XML ファイルの名前は次のようになります。

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`