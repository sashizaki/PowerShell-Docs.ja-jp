---
title: コマンドレット コードの例 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6fed2f68-ce6d-4a8f-bf21-f94f27a155c2
caps.latest.revision: 9
ms.openlocfilehash: 936728d64f30a08fb9e2fa9ccef103683594aa3e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068200"
---
# <a name="examples-of-cmdlet-code"></a>コマンドレット コードの例

このセクションでは、独自のコマンドレットの記述を開始するために使用できるコマンドレットのコードの例を示します。

> [!IMPORTANT]
> コマンドレットを作成する手順を実行する場合に、「[コマンドレットの記述に関するチュートリアル](./tutorials-for-writing-cmdlets.md)します。

## <a name="in-this-section"></a>このセクションの内容

[単純なコマンドレットの記述方法](./how-to-write-a-simple-cmdlet.md)コマンドレット コードの基本構造を示します。

[コマンドレットのパラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)この例は、異なる型のパラメーターを宣言する方法を示します。

[パラメーターの設定の宣言方法](./how-to-declare-parameter-sets.md)コマンドレットを実行するアクションを変更できるパラメーターのセットを宣言する方法を示します。

[パラメーターの入力の検証方法](./how-to-validate-parameter-input.md)これらの例は、パラメーターの入力を検証する方法を示します。

[動的パラメーターを宣言する方法](./how-to-declare-dynamic-parameters.md)この例は、実行時に追加されるパラメーターを宣言する方法を示します。

[コマンドレット内でスクリプトを呼び出す方法](./how-to-invoke-scripts-within-a-cmdlet.md)コマンドレットに指定されているスクリプトを起動する方法を示します。

[入力処理メソッドをオーバーライドする方法](./how-to-override-input-processing-methods.md)これらの例は、BeginProcessing、ProcessRecord、EndProcessing メソッドをオーバーライドするために使用する基本的な構造を示します。

[ShouldProcess の呼び出しをサポートする方法](./how-to-request-confirmations.md)この例では、どのように[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドは、コマンドレット内からを呼び出す必要があります。

[トランザクションをサポートする方法](./how-to-support-transactions.md)コマンドレットは、トランザクションをサポートしているを指定する方法と、トランザクション内でコマンドレットを使用する場合に実行するアクションを実装する方法を示します。

[ジョブのサポート方法](./how-to-support-jobs.md)コマンドレットを記述するときにジョブをサポートする方法を示します。

[コマンドレットからのコマンドレットを呼び出す方法](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)この例は、別のコマンドレットが呼び出されたコマンドレットの機能を開発しているコマンドレットに追加することができます内からコマンドレットを呼び出す方法を示します。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
