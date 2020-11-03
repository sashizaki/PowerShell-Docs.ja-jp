---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restore-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-Computer
ms.openlocfilehash: 824e9a24693c7a7de01358a048a0df55be333263
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214475"
---
# <span data-ttu-id="bab32-103">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="bab32-103">Restore-Computer</span></span>

## <span data-ttu-id="bab32-104">概要</span><span class="sxs-lookup"><span data-stu-id="bab32-104">SYNOPSIS</span></span>
<span data-ttu-id="bab32-105">ローカル コンピューターでシステムの復元を開始します。</span><span class="sxs-lookup"><span data-stu-id="bab32-105">Starts a system restore on the local computer.</span></span>

## <span data-ttu-id="bab32-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bab32-106">SYNTAX</span></span>

```
Restore-Computer [-RestorePoint] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="bab32-107">Description</span><span class="sxs-lookup"><span data-stu-id="bab32-107">DESCRIPTION</span></span>
<span data-ttu-id="bab32-108">**Restore Computer** コマンドレットは、指定したシステム復元ポイントにローカルコンピューターを復元します。</span><span class="sxs-lookup"><span data-stu-id="bab32-108">The **Restore-Computer** cmdlet restores the local computer to the specified system restore point.</span></span>

<span data-ttu-id="bab32-109">**復元-** コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="bab32-109">**Restore-Computer** restarts the computer.</span></span>
<span data-ttu-id="bab32-110">復元は再起動操作時に完了します。</span><span class="sxs-lookup"><span data-stu-id="bab32-110">The restore is completed during the restart operation.</span></span>

<span data-ttu-id="bab32-111">システムの復元ポイントと **復元-コンピューター** は、windows 7、windows Vista、windows XP などのクライアントオペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bab32-111">System restore points and **Restore-Computer** are supported only on client operating systems, such as Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="bab32-112">例</span><span class="sxs-lookup"><span data-stu-id="bab32-112">EXAMPLES</span></span>

### <span data-ttu-id="bab32-113">例 1: ローカルコンピューターを復元する</span><span class="sxs-lookup"><span data-stu-id="bab32-113">Example 1: Restore the local computer</span></span>

```
PS C:\> Restore-Computer -RestorePoint 253
```

<span data-ttu-id="bab32-114">このコマンドは、シーケンス番号253を持つ復元ポイントにローカルコンピューターを復元します。</span><span class="sxs-lookup"><span data-stu-id="bab32-114">This command restores the local computer to the restore point that has sequence number 253.</span></span>

### <span data-ttu-id="bab32-115">例 2: 確認を使用してローカルコンピューターを復元する</span><span class="sxs-lookup"><span data-stu-id="bab32-115">Example 2: Restore the local computer with confirmation</span></span>

```
PS C:\> Restore-Computer -RestorePoint 255 -Confirm
Confirm
Are you sure you want to perform this action?
Performing operation "Restore-Computer" .
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="bab32-116">このコマンドは、シーケンス番号255を持つ復元ポイントにローカルコンピューターを復元します。</span><span class="sxs-lookup"><span data-stu-id="bab32-116">This command restores the local computer to the restore point that has sequence number 255.</span></span>
<span data-ttu-id="bab32-117">*Confirm* パラメーターを使用して、実際に操作を実行する前にユーザーに確認メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="bab32-117">It uses the *Confirm* parameter to prompt the user before actually performing the operation.</span></span>

### <span data-ttu-id="bab32-118">例 3: コンピューターを復元して状態を確認する</span><span class="sxs-lookup"><span data-stu-id="bab32-118">Example 3: Restore a computer and check the status</span></span>

```
PS C:\> Get-ComputerRestorePoint
PS C:\> Restore-Computer -RestorePoint 255
PS C:\> Get-ComputerRestorePoint -LastStatus
```

<span data-ttu-id="bab32-119">これらのコマンドはシステムの復元を実行し、その状態をチェックします。</span><span class="sxs-lookup"><span data-stu-id="bab32-119">These commands run a system restore and then check its status.</span></span>

<span data-ttu-id="bab32-120">最初のコマンドは、 **Get ComputerRestorePoint** を使用して、ローカルコンピューター上の復元ポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="bab32-120">The first command uses **Get-ComputerRestorePoint** to get the restore points on the local computer.</span></span>

<span data-ttu-id="bab32-121">2番目のコマンドは、シーケンス番号255を使用してコンピュータを復元ポイントに復元します。</span><span class="sxs-lookup"><span data-stu-id="bab32-121">The second command restores the computer to the restore point with sequence number 255.</span></span>

<span data-ttu-id="bab32-122">3番目のコマンドは、 *Get ComputerRestorePoint* コマンドレットの *laststatus* パラメーターを使用して、復元操作の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="bab32-122">The third command uses the *LastStatus* parameter of *Get-ComputerRestorePoint* cmdlet to check the status of the restore operation.</span></span>
<span data-ttu-id="bab32-123">**復元コンピューター** によって再起動が強制されるため、このコマンドはコンピューターの再起動後に入力されます。</span><span class="sxs-lookup"><span data-stu-id="bab32-123">Because **Restore-Computer** forces a restart, this command would be entered after the computer restarts.</span></span>

## <span data-ttu-id="bab32-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bab32-124">PARAMETERS</span></span>

### <span data-ttu-id="bab32-125">-RestorePoint</span><span class="sxs-lookup"><span data-stu-id="bab32-125">-RestorePoint</span></span>
<span data-ttu-id="bab32-126">復元ポイントのシーケンス番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="bab32-126">Specifies the sequence number of the restore point.</span></span>
<span data-ttu-id="bab32-127">シーケンス番号を検索するには、Get-ComputerRestorePoint コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bab32-127">To find the sequence number, use the Get-ComputerRestorePoint cmdlet.</span></span>
<span data-ttu-id="bab32-128">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="bab32-128">This parameter is required.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: SequenceNumber, SN, RP

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bab32-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bab32-129">-Confirm</span></span>
<span data-ttu-id="bab32-130">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bab32-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bab32-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bab32-131">-WhatIf</span></span>
<span data-ttu-id="bab32-132">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="bab32-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="bab32-133">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="bab32-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bab32-134">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="bab32-134">CommonParameters</span></span>
<span data-ttu-id="bab32-135">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="bab32-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bab32-136">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bab32-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bab32-137">入力</span><span class="sxs-lookup"><span data-stu-id="bab32-137">INPUTS</span></span>

### <span data-ttu-id="bab32-138">なし</span><span class="sxs-lookup"><span data-stu-id="bab32-138">None</span></span>
<span data-ttu-id="bab32-139">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="bab32-139">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="bab32-140">出力</span><span class="sxs-lookup"><span data-stu-id="bab32-140">OUTPUTS</span></span>

### <span data-ttu-id="bab32-141">なし</span><span class="sxs-lookup"><span data-stu-id="bab32-141">None</span></span>
<span data-ttu-id="bab32-142">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="bab32-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="bab32-143">注</span><span class="sxs-lookup"><span data-stu-id="bab32-143">NOTES</span></span>

* <span data-ttu-id="bab32-144">Windows Vista 以降のバージョンの Windows オペレーティングシステムで Restore-Computer コマンドを実行するには、[管理者として実行] オプションを使用して Windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="bab32-144">To run a Restore-Computer command on Windows Vista and later versions of the Windows operating system, open Windows PowerShell by using the Run as administrator option.</span></span>
* <span data-ttu-id="bab32-145">このコマンドレットは、Windows Management Instrumentation (WMI) **Systemrestore** クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="bab32-145">This cmdlet uses the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

## <span data-ttu-id="bab32-146">関連リンク</span><span class="sxs-lookup"><span data-stu-id="bab32-146">RELATED LINKS</span></span>

[<span data-ttu-id="bab32-147">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="bab32-147">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="bab32-148">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="bab32-148">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="bab32-149">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="bab32-149">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="bab32-150">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="bab32-150">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="bab32-151">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="bab32-151">Restart-Computer</span></span>](Restart-Computer.md)
