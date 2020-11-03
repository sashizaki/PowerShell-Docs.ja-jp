---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-SecureString
ms.openlocfilehash: 6e536681f78a79660e80951d0dcc446fbba32553
ms.sourcegitcommit: df80c558e9a4b89c9798f084bd04012ece15155c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2020
ms.locfileid: "93225147"
---
# <span data-ttu-id="8a5c5-103">ConvertTo-SecureString</span><span class="sxs-lookup"><span data-stu-id="8a5c5-103">ConvertTo-SecureString</span></span>

## <span data-ttu-id="8a5c5-104">概要</span><span class="sxs-lookup"><span data-stu-id="8a5c5-104">SYNOPSIS</span></span>
<span data-ttu-id="8a5c5-105">プレーンテキストまたは暗号化された文字列をセキュリティで保護された文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-105">Converts plain text or encrypted strings to secure strings.</span></span>

## <span data-ttu-id="8a5c5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8a5c5-106">SYNTAX</span></span>

### <span data-ttu-id="8a5c5-107">Secure (既定)</span><span class="sxs-lookup"><span data-stu-id="8a5c5-107">Secure (Default)</span></span>

```
ConvertTo-SecureString [-String] <String> [[-SecureKey] <SecureString>] [<CommonParameters>]
```

### <span data-ttu-id="8a5c5-108">PlainText</span><span class="sxs-lookup"><span data-stu-id="8a5c5-108">PlainText</span></span>

```
ConvertTo-SecureString [-String] <String> [-AsPlainText] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="8a5c5-109">[ファイル]</span><span class="sxs-lookup"><span data-stu-id="8a5c5-109">Open</span></span>

```
ConvertTo-SecureString [-String] <String> [-Key <Byte[]>] [<CommonParameters>]
```

## <span data-ttu-id="8a5c5-110">Description</span><span class="sxs-lookup"><span data-stu-id="8a5c5-110">DESCRIPTION</span></span>

<span data-ttu-id="8a5c5-111">`ConvertTo-SecureString`コマンドレットは、暗号化された標準文字列をセキュリティで保護された文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-111">The `ConvertTo-SecureString` cmdlet converts encrypted standard strings into secure strings.</span></span> <span data-ttu-id="8a5c5-112">プレーンテキストをセキュリティで保護された文字列に変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-112">It can also convert plain text to secure strings.</span></span> <span data-ttu-id="8a5c5-113">これは、およびと共に使用され `ConvertFrom-SecureString` `Read-Host` ます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-113">It is used with `ConvertFrom-SecureString` and `Read-Host`.</span></span> <span data-ttu-id="8a5c5-114">コマンドレットによって作成されるセキュリティで保護された文字列は、 **SecureString** 型のパラメーターを必要とするコマンドレットまたは関数で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-114">The secure string created by the cmdlet can be used with cmdlets or functions that require a parameter of type **SecureString**.</span></span> <span data-ttu-id="8a5c5-115">セキュリティで保護された文字列は、コマンドレットを使用して、暗号化された標準文字列に変換して戻すことができ `ConvertFrom-SecureString` ます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-115">The secure string can be converted back to an encrypted, standard string using the `ConvertFrom-SecureString` cmdlet.</span></span> <span data-ttu-id="8a5c5-116">この文字列は、後で使用できるようにファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-116">This enables it to be stored in a file for later use.</span></span>

<span data-ttu-id="8a5c5-117">変換される標準の文字列が指定したキーを使用して暗号化されている場合は、 `ConvertFrom-SecureString` コマンドレットの **key** または **securekey** パラメーターの値と同じキーを指定する必要があり `ConvertTo-SecureString` ます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-117">If the standard string being converted was encrypted with `ConvertFrom-SecureString` using a specified key, that same key must be provided as the value of the **Key** or **SecureKey** parameter of the `ConvertTo-SecureString` cmdlet.</span></span>

## <span data-ttu-id="8a5c5-118">例</span><span class="sxs-lookup"><span data-stu-id="8a5c5-118">EXAMPLES</span></span>

### <span data-ttu-id="8a5c5-119">例 1: セキュリティで保護された文字列を暗号化された文字列に変換する</span><span class="sxs-lookup"><span data-stu-id="8a5c5-119">Example 1: Convert a secure string to an encrypted string</span></span>

<span data-ttu-id="8a5c5-120">この例では、ユーザー入力からセキュリティで保護された文字列を作成し、セキュリティで保護された文字列を暗号化された標準文字列に変換してから、暗号化された標準文字列をセキュリティで保護された文字列に戻す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-120">This example shows how to create a secure string from user input, convert the secure string to an encrypted standard string, and then convert the encrypted standard string back to a secure string.</span></span>

```powershell
PS C:\> $Secure = Read-Host -AsSecureString
PS C:\> $Secure
System.Security.SecureString
PS C:\> $Encrypted = ConvertFrom-SecureString -SecureString $Secure
PS C:\> $Encrypted
01000000d08c9ddf0115d1118c7a00c04fc297eb010000001a114d45b8dd3f4aa11ad7c0abdae98000000000
02000000000003660000a8000000100000005df63cea84bfb7d70bd6842e7efa79820000000004800000a000
000010000000f10cd0f4a99a8d5814d94e0687d7430b100000008bf11f1960158405b2779613e9352c6d1400
0000e6b7bf46a9d485ff211b9b2a2df3bd6eb67aae41
PS C:\> $Secure2 = ConvertTo-SecureString -String $Encrypted
PS C:\> $Secure2
System.Security.SecureString
```

<span data-ttu-id="8a5c5-121">最初のコマンドは、コマンドレットの **AsSecureString** パラメーターを使用して、 `Read-Host` セキュリティで保護された文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-121">The first command uses the **AsSecureString** parameter of the `Read-Host` cmdlet to create a secure string.</span></span> <span data-ttu-id="8a5c5-122">コマンドを入力すると、入力した文字がセキュリティで保護された文字列に変換され、変数に保存され `$Secure` ます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-122">After you enter the command, any characters that you type are converted into a secure string and then saved in the `$Secure` variable.</span></span>

<span data-ttu-id="8a5c5-123">2番目のコマンドは、変数の内容を表示し `$Secure` ます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-123">The second command displays the contents of the `$Secure` variable.</span></span> <span data-ttu-id="8a5c5-124">変数には `$Secure` セキュリティで保護された文字列が含まれているため、PowerShell では **SecureString** 型のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-124">Because the `$Secure` variable contains a secure string, PowerShell displays only the **System.Security.SecureString** type.</span></span>

<span data-ttu-id="8a5c5-125">3番目のコマンドは、コマンドレットを使用して、 `ConvertFrom-SecureString` 変数内のセキュリティで保護された文字列を `$Secure` 暗号化された標準文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-125">The third command uses the `ConvertFrom-SecureString` cmdlet to convert the secure string in the `$Secure` variable into an encrypted standard string.</span></span> <span data-ttu-id="8a5c5-126">結果は変数に保存され `$Encrypted` ます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-126">It saves the result in the `$Encrypted` variable.</span></span>

<span data-ttu-id="8a5c5-127">4番目のコマンドは、暗号化された文字列を変数の値で表示し `$Encrypted` ます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-127">The fourth command displays the encrypted string in the value of the `$Encrypted` variable.</span></span>

<span data-ttu-id="8a5c5-128">5番目のコマンドは、コマンドレットを使用して、 `ConvertTo-SecureString` 変数内の暗号化された標準文字列を `$Encrypted` セキュリティで保護された文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-128">The fifth command uses the `ConvertTo-SecureString` cmdlet to convert the encrypted standard string in the `$Encrypted` variable back into a secure string.</span></span> <span data-ttu-id="8a5c5-129">結果は変数に保存され `$Secure2` ます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-129">It saves the result in the `$Secure2` variable.</span></span>
<span data-ttu-id="8a5c5-130">6番目のコマンドは、変数の値を表示し `$Secure2` ます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-130">The sixth command displays the value of the `$Secure2` variable.</span></span> <span data-ttu-id="8a5c5-131">SecureString 型は、コマンドが成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-131">The SecureString type indicates that the command was successful.</span></span>

### <span data-ttu-id="8a5c5-132">例 2: ファイル内の暗号化された文字列からセキュリティで保護された文字列を作成する</span><span class="sxs-lookup"><span data-stu-id="8a5c5-132">Example 2: Create a secure string from an encrypted string in a file</span></span>

<span data-ttu-id="8a5c5-133">この例では、ファイルに保存されている暗号化された標準文字列からセキュリティで保護された文字列を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-133">This example shows how to create a secure string from an encrypted standard string that is saved in a file.</span></span>

```powershell
$Secure = Read-Host -AsSecureString
$Encrypted = ConvertFrom-SecureString -SecureString $Secure -Key (1..16)
$Encrypted | Set-Content Encrypted.txt
$Secure2 = Get-Content Encrypted.txt | ConvertTo-SecureString -Key (1..16)
```

<span data-ttu-id="8a5c5-134">最初のコマンドは、コマンドレットの **AsSecureString** パラメーターを使用して、 `Read-Host` セキュリティで保護された文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-134">The first command uses the **AsSecureString** parameter of the `Read-Host` cmdlet to create a secure string.</span></span> <span data-ttu-id="8a5c5-135">コマンドを入力すると、入力した文字がセキュリティで保護された文字列に変換され、変数に保存され `$Secure` ます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-135">After you enter the command, any characters that you type are converted into a secure string and then saved in the `$Secure` variable.</span></span>

<span data-ttu-id="8a5c5-136">2番目のコマンドは、コマンドレットを使用して、 `ConvertFrom-SecureString` 指定されたキーを使用して、変数内のセキュリティで保護された文字列を `$Secure` 暗号化された標準文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-136">The second command uses the `ConvertFrom-SecureString` cmdlet to convert the secure string in the `$Secure` variable into an encrypted standard string by using the specified key.</span></span> <span data-ttu-id="8a5c5-137">内容は変数に保存され `$Encrypted` ます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-137">The contents are saved in the `$Encrypted` variable.</span></span>

<span data-ttu-id="8a5c5-138">3番目のコマンドは、パイプライン演算子 () を使用して、 `|` 変数の値を `$Encrypted` コマンドレットに送信し `Set-Content` ます。これにより、Encrypted.txt ファイルに値が保存されます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-138">The third command uses a pipeline operator (`|`) to send the value of the `$Encrypted` variable to the `Set-Content` cmdlet, which saves the value in the Encrypted.txt file.</span></span>

<span data-ttu-id="8a5c5-139">4番目のコマンドは、コマンドレットを使用して、 `Get-Content` 暗号化された標準文字列を Encrypted.txt ファイルで取得します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-139">The fourth command uses the `Get-Content` cmdlet to get the encrypted standard string in the Encrypted.txt file.</span></span> <span data-ttu-id="8a5c5-140">このコマンドは、パイプライン演算子を使用して暗号化された文字列をコマンドレットに送信し `ConvertTo-SecureString` 、指定されたキーを使用してセキュリティで保護された文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-140">The command uses a pipeline operator to send the encrypted string to the `ConvertTo-SecureString` cmdlet, which converts it to a secure string by using the specified key.</span></span>
<span data-ttu-id="8a5c5-141">結果は変数に保存され `$Secure2` ます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-141">The results are saved in the `$Secure2` variable.</span></span>

### <span data-ttu-id="8a5c5-142">例 3: プレーンテキスト文字列をセキュリティで保護された文字列に変換する</span><span class="sxs-lookup"><span data-stu-id="8a5c5-142">Example 3: Convert a plain text string to a secure string</span></span>

<span data-ttu-id="8a5c5-143">このコマンドは、プレーンテキスト文字列を `P@ssW0rD!` セキュリティで保護された文字列に変換し、その結果を変数に格納し `$Secure_String_Pwd` ます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-143">This command converts the plain text string `P@ssW0rD!` into a secure string and stores the result in the `$Secure_String_Pwd` variable.</span></span> <span data-ttu-id="8a5c5-144">**Asplaintext** パラメーターを使用するには、 **Force** パラメーターもコマンドに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-144">To use the **AsPlainText** parameter, the **Force** parameter must also be included in the command.</span></span>

```powershell
$Secure_String_Pwd = ConvertTo-SecureString "P@ssW0rD!" -AsPlainText -Force
```

> [!CAUTION]
> <span data-ttu-id="8a5c5-145">スクリプトまたはコマンドラインからプレーンテキスト文字列を使用することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-145">You should avoid using plain text strings in script or from the command line.</span></span> <span data-ttu-id="8a5c5-146">プレーンテキストは、イベントログとコマンド履歴ログに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-146">The plain text can show up in event logs and command history logs.</span></span>

## <span data-ttu-id="8a5c5-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8a5c5-147">PARAMETERS</span></span>

### <span data-ttu-id="8a5c5-148">-AsPlainText</span><span class="sxs-lookup"><span data-stu-id="8a5c5-148">-AsPlainText</span></span>

<span data-ttu-id="8a5c5-149">セキュリティで保護された文字列に変換するプレーンテキスト文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-149">Specifies a plain text string to convert to a secure string.</span></span> <span data-ttu-id="8a5c5-150">セキュリティで保護された文字列コマンドレットは、秘密情報テキストを保護できます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-150">The secure string cmdlets help protect confidential text.</span></span> <span data-ttu-id="8a5c5-151">テキストはプライバシー保護のために暗号化され、使用後にコンピューターのメモリから削除されます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-151">The text is encrypted for privacy and is deleted from computer memory after it is used.</span></span> <span data-ttu-id="8a5c5-152">このパラメーターを使用してプレーンテキストを入力として提供すると、システムはこの方法でその入力を保護することはできません。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-152">If you use this parameter to provide plain text as input, the system cannot protect that input in this manner.</span></span> <span data-ttu-id="8a5c5-153">このパラメーターを使用するには、 **Force** パラメーターも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-153">To use this parameter, you must also specify the **Force** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PlainText
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a5c5-154">-Force</span><span class="sxs-lookup"><span data-stu-id="8a5c5-154">-Force</span></span>

<span data-ttu-id="8a5c5-155">**Asplaintext** パラメーターを使用することによる影響を理解し、それを使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-155">Confirms that you understand the implications of using the **AsPlainText** parameter and still want to use it.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PlainText
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a5c5-156">-キー</span><span class="sxs-lookup"><span data-stu-id="8a5c5-156">-Key</span></span>

<span data-ttu-id="8a5c5-157">元のセキュリティ文字列を暗号化された標準文字列に変換するために使用する暗号化キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-157">Specifies the encryption key used to convert the original secure string into the encrypted standard string.</span></span> <span data-ttu-id="8a5c5-158">有効なキーの長さは、16、24、および32バイトです。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-158">Valid key lengths are 16, 24 and 32 bytes.</span></span>

```yaml
Type: System.Byte[]
Parameter Sets: Open
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a5c5-159">-SecureKey</span><span class="sxs-lookup"><span data-stu-id="8a5c5-159">-SecureKey</span></span>

<span data-ttu-id="8a5c5-160">元のセキュリティ文字列を暗号化された標準文字列に変換するために使用する暗号化キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-160">Specifies the encryption key used to convert the original secure string into the encrypted standard string.</span></span> <span data-ttu-id="8a5c5-161">セキュリティで保護された文字列の形式で、キーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-161">The key must be provided in the format of a secure string.</span></span> <span data-ttu-id="8a5c5-162">セキュリティで保護された文字列は、キーとして使用されるバイト配列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-162">The secure string will be converted to a byte array to be used as the key.</span></span> <span data-ttu-id="8a5c5-163">セキュリティで保護された有効なキーの長さは、8、12、16のコードポイントです。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-163">Valid secure key lengths are 8, 12 and 16 code points.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: Secure
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a5c5-164">-文字列</span><span class="sxs-lookup"><span data-stu-id="8a5c5-164">-String</span></span>

<span data-ttu-id="8a5c5-165">セキュリティで保護された文字列に変換する文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-165">Specifies the string to convert to a secure string.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8a5c5-166">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a5c5-166">CommonParameters</span></span>

<span data-ttu-id="8a5c5-167">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8a5c5-168">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8a5c5-169">入力</span><span class="sxs-lookup"><span data-stu-id="8a5c5-169">INPUTS</span></span>

### <span data-ttu-id="8a5c5-170">System.String</span><span class="sxs-lookup"><span data-stu-id="8a5c5-170">System.String</span></span>

<span data-ttu-id="8a5c5-171">パイプを使用して、標準の暗号化された文字列をにパイプすることができ `ConvertTo-SecureString` ます。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-171">You can pipe a standard encrypted string to `ConvertTo-SecureString`.</span></span>

## <span data-ttu-id="8a5c5-172">出力</span><span class="sxs-lookup"><span data-stu-id="8a5c5-172">OUTPUTS</span></span>

### <span data-ttu-id="8a5c5-173">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="8a5c5-173">System.Security.SecureString</span></span>

<span data-ttu-id="8a5c5-174">`ConvertTo-SecureString`**SecureString** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-174">`ConvertTo-SecureString` returns a **SecureString** object.</span></span>

## <span data-ttu-id="8a5c5-175">注</span><span class="sxs-lookup"><span data-stu-id="8a5c5-175">NOTES</span></span>

<span data-ttu-id="8a5c5-176">絵文字などの一部の文字は、それらを含む文字列内の複数のコードポイントに対応します。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-176">Some characters, such as emoticons, correspond to several code points in the string that contains them.</span></span> <span data-ttu-id="8a5c5-177">これらの文字は、パスワードで使用するときに問題や誤解を招く可能性があるため、使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="8a5c5-177">Avoid using these characters because they may cause problems and misunderstandings when used in a password.</span></span>

## <span data-ttu-id="8a5c5-178">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8a5c5-178">RELATED LINKS</span></span>

[<span data-ttu-id="8a5c5-179">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="8a5c5-179">ConvertFrom-SecureString</span></span>](ConvertFrom-SecureString.md)

[<span data-ttu-id="8a5c5-180">Read-Host</span><span class="sxs-lookup"><span data-stu-id="8a5c5-180">Read-Host</span></span>](../Microsoft.PowerShell.Utility/Read-Host.md)