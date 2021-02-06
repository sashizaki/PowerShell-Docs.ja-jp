---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-clixml?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Clixml
ms.openlocfilehash: 3658ea5eded0fed95a1c9a1ea6e7d84a557e1e36
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602216"
---
# <span data-ttu-id="ce07e-102">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="ce07e-102">Import-Clixml</span></span>

## <span data-ttu-id="ce07e-103">概要</span><span class="sxs-lookup"><span data-stu-id="ce07e-103">SYNOPSIS</span></span>
<span data-ttu-id="ce07e-104">EXPORT-CLIXML ファイルをインポートし、対応するオブジェクトを PowerShell に作成します。</span><span class="sxs-lookup"><span data-stu-id="ce07e-104">Imports a CLIXML file and creates corresponding objects in PowerShell.</span></span>

## <span data-ttu-id="ce07e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ce07e-105">SYNTAX</span></span>

### <span data-ttu-id="ce07e-106">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="ce07e-106">ByPath (Default)</span></span>

```
Import-Clixml [-Path] <String[]> [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

### <span data-ttu-id="ce07e-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="ce07e-107">ByLiteralPath</span></span>

```
Import-Clixml -LiteralPath <String[]> [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

## <span data-ttu-id="ce07e-108">Description</span><span class="sxs-lookup"><span data-stu-id="ce07e-108">DESCRIPTION</span></span>

<span data-ttu-id="ce07e-109">この `Import-Clixml` コマンドレットは、Microsoft .NET Framework オブジェクトを表すデータを含む共通言語基盤 (CLI) XML ファイルをインポートし、PowerShell オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ce07e-109">The `Import-Clixml` cmdlet imports a Common Language Infrastructure (CLI) XML file with data that represents Microsoft .NET Framework objects and creates the PowerShell objects.</span></span> <span data-ttu-id="ce07e-110">CLI の詳細については、「 [言語に依存](/dotnet/standard/language-independence)しない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce07e-110">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="ce07e-111">Windows コンピューターでを使用する場合 `Import-Clixml` は、資格情報をインポートし、を使用してセキュリティで保護された XML としてエクスポートした文字列をセキュリティで保護することが重要です `Export-Clixml` 。</span><span class="sxs-lookup"><span data-stu-id="ce07e-111">A valuable use of `Import-Clixml` on Windows computers is to import credentials and secure strings that were exported as secure XML using `Export-Clixml`.</span></span> <span data-ttu-id="ce07e-112">例については、例2を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce07e-112">For an example, see Example 2.</span></span>

<span data-ttu-id="ce07e-113">`Import-Clixml` バイト順マーク (BOM) を使用して、ファイルのエンコード形式を検出します。</span><span class="sxs-lookup"><span data-stu-id="ce07e-113">`Import-Clixml` uses the byte-order-mark (BOM) to detect the encoding format of the file.</span></span> <span data-ttu-id="ce07e-114">ファイルに BOM がない場合は、エンコードが UTF8 であると想定されます。</span><span class="sxs-lookup"><span data-stu-id="ce07e-114">If the file has no BOM, it assumes the encoding is UTF8.</span></span>

## <span data-ttu-id="ce07e-115">例</span><span class="sxs-lookup"><span data-stu-id="ce07e-115">EXAMPLES</span></span>

### <span data-ttu-id="ce07e-116">例 1: シリアル化されたファイルをインポートしてオブジェクトを再作成する</span><span class="sxs-lookup"><span data-stu-id="ce07e-116">Example 1: Import a serialized file and recreate an object</span></span>

<span data-ttu-id="ce07e-117">この例では、 `Export-Clixml` コマンドレットを使用して、によって返されるプロセス情報のシリアル化されたコピーを保存し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="ce07e-117">This example uses the `Export-Clixml` cmdlet to save a serialized copy of the process information returned by `Get-Process`.</span></span> <span data-ttu-id="ce07e-118">`Import-Clixml` シリアル化されたファイルの内容を取得し、変数に格納されているオブジェクトを再作成し `$Processes` ます。</span><span class="sxs-lookup"><span data-stu-id="ce07e-118">`Import-Clixml` retrieves the serialized file's contents and recreates an object that is stored in the `$Processes` variable.</span></span>

```powershell
Get-Process | Export-Clixml -Path .\pi.xml
$Processes = Import-Clixml -Path .\pi.xml
```

### <span data-ttu-id="ce07e-119">例 2: セキュリティで保護された資格情報オブジェクトをインポートする</span><span class="sxs-lookup"><span data-stu-id="ce07e-119">Example 2: Import a secure credential object</span></span>

<span data-ttu-id="ce07e-120">この例では、コマンドレットを実行して変数に格納した資格情報を指定した場合、 `$Credential` `Get-Credential` コマンドレットを実行して `Export-Clixml` 資格情報をディスクに保存できます。</span><span class="sxs-lookup"><span data-stu-id="ce07e-120">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce07e-121">`Export-Clixml` 暗号化された資格情報のみを Windows でエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ce07e-121">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="ce07e-122">MacOS や Linux などの Windows 以外のオペレーティングシステムでは、資格情報はプレーンテキストでエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="ce07e-122">On non-Windows operating systems such as macOS and Linux, credentials are exported in plain text.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="ce07e-123">コマンドレットでは、 `Export-Clixml` Windows [データ保護 API](/previous-versions/windows/apps/hh464970(v=win.10))を使用して資格情報オブジェクトを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="ce07e-123">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span>
<span data-ttu-id="ce07e-124">暗号化により、ユーザーアカウントのみが資格情報オブジェクトの内容を復号化できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ce07e-124">The encryption ensures that only your user account can decrypt the contents of the credential object.</span></span> <span data-ttu-id="ce07e-125">エクスポートされたファイルは、 `CLIXML` 別のコンピューターまたは別のユーザーが使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ce07e-125">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="ce07e-126">この例では、資格情報が格納されているファイルがによって表され `TestScript.ps1.credential` ます。</span><span class="sxs-lookup"><span data-stu-id="ce07e-126">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="ce07e-127">**Testscript** を、資格情報の読み込みに使用するスクリプトの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ce07e-127">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="ce07e-128">資格情報オブジェクトをパイプラインの下に送信 `Export-Clixml` し、 `$Credxmlpath` 最初のコマンドで指定したパスに保存します。</span><span class="sxs-lookup"><span data-stu-id="ce07e-128">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="ce07e-129">スクリプトに資格情報を自動的にインポートするには、最後の2つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ce07e-129">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="ce07e-130">を実行し `Import-Clixml` て、セキュリティで保護された資格情報オブジェクトをスクリプトにインポートします。</span><span class="sxs-lookup"><span data-stu-id="ce07e-130">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="ce07e-131">このインポートにより、スクリプトにプレーンテキストのパスワードが公開されるリスクがなくなります。</span><span class="sxs-lookup"><span data-stu-id="ce07e-131">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

## <span data-ttu-id="ce07e-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ce07e-132">PARAMETERS</span></span>

### <span data-ttu-id="ce07e-133">-最初</span><span class="sxs-lookup"><span data-stu-id="ce07e-133">-First</span></span>

<span data-ttu-id="ce07e-134">指定された数のオブジェクトのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="ce07e-134">Gets only the specified number of objects.</span></span> <span data-ttu-id="ce07e-135">取得するオブジェクトの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="ce07e-135">Enter the number of objects to get.</span></span>

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce07e-136">-IncludeTotalCount</span><span class="sxs-lookup"><span data-stu-id="ce07e-136">-IncludeTotalCount</span></span>

<span data-ttu-id="ce07e-137">データセット内のオブジェクトのうち、選択したオブジェクトの合計数を報告します。</span><span class="sxs-lookup"><span data-stu-id="ce07e-137">Reports the total number of objects in the data set followed by the selected objects.</span></span> <span data-ttu-id="ce07e-138">コマンドレットが合計数を判別できない場合は、[ **不明な合計数**] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce07e-138">If the cmdlet can't determine the total count, it displays **Unknown total count**.</span></span> <span data-ttu-id="ce07e-139">整数には、合計数の値の信頼性を示す " **精度** " プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="ce07e-139">The integer has an **Accuracy** property that indicates the reliability of the total count value.</span></span> <span data-ttu-id="ce07e-140">**精度** の範囲の値がからの場合は、 `0.0` `1.0` `0.0` コマンドレットがオブジェクトをカウントできなかったことを意味します。は、この `1.0` カウントが正確であることを意味し、との間の値は、より信頼性の高い推定値であること `0.0` `1.0` を示します。</span><span class="sxs-lookup"><span data-stu-id="ce07e-140">The value of **Accuracy** ranges from `0.0` to `1.0` where `0.0` means that the cmdlet couldn't count the objects, `1.0` means that the count is exact, and a value between `0.0` and `1.0` indicates an increasingly reliable estimate.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce07e-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ce07e-141">-LiteralPath</span></span>

<span data-ttu-id="ce07e-142">XML ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ce07e-142">Specifies the path to the XML files.</span></span> <span data-ttu-id="ce07e-143">**Path** と異なり、 **LiteralPath** パラメーターの値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ce07e-143">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="ce07e-144">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="ce07e-144">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="ce07e-145">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="ce07e-145">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="ce07e-146">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="ce07e-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ce07e-147">-Path</span><span class="sxs-lookup"><span data-stu-id="ce07e-147">-Path</span></span>

<span data-ttu-id="ce07e-148">XML ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ce07e-148">Specifies the path to the XML files.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ce07e-149">-Skip</span><span class="sxs-lookup"><span data-stu-id="ce07e-149">-Skip</span></span>

<span data-ttu-id="ce07e-150">指定された数のオブジェクトを無視してから、残りのオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="ce07e-150">Ignores the specified number of objects and then gets the remaining objects.</span></span> <span data-ttu-id="ce07e-151">スキップするオブジェクトの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="ce07e-151">Enter the number of objects to skip.</span></span>

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce07e-152">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ce07e-152">CommonParameters</span></span>

<span data-ttu-id="ce07e-153">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ce07e-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ce07e-154">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce07e-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ce07e-155">入力</span><span class="sxs-lookup"><span data-stu-id="ce07e-155">INPUTS</span></span>

### <span data-ttu-id="ce07e-156">System.String</span><span class="sxs-lookup"><span data-stu-id="ce07e-156">System.String</span></span>

<span data-ttu-id="ce07e-157">へのパスを含む文字列をパイプラインでき `Import-Clixml` ます。</span><span class="sxs-lookup"><span data-stu-id="ce07e-157">You can pipeline a string that contains a path to `Import-Clixml`.</span></span>

## <span data-ttu-id="ce07e-158">出力</span><span class="sxs-lookup"><span data-stu-id="ce07e-158">OUTPUTS</span></span>

### <span data-ttu-id="ce07e-159">PSObject</span><span class="sxs-lookup"><span data-stu-id="ce07e-159">PSObject</span></span>

<span data-ttu-id="ce07e-160">`Import-Clixml` 格納されている XML ファイルから逆シリアル化されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="ce07e-160">`Import-Clixml` returns objects that were deserialized from the stored XML files.</span></span>

## <span data-ttu-id="ce07e-161">注</span><span class="sxs-lookup"><span data-stu-id="ce07e-161">NOTES</span></span>

<span data-ttu-id="ce07e-162">パラメーターの複数の値を指定する場合は、コンマを使用して値を区切ります。</span><span class="sxs-lookup"><span data-stu-id="ce07e-162">When specifying multiple values for a parameter, use commas to separate the values.</span></span> <span data-ttu-id="ce07e-163">たとえば、「 `<parameter-name> <value1>, <value2>` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ce07e-163">For example, `<parameter-name> <value1>, <value2>`.</span></span>

## <span data-ttu-id="ce07e-164">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ce07e-164">RELATED LINKS</span></span>

[<span data-ttu-id="ce07e-165">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="ce07e-165">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="ce07e-166">XML シリアル化の概要</span><span class="sxs-lookup"><span data-stu-id="ce07e-166">Introducing XML Serialization</span></span>](/dotnet/standard/serialization/introducing-xml-serialization)

[<span data-ttu-id="ce07e-167">Join-Path</span><span class="sxs-lookup"><span data-stu-id="ce07e-167">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

[<span data-ttu-id="ce07e-168">ディスクへの資格情報の安全な保存</span><span class="sxs-lookup"><span data-stu-id="ce07e-168">Securely Store Credentials on Disk</span></span>](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[<span data-ttu-id="ce07e-169">PowerShell を使用してレガシシステムに資格情報を渡す</span><span class="sxs-lookup"><span data-stu-id="ce07e-169">Use PowerShell to Pass Credentials to Legacy Systems</span></span>](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)

