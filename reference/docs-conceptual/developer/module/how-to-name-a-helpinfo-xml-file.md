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
# <a name="how-to-name-a-helpinfo-xml-file"></a>HelpInfo XML ファイルに名前を付ける方法

このトピックでは、HelpInfo XML ファイルと呼ばれる、更新可能なヘルプ情報ファイルに必要な名前の形式について説明します。

## <a name="how-to-name-a-helpinfo-xml-file"></a>HelpInfo XML ファイルに名前を付ける方法

HelpInfo XML ファイルには、次の形式の名前を付ける必要があります。

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

名前の要素は次のとおりです。

ModuleName コマンドレットが返す**Moduleinfo**オブジェクトの**Name**プロパティの値を[指定します](/powershell/module/Microsoft.PowerShell.Core/Get-Module)。

ModuleGUID モジュールマニフェスト内の**guid**キーの値。

たとえば、モジュール名が "TestModule" で、モジュール GUID が 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 の場合、モジュールの HelpInfo XML ファイルの名前は次のようになります。

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`