---
ms.date: 07/17/2020
ms.topic: reference
title: Linux 用 DSC の nxFileLine リソース
description: Linux 用 DSC の nxFileLine リソース
ms.openlocfilehash: b342021176e4d8584afec82173f31bf5191ad264
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644764"
---
# <a name="dsc-for-linux-nxfileline-resource"></a><span data-ttu-id="cfbe0-103">Linux 用 DSC の nxFileLine リソース</span><span class="sxs-lookup"><span data-stu-id="cfbe0-103">DSC for Linux nxFileLine Resource</span></span>

<span data-ttu-id="cfbe0-104">PowerShell Desired State Configuration (DSC) の **nxFileLine** リソースは、Linux ノード上で構成ファイルの行を管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="cfbe0-104">The **nxFileLine** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage lines within a configuration file on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="cfbe0-105">構文</span><span class="sxs-lookup"><span data-stu-id="cfbe0-105">Syntax</span></span>

```Syntax
nxFileLine <string> #ResourceName
{
    FilePath = <string>
    ContainsLine = <string>
    [ DoesNotContainPattern = <string> ]
    [ DependsOn = <string[]> ]
}
```

## <a name="properties"></a><span data-ttu-id="cfbe0-106">Properties</span><span class="sxs-lookup"><span data-stu-id="cfbe0-106">Properties</span></span>

|<span data-ttu-id="cfbe0-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="cfbe0-107">Property</span></span> |<span data-ttu-id="cfbe0-108">説明</span><span class="sxs-lookup"><span data-stu-id="cfbe0-108">Description</span></span> |
|---|---|
|<span data-ttu-id="cfbe0-109">FilePath</span><span class="sxs-lookup"><span data-stu-id="cfbe0-109">FilePath</span></span> |<span data-ttu-id="cfbe0-110">ターゲット ノード上の行を管理するファイルの完全パス。</span><span class="sxs-lookup"><span data-stu-id="cfbe0-110">The full path to the file to manage lines in on the target node.</span></span> |
|<span data-ttu-id="cfbe0-111">ContainsLine</span><span class="sxs-lookup"><span data-stu-id="cfbe0-111">ContainsLine</span></span> |<span data-ttu-id="cfbe0-112">ファイルに行が存在するようにします。</span><span class="sxs-lookup"><span data-stu-id="cfbe0-112">A line to ensure exists in the file.</span></span> <span data-ttu-id="cfbe0-113">ファイルに行が存在しない場合、この行がファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="cfbe0-113">This line will be appended to the file if it does not exist in the file.</span></span> <span data-ttu-id="cfbe0-114">**ContainsLine** は必須ですが、必要ない場合は空の文字列 (`ContainsLine = ""`) に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="cfbe0-114">**ContainsLine** is mandatory, but can be set to an empty string (`ContainsLine = ""`) if it is not needed.</span></span> |
|<span data-ttu-id="cfbe0-115">DoesNotContainPattern</span><span class="sxs-lookup"><span data-stu-id="cfbe0-115">DoesNotContainPattern</span></span> |<span data-ttu-id="cfbe0-116">ファイルに存在することができない行の正規表現パターン。</span><span class="sxs-lookup"><span data-stu-id="cfbe0-116">A regular expression pattern for lines that should not exist in the file.</span></span> <span data-ttu-id="cfbe0-117">ファイルに存在する行のうち、この正規表現に一致する行は、ファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="cfbe0-117">For any lines that exist in the file that match this regular expression, the line will be removed from the file.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="cfbe0-118">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="cfbe0-118">Common properties</span></span>

|<span data-ttu-id="cfbe0-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="cfbe0-119">Property</span></span> |<span data-ttu-id="cfbe0-120">説明</span><span class="sxs-lookup"><span data-stu-id="cfbe0-120">Description</span></span> |
|---|---|
|<span data-ttu-id="cfbe0-121">DependsOn</span><span class="sxs-lookup"><span data-stu-id="cfbe0-121">DependsOn</span></span> |<span data-ttu-id="cfbe0-122">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="cfbe0-122">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="cfbe0-123">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="cfbe0-123">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |

## <a name="example"></a><span data-ttu-id="cfbe0-124">例</span><span class="sxs-lookup"><span data-stu-id="cfbe0-124">Example</span></span>

<span data-ttu-id="cfbe0-125">この例では、 **nxFileLine** リソースを使用して、ユーザー monuser が not requiretty に構成されるように `/etc/sudoers` ファイルを構成しています。</span><span class="sxs-lookup"><span data-stu-id="cfbe0-125">This example demonstrates using the **nxFileLine** resource to configure the `/etc/sudoers` file, ensuring that the user: monuser is configured to not requiretty.</span></span>

```powershell
Import-DscResource -Module nx

nxFileLine DoNotRequireTTY
{
   FilePath = "/etc/sudoers"
   ContainsLine = 'Defaults:monuser !requiretty'
   DoesNotContainPattern = "Defaults:monuser[ ]+requiretty"
}
```
