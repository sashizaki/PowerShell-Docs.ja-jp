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
ms.openlocfilehash: 3562804157ebdfca561445a8671d726b55cc4efd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367261"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a>更新可能なヘルプ CAB ファイルで許可されるファイルの種類

このトピックでは、更新可能なヘルプ CAB ファイルのコンテンツ要件について説明します。

## <a name="updatable-help-cab-file-requirements"></a>更新可能なヘルプ CAB ファイルの要件

圧縮されていない CAB ファイルの内容は、既定で 1 GB に制限されています。 この[制限を回避](/powershell/module/Microsoft.PowerShell.Core/Save-Help)するには、ユーザー[は update-help コマンドレットと help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドレットの**Force**パラメーターを使用する必要があります。

インターネットからダウンロードされたヘルプファイルのセキュリティを確保するために、更新可能なヘルプ CAB ファイルには、以下に示すファイルの種類のみを含めることができます。 Update-help[コマンドレット](/powershell/module/Microsoft.PowerShell.Core/Update-Help)は、ヘルプトピックスキーマに対してすべてのファイルを検証します。 `Update-Help` コマンドレットで、無効なファイルや許可されていない種類のファイルが検出されると、無効なファイルはインストールされず、ユーザーのコンピューター上の CAB からのファイルのインストールが停止します。

- コマンドレットの XML ベースのヘルプトピックです。

- スクリプトと関数の XML ベースのヘルプトピックです。

- Windows PowerShell プロバイダーの XML ベースのヘルプトピックです。

- トピックの概要などのテキストベースのヘルプトピック。

[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)は、cab をアンパックするときに cab の内容を確認します。 更新可能なヘルプ CAB ファイルで準拠していないファイルの種類が検出されると `Update-Help` は終了エラーを生成し、操作を停止します。 準拠しているファイルの種類であっても、CAB からはヘルプファイルはインストールされません。