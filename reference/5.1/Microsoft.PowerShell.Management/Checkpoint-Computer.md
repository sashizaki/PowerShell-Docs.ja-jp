---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/checkpoint-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Checkpoint-Computer
ms.openlocfilehash: 61f8d626cd45cfe47f0e65a3043696a01c97ca20
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215608"
---
# <span data-ttu-id="36ec0-103">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="36ec0-103">Checkpoint-Computer</span></span>

## <span data-ttu-id="36ec0-104">概要</span><span class="sxs-lookup"><span data-stu-id="36ec0-104">SYNOPSIS</span></span>
<span data-ttu-id="36ec0-105">ローカル コンピューターのシステム復元ポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="36ec0-105">Creates a system restore point on the local computer.</span></span>

## <span data-ttu-id="36ec0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="36ec0-106">SYNTAX</span></span>

```
Checkpoint-Computer [-Description] <String> [[-RestorePointType] <String>] [<CommonParameters>]
```

## <span data-ttu-id="36ec0-107">Description</span><span class="sxs-lookup"><span data-stu-id="36ec0-107">DESCRIPTION</span></span>

<span data-ttu-id="36ec0-108">コマンドレットにより、 `Checkpoint-Computer` システムの復元ポイントがローカルコンピューター上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="36ec0-108">The `Checkpoint-Computer` cmdlet creates a system restore point on the local computer.</span></span>

<span data-ttu-id="36ec0-109">システムの復元ポイントと `Checkpoint-Computer` コマンドレットは、windows 8、windows 7、Windows Vista、WINDOWS XP などのクライアントオペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="36ec0-109">System restore points and the `Checkpoint-Computer` cmdlet are supported only on client operating systems, such as Windows 8, Windows 7, Windows Vista, and Windows XP.</span></span>

<span data-ttu-id="36ec0-110">Windows 8 以降では、1日に複数の `Checkpoint-Computer` チェックポイントを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="36ec0-110">Beginning in Windows 8, `Checkpoint-Computer` cannot create more than one checkpoint each day.</span></span>

## <span data-ttu-id="36ec0-111">例</span><span class="sxs-lookup"><span data-stu-id="36ec0-111">EXAMPLES</span></span>

### <span data-ttu-id="36ec0-112">例 1: システムの復元ポイントを作成する</span><span class="sxs-lookup"><span data-stu-id="36ec0-112">Example 1: Create a system restore point</span></span>

```powershell
Checkpoint-Computer -Description "Install MyApp"
```

<span data-ttu-id="36ec0-113">このコマンドは、Install MyApp というシステム復元ポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="36ec0-113">This command creates a system restore point called Install MyApp.</span></span>
<span data-ttu-id="36ec0-114">復元ポイントの種類には、既定値の APPLICATION_INSTALL を使用します。</span><span class="sxs-lookup"><span data-stu-id="36ec0-114">It uses the default APPLICATION_INSTALL restore point type.</span></span>

### <span data-ttu-id="36ec0-115">例 2: システム MODIFY_SETTINGS の復元ポイントを作成する</span><span class="sxs-lookup"><span data-stu-id="36ec0-115">Example 2: Create a system MODIFY_SETTINGS restore point</span></span>

```powershell
Checkpoint-Computer -Description "ChangeNetSettings" -RestorePointType MODIFY_SETTINGS
```

<span data-ttu-id="36ec0-116">このコマンドは、"ChangeNetSettings" という名前の MODIFY_SETTINGS システム復元ポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="36ec0-116">This command creates a MODIFY_SETTINGS system restore point called "ChangeNetSettings".</span></span>

## <span data-ttu-id="36ec0-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="36ec0-117">PARAMETERS</span></span>

### <span data-ttu-id="36ec0-118">-Description</span><span class="sxs-lookup"><span data-stu-id="36ec0-118">-Description</span></span>

<span data-ttu-id="36ec0-119">復元ポイントのわかりやすい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="36ec0-119">Specifies a descriptive name for the restore point.</span></span>
<span data-ttu-id="36ec0-120">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="36ec0-120">This parameter is required.</span></span>

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

### <span data-ttu-id="36ec0-121">-RestorePointType</span><span class="sxs-lookup"><span data-stu-id="36ec0-121">-RestorePointType</span></span>

<span data-ttu-id="36ec0-122">復元ポイントの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="36ec0-122">Specifies the type of restore point.</span></span>
<span data-ttu-id="36ec0-123">既定値は APPLICATION_INSTALL です。</span><span class="sxs-lookup"><span data-stu-id="36ec0-123">The default is APPLICATION_INSTALL.</span></span>

<span data-ttu-id="36ec0-124">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="36ec0-124">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="36ec0-125">APPLICATION_INSTALL</span><span class="sxs-lookup"><span data-stu-id="36ec0-125">APPLICATION_INSTALL</span></span>
- <span data-ttu-id="36ec0-126">APPLICATION_UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="36ec0-126">APPLICATION_UNINSTALL</span></span>
- <span data-ttu-id="36ec0-127">DEVICE_DRIVER_INSTALL</span><span class="sxs-lookup"><span data-stu-id="36ec0-127">DEVICE_DRIVER_INSTALL</span></span>
- <span data-ttu-id="36ec0-128">MODIFY_SETTINGS</span><span class="sxs-lookup"><span data-stu-id="36ec0-128">MODIFY_SETTINGS</span></span>
- <span data-ttu-id="36ec0-129">CANCELLED_OPERATION</span><span class="sxs-lookup"><span data-stu-id="36ec0-129">CANCELLED_OPERATION</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RPT
Accepted values: APPLICATION_INSTALL, APPLICATION_UNINSTALL, DEVICE_DRIVER_INSTALL, MODIFY_SETTINGS, CANCELLED_OPERATION

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="36ec0-130">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="36ec0-130">CommonParameters</span></span>

<span data-ttu-id="36ec0-131">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="36ec0-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="36ec0-132">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36ec0-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="36ec0-133">入力</span><span class="sxs-lookup"><span data-stu-id="36ec0-133">INPUTS</span></span>

### <span data-ttu-id="36ec0-134">なし</span><span class="sxs-lookup"><span data-stu-id="36ec0-134">None</span></span>

<span data-ttu-id="36ec0-135">パイプを使用してオブジェクトをにパイプすることはできません `Checkpoint-Computer` 。</span><span class="sxs-lookup"><span data-stu-id="36ec0-135">You cannot pipe objects to `Checkpoint-Computer`.</span></span>

## <span data-ttu-id="36ec0-136">出力</span><span class="sxs-lookup"><span data-stu-id="36ec0-136">OUTPUTS</span></span>

### <span data-ttu-id="36ec0-137">なし</span><span class="sxs-lookup"><span data-stu-id="36ec0-137">None</span></span>

<span data-ttu-id="36ec0-138">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="36ec0-138">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="36ec0-139">注</span><span class="sxs-lookup"><span data-stu-id="36ec0-139">NOTES</span></span>

- <span data-ttu-id="36ec0-140">このコマンドレットは、 **Systemrestore** クラスの **Createrestorepoint** メソッドを **BEGIN_SYSTEM_CHANGE** イベントと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="36ec0-140">This cmdlet uses the **CreateRestorePoint** method of the **SystemRestore** class with a **BEGIN_SYSTEM_CHANGE** event.</span></span>
- <span data-ttu-id="36ec0-141">Windows 8 以降では、1日に複数の `Checkpoint-Computer` システム復元ポイントを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="36ec0-141">Beginning in Windows 8, `Checkpoint-Computer` cannot create more than one system restore point each day.</span></span> <span data-ttu-id="36ec0-142">24 時間が経過する前に新しい復元ポイントを作成しようとすると、Windows PowerShell によって次のエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="36ec0-142">If you try to create a new restore point before the 24-hour period has elapsed, Windows PowerShell generates the following error:</span></span>

  `"A new system restore point cannot be created because one has already been created within the past 24 hours.
  Please try again later."`

## <span data-ttu-id="36ec0-143">関連リンク</span><span class="sxs-lookup"><span data-stu-id="36ec0-143">RELATED LINKS</span></span>

[<span data-ttu-id="36ec0-144">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="36ec0-144">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="36ec0-145">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="36ec0-145">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="36ec0-146">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="36ec0-146">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="36ec0-147">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="36ec0-147">Restore-Computer</span></span>](Restore-Computer.md)
