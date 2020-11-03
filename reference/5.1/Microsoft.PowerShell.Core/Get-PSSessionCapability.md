---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssessioncapability?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSessionCapability
ms.openlocfilehash: d76baaef31c27184bc355b6f0fc79ca67b986157
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212016"
---
# <span data-ttu-id="77bbf-103">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="77bbf-103">Get-PSSessionCapability</span></span>

## <span data-ttu-id="77bbf-104">概要</span><span class="sxs-lookup"><span data-stu-id="77bbf-104">SYNOPSIS</span></span>
<span data-ttu-id="77bbf-105">制約付きセッション構成で特定のユーザーの機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="77bbf-105">Gets the capabilities of a specific user on a constrained session configuration.</span></span>

## <span data-ttu-id="77bbf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="77bbf-106">SYNTAX</span></span>

```
Get-PSSessionCapability [-ConfigurationName] <String> [-Username] <String> [-Full] [<CommonParameters>]
```

## <span data-ttu-id="77bbf-107">Description</span><span class="sxs-lookup"><span data-stu-id="77bbf-107">DESCRIPTION</span></span>
<span data-ttu-id="77bbf-108">**Get PSSessionCapability** コマンドレットは、制約付きセッション構成で特定のユーザーの機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="77bbf-108">The **Get-PSSessionCapability** cmdlet gets the capabilities of a specific user on a constrained session configuration.</span></span>
<span data-ttu-id="77bbf-109">このコマンドレットを使用して、ユーザーのカスタマイズされたセッション構成を監査します。</span><span class="sxs-lookup"><span data-stu-id="77bbf-109">Use this cmdlet to audit customized session configurations for users.</span></span>

<span data-ttu-id="77bbf-110">Windows PowerShell 5.0 以降では、セッション構成 (.pssc) ファイルで **Roledefinitions** プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="77bbf-110">Starting in Windows PowerShell 5.0, you can use the **RoleDefinitions** property in a session configuration (.pssc) file.</span></span>
<span data-ttu-id="77bbf-111">このプロパティを使用すると、グループのメンバーシップに基づいて、1つの制約付きエンドポイントに対してユーザーのさまざまな機能を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="77bbf-111">Using this property lets you grant users different capabilities on a single constrained endpoint based on group membership.</span></span>
<span data-ttu-id="77bbf-112">**Get PSSessionCapability** コマンドレットを使用すると、ユーザーに付与されている正確な機能を決定できるため、これらのエンドポイントを監査する際の複雑さが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="77bbf-112">The **Get-PSSessionCapability** cmdlet reduces complexity when auditing these endpoints by letting you determine the exact capabilities granted to a user.</span></span>

<span data-ttu-id="77bbf-113">既定では、 **取得-PSSessionCapability ビリティ** コマンドレットは、指定されたユーザーが指定したエンドポイントで実行できるコマンドの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="77bbf-113">By default, the **Get-PSSessionCapability** cmdlet returns a list of commands the specified user can run in the specified endpoint.</span></span>
<span data-ttu-id="77bbf-114">これは、指定されたエンドポイントで **Get コマンド** を実行しているユーザーに相当します。</span><span class="sxs-lookup"><span data-stu-id="77bbf-114">This is equivalent to the user running **Get-Command** in the specified endpoint.</span></span>
<span data-ttu-id="77bbf-115">*Full* パラメーターを指定して実行すると、このコマンドレットは **InitialSessionState** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="77bbf-115">When run with the *Full* parameter, this cmdlet returns an **InitialSessionState** object.</span></span>
<span data-ttu-id="77bbf-116">このオブジェクトには、指定したユーザーが指定したエンドポイントに対して操作する Windows PowerShell 実行空間に関する詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="77bbf-116">This object contains details about the Windows PowerShell runspace the specified user would interact with for the specified endpoint.</span></span>
<span data-ttu-id="77bbf-117">これには、言語モード、実行ポリシー、および環境変数などの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="77bbf-117">It includes information such as Language Mode, Execution Policy, and Environmental Variables.</span></span>

## <span data-ttu-id="77bbf-118">例</span><span class="sxs-lookup"><span data-stu-id="77bbf-118">EXAMPLES</span></span>

### <span data-ttu-id="77bbf-119">例 1: ユーザーが使用できるコマンドを取得する</span><span class="sxs-lookup"><span data-stu-id="77bbf-119">Example 1: Get commands available for a user</span></span>

```
PS C:\> Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User'
```

<span data-ttu-id="77bbf-120">この例では、ローカルコンピューター上の Endpoint1 の制約付きエンドポイントに接続するときに、ユーザー CONTOSO\User が使用できるコマンドを返します。</span><span class="sxs-lookup"><span data-stu-id="77bbf-120">This example returns the commands available to the user CONTOSO\User when connecting to the Endpoint1 constrained endpoint on the local computer.</span></span>

### <span data-ttu-id="77bbf-121">例 2: ユーザーの実行空間に関する詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="77bbf-121">Example 2: Get details about a runspace for a user</span></span>

```
PS C:\> Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User' -Full
```

<span data-ttu-id="77bbf-122">この例では、Endpoint1 の制約付きエンドポイントに接続するときに、ユーザー CONTOSO\User が操作する実行空間に関する詳細を返します。</span><span class="sxs-lookup"><span data-stu-id="77bbf-122">This example returns details about the runspace the user CONTOSO\User would interact with when connecting to the Endpoint1 constrained endpoint.</span></span>

## <span data-ttu-id="77bbf-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="77bbf-123">PARAMETERS</span></span>

### <span data-ttu-id="77bbf-124">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="77bbf-124">-ConfigurationName</span></span>
<span data-ttu-id="77bbf-125">検査する制約付きセッション構成 (エンドポイント) を指定します。</span><span class="sxs-lookup"><span data-stu-id="77bbf-125">Specifies the constrained session configuration (endpoint) that you are inspecting.</span></span>

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

### <span data-ttu-id="77bbf-126">-Full</span><span class="sxs-lookup"><span data-stu-id="77bbf-126">-Full</span></span>
<span data-ttu-id="77bbf-127">このコマンドレットが、指定された制約付きエンドポイントで、指定したユーザーの初期セッション状態全体を返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="77bbf-127">Indicates that this cmdlet returns the entire initial session state for the specified user at the specified constrained endpoint.</span></span>

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

### <span data-ttu-id="77bbf-128">-Username</span><span class="sxs-lookup"><span data-stu-id="77bbf-128">-Username</span></span>
<span data-ttu-id="77bbf-129">検査する機能を持つユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="77bbf-129">Specifies the user whose capabilities you are inspecting.</span></span>

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

### <span data-ttu-id="77bbf-130">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="77bbf-130">CommonParameters</span></span>
<span data-ttu-id="77bbf-131">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="77bbf-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="77bbf-132">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77bbf-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="77bbf-133">入力</span><span class="sxs-lookup"><span data-stu-id="77bbf-133">INPUTS</span></span>

## <span data-ttu-id="77bbf-134">出力</span><span class="sxs-lookup"><span data-stu-id="77bbf-134">OUTPUTS</span></span>

### <span data-ttu-id="77bbf-135">システム管理. エイリアス情報</span><span class="sxs-lookup"><span data-stu-id="77bbf-135">System.Management.Automation.AliasInfo</span></span>

### <span data-ttu-id="77bbf-136">システム管理. FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="77bbf-136">System.Management.Automation.FunctionInfo</span></span>

### <span data-ttu-id="77bbf-137">System.Management.Automation.Runspaces.InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="77bbf-137">System.Management.Automation.Runspaces.InitialSessionState</span></span>

## <span data-ttu-id="77bbf-138">注</span><span class="sxs-lookup"><span data-stu-id="77bbf-138">NOTES</span></span>

## <span data-ttu-id="77bbf-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="77bbf-139">RELATED LINKS</span></span>

[<span data-ttu-id="77bbf-140">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="77bbf-140">New-PSRoleCapabilityFile</span></span>](New-PSRoleCapabilityFile.md)
