---
description: PowerShell の試験的機能のサポートは、試験的機能を PowerShell または PowerShell モジュールの既存の安定した機能と共存させるためのメカニズムを提供します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: 試験的な機能について
ms.openlocfilehash: 663b8bbd8659b972004499e0c8a247818b8ef311
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221672"
---
# <a name="experimental-features"></a><span data-ttu-id="3dcb2-104">試験的な機能</span><span class="sxs-lookup"><span data-stu-id="3dcb2-104">Experimental Features</span></span>

<span data-ttu-id="3dcb2-105">PowerShell の試験的機能のサポートは、試験的機能を PowerShell または PowerShell モジュールの既存の安定した機能と共存させるためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-105">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="3dcb2-106">試験的機能は、設計が未完成です。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-106">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="3dcb2-107">この機能は、ユーザーがテストしてフィードバックを提供するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-107">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="3dcb2-108">試験的機能が完成すると、設計の変更が破壊的変更になります。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-108">Once an experimental feature is finalized, the design changes become breaking changes.</span></span> <span data-ttu-id="3dcb2-109">試験的機能は、変更が破壊的になる可能性があるため、運用環境で使用することは想定されていません。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-109">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span>

<span data-ttu-id="3dcb2-110">試験的な機能は既定で無効になっており、システムのユーザーまたは管理者が明示的に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-110">Experimental features are disabled by default and need to be explicitly enabled by the user or administrator of the system.</span></span>

<span data-ttu-id="3dcb2-111">有効な試験的な機能は、 `powershell.config.json` `$PSHOME` 特定のユーザーのすべてのユーザーまたはユーザー固有の構成ファイルのファイルに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-111">Enabled experimental features are listed in the `powershell.config.json` file in `$PSHOME` for all users or the user-specific configuration file for a specific user.</span></span>

> [!NOTE]
> <span data-ttu-id="3dcb2-112">ユーザー構成ファイルで有効になっている試験的な機能は、システム構成ファイルに記載されている試験的な機能よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-112">Experimental features enabled in the user configuration file take precedence over experimental features listed in the system configuration file.</span></span>

## <a name="the-experimental-attribute"></a><span data-ttu-id="3dcb2-113">実験的属性</span><span class="sxs-lookup"><span data-stu-id="3dcb2-113">The Experimental Attribute</span></span>

<span data-ttu-id="3dcb2-114">属性を使用し `Experimental` て、実験用として一部のコードを宣言します。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-114">Use the `Experimental` attribute to declare some code as experimental.</span></span>

<span data-ttu-id="3dcb2-115">次の構文を使用して、 `Experimental` 試験的な機能の名前を提供する属性と、実験的な機能が有効になっている場合に実行するアクションを宣言します。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-115">Use the following syntax to declare the `Experimental` attribute providing the name of the experimental feature and the action to take if the experimental feature is enabled:</span></span>

```csharp
[Experimental(NameOfExperimentalFeature, ExperimentAction)]
```

<span data-ttu-id="3dcb2-116">モジュールの場合、は `NameOfExperimentalFeature` の形式に従っている必要があり `<modulename>.<experimentname>` ます。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-116">For modules, the `NameOfExperimentalFeature` must follow the form of `<modulename>.<experimentname>`.</span></span> <span data-ttu-id="3dcb2-117">`ExperimentAction`パラメーターを指定する必要があります。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-117">The `ExperimentAction` parameter must be specified and the only valid values are:</span></span>

- <span data-ttu-id="3dcb2-118">`Show` 機能が有効になっている場合に、この試験的な機能を表示することを意味します</span><span class="sxs-lookup"><span data-stu-id="3dcb2-118">`Show` means to show this experimental feature if the feature is enabled</span></span>
- <span data-ttu-id="3dcb2-119">`Hide` 機能が有効になっている場合に、この実験的な機能を非表示にすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-119">`Hide` means to hide this experimental feature if the feature is enabled</span></span>

### <a name="declaring-experimental-features-in-modules-written-in-c"></a><span data-ttu-id="3dcb2-120">C で記述されたモジュールでの試験的な特徴の宣言\#</span><span class="sxs-lookup"><span data-stu-id="3dcb2-120">Declaring Experimental Features in Modules Written in C\#</span></span>

<span data-ttu-id="3dcb2-121">試験的な機能フラグを使用するモジュールの作成者は、属性を使用して、コマンドレットを試験段階として宣言でき `Experimental` ます。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-121">Module authors who want to use the Experimental Feature flags can declare a cmdlet as experimental by using the `Experimental` attribute.</span></span>

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }
```

### <a name="declaring-experimental-features-in-modules-written-in-powershell"></a><span data-ttu-id="3dcb2-122">PowerShell で記述されたモジュールでの試験的な機能の宣言</span><span class="sxs-lookup"><span data-stu-id="3dcb2-122">Declaring Experimental Features in Modules written in PowerShell</span></span>

<span data-ttu-id="3dcb2-123">PowerShell で記述されたモジュールは、属性を使用して試験的なコマンドレットを宣言することもでき `Experimental` ます。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-123">Module written in PowerShell can also use the `Experimental` attribute to declare experimental cmdlets:</span></span>

```powershell
function Enable-SSHRemoting {
    [Experimental("MyRemoting.PSSSHRemoting", "Show")]
    [CmdletBinding()]
    param()
    ...
}
```

### <a name="mutually-exclusive-experimental-features"></a><span data-ttu-id="3dcb2-124">相互排他的な実験用の機能</span><span class="sxs-lookup"><span data-stu-id="3dcb2-124">Mutually Exclusive Experimental Features</span></span>

<span data-ttu-id="3dcb2-125">試験的な機能を既存の機能または別の試験的な機能と並行して共存させることができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-125">There are cases where an experimental feature cannot co-exist side-by-side with an existing feature or another experimental feature.</span></span>

<span data-ttu-id="3dcb2-126">たとえば、既存のコマンドレットをオーバーライドする実験的なコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-126">For example, you can have an experimental cmdlet that overrides an existing cmdlet.</span></span> <span data-ttu-id="3dcb2-127">2つのバージョンをサイドバイサイドで共存させることはできません。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-127">The two versions can't coexist side by side.</span></span> <span data-ttu-id="3dcb2-128">この設定では、 `ExperimentAction.Hide` 2 つのコマンドレットのうち1つだけを同時に有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-128">The `ExperimentAction.Hide` setting allows only one of the two cmdlets to be enabled at one time.</span></span>

<span data-ttu-id="3dcb2-129">この例では、新しい実験的なコマンドレットを作成し `Invoke-WebRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-129">In this example, we create a new experimental `Invoke-WebRequest` cmdlet.</span></span>
<span data-ttu-id="3dcb2-130">`InvokeWebRequestCommand` 試験的ではない実装が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-130">`InvokeWebRequestCommand` contains the non-experimental implementation.</span></span>
<span data-ttu-id="3dcb2-131">`InvokeWebRequestCommandV2` コマンドレットの実験用バージョンを含みます。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-131">`InvokeWebRequestCommandV2` contains the experimental version of the cmdlet.</span></span>

<span data-ttu-id="3dcb2-132">を使用すると、 `ExperimentAction.Hide` 2 つの機能のうち1つのみを同時に有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-132">The use of `ExperimentAction.Hide` will allow only one of the two features to be enabled at one time:</span></span>

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }

[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Hide)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommand : WebCmdletBase { ... }
```

<span data-ttu-id="3dcb2-133">試験的 `MyWebCmdlets.PSWebCmdletV2` な機能が有効になっている場合、既存の `InvokeWebRequestCommand` 実装は非表示になり、は `InvokeWebRequestCommandV2` の実装を提供し `Invoke-WebRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-133">When the `MyWebCmdlets.PSWebCmdletV2` experimental feature is enabled, the existing `InvokeWebRequestCommand` implementation is hidden and the `InvokeWebRequestCommandV2` provides the implementation of `Invoke-WebRequest`.</span></span>

<span data-ttu-id="3dcb2-134">これにより、ユーザーは新しいコマンドレットを試して、フィードバックを提供し、必要に応じて試験的ではないバージョンに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-134">This allows users to try out the new cmdlet and provide feedback then revert to the non-experimental version when needed.</span></span>

### <a name="experimental-parameters-in-cmdlets"></a><span data-ttu-id="3dcb2-135">コマンドレットの試験的なパラメーター</span><span class="sxs-lookup"><span data-stu-id="3dcb2-135">Experimental Parameters in Cmdlets</span></span>

<span data-ttu-id="3dcb2-136">属性は、 `Experimental` 個々のパラメーターにも適用できます。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-136">The `Experimental` attribute can also be applied to individual parameters.</span></span> <span data-ttu-id="3dcb2-137">これにより、完全に新しいコマンドレットを使用するのではなく、既存のコマンドレットの試験的なパラメーターセットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-137">This allows you to create an experimental set of parameters for an existing cmdlet rather than an entirely new cmdlet.</span></span>

<span data-ttu-id="3dcb2-138">C# の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-138">Here is an example in C#:</span></span>

```csharp
[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Show)]
[Parameter(ParameterSet = "NewCompilation")]
public CompilationParameters CompileParameters { ... }

[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Hide)]
[Parameter()]
public CodeDom CodeDom { ... }
```

<span data-ttu-id="3dcb2-139">PowerShell スクリプトの別の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-139">Here is a different example in PowerShell script:</span></span>

```powershell
param(
    [Experimental("MyModule.PSNewFeature", "Show")]
    [string] $NewName,

    [Experimental("MyModule.PSNewFeature", "Hide")]
    [string] $OldName
)
```

## <a name="checking-if-an-experimental-feature-is-enabled"></a><span data-ttu-id="3dcb2-140">試験的な機能が有効かどうかを確認しています</span><span class="sxs-lookup"><span data-stu-id="3dcb2-140">Checking if an Experimental Feature is Enabled</span></span>

<span data-ttu-id="3dcb2-141">コードでは、適切な処置を行う前に試験的な機能が有効になっているかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-141">In your code, you will need to check if your experimental feature is enabled before taking appropriate action.</span></span> <span data-ttu-id="3dcb2-142">クラスの静的メソッドを使用して試験的な機能が有効になっているかどうかを確認でき `IsEnabled()` `System.Management.Automation.ExperimentalFeature` ます。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-142">You can determine if an experimental feature is enabled using the static `IsEnabled()` method on the `System.Management.Automation.ExperimentalFeature` class.</span></span>

<span data-ttu-id="3dcb2-143">C# の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-143">Here is an example in C#:</span></span>

```csharp
if (ExperimentalFeature.IsEnabled("MyModule.MyExperimentalFeature"))
{
   // code specific to the experimental feature
}
```

<span data-ttu-id="3dcb2-144">PowerShell スクリプトの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3dcb2-144">Here is an example in PowerShell script:</span></span>

```powershell
if ([ExperimentalFeature]::IsEnabled("MyModule.MyExperimentalFeature"))
{
  # code specific to the experimental feature
}
```

## <a name="see-also"></a><span data-ttu-id="3dcb2-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="3dcb2-145">See also</span></span>

[<span data-ttu-id="3dcb2-146">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="3dcb2-146">Enable-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Enable-ExperimentalFeature)

[<span data-ttu-id="3dcb2-147">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="3dcb2-147">Disable-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Disable-ExperimentalFeature)

[<span data-ttu-id="3dcb2-148">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="3dcb2-148">Get-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Get-ExperimentalFeature)
