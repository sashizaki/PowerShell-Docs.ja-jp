---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/disable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ComputerRestore
ms.openlocfilehash: 941829c3caa0f6bb2f5712dda9eb7d8c36908062
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215496"
---
# <span data-ttu-id="761d7-103">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="761d7-103">Disable-ComputerRestore</span></span>

## <span data-ttu-id="761d7-104">概要</span><span class="sxs-lookup"><span data-stu-id="761d7-104">SYNOPSIS</span></span>
<span data-ttu-id="761d7-105">指定したファイル システム ドライブのシステム復元機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="761d7-105">Disables the System Restore feature on the specified file system drive.</span></span>

## <span data-ttu-id="761d7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="761d7-106">SYNTAX</span></span>

```
Disable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="761d7-107">Description</span><span class="sxs-lookup"><span data-stu-id="761d7-107">DESCRIPTION</span></span>
<span data-ttu-id="761d7-108">**Computerrestore** コマンドレットは、1つまたは複数のファイルシステムドライブのシステム復元機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="761d7-108">The **Disable-ComputerRestore** cmdlet turns off the System Restore feature on one or more file system drives.</span></span>
<span data-ttu-id="761d7-109">その結果、指定したドライブはコンピューターを復元する際の対象になりません。</span><span class="sxs-lookup"><span data-stu-id="761d7-109">As a result, attempts to restore the computer do not affect the specified drive.</span></span>

<span data-ttu-id="761d7-110">ドライブのシステム復元を無効にするには、システム ドライブ上で無効にする必要があります。これは最初にまたは同時に行います。</span><span class="sxs-lookup"><span data-stu-id="761d7-110">To disable System Restore on any drive, it must be disabled on the system drive, either first or concurrently.</span></span>

<span data-ttu-id="761d7-111">システム復元を再び有効にするには、Enable-ComputerRestore コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="761d7-111">To re-enable System Restore, use the Enable-ComputerRestore cmdlet.</span></span>
<span data-ttu-id="761d7-112">各ドライブのシステム復元の状態を調べるには、Rstrui.exe を使用します。</span><span class="sxs-lookup"><span data-stu-id="761d7-112">To find the state of System Restore for each drive, use Rstrui.exe.</span></span>

<span data-ttu-id="761d7-113">システムの復元ポイントおよび ComputerRestore コマンドレットは、Windows 7、Windows Vista、Windows XP のようなクライアント オペレーティング システムだけでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="761d7-113">System restore points and the ComputerRestore cmdlets are supported only on client operating systems, such as Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="761d7-114">例</span><span class="sxs-lookup"><span data-stu-id="761d7-114">EXAMPLES</span></span>

### <span data-ttu-id="761d7-115">例 1: 指定されたドライブでシステムの復元を無効にする</span><span class="sxs-lookup"><span data-stu-id="761d7-115">Example 1: Disable System Restore on the specified drive</span></span>

```
PS C:\> Disable-ComputerRestore -Drive "C:\"
```

<span data-ttu-id="761d7-116">このコマンドは、C ドライブのシステム復元を無効にします。</span><span class="sxs-lookup"><span data-stu-id="761d7-116">This command disables System Restore on the C: drive.</span></span>

### <span data-ttu-id="761d7-117">例 2: 複数のドライブのシステム復元を無効にする</span><span class="sxs-lookup"><span data-stu-id="761d7-117">Example 2: Disable System Restore on multiple drives</span></span>

```
PS C:\> Disable-ComputerRestore "C:\", "D:\"
```

<span data-ttu-id="761d7-118">このコマンドは、C ドライブおよび D ドライブのシステム復元を無効にします。</span><span class="sxs-lookup"><span data-stu-id="761d7-118">This command disables System Restore on the C: and D: drives.</span></span>
<span data-ttu-id="761d7-119">このコマンドでは *drive* パラメーターを使用しますが、ドライブパラメーター名は省略しています。</span><span class="sxs-lookup"><span data-stu-id="761d7-119">The command uses the *Drive* parameter, but it omits the Drive parameter name.</span></span>

## <span data-ttu-id="761d7-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="761d7-120">PARAMETERS</span></span>

### <span data-ttu-id="761d7-121">-ドライブ</span><span class="sxs-lookup"><span data-stu-id="761d7-121">-Drive</span></span>
<span data-ttu-id="761d7-122">ファイル システム ドライブを指定します。</span><span class="sxs-lookup"><span data-stu-id="761d7-122">Specifies the file system drives.</span></span>
<span data-ttu-id="761d7-123">1つまたは複数のファイルシステムドライブ文字を入力し、その後にコロンと円記号を入力して、C:\ などの引用符で囲みます。または D:\</span><span class="sxs-lookup"><span data-stu-id="761d7-123">Enter one or more file system drive letters, each followed by a colon and a backslash and enclosed in quotation marks, such as C:\ or D:\.</span></span>
<span data-ttu-id="761d7-124">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="761d7-124">This parameter is required.</span></span>

<span data-ttu-id="761d7-125">リモート ネットワーク ドライブは、ローカル コンピューターにマップされていてもこのコマンドレットを使用してシステム復元を無効にすることはできません。また、外部ドライブのようにシステム復元の対象にならないドライブのシステム復元を無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="761d7-125">You cannot use this cmdlet to disable System Restore on a remote network drive, even if the drive is mapped to the local computer, and you cannot disable System Restore on drives that are not eligible for System Restore, such as external drives.</span></span>

<span data-ttu-id="761d7-126">ドライブのシステム復元を無効にするには、システム ドライブ上でシステム復元を無効にする必要があります。これは事前にまたは同時に行います。</span><span class="sxs-lookup"><span data-stu-id="761d7-126">To disable System Restore on any drive, System Restore must be disabled on the system drive, either before or concurrently.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="761d7-127">-Confirm</span><span class="sxs-lookup"><span data-stu-id="761d7-127">-Confirm</span></span>
<span data-ttu-id="761d7-128">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="761d7-128">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="761d7-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="761d7-129">-WhatIf</span></span>
<span data-ttu-id="761d7-130">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="761d7-130">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="761d7-131">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="761d7-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="761d7-132">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="761d7-132">CommonParameters</span></span>
<span data-ttu-id="761d7-133">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="761d7-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="761d7-134">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="761d7-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="761d7-135">入力</span><span class="sxs-lookup"><span data-stu-id="761d7-135">INPUTS</span></span>

### <span data-ttu-id="761d7-136">なし</span><span class="sxs-lookup"><span data-stu-id="761d7-136">None</span></span>
<span data-ttu-id="761d7-137">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="761d7-137">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="761d7-138">出力</span><span class="sxs-lookup"><span data-stu-id="761d7-138">OUTPUTS</span></span>

### <span data-ttu-id="761d7-139">なし</span><span class="sxs-lookup"><span data-stu-id="761d7-139">None</span></span>
<span data-ttu-id="761d7-140">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="761d7-140">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="761d7-141">注</span><span class="sxs-lookup"><span data-stu-id="761d7-141">NOTES</span></span>

* <span data-ttu-id="761d7-142">Windows Vista 以降のバージョンの Windows でこのコマンドレットを実行するには、[管理者として実行] オプションを使用して Windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="761d7-142">To run this cmdlet on Windows Vista and later versions of Windows, open Windows PowerShell with the Run as administrator option.</span></span>

  <span data-ttu-id="761d7-143">システムの復元の対象となるファイルシステムドライブを調べるには、コントロールパネルの [システム] で、[システムの保護] タブを参照してください。Windows PowerShell でこのタブを開くには、「」と入力 `SystemPropertiesProtection` します。</span><span class="sxs-lookup"><span data-stu-id="761d7-143">To find the file system drives that are eligible for system restore, in System in Control Panel, see the System Protection tab. To open this tab in Windows PowerShell, type `SystemPropertiesProtection`.</span></span>

  <span data-ttu-id="761d7-144">このコマンドレットは、Windows Management Instrumentation (WMI) **Systemrestore** クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="761d7-144">This cmdlet uses the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

*

## <span data-ttu-id="761d7-145">関連リンク</span><span class="sxs-lookup"><span data-stu-id="761d7-145">RELATED LINKS</span></span>

[<span data-ttu-id="761d7-146">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="761d7-146">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="761d7-147">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="761d7-147">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="761d7-148">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="761d7-148">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="761d7-149">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="761d7-149">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="761d7-150">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="761d7-150">Restore-Computer</span></span>](Restore-Computer.md)
