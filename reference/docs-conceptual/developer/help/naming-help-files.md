---
ms.date: 09/12/2016
ms.topic: reference
title: ヘルプ ファイルに名前を付ける
description: ヘルプ ファイルに名前を付ける
ms.openlocfilehash: b77af8f9b9510785a4198fed9da1263184a27b99
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667591"
---
# <a name="naming-help-files"></a><span data-ttu-id="a8b57-103">ヘルプ ファイルに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="a8b57-103">Naming Help Files</span></span>

<span data-ttu-id="a8b57-104">このトピックでは、 [get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) コマンドレットで検索できるように、XML ベースのヘルプファイルに名前を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8b57-104">This topic explains how to name an XML-based help file so that the [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet can find it.</span></span> <span data-ttu-id="a8b57-105">名前の要件は、コマンドの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a8b57-105">The name requirements differ for each command type.</span></span>

## <a name="cmdlet-help-files"></a><span data-ttu-id="a8b57-106">コマンドレットのヘルプファイル</span><span class="sxs-lookup"><span data-stu-id="a8b57-106">Cmdlet Help Files</span></span>

<span data-ttu-id="a8b57-107">C# コマンドレットのヘルプファイルには、コマンドレットが定義されているアセンブリの名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8b57-107">The help file for a C# cmdlet must be named for the assembly in which the cmdlet is defined.</span></span> <span data-ttu-id="a8b57-108">次のファイル名形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="a8b57-108">Use the following filename format:</span></span>

```
<AssemblyName>.dll-help.xml
```

<span data-ttu-id="a8b57-109">アセンブリが入れ子になっているモジュールの場合でも、アセンブリ名の形式が必要です。</span><span class="sxs-lookup"><span data-stu-id="a8b57-109">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="a8b57-110">たとえば、Microsoft.PowerShell.Diagnostics.dll アセンブリでは、 [Get WinEvent](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) コマンドレットが定義されています。</span><span class="sxs-lookup"><span data-stu-id="a8b57-110">For example, the [Get-WinEvent](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) cmdlet is defined in the Microsoft.PowerShell.Diagnostics.dll assembly.</span></span> <span data-ttu-id="a8b57-111">`Get-Help`コマンドレットは、 `Get-WinEvent` モジュールディレクトリ内のファイルでのみ、コマンドレットのヘルプトピックを検索し `Microsoft.PowerShell.Diagnostics.dll-help.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="a8b57-111">The `Get-Help` cmdlet looks for a help topic for the `Get-WinEvent` cmdlet only in the `Microsoft.PowerShell.Diagnostics.dll-help.xml` file in the module directory.</span></span>

## <a name="provider-help-files"></a><span data-ttu-id="a8b57-112">プロバイダーヘルプファイル</span><span class="sxs-lookup"><span data-stu-id="a8b57-112">Provider Help files</span></span>

<span data-ttu-id="a8b57-113">PowerShell プロバイダーのヘルプファイルには、プロバイダーが定義されているアセンブリの名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8b57-113">The help file for a PowerShell provider must be named for the assembly in which the provider is defined.</span></span> <span data-ttu-id="a8b57-114">次のファイル名形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="a8b57-114">Use the following filename format:</span></span>

`<AssemblyName>.dll-help.xml`

<span data-ttu-id="a8b57-115">アセンブリが入れ子になっているモジュールの場合でも、アセンブリ名の形式が必要です。</span><span class="sxs-lookup"><span data-stu-id="a8b57-115">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="a8b57-116">たとえば、証明書プロバイダーはアセンブリで定義されてい `Microsoft.PowerShell.Security.dll` ます。</span><span class="sxs-lookup"><span data-stu-id="a8b57-116">For example, the Certificate provider is defined in the `Microsoft.PowerShell.Security.dll` assembly.</span></span> <span data-ttu-id="a8b57-117">この `Get-Help` コマンドレットは、モジュールディレクトリ内のファイルでのみ、証明書プロバイダーのヘルプトピックを検索し `Microsoft.PowerShell.Security.dll-help.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="a8b57-117">The `Get-Help` cmdlet looks for a help topic for the Certificate provider only in the `Microsoft.PowerShell.Security.dll-help.xml` file in the module directory.</span></span>

## <a name="function-help-files"></a><span data-ttu-id="a8b57-118">関数のヘルプファイル</span><span class="sxs-lookup"><span data-stu-id="a8b57-118">Function Help Files</span></span>

<span data-ttu-id="a8b57-119">関数は、 [コメントベースのヘルプ](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) を使用するか、XML ヘルプファイルに記載されているドキュメントに記載されています。</span><span class="sxs-lookup"><span data-stu-id="a8b57-119">Functions can be documented by using [comment-based help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) or documented in an XML help file.</span></span> <span data-ttu-id="a8b57-120">関数が XML ファイルに記述されている場合、関数は `.ExternalHelp` 、xml ファイルに関数を関連付ける comment キーワードを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8b57-120">When the function is documented in an XML file, the function must have an `.ExternalHelp` comment keyword that associates the function with the XML file.</span></span> <span data-ttu-id="a8b57-121">それ以外の場合、 `Get-Help` コマンドレットはヘルプファイルを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="a8b57-121">Otherwise, the `Get-Help` cmdlet cannot find the help file.</span></span>

<span data-ttu-id="a8b57-122">関数のヘルプファイルの名前に関する技術的な要件はありません。</span><span class="sxs-lookup"><span data-stu-id="a8b57-122">There are no technical requirements for the name of a function help file.</span></span> <span data-ttu-id="a8b57-123">ただし、関数が定義されているスクリプトモジュールのヘルプファイルには、という名前を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a8b57-123">However, a best practice is to name the help file for the script module in which the function is defined.</span></span> <span data-ttu-id="a8b57-124">たとえば、次の関数はファイルで定義されてい `MyModule.psm1` ます。</span><span class="sxs-lookup"><span data-stu-id="a8b57-124">For example, the following function is defined in the `MyModule.psm1` file.</span></span>

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a><span data-ttu-id="a8b57-125">CIM コマンドのヘルプファイル</span><span class="sxs-lookup"><span data-stu-id="a8b57-125">CIM Command Help Files</span></span>

<span data-ttu-id="a8b57-126">Cim コマンドのヘルプファイルには、CIM コマンドが定義されている CDXML ファイルの名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8b57-126">The help file for a CIM command must be named for the CDXML file in which the CIM command is defined.</span></span> <span data-ttu-id="a8b57-127">次のファイル名形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="a8b57-127">Use the following filename format:</span></span>

`<FileName>.cdxml-help.xml`

<span data-ttu-id="a8b57-128">CIM コマンドは、モジュールに入れ子になったモジュールとして含めることができる、CDXML ファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="a8b57-128">CIM commands are defined in CDXML files that can be included in modules as nested modules.</span></span> <span data-ttu-id="a8b57-129">CIM コマンドが関数としてセッションにインポートされると、PowerShell によって関数定義に comment キーワードが追加され、この関数 `.ExternalHelp` は、cim コマンドが定義されている CDXML ファイルの名前が付けられた XML ヘルプファイルに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="a8b57-129">When the CIM command is imported into the session as a function, PowerShell adds an `.ExternalHelp` comment keyword to the function definition that associates the function with an XML help file that is named for the CDXML file in which the CIM command is defined.</span></span>

## <a name="script-workflow-help-files"></a><span data-ttu-id="a8b57-130">スクリプトワークフローのヘルプファイル</span><span class="sxs-lookup"><span data-stu-id="a8b57-130">Script Workflow Help Files</span></span>

<span data-ttu-id="a8b57-131">モジュールに含まれているスクリプトワークフローは、XML ベースのヘルプファイルに記載されています。</span><span class="sxs-lookup"><span data-stu-id="a8b57-131">Script workflows that are included in modules can be documented in XML-based help files.</span></span> <span data-ttu-id="a8b57-132">ヘルプファイルの名前に関する技術的な要件はありません。</span><span class="sxs-lookup"><span data-stu-id="a8b57-132">There are no technical requirements for the name of the help file.</span></span> <span data-ttu-id="a8b57-133">ただし、スクリプトワークフローが定義されているスクリプトモジュールのヘルプファイルには、という名前を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a8b57-133">However, a best practice is to name the help file for the script module in which the script workflow is defined.</span></span> <span data-ttu-id="a8b57-134">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a8b57-134">For example:</span></span>

`<ScriptModule>.psm1-help.xml`

<span data-ttu-id="a8b57-135">スクリプト化された他のコマンドとは異なり、スクリプトワークフローでは、 `.ExternalHelp` コメントキーワードを使用してヘルプファイルに関連付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a8b57-135">Unlike other scripted commands, script workflows do not require an `.ExternalHelp` comment keyword to associate them with a help file.</span></span> <span data-ttu-id="a8b57-136">代わりに、PowerShell は、モジュールディレクトリの UI カルチャ固有のサブディレクトリで XML ベースのヘルプファイルを検索し、すべてのファイルでスクリプトワークフローのヘルプを検索します。</span><span class="sxs-lookup"><span data-stu-id="a8b57-136">Instead, PowerShell searches the UI-Culture-specific subdirectories of the module directory for XML-based help files and looks for help for the script workflow in all the files.</span></span> <span data-ttu-id="a8b57-137">`.ExternalHelp` comment キーワードは無視されます。</span><span class="sxs-lookup"><span data-stu-id="a8b57-137">`.ExternalHelp` comment keyword are ignored.</span></span>

<span data-ttu-id="a8b57-138">`.ExternalHelp`Comment キーワードは無視されるため、 `Get-Help` コマンドレットは、モジュールに含まれている場合にのみスクリプトワークフローのヘルプを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="a8b57-138">Because the `.ExternalHelp` comment keyword is ignored, the `Get-Help` cmdlet can find help for script workflows only when they are included in modules.</span></span>
