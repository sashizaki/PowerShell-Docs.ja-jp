---
title: エラー報告の概念 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- non-terminating errors [PowerShell SDK]
- errors [PowerShell SDK], described
- terminating errors [PowerShell SDK]
- errors [PowerShell SDK]
ms.openlocfilehash: ff010bbe1a87daa351ec13ed249ffc899781a8c3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774509"
---
# <a name="error-reporting-concepts"></a>エラー レポートの概念

Windows PowerShell には、エラーを報告するためのメカニズムが2つ用意されています。エラーを*終了*するメカニズムと、*終了しないエラー*のためのメカニズムがあります。 コマンドレットを実行しているホストアプリケーションが適切な方法で応答できるように、コマンドレットでエラーを正しく報告することが重要です。

コマンドレットでは、入力オブジェクトの処理を続行しない、または許可しないというエラーが発生した場合に、 [Throwterminatingerror *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)メソッドを呼び出す必要があります。 コマンドレットは、 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドを呼び出して、コマンドレットが入力オブジェクトの処理を続行できるときに、終了しないエラーを報告する必要があります。 どちらの方法でも、ホストアプリケーションでエラーの原因を調査するために使用できるエラーレコードが提供されます。

エラーが終了または終了しないエラーであるかどうかを判断するには、次のガイドラインに従います。

- エラーは、コマンドレットが現在のオブジェクトの処理を続行できないようにする場合、またはコンテンツに関係なく、他の入力オブジェクトを正常に処理しない場合に発生します。

- エラーは、内容に関係なく、現在のオブジェクトまたはその他の入力オブジェクトの処理をコマンドレットで続行しない場合に発生するエラーです。

- オブジェクトを受け入れたり返したりしないコマンドレットで発生した場合、または1つのオブジェクトのみを受け入れるか返すコマンドレットで発生した場合は、エラーが終了エラーになります。

- コマンドレットで現在のオブジェクトとその他の入力オブジェクトの処理を続行する場合は、エラーが終了しないエラーです。

- エラーは、特定の入力オブジェクトまたは入力オブジェクトのサブセットに関連付けられている場合は、終了しないエラーです。

## <a name="see-also"></a>参照

[Throwterminatingerror * のようになります。](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[WriteError (システム管理)](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[Windows PowerShell エラー レコード](./windows-powershell-error-records.md)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
