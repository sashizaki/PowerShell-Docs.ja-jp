---
title: 管理 OData web サービスの XML スキーマファイルの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e83c9d9-6d06-4247-94d9-e3bfd4013b11
caps.latest.revision: 4
ms.openlocfilehash: 7ccdeeb2833b79cabc7c77d1a400e0c9132b2dcd
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561466"
---
# <a name="authoring-the-xml-schema-file-for-a-management-odata-web-service"></a><span data-ttu-id="cbf33-102">Management OData Web サービスの XML スキーマ ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="cbf33-102">Authoring the XML schema file for a Management OData web service</span></span>

<span data-ttu-id="cbf33-103">Web サービスが公開するリソース (「 [Management OData web サービスの MOF スキーマファイルの作成](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)」を参照) を定義した後、リソース[マッピングスキーマ](./resource-mapping-schema.md)に準拠した XML ファイルを作成することにより、各リソースに対してサポートされている操作を実装する、基になる Windows PowerShell コマンドレットにそれらのリソースをマップします。</span><span class="sxs-lookup"><span data-stu-id="cbf33-103">After you define the resources your web service will expose (see [Authoring the MOF schema file for a Management OData web service](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)), you map those resources to the underlying Windows PowerShell cmdlets that implement the supported operations for each resource by creating an XML file that conforms to the [Resource Mapping Schema](./resource-mapping-schema.md).</span></span> <span data-ttu-id="cbf33-104">また、この XML ファイルは、クライアントがリソースにアクセスするために使用する Url を指定します。</span><span class="sxs-lookup"><span data-stu-id="cbf33-104">The XML file also specifies the URLs that are used by the client to access the resources.</span></span>

## <a name="mappng-resources-to-urls"></a><span data-ttu-id="cbf33-105">Url へのリソースの Mappng</span><span class="sxs-lookup"><span data-stu-id="cbf33-105">Mappng resources to URLs</span></span>

<span data-ttu-id="cbf33-106">XML ファイルの最初の部分は、MOF スキーマファイルで定義されているリソースを、それらへのアクセスに使用される Url にマップします。</span><span class="sxs-lookup"><span data-stu-id="cbf33-106">The first part of the XML file maps the resources defined in the MOF schema file to the URLs that are used to access them.</span></span> <span data-ttu-id="cbf33-107">次の例は、そのマッピングを示しています。</span><span class="sxs-lookup"><span data-stu-id="cbf33-107">The following example shows that mapping.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<ResourceMetadata xmlns="https://schemas.microsoft.com/powershell-web-services/2010/09">
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

## <a name="mapping-cmdlets-to-crud-operations"></a><span data-ttu-id="cbf33-108">コマンドレットを CRUD 操作にマッピングする</span><span class="sxs-lookup"><span data-stu-id="cbf33-108">Mapping cmdlets to CRUD operations</span></span>

<span data-ttu-id="cbf33-109">次に、リソースがサポートする CRUD (作成、読み取り、更新、および削除) 操作に対応するコマンドレットを指定します。</span><span class="sxs-lookup"><span data-stu-id="cbf33-109">You then specify the cmdlets that correspond to the CRUD (create, read, update, and delete) operations that the resources support.</span></span> <span data-ttu-id="cbf33-110">Management OData[リソースマッピングスキーマ](./resource-mapping-schema.md)では、CRUD 操作は次のようにマップされます。</span><span class="sxs-lookup"><span data-stu-id="cbf33-110">In the Management OData [Resource Mapping Schema](./resource-mapping-schema.md), the CRUD operations are mapped as follows.</span></span>

|<span data-ttu-id="cbf33-111">CRUD コマンド</span><span class="sxs-lookup"><span data-stu-id="cbf33-111">CRUD command</span></span>|<span data-ttu-id="cbf33-112">XML 要素</span><span class="sxs-lookup"><span data-stu-id="cbf33-112">XML element</span></span>|
|------------------|-----------------|
|<span data-ttu-id="cbf33-113">作成</span><span class="sxs-lookup"><span data-stu-id="cbf33-113">Create</span></span>|<span data-ttu-id="cbf33-114">作成</span><span class="sxs-lookup"><span data-stu-id="cbf33-114">Create</span></span>|
|<span data-ttu-id="cbf33-115">読み取り</span><span class="sxs-lookup"><span data-stu-id="cbf33-115">Read</span></span>|<span data-ttu-id="cbf33-116">クエリ</span><span class="sxs-lookup"><span data-stu-id="cbf33-116">Query</span></span>|
|<span data-ttu-id="cbf33-117">更新</span><span class="sxs-lookup"><span data-stu-id="cbf33-117">Update</span></span>|<span data-ttu-id="cbf33-118">更新</span><span class="sxs-lookup"><span data-stu-id="cbf33-118">Update</span></span>|
|<span data-ttu-id="cbf33-119">削除</span><span class="sxs-lookup"><span data-stu-id="cbf33-119">Delete</span></span>|<span data-ttu-id="cbf33-120">削除</span><span class="sxs-lookup"><span data-stu-id="cbf33-120">Delete</span></span>|

<span data-ttu-id="cbf33-121">次の例は、リソースに対する作成、読み取り、更新の各操作のマッピングを示して `Service` います。</span><span class="sxs-lookup"><span data-stu-id="cbf33-121">The following example shows the mappings for the Create, Read, and Update operations on the `Service` resource.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cbf33-122">参照</span><span class="sxs-lookup"><span data-stu-id="cbf33-122">See Also</span></span>

[<span data-ttu-id="cbf33-123">Management OData Web サービスの MOF スキーマ ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="cbf33-123">Authoring the MOF schema file for a Management OData web service</span></span>](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

[<span data-ttu-id="cbf33-124">リソース マッピング スキーマ</span><span class="sxs-lookup"><span data-stu-id="cbf33-124">Resource Mapping Schema</span></span>](./resource-mapping-schema.md)

[<span data-ttu-id="cbf33-125">Management OData Web サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="cbf33-125">Creating a Management OData Web Service</span></span>](./creating-a-management-odata-web-service.md)
