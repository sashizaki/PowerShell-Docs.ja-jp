---
title: 管理 OData Web サービスを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06b1b050-0bf7-48f5-ba05-43f489d597c0
caps.latest.revision: 10
ms.openlocfilehash: f903c99300a34c0dfbed598738e96142588d69d9
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83691488"
---
# <a name="creating-a-management-odata-web-service"></a>Management OData Web サービスを作成する

Management ODATA IIS 拡張機能は、Windows PowerShell コマンドレットとスクリプトを通じてアクセスされる管理データを OData Web サービスエンティティとして公開する ASP.NET web サービスエンドポイントを作成するためのインフラストラクチャです。 これは、OData 要求を処理し、それを Windows PowerShell の呼び出しに変換することによって行われます。 製品チームは、このインフラストラクチャの上に構築して、特定の管理データのセットを公開するエンドポイントを作成できます。

[Pswsroleñプラグイン](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a)サンプルをダウンロードしてインストールします。 指示に従って web サービスをデプロイします。 この web サービスは、作成、読み取り、更新、および削除 (CRUD) 操作を通じてサービスとプロセスを公開します。 Web サービスに対して行われた CRUD 要求は、要求された操作を実行する Windows PowerShell コマンドを呼び出します。 CRUD 操作と基になる Windows PowerShell コマンドの間のマッピングは、スキーマの .mof と .xml の2つのスキーマファイルによって実装されます。 スキーマ .mof ファイルは、[分散管理タスクフォース](https://www.dmtf.org/)(DMTF) の管理オブジェクト (mof) 標準を使用します。 スキーマ .xml ファイルは、「[リソースマッピングスキーマ](./resource-mapping-schema.md)」で説明されている xml スキーマを使用します。

> [!IMPORTANT]
> Windows Server 2008 R2 SP1 で管理 ODATA IIS 拡張機能を有効にする前に、次の機能を有効にする必要があります。
>
> 1. IIS-WebServerRole
> 2. IIS-WebServer
> 3. IIS-HttpTracing
> 4. IIS-ManagementOData

## <a name="steps-for-creating-a-management-odata-web-service"></a>管理用の OData web サービスを作成する手順

次のトピックでは、管理 OData web サービスを作成および展開する方法について説明します。

- [Management OData Web サービスにリソースを追加する](./adding-resources-to-a-management-odata-web-service.md)

- [Management OData Web サービスのカスタム認可を実装する](./implementing-custom-authorization-for-a-management-odata-web-service.md)

- [Management OData Web サービスの SessionConfiguration を実装する](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

- [Management OData Web サービスの MOF スキーマ ファイルを作成する](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

- [Management OData Web サービスの XML スキーマ ファイルを作成する](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

- [Management OData Web サービスの Web.config ファイルを作成する](./authoring-the-web-config-file-for-a-management-odata-web-service.md)

- [Management OData Web サービスを展開する](./deploying-a-management-odata-web-service.md)

- [Management OData エンティティを関連付ける](./associating-management-odata-entities.md)

## <a name="see-also"></a>参照

[Management ODATA IIS 拡張スキーマファイル](./management-odata-iis-extension-schema-files.md)
