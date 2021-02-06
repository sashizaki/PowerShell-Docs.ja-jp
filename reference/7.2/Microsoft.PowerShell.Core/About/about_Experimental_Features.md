---
description: PowerShell の試験的機能のサポートは、試験的機能を PowerShell または PowerShell モジュールの既存の安定した機能と共存させるためのメカニズムを提供します。
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: 試験的な機能について
ms.openlocfilehash: 82f5ef9838fcbb98e71e362ad00b1ec68f9a9f67
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600809"
---
# <a name="experimental-features"></a><span data-ttu-id="a1ffa-103">試験的な機能</span><span class="sxs-lookup"><span data-stu-id="a1ffa-103">Experimental Features</span></span>

<span data-ttu-id="a1ffa-104">PowerShell の試験的機能のサポートは、試験的機能を PowerShell または PowerShell モジュールの既存の安定した機能と共存させるためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-104">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="a1ffa-105">試験的機能は、設計が未完成です。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-105">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="a1ffa-106">この機能は、ユーザーがテストしてフィードバックを提供するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-106">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="a1ffa-107">試験的機能が完成すると、設計の変更が破壊的変更になります。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-107">Once an experimental feature is finalized, the design changes become breaking changes.</span></span> <span data-ttu-id="a1ffa-108">試験的機能は、変更が破壊的になる可能性があるため、運用環境で使用することは想定されていません。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-108">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span>

<span data-ttu-id="a1ffa-109">試験的な機能は既定で無効になっており、システムのユーザーまたは管理者が明示的に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-109">Experimental features are disabled by default and need to be explicitly enabled by the user or administrator of the system.</span></span>

<span data-ttu-id="a1ffa-110">有効な試験的な機能は、 `powershell.config.json` `$PSHOME` 特定のユーザーのすべてのユーザーまたはユーザー固有の構成ファイルのファイルに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-110">Enabled experimental features are listed in the `powershell.config.json` file in `$PSHOME` for all users or the user-specific configuration file for a specific user.</span></span>

> [!NOTE]
> <span data-ttu-id="a1ffa-111">ユーザー構成ファイルで有効になっている試験的な機能は、システム構成ファイルに記載されている試験的な機能よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-111">Experimental features enabled in the user configuration file take precedence over experimental features listed in the system configuration file.</span></span>

## <a name="the-experimental-attribute"></a><span data-ttu-id="a1ffa-112">実験的属性</span><span class="sxs-lookup"><span data-stu-id="a1ffa-112">The Experimental Attribute</span></span>

<span data-ttu-id="a1ffa-113">属性を使用し `Experimental` て、実験用として一部のコードを宣言します。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-113">Use the `Experimental` attribute to declare some code as experimental.</span></span>

<span data-ttu-id="a1ffa-114">次の構文を使用して、 `Experimental` 試験的な機能の名前を提供する属性と、実験的な機能が有効になっている場合に実行するアクションを宣言します。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-114">Use the following syntax to declare the `Experimental` attribute providing the name of the experimental feature and the action to take if the experimental feature is enabled:</span></span>

```csharp
[Experimental(NameOfExperimentalFeature, ExperimentAction)]
```

<span data-ttu-id="a1ffa-115">モジュールの場合、は `NameOfExperimentalFeature` の形式に従っている必要があり `<modulename>.<experimentname>` ます。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-115">For modules, the `NameOfExperimentalFeature` must follow the form of `<modulename>.<experimentname>`.</span></span> <span data-ttu-id="a1ffa-116">`ExperimentAction`パラメーターを指定する必要があります。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-116">The `ExperimentAction` parameter must be specified and the only valid values are:</span></span>

- <span data-ttu-id="a1ffa-117">`Show` 機能が有効になっている場合に、この試験的な機能を表示することを意味します</span><span class="sxs-lookup"><span data-stu-id="a1ffa-117">`Show` means to show this experimental feature if the feature is enabled</span></span>
- <span data-ttu-id="a1ffa-118">`Hide` 機能が有効になっている場合に、この実験的な機能を非表示にすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-118">`Hide` means to hide this experimental feature if the feature is enabled</span></span>

### <a name="declaring-experimental-features-in-modules-written-in-c"></a><span data-ttu-id="a1ffa-119">C で記述されたモジュールでの試験的な特徴の宣言\#</span><span class="sxs-lookup"><span data-stu-id="a1ffa-119">Declaring Experimental Features in Modules Written in C\#</span></span>

<span data-ttu-id="a1ffa-120">試験的な機能フラグを使用するモジュールの作成者は、属性を使用して、コマンドレットを試験段階として宣言でき `Experimental` ます。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-120">Module authors who want to use the Experimental Feature flags can declare a cmdlet as experimental by using the `Experimental` attribute.</span></span>

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }
```

### <a name="declaring-experimental-features-in-modules-written-in-powershell"></a><span data-ttu-id="a1ffa-121">PowerShell で記述されたモジュールでの試験的な機能の宣言</span><span class="sxs-lookup"><span data-stu-id="a1ffa-121">Declaring Experimental Features in Modules written in PowerShell</span></span>

<span data-ttu-id="a1ffa-122">PowerShell で記述されたモジュールは、属性を使用して試験的なコマンドレットを宣言することもでき `Experimental` ます。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-122">Module written in PowerShell can also use the `Experimental` attribute to declare experimental cmdlets:</span></span>

```powershell
function Enable-SSHRemoting {
    [Experimental("MyRemoting.PSSSHRemoting", "Show")]
    [CmdletBinding()]
    param()
    ...
}
```

### <a name="mutually-exclusive-experimental-features"></a><span data-ttu-id="a1ffa-123">相互排他的な実験用の機能</span><span class="sxs-lookup"><span data-stu-id="a1ffa-123">Mutually Exclusive Experimental Features</span></span>

<span data-ttu-id="a1ffa-124">試験的な機能を既存の機能または別の試験的な機能と並行して共存させることができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-124">There are cases where an experimental feature cannot co-exist side-by-side with an existing feature or another experimental feature.</span></span>

<span data-ttu-id="a1ffa-125">たとえば、既存のコマンドレットをオーバーライドする実験的なコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-125">For example, you can have an experimental cmdlet that overrides an existing cmdlet.</span></span> <span data-ttu-id="a1ffa-126">2つのバージョンをサイドバイサイドで共存させることはできません。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-126">The two versions can't coexist side by side.</span></span> <span data-ttu-id="a1ffa-127">この設定では、 `ExperimentAction.Hide` 2 つのコマンドレットのうち1つだけを同時に有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-127">The `ExperimentAction.Hide` setting allows only one of the two cmdlets to be enabled at one time.</span></span>

<span data-ttu-id="a1ffa-128">この例では、新しい実験的なコマンドレットを作成し `Invoke-WebRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-128">In this example, we create a new experimental `Invoke-WebRequest` cmdlet.</span></span>
<span data-ttu-id="a1ffa-129">`InvokeWebRequestCommand` 試験的ではない実装が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-129">`InvokeWebRequestCommand` contains the non-experimental implementation.</span></span>
<span data-ttu-id="a1ffa-130">`InvokeWebRequestCommandV2` コマンドレットの実験用バージョンを含みます。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-130">`InvokeWebRequestCommandV2` contains the experimental version of the cmdlet.</span></span>

<span data-ttu-id="a1ffa-131">を使用すると、 `ExperimentAction.Hide` 2 つの機能のうち1つのみを同時に有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-131">The use of `ExperimentAction.Hide` will allow only one of the two features to be enabled at one time:</span></span>

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }

[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Hide)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommand : WebCmdletBase { ... }
```

<span data-ttu-id="a1ffa-132">試験的 `MyWebCmdlets.PSWebCmdletV2` な機能が有効になっている場合、既存の `InvokeWebRequestCommand` 実装は非表示になり、は `InvokeWebRequestCommandV2` の実装を提供し `Invoke-WebRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-132">When the `MyWebCmdlets.PSWebCmdletV2` experimental feature is enabled, the existing `InvokeWebRequestCommand` implementation is hidden and the `InvokeWebRequestCommandV2` provides the implementation of `Invoke-WebRequest`.</span></span>

<span data-ttu-id="a1ffa-133">これにより、ユーザーは新しいコマンドレットを試して、フィードバックを提供し、必要に応じて試験的ではないバージョンに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-133">This allows users to try out the new cmdlet and provide feedback then revert to the non-experimental version when needed.</span></span>

### <a name="experimental-parameters-in-cmdlets"></a><span data-ttu-id="a1ffa-134">コマンドレットの試験的なパラメーター</span><span class="sxs-lookup"><span data-stu-id="a1ffa-134">Experimental Parameters in Cmdlets</span></span>

<span data-ttu-id="a1ffa-135">属性は、 `Experimental` 個々のパラメーターにも適用できます。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-135">The `Experimental` attribute can also be applied to individual parameters.</span></span> <span data-ttu-id="a1ffa-136">これにより、完全に新しいコマンドレットを使用するのではなく、既存のコマンドレットの試験的なパラメーターセットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-136">This allows you to create an experimental set of parameters for an existing cmdlet rather than an entirely new cmdlet.</span></span>

<span data-ttu-id="a1ffa-137">C# の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-137">Here is an example in C#:</span></span>

```csharp
[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Show)]
[Parameter(ParameterSet = "NewCompilation")]
public CompilationParameters CompileParameters { ... }

[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Hide)]
[Parameter()]
public CodeDom CodeDom { ... }
```

<span data-ttu-id="a1ffa-138">PowerShell スクリプトの別の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-138">Here is a different example in PowerShell script:</span></span>

```powershell
param(
    [Experimental("MyModule.PSNewFeature", "Show")]
    [string] $NewName,

    [Experimental("MyModule.PSNewFeature", "Hide")]
    [string] $OldName
)
```

## <a name="checking-if-an-experimental-feature-is-enabled"></a><span data-ttu-id="a1ffa-139">試験的な機能が有効かどうかを確認しています</span><span class="sxs-lookup"><span data-stu-id="a1ffa-139">Checking if an Experimental Feature is Enabled</span></span>

<span data-ttu-id="a1ffa-140">コードでは、適切な処置を行う前に試験的な機能が有効になっているかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-140">In your code, you will need to check if your experimental feature is enabled before taking appropriate action.</span></span> <span data-ttu-id="a1ffa-141">クラスの静的メソッドを使用して試験的な機能が有効になっているかどうかを確認でき `IsEnabled()` `System.Management.Automation.ExperimentalFeature` ます。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-141">You can determine if an experimental feature is enabled using the static `IsEnabled()` method on the `System.Management.Automation.ExperimentalFeature` class.</span></span>

<span data-ttu-id="a1ffa-142">C# の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-142">Here is an example in C#:</span></span>

```csharp
if (ExperimentalFeature.IsEnabled("MyModule.MyExperimentalFeature"))
{
   // code specific to the experimental feature
}
```

<span data-ttu-id="a1ffa-143">PowerShell スクリプトの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a1ffa-143">Here is an example in PowerShell script:</span></span>

```powershell
if ([ExperimentalFeature]::IsEnabled("MyModule.MyExperimentalFeature"))
{
  # code specific to the experimental feature
}
```

## <a name="see-also"></a><span data-ttu-id="a1ffa-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1ffa-144">See also</span></span>

[<span data-ttu-id="a1ffa-145">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="a1ffa-145">Enable-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Enable-ExperimentalFeature)

[<span data-ttu-id="a1ffa-146">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="a1ffa-146">Disable-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Disable-ExperimentalFeature)

[<span data-ttu-id="a1ffa-147">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="a1ffa-147">Get-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Get-ExperimentalFeature)

