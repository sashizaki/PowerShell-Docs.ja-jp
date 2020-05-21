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
# <a name="creating-a-management-odata-web-service"></a><span data-ttu-id="0bda6-102">Management OData Web サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="0bda6-102">Creating a Management OData Web Service</span></span>

<span data-ttu-id="0bda6-103">Management ODATA IIS 拡張機能は、Windows PowerShell コマンドレットとスクリプトを通じてアクセスされる管理データを OData Web サービスエンティティとして公開する ASP.NET web サービスエンドポイントを作成するためのインフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="0bda6-103">Management ODATA IIS Extension is an infrastructure for creating an ASP.NET web service end point that exposes your management data, accessed through Windows PowerShell cmdlets and scripts, as OData Web service entities.</span></span> <span data-ttu-id="0bda6-104">これは、OData 要求を処理し、それを Windows PowerShell の呼び出しに変換することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="0bda6-104">It does that by processing OData requests and converting them into a Windows PowerShell invocation.</span></span> <span data-ttu-id="0bda6-105">製品チームは、このインフラストラクチャの上に構築して、特定の管理データのセットを公開するエンドポイントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0bda6-105">Product teams can build on top of this infrastructure to create endpoints that expose specific sets of management data.</span></span>

<span data-ttu-id="0bda6-106">[Pswsroleñプラグイン](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a)サンプルをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="0bda6-106">Download and install the [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) sample.</span></span> <span data-ttu-id="0bda6-107">指示に従って web サービスをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="0bda6-107">Follow the instructions to deploy the web service.</span></span> <span data-ttu-id="0bda6-108">この web サービスは、作成、読み取り、更新、および削除 (CRUD) 操作を通じてサービスとプロセスを公開します。</span><span class="sxs-lookup"><span data-stu-id="0bda6-108">This web service exposes Services and Processes through Create, Read, Update, and Delete (CRUD) operations.</span></span> <span data-ttu-id="0bda6-109">Web サービスに対して行われた CRUD 要求は、要求された操作を実行する Windows PowerShell コマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0bda6-109">CRUD requests made to the web service invoke  Windows PowerShell commands that perform the requested operations.</span></span> <span data-ttu-id="0bda6-110">CRUD 操作と基になる Windows PowerShell コマンドの間のマッピングは、スキーマの .mof と .xml の2つのスキーマファイルによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="0bda6-110">A mapping between the CRUD operations and the underlying Windows PowerShell commands is implemented by two schema files, schema.mof and schema.xml.</span></span> <span data-ttu-id="0bda6-111">スキーマ .mof ファイルは、[分散管理タスクフォース](https://www.dmtf.org/)(DMTF) の管理オブジェクト (mof) 標準を使用します。</span><span class="sxs-lookup"><span data-stu-id="0bda6-111">The schema.mof file uses the [Distributed Management  Task Force](https://www.dmtf.org/) (DMTF) Managed Object (MOF) standard.</span></span> <span data-ttu-id="0bda6-112">スキーマ .xml ファイルは、「[リソースマッピングスキーマ](./resource-mapping-schema.md)」で説明されている xml スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="0bda6-112">The schema.xml file uses an XML schema that is described in [Resource Mapping Schema](./resource-mapping-schema.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bda6-113">Windows Server 2008 R2 SP1 で管理 ODATA IIS 拡張機能を有効にする前に、次の機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bda6-113">Before you enabling Management ODATA IIS Extension on Windows Server 2008 R2 SP1, the following features must be enabled.</span></span>
>
> 1. <span data-ttu-id="0bda6-114">IIS-WebServerRole</span><span class="sxs-lookup"><span data-stu-id="0bda6-114">IIS-WebServerRole</span></span>
> 2. <span data-ttu-id="0bda6-115">IIS-WebServer</span><span class="sxs-lookup"><span data-stu-id="0bda6-115">IIS-WebServer</span></span>
> 3. <span data-ttu-id="0bda6-116">IIS-HttpTracing</span><span class="sxs-lookup"><span data-stu-id="0bda6-116">IIS-HttpTracing</span></span>
> 4. <span data-ttu-id="0bda6-117">IIS-ManagementOData</span><span class="sxs-lookup"><span data-stu-id="0bda6-117">IIS-ManagementOData</span></span>

## <a name="steps-for-creating-a-management-odata-web-service"></a><span data-ttu-id="0bda6-118">管理用の OData web サービスを作成する手順</span><span class="sxs-lookup"><span data-stu-id="0bda6-118">Steps for creating a Management OData web service</span></span>

<span data-ttu-id="0bda6-119">次のトピックでは、管理 OData web サービスを作成および展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0bda6-119">The following topics describe how to create and deploy a Management OData web service.</span></span>

- [<span data-ttu-id="0bda6-120">Management OData Web サービスにリソースを追加する</span><span class="sxs-lookup"><span data-stu-id="0bda6-120">Adding Resources to a Management OData Web Service</span></span>](./adding-resources-to-a-management-odata-web-service.md)

- [<span data-ttu-id="0bda6-121">Management OData Web サービスのカスタム認可を実装する</span><span class="sxs-lookup"><span data-stu-id="0bda6-121">Implementing Custom Authorization for a Management OData web service</span></span>](./implementing-custom-authorization-for-a-management-odata-web-service.md)

- [<span data-ttu-id="0bda6-122">Management OData Web サービスの SessionConfiguration を実装する</span><span class="sxs-lookup"><span data-stu-id="0bda6-122">Implementing SessionConfiguration for a Management OData web service</span></span>](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

- [<span data-ttu-id="0bda6-123">Management OData Web サービスの MOF スキーマ ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="0bda6-123">Authoring the MOF schema file for a Management OData web service</span></span>](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="0bda6-124">Management OData Web サービスの XML スキーマ ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="0bda6-124">Authoring the XML schema file for a Management OData web service</span></span>](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="0bda6-125">Management OData Web サービスの Web.config ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="0bda6-125">Authoring the Web.config file for a Management OData web service</span></span>](./authoring-the-web-config-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="0bda6-126">Management OData Web サービスを展開する</span><span class="sxs-lookup"><span data-stu-id="0bda6-126">Deploying a Management OData web service</span></span>](./deploying-a-management-odata-web-service.md)

- [<span data-ttu-id="0bda6-127">Management OData エンティティを関連付ける</span><span class="sxs-lookup"><span data-stu-id="0bda6-127">Associating Management OData Entities</span></span>](./associating-management-odata-entities.md)

## <a name="see-also"></a><span data-ttu-id="0bda6-128">参照</span><span class="sxs-lookup"><span data-stu-id="0bda6-128">See Also</span></span>

[<span data-ttu-id="0bda6-129">Management ODATA IIS 拡張スキーマファイル</span><span class="sxs-lookup"><span data-stu-id="0bda6-129">Management ODATA IIS Extension Schema Files</span></span>](./management-odata-iis-extension-schema-files.md)
