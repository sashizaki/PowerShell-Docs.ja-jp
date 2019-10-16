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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367261"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a>更新可能なヘルプ CAB ファイルで許可されるファイルの種類

このトピックでは、更新可能なヘルプ CAB ファイルのコンテンツ要件について説明します。

## <a name="updatable-help-cab-file-requirements"></a>更新可能なヘルプ CAB ファイルの要件

圧縮されていない CAB ファイルの内容は、既定で 1 GB に制限されています。 この[制限を回避](/powershell/module/Microsoft.PowerShell.Core/Save-Help)するには、ユーザー[は update-help コマンドレットと help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドレットの**Force**パラメーターを使用する必要があります。

インターネットからダウンロードされたヘルプファイルのセキュリティを確保するために、更新可能なヘルプ CAB ファイルには、以下に示すファイルの種類のみを含めることができます。 Update-help[コマンドレット](/powershell/module/Microsoft.PowerShell.Core/Update-Help)は、ヘルプトピックスキーマに対してすべてのファイルを検証します。 @No__t 0 のコマンドレットが、無効なファイルや許可されていない種類のファイルを検出した場合、無効なファイルはインストールされず、ユーザーのコンピューター上の CAB からのファイルのインストールが停止します。

- コマンドレットの XML ベースのヘルプトピックです。

- スクリプトと関数の XML ベースのヘルプトピックです。

- Windows PowerShell プロバイダーの XML ベースのヘルプトピックです。

- トピックの概要などのテキストベースのヘルプトピック。

[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)は、cab をアンパックするときに cab の内容を確認します。 @No__t-0 の場合、更新可能なヘルプ CAB ファイルで非対応のファイルの種類が検出されると、終了エラーが生成され、操作が停止されます。 準拠しているファイルの種類であっても、CAB からはヘルプファイルはインストールされません。