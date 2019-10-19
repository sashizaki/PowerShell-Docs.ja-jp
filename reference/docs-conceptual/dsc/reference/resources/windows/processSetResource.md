---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC ProcessSet リソース
ms.openlocfilehash: 72925d3a9516f5c0040427773a3b1d66034667bb
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953129"
---
# <a name="dsc-processset-resource"></a><span data-ttu-id="4c111-103">DSC ProcessSet リソース</span><span class="sxs-lookup"><span data-stu-id="4c111-103">DSC ProcessSet Resource</span></span>

> <span data-ttu-id="4c111-104">適用先:Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="4c111-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="4c111-105">Windows PowerShell Desired State Configuration (DSC) の **ProcessSet** リソースは、ターゲット ノードにプロセスを構成するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="4c111-105">The **ProcessSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to configure processes on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="4c111-106">構文</span><span class="sxs-lookup"><span data-stu-id="4c111-106">Syntax</span></span>

```Syntax
ProcessSet [string] #ResourceName
{
    Path = [string]
    [ Credential = [PSCredential] ]
    [ StandardOutputPath = [string] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="4c111-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4c111-107">Properties</span></span>

|<span data-ttu-id="4c111-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4c111-108">Property</span></span> |<span data-ttu-id="4c111-109">説明</span><span class="sxs-lookup"><span data-stu-id="4c111-109">Description</span></span> |
|---|---|
|<span data-ttu-id="4c111-110">パス</span><span class="sxs-lookup"><span data-stu-id="4c111-110">Path</span></span> |<span data-ttu-id="4c111-111">プロセスの実行可能ファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="4c111-111">The path to the process executable.</span></span> <span data-ttu-id="4c111-112">実行可能ファイルの名前がある場合 (完全修飾パスではない)、DSC リソースは環境 `$env:Path` 変数を検索し、ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="4c111-112">If these are the names of the executable files (not fully qualified paths), the DSC resource will search the environment `$env:Path` variable to find the files.</span></span> <span data-ttu-id="4c111-113">このプロパティの値が完全修飾パスの場合、DSC は `$env:Path` 環境変数でファイルを探すことはせず、パスが存在しない場合はエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="4c111-113">If the values of this property are fully qualified paths, DSC will not use the `$env:Path` environment variable to find the files, and will throw an error if any of the paths do not exist.</span></span> <span data-ttu-id="4c111-114">相対パスは指定できません。</span><span class="sxs-lookup"><span data-stu-id="4c111-114">Relative paths are not allowed.</span></span> |
|<span data-ttu-id="4c111-115">Credential</span><span class="sxs-lookup"><span data-stu-id="4c111-115">Credential</span></span> |<span data-ttu-id="4c111-116">プロセスを開始するための資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c111-116">Indicates the credentials for starting the process.</span></span> |
|<span data-ttu-id="4c111-117">StandardErrorPath</span><span class="sxs-lookup"><span data-stu-id="4c111-117">StandardErrorPath</span></span> |<span data-ttu-id="4c111-118">プロセスにより標準エラーが書き込まれるパス。</span><span class="sxs-lookup"><span data-stu-id="4c111-118">The path to which the processes write standard error.</span></span> <span data-ttu-id="4c111-119">既存のファイルは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="4c111-119">Any existing file there will be overwritten.</span></span> |
|<span data-ttu-id="4c111-120">StandardInputPath</span><span class="sxs-lookup"><span data-stu-id="4c111-120">StandardInputPath</span></span> |<span data-ttu-id="4c111-121">プロセスが標準入力を受け取るとき、その発信元となるストリーム。</span><span class="sxs-lookup"><span data-stu-id="4c111-121">The stream from which the process receives standard input.</span></span> |
|<span data-ttu-id="4c111-122">StandardOutputPath</span><span class="sxs-lookup"><span data-stu-id="4c111-122">StandardOutputPath</span></span> |<span data-ttu-id="4c111-123">プロセスにより標準出力が書き込まれるファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="4c111-123">The path of the file to which the processes write standard output.</span></span> <span data-ttu-id="4c111-124">既存のファイルは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="4c111-124">Any existing file there will be overwritten.</span></span> |
|<span data-ttu-id="4c111-125">WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="4c111-125">WorkingDirectory</span></span> |<span data-ttu-id="4c111-126">プロセスの現在の作業ディレクトリとして使用されている場所。</span><span class="sxs-lookup"><span data-stu-id="4c111-126">The location used as the current working directory for the processes.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="4c111-127">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="4c111-127">Common properties</span></span>

|<span data-ttu-id="4c111-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4c111-128">Property</span></span> |<span data-ttu-id="4c111-129">説明</span><span class="sxs-lookup"><span data-stu-id="4c111-129">Description</span></span> |
|---|---|
|<span data-ttu-id="4c111-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="4c111-130">DependsOn</span></span> |<span data-ttu-id="4c111-131">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="4c111-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="4c111-132">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="4c111-132">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="4c111-133">Ensure</span><span class="sxs-lookup"><span data-stu-id="4c111-133">Ensure</span></span> |<span data-ttu-id="4c111-134">プロセスが存在するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4c111-134">Specifies whether the processes exists.</span></span> <span data-ttu-id="4c111-135">プロセスの存在を保証するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="4c111-135">Set this property to **Present** to ensure that the process exists.</span></span> <span data-ttu-id="4c111-136">それ以外の場合は、**Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="4c111-136">Otherwise, set it to **Absent**.</span></span> <span data-ttu-id="4c111-137">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="4c111-137">The default value is **Present**.</span></span> |
|<span data-ttu-id="4c111-138">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="4c111-138">PsDscRunAsCredential</span></span> |<span data-ttu-id="4c111-139">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="4c111-139">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="4c111-140">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="4c111-140">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="4c111-141">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c111-141">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>