---
title: コマンドレットから確認を求める |Microsoft Docs
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
ms.openlocfilehash: ec441831f5e3231a44c9875d1b6d2bf6280a6965
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853398"
---
# <a name="requesting-confirmation-from-cmdlets"></a>コマンドレットからの確認を要求する

コマンドレットは、Windows PowerShell 環境の外であるシステムに変更を加えるとしているときに、確認を要求する必要があります。 たとえば、コマンドレットは、ユーザー アカウントを追加またはプロセスを停止するのには場合に進む前に、コマンドレットは、ユーザーから送信される確認必要があります。 これに対し、コマンドレットを Windows PowerShell 変数を変更する場合は、コマンドレットが、確認を要求する必要はありません。

確認要求を行うために、コマンドレットを確認要求では、サポートを呼び出す必要があります示す必要があります、 [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.Shouldcontinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)確認要求メッセージを表示する (省略可能) のメソッド。

## <a name="supporting-confirmation-requests"></a>確認要求をサポートしています。

確認要求をサポートするために、コマンドレットを設定する必要があります、`SupportsShouldProcess`コマンドレットの属性のパラメーター`true`します。 これにより、`Confirm`と`WhatIf`Windows PowerShell によって提供されるコマンドレットのパラメーター。 `Confirm`パラメーター、確認要求が表示されるかどうかをユーザーが管理を使用できます。 `WhatIf`パラメーターには、コマンドレットでメッセージを表示する必要があります、そのアクションを実行するかを判断できます。 手動で追加しないでください、`Confirm`と`WhatIf`コマンドレットのパラメーター。

次の例では、確認要求をサポートするコマンドレットの属性宣言を示します。

```csharp
[Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
        SupportsShouldProcess = true)]
```

## <a name="calling-the-confirmation-request-methods"></a>確認要求のメソッドの呼び出し

コマンドレットのコードで呼び出し、 [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッド、システムを変更する操作を実行する前にします。 場合の値が返され、呼び出し、コマンドレットを設計`false`操作は実行されず、およびコマンドレットは、次の操作を処理します。

## <a name="calling-the-shouldcontinue-method"></a>ShouldContinue メソッドを呼び出す

ほとんどのコマンドレットのみを使用して確認を要求する、 [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッド。 ただし、場合によっては、追加の確認を必要があります。 このような場合は、補完、 [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)への呼び出しで呼び出し、 [System.Management.Automation.Cmdlet.Shouldcontinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッド。 これにより、コマンドレットやプロバイダーのスコープをより細かく制御する、 **[すべてはい]** 確認プロンプトに応答します。

コマンドレットを呼び出す場合、 [System.Management.Automation.Cmdlet.Shouldcontinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドでは、コマンドレットを提供する必要がありますも、`Force`スイッチ パラメーター。 ユーザーが指定されている場合`Force`コマンドレットを呼び出す必要があります、ユーザーが、コマンドレットを呼び出すと[System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)への呼び出しをバイパスする必要がありますが、 [System.Management.Automation.Cmdlet.Shouldcontinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)します。

[System.Management.Automation.Cmdlet.Shouldcontinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)ユーザーを求められますことはできません、非対話型環境から呼び出されたときに例外がスローされます。 追加、`Force`パラメーターにより非対話型環境で呼び出された場合は、コマンドを実行もできるようになります。

次の例は、呼び出す方法を示しています。 [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.Shouldcontinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)します。

```csharp
if (ShouldProcess (...) )
{
  if (Force || ShouldContinue(...))
  {
     // Add code that performs the operation.
  }
}
```

動作を[System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出しは、コマンドレットが呼び出される環境によって異なります。 前のガイドラインを使用に役立つコマンドレットがホスト環境に関係なく、他のコマンドレットで一貫して動作することを確認します。

呼び出し元の例については、 [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッドを参照してください[依頼の確認方法](./how-to-request-confirmations.md)します。

## <a name="specify-the-impact-level"></a>影響のレベルを指定します。

コマンドレットを作成する場合は、変更の影響レベル (重要度) を指定します。 これを行うには、値を設定、`ConfirmImpact`高、中、低コマンドレットの属性のパラメーター。 値を指定する`ConfirmImpact`のみときに指定することも、`SupportsShouldProcess`コマンドレットのパラメーター。

ほとんどのコマンドレットには明示的に指定する必要はありません`ConfirmImpact`します。  代わりに、中であるパラメーターの既定の設定を使用します。 設定した場合`ConfirmImpact`高 に既定では、操作が確認されます。 ハード ディスク ボリュームを再フォーマットなどの高度に破壊的な操作には、この設定を予約します。

## <a name="calling-non-confirmation-methods"></a>非確認メソッドを呼び出す

コマンドレットまたはプロバイダーがメッセージを送信、確認を要求する必要がありますは、次の 3 つのメソッドを呼び出すことができます。 使用しないでください、 [System.Management.Automation.Cmdlet.Writeobject*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)ため、これらの型のメッセージを送信するメソッド[System.Management.Automation.Cmdlet.Writeobject*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)出力の混在コマンドレットまたはプロバイダーの通常の出力で困難スクリプトを記述します。

- コマンドレットまたはプロバイダーを呼び出すことができます、ユーザーに警告して、操作を続行に、 [System.Management.Automation.Cmdlet.Writewarning*](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning)メソッド。

- 追加の情報を使用して、ユーザーを取得できる、`Verbose`パラメーターでは、コマンドレット、プロバイダーが呼び出すことができます、 [System.Management.Automation.Cmdlet.Writeverbose*](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)メソッド。

- コマンドレットまたはプロバイダーを呼び出すことが他の開発者、または製品サポートについては、デバッグ レベルの詳細を提供するには[System.Management.Automation.Cmdlet.Writedebug*](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)メソッド。 ユーザーを使用してこの情報を取得することができます、`Debug`パラメーター。

コマンドレットとプロバイダーは、まず Windows PowerShell の外部のシステムを変更する操作の実行を試みる前に、確認を要求する次のメソッドを呼び出します。

- [System.Management.Automation.Cmdlet.Shouldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)

- [System.Management.Automation.Provider.Cmdletprovider.Shouldprocess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)

呼び出すときは、 [System.Management.Automation.Cmdlet.Shouldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッドで、ユーザーが、ユーザーがコマンドを呼び出す方法に基づいて、操作を確認するメッセージが表示されます。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
