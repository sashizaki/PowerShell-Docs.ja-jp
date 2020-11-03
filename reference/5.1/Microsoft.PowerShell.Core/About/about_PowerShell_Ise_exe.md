---
description: PowerShell_Ise.exe コマンドラインツールの使用方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_ise_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Ise_exe
ms.openlocfilehash: c7500eb6d8586b9dca568edc4e805c577e94bec4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223339"
---
# <a name="about-powershell-iseexe"></a><span data-ttu-id="c3b58-104">PowerShell Ise.exe について</span><span class="sxs-lookup"><span data-stu-id="c3b58-104">About PowerShell Ise.exe</span></span>

## <a name="short-description"></a><span data-ttu-id="c3b58-105">概要</span><span class="sxs-lookup"><span data-stu-id="c3b58-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="c3b58-106">PowerShell_Ise.exe コマンドラインツールの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3b58-106">Explains how to use the PowerShell_Ise.exe command-line tool.</span></span>

## <a name="long-description"></a><span data-ttu-id="c3b58-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="c3b58-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="c3b58-108">PowerShell_Ise.exe は、Windows PowerShell Integrated Scripting Environment (ISE) セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="c3b58-108">PowerShell_Ise.exe starts a Windows PowerShell Integrated Scripting Environment (ISE) session.</span></span> <span data-ttu-id="c3b58-109">これは Cmd.exe と Windows PowerShell で実行できます。</span><span class="sxs-lookup"><span data-stu-id="c3b58-109">You can run it in Cmd.exe and in Windows PowerShell.</span></span>

<span data-ttu-id="c3b58-110">PowerShell_ISE.exe を実行するには、「PowerShell_ISE.exe、PowerShell_ISE、または ISE」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c3b58-110">To run PowerShell_ISE.exe, type PowerShell_ISE.exe, PowerShell_ISE, or ISE.</span></span>

## <a name="syntax"></a><span data-ttu-id="c3b58-111">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c3b58-111">SYNTAX</span></span>

```
PowerShell_Ise[.exe]
PowerShell_ISE[.exe]
ISE[.exe]
[-File]<FilePath[]> [-NoProfile] [-MTA]
-Help | ? | -? | /? Displays the syntax and describes the command-line switches.
```

## <a name="parameters"></a><span data-ttu-id="c3b58-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c3b58-112">PARAMETERS</span></span>

### <a name="-file"></a><span data-ttu-id="c3b58-113">-File</span><span class="sxs-lookup"><span data-stu-id="c3b58-113">-File</span></span>

<span data-ttu-id="c3b58-114">Windows PowerShell ISE で指定されたファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c3b58-114">Opens the specified files in Windows PowerShell ISE.</span></span> <span data-ttu-id="c3b58-115">パラメーター名 ("-File") は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c3b58-115">The parameter name ("-File") is optional.</span></span> <span data-ttu-id="c3b58-116">複数のファイルを一覧表示するには、1つのテキスト文字列を引用符で囲んで入力します。</span><span class="sxs-lookup"><span data-stu-id="c3b58-116">To list more than one file, enter one text string enclosed in quotation marks.</span></span> <span data-ttu-id="c3b58-117">文字列内でファイル名を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="c3b58-117">Use commas to separate the file names within the string.</span></span>

<span data-ttu-id="c3b58-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c3b58-118">For example:</span></span>

<span data-ttu-id="c3b58-119">PowerShell_ISE-ファイル "File1.ps1、File2.ps1、File3.xml"。</span><span class="sxs-lookup"><span data-stu-id="c3b58-119">PowerShell_ISE -File "File1.ps1,File2.ps1,File3.xml".</span></span>

<span data-ttu-id="c3b58-120">Windows PowerShell では、ファイル名の間にスペースが許可されますが、Cmd.exe などの他のプログラムでは正しく解釈されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3b58-120">Spaces between the file names are permitted in Windows PowerShell, but might not be interpreted correctly by other programs, such as Cmd.exe.</span></span>

<span data-ttu-id="c3b58-121">このパラメーターを使用すると、Windows PowerShell スクリプトファイルや XML ファイルなど、任意のテキストファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="c3b58-121">You can use this parameter to open any text file, including Windows PowerShell script files and XML files.</span></span>

### <a name="-mta"></a><span data-ttu-id="c3b58-122">-Mta</span><span class="sxs-lookup"><span data-stu-id="c3b58-122">-Mta</span></span>

<span data-ttu-id="c3b58-123">マルチスレッドアパートメントを使用して Windows PowerShell ISE を開始します。</span><span class="sxs-lookup"><span data-stu-id="c3b58-123">Starts Windows PowerShell ISE using a multi-threaded apartment.</span></span> <span data-ttu-id="c3b58-124">このパラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c3b58-124">This parameter is introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="c3b58-125">シングルスレッドアパートメント (STA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="c3b58-125">Single-threaded apartment (STA) is the default.</span></span>

### <a name="-noprofile"></a><span data-ttu-id="c3b58-126">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="c3b58-126">-NoProfile</span></span>

<span data-ttu-id="c3b58-127">では、Windows PowerShell プロファイルは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c3b58-127">Does not run Windows PowerShell profiles.</span></span> <span data-ttu-id="c3b58-128">既定では、Windows PowerShell プロファイルはすべてのセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="c3b58-128">By default, Windows PowerShell profiles are run in every session.</span></span>

<span data-ttu-id="c3b58-129">異なるプロファイルを持つシステムで実行される関数やスクリプトなど、共有コンテンツを作成する場合は、このパラメーターを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3b58-129">This parameter is recommended when you are writing shared content, such as functions and scripts that will be run on systems with different profiles.</span></span>
<span data-ttu-id="c3b58-130">詳細については、「 [about_Profiles](about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3b58-130">For more information, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="-help---"></a><span data-ttu-id="c3b58-131">-Help-?,/?</span><span class="sxs-lookup"><span data-stu-id="c3b58-131">-Help -?, /?</span></span>

<span data-ttu-id="c3b58-132">PowerShell_ISE.exe のヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="c3b58-132">Displays help for PowerShell_ISE.exe.</span></span>

## <a name="examples"></a><span data-ttu-id="c3b58-133">例</span><span class="sxs-lookup"><span data-stu-id="c3b58-133">EXAMPLES</span></span>

<span data-ttu-id="c3b58-134">これらのコマンドは Windows PowerShell ISE を開始します。</span><span class="sxs-lookup"><span data-stu-id="c3b58-134">These commands start Windows PowerShell ISE.</span></span> <span data-ttu-id="c3b58-135">コマンドは等価であり、同じ意味で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c3b58-135">The commands are equivalent and can be used interchangeably.</span></span>

```
PS C:> PowerShell_ISE.exe
PS C:> PowerShell_ISE
PS C:> ISE
```

<span data-ttu-id="c3b58-136">これらのコマンドは、Windows PowerShell ISE で Get-Profile.ps1 スクリプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="c3b58-136">These commands open the Get-Profile.ps1 script in Windows PowerShell ISE.</span></span>
<span data-ttu-id="c3b58-137">コマンドは等価であり、同じ意味で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c3b58-137">The commands are equivalent and can be used interchangeably.</span></span>

```
PS C:> PowerShell_ISE.exe -File .\Get-Profile.ps1
PS C:> ISE -File .\Get-Profile.ps1
PS C:> ISE .\Get-Profile.ps1
```

<span data-ttu-id="c3b58-138">このコマンドは Windows PowerShell ISE で Get-Backups.ps1 スクリプトと Get-BackupInstance.ps1 スクリプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="c3b58-138">This command opens the Get-Backups.ps1 and Get-BackupInstance.ps1 scripts in Windows PowerShell ISE.</span></span> <span data-ttu-id="c3b58-139">複数のファイルを開くには、コンマを使用してファイル名を区切り、ファイル名の値全体を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c3b58-139">To open more than one file, use a comma to separate the file names and enclose the entire file name value in quotation marks.</span></span>

```
PS C:> ISE -File ".\Get-Backups.ps1,Get-BackupInstance.ps1"
```

<span data-ttu-id="c3b58-140">このコマンドは、プロファイルのない Windows PowerShell ISE を開始します。</span><span class="sxs-lookup"><span data-stu-id="c3b58-140">This command starts Windows PowerShell ISE with no profiles.</span></span>

```
PS C:> ISE -NoProfile
```

<span data-ttu-id="c3b58-141">このコマンドは、PowerShell_ISE.exe のヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="c3b58-141">This command gets help for PowerShell_ISE.exe.</span></span>

```
PS C:> ISE -help
```

## <a name="see-also"></a><span data-ttu-id="c3b58-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3b58-142">SEE ALSO</span></span>

[<span data-ttu-id="c3b58-143">about_PowerShell.exe</span><span class="sxs-lookup"><span data-stu-id="c3b58-143">about_PowerShell.exe</span></span>](about_PowerShell_exe.md)

[<span data-ttu-id="c3b58-144">about_Windows_PowerShell_ISE</span><span class="sxs-lookup"><span data-stu-id="c3b58-144">about_Windows_PowerShell_ISE</span></span>](about_Windows_PowerShell_ISE.md)

[<span data-ttu-id="c3b58-145">Windows PowerShell Integrated Scripting Environment (ISE)</span><span class="sxs-lookup"><span data-stu-id="c3b58-145">Windows PowerShell Integrated Scripting Environment (ISE)</span></span>](/powershell/scripting/windows-powershell/ise/introducing-the-windows-powershell-ise)
