---
title: コマンドレットからの確認を要求する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ConfirmImpact [PowerShell Programmer's Guide], described
- ShouldContinue [PowerShell Programmer's Guide], described
- user feedback [PowerShell Programmer's Guide], requesting
- ShouldProcess [PowerShell Programmer's Guide], described
- ConfirmPreference [PowerShell Programmer's Guide], described
ms.assetid: 37d6e87f-57b7-40bd-b645-392cf0b6e88e
caps.latest.revision: 13
ms.openlocfilehash: 0c0517ef7fbd5ae6434773a2dfe276f3a8c35f39
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369531"
---
# <a name="requesting-confirmation-from-cmdlets"></a>コマンドレットからの確認を要求する

コマンドレットは、Windows PowerShell 環境の外部にあるシステムを変更しようとしているときに確認を要求する必要があります。 たとえば、コマンドレットを使用してユーザーアカウントを追加しようとしたり、プロセスを停止したりする場合は、コマンドレットを実行する前に、ユーザーからの確認が必要になります。 これに対して、コマンドレットが Windows PowerShell 変数を変更しようとしている場合、コマンドレットで確認が必要になることはありません。

確認要求を行うには、コマンドレットで確認要求がサポートされていることを示す必要があります。また、このコマンドレットは、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) .............. [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)(省略可能) 確認要求メッセージを表示するメソッド。

## <a name="supporting-confirmation-requests"></a>確認要求のサポート

確認要求をサポートするには、コマンドレットで、コマンドレット属性の `SupportsShouldProcess` パラメーターを `true` に設定する必要があります。 これにより、Windows PowerShell によって提供される `Confirm` および `WhatIf` コマンドレットパラメーターが有効になります。 @No__t_0 パラメーターを使用すると、確認要求を表示するかどうかをユーザーが制御できます。 @No__t_0 パラメーターを使用すると、コマンドレットでメッセージを表示するかどうか、またはそのアクションを実行するかどうかをユーザーが決定できます。 コマンドレットに `Confirm` パラメーターと `WhatIf` パラメーターを手動で追加しないでください。

次の例は、確認要求をサポートするコマンドレット属性の宣言を示しています。

```csharp
[Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
        SupportsShouldProcess = true)]
```

## <a name="calling-the-confirmation-request-methods"></a>確認要求メソッドの呼び出し

コマンドレットのコードで、システムを変更する操作を実行する前に、 [system.string メソッドを呼び出します。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 呼び出しが `false` の値を返す場合、操作は実行されず、コマンドレットは次の操作を処理するようにコマンドレットを設計します。

## <a name="calling-the-shouldcontinue-method"></a>"メソッドの続行" メソッドの呼び出し

ほとんどのコマンドレットでは、 [System.](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) ....................... ただし、場合によっては、追加の確認が必要になる場合があります。 このような場合は、 [system.](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) [.](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) ....................................... これにより、コマンドレットまたはプロバイダーは、確認プロンプトに対する **[はい] のすべて**の応答のスコープをより細かく制御できます。

コマンドレットで[system.servicemodel メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)呼び出す場合は、コマンドレットで `Force` スイッチパラメーターも指定する必要があります。 ユーザーがコマンドレットを呼び出したときに、ユーザーが `Force` を指定した場合、コマンドレットは引き続き system.object を[呼び出す必要](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)がありますが、このコマンドレットでは、system.object の呼び出しをバイパスする必要があり[ます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)

ユーザーにプロンプトが表示されない非対話型環境から呼び出された場合は、例外が[スローされ](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)ます ()。 @No__t_0 パラメーターを追加すると、非対話型環境で呼び出された場合でも、コマンドを実行できるようになります。

次の例では、.............................. コマンド[レット](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)[を呼び出す方法](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)を示します。

```csharp
if (ShouldProcess (...) )
{
  if (Force || ShouldContinue(...))
  {
     // Add code that performs the operation.
  }
}
```

コマンドレットの呼び出しの動作は、コマンドレットが呼び出される環境によって[異なる場合があります](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)。 前のガイドラインを使用すると、ホスト環境に関係なく、コマンドレットを他のコマンドレットと一貫して動作させることができます。

System.servicemodel メソッドの呼び出しの例については、「確認[を要求する方法](./how-to-request-confirmations.md)」を参照して[ください。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)

## <a name="specify-the-impact-level"></a>影響レベルを指定します

コマンドレットを作成するときに、変更の影響レベル (重大度) を指定します。 これを行うには、コマンドレット属性の `ConfirmImpact` パラメーターの値を High、Medium、または Low に設定します。 @No__t_0 の値は、コマンドレットの `SupportsShouldProcess` パラメーターも指定する場合にのみ指定できます。

ほとんどのコマンドレットでは、`ConfirmImpact` を明示的に指定する必要はありません。  代わりに、[中] のパラメーターの既定の設定を使用します。 @No__t_0 を [高] に設定すると、既定で操作が確認されます。 ハードディスクボリュームの再フォーマットなど、非常に破壊的な操作を行う場合は、この設定を予約します。

## <a name="calling-non-confirmation-methods"></a>確認以外のメソッドの呼び出し

コマンドレットまたはプロバイダーがメッセージを送信する必要があるが、確認を要求しない場合は、次の3つのメソッドを呼び出すことができます。 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッドを使用してこれらの型のメッセージを送信するのは避けてください。 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)出力は、コマンドレットまたはプロバイダーの通常の出力と混在しているためです。これにより、スクリプトの書き込みが困難になります。

- ユーザーに注意して操作を続行するには、コマンドレットまたはプロバイダー[が、system.string メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning)呼び出すことができます。

- @No__t_0 パラメーターを使用してユーザーが取得できる追加情報を提供するために、コマンドレットまたはプロバイダー[は、system.servicemodel メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)呼び出すことができます。

- 他の開発者や製品サポートに関するデバッグレベルの詳細を提供するために、コマンドレットまたはプロバイダーは、system.servicemodel[デバッグ](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)メソッドを呼び出すことができます。 ユーザーは、`Debug` パラメーターを使用してこの情報を取得できます。

コマンドレットとプロバイダーは、まず次のメソッドを呼び出して、Windows PowerShell の外部でシステムを変更する操作の実行を試みる前に、確認を要求します。

- [System.... コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)

- [システムの管理..........](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)

これを行うには、ユーザーがコマンドを呼び出した方法に基づいて操作を確認するように求めるメッセージを表示して、[このメソッドを呼び出します。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
