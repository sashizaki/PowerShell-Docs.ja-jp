---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC ProcessSet リソース
ms.openlocfilehash: d3c7383da5fd10580612527465ab621004ee7269
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="dsc-windowsprocess-resource"></a><span data-ttu-id="36fde-103">DSC WindowsProcess リソース</span><span class="sxs-lookup"><span data-stu-id="36fde-103">DSC WindowsProcess Resource</span></span>

> <span data-ttu-id="36fde-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="36fde-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="36fde-105">Windows PowerShell Desired State Configuration (DSC) の **ProcessSet** リソースは、ターゲット ノードにプロセスを構成するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="36fde-105">The **ProcessSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to configure processes on a target node.</span></span> <span data-ttu-id="36fde-106">このリソースは[複合リソース](authoringResourceComposite.md)であり、`GroupName` パラメーターに指定されているグループごとに [WindowsProcess リソース](windowsProcessResource.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="36fde-106">This resource is a [composite resource](authoringResourceComposite.md) that calls the [WindowsProcess resource](windowsProcessResource.md) for each group specified in the `GroupName` parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="36fde-107">構文</span><span class="sxs-lookup"><span data-stu-id="36fde-107">Syntax</span></span>

```
WindowsProcess [string] #ResourceName
{
    Arguments = [string]
    Path = [string]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ StandardOutputPath = [string] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="36fde-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="36fde-108">Properties</span></span>
|  <span data-ttu-id="36fde-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="36fde-109">Property</span></span>  |  <span data-ttu-id="36fde-110">説明</span><span class="sxs-lookup"><span data-stu-id="36fde-110">Description</span></span>   |
|---|---|
| <span data-ttu-id="36fde-111">引数</span><span class="sxs-lookup"><span data-stu-id="36fde-111">Arguments</span></span>| <span data-ttu-id="36fde-112">現状のままプロセスに渡す引数の文字列。</span><span class="sxs-lookup"><span data-stu-id="36fde-112">A string that contains arguments to pass to the process as-is.</span></span> <span data-ttu-id="36fde-113">複数の引数を渡す必要がある場合は、そのすべてをこの文字列内に配置します。</span><span class="sxs-lookup"><span data-stu-id="36fde-113">If you need to pass several arguments, put them all in this string.</span></span>|
| <span data-ttu-id="36fde-114">パス</span><span class="sxs-lookup"><span data-stu-id="36fde-114">Path</span></span>| <span data-ttu-id="36fde-115">プロセスの実行可能ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="36fde-115">The paths to the process executables.</span></span> <span data-ttu-id="36fde-116">実行可能ファイルの名前がある場合 (完全修飾パスではない)、DSC リソースは環境**パス**変数 (`$env:Path`) を検索し、ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="36fde-116">If these are the names of the executable files (not fully qualified paths), the DSC resource will search the environment **Path** variable (`$env:Path`) to find the files.</span></span> <span data-ttu-id="36fde-117">このプロパティの値が完全修飾パスの場合、DSC は**パス**環境変数でファイルを探すことはせず、パスが存在しない場合はエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="36fde-117">If the values of this property are fully qualified paths, DSC will not use the **Path** environment variable to find the files, and will throw an error if any of the paths do not exist.</span></span> <span data-ttu-id="36fde-118">相対パスは指定できません。</span><span class="sxs-lookup"><span data-stu-id="36fde-118">Relative paths are not allowed.</span></span>|
| <span data-ttu-id="36fde-119">Credential</span><span class="sxs-lookup"><span data-stu-id="36fde-119">Credential</span></span>| <span data-ttu-id="36fde-120">プロセスを開始するための資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36fde-120">Indicates the credentials for starting the process.</span></span>|
| <span data-ttu-id="36fde-121">Ensure</span><span class="sxs-lookup"><span data-stu-id="36fde-121">Ensure</span></span>| <span data-ttu-id="36fde-122">プロセスが存在するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="36fde-122">Specifies whether the processes exists.</span></span> <span data-ttu-id="36fde-123">プロセスが存在することを保証するには、このプロパティを "Present" に設定します。</span><span class="sxs-lookup"><span data-stu-id="36fde-123">Set this property to "Present" to ensure that the process exists.</span></span> <span data-ttu-id="36fde-124">それ以外の場合は、"Absent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="36fde-124">Otherwise, set it to "Absent".</span></span> <span data-ttu-id="36fde-125">既定は "Present" です。</span><span class="sxs-lookup"><span data-stu-id="36fde-125">The default is "Present".</span></span>|
| <span data-ttu-id="36fde-126">StandardErrorPath</span><span class="sxs-lookup"><span data-stu-id="36fde-126">StandardErrorPath</span></span>| <span data-ttu-id="36fde-127">プロセスにより標準エラーが書き込まれるパス。</span><span class="sxs-lookup"><span data-stu-id="36fde-127">The path to which the processes write standard error.</span></span> <span data-ttu-id="36fde-128">既存のファイルは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="36fde-128">Any existing file there will be overwritten.</span></span>|
| <span data-ttu-id="36fde-129">StandardInputPath</span><span class="sxs-lookup"><span data-stu-id="36fde-129">StandardInputPath</span></span>| <span data-ttu-id="36fde-130">プロセスが標準入力を受け取るとき、その発信元となるストリーム。</span><span class="sxs-lookup"><span data-stu-id="36fde-130">The stream from which the process receives standard input.</span></span>|
| <span data-ttu-id="36fde-131">StandardOutputPath</span><span class="sxs-lookup"><span data-stu-id="36fde-131">StandardOutputPath</span></span>| <span data-ttu-id="36fde-132">プロセスにより標準出力が書き込まれるファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="36fde-132">The path of the file to which the processes write standard output.</span></span> <span data-ttu-id="36fde-133">既存のファイルは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="36fde-133">Any existing file there will be overwritten.</span></span>|
| <span data-ttu-id="36fde-134">WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="36fde-134">WorkingDirectory</span></span>| <span data-ttu-id="36fde-135">プロセスの現在の作業ディレクトリとして使用されている場所。</span><span class="sxs-lookup"><span data-stu-id="36fde-135">The location used as the current working directory for the processes.</span></span>|
| <span data-ttu-id="36fde-136">DependsOn</span><span class="sxs-lookup"><span data-stu-id="36fde-136">DependsOn</span></span> | <span data-ttu-id="36fde-137">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="36fde-137">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="36fde-138">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **_ResourceType** である場合、このプロパティを使用する構文は DependsOn = "[ResourceType]ResourceName" になります。</span><span class="sxs-lookup"><span data-stu-id="36fde-138">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **_ResourceType**, the syntax for using this property is \`DependsOn = "[ResourceType]ResourceName"\`\` .</span></span>|