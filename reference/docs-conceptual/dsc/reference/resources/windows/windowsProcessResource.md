---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WindowsProcess リソース
ms.openlocfilehash: 5c30af98bf7b99551396082630605c566a866697
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560493"
---
# <a name="dsc-windowsprocess-resource"></a><span data-ttu-id="43d9f-103">DSC WindowsProcess リソース</span><span class="sxs-lookup"><span data-stu-id="43d9f-103">DSC WindowsProcess Resource</span></span>

> <span data-ttu-id="43d9f-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="43d9f-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="43d9f-105">Windows PowerShell Desired State Configuration (DSC) の **WindowsProcess** リソースは、ターゲット ノードにプロセスを構成するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="43d9f-105">The **WindowsProcess** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to configure processes on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="43d9f-106">構文</span><span class="sxs-lookup"><span data-stu-id="43d9f-106">Syntax</span></span>

```Syntax
WindowsProcess [string] #ResourceName
{
    Arguments = [string]
    Path = [string]
    [ Credential = [PSCredential] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ StandardOutputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="43d9f-107">Properties</span><span class="sxs-lookup"><span data-stu-id="43d9f-107">Properties</span></span>

|<span data-ttu-id="43d9f-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="43d9f-108">Property</span></span> |<span data-ttu-id="43d9f-109">説明</span><span class="sxs-lookup"><span data-stu-id="43d9f-109">Description</span></span> |
|---|---|
|<span data-ttu-id="43d9f-110">引数</span><span class="sxs-lookup"><span data-stu-id="43d9f-110">Arguments</span></span> |<span data-ttu-id="43d9f-111">プロセスに渡す引数の文字列をそのまま示します。</span><span class="sxs-lookup"><span data-stu-id="43d9f-111">Indicates a string of arguments to pass to the process as-is.</span></span> <span data-ttu-id="43d9f-112">複数の引数を渡す必要がある場合は、そのすべてをこの文字列内に配置します。</span><span class="sxs-lookup"><span data-stu-id="43d9f-112">If you need to pass several arguments, put them all in this string.</span></span> |
|<span data-ttu-id="43d9f-113">Path</span><span class="sxs-lookup"><span data-stu-id="43d9f-113">Path</span></span> |<span data-ttu-id="43d9f-114">プロセスの実行可能ファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="43d9f-114">The path to the process executable.</span></span> <span data-ttu-id="43d9f-115">これが (完全修飾パスではなく) 実行可能ファイルの名前の場合、DSC リソースではその実行可能ファイルを見つけるために環境 `$env:Path` 変数が検索されます。</span><span class="sxs-lookup"><span data-stu-id="43d9f-115">If this the file name of the executable (not the fully qualified path), the DSC resource will search the environment `$env:Path` variable to find the executable file.</span></span> <span data-ttu-id="43d9f-116">このプロパティの値が完全修飾パスの場合、DSC ではそのファイルを見つけるために `$env:Path` 変数は使用されず、パスが存在しない場合はエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="43d9f-116">If the value of this property is a fully qualified path, DSC will not use the `$env:Path` variable to find the file, and will throw an error if the path does not exist.</span></span> <span data-ttu-id="43d9f-117">相対パスは指定できません。</span><span class="sxs-lookup"><span data-stu-id="43d9f-117">Relative paths are not allowed.</span></span> |
|<span data-ttu-id="43d9f-118">資格情報</span><span class="sxs-lookup"><span data-stu-id="43d9f-118">Credential</span></span> |<span data-ttu-id="43d9f-119">プロセスを開始するための資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="43d9f-119">Indicates the credentials for starting the process.</span></span> |
|<span data-ttu-id="43d9f-120">StandardErrorPath</span><span class="sxs-lookup"><span data-stu-id="43d9f-120">StandardErrorPath</span></span> |<span data-ttu-id="43d9f-121">標準エラーを書き込むディレクトリ パスを示します。</span><span class="sxs-lookup"><span data-stu-id="43d9f-121">Indicates the directory path to write the standard error.</span></span> <span data-ttu-id="43d9f-122">既存のファイルは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="43d9f-122">Any existing file there will be overwritten.</span></span> |
|<span data-ttu-id="43d9f-123">StandardInputPath</span><span class="sxs-lookup"><span data-stu-id="43d9f-123">StandardInputPath</span></span> |<span data-ttu-id="43d9f-124">標準入力の場所を示します。</span><span class="sxs-lookup"><span data-stu-id="43d9f-124">Indicates the standard input location.</span></span> |
|<span data-ttu-id="43d9f-125">StandardOutputPath</span><span class="sxs-lookup"><span data-stu-id="43d9f-125">StandardOutputPath</span></span> |<span data-ttu-id="43d9f-126">標準出力の書き込み場所を示します。</span><span class="sxs-lookup"><span data-stu-id="43d9f-126">Indicates the location to write the standard output.</span></span> <span data-ttu-id="43d9f-127">既存のファイルは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="43d9f-127">Any existing file there will be overwritten.</span></span> |
|<span data-ttu-id="43d9f-128">WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="43d9f-128">WorkingDirectory</span></span> |<span data-ttu-id="43d9f-129">プロセスの現在の作業ディレクトリとして使用される場所を示します。</span><span class="sxs-lookup"><span data-stu-id="43d9f-129">Indicates the location that will be used as the current working directory for the process.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="43d9f-130">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="43d9f-130">Common properties</span></span>

|<span data-ttu-id="43d9f-131">プロパティ</span><span class="sxs-lookup"><span data-stu-id="43d9f-131">Property</span></span> |<span data-ttu-id="43d9f-132">説明</span><span class="sxs-lookup"><span data-stu-id="43d9f-132">Description</span></span> |
|---|---|
|<span data-ttu-id="43d9f-133">DependsOn</span><span class="sxs-lookup"><span data-stu-id="43d9f-133">DependsOn</span></span> |<span data-ttu-id="43d9f-134">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="43d9f-134">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="43d9f-135">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="43d9f-135">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="43d9f-136">Ensure</span><span class="sxs-lookup"><span data-stu-id="43d9f-136">Ensure</span></span> |<span data-ttu-id="43d9f-137">プロセスが存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="43d9f-137">Indicates if the process exists.</span></span> <span data-ttu-id="43d9f-138">プロセスの存在を保証するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="43d9f-138">Set this property to **Present** to ensure that the process exists.</span></span> <span data-ttu-id="43d9f-139">それ以外の場合は、**Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="43d9f-139">Otherwise, set it to **Absent**.</span></span> <span data-ttu-id="43d9f-140">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="43d9f-140">The default value is **Present**.</span></span> |
|<span data-ttu-id="43d9f-141">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="43d9f-141">PsDscRunAsCredential</span></span> |<span data-ttu-id="43d9f-142">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="43d9f-142">Sets the credential for running the entire resource as.</span></span> |
