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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364441"
---
# <a name="getproc-tutorial"></a>GetProc チュートリアル

このセクションでは、Windows PowerShell によって提供される[Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットによく似た get Proc コマンドレットを作成するためのチュートリアルを提供します。 このチュートリアルでは、コマンドレットの実装方法とコードの説明を示すコードのフラグメントを示します。

## <a name="topics-in-this-tutorial"></a>このチュートリアルのトピック

このチュートリアルのトピックは、前のトピックで説明した内容を各トピックで作成することで、順番に読むように設計されています。

[パラメーターを指定せずにコマンドレットを作成する](./creating-a-cmdlet-without-parameters.md)このセクションでは、パラメーターを使用せずにローカルコンピューターから情報を取得するコマンドレットを作成し、その情報をパイプラインに書き込む方法について説明します。

[コマンドライン入力を処理するパラメーターの追加](./adding-parameters-that-process-command-line-input.md)このセクションでは、コマンドレットに渡された明示的なオブジェクトに基づいて入力を処理できるように、Get Proc コマンドレットにパラメーターを追加する方法について説明します。 ここで説明する実装では、名前に基づいてプロセスを取得し、その情報をパイプラインに書き込みます。

[パイプライン入力を処理するパラメーターの追加](./adding-parameters-that-process-pipeline-input.md)このセクションでは、コマンドレットがパイプラインを介して渡されたオブジェクトを処理できるように、Get Proc コマンドレットにパラメーターを追加する方法について説明します。 ここで説明する実装コマンドレットは、コマンドレットに渡されたオブジェクトに基づいてプロセスを取得し、その情報をパイプラインに書き込みます。

[コマンドレットに終了しないエラー報告を追加して](./adding-non-terminating-error-reporting-to-your-cmdlet.md)いますこのセクションでは、終了しないエラー報告をコマンドレットに追加する方法について説明します。 ここで説明する実装では、入力を処理するときに発生する終了しないエラーを検出し、エラーレコードをエラーストリームに書き込みます。

## <a name="see-also"></a>参照

[パラメーターを指定せずにコマンドレットを作成する](./creating-a-cmdlet-without-parameters.md)

[コマンドライン入力を処理するパラメーターの追加](./adding-parameters-that-process-command-line-input.md)

[パイプライン入力を処理するパラメーターの追加](./adding-parameters-that-process-pipeline-input.md)

[コマンドレットに終了しないエラー報告を追加しています](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
