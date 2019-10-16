---
title: エラー報告の概念 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- non-terminating errors [PowerShell SDK]
- errors [PowerShell SDK], described
- terminating errors [PowerShell SDK]
- errors [PowerShell SDK]
ms.assetid: 0dce97c0-bd9a-4691-8ca3-e8d5dea902c5
caps.latest.revision: 11
ms.openlocfilehash: 2f185e415e3effc2cf09a282ca1167e3bcfb7d6a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364621"
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

[Windows PowerShell エラーレコード](./windows-powershell-error-records.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
