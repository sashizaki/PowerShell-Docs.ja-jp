---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-error?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Error
ms.openlocfilehash: 883990ace87c947ad9f0e10100d4d1dc7f1b8cbe
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224376"
---
# <span data-ttu-id="cd7de-103">Write-Error</span><span class="sxs-lookup"><span data-stu-id="cd7de-103">Write-Error</span></span>

## <span data-ttu-id="cd7de-104">概要</span><span class="sxs-lookup"><span data-stu-id="cd7de-104">SYNOPSIS</span></span>
<span data-ttu-id="cd7de-105">エラー ストリームにオブジェクトを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="cd7de-105">Writes an object to the error stream.</span></span>

## <span data-ttu-id="cd7de-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cd7de-106">SYNTAX</span></span>

### <span data-ttu-id="cd7de-107">NoException (既定値)</span><span class="sxs-lookup"><span data-stu-id="cd7de-107">NoException (Default)</span></span>

```
Write-Error [-Message] <String> [-Category <ErrorCategory>] [-ErrorId <String>] [-TargetObject <Object>]
 [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### <span data-ttu-id="cd7de-108">WithException</span><span class="sxs-lookup"><span data-stu-id="cd7de-108">WithException</span></span>

```
Write-Error -Exception <Exception> [-Message <String>] [-Category <ErrorCategory>] [-ErrorId <String>]
 [-TargetObject <Object>] [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### <span data-ttu-id="cd7de-109">ErrorRecord</span><span class="sxs-lookup"><span data-stu-id="cd7de-109">ErrorRecord</span></span>

```
Write-Error -ErrorRecord <ErrorRecord> [-RecommendedAction <String>] [-CategoryActivity <String>]
 [-CategoryReason <String>] [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

## <span data-ttu-id="cd7de-110">Description</span><span class="sxs-lookup"><span data-stu-id="cd7de-110">DESCRIPTION</span></span>

<span data-ttu-id="cd7de-111">`Write-Error`コマンドレットは、終了しないエラーを宣言します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-111">The `Write-Error` cmdlet declares a non-terminating error.</span></span> <span data-ttu-id="cd7de-112">既定では、エラー ストリームで出力と共に表示されるホスト プログラムにエラーが送信されます。</span><span class="sxs-lookup"><span data-stu-id="cd7de-112">By default, errors are sent in the error stream to the host program to be displayed, along with output.</span></span>

<span data-ttu-id="cd7de-113">未終了エラーを書き込むには、エラー メッセージ文字列の **ErrorRecord** オブジェクトまたは **Exception** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-113">To write a non-terminating error, enter an error message string, an **ErrorRecord** object, or an **Exception** object.</span></span> <span data-ttu-id="cd7de-114">の他のパラメーターを使用し `Write-Error` て、エラーレコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-114">Use the other parameters of `Write-Error` to populate the error record.</span></span>

<span data-ttu-id="cd7de-115">未終了エラーにより、エラー ストリームにエラーが書き込まれますが、コマンド処理は停止されません。</span><span class="sxs-lookup"><span data-stu-id="cd7de-115">Non-terminating errors write an error to the error stream, but they do not stop command processing.</span></span>
<span data-ttu-id="cd7de-116">未終了エラーが、入力項目のコレクション内の 1 つの項目で宣言された場合、コマンドはコレクション内の他の項目の処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-116">If a non-terminating error is declared on one item in a collection of input items, the command continues to process the other items in the collection.</span></span>

<span data-ttu-id="cd7de-117">終了エラーを宣言するには、キーワードを使用し `Throw` ます。</span><span class="sxs-lookup"><span data-stu-id="cd7de-117">To declare a terminating error, use the `Throw` keyword.</span></span>
<span data-ttu-id="cd7de-118">詳細については、「 [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd7de-118">For more information, see [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md).</span></span>

## <span data-ttu-id="cd7de-119">例</span><span class="sxs-lookup"><span data-stu-id="cd7de-119">EXAMPLES</span></span>

### <span data-ttu-id="cd7de-120">例 1: RegistryKey オブジェクトのエラーを書き込む</span><span class="sxs-lookup"><span data-stu-id="cd7de-120">Example 1: Write an error for RegistryKey object</span></span>

```powershell
Get-ChildItem | ForEach-Object {
    if ($_.GetType().ToString() -eq "Microsoft.Win32.RegistryKey")
    {
        Write-Error "Invalid object" -ErrorId B1 -TargetObject $_
    }
    else
    {
        $_
    }
}
```

<span data-ttu-id="cd7de-121">このコマンドレットによっ `Get-ChildItem` `Microsoft.Win32.RegistryKey` て、 `HKLM:` PowerShell レジストリプロバイダーのまたはドライブ内のオブジェクトなどのオブジェクトが返された場合に、終了しないエラーが宣言され `HKCU:` ます。</span><span class="sxs-lookup"><span data-stu-id="cd7de-121">This command declares a non-terminating error when the `Get-ChildItem` cmdlet returns a `Microsoft.Win32.RegistryKey` object, such as the objects in the `HKLM:` or `HKCU:` drives of the PowerShell Registry provider.</span></span>

### <span data-ttu-id="cd7de-122">例 2: コンソールにエラーメッセージを書き込む</span><span class="sxs-lookup"><span data-stu-id="cd7de-122">Example 2: Write an error message to the console</span></span>

```powershell
Write-Error "Access denied."
```

<span data-ttu-id="cd7de-123">このコマンドは、未終了エラーを宣言し、"Access denied" エラーを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="cd7de-123">This command declares a non-terminating error and writes an "Access denied" error.</span></span> <span data-ttu-id="cd7de-124">このコマンドでは、 **Message** パラメーターを使用してメッセージを指定しますが、オプションの **Message** パラメーター名は省略します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-124">The command uses the **Message** parameter to specify the message, but omits the optional **Message** parameter name.</span></span>

### <span data-ttu-id="cd7de-125">例 3: コンソールにエラーを書き込み、カテゴリを指定する</span><span class="sxs-lookup"><span data-stu-id="cd7de-125">Example 3: Write an error to the console and specify the category</span></span>

```powershell
Write-Error -Message "Error: Too many input values." -Category InvalidArgument
```

<span data-ttu-id="cd7de-126">このコマンドは、未終了エラーを宣言し、エラー カテゴリを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="cd7de-126">This command declares a non-terminating error and specifies an error category.</span></span>

### <span data-ttu-id="cd7de-127">例 4: 例外オブジェクトを使用してエラーを記述する</span><span class="sxs-lookup"><span data-stu-id="cd7de-127">Example 4: Write an error using an Exception object</span></span>

```powershell
$E = [System.Exception]@{Source="Get-ParameterNames.ps1";HelpLink="https://go.microsoft.com/fwlink/?LinkID=113425"}
Write-Error -Exception $E -Message "Files not found. The $Files location does not contain any XML files."
```

<span data-ttu-id="cd7de-128">このコマンドは、 **Exception** オブジェクトを使用して未終了エラーを宣言します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-128">This command uses an **Exception** object to declare a non-terminating error.</span></span>

<span data-ttu-id="cd7de-129">最初のコマンドは、ハッシュ テーブルを使用して、 **System.Exception** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-129">The first command uses a hash table to create the **System.Exception** object.</span></span> <span data-ttu-id="cd7de-130">例外オブジェクトは変数に保存され `$E` ます。</span><span class="sxs-lookup"><span data-stu-id="cd7de-130">It saves the exception object in the `$E` variable.</span></span> <span data-ttu-id="cd7de-131">ハッシュ テーブルを使用して、null コンストラクターを持つ種類のオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-131">You can use a hash table to create any object of a type that has a null constructor.</span></span>

<span data-ttu-id="cd7de-132">2番目のコマンドは、コマンドレットを使用して、 `Write-Error` 終了しないエラーを宣言します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-132">The second command uses the `Write-Error` cmdlet to declare a non-terminating error.</span></span> <span data-ttu-id="cd7de-133">**Exception** パラメーターの値は、変数内の **exception** オブジェクトです `$E` 。</span><span class="sxs-lookup"><span data-stu-id="cd7de-133">The value of the **Exception** parameter is the **Exception** object in the `$E` variable.</span></span>

## <span data-ttu-id="cd7de-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cd7de-134">PARAMETERS</span></span>

### <span data-ttu-id="cd7de-135">-カテゴリ</span><span class="sxs-lookup"><span data-stu-id="cd7de-135">-Category</span></span>

<span data-ttu-id="cd7de-136">エラーのカテゴリを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-136">Specifies the category of the error.</span></span> <span data-ttu-id="cd7de-137">既定値は **Notspecified** です。</span><span class="sxs-lookup"><span data-stu-id="cd7de-137">The default value is **NotSpecified** .</span></span> <span data-ttu-id="cd7de-138">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cd7de-138">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="cd7de-139">NotSpecified</span><span class="sxs-lookup"><span data-stu-id="cd7de-139">NotSpecified</span></span>
- <span data-ttu-id="cd7de-140">OpenError</span><span class="sxs-lookup"><span data-stu-id="cd7de-140">OpenError</span></span>
- <span data-ttu-id="cd7de-141">CloseError</span><span class="sxs-lookup"><span data-stu-id="cd7de-141">CloseError</span></span>
- <span data-ttu-id="cd7de-142">DeviceError</span><span class="sxs-lookup"><span data-stu-id="cd7de-142">DeviceError</span></span>
- <span data-ttu-id="cd7de-143">DeadlockDetected</span><span class="sxs-lookup"><span data-stu-id="cd7de-143">DeadlockDetected</span></span>
- <span data-ttu-id="cd7de-144">InvalidArgument</span><span class="sxs-lookup"><span data-stu-id="cd7de-144">InvalidArgument</span></span>
- <span data-ttu-id="cd7de-145">InvalidData</span><span class="sxs-lookup"><span data-stu-id="cd7de-145">InvalidData</span></span>
- <span data-ttu-id="cd7de-146">InvalidOperation</span><span class="sxs-lookup"><span data-stu-id="cd7de-146">InvalidOperation</span></span>
- <span data-ttu-id="cd7de-147">InvalidResult</span><span class="sxs-lookup"><span data-stu-id="cd7de-147">InvalidResult</span></span>
- <span data-ttu-id="cd7de-148">InvalidType</span><span class="sxs-lookup"><span data-stu-id="cd7de-148">InvalidType</span></span>
- <span data-ttu-id="cd7de-149">MetadataError</span><span class="sxs-lookup"><span data-stu-id="cd7de-149">MetadataError</span></span>
- <span data-ttu-id="cd7de-150">NotImplemented</span><span class="sxs-lookup"><span data-stu-id="cd7de-150">NotImplemented</span></span>
- <span data-ttu-id="cd7de-151">NotInstalled</span><span class="sxs-lookup"><span data-stu-id="cd7de-151">NotInstalled</span></span>
- <span data-ttu-id="cd7de-152">ObjectNotFound</span><span class="sxs-lookup"><span data-stu-id="cd7de-152">ObjectNotFound</span></span>
- <span data-ttu-id="cd7de-153">OperationStopped</span><span class="sxs-lookup"><span data-stu-id="cd7de-153">OperationStopped</span></span>
- <span data-ttu-id="cd7de-154">OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="cd7de-154">OperationTimeout</span></span>
- <span data-ttu-id="cd7de-155">SyntaxError</span><span class="sxs-lookup"><span data-stu-id="cd7de-155">SyntaxError</span></span>
- <span data-ttu-id="cd7de-156">ParserError</span><span class="sxs-lookup"><span data-stu-id="cd7de-156">ParserError</span></span>
- <span data-ttu-id="cd7de-157">PermissionDenied</span><span class="sxs-lookup"><span data-stu-id="cd7de-157">PermissionDenied</span></span>
- <span data-ttu-id="cd7de-158">ResourceBusy</span><span class="sxs-lookup"><span data-stu-id="cd7de-158">ResourceBusy</span></span>
- <span data-ttu-id="cd7de-159">ResourceExists</span><span class="sxs-lookup"><span data-stu-id="cd7de-159">ResourceExists</span></span>
- <span data-ttu-id="cd7de-160">リソースを使用できません</span><span class="sxs-lookup"><span data-stu-id="cd7de-160">ResourceUnavailable</span></span>
- <span data-ttu-id="cd7de-161">ReadError</span><span class="sxs-lookup"><span data-stu-id="cd7de-161">ReadError</span></span>
- <span data-ttu-id="cd7de-162">WriteError</span><span class="sxs-lookup"><span data-stu-id="cd7de-162">WriteError</span></span>
- <span data-ttu-id="cd7de-163">FromStdErr</span><span class="sxs-lookup"><span data-stu-id="cd7de-163">FromStdErr</span></span>
- <span data-ttu-id="cd7de-164">SecurityError</span><span class="sxs-lookup"><span data-stu-id="cd7de-164">SecurityError</span></span>
- <span data-ttu-id="cd7de-165">ProtocolError</span><span class="sxs-lookup"><span data-stu-id="cd7de-165">ProtocolError</span></span>
- <span data-ttu-id="cd7de-166">ConnectionError</span><span class="sxs-lookup"><span data-stu-id="cd7de-166">ConnectionError</span></span>
- <span data-ttu-id="cd7de-167">AuthenticationError</span><span class="sxs-lookup"><span data-stu-id="cd7de-167">AuthenticationError</span></span>
- <span data-ttu-id="cd7de-168">LimitsExceeded</span><span class="sxs-lookup"><span data-stu-id="cd7de-168">LimitsExceeded</span></span>
- <span data-ttu-id="cd7de-169">QuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="cd7de-169">QuotaExceeded</span></span>
- <span data-ttu-id="cd7de-170">NotEnabled</span><span class="sxs-lookup"><span data-stu-id="cd7de-170">NotEnabled</span></span>

<span data-ttu-id="cd7de-171">エラーカテゴリの詳細については、「 [ErrorCategory Enumeration](https://go.microsoft.com/fwlink/?LinkId=143600)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd7de-171">For information about the error categories, see [ErrorCategory Enumeration](https://go.microsoft.com/fwlink/?LinkId=143600).</span></span>

```yaml
Type: System.Management.Automation.ErrorCategory
Parameter Sets: NoException, WithException
Aliases:
Accepted values: NotSpecified, OpenError, CloseError, DeviceError, DeadlockDetected, InvalidArgument, InvalidData, InvalidOperation, InvalidResult, InvalidType, MetadataError, NotImplemented, NotInstalled, ObjectNotFound, OperationStopped, OperationTimeout, SyntaxError, ParserError, PermissionDenied, ResourceBusy, ResourceExists, ResourceUnavailable, ReadError, WriteError, FromStdErr, SecurityError, ProtocolError, ConnectionError, AuthenticationError, LimitsExceeded, QuotaExceeded, NotEnabled

Required: False
Position: Named
Default value: NotSpecified
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd7de-172">-カテゴリアクティビティ</span><span class="sxs-lookup"><span data-stu-id="cd7de-172">-CategoryActivity</span></span>

<span data-ttu-id="cd7de-173">エラーの原因となったアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-173">Specifies the action that caused the error.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Activity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd7de-174">-カテゴリの理由</span><span class="sxs-lookup"><span data-stu-id="cd7de-174">-CategoryReason</span></span>

<span data-ttu-id="cd7de-175">アクティビティでエラーが発生した方法または理由を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-175">Specifies how or why the activity caused the error.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Reason

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd7de-176">-カテゴリのターゲット \ ターゲット</span><span class="sxs-lookup"><span data-stu-id="cd7de-176">-CategoryTargetName</span></span>

<span data-ttu-id="cd7de-177">エラーが発生したときに処理されていたオブジェクトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-177">Specifies the name of the object that was being processed when the error occurred.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd7de-178">-カテゴリ Targettype</span><span class="sxs-lookup"><span data-stu-id="cd7de-178">-CategoryTargetType</span></span>

<span data-ttu-id="cd7de-179">エラーが発生したときに処理されていたオブジェクトの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-179">Specifies the type of the object that was being processed when the error occurred.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetType

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd7de-180">-ErrorId</span><span class="sxs-lookup"><span data-stu-id="cd7de-180">-ErrorId</span></span>

<span data-ttu-id="cd7de-181">エラーを識別する ID 文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-181">Specifies an ID string to identify the error.</span></span> <span data-ttu-id="cd7de-182">この文字列、はエラーに対して一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd7de-182">The string should be unique to the error.</span></span>

```yaml
Type: System.String
Parameter Sets: NoException, WithException
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd7de-183">-ErrorRecord</span><span class="sxs-lookup"><span data-stu-id="cd7de-183">-ErrorRecord</span></span>

<span data-ttu-id="cd7de-184">エラーを表す エラー レコード オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-184">Specifies an error record object that represents the error.</span></span> <span data-ttu-id="cd7de-185">エラーを説明するオブジェクトのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-185">Use the properties of the object to describe the error.</span></span>

<span data-ttu-id="cd7de-186">エラーレコードオブジェクトを作成するには、 `New-Object` コマンドレットを使用するか、自動変数の配列からエラーレコードオブジェクトを取得し `$Error` ます。</span><span class="sxs-lookup"><span data-stu-id="cd7de-186">To create an error record object, use the `New-Object` cmdlet or get an error record object from the array in the `$Error` automatic variable.</span></span>

```yaml
Type: System.Management.Automation.ErrorRecord
Parameter Sets: ErrorRecord
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd7de-187">-例外</span><span class="sxs-lookup"><span data-stu-id="cd7de-187">-Exception</span></span>

<span data-ttu-id="cd7de-188">エラーを表す例外オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-188">Specifies an exception object that represents the error.</span></span> <span data-ttu-id="cd7de-189">エラーを説明するオブジェクトのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-189">Use the properties of the object to describe the error.</span></span>

<span data-ttu-id="cd7de-190">例外オブジェクトを作成するには、ハッシュテーブルを使用するか、コマンドレットを使用し `New-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="cd7de-190">To create an exception object, use a hash table or use the `New-Object` cmdlet.</span></span>

```yaml
Type: System.Exception
Parameter Sets: WithException
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd7de-191">-メッセージ</span><span class="sxs-lookup"><span data-stu-id="cd7de-191">-Message</span></span>

<span data-ttu-id="cd7de-192">エラーのメッセージ テキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-192">Specifies the message text of the error.</span></span> <span data-ttu-id="cd7de-193">テキストにスペースまたは特殊文字が含まれる場合は、二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="cd7de-193">If the text includes spaces or special characters, enclose it in quotation marks.</span></span> <span data-ttu-id="cd7de-194">また、パイプを使用してメッセージ文字列をにパイプすることもでき `Write-Error` ます。</span><span class="sxs-lookup"><span data-stu-id="cd7de-194">You can also pipe a message string to `Write-Error`.</span></span>

```yaml
Type: System.String
Parameter Sets: NoException, WithException
Aliases: Msg

Required: True (NoException), False (WithException)
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="cd7de-195">-RecommendedAction</span><span class="sxs-lookup"><span data-stu-id="cd7de-195">-RecommendedAction</span></span>

<span data-ttu-id="cd7de-196">エラーを解決または回避するためにユーザーが実行する必要のあるアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-196">Specifies the action that the user should take to resolve or prevent the error.</span></span>

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

### <span data-ttu-id="cd7de-197">-TargetObject</span><span class="sxs-lookup"><span data-stu-id="cd7de-197">-TargetObject</span></span>

<span data-ttu-id="cd7de-198">エラーが発生したときに処理されていたオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-198">Specifies the object that was being processed when the error occurred.</span></span> <span data-ttu-id="cd7de-199">オブジェクト、オブジェクトを含む変数、またはオブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-199">Enter the object, a variable that contains the object, or a command that gets the object.</span></span>

```yaml
Type: System.Object
Parameter Sets: NoException, WithException
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd7de-200">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="cd7de-200">CommonParameters</span></span>

<span data-ttu-id="cd7de-201">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="cd7de-201">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cd7de-202">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd7de-202">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cd7de-203">入力</span><span class="sxs-lookup"><span data-stu-id="cd7de-203">INPUTS</span></span>

### <span data-ttu-id="cd7de-204">System.String</span><span class="sxs-lookup"><span data-stu-id="cd7de-204">System.String</span></span>

<span data-ttu-id="cd7de-205">パイプを使用して、エラーメッセージを含む文字列をにパイプすることができ `Write-Error` ます。</span><span class="sxs-lookup"><span data-stu-id="cd7de-205">You can pipe a string that contains an error message to `Write-Error`.</span></span>

## <span data-ttu-id="cd7de-206">出力</span><span class="sxs-lookup"><span data-stu-id="cd7de-206">OUTPUTS</span></span>

### <span data-ttu-id="cd7de-207">エラー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="cd7de-207">Error object</span></span>

<span data-ttu-id="cd7de-208">`Write-Error` エラーストリームにのみ書き込みます。</span><span class="sxs-lookup"><span data-stu-id="cd7de-208">`Write-Error` writes only to the error stream.</span></span> <span data-ttu-id="cd7de-209">このコマンドはオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="cd7de-209">It does not return any objects.</span></span>

## <span data-ttu-id="cd7de-210">注</span><span class="sxs-lookup"><span data-stu-id="cd7de-210">NOTES</span></span>

<span data-ttu-id="cd7de-211">`Write-Error` は自動変数の値を変更しない `$?` ため、終了エラー状態を通知しません。</span><span class="sxs-lookup"><span data-stu-id="cd7de-211">`Write-Error` does not change the value of the `$?` automatic variable, therefore it does not signal a terminating error condition.</span></span> <span data-ttu-id="cd7de-212">終了エラーを通知するには、 [WriteError ()](/dotnet/api/system.management.automation.cmdlet.writeerror) メソッドを $PSCmdlet 使用します。</span><span class="sxs-lookup"><span data-stu-id="cd7de-212">To signal a terminating error, use the [$PSCmdlet.WriteError()](/dotnet/api/system.management.automation.cmdlet.writeerror) method.</span></span>

## <span data-ttu-id="cd7de-213">関連リンク</span><span class="sxs-lookup"><span data-stu-id="cd7de-213">RELATED LINKS</span></span>

[<span data-ttu-id="cd7de-214">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="cd7de-214">about_Automatic_Variables</span></span>](../microsoft.powershell.core/about/about_automatic_variables.md)

[<span data-ttu-id="cd7de-215">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="cd7de-215">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="cd7de-216">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="cd7de-216">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="cd7de-217">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="cd7de-217">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="cd7de-218">Write-Host</span><span class="sxs-lookup"><span data-stu-id="cd7de-218">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="cd7de-219">Write-Output</span><span class="sxs-lookup"><span data-stu-id="cd7de-219">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="cd7de-220">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="cd7de-220">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="cd7de-221">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="cd7de-221">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="cd7de-222">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="cd7de-222">Write-Warning</span></span>](Write-Warning.md)
