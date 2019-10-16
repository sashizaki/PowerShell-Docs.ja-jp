---
title: コマンドレット内のコマンドレットとスクリプトの呼び出し |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7040a5c-4a47-42df-a2ea-96b134a4ed9b
caps.latest.revision: 10
ms.openlocfilehash: f20708ff41d9a6de90090997a875ba5371eccd74
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364291"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a>コマンドレット内でコマンドレットとスクリプトを呼び出す

コマンドレットは、コマンドレットの入力処理メソッド内から他のコマンドレットとスクリプトを呼び出すことができます。 これにより、コードを書き直しなくても、既存のコマンドレットとスクリプトの機能をコマンドレットに追加できます。

## <a name="the-invoke-method"></a>Invoke メソッド

すべてのコマンドレットは、既存のコマンドレットを呼び出すことができます。これは、によってオーバーライドされる、[システム](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)の[呼び出し](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)などの入力処理メソッド内から呼び出されます。コマンドレット。 ただし、を呼び出すことが[できるのは、system.servicemodel クラスから](/dotnet/api/System.Management.Automation.Cmdlet)直接派生したコマンドレットだけです。 [PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)クラスから派生したコマンドレットを呼び出すことはできません。

System.servicemodel [*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)メソッドには、次のバリアントがあります。

System.string。この variant を[呼び出す](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)と、コマンドレットオブジェクトが呼び出され、"T" 型のオブジェクトのコレクションが返されます。

Emumerator この variant を[呼び出す](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)と、コマンドレットオブジェクトが呼び出され、厳密に型指定されたが返されます。 このバリアントを使用すると、ユーザーはコレクション内のオブジェクトを使用してカスタム操作を実行できます。

## <a name="examples"></a>例

|例|[説明]|
|-------------|-----------------|
|[コマンドレット内でのコマンドレットの呼び出し](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|この例は、別のコマンドレット内からコマンドレットを呼び出す方法を示しています。|
|[コマンドレット内でのスクリプトの呼び出し](./how-to-invoke-scripts-within-a-cmdlet.md)|この例では、別のコマンドレット内からコマンドレットに指定されたスクリプトを呼び出す方法を示します。|

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
