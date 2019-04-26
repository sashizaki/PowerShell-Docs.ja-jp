---
title: コマンドレットとコマンドレット内でスクリプトを呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7040a5c-4a47-42df-a2ea-96b134a4ed9b
caps.latest.revision: 10
ms.openlocfilehash: f20708ff41d9a6de90090997a875ba5371eccd74
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067673"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a>コマンドレット内でコマンドレットとスクリプトを呼び出す

コマンドレットは、その他のコマンドレットとコマンドレットのメソッドを処理する入力の中からスクリプトを呼び出すことができます。 これにより、コードを書き直すことがなく、コマンドレットを既存のコマンドレットとスクリプトの機能を追加することができます。

## <a name="the-invoke-method"></a>メソッドを呼び出す

すべてのコマンドレットは、呼び出すことによって、既存のコマンドレットを呼び出すことができます、 [System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)メソッドなど、メソッドの処理の入力内から[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)、つまり、コマンドレットによってオーバーライドします。 ただしから直接派生したコマンドレットのみを呼び出すことができます、 [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)クラス。 派生したコマンドレットを呼び出すことはできません、 [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)クラス。

[System.Management.Automation.Cmdlet.Invoke*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)メソッドには次のバリエーション。

[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)このバリアントは、コマンドレット オブジェクトを呼び出すし、"T"型のオブジェクトのコレクションを返します。

[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)このバリアントはコマンドレット オブジェクトを呼び出すし、厳密に型指定された emumerator を返します。 このバリアントでは、カスタム操作を実行するコレクション内のオブジェクトを使用するユーザーを許可します。

## <a name="examples"></a>例

|例|説明|
|-------------|-----------------|
|[コマンドレット内でコマンドレットを呼び出す](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|この例では、別のコマンドレット内のコマンドレットを呼び出す方法を示します。|
|[コマンドレット内でスクリプトを呼び出す](./how-to-invoke-scripts-within-a-cmdlet.md)|この例では、別のコマンドレット内からコマンドレットに指定されているスクリプトを呼び出す方法を示します。|

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
