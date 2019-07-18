---
title: 一般的なワークフロー パラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5891467-8e13-484d-b7af-32e6bffab35d
caps.latest.revision: 4
ms.openlocfilehash: b2e8f272a82ee03de306fd8eac45e109142f6284
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080409"
---
# <a name="common-workflow-parameters"></a>共通ワークフロー パラメーター

Windows PowerShell コマンドレットから生成されたワークフロー アクティビティは、すべてのアクティビティにその一般的なパラメーター数を定義します。 ワークフローの作成者はアクティビティをカスタマイズできるように、作成時は、これらのパラメーターのサブセットを指定できます。 アクティビティを呼び出すときに、ユーザーがこれらのパラメーターの別のサブセットを指定できます。

一般的なワークフロー パラメーターは、次のように、いくつかのカテゴリに分類されます。

## <a name="connectivity-parameters"></a>接続パラメーター

|名前|型|説明|実行時にエンドユーザーを指定できますか。|作成時のワークフローの作成者によって指定できますか。|インスタンス作成時にワークフローの作成者によって指定できますか。|
|----------|----------|-----------------|-----------------------------------------------------|------------------------------------------------------------|-----------------------------------------------------------|
|PSComputerName|String[]|ジョブを起動する対象のコンピューター名の一覧。|可|[はい]|可|
|PSCredential|[System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)|使用する認証資格情報、PSComputerName パラメーターで指定されているコンピューターにログインします。 このパラメーターは PSComputerName が指定されている場合にのみ有効です。|可|[はい]|可|
|PSPort|UInt32|ワークフローの実行に使用するポート。|可|[はい]|可|
|PSUseSSL|ブール型|ワークフローを実行するのにリモート コンピューターにセキュリティで保護された接続を確立するのにには、Secure Sockets Layer (SSL) プロトコルを使用します。|可|[はい]|可|
|PSConfigurationName|String|セッション構成は、ワークフローを実行するために使用します。|可|[はい]|可|
|PSApplicationName|String|ワークフローの実行の接続 URI のアプリケーションの名前の部分。 ConnectionURI パラメーターを使用していない場合にのみ、このパラメーターを使用します。|可|[はい]|可|
|PSThrottleLimit|UInt32|ワークフローを実行するために確立できる同時接続の最大数。|可|TBD|可|
|PSConnectionURI|String[]|ワークフローを実行するために使用する対話型セッション向けにエンドポイントを指定する絶対 Uri の配列。|可|[はい]|可|
|PSAllowRedirection|ブール型|ワークフローを実行する代替 URI への接続でのリダイレクトを許可するかどうかを指定します。|可|[はい]|可|
|PSSessionOption|[System.Management.Automation.Remoting.Pssessionoption](/dotnet/api/System.Management.Automation.Remoting.PSSessionOption)|ワークフローを実行するために使用するセッションの高度なオプションです。|可|[はい]|可|
|PSAuthentication|[System.Management.Automation.Runspaces.Authenticationmechanism](/dotnet/api/System.Management.Automation.Runspaces.AuthenticationMechanism)|値、 [System.Management.Automation.Runspaces.Authenticationmechanism](/dotnet/api/System.Management.Automation.Runspaces.AuthenticationMechanism)ユーザーの資格情報の認証に使用する認証メカニズムを指定する列挙体。|可|[はい]|可|
|PSCertificateThumbprint|String|デジタル公開キー証明書 (X509) のワークフローを実行するアクセス許可を持つユーザー アカウント。|可|[はい]|可|

### <a name="behavior-parameters"></a>パラメーターの動作