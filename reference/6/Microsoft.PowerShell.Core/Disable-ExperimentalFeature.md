---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-experimentalfeature?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ExperimentalFeature
ms.openlocfilehash: 9b85e429df0de4c740345a7e1afc42b7614a4a96
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215067"
---
# <span data-ttu-id="b8036-102">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="b8036-102">Disable-ExperimentalFeature</span></span>

## <span data-ttu-id="b8036-103">概要</span><span class="sxs-lookup"><span data-stu-id="b8036-103">SYNOPSIS</span></span>
<span data-ttu-id="b8036-104">PowerShell の新しいインスタンスの起動時に実験的な機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b8036-104">Disable an experimental feature on startup of new instance of PowerShell.</span></span>

## <span data-ttu-id="b8036-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b8036-105">SYNTAX</span></span>

```
Disable-ExperimentalFeature [-Name] <String[]> [-Scope <ConfigScope>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b8036-106">Description</span><span class="sxs-lookup"><span data-stu-id="b8036-106">DESCRIPTION</span></span>

<span data-ttu-id="b8036-107">`Disable-ExperimentalFeature`コマンドレットは、 `powershell.config.json` PowerShell の起動時に読み取られる設定ファイルから、名前付きの試験的な機能を削除することにより、実験的な機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b8036-107">The `Disable-ExperimentalFeature` cmdlet disables experimental features by removing the named experimental features from the `powershell.config.json` settings file read on PowerShell startup.</span></span>

<span data-ttu-id="b8036-108">このコマンドレットは、PowerShell 6.2 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b8036-108">This cmdlet was introduced in PowerShell 6.2.</span></span>

> [!NOTE]
> <span data-ttu-id="b8036-109">実験的な機能の状態に対する変更は、PowerShell の再起動時にのみ有効になります</span><span class="sxs-lookup"><span data-stu-id="b8036-109">Any changes to experimental feature state only takes effect on restart of PowerShell</span></span>

## <span data-ttu-id="b8036-110">例</span><span class="sxs-lookup"><span data-stu-id="b8036-110">EXAMPLES</span></span>

### <span data-ttu-id="b8036-111">例 1: 試験的な機能を無効にする</span><span class="sxs-lookup"><span data-stu-id="b8036-111">Example 1: Disable an experimental feature</span></span>

<span data-ttu-id="b8036-112">この例では、この実験的な機能が既に有効になっている場合、 `powershell.config.json` PowerShell を再起動した後に、ユーザーがこの機能を有効にしないように、ファイルが更新されます。</span><span class="sxs-lookup"><span data-stu-id="b8036-112">In this example, if this experimental feature was previously enabled, then the `powershell.config.json` file is updated for the user to not enable that feature once PowerShell is restarted.</span></span>
<span data-ttu-id="b8036-113">成功すると、何もパイプラインに出力されず、警告メッセージのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8036-113">Upon success nothing is output to the pipeline and only a warning message is displayed.</span></span>

```powershell
PS C:\> Disable-ExperimentalFeature PSImplicitRemotingBatching
```

```Output
WARNING: Enabling and disabling experimental features do not take effect until next start of PowerShell.
```

## <span data-ttu-id="b8036-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b8036-114">PARAMETERS</span></span>

### <span data-ttu-id="b8036-115">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b8036-115">-Confirm</span></span>

<span data-ttu-id="b8036-116">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8036-116">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8036-117">-Name</span><span class="sxs-lookup"><span data-stu-id="b8036-117">-Name</span></span>

<span data-ttu-id="b8036-118">無効にする試験的な機能の名前。</span><span class="sxs-lookup"><span data-stu-id="b8036-118">The name or names of the experimental features to disable.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b8036-119">-スコープ</span><span class="sxs-lookup"><span data-stu-id="b8036-119">-Scope</span></span>

<span data-ttu-id="b8036-120">すべての `powershell.config.json` ユーザーに影響するか、現在のユーザーのみに影響するかを更新するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="b8036-120">Determines which `powershell.config.json` to update whether it affects all users or just the current user.</span></span>

```yaml
Type: System.Management.Automation.Configuration.ConfigScope
Parameter Sets: (All)
Aliases:
Accepted values: AllUsers, CurrentUser

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8036-121">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b8036-121">-WhatIf</span></span>

<span data-ttu-id="b8036-122">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="b8036-122">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b8036-123">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="b8036-123">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8036-124">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b8036-124">CommonParameters</span></span>

<span data-ttu-id="b8036-125">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b8036-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b8036-126">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8036-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b8036-127">入力</span><span class="sxs-lookup"><span data-stu-id="b8036-127">INPUTS</span></span>

### <span data-ttu-id="b8036-128">ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="b8036-128">ExperimentalFeature</span></span>

<span data-ttu-id="b8036-129">ExperimentalFeature のパイプインスタンスを `Get-ExperimentalFeature` コマンドレットから無効にします。</span><span class="sxs-lookup"><span data-stu-id="b8036-129">Pipe instances of ExperimentalFeature from `Get-ExperimentalFeature` cmdlet to disable.</span></span>

## <span data-ttu-id="b8036-130">出力</span><span class="sxs-lookup"><span data-stu-id="b8036-130">OUTPUTS</span></span>

### <span data-ttu-id="b8036-131">なし</span><span class="sxs-lookup"><span data-stu-id="b8036-131">None</span></span>

<span data-ttu-id="b8036-132">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="b8036-132">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="b8036-133">注</span><span class="sxs-lookup"><span data-stu-id="b8036-133">NOTES</span></span>

<span data-ttu-id="b8036-134">試験的な機能の状態に対する変更は、PowerShell の再起動時にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="b8036-134">Changes to state of an experimental feature only take effect on restart of PowerShell.</span></span>

## <span data-ttu-id="b8036-135">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b8036-135">RELATED LINKS</span></span>

[<span data-ttu-id="b8036-136">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="b8036-136">Enable-ExperimentalFeature</span></span>](Enable-ExperimentalFeature.md)

[<span data-ttu-id="b8036-137">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="b8036-137">Get-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)