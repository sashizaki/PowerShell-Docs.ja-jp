---
title: ヘルプファイルの名前付け |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf54eac7-88c6-4108-a5f6-2f0906d1662b
caps.latest.revision: 5
ms.openlocfilehash: f65a90023df88fceafae1d1875ddf46b9088e2b8
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367011"
---
# <a name="naming-help-files"></a><span data-ttu-id="b16e5-102">ヘルプ ファイルに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="b16e5-102">Naming Help Files</span></span>

<span data-ttu-id="b16e5-103">このトピックでは、 [get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help)コマンドレットで検索できるように、XML ベースのヘルプファイルに名前を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b16e5-103">This topic explains how to name an XML-based help file so that the [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet can find it.</span></span> <span data-ttu-id="b16e5-104">名前の要件は、コマンドの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b16e5-104">The name requirements differ for each command type.</span></span>

## <a name="cmdlet-help-files"></a><span data-ttu-id="b16e5-105">コマンドレットのヘルプファイル</span><span class="sxs-lookup"><span data-stu-id="b16e5-105">Cmdlet Help Files</span></span>

<span data-ttu-id="b16e5-106">コマンドレットのC#ヘルプファイルには、コマンドレットが定義されているアセンブリの名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="b16e5-106">The help file for a C# cmdlet must be named for the assembly in which the cmdlet is defined.</span></span> <span data-ttu-id="b16e5-107">次のファイル名の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="b16e5-107">Use the following file name format:</span></span>

```
<AssemblyName>.dll-help.xml
```

<span data-ttu-id="b16e5-108">アセンブリが入れ子になっているモジュールの場合でも、アセンブリ名の形式が必要です。</span><span class="sxs-lookup"><span data-stu-id="b16e5-108">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="b16e5-109">たとえば、 [Get-WinEvent;PSITPro5_Diagnostic;](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent)コマンドレットは、Microsoft... .dll アセンブリで定義されています。</span><span class="sxs-lookup"><span data-stu-id="b16e5-109">For example, the [Get-WinEvent;PSITPro5_Diagnostic;](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) cmdlet is defined in the Microsoft.PowerShell.Diagnostics.dll assembly.</span></span> <span data-ttu-id="b16e5-110">@No__t-0 コマンドレットは、モジュールディレクトリ内の dll-help ファイルでのみ `Get-WinEvent` コマンドレットのヘルプトピックを検索します。</span><span class="sxs-lookup"><span data-stu-id="b16e5-110">The `Get-Help` cmdlet looks for a help topic for the `Get-WinEvent` cmdlet only in the Microsoft.PowerShell.Diagnostics.dll-help.xml file in the module directory.</span></span>

## <a name="provider-help-files"></a><span data-ttu-id="b16e5-111">プロバイダーヘルプファイル</span><span class="sxs-lookup"><span data-stu-id="b16e5-111">Provider Help files</span></span>

<span data-ttu-id="b16e5-112">Windows PowerShell プロバイダーのヘルプファイルには、プロバイダーが定義されているアセンブリの名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="b16e5-112">The help file for a Windows PowerShell provider must be named for the assembly in which the provider is defined.</span></span> <span data-ttu-id="b16e5-113">次のファイル名の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="b16e5-113">Use the following file name format:</span></span>

```
<AssemblyName>.dll-help.xml
```

<span data-ttu-id="b16e5-114">アセンブリが入れ子になっているモジュールの場合でも、アセンブリ名の形式が必要です。</span><span class="sxs-lookup"><span data-stu-id="b16e5-114">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="b16e5-115">たとえば、証明書プロバイダーは、Microsoft の .dll アセンブリで定義されています。</span><span class="sxs-lookup"><span data-stu-id="b16e5-115">For example, the Certificate provider is defined in the Microsoft.PowerShell.Security.dll assembly.</span></span> <span data-ttu-id="b16e5-116">@No__t-0 コマンドレットは、モジュールディレクトリ内の dll-help ファイルでのみ、証明書プロバイダーのヘルプトピックを検索します。</span><span class="sxs-lookup"><span data-stu-id="b16e5-116">The `Get-Help` cmdlet looks for a help topic for the Certificate provider only in the Microsoft.PowerShell.Security.dll-help.xml file in the module directory.</span></span>

## <a name="function-help-files"></a><span data-ttu-id="b16e5-117">関数のヘルプファイル</span><span class="sxs-lookup"><span data-stu-id="b16e5-117">Function Help Files</span></span>

<span data-ttu-id="b16e5-118">関数は、[コメントベースのヘルプ](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)を使用するか、XML ヘルプファイルに記載されているドキュメントに記載されています。</span><span class="sxs-lookup"><span data-stu-id="b16e5-118">Functions can be documented by using [comment-based help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) or documented in an XML help file.</span></span> <span data-ttu-id="b16e5-119">関数が XML ファイルに記述されている場合、関数には、XML ファイルに関数を関連付ける @no__t 0 comment キーワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="b16e5-119">When the function is documented in an XML file, the function must have an `.ExternalHelp` comment keyword that associates the function with the XML file.</span></span> <span data-ttu-id="b16e5-120">それ以外の場合、@no__t 0 のコマンドレットはヘルプファイルを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="b16e5-120">Otherwise, the `Get-Help` cmdlet cannot find the help file.</span></span>

<span data-ttu-id="b16e5-121">関数のヘルプファイルの名前に関する技術的な要件はありません。</span><span class="sxs-lookup"><span data-stu-id="b16e5-121">There are no technical requirements for the name of a function help file.</span></span> <span data-ttu-id="b16e5-122">ただし、関数が定義されているスクリプトモジュールのヘルプファイルには、という名前を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b16e5-122">However, a best practice is to name the help file for the script module in which the function is defined.</span></span> <span data-ttu-id="b16e5-123">たとえば、次の関数は、hbase-runner.psm1 ファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="b16e5-123">For example, the following function is defined in the MyModule.psm1 file.</span></span>

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a><span data-ttu-id="b16e5-124">CIM コマンドのヘルプファイル</span><span class="sxs-lookup"><span data-stu-id="b16e5-124">CIM Command Help Files</span></span>

<span data-ttu-id="b16e5-125">Cim コマンドのヘルプファイルには、CIM コマンドが定義されている CDXML ファイルの名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="b16e5-125">The help file for a CIM command must be named for the CDXML file in which the CIM command is defined.</span></span> <span data-ttu-id="b16e5-126">次のファイル名の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="b16e5-126">Use the following file name format:</span></span>

```
<FileName>.cdxml-help.xml
```

<span data-ttu-id="b16e5-127">CIM コマンドは、モジュールに入れ子になったモジュールとして含めることができる、CDXML ファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="b16e5-127">CIM commands are defined in CDXML files that can be included in modules as nested modules.</span></span> <span data-ttu-id="b16e5-128">CIM コマンドが関数としてセッションにインポートされると、Windows PowerShell は、関数定義に @no__t 0 comment キーワードを追加します。この関数は、CIM コマンドが定義されている CDXML ファイルの名前が付けられている XML ヘルプファイルに関数を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="b16e5-128">When the CIM command is imported into the session as a function, Windows PowerShell adds an `.ExternalHelp` comment keyword to the function definition that associates the function with an XML help file that is named for the CDXML file in which the CIM command is defined.</span></span>

## <a name="script-workflow-help-files"></a><span data-ttu-id="b16e5-129">スクリプトワークフローのヘルプファイル</span><span class="sxs-lookup"><span data-stu-id="b16e5-129">Script Workflow Help Files</span></span>

<span data-ttu-id="b16e5-130">モジュールに含まれているスクリプトワークフローは、XML ベースのヘルプファイルに記載されています。</span><span class="sxs-lookup"><span data-stu-id="b16e5-130">Script workflows that are included in modules can be documented in XML-based help files.</span></span> <span data-ttu-id="b16e5-131">ヘルプファイルの名前に関する技術的な要件はありません。</span><span class="sxs-lookup"><span data-stu-id="b16e5-131">There are no technical requirements for the name of the help file.</span></span> <span data-ttu-id="b16e5-132">ただし、スクリプトワークフローが定義されているスクリプトモジュールのヘルプファイルには、という名前を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b16e5-132">However, a best practice is to name the help file for the script module in which the script workflow is defined.</span></span> <span data-ttu-id="b16e5-133">たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b16e5-133">For example:</span></span>

```
<ScriptModule>.psm1-help.xml
```

<span data-ttu-id="b16e5-134">スクリプト化された他のコマンドとは異なり、スクリプトワークフローには、ヘルプファイルに関連付けるための @no__t 0 コメントキーワードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b16e5-134">Unlike other scripted commands, script workflows do not require an `.ExternalHelp` comment keyword to associate them with a help file.</span></span> <span data-ttu-id="b16e5-135">代わりに、Windows PowerShell は、モジュールディレクトリの UI カルチャ固有のサブディレクトリで XML ベースのヘルプファイルを検索し、すべてのファイルでスクリプトワークフローのヘルプを検索します。</span><span class="sxs-lookup"><span data-stu-id="b16e5-135">Instead, Windows PowerShell searches the UI-Culture-specific subdirectories of the module directory for XML-based help files and looks for help for the script workflow in all the files.</span></span> <span data-ttu-id="b16e5-136">`.ExternalHelp` コメントキーワードは無視されます。</span><span class="sxs-lookup"><span data-stu-id="b16e5-136">`.ExternalHelp` comment keyword are ignored.</span></span>

<span data-ttu-id="b16e5-137">@No__t-0 comment キーワードは無視されるため、`Get-Help` コマンドレットは、モジュールに含まれている場合にのみスクリプトワークフローのヘルプを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="b16e5-137">Because the `.ExternalHelp` comment keyword is ignored, the `Get-Help` cmdlet can find help for script workflows only when they are included in modules.</span></span>