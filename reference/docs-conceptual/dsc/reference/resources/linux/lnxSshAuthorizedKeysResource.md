---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 DSC の nxSshAuthorizedKeys リソース
ms.openlocfilehash: 6e008efcbff2e679650d0bc3d5b8b573f6ef83e0
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953259"
---
# <a name="dsc-for-linux-nxsshauthorizedkeys-resource"></a><span data-ttu-id="396fc-103">Linux 用 DSC の nxSshAuthorizedKeys リソース</span><span class="sxs-lookup"><span data-stu-id="396fc-103">DSC for Linux nxSshAuthorizedKeys Resource</span></span>

<span data-ttu-id="396fc-104">PowerShell Desired State Configuration (DSC) の **nxAuthorizedKeys** リソースは、特定のユーザーの承認された ssh キーを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="396fc-104">The **nxAuthorizedKeys** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage authorized ssh keys for a specified user.</span></span>

## <a name="syntax"></a><span data-ttu-id="396fc-105">構文</span><span class="sxs-lookup"><span data-stu-id="396fc-105">Syntax</span></span>

```Syntax
nxAuthorizedKeys <string> #ResourceName
{
    KeyComment = <string>
    [ Username = <string> ]
    [ Key = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a><span data-ttu-id="396fc-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="396fc-106">Properties</span></span>

|<span data-ttu-id="396fc-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="396fc-107">Property</span></span> |<span data-ttu-id="396fc-108">説明</span><span class="sxs-lookup"><span data-stu-id="396fc-108">Description</span></span> |
|---|---|
|<span data-ttu-id="396fc-109">KeyComment</span><span class="sxs-lookup"><span data-stu-id="396fc-109">KeyComment</span></span> |<span data-ttu-id="396fc-110">キーの一意のコメント。</span><span class="sxs-lookup"><span data-stu-id="396fc-110">A unique comment for the key.</span></span> <span data-ttu-id="396fc-111">これは、キーを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="396fc-111">This is used to uniquely identify keys.</span></span> |
|<span data-ttu-id="396fc-112">Username</span><span class="sxs-lookup"><span data-stu-id="396fc-112">Username</span></span> |<span data-ttu-id="396fc-113">承認された ssh キーを管理するユーザー名。</span><span class="sxs-lookup"><span data-stu-id="396fc-113">The username to manage ssh authorized keys for.</span></span> <span data-ttu-id="396fc-114">定義されていない場合、既定のユーザーは **root** です。</span><span class="sxs-lookup"><span data-stu-id="396fc-114">If not defined, the default user is **root**.</span></span> |
|<span data-ttu-id="396fc-115">キー</span><span class="sxs-lookup"><span data-stu-id="396fc-115">Key</span></span> |<span data-ttu-id="396fc-116">キーの内容。</span><span class="sxs-lookup"><span data-stu-id="396fc-116">The contents of the key.</span></span> <span data-ttu-id="396fc-117">**Ensure** を **Present** に設定する場合、これは必須になります。</span><span class="sxs-lookup"><span data-stu-id="396fc-117">This is required if **Ensure** is set to **Present**.</span></span>|

## <a name="common-properties"></a><span data-ttu-id="396fc-118">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="396fc-118">Common properties</span></span>

|<span data-ttu-id="396fc-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="396fc-119">Property</span></span> |<span data-ttu-id="396fc-120">説明</span><span class="sxs-lookup"><span data-stu-id="396fc-120">Description</span></span> |
|---|---|
|<span data-ttu-id="396fc-121">DependsOn</span><span class="sxs-lookup"><span data-stu-id="396fc-121">DependsOn</span></span> |<span data-ttu-id="396fc-122">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="396fc-122">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="396fc-123">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="396fc-123">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="396fc-124">Ensure</span><span class="sxs-lookup"><span data-stu-id="396fc-124">Ensure</span></span> |<span data-ttu-id="396fc-125">キーが定義されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="396fc-125">Specifies whether the key is defined.</span></span> <span data-ttu-id="396fc-126">ユーザーの認定キー ファイルにキーが確実に存在しないようにするには、このプロパティを **Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="396fc-126">Set this property to **Absent** to ensure the key does not exist in the user's authorized keys file.</span></span> <span data-ttu-id="396fc-127">ユーザーの承認されたキー ファイルにキーが確実に定義されるようにするには、このプロパティに **Present** を設定します。</span><span class="sxs-lookup"><span data-stu-id="396fc-127">Set it to **Present** to ensure the key is defined in the user's authorized key file.</span></span> |

## <a name="example"></a><span data-ttu-id="396fc-128">例</span><span class="sxs-lookup"><span data-stu-id="396fc-128">Example</span></span>

<span data-ttu-id="396fc-129">次の例では、ユーザー "monuser" の公開 ssh 承認済みキーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="396fc-129">The following example defines a public ssh authorized key for the user "monuser".</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxSshAuthorizedKeys myKey
    {
        KeyComment = "myKey"
        Ensure = "Present"
        Key = 'ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEA0b+0xSd07QXRifm3FXj7Pn/DblA6QI5VAkDm6OivFzj3U6qGD1VJ6AAxWPCyMl/qhtpRtxZJDu/TxD8AyZNgc8aN2CljN1hOMbBRvH2q5QPf/nCnnJRaGsrxIqZjyZdYo9ZEEzjZUuMDM5HI1LA9B99k/K6PK2Bc1NLivpu7nbtVG2tLOQs+GefsnHuetsRMwo/+c3LtwYm9M0XfkGjYVCLO4CoFuSQpvX6AB3TedUy6NZ0iuxC0kRGg1rIQTwSRcw+McLhslF0drs33fw6tYdzlLBnnzimShMuiDWiT37WqCRovRGYrGCaEFGTG2e0CN8Co8nryXkyWc6NSDNpMzw== rsa-key-20150401'
        UserName = "monuser"
    }
}
```