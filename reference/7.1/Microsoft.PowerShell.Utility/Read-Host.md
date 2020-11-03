---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: b76fc092046a29dcad52f755794fd55dd84ac675
ms.sourcegitcommit: 57df49488015e7ac17ff1df402a94441aa6d6064
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "93217923"
---
# <span data-ttu-id="deece-103">Read-Host</span><span class="sxs-lookup"><span data-stu-id="deece-103">Read-Host</span></span>

## <span data-ttu-id="deece-104">概要</span><span class="sxs-lookup"><span data-stu-id="deece-104">SYNOPSIS</span></span>
<span data-ttu-id="deece-105">コンソールからの入力行を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="deece-105">Reads a line of input from the console.</span></span>

## <span data-ttu-id="deece-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="deece-106">SYNTAX</span></span>

### <span data-ttu-id="deece-107">AsString (既定値)</span><span class="sxs-lookup"><span data-stu-id="deece-107">AsString (Default)</span></span>

```
Read-Host [[-Prompt] <Object>] [-MaskInput] [<CommonParameters>]
```

### <span data-ttu-id="deece-108">AsSecureString</span><span class="sxs-lookup"><span data-stu-id="deece-108">AsSecureString</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="deece-109">Description</span><span class="sxs-lookup"><span data-stu-id="deece-109">DESCRIPTION</span></span>

<span data-ttu-id="deece-110">コマンドレットでは、 `Read-Host` コンソールから入力行を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="deece-110">The `Read-Host` cmdlet reads a line of input from the console.</span></span> <span data-ttu-id="deece-111">ユーザーに入力を求めるために使用できます。</span><span class="sxs-lookup"><span data-stu-id="deece-111">You can use it to prompt a user for input.</span></span> <span data-ttu-id="deece-112">セキュリティで保護された文字列として入力を保存できるため、このコマンドレットを使用して、パスワードなどのセキュリティで保護されたデータと共有データなどの入力をユーザーに求めることができます。</span><span class="sxs-lookup"><span data-stu-id="deece-112">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords, as well as shared data.</span></span>

## <span data-ttu-id="deece-113">例</span><span class="sxs-lookup"><span data-stu-id="deece-113">EXAMPLES</span></span>

### <span data-ttu-id="deece-114">例 1: コンソールの入力を変数に保存する</span><span class="sxs-lookup"><span data-stu-id="deece-114">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="deece-115">この例では、プロンプトとして "age:" という文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="deece-115">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="deece-116">値を入力し、Enter キーを押すと、値は変数に格納され `$Age` ます。</span><span class="sxs-lookup"><span data-stu-id="deece-116">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="deece-117">例 2: コンソール入力をセキュリティで保護された文字列として保存する</span><span class="sxs-lookup"><span data-stu-id="deece-117">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="deece-118">この例では、プロンプトとして "Enter a Password:" という文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="deece-118">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="deece-119">値が入力されると、 `*` 入力の代わりにアスタリスク () がコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="deece-119">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="deece-120">Enter キーを押すと、値は変数に **SecureString** オブジェクトとして格納され `$pwd_secure_string` ます。</span><span class="sxs-lookup"><span data-stu-id="deece-120">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

### <span data-ttu-id="deece-121">例 3: 入力をプレーンテキスト文字列としてマスクする</span><span class="sxs-lookup"><span data-stu-id="deece-121">Example 3: Mask input and as a plaintext string</span></span>

<span data-ttu-id="deece-122">この例では、プロンプトとして "Enter a Password:" という文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="deece-122">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="deece-123">値が入力されると、 `*` 入力の代わりにアスタリスク () がコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="deece-123">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="deece-124">Enter キーを押すと、値はプレーンテキスト **文字列** オブジェクトとして変数に格納され `$pwd_string` ます。</span><span class="sxs-lookup"><span data-stu-id="deece-124">When the Enter key is pressed, the value is stored as a plaintext **String** object in the `$pwd_string` variable.</span></span>

```powershell
$pwd_string = Read-Host "Enter a Password" -MaskInput
```

## <span data-ttu-id="deece-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="deece-125">PARAMETERS</span></span>

### <span data-ttu-id="deece-126">-AsSecureString</span><span class="sxs-lookup"><span data-stu-id="deece-126">-AsSecureString</span></span>

<span data-ttu-id="deece-127">コマンドレットによって、 `*` ユーザーが入力として入力した文字の代わりにアスタリスク () が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="deece-127">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="deece-128">このパラメーターを使用すると、 `Read-Host` コマンドレットの出力は **SecureString** オブジェクト ( **SecureString** ) になります。</span><span class="sxs-lookup"><span data-stu-id="deece-128">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object ( **System.Security.SecureString** ).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsSecureString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="deece-129">-MaskInput</span><span class="sxs-lookup"><span data-stu-id="deece-129">-MaskInput</span></span>

<span data-ttu-id="deece-130">コマンドレットによって、 `*` ユーザーが入力として入力した文字の代わりにアスタリスク () が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="deece-130">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="deece-131">このパラメーターを使用すると、 `Read-Host` コマンドレットの出力は **String** オブジェクトになります。</span><span class="sxs-lookup"><span data-stu-id="deece-131">When you use this parameter, the output of the `Read-Host` cmdlet is a **String** object.</span></span>
<span data-ttu-id="deece-132">これにより、 **SecureString** の代わりにプレーンテキストとして返されるパスワードの入力を安全に求めることができます。</span><span class="sxs-lookup"><span data-stu-id="deece-132">This allows you to safely prompt for a password that is returned as plaintext instead of **SecureString**.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="deece-133">-Prompt</span><span class="sxs-lookup"><span data-stu-id="deece-133">-Prompt</span></span>

<span data-ttu-id="deece-134">プロンプトのテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="deece-134">Specifies the text of the prompt.</span></span>
<span data-ttu-id="deece-135">文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="deece-135">Type a string.</span></span>
<span data-ttu-id="deece-136">文字列にスペースが含まれる場合は、二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="deece-136">If the string includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="deece-137">入力した `:` テキストに、PowerShell によってコロン () が追加されます。</span><span class="sxs-lookup"><span data-stu-id="deece-137">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="deece-138">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="deece-138">CommonParameters</span></span>

<span data-ttu-id="deece-139">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="deece-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="deece-140">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="deece-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="deece-141">入力</span><span class="sxs-lookup"><span data-stu-id="deece-141">INPUTS</span></span>

### <span data-ttu-id="deece-142">なし</span><span class="sxs-lookup"><span data-stu-id="deece-142">None</span></span>

<span data-ttu-id="deece-143">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="deece-143">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="deece-144">出力</span><span class="sxs-lookup"><span data-stu-id="deece-144">OUTPUTS</span></span>

### <span data-ttu-id="deece-145">System.string、または SecureString</span><span class="sxs-lookup"><span data-stu-id="deece-145">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="deece-146">**AsSecureString** パラメーターが使用されている場合、は `Read-Host` **SecureString** を返します。</span><span class="sxs-lookup"><span data-stu-id="deece-146">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString**.</span></span> <span data-ttu-id="deece-147">それ以外の場合、文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="deece-147">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="deece-148">注</span><span class="sxs-lookup"><span data-stu-id="deece-148">NOTES</span></span>

## <span data-ttu-id="deece-149">関連リンク</span><span class="sxs-lookup"><span data-stu-id="deece-149">RELATED LINKS</span></span>

[<span data-ttu-id="deece-150">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="deece-150">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="deece-151">Get-Host</span><span class="sxs-lookup"><span data-stu-id="deece-151">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="deece-152">Write-Host</span><span class="sxs-lookup"><span data-stu-id="deece-152">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="deece-153">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="deece-153">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
