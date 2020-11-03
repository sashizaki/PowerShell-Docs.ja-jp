---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/enable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ComputerRestore
ms.openlocfilehash: f9616a7f9af4dd2fa45e150bb64eef65427b4947
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215491"
---
# <span data-ttu-id="ac81d-103">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="ac81d-103">Enable-ComputerRestore</span></span>

## <span data-ttu-id="ac81d-104">概要</span><span class="sxs-lookup"><span data-stu-id="ac81d-104">SYNOPSIS</span></span>
<span data-ttu-id="ac81d-105">指定したファイル システム ドライブのシステム復元機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ac81d-105">Enables the System Restore feature on the specified file system drive.</span></span>

## <span data-ttu-id="ac81d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ac81d-106">SYNTAX</span></span>

```
Enable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ac81d-107">Description</span><span class="sxs-lookup"><span data-stu-id="ac81d-107">DESCRIPTION</span></span>
<span data-ttu-id="ac81d-108">**Computerrestore** コマンドレットは、1つまたは複数のファイルシステムドライブのシステム復元機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ac81d-108">The **Enable-ComputerRestore** cmdlet turns on the System Restore feature on one or more file system drives.</span></span>
<span data-ttu-id="ac81d-109">その結果、Restore-Computer コマンドレットなどのツールを使用してコンピューターを以前の状態に復元できます。</span><span class="sxs-lookup"><span data-stu-id="ac81d-109">As a result, you can use tools, such as the Restore-Computer cmdlet, to restore the computer to a previous state.</span></span>

<span data-ttu-id="ac81d-110">既定では、システム復元を使用できるすべてのドライブでシステム復元は有効ですが、Disable-ComputerRestore コマンドレットなどを使用して無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ac81d-110">By default, System Restore is enabled on all eligible drives, but you can disable it, such as by using the Disable-ComputerRestore cmdlet.</span></span>
<span data-ttu-id="ac81d-111">任意のドライブのシステム復元を有効に (または再び有効に) するには、システム ドライブ上でシステム復元を有効にする必要があります。これは最初にまたは同時に行います。</span><span class="sxs-lookup"><span data-stu-id="ac81d-111">To enable (or re-enable) System Restore on any drive, it must be enabled on the system drive, either first or concurrently.</span></span>
<span data-ttu-id="ac81d-112">各ドライブのシステム復元の状態を調べるには、Rstrui.exe を使用します。</span><span class="sxs-lookup"><span data-stu-id="ac81d-112">To find the state of System Restore for each drive, use Rstrui.exe.</span></span>

<span data-ttu-id="ac81d-113">システムの復元ポイントおよび ComputerRestore コマンドレットは、Windows 7、Windows Vista、Windows XP のようなクライアント オペレーティング システムだけでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ac81d-113">System restore points and the ComputerRestore cmdlets are supported only on client operating systems, such as Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="ac81d-114">例</span><span class="sxs-lookup"><span data-stu-id="ac81d-114">EXAMPLES</span></span>

### <span data-ttu-id="ac81d-115">例 1: 指定されたドライブでシステムの復元を有効にする</span><span class="sxs-lookup"><span data-stu-id="ac81d-115">Example 1: Enable System Restore on the specified drive</span></span>

```
PS C:\> Enable-ComputerRestore -Drive "C:\"
```

<span data-ttu-id="ac81d-116">このコマンドは、ローカル コンピューターの C ドライブのシステム復元を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ac81d-116">This command enables System Restore on the C: drive of the local computer.</span></span>

### <span data-ttu-id="ac81d-117">例 2: 複数のドライブでシステムの復元を有効にする</span><span class="sxs-lookup"><span data-stu-id="ac81d-117">Example 2: Enable System Restore on multiple drives</span></span>

```
PS C:\> Enable-ComputerRestore -Drive "C:\", "D:\"
```

<span data-ttu-id="ac81d-118">このコマンドは、ローカル コンピューターの C ドライブと D ドライブのシステム復元を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ac81d-118">This command enables System Restore on the C: and D: drives of the local computer.</span></span>

## <span data-ttu-id="ac81d-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ac81d-119">PARAMETERS</span></span>

### <span data-ttu-id="ac81d-120">-ドライブ</span><span class="sxs-lookup"><span data-stu-id="ac81d-120">-Drive</span></span>
<span data-ttu-id="ac81d-121">ファイル システム ドライブを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac81d-121">Specifies the file system drives.</span></span>
<span data-ttu-id="ac81d-122">1つまたは複数のファイルシステムドライブ文字を入力し、その後にコロンと円記号を入力して、C:\ などの引用符で囲みます。または D:\</span><span class="sxs-lookup"><span data-stu-id="ac81d-122">Enter one or more file system drive letters, each followed by a colon and a backslash and enclosed in quotation marks, such as C:\ or D:\.</span></span>
<span data-ttu-id="ac81d-123">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="ac81d-123">This parameter is required.</span></span>

<span data-ttu-id="ac81d-124">リモート ネットワーク ドライブは、ローカル コンピューターにマップされていてもこのコマンドレットを使用してシステム復元を有効にすることはできません。また、外部ドライブのようにシステム復元の対象にならないドライブのシステム復元を有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ac81d-124">You cannot use this cmdlet to enable System Restore on a remote network drive, even if the drive is mapped to the local computer, and you cannot enable System Restore on drives that are not eligible for System Restore, such as external drives.</span></span>

<span data-ttu-id="ac81d-125">任意のドライブのシステム復元を有効にするには、システム ドライブ上でシステム復元を有効にする必要があります。これは事前にまたは同時に行います。</span><span class="sxs-lookup"><span data-stu-id="ac81d-125">To enable System Restore on any drive, System Restore must be enabled on the system drive, either before or concurrently.</span></span>

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

### <span data-ttu-id="ac81d-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ac81d-126">-Confirm</span></span>
<span data-ttu-id="ac81d-127">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac81d-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ac81d-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ac81d-128">-WhatIf</span></span>
<span data-ttu-id="ac81d-129">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="ac81d-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ac81d-130">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="ac81d-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ac81d-131">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ac81d-131">CommonParameters</span></span>
<span data-ttu-id="ac81d-132">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ac81d-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ac81d-133">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac81d-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ac81d-134">入力</span><span class="sxs-lookup"><span data-stu-id="ac81d-134">INPUTS</span></span>

### <span data-ttu-id="ac81d-135">なし</span><span class="sxs-lookup"><span data-stu-id="ac81d-135">None</span></span>
<span data-ttu-id="ac81d-136">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="ac81d-136">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="ac81d-137">出力</span><span class="sxs-lookup"><span data-stu-id="ac81d-137">OUTPUTS</span></span>

### <span data-ttu-id="ac81d-138">なし</span><span class="sxs-lookup"><span data-stu-id="ac81d-138">None</span></span>
<span data-ttu-id="ac81d-139">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="ac81d-139">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ac81d-140">注</span><span class="sxs-lookup"><span data-stu-id="ac81d-140">NOTES</span></span>

* <span data-ttu-id="ac81d-141">Windows Vista 以降のバージョンの Windows でこのコマンドレットを実行するには、[管理者として実行] オプションを使用して Windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="ac81d-141">To run this cmdlet on Windows Vista and later versions of Windows, open Windows PowerShell with the Run as administrator option.</span></span>

  <span data-ttu-id="ac81d-142">システムの復元の対象となるファイルシステムドライブを調べるには、コントロールパネルの [システム] で、[システムの保護] タブを参照してください。Windows PowerShell でこのタブを開くには、「」と入力 `SystemPropertiesProtection` します。</span><span class="sxs-lookup"><span data-stu-id="ac81d-142">To find the file system drives that are eligible for system restore, in System in Control Panel, see the System Protection tab. To open this tab in Windows PowerShell, type `SystemPropertiesProtection`.</span></span>

  <span data-ttu-id="ac81d-143">このコマンドレットは、Windows Management Instrumentation (WMI) **Systemrestore** クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="ac81d-143">This cmdlet uses the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

*

## <span data-ttu-id="ac81d-144">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ac81d-144">RELATED LINKS</span></span>

[<span data-ttu-id="ac81d-145">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="ac81d-145">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="ac81d-146">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="ac81d-146">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="ac81d-147">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="ac81d-147">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="ac81d-148">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="ac81d-148">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="ac81d-149">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="ac81d-149">Restore-Computer</span></span>](Restore-Computer.md)
