---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-modulemanifest?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ModuleManifest
ms.openlocfilehash: 41b5ef4471ec2bef0bf4b30f8996f2e0010eceff
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209832"
---
# <span data-ttu-id="2c2eb-103">Test-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="2c2eb-103">Test-ModuleManifest</span></span>

## <span data-ttu-id="2c2eb-104">概要</span><span class="sxs-lookup"><span data-stu-id="2c2eb-104">SYNOPSIS</span></span>
<span data-ttu-id="2c2eb-105">モジュールのマニフェスト ファイルにモジュールの内容が正確に記述されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-105">Verifies that a module manifest file accurately describes the contents of a module.</span></span>

## <span data-ttu-id="2c2eb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2c2eb-106">SYNTAX</span></span>

```
Test-ModuleManifest [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="2c2eb-107">Description</span><span class="sxs-lookup"><span data-stu-id="2c2eb-107">DESCRIPTION</span></span>

<span data-ttu-id="2c2eb-108">**New-modulemanifest** コマンドレットは、モジュールマニフェスト (.psd1) ファイルに一覧表示されているファイルが、実際に指定されたパスにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-108">The **Test-ModuleManifest** cmdlet verifies that the files that are listed in the module manifest (.psd1) file are actually in the specified paths.</span></span>

<span data-ttu-id="2c2eb-109">このコマンドレットは、モジュールの作成者がマニフェスト ファイルをテストできるようにすることを目的として設計されています。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-109">This cmdlet is designed to help module authors test their manifest files.</span></span>
<span data-ttu-id="2c2eb-110">モジュールユーザーは、スクリプトやコマンドでこのコマンドレットを使用して、モジュールに依存するスクリプトを実行する前にエラーを検出することもできます。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-110">Module users can also use this cmdlet in scripts and commands to detect errors before they run scripts that depend on the module.</span></span>

<span data-ttu-id="2c2eb-111">**New-modulemanifest** は、モジュールを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-111">**Test-ModuleManifest** returns an object that represents the module.</span></span>
<span data-ttu-id="2c2eb-112">これは Get-Module が返すオブジェクトの型と同じです。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-112">This is the same type of object that Get-Module returns.</span></span>
<span data-ttu-id="2c2eb-113">マニフェストに指定された場所にいずれかのファイルが存在しない場合、不足しているファイルごとにエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-113">If any files are not in the locations specified in the manifest, the cmdlet also generates an error for each missing file.</span></span>

## <span data-ttu-id="2c2eb-114">例</span><span class="sxs-lookup"><span data-stu-id="2c2eb-114">EXAMPLES</span></span>

### <span data-ttu-id="2c2eb-115">例 1: マニフェストをテストする</span><span class="sxs-lookup"><span data-stu-id="2c2eb-115">Example 1: Test a manifest</span></span>

```powershell
test-ModuleManifest -Path "$pshome\Modules\TestModule.psd1"
```

<span data-ttu-id="2c2eb-116">このコマンドは、TestModule.psd1 モジュール マニフェストをテストします。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-116">This command tests the TestModule.psd1 module manifest.</span></span>

### <span data-ttu-id="2c2eb-117">例 2: パイプラインを使用してマニフェストをテストする</span><span class="sxs-lookup"><span data-stu-id="2c2eb-117">Example 2: Test a manifest by using the pipeline</span></span>

```powershell
"$pshome\Modules\TestModule.psd1" | test-modulemanifest
```

```Output
Test-ModuleManifest : The specified type data file 'C:\Windows\System32\Wi
ndowsPowerShell\v1.0\Modules\TestModule\TestTypes.ps1xml' could not be processed because the file was not found. Please correct the path and try again.
At line:1 char:34
+ "$pshome\Modules\TestModule.psd1" | test-modulemanifest <<<<
+ CategoryInfo          : ResourceUnavailable: (C:\Windows\System32\WindowsPowerShell\v1.0\Modules\TestModule\TestTypes.ps1xml:String) [Test-ModuleManifest], FileNotFoundException
+ FullyQualifiedErrorId : Modules_TypeDataFileNotFound,Microsoft.PowerShell.Commands.TestModuleManifestCommandName

Name              : TestModule
Path              : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\TestModule\TestModule.psd1
Description       :
Guid              : 6f0f1387-cd25-4902-b7b4-22cff6aefa7b
Version           : 1.0
ModuleBase        : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\TestModule
ModuleType        : Manifest
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {}
ExportedVariables : {}
NestedModules     : {}
```

<span data-ttu-id="2c2eb-118">このコマンドは、パイプライン演算子 (|) を使用してパス文字列を **new-modulemanifest** に送信します。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-118">This command uses a pipeline operator (|) to send a path string to **Test-ModuleManifest** .</span></span>

<span data-ttu-id="2c2eb-119">コマンド出力にはテストが失敗したことが示されています。これは、マニフェストに示されている TestTypes.ps1xml ファイルが見つからなかったためです。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-119">The command output shows that the test failed, because the TestTypes.ps1xml file, which was listed in the manifest, was not found.</span></span>

### <span data-ttu-id="2c2eb-120">例 3: モジュールマニフェストをテストする関数を記述する</span><span class="sxs-lookup"><span data-stu-id="2c2eb-120">Example 3: Write a function to test a module manifest</span></span>

```powershell
function Test-ManifestBool ($path)
```

```Output
{$a = dir $path | Test-ModuleManifest -ErrorAction SilentlyContinue; $?}
```

<span data-ttu-id="2c2eb-121">この関数は **new-modulemanifest** に似ていますが、ブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-121">This function is like **Test-ModuleManifest** , but it returns a Boolean value.</span></span>
<span data-ttu-id="2c2eb-122">関数は、マニフェストがテストに合格した場合は $True を返し、それ以外の場合は $False を返します。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-122">The function returns $True if the manifest passed the test and $False otherwise.</span></span>

<span data-ttu-id="2c2eb-123">関数は、Get-ChildItem コマンドレット alias = dir を使用して、$path 変数によって指定されたモジュールマニフェストを取得します。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-123">The function uses the Get-ChildItem cmdlet, alias = dir, to get the module manifest specified by the $path variable.</span></span>
<span data-ttu-id="2c2eb-124">このコマンドは、パイプライン演算子 (|) を使用して、ファイルオブジェクトを **new-modulemanifest** に渡します。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-124">The command uses a pipeline operator (|) to pass the file object to **Test-ModuleManifest** .</span></span>

<span data-ttu-id="2c2eb-125">**New-modulemanifest** は、 *erroraction* 共通パラメーターに SilentlyContinue の値を使用して、コマンドによって生成されるエラーの表示を抑制します。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-125">**Test-ModuleManifest** uses the *ErrorAction* common parameter with a value of SilentlyContinue to suppress the display of any errors that the command generates.</span></span>
<span data-ttu-id="2c2eb-126">また、 **PSModuleInfo** が $a 変数に返す **new-modulemanifest** オブジェクトも保存します。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-126">It also saves the **PSModuleInfo** object that **Test-ModuleManifest** returns in the $a variable.</span></span>
<span data-ttu-id="2c2eb-127">そのため、オブジェクトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-127">Therefore, the object is not displayed.</span></span>

<span data-ttu-id="2c2eb-128">次に、別のコマンドで、関数は $? の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-128">Then, in a separate command, the function displays the value of the $?</span></span>
<span data-ttu-id="2c2eb-129">自動変数。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-129">automatic variable.</span></span>
<span data-ttu-id="2c2eb-130">前のコマンドでエラーが生成されなかった場合、コマンドは $True を表示し、それ以外の場合は $False します。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-130">If the previous command generates no error, the command displays $True, and $False otherwise.</span></span>

<span data-ttu-id="2c2eb-131">この関数は、条件付きステートメントで使用できます。たとえば、 **インポートモジュール** のコマンドの前にある場合もあれば、モジュールを使用するコマンドの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-131">You can use this function in conditional statements, such as those that might precede an **Import-Module** command or a command that uses the module.</span></span>

## <span data-ttu-id="2c2eb-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2c2eb-132">PARAMETERS</span></span>

### <span data-ttu-id="2c2eb-133">-Path</span><span class="sxs-lookup"><span data-stu-id="2c2eb-133">-Path</span></span>

<span data-ttu-id="2c2eb-134">マニフェストファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-134">Specifies a path and file name for the manifest file.</span></span>
<span data-ttu-id="2c2eb-135">.Psd1 ファイル名拡張子を持つモジュールマニフェストファイルのパスと名前を入力します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-135">Enter an optional path and name of the module manifest file that has the .psd1 file name extension.</span></span>
<span data-ttu-id="2c2eb-136">既定の場所は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-136">The default location is the current directory.</span></span>
<span data-ttu-id="2c2eb-137">ワイルドカード文字はサポートされていますが、1つのモジュールマニフェストファイルに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-137">Wildcard characters are supported, but must resolve to a single module manifest file.</span></span>
<span data-ttu-id="2c2eb-138">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-138">This parameter is required.</span></span>
<span data-ttu-id="2c2eb-139">パイプを使用してパスを **new-modulemanifest** にパイプすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-139">You can also pipe a path to **Test-ModuleManifest** .</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="2c2eb-140">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2c2eb-140">CommonParameters</span></span>

<span data-ttu-id="2c2eb-141">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2c2eb-142">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2c2eb-143">入力</span><span class="sxs-lookup"><span data-stu-id="2c2eb-143">INPUTS</span></span>

### <span data-ttu-id="2c2eb-144">System.String</span><span class="sxs-lookup"><span data-stu-id="2c2eb-144">System.String</span></span>

<span data-ttu-id="2c2eb-145">パイプを使用してモジュールマニフェストへのパスをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-145">You can pipe the path to a module manifest to this cmdlet.</span></span>

## <span data-ttu-id="2c2eb-146">出力</span><span class="sxs-lookup"><span data-stu-id="2c2eb-146">OUTPUTS</span></span>

### <span data-ttu-id="2c2eb-147">PSModuleInfo (システム管理)</span><span class="sxs-lookup"><span data-stu-id="2c2eb-147">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="2c2eb-148">このコマンドレットは、モジュールを表す **PSModuleInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-148">This cmdlet returns a **PSModuleInfo** object that represents the module.</span></span>
<span data-ttu-id="2c2eb-149">このオブジェクトは、マニフェストにエラーがある場合でも返されます。</span><span class="sxs-lookup"><span data-stu-id="2c2eb-149">It returns this object even if the manifest has errors.</span></span>

## <span data-ttu-id="2c2eb-150">注</span><span class="sxs-lookup"><span data-stu-id="2c2eb-150">NOTES</span></span>

## <span data-ttu-id="2c2eb-151">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2c2eb-151">RELATED LINKS</span></span>

[<span data-ttu-id="2c2eb-152">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="2c2eb-152">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="2c2eb-153">Get-Module</span><span class="sxs-lookup"><span data-stu-id="2c2eb-153">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="2c2eb-154">Import-Module</span><span class="sxs-lookup"><span data-stu-id="2c2eb-154">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="2c2eb-155">New-Module</span><span class="sxs-lookup"><span data-stu-id="2c2eb-155">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="2c2eb-156">New-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="2c2eb-156">New-ModuleManifest</span></span>](New-ModuleManifest.md)

[<span data-ttu-id="2c2eb-157">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="2c2eb-157">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="2c2eb-158">about_Modules</span><span class="sxs-lookup"><span data-stu-id="2c2eb-158">about_Modules</span></span>](About/about_Modules.md)
