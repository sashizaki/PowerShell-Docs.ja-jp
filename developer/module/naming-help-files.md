---
title: ヘルプ ファイルの名前付け |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf54eac7-88c6-4108-a5f6-2f0906d1662b
caps.latest.revision: 5
ms.openlocfilehash: 06281a1260dbdc120867fce89e6d5c8dd0754b87
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856668"
---
# <a name="naming-help-files"></a><span data-ttu-id="6f412-102">ヘルプ ファイルに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="6f412-102">Naming Help Files</span></span>

<span data-ttu-id="6f412-103">このトピックでは、XML ベースのヘルプ ファイルの名前を付ける方法をについて説明できるように、 [Get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help)コマンドレットで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="6f412-103">This topic explains how to name an XML-based help file so that the [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet can find it.</span></span> <span data-ttu-id="6f412-104">名の要件は、各コマンドの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6f412-104">The name requirements differ for each command type.</span></span>
<span data-ttu-id="6f412-105">このトピックでは、XML ベースのヘルプ ファイルの名前を付ける方法をについて説明できるように、 [Get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help)コマンドレットで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="6f412-105">This topic explains how to name an XML-based help file so that the [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet can find it.</span></span> <span data-ttu-id="6f412-106">名の要件は、各コマンドの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6f412-106">The name requirements differ for each command type.</span></span>

## <a name="cmdlet-help-files"></a><span data-ttu-id="6f412-107">コマンドレットのヘルプ ファイル</span><span class="sxs-lookup"><span data-stu-id="6f412-107">Cmdlet Help Files</span></span>

<span data-ttu-id="6f412-108">ヘルプ ファイル、C#コマンドレットは、コマンドレットが定義されているアセンブリの名前必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f412-108">The help file for a C# cmdlet must be named for the assembly in which the cmdlet is defined.</span></span> <span data-ttu-id="6f412-109">次のファイル名の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f412-109">Use the following file name format:</span></span>

```
<AssemblyName>.dll-help.xml
```

<span data-ttu-id="6f412-110">アセンブリが入れ子になったモジュールの場合でも、アセンブリ名の形式が必要です。</span><span class="sxs-lookup"><span data-stu-id="6f412-110">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="6f412-111">たとえば、 [Get-winevent;PSITPro5_Diagnostic;](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent)コマンドレットが Microsoft.PowerShell.Diagnostics.dll アセンブリで定義されています。</span><span class="sxs-lookup"><span data-stu-id="6f412-111">For example, the [Get-WinEvent;PSITPro5_Diagnostic;](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) cmdlet is defined in the Microsoft.PowerShell.Diagnostics.dll assembly.</span></span> <span data-ttu-id="6f412-112">`Get-Help`コマンドレットのヘルプ トピックを検索、`Get-WinEvent`コマンドレット モジュール ディレクトリに Microsoft.PowerShell.Diagnostics.dll help.xml ファイルにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="6f412-112">The `Get-Help` cmdlet looks for a help topic for the `Get-WinEvent` cmdlet only in the Microsoft.PowerShell.Diagnostics.dll-help.xml file in the module directory.</span></span>
<span data-ttu-id="6f412-113">たとえば、 [Get-winevent;PSITPro5_Diagnostic;](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent)コマンドレットが Microsoft.PowerShell.Diagnostics.dll アセンブリで定義されています。</span><span class="sxs-lookup"><span data-stu-id="6f412-113">For example, the [Get-WinEvent;PSITPro5_Diagnostic;](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) cmdlet is defined in the Microsoft.PowerShell.Diagnostics.dll assembly.</span></span> <span data-ttu-id="6f412-114">`Get-Help`コマンドレットのヘルプ トピックを検索、`Get-WinEvent`コマンドレット モジュール ディレクトリに Microsoft.PowerShell.Diagnostics.dll help.xml ファイルにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="6f412-114">The `Get-Help` cmdlet looks for a help topic for the `Get-WinEvent` cmdlet only in the Microsoft.PowerShell.Diagnostics.dll-help.xml file in the module directory.</span></span>

## <a name="provider-help-files"></a><span data-ttu-id="6f412-115">プロバイダーのヘルプ ファイル</span><span class="sxs-lookup"><span data-stu-id="6f412-115">Provider Help files</span></span>

<span data-ttu-id="6f412-116">Windows PowerShell プロバイダーのヘルプ ファイルは、プロバイダーが定義されているアセンブリの名前をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f412-116">The help file for a Windows PowerShell provider must be named for the assembly in which the provider is defined.</span></span> <span data-ttu-id="6f412-117">次のファイル名の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f412-117">Use the following file name format:</span></span>

```
<AssemblyName>.dll-help.xml
```

<span data-ttu-id="6f412-118">アセンブリが入れ子になったモジュールの場合でも、アセンブリ名の形式が必要です。</span><span class="sxs-lookup"><span data-stu-id="6f412-118">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="6f412-119">たとえば、証明書プロバイダーは、Microsoft.PowerShell.Security.dll アセンブリで定義されます。</span><span class="sxs-lookup"><span data-stu-id="6f412-119">For example, the Certificate provider is defined in the Microsoft.PowerShell.Security.dll assembly.</span></span> <span data-ttu-id="6f412-120">`Get-Help`コマンドレットはモジュール ディレクトリに Microsoft.PowerShell.Security.dll help.xml ファイルでのみ証明書プロバイダーのヘルプ トピックを検索します。</span><span class="sxs-lookup"><span data-stu-id="6f412-120">The `Get-Help` cmdlet looks for a help topic for the Certificate provider only in the Microsoft.PowerShell.Security.dll-help.xml file in the module directory.</span></span>

## <a name="function-help-files"></a><span data-ttu-id="6f412-121">関数のヘルプ ファイル</span><span class="sxs-lookup"><span data-stu-id="6f412-121">Function Help Files</span></span>

<span data-ttu-id="6f412-122">使用して関数を記述できます[コメント ベースのヘルプ](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)や XML のヘルプ ファイルに記載されています。</span><span class="sxs-lookup"><span data-stu-id="6f412-122">Functions can be documented by using [comment-based help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) or documented in an XML help file.</span></span> <span data-ttu-id="6f412-123">関数が必要、関数が XML ファイルに記載されているときに、`.ExternalHelp`コメントを XML ファイルを使用して、関数を関連付けるキーワード。</span><span class="sxs-lookup"><span data-stu-id="6f412-123">When the function is documented in an XML file, the function must have an `.ExternalHelp` comment keyword that associates the function with the XML file.</span></span> <span data-ttu-id="6f412-124">それ以外の場合、`Get-Help`コマンドレットは、ヘルプ ファイルを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="6f412-124">Otherwise, the `Get-Help` cmdlet cannot find the help file.</span></span>
<span data-ttu-id="6f412-125">使用して関数を記述できます[コメント ベースのヘルプ](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)や XML のヘルプ ファイルに記載されています。</span><span class="sxs-lookup"><span data-stu-id="6f412-125">Functions can be documented by using [comment-based help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) or documented in an XML help file.</span></span> <span data-ttu-id="6f412-126">関数が必要、関数が XML ファイルに記載されているときに、`.ExternalHelp`コメントを XML ファイルを使用して、関数を関連付けるキーワード。</span><span class="sxs-lookup"><span data-stu-id="6f412-126">When the function is documented in an XML file, the function must have an `.ExternalHelp` comment keyword that associates the function with the XML file.</span></span> <span data-ttu-id="6f412-127">それ以外の場合、`Get-Help`コマンドレットは、ヘルプ ファイルを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="6f412-127">Otherwise, the `Get-Help` cmdlet cannot find the help file.</span></span>

<span data-ttu-id="6f412-128">関数のヘルプ ファイルの名前の技術的な要件はありません。</span><span class="sxs-lookup"><span data-stu-id="6f412-128">There are no technical requirements for the name of a function help file.</span></span> <span data-ttu-id="6f412-129">ただし、関数が定義されている、スクリプト モジュールのヘルプ ファイルの名前をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6f412-129">However, a best practice is to name the help file for the script module in which the function is defined.</span></span> <span data-ttu-id="6f412-130">たとえば、次の関数は、MyModule.psm1 ファイルで定義されます。</span><span class="sxs-lookup"><span data-stu-id="6f412-130">For example, the following function is defined in the MyModule.psm1 file.</span></span>

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a><span data-ttu-id="6f412-131">CIM コマンドのヘルプ ファイル</span><span class="sxs-lookup"><span data-stu-id="6f412-131">CIM Command Help Files</span></span>

<span data-ttu-id="6f412-132">CIM コマンドのヘルプ ファイルは、CIM コマンドが定義されている CDXML ファイルの名前をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f412-132">The help file for a CIM command must be named for the CDXML file in which the CIM command is defined.</span></span> <span data-ttu-id="6f412-133">次のファイル名の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f412-133">Use the following file name format:</span></span>

```
<FileName>.cdxml-help.xml
```

<span data-ttu-id="6f412-134">CIM コマンドは、モジュールは、入れ子になったモジュールに含まれる CDXML ファイルで定義されます。</span><span class="sxs-lookup"><span data-stu-id="6f412-134">CIM commands are defined in CDXML files that can be included in modules as nested modules.</span></span> <span data-ttu-id="6f412-135">Windows PowerShell を追加、CIM コマンドを関数としてセッションにインポートするとき、`.ExternalHelp`コメント ファイルを XML ヘルプ、関数に関連付けている関数の定義のキーワードが、CIM コマンドが定義されている CDXML ファイルの名前が付け。</span><span class="sxs-lookup"><span data-stu-id="6f412-135">When the CIM command is imported into the session as a function, Windows PowerShell adds an `.ExternalHelp` comment keyword to the function definition that associates the function with an XML help file that is named for the CDXML file in which the CIM command is defined.</span></span>

## <a name="script-workflow-help-files"></a><span data-ttu-id="6f412-136">スクリプト ワークフローのヘルプ ファイル</span><span class="sxs-lookup"><span data-stu-id="6f412-136">Script Workflow Help Files</span></span>

<span data-ttu-id="6f412-137">モジュールに含まれているスクリプト ワークフローは、XML ベースのヘルプ ファイルに文書化することができます。</span><span class="sxs-lookup"><span data-stu-id="6f412-137">Script workflows that are included in modules can be documented in XML-based help files.</span></span> <span data-ttu-id="6f412-138">ヘルプ ファイルの名前の技術的な要件はありません。</span><span class="sxs-lookup"><span data-stu-id="6f412-138">There are no technical requirements for the name of the help file.</span></span> <span data-ttu-id="6f412-139">ただし、スクリプト ワークフローが定義されている、スクリプト モジュールのヘルプ ファイルの名前をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6f412-139">However, a best practice is to name the help file for the script module in which the script workflow is defined.</span></span> <span data-ttu-id="6f412-140">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6f412-140">For example:</span></span>

```
<ScriptModule>.psm1-help.xml
```

<span data-ttu-id="6f412-141">スクリプト ワークフローは必要としない、他のスクリプト化されたコマンドとは異なり、`.ExternalHelp`にヘルプ ファイルに関連付けるキーワードをコメントします。</span><span class="sxs-lookup"><span data-stu-id="6f412-141">Unlike other scripted commands, script workflows do not require an `.ExternalHelp` comment keyword to associate them with a help file.</span></span> <span data-ttu-id="6f412-142">代わりに、Windows PowerShell では、XML ベースのヘルプ ファイルをモジュール ディレクトリの UI カルチャ固有のサブディレクトリを検索し、すべてのファイル、スクリプト ワークフローのヘルプを検索します。</span><span class="sxs-lookup"><span data-stu-id="6f412-142">Instead, Windows PowerShell searches the UI-Culture-specific subdirectories of the module directory for XML-based help files and looks for help for the script workflow in all the files.</span></span> <span data-ttu-id="6f412-143">`.ExternalHelp` コメントのキーワードは無視されます。</span><span class="sxs-lookup"><span data-stu-id="6f412-143">`.ExternalHelp` comment keyword are ignored.</span></span>

<span data-ttu-id="6f412-144">`.ExternalHelp`コメント キーワードは無視されます、`Get-Help`コマンドレットは、モジュールに含まれる場合にのみに、スクリプト ワークフローのヘルプを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="6f412-144">Because the `.ExternalHelp` comment keyword is ignored, the `Get-Help` cmdlet can find help for script workflows only when they are included in modules.</span></span>