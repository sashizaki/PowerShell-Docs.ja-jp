---
title: 一般的なパラメーター名 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0db9f54c-4014-4450-9e81-c9f5fe562a0e
caps.latest.revision: 12
ms.openlocfilehash: c65deeda6b2ef1b52de55035dc606259a7f2d232
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068430"
---
# <a name="common-parameter-names"></a>共有パラメーター名

このトピックで説明されているパラメーターと呼びます*共通パラメーター*します。 Windows PowerShell ランタイムではコマンドレットに追加され、コマンドレットで宣言することはできません。

> [!NOTE]
> プロバイダー コマンドレットと関数で装飾されますが、これらのパラメーターが追加も、`CmdletBinding`属性。

## <a name="general-common-parameters"></a>一般的な共通パラメーター

次のパラメーターは、すべてのコマンドレットに追加され、コマンドレットが実行されるたびにアクセスできます。 これらのパラメーターがによって定義されている、 [System.Management.Automation.Internal.Commonparameters](/dotnet/api/System.Management.Automation.Internal.CommonParameters)クラス。

### <a name="debug-alias-db"></a>Debug (別名: db)

データの種類:SwitchParameter

このパラメーターを指定するかどうかのメッセージ レベルのプログラマのデバッグ コマンド ラインに表示されることができます。 これらのメッセージは、コマンドレットの操作をトラブルシューティングするためのものし、への呼び出しによって生成される、 [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)メソッド。 デバッグ メッセージをローカライズする必要はありません。

### <a name="erroraction-alias-ea"></a>ErrorAction (別名: ea)

データの種類:列挙値

このパラメーターは、どのようなアクションが実行される、エラーが発生したときに指定します。 このパラメーターの値がによって定義されている、 [System.Management.Automation.Actionpreference](/dotnet/api/System.Management.Automation.ActionPreference)列挙体。

### <a name="errorvariable-alias-ev"></a>ErrorVariable (別名: ev)

データの種類:String

このパラメーターは、エラーが発生したときに、オブジェクトを配置先となる変数を指定します。 この変数に追加するには、使用 +*varname*オフにして、変数の設定ではなく。

### <a name="outvariable-alias-ov"></a>OutVariable (別名: ov)

データの種類:String

このパラメーターは、配置先となるすべての出力コマンドレットによって生成されたオブジェクト変数を指定します。 この変数に追加するには、使用 +*varname*オフにして、変数の設定ではなく。

### <a name="outbuffer-alias-ob"></a>OutBuffer (別名: ob)

データの種類:Int32

このパラメーターは、すべてのオブジェクトがパイプラインを介して渡される前に、出力バッファーに格納するオブジェクトの数を定義します。 既定では、オブジェクトはパイプラインは、すぐに渡されます。

### <a name="verbose-alias-vb"></a>Verbose (別名: vb)

データの種類:SwitchParameter

このパラメーターは、コマンドレットがコマンドラインで表示できる説明メッセージを書き込むかどうかを指定します。 これらのメッセージは、ユーザーに役立つ追加情報を提供するためのものし、への呼び出しによって生成される、 [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)メソッド。

### <a name="warningaction-alias-wa"></a>WarningAction (別名: wa)

データの種類:列挙値

このパラメーターは、どのようなアクションを実行するコマンドレットは、警告メッセージを書き込むときに指定します。 このパラメーターの値がによって定義されている、 [System.Management.Automation.Actionpreference](/dotnet/api/System.Management.Automation.ActionPreference)列挙体。

### <a name="warningvariable-alias-wv"></a>WarningVariable (別名: wv)

データの種類:String

このパラメーターは、警告メッセージを保存する変数を指定します。 この変数に追加するには、使用 +*varname*オフにして、変数の設定ではなく。

## <a name="risk-mitigation-parameters"></a>リスクを緩和するためのパラメーター

次のパラメーターは、それらのアクションの実行前に確認を要求するコマンドレットに追加されます。 確認要求の詳細については、次を参照してください。[確認を要求する](./requesting-confirmation-from-cmdlets.md)します。 これらのパラメーターがによって定義されている、 [System.Management.Automation.Internal.Shouldprocessparameters](/dotnet/api/System.Management.Automation.Internal.ShouldProcessParameters)クラス。

### <a name="confirm-alias-cf"></a>Confirm (別名: cf)

データの種類:SwitchParameter

このパラメーターは、コマンドレットに入力を求めるかどうか、ユーザーは続行することを確認してくださいプロンプトが表示されるかどうかを指定します。

### <a name="whatif-alias-wi"></a>WhatIf (別名: wi)

データの種類:SwitchParameter

このパラメーターは、コマンドレットで実際に操作を実行せず、コマンドレットを実行することの効果を説明するメッセージを書き込むかどうかを指定します。

## <a name="transaction-parameters"></a>トランザクション パラメーター

次のパラメーターは、トランザクションをサポートするコマンドレットに追加されます。 これらのパラメーターがによって定義されている、 [System.Management.Automation.Internal.Transactionparameters](/dotnet/api/System.Management.Automation.Internal.TransactionParameters)クラス。

### <a name="usetransaction-alias-usetx"></a>UseTransaction (別名: usetx)

データの種類:SwitchParameter

このパラメーターは、コマンドレットが、現在のトランザクションを使用して、操作を実行するかどうかを指定します。

## <a name="see-also"></a>参照

[System.Management.Automation.Internal.Commonparameters](/dotnet/api/System.Management.Automation.Internal.CommonParameters)

[System.Management.Automation.Internal.Shouldprocessparameters](/dotnet/api/System.Management.Automation.Internal.ShouldProcessParameters)

[System.Management.Automation.Internal.Transactionparameters](/dotnet/api/System.Management.Automation.Internal.TransactionParameters)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
