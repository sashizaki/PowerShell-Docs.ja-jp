---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-modulemanifest?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ModuleManifest
ms.openlocfilehash: c86a7253335b91011d2eb225bc53d1c5cc671aff
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602758"
---
# <span data-ttu-id="a16a3-102">Test-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="a16a3-102">Test-ModuleManifest</span></span>

## <span data-ttu-id="a16a3-103">概要</span><span class="sxs-lookup"><span data-stu-id="a16a3-103">SYNOPSIS</span></span>
<span data-ttu-id="a16a3-104">モジュールのマニフェスト ファイルにモジュールの内容が正確に記述されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a16a3-104">Verifies that a module manifest file accurately describes the contents of a module.</span></span>

## <span data-ttu-id="a16a3-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a16a3-105">SYNTAX</span></span>

```
Test-ModuleManifest [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="a16a3-106">Description</span><span class="sxs-lookup"><span data-stu-id="a16a3-106">DESCRIPTION</span></span>

<span data-ttu-id="a16a3-107">**New-modulemanifest** コマンドレットは、モジュールマニフェスト (.psd1) ファイルに一覧表示されているファイルが、実際に指定されたパスにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a16a3-107">The **Test-ModuleManifest** cmdlet verifies that the files that are listed in the module manifest (.psd1) file are actually in the specified paths.</span></span>

<span data-ttu-id="a16a3-108">このコマンドレットは、モジュールの作成者がマニフェスト ファイルをテストできるようにすることを目的として設計されています。</span><span class="sxs-lookup"><span data-stu-id="a16a3-108">This cmdlet is designed to help module authors test their manifest files.</span></span>
<span data-ttu-id="a16a3-109">モジュールユーザーは、スクリプトやコマンドでこのコマンドレットを使用して、モジュールに依存するスクリプトを実行する前にエラーを検出することもできます。</span><span class="sxs-lookup"><span data-stu-id="a16a3-109">Module users can also use this cmdlet in scripts and commands to detect errors before they run scripts that depend on the module.</span></span>

<span data-ttu-id="a16a3-110">**New-modulemanifest** は、モジュールを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a16a3-110">**Test-ModuleManifest** returns an object that represents the module.</span></span>
<span data-ttu-id="a16a3-111">これは Get-Module が返すオブジェクトの型と同じです。</span><span class="sxs-lookup"><span data-stu-id="a16a3-111">This is the same type of object that Get-Module returns.</span></span>
<span data-ttu-id="a16a3-112">マニフェストに指定された場所にいずれかのファイルが存在しない場合、不足しているファイルごとにエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a16a3-112">If any files are not in the locations specified in the manifest, the cmdlet also generates an error for each missing file.</span></span>

## <span data-ttu-id="a16a3-113">例</span><span class="sxs-lookup"><span data-stu-id="a16a3-113">EXAMPLES</span></span>

### <span data-ttu-id="a16a3-114">例 1: マニフェストをテストする</span><span class="sxs-lookup"><span data-stu-id="a16a3-114">Example 1: Test a manifest</span></span>

```powershell
test-ModuleManifest -Path "$pshome\Modules\TestModule.psd1"
```

<span data-ttu-id="a16a3-115">このコマンドは、TestModule.psd1 モジュール マニフェストをテストします。</span><span class="sxs-lookup"><span data-stu-id="a16a3-115">This command tests the TestModule.psd1 module manifest.</span></span>

### <span data-ttu-id="a16a3-116">例 2: パイプラインを使用してマニフェストをテストする</span><span class="sxs-lookup"><span data-stu-id="a16a3-116">Example 2: Test a manifest by using the pipeline</span></span>

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

<span data-ttu-id="a16a3-117">このコマンドは、パイプライン演算子 (|) を使用してパス文字列を **new-modulemanifest** に送信します。</span><span class="sxs-lookup"><span data-stu-id="a16a3-117">This command uses a pipeline operator (|) to send a path string to **Test-ModuleManifest**.</span></span>

<span data-ttu-id="a16a3-118">コマンド出力にはテストが失敗したことが示されています。これは、マニフェストに示されている TestTypes.ps1xml ファイルが見つからなかったためです。</span><span class="sxs-lookup"><span data-stu-id="a16a3-118">The command output shows that the test failed, because the TestTypes.ps1xml file, which was listed in the manifest, was not found.</span></span>

### <span data-ttu-id="a16a3-119">例 3: モジュールマニフェストをテストする関数を記述する</span><span class="sxs-lookup"><span data-stu-id="a16a3-119">Example 3: Write a function to test a module manifest</span></span>

```powershell
function Test-ManifestBool ($path)
```

```Output
{$a = dir $path | Test-ModuleManifest -ErrorAction SilentlyContinue; $?}
```

<span data-ttu-id="a16a3-120">この関数は **new-modulemanifest** に似ていますが、ブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="a16a3-120">This function is like **Test-ModuleManifest**, but it returns a Boolean value.</span></span>
<span data-ttu-id="a16a3-121">関数は、マニフェストがテストに合格した場合は $True を返し、それ以外の場合は $False を返します。</span><span class="sxs-lookup"><span data-stu-id="a16a3-121">The function returns $True if the manifest passed the test and $False otherwise.</span></span>

<span data-ttu-id="a16a3-122">関数は、Get-ChildItem コマンドレット alias = dir を使用して、$path 変数によって指定されたモジュールマニフェストを取得します。</span><span class="sxs-lookup"><span data-stu-id="a16a3-122">The function uses the Get-ChildItem cmdlet, alias = dir, to get the module manifest specified by the $path variable.</span></span>
<span data-ttu-id="a16a3-123">このコマンドは、パイプライン演算子 (|) を使用して、ファイルオブジェクトを **new-modulemanifest** に渡します。</span><span class="sxs-lookup"><span data-stu-id="a16a3-123">The command uses a pipeline operator (|) to pass the file object to **Test-ModuleManifest**.</span></span>

<span data-ttu-id="a16a3-124">**New-modulemanifest** は、 *erroraction* 共通パラメーターに SilentlyContinue の値を使用して、コマンドによって生成されるエラーの表示を抑制します。</span><span class="sxs-lookup"><span data-stu-id="a16a3-124">**Test-ModuleManifest** uses the *ErrorAction* common parameter with a value of SilentlyContinue to suppress the display of any errors that the command generates.</span></span>
<span data-ttu-id="a16a3-125">また、 **PSModuleInfo** が $a 変数に返す **new-modulemanifest** オブジェクトも保存します。</span><span class="sxs-lookup"><span data-stu-id="a16a3-125">It also saves the **PSModuleInfo** object that **Test-ModuleManifest** returns in the $a variable.</span></span>
<span data-ttu-id="a16a3-126">そのため、オブジェクトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a16a3-126">Therefore, the object is not displayed.</span></span>

<span data-ttu-id="a16a3-127">次に、別のコマンドで、関数は $? の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="a16a3-127">Then, in a separate command, the function displays the value of the $?</span></span>
<span data-ttu-id="a16a3-128">自動変数。</span><span class="sxs-lookup"><span data-stu-id="a16a3-128">automatic variable.</span></span>
<span data-ttu-id="a16a3-129">前のコマンドでエラーが生成されなかった場合、コマンドは $True を表示し、それ以外の場合は $False します。</span><span class="sxs-lookup"><span data-stu-id="a16a3-129">If the previous command generates no error, the command displays $True, and $False otherwise.</span></span>

<span data-ttu-id="a16a3-130">この関数は、条件付きステートメントで使用できます。たとえば、 **インポートモジュール** のコマンドの前にある場合もあれば、モジュールを使用するコマンドの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a16a3-130">You can use this function in conditional statements, such as those that might precede an **Import-Module** command or a command that uses the module.</span></span>

## <span data-ttu-id="a16a3-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a16a3-131">PARAMETERS</span></span>

### <span data-ttu-id="a16a3-132">-Path</span><span class="sxs-lookup"><span data-stu-id="a16a3-132">-Path</span></span>

<span data-ttu-id="a16a3-133">マニフェストファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a16a3-133">Specifies a path and file name for the manifest file.</span></span>
<span data-ttu-id="a16a3-134">.Psd1 ファイル名拡張子を持つモジュールマニフェストファイルのパスと名前を入力します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="a16a3-134">Enter an optional path and name of the module manifest file that has the .psd1 file name extension.</span></span>
<span data-ttu-id="a16a3-135">既定の場所は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="a16a3-135">The default location is the current directory.</span></span>
<span data-ttu-id="a16a3-136">ワイルドカード文字はサポートされていますが、1つのモジュールマニフェストファイルに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a16a3-136">Wildcard characters are supported, but must resolve to a single module manifest file.</span></span>
<span data-ttu-id="a16a3-137">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="a16a3-137">This parameter is required.</span></span>
<span data-ttu-id="a16a3-138">パイプを使用してパスを **new-modulemanifest** にパイプすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a16a3-138">You can also pipe a path to **Test-ModuleManifest**.</span></span>

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

### <span data-ttu-id="a16a3-139">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a16a3-139">CommonParameters</span></span>

<span data-ttu-id="a16a3-140">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a16a3-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a16a3-141">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a16a3-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a16a3-142">入力</span><span class="sxs-lookup"><span data-stu-id="a16a3-142">INPUTS</span></span>

### <span data-ttu-id="a16a3-143">System.String</span><span class="sxs-lookup"><span data-stu-id="a16a3-143">System.String</span></span>

<span data-ttu-id="a16a3-144">パイプを使用してモジュールマニフェストへのパスをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="a16a3-144">You can pipe the path to a module manifest to this cmdlet.</span></span>

## <span data-ttu-id="a16a3-145">出力</span><span class="sxs-lookup"><span data-stu-id="a16a3-145">OUTPUTS</span></span>

### <span data-ttu-id="a16a3-146">PSModuleInfo (システム管理)</span><span class="sxs-lookup"><span data-stu-id="a16a3-146">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="a16a3-147">このコマンドレットは、モジュールを表す **PSModuleInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a16a3-147">This cmdlet returns a **PSModuleInfo** object that represents the module.</span></span>
<span data-ttu-id="a16a3-148">このオブジェクトは、マニフェストにエラーがある場合でも返されます。</span><span class="sxs-lookup"><span data-stu-id="a16a3-148">It returns this object even if the manifest has errors.</span></span>

## <span data-ttu-id="a16a3-149">注</span><span class="sxs-lookup"><span data-stu-id="a16a3-149">NOTES</span></span>

## <span data-ttu-id="a16a3-150">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a16a3-150">RELATED LINKS</span></span>

[<span data-ttu-id="a16a3-151">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="a16a3-151">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="a16a3-152">Get-Module</span><span class="sxs-lookup"><span data-stu-id="a16a3-152">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="a16a3-153">Import-Module</span><span class="sxs-lookup"><span data-stu-id="a16a3-153">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="a16a3-154">New-Module</span><span class="sxs-lookup"><span data-stu-id="a16a3-154">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="a16a3-155">New-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="a16a3-155">New-ModuleManifest</span></span>](New-ModuleManifest.md)

[<span data-ttu-id="a16a3-156">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="a16a3-156">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="a16a3-157">about_Modules</span><span class="sxs-lookup"><span data-stu-id="a16a3-157">about_Modules</span></span>](About/about_Modules.md)

