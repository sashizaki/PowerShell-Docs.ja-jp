---
title: Management OData Web サービスを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06b1b050-0bf7-48f5-ba05-43f489d597c0
caps.latest.revision: 10
ms.openlocfilehash: 476fce9fc087b870bad93a9204a820c5a84df99e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080698"
---
# <a name="creating-a-management-odata-web-service"></a>Management OData Web サービスを作成する

Management ODATA IIS 拡張機能は、Windows PowerShell コマンドレットと OData Web サービスのエンティティとしてのスクリプトを使用してアクセスを管理データを公開する ASP.NET web サービス終了ポイントを作成するためのインフラストラクチャです。 OData 要求を処理して、Windows PowerShell の呼び出しに変換することはできます。 製品チームは、特定の管理データのセットを公開するエンドポイントを作成するには、このインフラストラクチャの上に構築できます。

ダウンロードしてインストール、 [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a)サンプル。 Web サービスをデプロイする手順に従います。 この web サービスは、作成、読み取り、更新、および削除 (CRUD) 操作を介してサービスとプロセスを公開します。 Web サービスへの CRUD 要求は、要求された操作を実行する Windows PowerShell コマンドを呼び出します。 CRUD 操作と基になる Windows PowerShell コマンドの間のマッピングは、2 つのスキーマ ファイル、schema.mof および schema.xml によって実装されます。 .Schema.mof ファイルを使用して、 [Distributed Management Task Force](https://www.dmtf.org/) (DMTF) 管理オブジェクト (MOF) 標準です。 Schema.xml ファイルで説明されている XML スキーマを使用する[リソース マッピング スキーマ](./resource-mapping-schema.md)します。

> [!IMPORTANT]
> Windows Server 2008 R2 sp1 Management ODATA IIS 拡張機能を有効にする前に、次の機能を有効にする必要があります。
>
> 1.  IIS-WebServerRole
> 2.  IIS-WebServer
> 3.  IIS-HttpTracing
> 4.  IIS ManagementOData

## <a name="steps-for-creating-a-management-odata-web-service"></a>Management OData web サービスを作成するための手順

次のトピックでは、作成し、Management OData web サービスをデプロイする方法について説明します。

- [リソース管理の OData Web サービスへの追加](./adding-resources-to-a-management-odata-web-service.md)

- [Management OData web サービスのカスタム承認を実装します。](./implementing-custom-authorization-for-a-management-odata-web-service.md)

- [Management OData web サービスのセッション構成を実装します。](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

- [Management OData web サービスの MOF スキーマ ファイルの作成](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

- [Management OData web サービスの XML スキーマ ファイルを作成](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

- [Management OData web サービスの Web.config ファイルの作成](./authoring-the-web-config-file-for-a-management-odata-web-service.md)

- [Management OData web サービスのデプロイ](./deploying-a-management-odata-web-service.md)

- [Management OData エンティティの関連付け](./associating-management-odata-entities.md)

## <a name="see-also"></a>参照

[Management ODATA IIS 拡張機能のスキーマ ファイル](./management-odata-iis-extension-schema-files.md)
