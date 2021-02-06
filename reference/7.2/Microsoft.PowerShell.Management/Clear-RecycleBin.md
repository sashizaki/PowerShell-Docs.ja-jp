---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/29/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: e7ce0f2bcd1ece0bb737aea1297641c37337f3e5
ms.sourcegitcommit: 81558c2adb9d109946a027e5b96e4d24b3b13747
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2021
ms.locfileid: "99605446"
---
# <span data-ttu-id="a40e2-102">Clear-RecycleBin</span><span class="sxs-lookup"><span data-stu-id="a40e2-102">Clear-RecycleBin</span></span>

## <span data-ttu-id="a40e2-103">概要</span><span class="sxs-lookup"><span data-stu-id="a40e2-103">SYNOPSIS</span></span>
<span data-ttu-id="a40e2-104">ごみ箱の内容をクリアします。</span><span class="sxs-lookup"><span data-stu-id="a40e2-104">Clears the contents of a recycle bin.</span></span>

## <span data-ttu-id="a40e2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a40e2-105">SYNTAX</span></span>

### <span data-ttu-id="a40e2-106">すべて</span><span class="sxs-lookup"><span data-stu-id="a40e2-106">All</span></span>

```
Clear-RecycleBin [[-DriveLetter] <String[]>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a40e2-107">Description</span><span class="sxs-lookup"><span data-stu-id="a40e2-107">DESCRIPTION</span></span>

<span data-ttu-id="a40e2-108">`Clear-RecycleBin`コマンドレットは、コンピューターのごみ箱の内容を削除します。</span><span class="sxs-lookup"><span data-stu-id="a40e2-108">The `Clear-RecycleBin` cmdlet deletes the content of a computer's recycle bin.</span></span> <span data-ttu-id="a40e2-109">この操作は、Windows の **空のごみ箱** の使用に似ています。</span><span class="sxs-lookup"><span data-stu-id="a40e2-109">This action is like using Windows **Empty Recycle Bin**.</span></span>

<span data-ttu-id="a40e2-110">このコマンドレットは、PowerShell 7 で readded ました。</span><span class="sxs-lookup"><span data-stu-id="a40e2-110">This cmdlet was readded in PowerShell 7.</span></span>

## <span data-ttu-id="a40e2-111">例</span><span class="sxs-lookup"><span data-stu-id="a40e2-111">EXAMPLES</span></span>

### <span data-ttu-id="a40e2-112">1: すべてのごみ箱をクリアします。</span><span class="sxs-lookup"><span data-stu-id="a40e2-112">1: Clear all recycle bins</span></span>

<span data-ttu-id="a40e2-113">この例では、すべてのローカルコンピューターのごみ箱がクリアされています。</span><span class="sxs-lookup"><span data-stu-id="a40e2-113">In this example, all the local computer's recycle bins are cleared.</span></span>

```powershell
Clear-RecycleBin
```

```Output
Confirm
Are you sure you want to perform this action?
Performing the operation "Clear-RecycleBin" on target "All of the contents of the Recycle Bin".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="a40e2-114">`Clear-RecycleBin` ローカルコンピューター上のすべてのごみ箱をクリアするかどうかを確認するメッセージをユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="a40e2-114">`Clear-RecycleBin` prompts the user for confirmation to clear all recycle bins on the local computer.</span></span>

### <span data-ttu-id="a40e2-115">2: 指定されたごみ箱をクリアします</span><span class="sxs-lookup"><span data-stu-id="a40e2-115">2: Clear a specified recycle bin</span></span>

<span data-ttu-id="a40e2-116">この例では、指定されたドライブ文字のごみ箱をクリアします。</span><span class="sxs-lookup"><span data-stu-id="a40e2-116">This example clears the recycle bin for a specified drive letter.</span></span>

```powershell
Clear-RecycleBin -DriveLetter C
```

<span data-ttu-id="a40e2-117">`Clear-RecycleBin`**ドライブ** 文字パラメーターを使用して、 **C** ボリュームにごみ箱を指定します。</span><span class="sxs-lookup"><span data-stu-id="a40e2-117">`Clear-RecycleBin` uses the **DriveLetter** parameter to specify the recycle bin on the **C** volume.</span></span> <span data-ttu-id="a40e2-118">コマンドを実行するかどうかを確認するメッセージがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a40e2-118">The user is prompted for confirmation to run the command.</span></span>

### <span data-ttu-id="a40e2-119">3: 確認せずにすべてのごみ箱をクリアする</span><span class="sxs-lookup"><span data-stu-id="a40e2-119">3: Clear all recycle bins without confirmation</span></span>

<span data-ttu-id="a40e2-120">この例では、ローカルコンピューターのごみ箱をクリアするかどうかを確認するプロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a40e2-120">This example doesn't prompt for confirmation to clear the local computer's recycle bins.</span></span>

```powershell
Clear-RecycleBin -Force
```

<span data-ttu-id="a40e2-121">`Clear-RecycleBin`**Force** パラメーターを使用し、ローカルコンピューター上のすべてのごみ箱をクリアするかどうかを確認するメッセージをユーザーに表示しません。</span><span class="sxs-lookup"><span data-stu-id="a40e2-121">`Clear-RecycleBin` uses the **Force** parameter and doesn't prompt the user for confirmation to clear all recycle bins on the local computer.</span></span>

<span data-ttu-id="a40e2-122">別の方法と `-Force` して、をに置き換え `-Confirm:$false` ます。</span><span class="sxs-lookup"><span data-stu-id="a40e2-122">An alternative is to replace `-Force` with `-Confirm:$false`.</span></span>

## <span data-ttu-id="a40e2-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a40e2-123">PARAMETERS</span></span>

### <span data-ttu-id="a40e2-124">-ドライブ文字</span><span class="sxs-lookup"><span data-stu-id="a40e2-124">-DriveLetter</span></span>

<span data-ttu-id="a40e2-125">1つのドライブ文字またはドライブ文字の配列に対してクリアするごみ箱を指定します。</span><span class="sxs-lookup"><span data-stu-id="a40e2-125">Specifies the recycle bin to clear for a single drive letter or an array of drive letters.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a40e2-126">-Force</span><span class="sxs-lookup"><span data-stu-id="a40e2-126">-Force</span></span>

<span data-ttu-id="a40e2-127">ごみ箱をクリアするかどうかを確認するメッセージがユーザーに表示されないように指定します。</span><span class="sxs-lookup"><span data-stu-id="a40e2-127">Specifies that the user isn't prompted for confirmation to clear a recycle bin.</span></span> <span data-ttu-id="a40e2-128">**Force** パラメーターは、 **WhatIf** パラメーターと **Confirm** パラメーターもオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="a40e2-128">The **Force** parameter also overrides the **WhatIf** and **Confirm** parameters.</span></span>

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

### <span data-ttu-id="a40e2-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a40e2-129">-Confirm</span></span>

<span data-ttu-id="a40e2-130">コマンドレットを実行する前に、ユーザーに確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a40e2-130">Prompts for user confirmation before running the cmdlet.</span></span> <span data-ttu-id="a40e2-131">**Confirm** パラメーターが指定されていない場合でも、ユーザーに確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a40e2-131">The user is prompted for confirmation even if the **Confirm** parameter isn't specified.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a40e2-132">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a40e2-132">-WhatIf</span></span>

<span data-ttu-id="a40e2-133">が実行された場合に何が起こるか `Clear-RecycleBin` を示します。</span><span class="sxs-lookup"><span data-stu-id="a40e2-133">Shows what would happen if `Clear-RecycleBin` runs.</span></span> <span data-ttu-id="a40e2-134">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a40e2-134">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a40e2-135">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a40e2-135">CommonParameters</span></span>

<span data-ttu-id="a40e2-136">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a40e2-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a40e2-137">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a40e2-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a40e2-138">入力</span><span class="sxs-lookup"><span data-stu-id="a40e2-138">INPUTS</span></span>

## <span data-ttu-id="a40e2-139">出力</span><span class="sxs-lookup"><span data-stu-id="a40e2-139">OUTPUTS</span></span>

### <span data-ttu-id="a40e2-140">なし</span><span class="sxs-lookup"><span data-stu-id="a40e2-140">None</span></span>

## <span data-ttu-id="a40e2-141">注</span><span class="sxs-lookup"><span data-stu-id="a40e2-141">NOTES</span></span>

<span data-ttu-id="a40e2-142">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a40e2-142">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="a40e2-143">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a40e2-143">RELATED LINKS</span></span>
