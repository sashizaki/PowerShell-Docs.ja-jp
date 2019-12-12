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
ms.openlocfilehash: 476fce9fc087b870bad93a9204a820c5a84df99e
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359721"
---
# <a name="creating-a-management-odata-web-service"></a><span data-ttu-id="1a6ca-102">Management OData Web サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="1a6ca-102">Creating a Management OData Web Service</span></span>

<span data-ttu-id="1a6ca-103">Management ODATA IIS 拡張機能は、Windows PowerShell コマンドレットとスクリプトを通じてアクセスされる管理データを OData Web サービスエンティティとして公開する ASP.NET web サービスエンドポイントを作成するためのインフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="1a6ca-103">Management ODATA IIS Extension is an infrastructure for creating an ASP.NET web service end point that exposes your management data, accessed through Windows PowerShell cmdlets and scripts, as OData Web service entities.</span></span> <span data-ttu-id="1a6ca-104">これは、OData 要求を処理し、それを Windows PowerShell の呼び出しに変換することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="1a6ca-104">It does that by processing OData requests and converting them into a Windows PowerShell invocation.</span></span> <span data-ttu-id="1a6ca-105">製品チームは、このインフラストラクチャの上に構築して、特定の管理データのセットを公開するエンドポイントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1a6ca-105">Product teams can build on top of this infrastructure to create endpoints that expose specific sets of management data.</span></span>

<span data-ttu-id="1a6ca-106">[Pswsroleñプラグイン](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a)サンプルをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="1a6ca-106">Download and install the [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) sample.</span></span> <span data-ttu-id="1a6ca-107">指示に従って web サービスをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="1a6ca-107">Follow the instructions to deploy the web service.</span></span> <span data-ttu-id="1a6ca-108">この web サービスは、作成、読み取り、更新、および削除 (CRUD) 操作を通じてサービスとプロセスを公開します。</span><span class="sxs-lookup"><span data-stu-id="1a6ca-108">This web service exposes Services and Processes through Create, Read, Update, and Delete (CRUD) operations.</span></span> <span data-ttu-id="1a6ca-109">Web サービスに対して行われた CRUD 要求は、要求された操作を実行する Windows PowerShell コマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1a6ca-109">CRUD requests made to the web service invoke  Windows PowerShell commands that perform the requested operations.</span></span> <span data-ttu-id="1a6ca-110">CRUD 操作と基になる Windows PowerShell コマンドの間のマッピングは、スキーマの .mof と .xml の2つのスキーマファイルによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="1a6ca-110">A mapping between the CRUD operations and the underlying Windows PowerShell commands is implemented by two schema files, schema.mof and schema.xml.</span></span> <span data-ttu-id="1a6ca-111">スキーマ .mof ファイルは、[分散管理タスクフォース](https://www.dmtf.org/)(DMTF) の管理オブジェクト (mof) 標準を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a6ca-111">The schema.mof file uses the [Distributed Management  Task Force](https://www.dmtf.org/) (DMTF) Managed Object (MOF) standard.</span></span> <span data-ttu-id="1a6ca-112">スキーマ .xml ファイルは、「[リソースマッピングスキーマ](./resource-mapping-schema.md)」で説明されている xml スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="1a6ca-112">The schema.xml file uses an XML schema that is described in [Resource Mapping Schema](./resource-mapping-schema.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a6ca-113">Windows Server 2008 R2 SP1 で管理 ODATA IIS 拡張機能を有効にする前に、次の機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6ca-113">Before you enabling Management ODATA IIS Extension on Windows Server 2008 R2 SP1, the following features must be enabled.</span></span>
>
> 1.  <span data-ttu-id="1a6ca-114">IIS-WebServerRole</span><span class="sxs-lookup"><span data-stu-id="1a6ca-114">IIS-WebServerRole</span></span>
> 2.  <span data-ttu-id="1a6ca-115">IIS-WebServer</span><span class="sxs-lookup"><span data-stu-id="1a6ca-115">IIS-WebServer</span></span>
> 3.  <span data-ttu-id="1a6ca-116">IIS-HttpTracing</span><span class="sxs-lookup"><span data-stu-id="1a6ca-116">IIS-HttpTracing</span></span>
> 4.  <span data-ttu-id="1a6ca-117">IIS-ManagementOData</span><span class="sxs-lookup"><span data-stu-id="1a6ca-117">IIS-ManagementOData</span></span>

## <a name="steps-for-creating-a-management-odata-web-service"></a><span data-ttu-id="1a6ca-118">管理用の OData web サービスを作成する手順</span><span class="sxs-lookup"><span data-stu-id="1a6ca-118">Steps for creating a Management OData web service</span></span>

<span data-ttu-id="1a6ca-119">次のトピックでは、管理 OData web サービスを作成および展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a6ca-119">The following topics describe how to create and deploy a Management OData web service.</span></span>

- [<span data-ttu-id="1a6ca-120">管理 OData Web サービスへのリソースの追加</span><span class="sxs-lookup"><span data-stu-id="1a6ca-120">Adding Resources to a Management OData Web Service</span></span>](./adding-resources-to-a-management-odata-web-service.md)

- [<span data-ttu-id="1a6ca-121">管理 OData web サービスのカスタム承認の実装</span><span class="sxs-lookup"><span data-stu-id="1a6ca-121">Implementing Custom Authorization for a Management OData web service</span></span>](./implementing-custom-authorization-for-a-management-odata-web-service.md)

- [<span data-ttu-id="1a6ca-122">管理 OData web サービスに SessionConfiguration を実装する</span><span class="sxs-lookup"><span data-stu-id="1a6ca-122">Implementing SessionConfiguration for a Management OData web service</span></span>](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

- [<span data-ttu-id="1a6ca-123">管理用の OData web サービスの MOF スキーマファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="1a6ca-123">Authoring the MOF schema file for a Management OData web service</span></span>](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="1a6ca-124">管理用の OData web サービス用の XML スキーマファイルの作成</span><span class="sxs-lookup"><span data-stu-id="1a6ca-124">Authoring the XML schema file for a Management OData web service</span></span>](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="1a6ca-125">管理 OData web サービスの Web.config ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="1a6ca-125">Authoring the Web.config file for a Management OData web service</span></span>](./authoring-the-web-config-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="1a6ca-126">Management OData web サービスのデプロイ</span><span class="sxs-lookup"><span data-stu-id="1a6ca-126">Deploying a Management OData web service</span></span>](./deploying-a-management-odata-web-service.md)

- [<span data-ttu-id="1a6ca-127">管理 OData エンティティの関連付け</span><span class="sxs-lookup"><span data-stu-id="1a6ca-127">Associating Management OData Entities</span></span>](./associating-management-odata-entities.md)

## <a name="see-also"></a><span data-ttu-id="1a6ca-128">参照</span><span class="sxs-lookup"><span data-stu-id="1a6ca-128">See Also</span></span>

[<span data-ttu-id="1a6ca-129">Management ODATA IIS 拡張スキーマファイル</span><span class="sxs-lookup"><span data-stu-id="1a6ca-129">Management ODATA IIS Extension Schema Files</span></span>](./management-odata-iis-extension-schema-files.md)
