---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/convertfrom-securestring?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SecureString
ms.openlocfilehash: 8a151da1b60b1956e580f9a0393d4eb137ef3447
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "93217963"
---
# <span data-ttu-id="7822b-103">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="7822b-103">ConvertFrom-SecureString</span></span>

## <span data-ttu-id="7822b-104">概要</span><span class="sxs-lookup"><span data-stu-id="7822b-104">SYNOPSIS</span></span>
<span data-ttu-id="7822b-105">セキュリティで保護された文字列を暗号化された標準文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="7822b-105">Converts a secure string to an encrypted standard string.</span></span>

## <span data-ttu-id="7822b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7822b-106">SYNTAX</span></span>

### <span data-ttu-id="7822b-107">Secure (既定)</span><span class="sxs-lookup"><span data-stu-id="7822b-107">Secure (Default)</span></span>

```
ConvertFrom-SecureString [-SecureString] <SecureString> [[-SecureKey] <SecureString>] [<CommonParameters>]
```

### <span data-ttu-id="7822b-108">[ファイル]</span><span class="sxs-lookup"><span data-stu-id="7822b-108">Open</span></span>

```
ConvertFrom-SecureString [-SecureString] <SecureString> [-Key <Byte[]>] [<CommonParameters>]
```

## <span data-ttu-id="7822b-109">Description</span><span class="sxs-lookup"><span data-stu-id="7822b-109">DESCRIPTION</span></span>

<span data-ttu-id="7822b-110">**SecureString** コマンドレットは、セキュリティで保護された文字列 ( **SecureString** ) を暗号化された標準文字列 ( **system.string** ) に変換します。</span><span class="sxs-lookup"><span data-stu-id="7822b-110">The **ConvertFrom-SecureString** cmdlet converts a secure string ( **System.Security.SecureString** ) into an encrypted standard string ( **System.String** ).</span></span> <span data-ttu-id="7822b-111">セキュリティで保護された文字列とは異なり、暗号化された標準文字列は、ファイルに保存して後で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7822b-111">Unlike a secure string, an encrypted standard string can be saved in a file for later use.</span></span> <span data-ttu-id="7822b-112">暗号化された標準文字列は、コマンドレットを使用して、セキュリティで保護された文字列形式に変換でき `ConvertTo-SecureString` ます。</span><span class="sxs-lookup"><span data-stu-id="7822b-112">The encrypted standard string can be converted back to its secure string format by using the `ConvertTo-SecureString` cmdlet.</span></span>

<span data-ttu-id="7822b-113">**Key** パラメーターまたは **SecureKey** パラメーターで暗号化キーを指定すると、高度暗号化標準 (AES) という暗号化アルゴリズムが使用されます。</span><span class="sxs-lookup"><span data-stu-id="7822b-113">If an encryption key is specified by using the **Key** or **SecureKey** parameters, the Advanced Encryption Standard (AES) encryption algorithm is used.</span></span> <span data-ttu-id="7822b-114">指定するキーの長さは、AES 暗号化アルゴリズムによってサポートされている 128、192、または 256 ビットにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7822b-114">The specified key must have a length of 128, 192, or 256 bits because those are the key lengths supported by the AES encryption algorithm.</span></span> <span data-ttu-id="7822b-115">キーを指定しない場合には、Windows データ保護 API (DPAPI) が使用されて標準文字列の表現が暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="7822b-115">If no key is specified, the Windows Data Protection API (DPAPI) is used to encrypt the standard string representation.</span></span>

> [!NOTE]
> <span data-ttu-id="7822b-116">[DotNet](/dotnet/api/system.security.securestring?view=netcore-2.1#remarks)ごとに、SecureString の内容は Windows 以外のシステムでは暗号化されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7822b-116">Note that per [DotNet](/dotnet/api/system.security.securestring?view=netcore-2.1#remarks), the contents of a SecureString are not encrypted on non-Windows systems.</span></span>

## <span data-ttu-id="7822b-117">例</span><span class="sxs-lookup"><span data-stu-id="7822b-117">EXAMPLES</span></span>

### <span data-ttu-id="7822b-118">例 1: セキュリティで保護された文字列を作成する</span><span class="sxs-lookup"><span data-stu-id="7822b-118">Example 1: Create a secure string</span></span>

```powershell
$SecureString = Read-Host -AsSecureString
```

<span data-ttu-id="7822b-119">このコマンドは、コマンド プロンプトで入力した文字からセキュリティで保護された文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="7822b-119">This command creates a secure string from characters that you type at the command prompt.</span></span> <span data-ttu-id="7822b-120">コマンドを入力した後で、セキュリティで保護された文字列として格納する文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="7822b-120">After entering the command, type the string you want to store as a secure string.</span></span> <span data-ttu-id="7822b-121">`*`入力した各文字を表すアスタリスク () が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7822b-121">An asterisk (`*`) is displayed to represent each character that you type.</span></span>

### <span data-ttu-id="7822b-122">例 2: セキュリティで保護された文字列を暗号化された標準文字列に変換する</span><span class="sxs-lookup"><span data-stu-id="7822b-122">Example 2: Convert a secure string to an encrypted standard string</span></span>

```powershell
$StandardString = ConvertFrom-SecureString $SecureString
```

<span data-ttu-id="7822b-123">このコマンドは、変数内のセキュリティで保護された文字列 `$SecureString` を暗号化された標準文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="7822b-123">This command converts the secure string in the `$SecureString` variable to an encrypted standard string.</span></span> <span data-ttu-id="7822b-124">結果として生成される暗号化された標準文字列は、変数に格納され `$StandardString` ます。</span><span class="sxs-lookup"><span data-stu-id="7822b-124">The resulting encrypted standard string is stored in the `$StandardString` variable.</span></span>

### <span data-ttu-id="7822b-125">例 3: セキュリティで保護された文字列を、192ビットキーを使用した暗号化された標準文字列に変換する</span><span class="sxs-lookup"><span data-stu-id="7822b-125">Example 3: Convert a secure string to an encrypted standard string with a 192-bit key</span></span>

```powershell
$Key = (3,4,2,3,56,34,254,222,1,1,2,23,42,54,33,233,1,34,2,7,6,5,35,43)
$StandardString = ConvertFrom-SecureString $SecureString -Key $Key
```

<span data-ttu-id="7822b-126">これらのコマンドは、Advanced Encryption Standard (AES) アルゴリズムを使用して、変数に格納されているセキュリティで保護された文字列 `$SecureString` を、暗号化された標準文字列に192ビットキーで変換します。</span><span class="sxs-lookup"><span data-stu-id="7822b-126">These commands use the Advanced Encryption Standard (AES) algorithm to convert the secure string stored in the `$SecureString` variable to an encrypted standard string with a 192-bit key.</span></span> <span data-ttu-id="7822b-127">結果として生成される暗号化された標準文字列は、変数に格納され `$StandardString` ます。</span><span class="sxs-lookup"><span data-stu-id="7822b-127">The resulting encrypted standard string is stored in the `$StandardString` variable.</span></span>

<span data-ttu-id="7822b-128">最初のコマンドは、キーを変数に格納し `$Key` ます。</span><span class="sxs-lookup"><span data-stu-id="7822b-128">The first command stores a key in the `$Key` variable.</span></span> <span data-ttu-id="7822b-129">キーは24個の10進数字の配列であり、それぞれが1つの符号なしバイトに収まるように256未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7822b-129">The key is an array of 24 decimal numerals, each of which must be less than 256 to fit within a single unsigned byte.</span></span>

<span data-ttu-id="7822b-130">10進数は1バイト (8 ビット) を表しているため、キーの合計は192ビット (8 x 24) の24桁になります。</span><span class="sxs-lookup"><span data-stu-id="7822b-130">Because each decimal numeral represents a single byte (8 bits), the key has 24 digits for a total of 192 bits (8 x 24).</span></span> <span data-ttu-id="7822b-131">これは、AES アルゴリズムの有効なキー長さです。</span><span class="sxs-lookup"><span data-stu-id="7822b-131">This is a valid key length for the AES algorithm.</span></span>

<span data-ttu-id="7822b-132">2番目のコマンドは、変数内のキーを使用して、 `$Key` セキュリティで保護された文字列を暗号化された標準文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="7822b-132">The second command uses the key in the `$Key` variable to convert the secure string to an encrypted standard string.</span></span>

## <span data-ttu-id="7822b-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7822b-133">PARAMETERS</span></span>

### <span data-ttu-id="7822b-134">-キー</span><span class="sxs-lookup"><span data-stu-id="7822b-134">-Key</span></span>

<span data-ttu-id="7822b-135">暗号化キーを、バイト配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="7822b-135">Specifies the encryption key as a byte array.</span></span>

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

### <span data-ttu-id="7822b-136">-SecureKey</span><span class="sxs-lookup"><span data-stu-id="7822b-136">-SecureKey</span></span>

<span data-ttu-id="7822b-137">暗号化キーを、セキュリティで保護された文字列として指定します。</span><span class="sxs-lookup"><span data-stu-id="7822b-137">Specifies the encryption key as a secure string.</span></span> <span data-ttu-id="7822b-138">セキュリティで保護された文字列値は、キーとして使用される前に、バイト配列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="7822b-138">The secure string value is converted to a byte array before being used as the key.</span></span>

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

### <span data-ttu-id="7822b-139">-SecureString</span><span class="sxs-lookup"><span data-stu-id="7822b-139">-SecureString</span></span>

<span data-ttu-id="7822b-140">暗号化された標準文字列に変換するセキュリティで保護された文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="7822b-140">Specifies the secure string to convert to an encrypted standard string.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7822b-141">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7822b-141">CommonParameters</span></span>

<span data-ttu-id="7822b-142">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="7822b-142">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`,`-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span>
<span data-ttu-id="7822b-143">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7822b-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7822b-144">入力</span><span class="sxs-lookup"><span data-stu-id="7822b-144">INPUTS</span></span>

### <span data-ttu-id="7822b-145">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="7822b-145">System.Security.SecureString</span></span>

<span data-ttu-id="7822b-146">パイプを使用して、 **SecureString** オブジェクトを Convertfrom-csv に SecureString に送ることができます。</span><span class="sxs-lookup"><span data-stu-id="7822b-146">You can pipe a **SecureString** object to ConvertFrom-SecureString.</span></span>

## <span data-ttu-id="7822b-147">出力</span><span class="sxs-lookup"><span data-stu-id="7822b-147">OUTPUTS</span></span>

### <span data-ttu-id="7822b-148">System.String</span><span class="sxs-lookup"><span data-stu-id="7822b-148">System.String</span></span>

<span data-ttu-id="7822b-149">ConvertFrom-SecureString は、標準文字列オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7822b-149">ConvertFrom-SecureString returns a standard string object.</span></span>

## <span data-ttu-id="7822b-150">注</span><span class="sxs-lookup"><span data-stu-id="7822b-150">NOTES</span></span>

- <span data-ttu-id="7822b-151">コマンドプロンプトで入力した文字からセキュリティで保護された文字列を作成するには、コマンドレットの **AsSecureString** パラメーターを使用し `Read-Host` ます。</span><span class="sxs-lookup"><span data-stu-id="7822b-151">To create a secure string from characters that are typed at the command prompt, use the **AsSecureString** parameter of the `Read-Host` cmdlet.</span></span>
- <span data-ttu-id="7822b-152">**キーまたは** **securekey** パラメーターを使用してキーを指定する場合、キーの長さは正しいものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7822b-152">When you use the **Key** or **SecureKey** parameters to specify a key, the key length must be correct.</span></span> <span data-ttu-id="7822b-153">たとえば、128ビットのキーは、16進数のバイト配列として指定できます。</span><span class="sxs-lookup"><span data-stu-id="7822b-153">For example, a key of 128 bits can be specified as a byte array of 16 decimal numerals.</span></span>
  <span data-ttu-id="7822b-154">同様に、192ビットと256ビットのキーは、それぞれ24および32の10進数のバイト配列に対応します。</span><span class="sxs-lookup"><span data-stu-id="7822b-154">Similarly, 192-bit and 256-bit keys correspond to byte arrays of 24 and 32 decimal numerals, respectively.</span></span>
- <span data-ttu-id="7822b-155">絵文字などの一部の文字は、それらを含む文字列内の複数のコードポイントに対応します。</span><span class="sxs-lookup"><span data-stu-id="7822b-155">Some characters, such as emoticons, correspond to several code points in the string that contains them.</span></span> <span data-ttu-id="7822b-156">これらの文字は、パスワードで使用するときに問題や誤解を招く可能性があるため、使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="7822b-156">Avoid using these characters because they may cause problems and misunderstandings when used in a password.</span></span>

## <span data-ttu-id="7822b-157">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7822b-157">RELATED LINKS</span></span>

[<span data-ttu-id="7822b-158">ConvertTo-SecureString</span><span class="sxs-lookup"><span data-stu-id="7822b-158">ConvertTo-SecureString</span></span>](ConvertTo-SecureString.md)

[<span data-ttu-id="7822b-159">Read-Host</span><span class="sxs-lookup"><span data-stu-id="7822b-159">Read-Host</span></span>](../Microsoft.PowerShell.Utility/Read-Host.md)
