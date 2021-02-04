---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/29/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: f59cc9ff4e6d1b6579292c84f440bbbdd156b65c
ms.sourcegitcommit: 81558c2adb9d109946a027e5b96e4d24b3b13747
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2021
ms.locfileid: "99098565"
---
# <span data-ttu-id="91578-102">Clear-RecycleBin</span><span class="sxs-lookup"><span data-stu-id="91578-102">Clear-RecycleBin</span></span>

## <span data-ttu-id="91578-103">概要</span><span class="sxs-lookup"><span data-stu-id="91578-103">SYNOPSIS</span></span>
<span data-ttu-id="91578-104">ごみ箱の内容をクリアします。</span><span class="sxs-lookup"><span data-stu-id="91578-104">Clears the contents of a recycle bin.</span></span>

## <span data-ttu-id="91578-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="91578-105">SYNTAX</span></span>

### <span data-ttu-id="91578-106">すべて</span><span class="sxs-lookup"><span data-stu-id="91578-106">All</span></span>

```
Clear-RecycleBin [[-DriveLetter] <String[]>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="91578-107">Description</span><span class="sxs-lookup"><span data-stu-id="91578-107">DESCRIPTION</span></span>

<span data-ttu-id="91578-108">`Clear-RecycleBin`コマンドレットは、コンピューターのごみ箱の内容を削除します。</span><span class="sxs-lookup"><span data-stu-id="91578-108">The `Clear-RecycleBin` cmdlet deletes the content of a computer's recycle bin.</span></span> <span data-ttu-id="91578-109">この操作は、Windows の **空のごみ箱** の使用に似ています。</span><span class="sxs-lookup"><span data-stu-id="91578-109">This action is like using Windows **Empty Recycle Bin**.</span></span>

## <span data-ttu-id="91578-110">例</span><span class="sxs-lookup"><span data-stu-id="91578-110">EXAMPLES</span></span>

### <span data-ttu-id="91578-111">1: すべてのごみ箱をクリアします。</span><span class="sxs-lookup"><span data-stu-id="91578-111">1: Clear all recycle bins</span></span>

<span data-ttu-id="91578-112">この例では、すべてのローカルコンピューターのごみ箱がクリアされています。</span><span class="sxs-lookup"><span data-stu-id="91578-112">In this example, all the local computer's recycle bins are cleared.</span></span>

```powershell
Clear-RecycleBin
```

```Output
Confirm
Are you sure you want to perform this action?
Performing the operation "Clear-RecycleBin" on target "All of the contents of the Recycle Bin".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="91578-113">`Clear-RecycleBin` ローカルコンピューター上のすべてのごみ箱をクリアするかどうかを確認するメッセージをユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="91578-113">`Clear-RecycleBin` prompts the user for confirmation to clear all recycle bins on the local computer.</span></span>

### <span data-ttu-id="91578-114">2: 指定されたごみ箱をクリアします</span><span class="sxs-lookup"><span data-stu-id="91578-114">2: Clear a specified recycle bin</span></span>

<span data-ttu-id="91578-115">この例では、指定されたドライブ文字のごみ箱をクリアします。</span><span class="sxs-lookup"><span data-stu-id="91578-115">This example clears the recycle bin for a specified drive letter.</span></span>

```powershell
Clear-RecycleBin -DriveLetter C
```

<span data-ttu-id="91578-116">`Clear-RecycleBin`**ドライブ** 文字パラメーターを使用して、 **C** ボリュームにごみ箱を指定します。</span><span class="sxs-lookup"><span data-stu-id="91578-116">`Clear-RecycleBin` uses the **DriveLetter** parameter to specify the recycle bin on the **C** volume.</span></span> <span data-ttu-id="91578-117">コマンドを実行するかどうかを確認するメッセージがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="91578-117">The user is prompted for confirmation to run the command.</span></span>

### <span data-ttu-id="91578-118">3: 確認せずにすべてのごみ箱をクリアする</span><span class="sxs-lookup"><span data-stu-id="91578-118">3: Clear all recycle bins without confirmation</span></span>

<span data-ttu-id="91578-119">この例では、ローカルコンピューターのごみ箱をクリアするかどうかを確認するプロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="91578-119">This example doesn't prompt for confirmation to clear the local computer's recycle bins.</span></span>

```powershell
Clear-RecycleBin -Force
```

<span data-ttu-id="91578-120">`Clear-RecycleBin`**Force** パラメーターを使用し、ローカルコンピューター上のすべてのごみ箱をクリアするかどうかを確認するメッセージをユーザーに表示しません。</span><span class="sxs-lookup"><span data-stu-id="91578-120">`Clear-RecycleBin` uses the **Force** parameter and doesn't prompt the user for confirmation to clear all recycle bins on the local computer.</span></span>

<span data-ttu-id="91578-121">別の方法と `-Force` して、をに置き換え `-Confirm:$false` ます。</span><span class="sxs-lookup"><span data-stu-id="91578-121">An alternative is to replace `-Force` with `-Confirm:$false`.</span></span>

## <span data-ttu-id="91578-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="91578-122">PARAMETERS</span></span>

### <span data-ttu-id="91578-123">-ドライブ文字</span><span class="sxs-lookup"><span data-stu-id="91578-123">-DriveLetter</span></span>

<span data-ttu-id="91578-124">1つのドライブ文字またはドライブ文字の配列に対してクリアするごみ箱を指定します。</span><span class="sxs-lookup"><span data-stu-id="91578-124">Specifies the recycle bin to clear for a single drive letter or an array of drive letters.</span></span>

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

### <span data-ttu-id="91578-125">-Force</span><span class="sxs-lookup"><span data-stu-id="91578-125">-Force</span></span>

<span data-ttu-id="91578-126">ごみ箱をクリアするかどうかを確認するメッセージがユーザーに表示されないように指定します。</span><span class="sxs-lookup"><span data-stu-id="91578-126">Specifies that the user isn't prompted for confirmation to clear a recycle bin.</span></span> <span data-ttu-id="91578-127">**Force** パラメーターは、 **WhatIf** パラメーターと **Confirm** パラメーターもオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="91578-127">The **Force** parameter also overrides the **WhatIf** and **Confirm** parameters.</span></span>

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

### <span data-ttu-id="91578-128">-Confirm</span><span class="sxs-lookup"><span data-stu-id="91578-128">-Confirm</span></span>

<span data-ttu-id="91578-129">コマンドレットを実行する前に、ユーザーに確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="91578-129">Prompts for user confirmation before running the cmdlet.</span></span> <span data-ttu-id="91578-130">**Confirm** パラメーターが指定されていない場合でも、ユーザーに確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="91578-130">The user is prompted for confirmation even if the **Confirm** parameter isn't specified.</span></span>

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

### <span data-ttu-id="91578-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="91578-131">-WhatIf</span></span>

<span data-ttu-id="91578-132">が実行された場合に何が起こるか `Clear-RecycleBin` を示します。</span><span class="sxs-lookup"><span data-stu-id="91578-132">Shows what would happen if `Clear-RecycleBin` runs.</span></span> <span data-ttu-id="91578-133">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="91578-133">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="91578-134">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="91578-134">CommonParameters</span></span>

<span data-ttu-id="91578-135">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="91578-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="91578-136">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91578-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="91578-137">入力</span><span class="sxs-lookup"><span data-stu-id="91578-137">INPUTS</span></span>

## <span data-ttu-id="91578-138">出力</span><span class="sxs-lookup"><span data-stu-id="91578-138">OUTPUTS</span></span>

### <span data-ttu-id="91578-139">なし</span><span class="sxs-lookup"><span data-stu-id="91578-139">None</span></span>

## <span data-ttu-id="91578-140">注</span><span class="sxs-lookup"><span data-stu-id="91578-140">NOTES</span></span>

## <span data-ttu-id="91578-141">関連リンク</span><span class="sxs-lookup"><span data-stu-id="91578-141">RELATED LINKS</span></span>
