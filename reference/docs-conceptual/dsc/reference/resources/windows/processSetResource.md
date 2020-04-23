---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC ProcessSet リソース
ms.openlocfilehash: 72925d3a9516f5c0040427773a3b1d66034667bb
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953129"
---
# <a name="dsc-processset-resource"></a><span data-ttu-id="08b4a-103">DSC ProcessSet リソース</span><span class="sxs-lookup"><span data-stu-id="08b4a-103">DSC ProcessSet Resource</span></span>

> <span data-ttu-id="08b4a-104">適用先:Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="08b4a-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="08b4a-105">Windows PowerShell Desired State Configuration (DSC) の **ProcessSet** リソースは、ターゲット ノードにプロセスを構成するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="08b4a-105">The **ProcessSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to configure processes on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="08b4a-106">構文</span><span class="sxs-lookup"><span data-stu-id="08b4a-106">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="08b4a-107">Properties</span><span class="sxs-lookup"><span data-stu-id="08b4a-107">Properties</span></span>

|<span data-ttu-id="08b4a-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="08b4a-108">Property</span></span> |<span data-ttu-id="08b4a-109">説明</span><span class="sxs-lookup"><span data-stu-id="08b4a-109">Description</span></span> |
|---|---|
|<span data-ttu-id="08b4a-110">Path</span><span class="sxs-lookup"><span data-stu-id="08b4a-110">Path</span></span> |<span data-ttu-id="08b4a-111">プロセスの実行可能ファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="08b4a-111">The path to the process executable.</span></span> <span data-ttu-id="08b4a-112">実行可能ファイルの名前がある場合 (完全修飾パスではない)、DSC リソースは環境 `$env:Path` 変数を検索し、ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="08b4a-112">If these are the names of the executable files (not fully qualified paths), the DSC resource will search the environment `$env:Path` variable to find the files.</span></span> <span data-ttu-id="08b4a-113">このプロパティの値が完全修飾パスの場合、DSC は `$env:Path` 環境変数でファイルを探すことはせず、パスが存在しない場合はエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="08b4a-113">If the values of this property are fully qualified paths, DSC will not use the `$env:Path` environment variable to find the files, and will throw an error if any of the paths do not exist.</span></span> <span data-ttu-id="08b4a-114">相対パスは指定できません。</span><span class="sxs-lookup"><span data-stu-id="08b4a-114">Relative paths are not allowed.</span></span> |
|<span data-ttu-id="08b4a-115">資格情報</span><span class="sxs-lookup"><span data-stu-id="08b4a-115">Credential</span></span> |<span data-ttu-id="08b4a-116">プロセスを開始するための資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="08b4a-116">Indicates the credentials for starting the process.</span></span> |
|<span data-ttu-id="08b4a-117">StandardErrorPath</span><span class="sxs-lookup"><span data-stu-id="08b4a-117">StandardErrorPath</span></span> |<span data-ttu-id="08b4a-118">プロセスにより標準エラーが書き込まれるパス。</span><span class="sxs-lookup"><span data-stu-id="08b4a-118">The path to which the processes write standard error.</span></span> <span data-ttu-id="08b4a-119">既存のファイルは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="08b4a-119">Any existing file there will be overwritten.</span></span> |
|<span data-ttu-id="08b4a-120">StandardInputPath</span><span class="sxs-lookup"><span data-stu-id="08b4a-120">StandardInputPath</span></span> |<span data-ttu-id="08b4a-121">プロセスが標準入力を受け取るとき、その発信元となるストリーム。</span><span class="sxs-lookup"><span data-stu-id="08b4a-121">The stream from which the process receives standard input.</span></span> |
|<span data-ttu-id="08b4a-122">StandardOutputPath</span><span class="sxs-lookup"><span data-stu-id="08b4a-122">StandardOutputPath</span></span> |<span data-ttu-id="08b4a-123">プロセスにより標準出力が書き込まれるファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="08b4a-123">The path of the file to which the processes write standard output.</span></span> <span data-ttu-id="08b4a-124">既存のファイルは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="08b4a-124">Any existing file there will be overwritten.</span></span> |
|<span data-ttu-id="08b4a-125">WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="08b4a-125">WorkingDirectory</span></span> |<span data-ttu-id="08b4a-126">プロセスの現在の作業ディレクトリとして使用されている場所。</span><span class="sxs-lookup"><span data-stu-id="08b4a-126">The location used as the current working directory for the processes.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="08b4a-127">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="08b4a-127">Common properties</span></span>

|<span data-ttu-id="08b4a-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="08b4a-128">Property</span></span> |<span data-ttu-id="08b4a-129">説明</span><span class="sxs-lookup"><span data-stu-id="08b4a-129">Description</span></span> |
|---|---|
|<span data-ttu-id="08b4a-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="08b4a-130">DependsOn</span></span> |<span data-ttu-id="08b4a-131">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="08b4a-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="08b4a-132">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="08b4a-132">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="08b4a-133">Ensure</span><span class="sxs-lookup"><span data-stu-id="08b4a-133">Ensure</span></span> |<span data-ttu-id="08b4a-134">プロセスが存在するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="08b4a-134">Specifies whether the processes exists.</span></span> <span data-ttu-id="08b4a-135">プロセスの存在を保証するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="08b4a-135">Set this property to **Present** to ensure that the process exists.</span></span> <span data-ttu-id="08b4a-136">それ以外の場合は、**Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="08b4a-136">Otherwise, set it to **Absent**.</span></span> <span data-ttu-id="08b4a-137">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="08b4a-137">The default value is **Present**.</span></span> |
|<span data-ttu-id="08b4a-138">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="08b4a-138">PsDscRunAsCredential</span></span> |<span data-ttu-id="08b4a-139">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="08b4a-139">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="08b4a-140">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="08b4a-140">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="08b4a-141">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08b4a-141">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>