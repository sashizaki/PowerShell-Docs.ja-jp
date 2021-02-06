---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: 2efe75730ef7d35618dc0d1fbf7a8d6f8a5db5ae
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605444"
---
# <span data-ttu-id="a0c41-102">Read-Host</span><span class="sxs-lookup"><span data-stu-id="a0c41-102">Read-Host</span></span>

## <span data-ttu-id="a0c41-103">概要</span><span class="sxs-lookup"><span data-stu-id="a0c41-103">SYNOPSIS</span></span>
<span data-ttu-id="a0c41-104">コンソールからの入力行を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="a0c41-104">Reads a line of input from the console.</span></span>

## <span data-ttu-id="a0c41-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a0c41-105">SYNTAX</span></span>

### <span data-ttu-id="a0c41-106">AsString (既定値)</span><span class="sxs-lookup"><span data-stu-id="a0c41-106">AsString (Default)</span></span>

```
Read-Host [[-Prompt] <Object>] [-MaskInput] [<CommonParameters>]
```

### <span data-ttu-id="a0c41-107">AsSecureString</span><span class="sxs-lookup"><span data-stu-id="a0c41-107">AsSecureString</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="a0c41-108">Description</span><span class="sxs-lookup"><span data-stu-id="a0c41-108">DESCRIPTION</span></span>

<span data-ttu-id="a0c41-109">コマンドレットでは、 `Read-Host` コンソールから入力行を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="a0c41-109">The `Read-Host` cmdlet reads a line of input from the console.</span></span> <span data-ttu-id="a0c41-110">ユーザーに入力を求めるために使用できます。</span><span class="sxs-lookup"><span data-stu-id="a0c41-110">You can use it to prompt a user for input.</span></span> <span data-ttu-id="a0c41-111">セキュリティで保護された文字列として入力を保存できるため、このコマンドレットを使用して、パスワードなどのセキュリティで保護されたデータと共有データなどの入力をユーザーに求めることができます。</span><span class="sxs-lookup"><span data-stu-id="a0c41-111">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords, as well as shared data.</span></span>

## <span data-ttu-id="a0c41-112">例</span><span class="sxs-lookup"><span data-stu-id="a0c41-112">EXAMPLES</span></span>

### <span data-ttu-id="a0c41-113">例 1: コンソールの入力を変数に保存する</span><span class="sxs-lookup"><span data-stu-id="a0c41-113">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="a0c41-114">この例では、プロンプトとして "age:" という文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0c41-114">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="a0c41-115">値を入力し、Enter キーを押すと、値は変数に格納され `$Age` ます。</span><span class="sxs-lookup"><span data-stu-id="a0c41-115">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="a0c41-116">例 2: コンソール入力をセキュリティで保護された文字列として保存する</span><span class="sxs-lookup"><span data-stu-id="a0c41-116">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="a0c41-117">この例では、プロンプトとして "Enter a Password:" という文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0c41-117">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="a0c41-118">値が入力されると、 `*` 入力の代わりにアスタリスク () がコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0c41-118">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="a0c41-119">Enter キーを押すと、値は変数に **SecureString** オブジェクトとして格納され `$pwd_secure_string` ます。</span><span class="sxs-lookup"><span data-stu-id="a0c41-119">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

### <span data-ttu-id="a0c41-120">例 3: 入力をプレーンテキスト文字列としてマスクする</span><span class="sxs-lookup"><span data-stu-id="a0c41-120">Example 3: Mask input and as a plaintext string</span></span>

<span data-ttu-id="a0c41-121">この例では、プロンプトとして "Enter a Password:" という文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0c41-121">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="a0c41-122">値が入力されると、 `*` 入力の代わりにアスタリスク () がコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0c41-122">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="a0c41-123">Enter キーを押すと、値はプレーンテキスト **文字列** オブジェクトとして変数に格納され `$pwd_string` ます。</span><span class="sxs-lookup"><span data-stu-id="a0c41-123">When the Enter key is pressed, the value is stored as a plaintext **String** object in the `$pwd_string` variable.</span></span>

```powershell
$pwd_string = Read-Host "Enter a Password" -MaskInput
```

## <span data-ttu-id="a0c41-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a0c41-124">PARAMETERS</span></span>

### <span data-ttu-id="a0c41-125">-AsSecureString</span><span class="sxs-lookup"><span data-stu-id="a0c41-125">-AsSecureString</span></span>

<span data-ttu-id="a0c41-126">コマンドレットによって、 `*` ユーザーが入力として入力した文字の代わりにアスタリスク () が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="a0c41-126">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="a0c41-127">このパラメーターを使用すると、 `Read-Host` コマンドレットの出力は **SecureString** オブジェクト (**SecureString**) になります。</span><span class="sxs-lookup"><span data-stu-id="a0c41-127">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object (**System.Security.SecureString**).</span></span>

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

### <span data-ttu-id="a0c41-128">-MaskInput</span><span class="sxs-lookup"><span data-stu-id="a0c41-128">-MaskInput</span></span>

<span data-ttu-id="a0c41-129">コマンドレットによって、 `*` ユーザーが入力として入力した文字の代わりにアスタリスク () が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="a0c41-129">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="a0c41-130">このパラメーターを使用すると、 `Read-Host` コマンドレットの出力は **String** オブジェクトになります。</span><span class="sxs-lookup"><span data-stu-id="a0c41-130">When you use this parameter, the output of the `Read-Host` cmdlet is a **String** object.</span></span>
<span data-ttu-id="a0c41-131">これにより、 **SecureString** の代わりにプレーンテキストとして返されるパスワードの入力を安全に求めることができます。</span><span class="sxs-lookup"><span data-stu-id="a0c41-131">This allows you to safely prompt for a password that is returned as plaintext instead of **SecureString**.</span></span>

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

### <span data-ttu-id="a0c41-132">-Prompt</span><span class="sxs-lookup"><span data-stu-id="a0c41-132">-Prompt</span></span>

<span data-ttu-id="a0c41-133">プロンプトのテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="a0c41-133">Specifies the text of the prompt.</span></span>
<span data-ttu-id="a0c41-134">文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0c41-134">Type a string.</span></span>
<span data-ttu-id="a0c41-135">文字列にスペースが含まれる場合は、二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="a0c41-135">If the string includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="a0c41-136">入力した `:` テキストに、PowerShell によってコロン () が追加されます。</span><span class="sxs-lookup"><span data-stu-id="a0c41-136">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

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

### <span data-ttu-id="a0c41-137">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a0c41-137">CommonParameters</span></span>

<span data-ttu-id="a0c41-138">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a0c41-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a0c41-139">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0c41-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a0c41-140">入力</span><span class="sxs-lookup"><span data-stu-id="a0c41-140">INPUTS</span></span>

### <span data-ttu-id="a0c41-141">なし</span><span class="sxs-lookup"><span data-stu-id="a0c41-141">None</span></span>

<span data-ttu-id="a0c41-142">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="a0c41-142">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a0c41-143">出力</span><span class="sxs-lookup"><span data-stu-id="a0c41-143">OUTPUTS</span></span>

### <span data-ttu-id="a0c41-144">System.string、または SecureString</span><span class="sxs-lookup"><span data-stu-id="a0c41-144">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="a0c41-145">**AsSecureString** パラメーターが使用されている場合、は `Read-Host` **SecureString** を返します。</span><span class="sxs-lookup"><span data-stu-id="a0c41-145">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString**.</span></span> <span data-ttu-id="a0c41-146">それ以外の場合、文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="a0c41-146">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="a0c41-147">注</span><span class="sxs-lookup"><span data-stu-id="a0c41-147">NOTES</span></span>

## <span data-ttu-id="a0c41-148">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a0c41-148">RELATED LINKS</span></span>

[<span data-ttu-id="a0c41-149">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="a0c41-149">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="a0c41-150">Get-Host</span><span class="sxs-lookup"><span data-stu-id="a0c41-150">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="a0c41-151">Write-Host</span><span class="sxs-lookup"><span data-stu-id="a0c41-151">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="a0c41-152">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="a0c41-152">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
