---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/reset-computermachinepassword?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-ComputerMachinePassword
ms.openlocfilehash: 1484bc83b9503ce43420b833a1b78b3c4215d98a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214488"
---
# <span data-ttu-id="fd39c-103">Reset-ComputerMachinePassword</span><span class="sxs-lookup"><span data-stu-id="fd39c-103">Reset-ComputerMachinePassword</span></span>

## <span data-ttu-id="fd39c-104">概要</span><span class="sxs-lookup"><span data-stu-id="fd39c-104">SYNOPSIS</span></span>
<span data-ttu-id="fd39c-105">コンピューターのアカウントのパスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="fd39c-105">Resets the machine account password for the computer.</span></span>

## <span data-ttu-id="fd39c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fd39c-106">SYNTAX</span></span>

```
Reset-ComputerMachinePassword [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="fd39c-107">Description</span><span class="sxs-lookup"><span data-stu-id="fd39c-107">DESCRIPTION</span></span>
<span data-ttu-id="fd39c-108">コンピューターがドメイン内のドメインコントローラーに対する認証に使用するコンピューターアカウント **のパスワードを変更します** 。</span><span class="sxs-lookup"><span data-stu-id="fd39c-108">The **Reset-ComputerMachinePassword** cmdlet changes the computer account password that the computers use to authenticate to the domain controllers in the domain.</span></span>
<span data-ttu-id="fd39c-109">ローカル コンピューターのパスワードをリセットするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="fd39c-109">You can use it to reset the password of the local computer.</span></span>

## <span data-ttu-id="fd39c-110">例</span><span class="sxs-lookup"><span data-stu-id="fd39c-110">EXAMPLES</span></span>

### <span data-ttu-id="fd39c-111">例 1: ローカルコンピューターのパスワードをリセットする</span><span class="sxs-lookup"><span data-stu-id="fd39c-111">Example 1: Reset the password for the local computer</span></span>

```
PS C:\> Reset-ComputerMachinePassword
```

<span data-ttu-id="fd39c-112">このコマンドは、ローカルコンピューターのコンピューターパスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="fd39c-112">This command resets the computer password for the local computer.</span></span>
<span data-ttu-id="fd39c-113">コマンドは、現在のユーザーの資格情報で実行されます。</span><span class="sxs-lookup"><span data-stu-id="fd39c-113">The command runs with the credentials of the current user.</span></span>

### <span data-ttu-id="fd39c-114">例 2: 指定したドメインコントローラーを使用してローカルコンピューターのパスワードをリセットする</span><span class="sxs-lookup"><span data-stu-id="fd39c-114">Example 2: Reset the password for the local computer by using a specified domain controller</span></span>

```
PS C:\> Reset-ComputerMachinePassword -Server "DC01" -Credential Domain01\Admin01
```

<span data-ttu-id="fd39c-115">このコマンドは、DC01 ドメインコントローラーを使用して、ローカルコンピューターのコンピューターパスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="fd39c-115">This command resets the computer password of the local computer by using the DC01 domain controller.</span></span>
<span data-ttu-id="fd39c-116">*Credential* パラメーターを使用して、ドメイン内のコンピューターパスワードをリセットするアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="fd39c-116">It uses the *Credential* parameter to specify a user account that has permission to reset a computer password in the domain.</span></span>

### <span data-ttu-id="fd39c-117">例 3: リモートコンピューターのパスワードをリセットする</span><span class="sxs-lookup"><span data-stu-id="fd39c-117">Example 3: Reset the password on a remote computer</span></span>

```
$cred = Get-Credential
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Reset-ComputerMachinePassword -Credential $using:cred}
```

<span data-ttu-id="fd39c-118">このコマンドは、Invoke-Command コマンドレットを使用して、Server01 リモートコンピューター上で **Reset-ComputerMachinePassword** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd39c-118">This command uses the Invoke-Command cmdlet to run a **Reset-ComputerMachinePassword** command on the Server01 remote computer.</span></span>

<span data-ttu-id="fd39c-119">Windows PowerShell のリモート コマンドの詳細については、「about_Remote」および「 **Invoke-Command** 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd39c-119">For more information about remote commands in Windows PowerShell, see about_Remote and **Invoke-Command** .</span></span>

## <span data-ttu-id="fd39c-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fd39c-120">PARAMETERS</span></span>

### <span data-ttu-id="fd39c-121">-Credential</span><span class="sxs-lookup"><span data-stu-id="fd39c-121">-Credential</span></span>
<span data-ttu-id="fd39c-122">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="fd39c-122">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="fd39c-123">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="fd39c-123">The default is the current user.</span></span>

<span data-ttu-id="fd39c-124">User01 や Domain01\user01」などのユーザー名を入力するか、Get-Credential コマンドレットによって生成された **PSCredential** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="fd39c-124">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="fd39c-125">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="fd39c-125">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="fd39c-126">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd39c-126">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd39c-127">-Server</span><span class="sxs-lookup"><span data-stu-id="fd39c-127">-Server</span></span>
<span data-ttu-id="fd39c-128">このコマンドレットでコンピューターアカウントのパスワードを設定するときに使用するドメインコントローラーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fd39c-128">Specifies the name of a domain controller to use when this cmdlet sets the computer account password.</span></span>

<span data-ttu-id="fd39c-129">このパラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="fd39c-129">This parameter is optional.</span></span>
<span data-ttu-id="fd39c-130">このパラメーターを省略した場合は、コマンドにサービスを提供するドメイン コントローラーが選択されます。</span><span class="sxs-lookup"><span data-stu-id="fd39c-130">If you omit this parameter, a domain controller is chosen to service the command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd39c-131">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fd39c-131">-Confirm</span></span>
<span data-ttu-id="fd39c-132">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd39c-132">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fd39c-133">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fd39c-133">-WhatIf</span></span>
<span data-ttu-id="fd39c-134">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="fd39c-134">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="fd39c-135">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="fd39c-135">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fd39c-136">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fd39c-136">CommonParameters</span></span>
<span data-ttu-id="fd39c-137">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="fd39c-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fd39c-138">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd39c-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fd39c-139">入力</span><span class="sxs-lookup"><span data-stu-id="fd39c-139">INPUTS</span></span>

### <span data-ttu-id="fd39c-140">なし</span><span class="sxs-lookup"><span data-stu-id="fd39c-140">None</span></span>
<span data-ttu-id="fd39c-141">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="fd39c-141">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="fd39c-142">出力</span><span class="sxs-lookup"><span data-stu-id="fd39c-142">OUTPUTS</span></span>

### <span data-ttu-id="fd39c-143">なし</span><span class="sxs-lookup"><span data-stu-id="fd39c-143">None</span></span>
<span data-ttu-id="fd39c-144">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="fd39c-144">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="fd39c-145">注</span><span class="sxs-lookup"><span data-stu-id="fd39c-145">NOTES</span></span>

## <span data-ttu-id="fd39c-146">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fd39c-146">RELATED LINKS</span></span>

## <span data-ttu-id="fd39c-147">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fd39c-147">RELATED LINKS</span></span>
