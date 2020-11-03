---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: 9017d2352f1d2735f21343f4c1194c5e97ce2848
ms.sourcegitcommit: 57df49488015e7ac17ff1df402a94441aa6d6064
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "93217928"
---
# <span data-ttu-id="3ee04-103">Read-Host</span><span class="sxs-lookup"><span data-stu-id="3ee04-103">Read-Host</span></span>

## <span data-ttu-id="3ee04-104">概要</span><span class="sxs-lookup"><span data-stu-id="3ee04-104">SYNOPSIS</span></span>
<span data-ttu-id="3ee04-105">コンソールからの入力行を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="3ee04-105">Reads a line of input from the console.</span></span>

## <span data-ttu-id="3ee04-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3ee04-106">SYNTAX</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="3ee04-107">Description</span><span class="sxs-lookup"><span data-stu-id="3ee04-107">DESCRIPTION</span></span>

<span data-ttu-id="3ee04-108">コマンドレットでは、 `Read-Host` コンソールから入力行を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="3ee04-108">The `Read-Host` cmdlet reads a line of input from the console.</span></span> <span data-ttu-id="3ee04-109">ユーザーに入力を求めるために使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ee04-109">You can use it to prompt a user for input.</span></span> <span data-ttu-id="3ee04-110">セキュリティで保護された文字列として入力を保存できるため、このコマンドレットを使用して、パスワードなどのセキュリティで保護されたデータと共有データなどの入力をユーザーに求めることができます。</span><span class="sxs-lookup"><span data-stu-id="3ee04-110">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords, as well as shared data.</span></span>

## <span data-ttu-id="3ee04-111">例</span><span class="sxs-lookup"><span data-stu-id="3ee04-111">EXAMPLES</span></span>

### <span data-ttu-id="3ee04-112">例 1: コンソールの入力を変数に保存する</span><span class="sxs-lookup"><span data-stu-id="3ee04-112">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="3ee04-113">この例では、プロンプトとして "age:" という文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ee04-113">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="3ee04-114">値を入力し、Enter キーを押すと、値は変数に格納され `$Age` ます。</span><span class="sxs-lookup"><span data-stu-id="3ee04-114">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="3ee04-115">例 2: コンソール入力をセキュリティで保護された文字列として保存する</span><span class="sxs-lookup"><span data-stu-id="3ee04-115">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="3ee04-116">この例では、プロンプトとして "Enter a Password:" という文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ee04-116">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="3ee04-117">値が入力されると、 `*` 入力の代わりにアスタリスク () がコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ee04-117">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="3ee04-118">Enter キーを押すと、値は変数に **SecureString** オブジェクトとして格納され `$pwd_secure_string` ます。</span><span class="sxs-lookup"><span data-stu-id="3ee04-118">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

## <span data-ttu-id="3ee04-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3ee04-119">PARAMETERS</span></span>

### <span data-ttu-id="3ee04-120">-AsSecureString</span><span class="sxs-lookup"><span data-stu-id="3ee04-120">-AsSecureString</span></span>

<span data-ttu-id="3ee04-121">コマンドレットによって、 `*` ユーザーが入力として入力した文字の代わりにアスタリスク () が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ee04-121">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="3ee04-122">このパラメーターを使用すると、 `Read-Host` コマンドレットの出力は **SecureString** オブジェクト ( **SecureString** ) になります。</span><span class="sxs-lookup"><span data-stu-id="3ee04-122">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object ( **System.Security.SecureString** ).</span></span>

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

### <span data-ttu-id="3ee04-123">-Prompt</span><span class="sxs-lookup"><span data-stu-id="3ee04-123">-Prompt</span></span>

<span data-ttu-id="3ee04-124">プロンプトのテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ee04-124">Specifies the text of the prompt.</span></span>
<span data-ttu-id="3ee04-125">文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="3ee04-125">Type a string.</span></span>
<span data-ttu-id="3ee04-126">文字列にスペースが含まれる場合は、二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="3ee04-126">If the string includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="3ee04-127">入力した `:` テキストに、PowerShell によってコロン () が追加されます。</span><span class="sxs-lookup"><span data-stu-id="3ee04-127">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

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

### <span data-ttu-id="3ee04-128">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="3ee04-128">CommonParameters</span></span>

<span data-ttu-id="3ee04-129">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="3ee04-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3ee04-130">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ee04-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3ee04-131">入力</span><span class="sxs-lookup"><span data-stu-id="3ee04-131">INPUTS</span></span>

### <span data-ttu-id="3ee04-132">なし</span><span class="sxs-lookup"><span data-stu-id="3ee04-132">None</span></span>

<span data-ttu-id="3ee04-133">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="3ee04-133">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="3ee04-134">出力</span><span class="sxs-lookup"><span data-stu-id="3ee04-134">OUTPUTS</span></span>

### <span data-ttu-id="3ee04-135">System.string、または SecureString</span><span class="sxs-lookup"><span data-stu-id="3ee04-135">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="3ee04-136">**AsSecureString** パラメーターが使用されている場合、は `Read-Host` **SecureString** を返します。</span><span class="sxs-lookup"><span data-stu-id="3ee04-136">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString**.</span></span> <span data-ttu-id="3ee04-137">それ以外の場合、文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="3ee04-137">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="3ee04-138">注</span><span class="sxs-lookup"><span data-stu-id="3ee04-138">NOTES</span></span>

## <span data-ttu-id="3ee04-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="3ee04-139">RELATED LINKS</span></span>

[<span data-ttu-id="3ee04-140">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="3ee04-140">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="3ee04-141">Get-Host</span><span class="sxs-lookup"><span data-stu-id="3ee04-141">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="3ee04-142">Write-Host</span><span class="sxs-lookup"><span data-stu-id="3ee04-142">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="3ee04-143">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="3ee04-143">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
