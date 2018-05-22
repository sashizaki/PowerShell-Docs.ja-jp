---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 DSC の nxFileLine リソース
ms.openlocfilehash: 6b927839c23478aa9916a5d23836b31fccc58484
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="dsc-for-linux-nxfileline-resource"></a><span data-ttu-id="06551-103">Linux 用 DSC の nxFileLine リソース</span><span class="sxs-lookup"><span data-stu-id="06551-103">DSC for Linux nxFileLine Resource</span></span>

<span data-ttu-id="06551-104">PowerShell Desired State Configuration (DSC) の **nxFileLine** リソースは、Linux ノード上で構成ファイルの行を管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="06551-104">The **nxFileLine** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to to manage lines within a configuration file on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="06551-105">構文</span><span class="sxs-lookup"><span data-stu-id="06551-105">Syntax</span></span>

```
nxFileLine <string> #ResourceName
{
    FilePath = <string>
    ContainsLine = <string>
    [ DoesNotContainPattern = <string> ]
    [ DependsOn = <string[]> ]

}
```

## <a name="properties"></a><span data-ttu-id="06551-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="06551-106">Properties</span></span>

|  <span data-ttu-id="06551-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="06551-107">Property</span></span> |  <span data-ttu-id="06551-108">説明</span><span class="sxs-lookup"><span data-stu-id="06551-108">Description</span></span> |
|---|---|
| <span data-ttu-id="06551-109">ファイル パス</span><span class="sxs-lookup"><span data-stu-id="06551-109">FilePath</span></span>| <span data-ttu-id="06551-110">ターゲット ノード上の行を管理するファイルの完全パス。</span><span class="sxs-lookup"><span data-stu-id="06551-110">The full path to the file to manage lines in on the target node.</span></span>|
| <span data-ttu-id="06551-111">ContainsLine</span><span class="sxs-lookup"><span data-stu-id="06551-111">ContainsLine</span></span>| <span data-ttu-id="06551-112">ファイルに行が存在するようにします。</span><span class="sxs-lookup"><span data-stu-id="06551-112">A line to ensure exists in the file.</span></span> <span data-ttu-id="06551-113">ファイルに行が存在しない場合、この行がファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="06551-113">This line will be appended to the file if it does not exist in the file.</span></span> <span data-ttu-id="06551-114">**ContainsLine** は必須ですが、必要ない場合は空の文字列 (\`ContainsLine = ‘’\`\`) に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="06551-114">**ContainsLine** is mandatory, but can be set to an empty string (\`ContainsLine = ‘’\`\`) if it is not needed.</span></span>|
| <span data-ttu-id="06551-115">DoesNotContainPattern</span><span class="sxs-lookup"><span data-stu-id="06551-115">DoesNotContainPattern</span></span>| <span data-ttu-id="06551-116">ファイルに存在することができない行の正規表現パターン。</span><span class="sxs-lookup"><span data-stu-id="06551-116">A regular expression pattern for lines that should not exist in the file.</span></span> <span data-ttu-id="06551-117">ファイルに存在する行のうち、この正規表現に一致する行は、ファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="06551-117">For any lines that exist in the file that match this regular expression, the line will be removed from the file.</span></span>|
| <span data-ttu-id="06551-118">DependsOn</span><span class="sxs-lookup"><span data-stu-id="06551-118">DependsOn</span></span> | <span data-ttu-id="06551-119">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="06551-119">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="06551-120">たとえば、最初に実行するリソース構成スクリプト ブロックの **ID** が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="06551-120">For example, if the **ID** of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="example"></a><span data-ttu-id="06551-121">例</span><span class="sxs-lookup"><span data-stu-id="06551-121">Example</span></span>

<span data-ttu-id="06551-122">この例では、**nxFileLine** リソースを使用して、ユーザー monuser が not requiretty に構成されるように `/etc/sudoers` ファイルを構成しています。</span><span class="sxs-lookup"><span data-stu-id="06551-122">This example demonstrates using the **nxFileLine** resource to configure the `/etc/sudoers` file, ensuring that the user: monuser is configured to not requiretty.</span></span>

```
Import-DSCResource -Module nx

nxFileLine DoNotRequireTTY
{
   FilePath = “/etc/sudoers”
   ContainsLine = 'Defaults:monuser !requiretty'
   DoesNotContainPattern = "Defaults:monuser[ ]+requiretty"
}
```