---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssessioncapability?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSessionCapability
ms.openlocfilehash: e81302a442294a7eeab81c6e8e1c6b7fd0cfb5fe
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603049"
---
# <span data-ttu-id="9df48-102">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="9df48-102">Get-PSSessionCapability</span></span>

## <span data-ttu-id="9df48-103">概要</span><span class="sxs-lookup"><span data-stu-id="9df48-103">SYNOPSIS</span></span>
<span data-ttu-id="9df48-104">制約付きセッション構成で特定のユーザーの機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="9df48-104">Gets the capabilities of a specific user on a constrained session configuration.</span></span>

## <span data-ttu-id="9df48-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9df48-105">SYNTAX</span></span>

```
Get-PSSessionCapability [-ConfigurationName] <String> [-Username] <String> [-Full] [<CommonParameters>]
```

## <span data-ttu-id="9df48-106">Description</span><span class="sxs-lookup"><span data-stu-id="9df48-106">DESCRIPTION</span></span>

<span data-ttu-id="9df48-107">**Get PSSessionCapability** コマンドレットは、制約付きセッション構成で特定のユーザーの機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="9df48-107">The **Get-PSSessionCapability** cmdlet gets the capabilities of a specific user on a constrained session configuration.</span></span>
<span data-ttu-id="9df48-108">このコマンドレットを使用して、ユーザーのカスタマイズされたセッション構成を監査します。</span><span class="sxs-lookup"><span data-stu-id="9df48-108">Use this cmdlet to audit customized session configurations for users.</span></span>

<span data-ttu-id="9df48-109">Windows PowerShell 5.0 以降では、セッション構成 (.pssc) ファイルで **Roledefinitions** プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9df48-109">Starting in Windows PowerShell 5.0, you can use the **RoleDefinitions** property in a session configuration (.pssc) file.</span></span>
<span data-ttu-id="9df48-110">このプロパティを使用すると、グループのメンバーシップに基づいて、1つの制約付きエンドポイントに対してユーザーのさまざまな機能を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="9df48-110">Using this property lets you grant users different capabilities on a single constrained endpoint based on group membership.</span></span>
<span data-ttu-id="9df48-111">**Get PSSessionCapability** コマンドレットを使用すると、ユーザーに付与されている正確な機能を決定できるため、これらのエンドポイントを監査する際の複雑さが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="9df48-111">The **Get-PSSessionCapability** cmdlet reduces complexity when auditing these endpoints by letting you determine the exact capabilities granted to a user.</span></span>

<span data-ttu-id="9df48-112">既定では、 **取得-PSSessionCapability ビリティ** コマンドレットは、指定されたユーザーが指定したエンドポイントで実行できるコマンドの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="9df48-112">By default, the **Get-PSSessionCapability** cmdlet returns a list of commands the specified user can run in the specified endpoint.</span></span>
<span data-ttu-id="9df48-113">これは、指定されたエンドポイントで **Get コマンド** を実行しているユーザーに相当します。</span><span class="sxs-lookup"><span data-stu-id="9df48-113">This is equivalent to the user running **Get-Command** in the specified endpoint.</span></span>
<span data-ttu-id="9df48-114">*Full* パラメーターを指定して実行すると、このコマンドレットは **InitialSessionState** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="9df48-114">When run with the *Full* parameter, this cmdlet returns an **InitialSessionState** object.</span></span>
<span data-ttu-id="9df48-115">このオブジェクトには、指定したユーザーが指定したエンドポイントに対して操作する PowerShell 実行空間に関する詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9df48-115">This object contains details about the PowerShell runspace the specified user would interact with for the specified endpoint.</span></span>
<span data-ttu-id="9df48-116">これには、言語モード、実行ポリシー、および環境変数などの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9df48-116">It includes information such as Language Mode, Execution Policy, and Environmental Variables.</span></span>

## <span data-ttu-id="9df48-117">例</span><span class="sxs-lookup"><span data-stu-id="9df48-117">EXAMPLES</span></span>

### <span data-ttu-id="9df48-118">例 1: ユーザーが使用できるコマンドを取得する</span><span class="sxs-lookup"><span data-stu-id="9df48-118">Example 1: Get commands available for a user</span></span>

```powershell
Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User'
```

<span data-ttu-id="9df48-119">この例では、ローカルコンピューター上の Endpoint1 の制約付きエンドポイントに接続するときに、ユーザー CONTOSO\User が使用できるコマンドを返します。</span><span class="sxs-lookup"><span data-stu-id="9df48-119">This example returns the commands available to the user CONTOSO\User when connecting to the Endpoint1 constrained endpoint on the local computer.</span></span>

### <span data-ttu-id="9df48-120">例 2: ユーザーの実行空間に関する詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="9df48-120">Example 2: Get details about a runspace for a user</span></span>

```powershell
Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User' -Full
```

<span data-ttu-id="9df48-121">この例では、Endpoint1 の制約付きエンドポイントに接続するときに、ユーザー CONTOSO\User が操作する実行空間に関する詳細を返します。</span><span class="sxs-lookup"><span data-stu-id="9df48-121">This example returns details about the runspace the user CONTOSO\User would interact with when connecting to the Endpoint1 constrained endpoint.</span></span>

## <span data-ttu-id="9df48-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9df48-122">PARAMETERS</span></span>

### <span data-ttu-id="9df48-123">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="9df48-123">-ConfigurationName</span></span>

<span data-ttu-id="9df48-124">検査する制約付きセッション構成 (エンドポイント) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9df48-124">Specifies the constrained session configuration (endpoint) that you are inspecting.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9df48-125">-Full</span><span class="sxs-lookup"><span data-stu-id="9df48-125">-Full</span></span>

<span data-ttu-id="9df48-126">このコマンドレットが、指定された制約付きエンドポイントで、指定したユーザーの初期セッション状態全体を返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="9df48-126">Indicates that this cmdlet returns the entire initial session state for the specified user at the specified constrained endpoint.</span></span>

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

### <span data-ttu-id="9df48-127">-Username</span><span class="sxs-lookup"><span data-stu-id="9df48-127">-Username</span></span>

<span data-ttu-id="9df48-128">検査する機能を持つユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="9df48-128">Specifies the user whose capabilities you are inspecting.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9df48-129">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9df48-129">CommonParameters</span></span>

<span data-ttu-id="9df48-130">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9df48-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9df48-131">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9df48-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9df48-132">入力</span><span class="sxs-lookup"><span data-stu-id="9df48-132">INPUTS</span></span>

## <span data-ttu-id="9df48-133">出力</span><span class="sxs-lookup"><span data-stu-id="9df48-133">OUTPUTS</span></span>

### <span data-ttu-id="9df48-134">システム管理. エイリアス情報</span><span class="sxs-lookup"><span data-stu-id="9df48-134">System.Management.Automation.AliasInfo</span></span>

### <span data-ttu-id="9df48-135">システム管理. FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="9df48-135">System.Management.Automation.FunctionInfo</span></span>

### <span data-ttu-id="9df48-136">System.Management.Automation.Runspaces.InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="9df48-136">System.Management.Automation.Runspaces.InitialSessionState</span></span>

## <span data-ttu-id="9df48-137">注</span><span class="sxs-lookup"><span data-stu-id="9df48-137">NOTES</span></span>

## <span data-ttu-id="9df48-138">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9df48-138">RELATED LINKS</span></span>

[<span data-ttu-id="9df48-139">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="9df48-139">New-PSRoleCapabilityFile</span></span>](New-PSRoleCapabilityFile.md)

