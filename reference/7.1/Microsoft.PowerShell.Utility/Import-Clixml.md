---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-clixml?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Clixml
ms.openlocfilehash: d33b74101301ec5806f456ddd9cc73bd8b6bb3e1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212976"
---
# <span data-ttu-id="802e8-103">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="802e8-103">Import-Clixml</span></span>

## <span data-ttu-id="802e8-104">概要</span><span class="sxs-lookup"><span data-stu-id="802e8-104">SYNOPSIS</span></span>
<span data-ttu-id="802e8-105">EXPORT-CLIXML ファイルをインポートし、対応するオブジェクトを PowerShell に作成します。</span><span class="sxs-lookup"><span data-stu-id="802e8-105">Imports a CLIXML file and creates corresponding objects in PowerShell.</span></span>

## <span data-ttu-id="802e8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="802e8-106">SYNTAX</span></span>

### <span data-ttu-id="802e8-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="802e8-107">ByPath (Default)</span></span>

```
Import-Clixml [-Path] <String[]> [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

### <span data-ttu-id="802e8-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="802e8-108">ByLiteralPath</span></span>

```
Import-Clixml -LiteralPath <String[]> [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

## <span data-ttu-id="802e8-109">Description</span><span class="sxs-lookup"><span data-stu-id="802e8-109">DESCRIPTION</span></span>

<span data-ttu-id="802e8-110">この `Import-Clixml` コマンドレットは、Microsoft .NET Framework オブジェクトを表すデータを含む共通言語基盤 (CLI) XML ファイルをインポートし、PowerShell オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="802e8-110">The `Import-Clixml` cmdlet imports a Common Language Infrastructure (CLI) XML file with data that represents Microsoft .NET Framework objects and creates the PowerShell objects.</span></span> <span data-ttu-id="802e8-111">CLI の詳細については、「 [言語に依存](/dotnet/standard/language-independence)しない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="802e8-111">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="802e8-112">Windows コンピューターでを使用する場合 `Import-Clixml` は、資格情報をインポートし、を使用してセキュリティで保護された XML としてエクスポートした文字列をセキュリティで保護することが重要です `Export-Clixml` 。</span><span class="sxs-lookup"><span data-stu-id="802e8-112">A valuable use of `Import-Clixml` on Windows computers is to import credentials and secure strings that were exported as secure XML using `Export-Clixml`.</span></span> <span data-ttu-id="802e8-113">例については、例2を参照してください。</span><span class="sxs-lookup"><span data-stu-id="802e8-113">For an example, see Example 2.</span></span>

<span data-ttu-id="802e8-114">`Import-Clixml` バイト順マーク (BOM) を使用して、ファイルのエンコード形式を検出します。</span><span class="sxs-lookup"><span data-stu-id="802e8-114">`Import-Clixml` uses the byte-order-mark (BOM) to detect the encoding format of the file.</span></span> <span data-ttu-id="802e8-115">ファイルに BOM がない場合は、エンコードが UTF8 であると想定されます。</span><span class="sxs-lookup"><span data-stu-id="802e8-115">If the file has no BOM, it assumes the encoding is UTF8.</span></span>

## <span data-ttu-id="802e8-116">例</span><span class="sxs-lookup"><span data-stu-id="802e8-116">EXAMPLES</span></span>

### <span data-ttu-id="802e8-117">例 1: シリアル化されたファイルをインポートしてオブジェクトを再作成する</span><span class="sxs-lookup"><span data-stu-id="802e8-117">Example 1: Import a serialized file and recreate an object</span></span>

<span data-ttu-id="802e8-118">この例では、 `Export-Clixml` コマンドレットを使用して、によって返されるプロセス情報のシリアル化されたコピーを保存し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="802e8-118">This example uses the `Export-Clixml` cmdlet to save a serialized copy of the process information returned by `Get-Process`.</span></span> <span data-ttu-id="802e8-119">`Import-Clixml` シリアル化されたファイルの内容を取得し、変数に格納されているオブジェクトを再作成し `$Processes` ます。</span><span class="sxs-lookup"><span data-stu-id="802e8-119">`Import-Clixml` retrieves the serialized file's contents and recreates an object that is stored in the `$Processes` variable.</span></span>

```powershell
Get-Process | Export-Clixml -Path .\pi.xml
$Processes = Import-Clixml -Path .\pi.xml
```

### <span data-ttu-id="802e8-120">例 2: セキュリティで保護された資格情報オブジェクトをインポートする</span><span class="sxs-lookup"><span data-stu-id="802e8-120">Example 2: Import a secure credential object</span></span>

<span data-ttu-id="802e8-121">この例では、コマンドレットを実行して変数に格納した資格情報を指定した場合、 `$Credential` `Get-Credential` コマンドレットを実行して `Export-Clixml` 資格情報をディスクに保存できます。</span><span class="sxs-lookup"><span data-stu-id="802e8-121">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="802e8-122">`Export-Clixml` 暗号化された資格情報のみを Windows でエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="802e8-122">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="802e8-123">MacOS や Linux などの Windows 以外のオペレーティングシステムでは、資格情報はプレーンテキストでエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="802e8-123">On non-Windows operating systems such as macOS and Linux, credentials are exported in plain text.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="802e8-124">コマンドレットでは、 `Export-Clixml` Windows [データ保護 API](/previous-versions/windows/apps/hh464970(v=win.10))を使用して資格情報オブジェクトを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="802e8-124">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span>
<span data-ttu-id="802e8-125">暗号化により、ユーザーアカウントのみが資格情報オブジェクトの内容を復号化できるようになります。</span><span class="sxs-lookup"><span data-stu-id="802e8-125">The encryption ensures that only your user account can decrypt the contents of the credential object.</span></span> <span data-ttu-id="802e8-126">エクスポートされたファイルは、 `CLIXML` 別のコンピューターまたは別のユーザーが使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="802e8-126">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="802e8-127">この例では、資格情報が格納されているファイルがによって表され `TestScript.ps1.credential` ます。</span><span class="sxs-lookup"><span data-stu-id="802e8-127">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="802e8-128">**Testscript** を、資格情報の読み込みに使用するスクリプトの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="802e8-128">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="802e8-129">資格情報オブジェクトをパイプラインの下に送信 `Export-Clixml` し、 `$Credxmlpath` 最初のコマンドで指定したパスに保存します。</span><span class="sxs-lookup"><span data-stu-id="802e8-129">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="802e8-130">スクリプトに資格情報を自動的にインポートするには、最後の2つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="802e8-130">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="802e8-131">を実行し `Import-Clixml` て、セキュリティで保護された資格情報オブジェクトをスクリプトにインポートします。</span><span class="sxs-lookup"><span data-stu-id="802e8-131">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="802e8-132">このインポートにより、スクリプトにプレーンテキストのパスワードが公開されるリスクがなくなります。</span><span class="sxs-lookup"><span data-stu-id="802e8-132">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

## <span data-ttu-id="802e8-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="802e8-133">PARAMETERS</span></span>

### <span data-ttu-id="802e8-134">-最初</span><span class="sxs-lookup"><span data-stu-id="802e8-134">-First</span></span>

<span data-ttu-id="802e8-135">指定された数のオブジェクトのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="802e8-135">Gets only the specified number of objects.</span></span> <span data-ttu-id="802e8-136">取得するオブジェクトの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="802e8-136">Enter the number of objects to get.</span></span>

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

### <span data-ttu-id="802e8-137">-IncludeTotalCount</span><span class="sxs-lookup"><span data-stu-id="802e8-137">-IncludeTotalCount</span></span>

<span data-ttu-id="802e8-138">データセット内のオブジェクトのうち、選択したオブジェクトの合計数を報告します。</span><span class="sxs-lookup"><span data-stu-id="802e8-138">Reports the total number of objects in the data set followed by the selected objects.</span></span> <span data-ttu-id="802e8-139">コマンドレットが合計数を判別できない場合は、[ **不明な合計数** ] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="802e8-139">If the cmdlet can't determine the total count, it displays **Unknown total count** .</span></span> <span data-ttu-id="802e8-140">整数には、合計数の値の信頼性を示す " **精度** " プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="802e8-140">The integer has an **Accuracy** property that indicates the reliability of the total count value.</span></span> <span data-ttu-id="802e8-141">**精度** の範囲の値がからの場合は、 `0.0` `1.0` `0.0` コマンドレットがオブジェクトをカウントできなかったことを意味します。は、この `1.0` カウントが正確であることを意味し、との間の値は、より信頼性の高い推定値であること `0.0` `1.0` を示します。</span><span class="sxs-lookup"><span data-stu-id="802e8-141">The value of **Accuracy** ranges from `0.0` to `1.0` where `0.0` means that the cmdlet couldn't count the objects, `1.0` means that the count is exact, and a value between `0.0` and `1.0` indicates an increasingly reliable estimate.</span></span>

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

### <span data-ttu-id="802e8-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="802e8-142">-LiteralPath</span></span>

<span data-ttu-id="802e8-143">XML ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="802e8-143">Specifies the path to the XML files.</span></span> <span data-ttu-id="802e8-144">**Path** と異なり、 **LiteralPath** パラメーターの値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="802e8-144">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="802e8-145">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="802e8-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="802e8-146">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="802e8-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="802e8-147">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="802e8-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="802e8-148">-Path</span><span class="sxs-lookup"><span data-stu-id="802e8-148">-Path</span></span>

<span data-ttu-id="802e8-149">XML ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="802e8-149">Specifies the path to the XML files.</span></span>

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

### <span data-ttu-id="802e8-150">-Skip</span><span class="sxs-lookup"><span data-stu-id="802e8-150">-Skip</span></span>

<span data-ttu-id="802e8-151">指定された数のオブジェクトを無視してから、残りのオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="802e8-151">Ignores the specified number of objects and then gets the remaining objects.</span></span> <span data-ttu-id="802e8-152">スキップするオブジェクトの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="802e8-152">Enter the number of objects to skip.</span></span>

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

### <span data-ttu-id="802e8-153">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="802e8-153">CommonParameters</span></span>

<span data-ttu-id="802e8-154">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="802e8-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="802e8-155">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="802e8-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="802e8-156">入力</span><span class="sxs-lookup"><span data-stu-id="802e8-156">INPUTS</span></span>

### <span data-ttu-id="802e8-157">System.String</span><span class="sxs-lookup"><span data-stu-id="802e8-157">System.String</span></span>

<span data-ttu-id="802e8-158">へのパスを含む文字列をパイプラインでき `Import-Clixml` ます。</span><span class="sxs-lookup"><span data-stu-id="802e8-158">You can pipeline a string that contains a path to `Import-Clixml`.</span></span>

## <span data-ttu-id="802e8-159">出力</span><span class="sxs-lookup"><span data-stu-id="802e8-159">OUTPUTS</span></span>

### <span data-ttu-id="802e8-160">PSObject</span><span class="sxs-lookup"><span data-stu-id="802e8-160">PSObject</span></span>

<span data-ttu-id="802e8-161">`Import-Clixml` 格納されている XML ファイルから逆シリアル化されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="802e8-161">`Import-Clixml` returns objects that were deserialized from the stored XML files.</span></span>

## <span data-ttu-id="802e8-162">注</span><span class="sxs-lookup"><span data-stu-id="802e8-162">NOTES</span></span>

<span data-ttu-id="802e8-163">パラメーターの複数の値を指定する場合は、コンマを使用して値を区切ります。</span><span class="sxs-lookup"><span data-stu-id="802e8-163">When specifying multiple values for a parameter, use commas to separate the values.</span></span> <span data-ttu-id="802e8-164">たとえば、「 `<parameter-name> <value1>, <value2>` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="802e8-164">For example, `<parameter-name> <value1>, <value2>`.</span></span>

## <span data-ttu-id="802e8-165">関連リンク</span><span class="sxs-lookup"><span data-stu-id="802e8-165">RELATED LINKS</span></span>

[<span data-ttu-id="802e8-166">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="802e8-166">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="802e8-167">XML シリアル化の概要</span><span class="sxs-lookup"><span data-stu-id="802e8-167">Introducing XML Serialization</span></span>](/dotnet/standard/serialization/introducing-xml-serialization)

[<span data-ttu-id="802e8-168">Join-Path</span><span class="sxs-lookup"><span data-stu-id="802e8-168">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

[<span data-ttu-id="802e8-169">ディスクへの資格情報の安全な保存</span><span class="sxs-lookup"><span data-stu-id="802e8-169">Securely Store Credentials on Disk</span></span>](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[<span data-ttu-id="802e8-170">PowerShell を使用してレガシシステムに資格情報を渡す</span><span class="sxs-lookup"><span data-stu-id="802e8-170">Use PowerShell to Pass Credentials to Legacy Systems</span></span>](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)
