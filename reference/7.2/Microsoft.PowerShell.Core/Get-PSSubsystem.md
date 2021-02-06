---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 10/15/2020
schema: 2.0.0
ms.openlocfilehash: 5cb8ddbd06f8b7fdbadae0b7c738e26a68ff5c48
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602030"
---
# <span data-ttu-id="7b21c-101">Get-PSSubsystem</span><span class="sxs-lookup"><span data-stu-id="7b21c-101">Get-PSSubsystem</span></span>

## <span data-ttu-id="7b21c-102">概要</span><span class="sxs-lookup"><span data-stu-id="7b21c-102">SYNOPSIS</span></span>
<span data-ttu-id="7b21c-103">PowerShell に登録されているサブシステムに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="7b21c-103">Retrieves information about the subsystems registered in PowerShell.</span></span>

## <span data-ttu-id="7b21c-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7b21c-104">SYNTAX</span></span>

### <span data-ttu-id="7b21c-105">GetAllSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="7b21c-105">GetAllSet (Default)</span></span>

```
Get-PSSubsystem [<CommonParameters>]
```

### <span data-ttu-id="7b21c-106">GetByKindSet</span><span class="sxs-lookup"><span data-stu-id="7b21c-106">GetByKindSet</span></span>

```
Get-PSSubsystem -Kind <SubsystemKind> [<CommonParameters>]
```

### <span data-ttu-id="7b21c-107">GetByTypeSet</span><span class="sxs-lookup"><span data-stu-id="7b21c-107">GetByTypeSet</span></span>

```
Get-PSSubsystem -SubsystemType <Type> [<CommonParameters>]
```

## <span data-ttu-id="7b21c-108">Description</span><span class="sxs-lookup"><span data-stu-id="7b21c-108">DESCRIPTION</span></span>

<span data-ttu-id="7b21c-109">PowerShell に登録されているサブシステムに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="7b21c-109">Retrieves information about the subsystems registered in PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="7b21c-110">これは試験段階の機能です。</span><span class="sxs-lookup"><span data-stu-id="7b21c-110">This is an experimental feature.</span></span> <span data-ttu-id="7b21c-111">このコマンドレットは、機能が有効になっている場合にのみ使用でき `PSSubsystemPluginModel` ます。</span><span class="sxs-lookup"><span data-stu-id="7b21c-111">This cmdlet is only available when the `PSSubsystemPluginModel` feature is enabled.</span></span> <span data-ttu-id="7b21c-112">詳細については、「[試験的な機能の使用](/powershell/scripting/learn/experimental-features)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b21c-112">For more information, see [Using Experimental Features](/powershell/scripting/learn/experimental-features).</span></span>

<span data-ttu-id="7b21c-113">この機能により、`System.Management.Automation.dll` のコンポーネントを、独自のアセンブリに存在する個々のサブシステムに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="7b21c-113">The feature makes it possible to separate components of `System.Management.Automation.dll` into individual subsystems that reside in their own assembly.</span></span> <span data-ttu-id="7b21c-114">この分割により、コア PowerShell エンジンのディスク占有領域が削減され、これらのコンポーネントを最小限の PowerShell インストールに対するオプション機能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7b21c-114">This separation reduces the disk footprint of the core PowerShell engine and allows these components to become optional features for a minimal PowerShell installation.</span></span>

<span data-ttu-id="7b21c-115">現時点では、**CommandPredictor** サブシステムのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7b21c-115">Currently, only the **CommandPredictor** subsystem is supported.</span></span> <span data-ttu-id="7b21c-116">このサブシステムは、カスタム予測プラグインを提供するために、PSReadLine モジュールと共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7b21c-116">This subsystem is used along with the PSReadLine module to provide custom prediction plugins.</span></span> <span data-ttu-id="7b21c-117">今後、**Job**、**CommandCompleter**、**Remoting** などのコンポーネントは、`System.Management.Automation.dll` 外のサブシステム アセンブリに分割される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7b21c-117">In future, **Job**, **CommandCompleter**, **Remoting** and other components could be separated into subsystem assemblies outside of `System.Management.Automation.dll`.</span></span>

## <span data-ttu-id="7b21c-118">例</span><span class="sxs-lookup"><span data-stu-id="7b21c-118">EXAMPLES</span></span>

### <span data-ttu-id="7b21c-119">例 1-使用可能なすべてのサブシステムを表示する</span><span class="sxs-lookup"><span data-stu-id="7b21c-119">Example 1 - Display all available subsystems</span></span>

```powershell
Get-PSSubsystem
```

```Output
Kind              SubsystemType     IsRegistered Implementations
----              -------------     ------------ ---------------
CommandPredictor  ICommandPredictor        False {}
```

### <span data-ttu-id="7b21c-120">例 2-特定の種類の使用可能なすべてのサブシステムを表示する</span><span class="sxs-lookup"><span data-stu-id="7b21c-120">Example 2 - Display all available subsystems of a specific kind</span></span>

```powershell
PS> Get-PSSubsystem -Kind CommandPredictor | Format-List
```

```Output
Kind                      : CommandPredictor
SubsystemType             : System.Management.Automation.Subsystem.ICommandPredictor
AllowUnregistration       : True
AllowMultipleRegistration : True
RequiredCmdlets           : {}
RequiredFunctions         : {}
IsRegistered              : False
Implementations           : {}
```

## <span data-ttu-id="7b21c-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7b21c-121">PARAMETERS</span></span>

### <span data-ttu-id="7b21c-122">-Kind</span><span class="sxs-lookup"><span data-stu-id="7b21c-122">-Kind</span></span>


<span data-ttu-id="7b21c-123">返されるサブシステムの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b21c-123">Specifies the kind of subsystem to be returned.</span></span> <span data-ttu-id="7b21c-124">有効な値は `CommandPredictor` です。</span><span class="sxs-lookup"><span data-stu-id="7b21c-124">Valid values are: `CommandPredictor`.</span></span>

```yaml
Type: System.Management.Automation.Subsystem.SubsystemKind
Parameter Sets: GetByKindSet
Aliases:
Accepted values: CommandPredictor

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7b21c-125">-SubsystemType</span><span class="sxs-lookup"><span data-stu-id="7b21c-125">-SubsystemType</span></span>

<span data-ttu-id="7b21c-126">返されるサブシステムの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b21c-126">Specifies the type of subsystem to be returned.</span></span>

```yaml
Type: System.Type
Parameter Sets: GetByTypeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7b21c-127">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7b21c-127">CommonParameters</span></span>

<span data-ttu-id="7b21c-128">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7b21c-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7b21c-129">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b21c-129">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7b21c-130">入力</span><span class="sxs-lookup"><span data-stu-id="7b21c-130">INPUTS</span></span>

### <span data-ttu-id="7b21c-131">システム.... サブシステムの種類</span><span class="sxs-lookup"><span data-stu-id="7b21c-131">System.Management.Automation.Subsystem.SubsystemKind</span></span>

### <span data-ttu-id="7b21c-132">System.Type</span><span class="sxs-lookup"><span data-stu-id="7b21c-132">System.Type</span></span>

## <span data-ttu-id="7b21c-133">出力</span><span class="sxs-lookup"><span data-stu-id="7b21c-133">OUTPUTS</span></span>

### <span data-ttu-id="7b21c-134">システム... Subsystem. SubsystemInfo</span><span class="sxs-lookup"><span data-stu-id="7b21c-134">System.Management.Automation.Subsystem.SubsystemInfo</span></span>

## <span data-ttu-id="7b21c-135">注</span><span class="sxs-lookup"><span data-stu-id="7b21c-135">NOTES</span></span>

## <span data-ttu-id="7b21c-136">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7b21c-136">RELATED LINKS</span></span>

[<span data-ttu-id="7b21c-137">about_experimental_features</span><span class="sxs-lookup"><span data-stu-id="7b21c-137">about_experimental_features</span></span>](about/about_experimental_features.md)

[<span data-ttu-id="7b21c-138">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="7b21c-138">Disable-ExperimentalFeature</span></span>](Disable-ExperimentalFeature.md)

[<span data-ttu-id="7b21c-139">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="7b21c-139">Enable-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

[<span data-ttu-id="7b21c-140">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="7b21c-140">Get-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

[<span data-ttu-id="7b21c-141">試験的機能の使用</span><span class="sxs-lookup"><span data-stu-id="7b21c-141">Using Experimental Features</span></span>](/powershell/scripting/learn/experimental-features)
