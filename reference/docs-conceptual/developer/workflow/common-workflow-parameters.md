---
title: 共通のワークフローパラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5891467-8e13-484d-b7af-32e6bffab35d
caps.latest.revision: 4
ms.openlocfilehash: b2e8f272a82ee03de306fd8eac45e109142f6284
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366051"
---
# <a name="common-workflow-parameters"></a>共通ワークフロー パラメーター

Windows PowerShell コマンドレットから生成されたワークフローアクティビティは、すべてのアクティビティに共通する多数のパラメーターを定義します。 これらのパラメーターのサブセットを作成時に指定して、ワークフローの作成者がアクティビティをカスタマイズできるようにすることができます。 これらのパラメーターのもう1つのサブセットは、アクティビティを呼び出すときにユーザーが指定できます。

共通のワークフローパラメーターは、次のようにいくつかのカテゴリに分類されます。

## <a name="connectivity-parameters"></a>接続パラメーター

|名前|種類|[説明]|実行時にエンドユーザーが指定できますか?|作成時にワークフロー作成者が指定できますか?|は、インスタンス化時にワークフロー作成者によって指定できますか。|
|----------|----------|-----------------|-----------------------------------------------------|------------------------------------------------------------|-----------------------------------------------------------|
|PSComputerName|String[]|ジョブを起動するコンピューター名の一覧。|可|可|可|
|PSCredential|[システム.... PSCredential](/dotnet/api/System.Management.Automation.PSCredential)|PSComputerName パラメーターによって指定されたコンピューターへのログインに使用する認証資格情報。 このパラメーターは、PSComputerName が指定されている場合にのみ有効です。|可|可|可|
|PSPort|UInt32|ワークフローを実行するために使用されるポート。|可|可|可|
|PSUseSSL|ブール型|Secure Sockets Layer (SSL) プロトコルを使用して、リモートコンピューターへのセキュリティで保護された接続を確立し、ワークフローを実行します。|可|可|可|
|PSConfigurationName|String|ワークフローを実行するために使用されるセッション構成。|可|可|可|
|PSApplicationName|String|ワークフロー実行のための接続 URI のアプリケーション名部分。 このパラメーターは、ConnectionURI パラメーターを使用していない場合にのみ使用してください。|可|可|可|
|PSThrottleLimit|UInt32|ワークフローを実行するために確立できる同時接続の最大数。|可|TBD|可|
|PSConnectionURI|String[]|ワークフローを実行するために使用される対話型セッションのエンドポイントを指定する完全修飾 Uri の配列。|可|可|可|
|PSAllowRedirection|ブール型|この接続を代替 URI にリダイレクトしてワークフローを実行できるようにするかどうかを指定します。|可|可|可|
|PSSessionOption|[システムの管理.... Pssessionoption](/dotnet/api/System.Management.Automation.Remoting.PSSessionOption)|ワークフローを実行するために使用されるセッションの詳細設定オプション。|可|可|可|
|PSAuthentication|[システムの管理.... Authenticationmechanism](/dotnet/api/System.Management.Automation.Runspaces.AuthenticationMechanism)|ユーザーの資格情報を認証するために使用される認証メカニズムを指定する、システムの.... [Authenticationmechanism](/dotnet/api/System.Management.Automation.Runspaces.AuthenticationMechanism)の列挙値。|可|可|可|
|PSCertificateThumbprint|String|ワークフローを実行するアクセス許可を持つユーザーアカウントのデジタル公開キー証明書 (X509)。|可|可|可|

### <a name="behavior-parameters"></a>動作パラメーター