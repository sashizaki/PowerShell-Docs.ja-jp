---
title: 共通パラメーター名 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d0939cfa5bf90ec55f0c0afcdeff56223d9dc78d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782227"
---
# <a name="common-parameter-names"></a>共有パラメーター名

このトピックで説明するパラメーターは、*共通パラメーター*と呼ばれます。 これらは、Windows PowerShell ランタイムによってコマンドレットに追加され、コマンドレットで宣言することはできません。

> [!NOTE]
> これらのパラメーターは、プロバイダーのコマンドレットと、属性で修飾された関数にも追加され `CmdletBinding` ます。

## <a name="general-common-parameters"></a>一般的な共通パラメーター

次のパラメーターはすべてのコマンドレットに追加され、コマンドレットを実行するたびにアクセスできます。 これらのパラメーターは、system.servicemodel[パラメーター](/dotnet/api/System.Management.Automation.Internal.CommonParameters)クラスによって定義されます。

### <a name="debug-alias-db"></a>デバッグ (エイリアス: db)

データ型: SwitchParameter

このパラメーターは、コマンドラインで表示できるプログラマレベルのデバッグメッセージを指定します。 これらのメッセージは、コマンドレットの操作のトラブルシューティングを目的としており、[このメソッドの](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)呼び出しによって生成されます。 デバッグメッセージをローカライズする必要はありません。

### <a name="erroraction-alias-ea"></a>ErrorAction (エイリアス: ea)

データ型: 列挙型

このパラメーターは、エラーが発生したときに実行するアクションを指定します。 このパラメーターに指定できる値[は、system.string 列挙型](/dotnet/api/System.Management.Automation.ActionPreference)によって定義されます。

### <a name="errorvariable-alias-ev"></a>ErrorVariable (別名: ev)

データ型: 文字列

このパラメーターは、エラーが発生したときにオブジェクトを配置する変数を指定します。 この変数にを追加するには、変数をクリアして設定するのではなく、+*varname*を使用します。

### <a name="outvariable-alias-ov"></a>OutVariable (エイリアス: ov-es)

データ型: 文字列

このパラメーターは、コマンドレットによって生成されるすべての出力オブジェクトを配置する変数を指定します。 この変数にを追加するには、変数をクリアして設定するのではなく、+*varname*を使用します。

### <a name="outbuffer-alias-ob"></a>OutBuffer (エイリアス: ob)

データ型: Int32

このパラメーターは、オブジェクトがパイプラインから渡される前に、出力バッファーに格納するオブジェクトの数を定義します。 既定では、オブジェクトはパイプラインのすぐ下に渡されます。

### <a name="verbose-alias-vb"></a>Verbose (エイリアス: vb)

データ型: SwitchParameter

このパラメーターは、コマンドラインで表示できる説明メッセージをコマンドレットが書き込むかどうかを指定します。 これらのメッセージは、ユーザーに追加のヘルプを提供することを目的としています。これは、[システム](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)の呼び出しによって生成されます。

### <a name="warningaction-alias-wa"></a>警告動作 (エイリアス: wa)

データ型: 列挙型

このパラメーターは、コマンドレットが警告メッセージを書き込むときに実行するアクションを指定します。 このパラメーターに指定できる値[は、system.string 列挙型](/dotnet/api/System.Management.Automation.ActionPreference)によって定義されます。

### <a name="warningvariable-alias-wv"></a>警告変数 (エイリアス: wv)

データ型: 文字列

このパラメーターは、警告メッセージを保存できる変数を指定します。 この変数にを追加するには、変数をクリアして設定するのではなく、+*varname*を使用します。

## <a name="risk-mitigation-parameters"></a>リスク軽減パラメーター

次のパラメーターは、アクションを実行する前に確認を要求するコマンドレットに追加されます。 確認要求の詳細については、「[確認の要求](./requesting-confirmation-from-cmdlets.md)」を参照してください。 これらのパラメーターは、 [Shouldprocessparameters](/dotnet/api/System.Management.Automation.Internal.ShouldProcessParameters)クラスによって定義されます。

### <a name="confirm-alias-cf"></a>Confirm (alias: cf)

データ型: SwitchParameter

このパラメーターは、コマンドレットで、ユーザーが操作を続行するかどうかを確認するプロンプトを表示するかどうかを指定します。

### <a name="whatif-alias-wi"></a>WhatIf (エイリアス: wi)

データ型: SwitchParameter

このパラメーターは、コマンドレットが、実際には何も操作を実行せずにコマンドレットを実行した場合の影響を説明するメッセージを書き込むかどうかを指定します。

## <a name="transaction-parameters"></a>トランザクションパラメーター

トランザクションをサポートするコマンドレットには、次のパラメーターが追加されています。 これらのパラメーターは、system.string[クラスに](/dotnet/api/System.Management.Automation.Internal.TransactionParameters)よって定義されます。

### <a name="usetransaction-alias-usetx"></a>UseTransaction (エイリアス: usetx)

データ型: SwitchParameter

このパラメーターは、コマンドレットが現在のトランザクションを使用してアクションを実行するかどうかを指定します。

## <a name="see-also"></a>参照

[System.... Commonparameters](/dotnet/api/System.Management.Automation.Internal.CommonParameters)

[Shouldprocessparameters (システム管理)](/dotnet/api/System.Management.Automation.Internal.ShouldProcessParameters)

[システムの管理. 内部パラメーター](/dotnet/api/System.Management.Automation.Internal.TransactionParameters)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
