---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSnapin
ms.openlocfilehash: 156cadecd87910e3c3312e84929b16709770641d
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388673"
---
# <span data-ttu-id="f7daa-103">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="f7daa-103">Get-PSSnapin</span></span>

## <span data-ttu-id="f7daa-104">概要</span><span class="sxs-lookup"><span data-stu-id="f7daa-104">SYNOPSIS</span></span>
<span data-ttu-id="f7daa-105">コンピューター上の Windows PowerShell スナップインを取得します。</span><span class="sxs-lookup"><span data-stu-id="f7daa-105">Gets the Windows PowerShell snap-ins on the computer.</span></span>

## <span data-ttu-id="f7daa-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f7daa-106">SYNTAX</span></span>

```
Get-PSSnapin [[-Name] <String[]>] [-Registered] [<CommonParameters>]
```

## <span data-ttu-id="f7daa-107">Description</span><span class="sxs-lookup"><span data-stu-id="f7daa-107">DESCRIPTION</span></span>

<span data-ttu-id="f7daa-108">この `Get-PSSnapin` コマンドレットは、現在のセッションに追加されている、またはシステムに登録されている Windows PowerShell スナップインを取得します。</span><span class="sxs-lookup"><span data-stu-id="f7daa-108">The `Get-PSSnapin` cmdlet gets the Windows PowerShell snap-ins that have been added to the current session or that have been registered on the system.</span></span> <span data-ttu-id="f7daa-109">このコマンドレットは、スナップインが検出された順に一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f7daa-109">This cmdlet lists the snap-ins in the order in which they are detected.</span></span>

<span data-ttu-id="f7daa-110">`Get-PSSnapin` 登録されたスナップインのみを取得します。Windows PowerShell スナップインを登録するには、Microsoft .NET Framework 2.0 に含まれている Installutil.exe ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7daa-110">`Get-PSSnapin` gets only registered snap-ins. To register a Windows PowerShell snap-in, use the InstallUtil tool included with the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="f7daa-111">詳細については、「 [コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7daa-111">For more information, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

<span data-ttu-id="f7daa-112">Windows PowerShell 3.0 以降では、Windows PowerShell に含まれるコアコマンドはモジュールにパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="f7daa-112">Starting in Windows PowerShell 3.0, the core commands that are included in Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="f7daa-113">例外は、スナップイン (PSSnapin) の **Microsoft.PowerShell.Core** です。</span><span class="sxs-lookup"><span data-stu-id="f7daa-113">The exception is **Microsoft.PowerShell.Core** , which is a snap-in (PSSnapin).</span></span>
<span data-ttu-id="f7daa-114">既定では、 **Microsoft.PowerShell.Core** スナップインのみがセッションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="f7daa-114">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span> <span data-ttu-id="f7daa-115">モジュールは初回使用時に自動的にインポートされ、コマンドレットを使用して `Import-Module` インポートできます。</span><span class="sxs-lookup"><span data-stu-id="f7daa-115">Modules are imported automatically on first use and you can use the `Import-Module` cmdlet to import them.</span></span>

## <span data-ttu-id="f7daa-116">例</span><span class="sxs-lookup"><span data-stu-id="f7daa-116">EXAMPLES</span></span>

### <span data-ttu-id="f7daa-117">例 1: 現在読み込まれているスナップインを取得する</span><span class="sxs-lookup"><span data-stu-id="f7daa-117">Example 1: Get snap-ins that are currently loaded</span></span>

```
PS C:\> Get-PSSnapIn
```

<span data-ttu-id="f7daa-118">このコマンドは、セッションで現在読み込まれている Windows PowerShell スナップインを取得します。</span><span class="sxs-lookup"><span data-stu-id="f7daa-118">This command gets the Windows PowerShell snap-ins that are currently loaded in the session.</span></span> <span data-ttu-id="f7daa-119">これには、Windows PowerShell でインストールされたスナップインや、セッションに追加されたスナップインが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f7daa-119">This includes the snap-ins that are installed with Windows PowerShell and those that have been added to the session.</span></span>

### <span data-ttu-id="f7daa-120">例 2: 登録されているスナップインを取得する</span><span class="sxs-lookup"><span data-stu-id="f7daa-120">Example 2: Get snap-ins that have been registered</span></span>

```
PS C:\> get-PSSnapIn -Registered
```

<span data-ttu-id="f7daa-121">このコマンドは、コンピューターに登録された Windows PowerShell スナップイン (既にセッションに追加されているスナップインを含む) を取得します。</span><span class="sxs-lookup"><span data-stu-id="f7daa-121">This command gets the Windows PowerShell snap-ins that have been registered on the computer, including those that have already been added to the session.</span></span> <span data-ttu-id="f7daa-122">Windows PowerShell でインストールされたスナップイン、またはシステムに登録されていない Windows PowerShell スナップインのダイナミック リンク ライブラリ (DLL) は、出力に含まれません。</span><span class="sxs-lookup"><span data-stu-id="f7daa-122">The output does not include snap-ins that are installed with Windows PowerShell or Windows PowerShell snap-in dynamic-link libraries (DLLs) that have not yet been registered on the system.</span></span>

### <span data-ttu-id="f7daa-123">例 3: 文字列に一致する現在のスナップインを取得する</span><span class="sxs-lookup"><span data-stu-id="f7daa-123">Example 3: Get current snap-ins that match a string</span></span>

```
PS C:\> Get-PSSnapIn -Name smp*
```

<span data-ttu-id="f7daa-124">このコマンドは、現在のセッションで、名前が smp で始まる Windows PowerShell スナップインを取得します。</span><span class="sxs-lookup"><span data-stu-id="f7daa-124">This command gets the Windows PowerShell snap-ins in the current session that have names that begin with smp.</span></span>

## <span data-ttu-id="f7daa-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f7daa-125">PARAMETERS</span></span>

### <span data-ttu-id="f7daa-126">-Name</span><span class="sxs-lookup"><span data-stu-id="f7daa-126">-Name</span></span>

<span data-ttu-id="f7daa-127">スナップイン名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7daa-127">Specifies an array of snap-in names.</span></span> <span data-ttu-id="f7daa-128">このコマンドレットは、指定された Windows PowerShell スナップインのみを取得します。ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7daa-128">This cmdlet gets only the specified Windows PowerShell snap-ins. Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7daa-129">-登録済み</span><span class="sxs-lookup"><span data-stu-id="f7daa-129">-Registered</span></span>

<span data-ttu-id="f7daa-130">このコマンドレットが、まだセッションに追加されていない場合でも、システムに登録されている Windows PowerShell スナップインを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="f7daa-130">Indicates that this cmdlet gets the Windows PowerShell snap-ins that have been registered on the system even if they have not yet been added to the session.</span></span>

<span data-ttu-id="f7daa-131">Windows PowerShell でインストールされたスナップインは、この一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="f7daa-131">The snap-ins that are installed with Windows PowerShell do not appear in this list.</span></span>

<span data-ttu-id="f7daa-132">このパラメーターを指定しない場合、 `Get-PSSnapin` セッションに追加されている Windows PowerShell スナップインを取得します。</span><span class="sxs-lookup"><span data-stu-id="f7daa-132">Without this parameter, `Get-PSSnapin` gets the Windows PowerShell snap-ins that have been added to the session.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7daa-133">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7daa-133">CommonParameters</span></span>

<span data-ttu-id="f7daa-134">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f7daa-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f7daa-135">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7daa-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f7daa-136">入力</span><span class="sxs-lookup"><span data-stu-id="f7daa-136">INPUTS</span></span>

### <span data-ttu-id="f7daa-137">なし</span><span class="sxs-lookup"><span data-stu-id="f7daa-137">None</span></span>
<span data-ttu-id="f7daa-138">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="f7daa-138">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="f7daa-139">出力</span><span class="sxs-lookup"><span data-stu-id="f7daa-139">OUTPUTS</span></span>

### <span data-ttu-id="f7daa-140">システム管理. PSSnapInInfo</span><span class="sxs-lookup"><span data-stu-id="f7daa-140">System.Management.Automation.PSSnapInInfo</span></span>

<span data-ttu-id="f7daa-141">`Get-PSSnapin` 取得した各スナップインのオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="f7daa-141">`Get-PSSnapin` returns an object for each snap-in that it gets.</span></span>

## <span data-ttu-id="f7daa-142">注</span><span class="sxs-lookup"><span data-stu-id="f7daa-142">NOTES</span></span>

<span data-ttu-id="f7daa-143">Windows powershell 3.0 以降では、Windows PowerShell と共にインストールされるコアコマンドはモジュールにパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="f7daa-143">Starting in Windows PowerShell 3.0, the core commands that are installed with Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="f7daa-144">Windows PowerShell 2.0、およびそれ以降のバージョンの Windows PowerShell で古いスタイルのセッションを作成するホストプログラムでは、コアコマンドはスナップイン ( **add-pssnapin** ) にパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="f7daa-144">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of Windows PowerShell, the core commands are packaged in snap-ins ( **PSSnapin** ).</span></span> <span data-ttu-id="f7daa-145">例外は、常にスナップインである、 **PowerShell です** 。</span><span class="sxs-lookup"><span data-stu-id="f7daa-145">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="f7daa-146">また、コマンドレットによって開始されるようなリモートセッション `New-PSSession` は、コアスナップインを含む古いスタイルのセッションです。</span><span class="sxs-lookup"><span data-stu-id="f7daa-146">Also, remote sessions, such as those started by the `New-PSSession` cmdlet, are older-style sessions that include core snap-ins.</span></span>

 <span data-ttu-id="f7daa-147">コアモジュールで新しいスタイルのセッションを作成する **CreateDefault2** メソッドの詳細については、「 [CreateDefault2 メソッド](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2#System_Management_Automation_Runspaces_InitialSessionState_CreateDefault2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7daa-147">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2#System_Management_Automation_Runspaces_InitialSessionState_CreateDefault2).</span></span>

## <span data-ttu-id="f7daa-148">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f7daa-148">RELATED LINKS</span></span>

[<span data-ttu-id="f7daa-149">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="f7daa-149">Add-PSSnapin</span></span>](Add-PSSnapin.md)

[<span data-ttu-id="f7daa-150">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="f7daa-150">Remove-PSSnapin</span></span>](Remove-PSSnapin.md)
