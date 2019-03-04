---
title: Management OData web サービスの XML スキーマ ファイルの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e83c9d9-6d06-4247-94d9-e3bfd4013b11
caps.latest.revision: 4
ms.openlocfilehash: a806d012097d107b6cc35710b9a93f2b27dd1ace
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857978"
---
# <a name="authoring-the-xml-schema-file-for-a-management-odata-web-service"></a><span data-ttu-id="cad84-102">Management OData Web サービスの XML スキーマ ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="cad84-102">Authoring the XML schema file for a Management OData web service</span></span>

<span data-ttu-id="cad84-103">リソースを定義した後、web サービスを公開 (を参照してください[Management OData web サービスの MOF スキーマ ファイルを作成](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md))、サポートされている実装を基になる Windows PowerShell コマンドレットにそれらのリソースをマップします。各リソースに準拠した XML ファイルを作成するための操作、[リソース マッピング スキーマ](./resource-mapping-schema.md)します。</span><span class="sxs-lookup"><span data-stu-id="cad84-103">After you define the resources your web service will expose (see [Authoring the MOF schema file for a Management OData web service](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)), you map those resources to the underlying Windows PowerShell cmdlets that implement the supported operations for each resource by creating an XML file that conforms to the [Resource Mapping Schema](./resource-mapping-schema.md).</span></span> <span data-ttu-id="cad84-104">XML ファイルには、リソースにアクセスするクライアントで使用される Url も指定します。</span><span class="sxs-lookup"><span data-stu-id="cad84-104">The XML file also specifies the URLs that are used by the client to access the resources.</span></span>

## <a name="mappng-resources-to-urls"></a><span data-ttu-id="cad84-105">Url に Mappng リソース</span><span class="sxs-lookup"><span data-stu-id="cad84-105">Mappng resources to URLs</span></span>

<span data-ttu-id="cad84-106">XML ファイルの最初の部分では、それらにアクセスするために使用する Url に、MOF スキーマ ファイルで定義されているリソースをマップします。</span><span class="sxs-lookup"><span data-stu-id="cad84-106">The first part of the XML file maps the resources defined in the MOF schema file to the URLs that are used to access them.</span></span> <span data-ttu-id="cad84-107">次の例では、そのマッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="cad84-107">The following example shows that mapping.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<ResourceMetadata xmlns="http://schemas.microsoft.com/powershell-web-services/2010/09">
    <SchemaNamespace>PswsTest</SchemaNamespace>
    <ContainerName>PSWSEntityContainer</ContainerName>
    <Resources>
        <Resource>
            <RelativeUrl>Service</RelativeUrl>
            <Class>PswsTest_Service</Class>
        </Resource>
        <Resource>
            <RelativeUrl>Process</RelativeUrl>
            <Class>PswsTest_Process</Class>
        </Resource>
    </Resources>
```

## <a name="mapping-cmdlets-to-crud-operations"></a><span data-ttu-id="cad84-108">CRUD 操作にマッピング コマンドレット</span><span class="sxs-lookup"><span data-stu-id="cad84-108">Mapping cmdlets to CRUD operations</span></span>

<span data-ttu-id="cad84-109">CRUD に対応するコマンドレットを指定します (作成、読み取り、更新、および削除)、リソースをサポートする操作。</span><span class="sxs-lookup"><span data-stu-id="cad84-109">You then specify the cmdlets that correspond to the CRUD (create, read, update, and delete) operations that the resources support.</span></span> <span data-ttu-id="cad84-110">Management odata[リソース マッピング スキーマ](./resource-mapping-schema.md)、CRUD 操作は次のようにマップされます。</span><span class="sxs-lookup"><span data-stu-id="cad84-110">In the Management OData [Resource Mapping Schema](./resource-mapping-schema.md), the CRUD operations are mapped as follows.</span></span>

|<span data-ttu-id="cad84-111">CRUD コマンド</span><span class="sxs-lookup"><span data-stu-id="cad84-111">CRUD command</span></span>|<span data-ttu-id="cad84-112">XML 要素</span><span class="sxs-lookup"><span data-stu-id="cad84-112">XML element</span></span>|
|------------------|-----------------|
|<span data-ttu-id="cad84-113">作成</span><span class="sxs-lookup"><span data-stu-id="cad84-113">Create</span></span>|<span data-ttu-id="cad84-114">作成</span><span class="sxs-lookup"><span data-stu-id="cad84-114">Create</span></span>|
|<span data-ttu-id="cad84-115">読み取り</span><span class="sxs-lookup"><span data-stu-id="cad84-115">Read</span></span>|<span data-ttu-id="cad84-116">クエリ</span><span class="sxs-lookup"><span data-stu-id="cad84-116">Query</span></span>|
|<span data-ttu-id="cad84-117">更新プログラム、更新</span><span class="sxs-lookup"><span data-stu-id="cad84-117">Update</span></span>|<span data-ttu-id="cad84-118">更新プログラム、更新</span><span class="sxs-lookup"><span data-stu-id="cad84-118">Update</span></span>|
|<span data-ttu-id="cad84-119">削除</span><span class="sxs-lookup"><span data-stu-id="cad84-119">Delete</span></span>|<span data-ttu-id="cad84-120">削除</span><span class="sxs-lookup"><span data-stu-id="cad84-120">Delete</span></span>|

<span data-ttu-id="cad84-121">次の例で、作成、読み取り、および更新操作のマッピングを示しています、`Service`リソース。</span><span class="sxs-lookup"><span data-stu-id="cad84-121">The following example shows the mappings for the Create, Read, and Update operations on the `Service` resource.</span></span>

```xml
<ClassImplementations>
        <Class>
            <Name>PswsTest_Service</Name>
            <CmdletImplementation>
                <Query>
                    <Cmdlet>Get-Service</Cmdlet>
                        <FieldParameterMap>
                            <Field>
                                <FieldName>ServiceName</FieldName>
                                <ParameterName>Name</ParameterName>
                            </Field>
                        </FieldParameterMap>
                        <ParameterSets>
                            <ParameterSet>
                                <Name>Default</Name>
                                <Parameter><Name>Name</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>ComputerName</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>Include</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>Exclude</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>ErrorVariable</Name></Parameter>
                                <Parameter><Name>WarningVariable</Name></Parameter>
                                <Parameter><Name>OutVariable</Name></Parameter>
                                <Parameter><Name>OutBuffer</Name></Parameter>
                            </ParameterSet>
                            <ParameterSet>
                                <Name>DisplayName</Name>
                                <Parameter><Name>DisplayName</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>ComputerName</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>Include</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>Exclude</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>ErrorVariable</Name></Parameter>
                                <Parameter><Name>WarningVariable</Name></Parameter>
                                <Parameter><Name>OutVariable</Name></Parameter>
                                <Parameter><Name>OutBuffer</Name></Parameter>
                            </ParameterSet>
                            <ParameterSet>
                                <Name>InputObject</Name>
                                <Parameter><Name>ComputerName</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>Include</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>Exclude</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>ErrorVariable</Name></Parameter>
                                <Parameter><Name>WarningVariable</Name></Parameter>
                                <Parameter><Name>OutVariable</Name></Parameter>
                                <Parameter><Name>OutBuffer</Name></Parameter>
                        </ParameterSet>
                    </ParameterSets>
                </Query>
                <Update>
                    <Cmdlet>Set-Service</Cmdlet>
                    <FieldParameterMap>
                        <Field>
                            <FieldName>ServiceName</FieldName>
                            <ParameterName>Name</ParameterName>
                        </Field>
                    </FieldParameterMap>
                    <ParameterSets>
                        <ParameterSet>
                            <Name>Name</Name>
                            <Parameter><Name>ComputerName</Name><Type>System.String[]</Type></Parameter>
                            <Parameter><Name>Name</Name></Parameter>
                            <Parameter><Name>DisplayName</Name></Parameter>
                            <Parameter><Name>Description</Name></Parameter>
                            <Parameter><Name>Status</Name></Parameter>
                            <Parameter><Name>ErrorVariable</Name></Parameter>
                            <Parameter><Name>WarningVariable</Name></Parameter>
                            <Parameter><Name>OutVariable</Name></Parameter>
                            <Parameter><Name>OutBuffer</Name></Parameter>
                        </ParameterSet>
                        <ParameterSet>
                            <Name>InputObject</Name>
                            <Parameter><Name>ComputerName</Name><Type>System.String[]</Type></Parameter>
                            <Parameter><Name>DisplayName</Name></Parameter>
                            <Parameter><Name>Description</Name></Parameter>
                        </ParameterSet>
                    </ParameterSets>
                </Update>
                <Create>
                    <Cmdlet>New-Service</Cmdlet>
                    <FieldParameterMap>
                        <Field>
                            <FieldName>ServiceName</FieldName>
                            <ParameterName>Name</ParameterName>
                        </Field>
                    </FieldParameterMap>
                    <ParameterSets>
                        <ParameterSet>
                            <Name>__AllParameterSets</Name>
                            <Parameter><Name>BinaryPathName</Name></Parameter>
                            <Parameter><Name>Name</Name></Parameter>
                            <Parameter><Name>DisplayName</Name></Parameter>
                            <Parameter><Name>Description</Name></Parameter>
                            <Parameter><Name>DependsOn</Name></Parameter>
                            <Parameter><Name>ErrorVariable</Name></Parameter>
                            <Parameter><Name>WarningVariable</Name></Parameter>
                            <Parameter><Name>OutVariable</Name></Parameter>
                            <Parameter><Name>OutBuffer</Name></Parameter>
                        </ParameterSet>
                    </ParameterSets>
                </Create>
            </CmdletImplementation>
        </Class>
```

## <a name="see-also"></a><span data-ttu-id="cad84-122">参照</span><span class="sxs-lookup"><span data-stu-id="cad84-122">See Also</span></span>

[<span data-ttu-id="cad84-123">Management OData web サービスの MOF スキーマ ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="cad84-123">Authoring the MOF schema file for a Management OData web service</span></span>](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

[<span data-ttu-id="cad84-124">リソースのマッピング スキーマ</span><span class="sxs-lookup"><span data-stu-id="cad84-124">Resource Mapping Schema</span></span>](./resource-mapping-schema.md)

[<span data-ttu-id="cad84-125">Management OData Web サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="cad84-125">Creating a Management OData Web Service</span></span>](./creating-a-management-odata-web-service.md)