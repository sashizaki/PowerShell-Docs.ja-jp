---
title: コマンドレット内のコマンドレットとスクリプトの呼び出し |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3d5f76242c02763c41b81215bbb031e19869066a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786579"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a>コマンドレット内でコマンドレットとスクリプトを呼び出す

コマンドレットは、コマンドレットの入力処理メソッド内から他のコマンドレットとスクリプトを呼び出すことができます。 これにより、コードを書き直しなくても、既存のコマンドレットとスクリプトの機能をコマンドレットに追加できます。

## <a name="the-invoke-method"></a>Invoke メソッド

すべてのコマンドレットで既存のコマンドレットを呼び出すことができます。これは、コマンドレットによってオーバーライドさ[れる、入力](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)処理メソッド (たとえば、) から[、システムの呼び出しメソッドを](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)呼び出すことによって実行できます。 ただし、を呼び出すことが[できるのは、system.servicemodel クラスから](/dotnet/api/System.Management.Automation.Cmdlet)直接派生したコマンドレットだけです。 [PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)クラスから派生したコマンドレットを呼び出すことはできません。

System.servicemodel [*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)メソッドには、次のバリアントがあります。

System.string。この variant を[呼び出す](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)と、コマンドレットオブジェクトが呼び出され、"T" 型のオブジェクトのコレクションが返されます。

Emumerator この variant を[呼び出す](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)と、コマンドレットオブジェクトが呼び出され、厳密に型指定されたが返されます。 このバリアントを使用すると、ユーザーはコレクション内のオブジェクトを使用してカスタム操作を実行できます。

## <a name="examples"></a>例

|例|説明|
|-------------|-----------------|
|[コマンドレット内でのコマンドレットの呼び出し](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|この例は、別のコマンドレット内からコマンドレットを呼び出す方法を示しています。|
|[コマンドレット内でのスクリプトの呼び出し](./how-to-invoke-scripts-within-a-cmdlet.md)|この例では、別のコマンドレット内からコマンドレットに指定されたスクリプトを呼び出す方法を示します。|

## <a name="see-also"></a>参照

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
