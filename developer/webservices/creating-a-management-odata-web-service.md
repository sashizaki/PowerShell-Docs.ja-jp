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
# <a name="creating-a-management-odata-web-service"></a><span data-ttu-id="3c4a1-102">Management OData Web サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="3c4a1-102">Creating a Management OData Web Service</span></span>

<span data-ttu-id="3c4a1-103">Management ODATA IIS 拡張機能は、Windows PowerShell コマンドレットと OData Web サービスのエンティティとしてのスクリプトを使用してアクセスを管理データを公開する ASP.NET web サービス終了ポイントを作成するためのインフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="3c4a1-103">Management ODATA IIS Extension is an infrastructure for creating an ASP.NET web service end point that exposes your management data, accessed through Windows PowerShell cmdlets and scripts, as OData Web service entities.</span></span> <span data-ttu-id="3c4a1-104">OData 要求を処理して、Windows PowerShell の呼び出しに変換することはできます。</span><span class="sxs-lookup"><span data-stu-id="3c4a1-104">It does that by processing OData requests and converting them into a Windows PowerShell invocation.</span></span> <span data-ttu-id="3c4a1-105">製品チームは、特定の管理データのセットを公開するエンドポイントを作成するには、このインフラストラクチャの上に構築できます。</span><span class="sxs-lookup"><span data-stu-id="3c4a1-105">Product teams can build on top of this infrastructure to create endpoints that expose specific sets of management data.</span></span>

<span data-ttu-id="3c4a1-106">ダウンロードしてインストール、 [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a)サンプル。</span><span class="sxs-lookup"><span data-stu-id="3c4a1-106">Download and install the [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) sample.</span></span> <span data-ttu-id="3c4a1-107">Web サービスをデプロイする手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3c4a1-107">Follow the instructions to deploy the web service.</span></span> <span data-ttu-id="3c4a1-108">この web サービスは、作成、読み取り、更新、および削除 (CRUD) 操作を介してサービスとプロセスを公開します。</span><span class="sxs-lookup"><span data-stu-id="3c4a1-108">This web service exposes Services and Processes through Create, Read, Update, and Delete (CRUD) operations.</span></span> <span data-ttu-id="3c4a1-109">Web サービスへの CRUD 要求は、要求された操作を実行する Windows PowerShell コマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3c4a1-109">CRUD requests made to the web service invoke  Windows PowerShell commands that perform the requested operations.</span></span> <span data-ttu-id="3c4a1-110">CRUD 操作と基になる Windows PowerShell コマンドの間のマッピングは、2 つのスキーマ ファイル、schema.mof および schema.xml によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="3c4a1-110">A mapping between the CRUD operations and the underlying Windows PowerShell commands is implemented by two schema files, schema.mof and schema.xml.</span></span> <span data-ttu-id="3c4a1-111">.Schema.mof ファイルを使用して、 [Distributed Management Task Force](https://www.dmtf.org/) (DMTF) 管理オブジェクト (MOF) 標準です。</span><span class="sxs-lookup"><span data-stu-id="3c4a1-111">The schema.mof file uses the [Distributed Management  Task Force](https://www.dmtf.org/) (DMTF) Managed Object (MOF) standard.</span></span> <span data-ttu-id="3c4a1-112">Schema.xml ファイルで説明されている XML スキーマを使用する[リソース マッピング スキーマ](./resource-mapping-schema.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c4a1-112">The schema.xml file uses an XML schema that is described in [Resource Mapping Schema](./resource-mapping-schema.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c4a1-113">Windows Server 2008 R2 sp1 Management ODATA IIS 拡張機能を有効にする前に、次の機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c4a1-113">Before you enabling Management ODATA IIS Extension on Windows Server 2008 R2 SP1, the following features must be enabled.</span></span>
>
> 1.  <span data-ttu-id="3c4a1-114">IIS-WebServerRole</span><span class="sxs-lookup"><span data-stu-id="3c4a1-114">IIS-WebServerRole</span></span>
> 2.  <span data-ttu-id="3c4a1-115">IIS-WebServer</span><span class="sxs-lookup"><span data-stu-id="3c4a1-115">IIS-WebServer</span></span>
> 3.  <span data-ttu-id="3c4a1-116">IIS-HttpTracing</span><span class="sxs-lookup"><span data-stu-id="3c4a1-116">IIS-HttpTracing</span></span>
> 4.  <span data-ttu-id="3c4a1-117">IIS ManagementOData</span><span class="sxs-lookup"><span data-stu-id="3c4a1-117">IIS-ManagementOData</span></span>

## <a name="steps-for-creating-a-management-odata-web-service"></a><span data-ttu-id="3c4a1-118">Management OData web サービスを作成するための手順</span><span class="sxs-lookup"><span data-stu-id="3c4a1-118">Steps for creating a Management OData web service</span></span>

<span data-ttu-id="3c4a1-119">次のトピックでは、作成し、Management OData web サービスをデプロイする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c4a1-119">The following topics describe how to create and deploy a Management OData web service.</span></span>

- [<span data-ttu-id="3c4a1-120">リソース管理の OData Web サービスへの追加</span><span class="sxs-lookup"><span data-stu-id="3c4a1-120">Adding Resources to a Management OData Web Service</span></span>](./adding-resources-to-a-management-odata-web-service.md)

- [<span data-ttu-id="3c4a1-121">Management OData web サービスのカスタム承認を実装します。</span><span class="sxs-lookup"><span data-stu-id="3c4a1-121">Implementing Custom Authorization for a Management OData web service</span></span>](./implementing-custom-authorization-for-a-management-odata-web-service.md)

- [<span data-ttu-id="3c4a1-122">Management OData web サービスのセッション構成を実装します。</span><span class="sxs-lookup"><span data-stu-id="3c4a1-122">Implementing SessionConfiguration for a Management OData web service</span></span>](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

- [<span data-ttu-id="3c4a1-123">Management OData web サービスの MOF スキーマ ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="3c4a1-123">Authoring the MOF schema file for a Management OData web service</span></span>](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="3c4a1-124">Management OData web サービスの XML スキーマ ファイルを作成</span><span class="sxs-lookup"><span data-stu-id="3c4a1-124">Authoring the XML schema file for a Management OData web service</span></span>](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="3c4a1-125">Management OData web サービスの Web.config ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="3c4a1-125">Authoring the Web.config file for a Management OData web service</span></span>](./authoring-the-web-config-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="3c4a1-126">Management OData web サービスのデプロイ</span><span class="sxs-lookup"><span data-stu-id="3c4a1-126">Deploying a Management OData web service</span></span>](./deploying-a-management-odata-web-service.md)

- [<span data-ttu-id="3c4a1-127">Management OData エンティティの関連付け</span><span class="sxs-lookup"><span data-stu-id="3c4a1-127">Associating Management OData Entities</span></span>](./associating-management-odata-entities.md)

## <a name="see-also"></a><span data-ttu-id="3c4a1-128">参照</span><span class="sxs-lookup"><span data-stu-id="3c4a1-128">See Also</span></span>

[<span data-ttu-id="3c4a1-129">Management ODATA IIS 拡張機能のスキーマ ファイル</span><span class="sxs-lookup"><span data-stu-id="3c4a1-129">Management ODATA IIS Extension Schema Files</span></span>](./management-odata-iis-extension-schema-files.md)
