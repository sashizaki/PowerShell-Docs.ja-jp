---
title: GetProc チュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4663905f-560a-4e39-9b03-6db2c315c322
caps.latest.revision: 6
ms.openlocfilehash: bbd07a0d0abd30742b7e02482adedae3af43aca4
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068098"
---
# <a name="getproc-tutorial"></a>GetProc チュートリアル

このセクションによく似ていますが、Get-proc コマンドレットを作成する方法についてのチュートリアルを提供します、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットの Windows PowerShell によって提供されます。 このチュートリアルでは、コマンドレットの実装方法を示すコードのフラグメントとコードの説明を提供します。

## <a name="topics-in-this-tutorial"></a>このチュートリアルのトピック

このチュートリアルのトピックは、前のトピックで説明した内容に基づき、各トピックで、順番に読み取ることが設計されています。

[パラメーターを指定しないでコマンドレットを作成する](./creating-a-cmdlet-without-parameters.md)パラメーターを使用せず、ローカル コンピューターから情報を取得し、パイプラインに情報を書き込みますコマンドレットを作成する方法について説明します。

[そのプロセス コマンド ライン入力パラメーターを追加する](./adding-parameters-that-process-command-line-input.md)コマンドレットは、コマンドレットに渡される明示的なオブジェクトに基づく入力を処理できるように、Get-proc コマンドレットにパラメーターを追加する方法について説明します。 説明されている実装では、ここで、名前に基づいてプロセスを取得し、パイプラインに情報を書き込みます。

[そのプロセス パイプラインの入力パラメーターを追加する](./adding-parameters-that-process-pipeline-input.md)コマンドレットは、パイプラインを介して渡されたオブジェクトを処理できるように、Get-proc コマンドレットにパラメーターを追加する方法について説明します。 説明されている実装コマンドレットは、ここで、コマンドレットに渡されたオブジェクトに基づいて、プロセスを取得し、パイプラインに情報を書き込みます。

[終了しないエラーの報告を追加、コマンドレットに](./adding-non-terminating-error-reporting-to-your-cmdlet.md)終了しないエラーがレポートをコマンドレットに追加する方法について説明します。 ここで説明されている実装では、入力を処理するときに発生してエラー レコードをエラー ストリームに書き込みを終了しないエラーを検出します。

## <a name="see-also"></a>参照

[パラメーターを指定しないでコマンドレットを作成します。](./creating-a-cmdlet-without-parameters.md)

[コマンドライン入力を処理するパラメーターの追加](./adding-parameters-that-process-command-line-input.md)

[プロセス パイプラインの入力パラメーターを追加します。](./adding-parameters-that-process-pipeline-input.md)

[終了しないエラーが報告、コマンドレットを追加します。](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
