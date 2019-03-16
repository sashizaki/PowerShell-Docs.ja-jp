---
title: エラー レポートの概念 |Microsoft Docs
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
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054409"
---
# <a name="error-reporting-concepts"></a>エラー レポートの概念

Windows PowerShell がエラーを報告した 2 つのメカニズムを提供します: 1 つのメカニズム*終了エラー*と別のメカニズムの*未終了エラー*します。 正しく、コマンドレットを実行しているホスト アプリケーションが適切な方法で対応できるようにエラーを報告するコマンドレットの重要なです。

コマンドレットを呼び出す必要があります、 [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)メソッドのエラーが発生する場合はまたはの入力オブジェクトの処理を続行するためのコマンドレットを許可しないでください。 コマンドレットを呼び出す必要があります、 [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)コマンドレットが入力オブジェクトの処理を続行することができる場合、未終了エラーを報告するメソッド。 どちらの方法では、エラーの原因を調査するホスト アプリケーションが使用できるエラー レコードを提供します。

次のガイドラインを使用すると、エラーが終了するかどうか未終了エラーを判断します。

- エラーは、現在のオブジェクトの処理を継続から、またはそのコンテンツに関係なく、さらに入力オブジェクトはすべてを正常に処理から、コマンドレットを防ぐことが場合終端エラーです。

- エラーは、現在のオブジェクトまたはそのコンテンツに関係なく、さらに入力オブジェクトはすべての処理を続行する、コマンドレットを設定したくない場合、終了エラーです。

- エラーは、受け付けられないか、オブジェクトを取得するコマンドレットで発生した場合、またはを受け入れるか 1 つだけオブジェクトを取得するコマンドレットで発生した場合、終了エラーです。

- エラーは、コマンドレットを現在のオブジェクトとさらに入力オブジェクトの処理を続行する場合に、未終了エラーです。

- エラーは、特定の入力オブジェクトまたは入力オブジェクトのサブセットに関連している場合に、未終了エラーです。

## <a name="see-also"></a>参照

[System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[Windows PowerShell のエラー レコード](./windows-powershell-error-records.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
