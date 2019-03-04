---
title: ヘルプ CAB ファイルの更新可能なで許可されているファイルの種類 |Microsoft Docs
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
ms.openlocfilehash: 931383858c0b83f0a9a66026c215e16481b89e9e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862838"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a>更新可能なヘルプ CAB ファイルで許可されるファイルの種類

このトピックでは、一覧し、ヘルプの更新可能な CAB ファイルのコンテンツの要件について説明します。

## <a name="updatable-help-cab-file-requirements"></a>更新可能なヘルプの CAB ファイルの要件

圧縮されていない CAB ファイルの内容は、既定では、1 GB に制限されます。 この制限をバイパスする、ユーザーが使用する必要、 **Force**のパラメーター、 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)と[Save-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)コマンドレット。
圧縮されていない CAB ファイルの内容は、既定では、1 GB に制限されます。 この制限をバイパスする、ユーザーが使用する必要、 **Force**のパラメーター、 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)と[Save-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)コマンドレット。

インターネットからダウンロードしたヘルプ ファイルのセキュリティを確保するために、ヘルプの更新可能な CAB ファイルは、以下に示すファイルの種類のみを含めることができます。 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドレット ヘルプ トピックのスキーマに対してすべてのファイルを検証します。 場合、`Update-Help`コマンドレットには、正しくないか許可されている型ではないファイルが検出すると、無効なファイルはインストールされませんし、ユーザーのコンピューターに cab ファイルからファイルのインストールを停止します。
インターネットからダウンロードしたヘルプ ファイルのセキュリティを確保するために、ヘルプの更新可能な CAB ファイルは、以下に示すファイルの種類のみを含めることができます。 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドレット ヘルプ トピックのスキーマに対してすべてのファイルを検証します。 場合、`Update-Help`コマンドレットには、正しくないか許可されている型ではないファイルが検出すると、無効なファイルはインストールされませんし、ユーザーのコンピューターに cab ファイルからファイルのインストールを停止します。

- XML ベースのコマンドレットのヘルプ。

- XML ベースのスクリプトや関数のトピックをヘルプ。

- XML ベースの Windows PowerShell プロバイダーのヘルプ。

- テキスト ベースのトピックに関するヘルプ トピックについてをなどです。

[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cab ファイルをアンパックする場合は、CAB の内容を確認します。 場合`Update-Help`ヘルプの更新可能な CAB ファイルに非準拠のファイルの種類、終了エラーを生成し、操作を停止を検索します。 準拠しているファイルの種類のものも含め cab ファイルからヘルプ ファイルはインストールされません。
[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cab ファイルをアンパックする場合は、CAB の内容を確認します。 場合`Update-Help`ヘルプの更新可能な CAB ファイルに非準拠のファイルの種類、終了エラーを生成し、操作を停止を検索します。 準拠しているファイルの種類のものも含め cab ファイルからヘルプ ファイルはインストールされません。