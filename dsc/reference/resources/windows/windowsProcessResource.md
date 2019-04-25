---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WindowsProcess リソース
ms.openlocfilehash: cee93ab283ded407d6e032161125aa6d6ac98827
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076771"
---
# <a name="dsc-windowsprocess-resource"></a><span data-ttu-id="515de-103">DSC WindowsProcess リソース</span><span class="sxs-lookup"><span data-stu-id="515de-103">DSC WindowsProcess Resource</span></span>

<span data-ttu-id="515de-104">_適用先:Windows PowerShell 4.0、Windows PowerShell 5.0_</span><span class="sxs-lookup"><span data-stu-id="515de-104">_Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0_</span></span>

<span data-ttu-id="515de-105">Windows PowerShell Desired State Configuration (DSC) の **WindowsProcess** リソースは、ターゲット ノードにプロセスを構成するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="515de-105">The **WindowsProcess** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to configure processes on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="515de-106">構文</span><span class="sxs-lookup"><span data-stu-id="515de-106">Syntax</span></span>

```
WindowsProcess [string] #ResourceName
{
    Arguments = [string]
    Path = [string]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ DependsOn = [string[]] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ StandardOutputPath = [string] ]
    [ WorkingDirectory = [string] ]
}
```

## <a name="properties"></a><span data-ttu-id="515de-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="515de-107">Properties</span></span>

| <span data-ttu-id="515de-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="515de-108">Property</span></span> | <span data-ttu-id="515de-109">説明</span><span class="sxs-lookup"><span data-stu-id="515de-109">Description</span></span> |
| --- | --- |
| <span data-ttu-id="515de-110">引数</span><span class="sxs-lookup"><span data-stu-id="515de-110">Arguments</span></span>| <span data-ttu-id="515de-111">プロセスに渡す引数の文字列をそのまま示します。</span><span class="sxs-lookup"><span data-stu-id="515de-111">Indicates a string of arguments to pass to the process as-is.</span></span> <span data-ttu-id="515de-112">複数の引数を渡す必要がある場合は、そのすべてをこの文字列内に配置します。</span><span class="sxs-lookup"><span data-stu-id="515de-112">If you need to pass several arguments, put them all in this string.</span></span>|
| <span data-ttu-id="515de-113">パス</span><span class="sxs-lookup"><span data-stu-id="515de-113">Path</span></span>| <span data-ttu-id="515de-114">プロセスの実行可能ファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="515de-114">The path to the process executable.</span></span> <span data-ttu-id="515de-115">これが実行可能ファイルの名前の場合 (完全修飾パスではない)、DSC リソースは環境**パス**変数 (`$env:Path`) を検索し、ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="515de-115">If this the file name of the executable (not the fully qualified path), the DSC resource will search the environment **Path** variable (`$env:Path`) to find the executable file.</span></span> <span data-ttu-id="515de-116">このプロパティの値が完全修飾パスの場合、DSC は**パス**環境変数でファイルを探すことはせず、パスが存在しない場合はエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="515de-116">If the value of this property is a fully qualified path, DSC will not use the **Path** environment variable to find the file, and will throw an error if the path does not exist.</span></span> <span data-ttu-id="515de-117">相対パスは指定できません。</span><span class="sxs-lookup"><span data-stu-id="515de-117">Relative paths are not allowed.</span></span>|
| <span data-ttu-id="515de-118">Credential</span><span class="sxs-lookup"><span data-stu-id="515de-118">Credential</span></span>| <span data-ttu-id="515de-119">プロセスを開始するための資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="515de-119">Indicates the credentials for starting the process.</span></span>|
| <span data-ttu-id="515de-120">Ensure</span><span class="sxs-lookup"><span data-stu-id="515de-120">Ensure</span></span>| <span data-ttu-id="515de-121">プロセスが存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="515de-121">Indicates if the process exists.</span></span> <span data-ttu-id="515de-122">プロセスが存在することを保証するには、このプロパティを "Present" に設定します。</span><span class="sxs-lookup"><span data-stu-id="515de-122">Set this property to "Present" to ensure that the process exists.</span></span> <span data-ttu-id="515de-123">それ以外の場合は、"Absent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="515de-123">Otherwise, set it to "Absent".</span></span> <span data-ttu-id="515de-124">既定は "Present" です。</span><span class="sxs-lookup"><span data-stu-id="515de-124">The default is "Present".</span></span>|
| <span data-ttu-id="515de-125">DependsOn</span><span class="sxs-lookup"><span data-stu-id="515de-125">DependsOn</span></span> | <span data-ttu-id="515de-126">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="515de-126">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="515de-127">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="515de-127">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"` .</span></span>|
| <span data-ttu-id="515de-128">StandardErrorPath</span><span class="sxs-lookup"><span data-stu-id="515de-128">StandardErrorPath</span></span>| <span data-ttu-id="515de-129">標準エラーを書き込むディレクトリ パスを示します。</span><span class="sxs-lookup"><span data-stu-id="515de-129">Indicates the directory path to write the standard error.</span></span> <span data-ttu-id="515de-130">既存のファイルは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="515de-130">Any existing file there will be overwritten.</span></span>|
| <span data-ttu-id="515de-131">StandardInputPath</span><span class="sxs-lookup"><span data-stu-id="515de-131">StandardInputPath</span></span>| <span data-ttu-id="515de-132">標準入力の場所を示します。</span><span class="sxs-lookup"><span data-stu-id="515de-132">Indicates the standard input location.</span></span>|
| <span data-ttu-id="515de-133">StandardOutputPath</span><span class="sxs-lookup"><span data-stu-id="515de-133">StandardOutputPath</span></span>| <span data-ttu-id="515de-134">標準出力の書き込み場所を示します。</span><span class="sxs-lookup"><span data-stu-id="515de-134">Indicates the location to write the standard output.</span></span> <span data-ttu-id="515de-135">既存のファイルは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="515de-135">Any existing file there will be overwritten.</span></span>|
| <span data-ttu-id="515de-136">WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="515de-136">WorkingDirectory</span></span>| <span data-ttu-id="515de-137">プロセスの現在の作業ディレクトリとして使用される場所を示します。</span><span class="sxs-lookup"><span data-stu-id="515de-137">Indicates the location that will be used as the current working directory for the process.</span></span>|