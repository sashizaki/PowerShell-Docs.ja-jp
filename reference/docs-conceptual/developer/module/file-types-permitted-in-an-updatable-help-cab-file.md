---
title: 更新可能なヘルプ CAB ファイルで許可されているファイルの種類 |Microsoft Docs
ms.custom: ''
ms.date: 03/22/2012
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Windows PowerShell 3.0
ms.assetid: acabdb93-c41a-4b8d-acbe-45cdab91e198
caps.latest.revision: 10
ms.openlocfilehash: 6e9e51a50226430465726d27874e02e98ee67672
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560986"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a>更新可能なヘルプ CAB ファイルで許可されるファイルの種類

このトピックでは、更新可能なヘルプ CAB ファイルのコンテンツ要件について説明します。

## <a name="updatable-help-cab-file-requirements"></a>更新可能なヘルプ CAB ファイルの要件

圧縮されていない CAB ファイルの内容は、既定で 1 GB に制限されています。 この[制限を回避](/powershell/module/Microsoft.PowerShell.Core/Save-Help)するには、ユーザー[は update-help コマンドレットと help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドレットの**Force**パラメーターを使用する必要があります。

インターネットからダウンロードされたヘルプファイルのセキュリティを確保するために、更新可能なヘルプ CAB ファイルには、以下に示すファイルの種類のみを含めることができます。 Update-help[コマンドレット](/powershell/module/Microsoft.PowerShell.Core/Update-Help)は、ヘルプトピックスキーマに対してすべてのファイルを検証します。 `Update-Help`コマンドレットで、無効なファイルや許可されていない種類のファイルが検出された場合、無効なファイルはインストールされず、ユーザーのコンピューター上の CAB からのファイルのインストールは停止します。

- コマンドレットの XML ベースのヘルプトピックです。

- スクリプトと関数の XML ベースのヘルプトピックです。

- Windows PowerShell プロバイダーの XML ベースのヘルプトピックです。

- トピックの概要などのテキストベースのヘルプトピック。

[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)は、cab をアンパックするときに cab の内容を確認します。 は `Update-Help` 、更新可能なヘルプ CAB ファイルで準拠していないファイルの種類を検出すると、終了エラーを生成し、操作を停止します。 準拠しているファイルの種類であっても、CAB からはヘルプファイルはインストールされません。
