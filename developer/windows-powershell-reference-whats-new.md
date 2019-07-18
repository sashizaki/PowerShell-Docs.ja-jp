---
title: Windows PowerShell リファレンス - 新機能
ms.date: 09/13/2016
ms.topic: article
ms.openlocfilehash: 364d081ddf2f87ceeaa47732266a35f4a126246f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080528"
---
# <a name="whats-new"></a>新機能

Windows PowerShell 2.0 では、コマンドレット、プロバイダー、およびホスト アプリケーションを作成するときに使用するため、次の新機能を提供します。

## <a name="modules"></a>モジュール

パッケージ化し、モジュールを使用して、Windows PowerShell のソリューションを配布できます。 モジュールにより、パーティションをするには、整理、および再利用可能な自己完結型の単位に、Windows PowerShell コードを抽象化します。 モジュールの詳細については、Windows PowerShell モジュールの記述を参照してください。

## <a name="the-powershell-class"></a>PowerShell クラス

PowerShell クラスは、プログラムでのコマンドを実行するホスト アプリケーションと呼ばれるアプリケーションを作成するための簡単なソリューションを提供します。 このクラスを使用すると、コマンドのパイプラインを作成のコマンドを実行するために使用する実行空間を指定し、同期または非同期コマンドを呼び出すことを指定できます。

## <a name="the-runspacepool-class"></a>RunspacePool クラス

実行空間プールを使用すると、1 回の呼び出しを使用して複数の実行空間を作成できます。 CreateRunspacePool メソッドは、同じホスト、最初のセッション状態、および接続情報など、同じ機能の実行空間を作成するために使用するいくつかのオーバー ロードを提供します。

## <a name="the-initialsessionstate-class"></a>InitialSessionState クラス

InitialSessionState クラスを使用する実行空間が開いたときに使用されるセッション状態の構成を作成することができます。 カスタム構成、mshshort、によって提供されるコマンドを含む既定の構成、およびそのコマンドは、セッションの機能に基づく制限の構成を作成できます。

## <a name="remote-runspaces"></a>リモート実行空間

今すぐ作成できます空間を開くことができますのリモート コンピューター上、リモート コンピューター上のコマンドを実行し、ローカルで結果を収集することができます。 リモートの実行空間を作成するには、実行空間を作成するときにリモート接続に関する情報を指定する必要があります。 例については、CreateRunspace および CreateRunspacePool のメソッドを参照してください。 接続情報は、RunspaceConnectionInfo クラスによって定義されます。

## <a name="private-runspace-elements"></a>実行空間のプライベート要素

要素がパブリックまたはプライベートの実行空間を作成できます。 これにより、要素が、実行空間を利用できますが、ユーザーが使用可能でない実行空間を作成することができます。 実行空間の要素をプライベートにできることを確認する ConstrainedSessionStateEntry クラスを参照してください。

## <a name="runspace-threading-modes-and-apartment-state"></a>スレッド処理モードとアパートメント状態実行空間

スレッドが作成され、実行空間でコマンドを実行するときに使用する方法を指定できます。 System.Management.Automation.Runspaces.Runspace.ThreadOptions と System.Management.Automation.Runspaces.RunspacePool.ThreadOptions プロパティを参照してください。

使用して、実行空間でコマンドを実行するスレッドのアパートメント状態を取得できます。 System.Management.Automation.Runspaces.Runspace.ApartmentState と System.Management.Automation.Runspaces.RunspacePool.ApartmentState プロパティを参照してください。

## <a name="transaction-cmdlets"></a>トランザクションのコマンドレット

トランザクション内で使用できるコマンドレットを作成できます。 トランザクションでコマンドレットを使用するときにそのアクションは一時的なものと承諾または Windows PowerShell によって提供されるトランザクション コマンドレットによって拒否されたことができます。

トランザクションの詳細については、次を参照してください。 トランザクションをサポートする方法。

## <a name="transaction-provider"></a>トランザクションのプロバイダー

トランザクション内で使用できるプロバイダーを作成できます。 そのアクションは一時的なものは、コマンドレット、プロバイダーがトランザクションで使用される場合と同様に、および承諾または Windows PowerShell によって提供されるトランザクション コマンドレットによって拒否されたことができます。

プロバイダー クラス内のトランザクションのサポートを指定する方法については、System.Management.Automation.Provider.CmdletProviderAttribute.ProviderCapabilities プロパティを参照してください。

## <a name="job-cmdlets"></a>ジョブのコマンドレット

ジョブとしてその操作を実行できるコマンドレットを記述できますようになりました。 これらのジョブは、現在のセッションと対話することがなく、バック グラウンドで実行されます。 Windows PowerShell でジョブをサポートする方法の詳細については、バック グラウンド ジョブを参照してください。

## <a name="cmdlet-output-types"></a>コマンドレットの出力の種類

これで、コマンドレットを記述するときに、OutputType 属性を宣言することで、コマンドレットによって返される .NET Framework の型を指定できます。 これは、調べるコマンドレットの OutputType プロパティ コマンドレットによって返されるオブジェクトの種類を決定する他のユーザーに許可されます。

## <a name="event-support"></a>イベントのサポート

追加およびイベントを使用するコマンドレットを記述できますようになりました。 PSEvent クラスを参照してください。

## <a name="proxy-commands"></a>プロキシ コマンド

別のコマンドを実行するために使用するプロキシ コマンドを記述できますようになりました。 プロキシ コマンドを使用すると、ユーザーに可能なソース コマンドレットの機能を制御できます。 たとえば、ソースのコマンドで指定されているパラメーターを削除するプロキシ コマンドを作成できます。 ProxyCommand クラスを参照してください。

## <a name="multiple-choice-prompts"></a>複数選択画面の指示

ユーザーが複数の選択肢を選択する画面の指示を提供するアプリケーションを記述できますようになりました。 IHostUISupportsMultipleChoiceSelection インターフェイスを参照してください。

## <a name="interactive-sessions"></a>対話型セッション

開始して、リモート コンピューター上の対話型セッションを停止できるアプリケーションを記述できますようになりました。
IHostSupportsInteractiveSession インターフェイスを参照してください。

## <a name="custom-cmdlet-help-for-providers"></a>プロバイダーのカスタム コマンドレット ヘルプ

プロバイダー コマンドレットのカスタマイズされたヘルプ トピックを作成できます。 カスタム コマンドレット ヘルプ トピックのコマンドレット、プロバイダー パスとドキュメントの特殊な機能に、コマンドレット、プロバイダーを追加する動的パラメーターを含むの動作方法を説明します。
