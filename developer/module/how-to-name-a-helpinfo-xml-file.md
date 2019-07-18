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
# <a name="how-to-name-a-helpinfo-xml-file"></a>HelpInfo XML ファイルに名前を付ける方法

このトピックでは、一般的 HelpInfo XML ファイルと呼ばれる、更新可能なヘルプ情報ファイルの必要な名前の形式について説明します。

## <a name="how-to-name-a-helpinfo-xml-file"></a>HelpInfo XML ファイルに名前を付ける方法

HelpInfo XML ファイルを次の形式で名前が必要です。

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

名前の要素は次のとおりです。

ModuleName、値の**名前**のプロパティ、 **ModuleInfo**オブジェクトを[Get-module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットを返します。

ModuleGUID 値の**GUID**モジュール マニフェストでキー。

たとえば、モジュール名が"TestModule"モジュールの GUID が 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 の場合、モジュールの HelpInfo XML ファイルの名前は次のようになります。

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`