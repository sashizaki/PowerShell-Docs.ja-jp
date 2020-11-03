---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 03/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-acl?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Acl
ms.openlocfilehash: 6b862ad6bada3035551d35d592183db5805b232f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214280"
---
# <span data-ttu-id="75fb9-103">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="75fb9-103">Get-Acl</span></span>

## <span data-ttu-id="75fb9-104">概要</span><span class="sxs-lookup"><span data-stu-id="75fb9-104">SYNOPSIS</span></span>
<span data-ttu-id="75fb9-105">ファイル、レジストリ キーなどのリソースのセキュリティ記述子を取得します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-105">Gets the security descriptor for a resource, such as a file or registry key.</span></span>

## <span data-ttu-id="75fb9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="75fb9-106">SYNTAX</span></span>

### <span data-ttu-id="75fb9-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="75fb9-107">ByPath (Default)</span></span>

```
Get-Acl [[-Path] <String[]>] [-Audit] [-AllCentralAccessPolicies] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="75fb9-108">ByInputObject</span><span class="sxs-lookup"><span data-stu-id="75fb9-108">ByInputObject</span></span>

```
Get-Acl -InputObject <PSObject> [-Audit] [-AllCentralAccessPolicies] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="75fb9-109">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="75fb9-109">ByLiteralPath</span></span>

```
Get-Acl [-LiteralPath <String[]>] [-Audit] [-AllCentralAccessPolicies] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="75fb9-110">Description</span><span class="sxs-lookup"><span data-stu-id="75fb9-110">DESCRIPTION</span></span>

<span data-ttu-id="75fb9-111">`Get-Acl`コマンドレットは、ファイルまたはリソースのセキュリティ記述子を表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-111">The `Get-Acl` cmdlet gets objects that represent the security descriptor of a file or resource.</span></span> <span data-ttu-id="75fb9-112">セキュリティ記述子には、リソースのアクセス制御リスト (ACL) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-112">The security descriptor contains the access control lists (ACLs) of the resource.</span></span> <span data-ttu-id="75fb9-113">ACL は、リソースにアクセスするユーザーおよびユーザー グループに割り当てられるアクセス許可を指定します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-113">The ACL specifies the permissions that users and user groups have to access the resource.</span></span>

<span data-ttu-id="75fb9-114">Windows PowerShell 3.0 以降では、の **InputObject** パラメーターを使用して、 `Get-Acl` パスを持たないオブジェクトのセキュリティ記述子を取得できます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-114">Beginning in Windows PowerShell 3.0, you can use the **InputObject** parameter of `Get-Acl` to get the security descriptor of objects that do not have a path.</span></span>

## <span data-ttu-id="75fb9-115">例</span><span class="sxs-lookup"><span data-stu-id="75fb9-115">EXAMPLES</span></span>

### <span data-ttu-id="75fb9-116">例 1-フォルダーの ACL を取得する</span><span class="sxs-lookup"><span data-stu-id="75fb9-116">Example 1- Get an ACL for a folder</span></span>

<span data-ttu-id="75fb9-117">この例では、ディレクトリのセキュリティ記述子を取得し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-117">This example gets the security descriptor of the `C:\Windows` directory.</span></span>

```powershell
Get-Acl C:\Windows
```

### <span data-ttu-id="75fb9-118">例 2-ワイルドカードを使用してフォルダーの ACL を取得する</span><span class="sxs-lookup"><span data-stu-id="75fb9-118">Example 2 - Get an ACL for a folder using wildcards</span></span>

<span data-ttu-id="75fb9-119">この例では、 `.log` `C:\Windows` 名前がで始まるディレクトリ内のすべてのファイルの PowerShell パスと SDDL を取得し `s` ます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-119">This example gets the PowerShell path and SDDL for all of the `.log` files in the `C:\Windows` directory whose names begin with `s`.</span></span>

```powershell
Get-Acl C:\Windows\s*.log | Format-List -Property PSPath, Sddl
```

<span data-ttu-id="75fb9-120">このコマンドは、コマンドレットを使用して、 `Get-Acl` 各ログファイルのセキュリティ記述子を表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-120">The command uses the `Get-Acl` cmdlet to get objects representing the security descriptors of each log file.</span></span> <span data-ttu-id="75fb9-121">パイプライン演算子 () を使用して、 `|` 結果をコマンドレットに送信し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-121">It uses a pipeline operator (`|`) to send the results to the `Format-List` cmdlet.</span></span> <span data-ttu-id="75fb9-122">このコマンドは、の **Property** パラメーターを使用して `Format-List` 、各セキュリティ記述子オブジェクトの **Pspath** プロパティと **SDDL** プロパティのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-122">The command uses the **Property** parameter of `Format-List` to display only the **PsPath** and **SDDL** properties of each security descriptor object.</span></span>

<span data-ttu-id="75fb9-123">テーブルでは長い値が切り捨てられるため、多くの場合、一覧は PowerShell で使用されます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-123">Lists are often used in PowerShell, because long values appear truncated in tables.</span></span>

<span data-ttu-id="75fb9-124">**SDDL** 値は、システム管理者に有用です。それは、これらの値がセキュリティ記述子内にすべての情報を含む単純なテキスト文字列であるためです。</span><span class="sxs-lookup"><span data-stu-id="75fb9-124">The **SDDL** values are valuable to system administrators, because they are simple text strings that contain all of the information in the security descriptor.</span></span> <span data-ttu-id="75fb9-125">そのため、これらの値は簡単に渡して保存でき、必要なときに解析できます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-125">As such, they are easy to pass and store, and they can be parsed when needed.</span></span>

### <span data-ttu-id="75fb9-126">例 3-ACL の監査エントリの数を取得する</span><span class="sxs-lookup"><span data-stu-id="75fb9-126">Example 3 - Get count of Audit entries for an ACL</span></span>

<span data-ttu-id="75fb9-127">この例では、 `.log` `C:\Windows` 名前がで始まるディレクトリ内のファイルのセキュリティ記述子を取得し `s` ます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-127">This example gets the security descriptors of the `.log` files in the `C:\Windows` directory whose names begin with `s`.</span></span>

```powershell
Get-Acl C:\Windows\s*.log -Audit | ForEach-Object { $_.Audit.Count }
```

<span data-ttu-id="75fb9-128">ここでは、 **Audit** パラメーターを使用して、セキュリティ記述子の SACL から監査レコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-128">It uses the **Audit** parameter to get the audit records from the SACL in the security descriptor.</span></span>
<span data-ttu-id="75fb9-129">次に、コマンドレットを使用して、 `ForEach-Object` 各ファイルに関連付けられている監査レコードの数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="75fb9-129">Then it uses the `ForEach-Object` cmdlet to count the number of audit records associated with each file.</span></span> <span data-ttu-id="75fb9-130">結果として、各ログ ファイルの監査レコードの数を表す番号のリストが得られます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-130">The result is a list of numbers representing the number of audit records for each log file.</span></span>

### <span data-ttu-id="75fb9-131">例 4-レジストリキーの ACL を取得する</span><span class="sxs-lookup"><span data-stu-id="75fb9-131">Example 4 - Get an ACL for a registry key</span></span>

<span data-ttu-id="75fb9-132">この例では、コマンドレットを使用して、 `Get-Acl` レジストリの Control サブキー () のセキュリティ記述子を取得し `HKLM:\SYSTEM\CurrentControlSet\Control` ます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-132">This example uses the `Get-Acl` cmdlet to get the security descriptor of the Control subkey (`HKLM:\SYSTEM\CurrentControlSet\Control`) of the registry.</span></span>

```powershell
Get-Acl -Path HKLM:\System\CurrentControlSet\Control | Format-List
```

<span data-ttu-id="75fb9-133">**Path** パラメーターは、Control サブキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-133">The **Path** parameter specifies the Control subkey.</span></span> <span data-ttu-id="75fb9-134">パイプライン演算子 () は、 `|` コマンドに対して取得するセキュリティ記述子を渡し `Get-Acl` ます。これにより、 `Format-List` セキュリティ記述子のプロパティがリストとして書式設定され、読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="75fb9-134">The pipeline operator (`|`) passes the security descriptor that `Get-Acl` gets to the `Format-List` command, which formats the properties of the security descriptor as a list so that they are easy to read.</span></span>

### <span data-ttu-id="75fb9-135">例 5- **InputObject** を使用して ACL を取得する</span><span class="sxs-lookup"><span data-stu-id="75fb9-135">Example 5 - Get an ACL using **InputObject**</span></span>

<span data-ttu-id="75fb9-136">この例では、の **InputObject** パラメーターを使用して、 `Get-Acl` ストレージサブシステムオブジェクトのセキュリティ記述子を取得します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-136">This example uses the **InputObject** parameter of `Get-Acl` to get the security descriptor of a storage subsystem object.</span></span>

```powershell
Get-Acl -InputObject (Get-StorageSubSystem -Name S087)
```

## <span data-ttu-id="75fb9-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="75fb9-137">PARAMETERS</span></span>

### <span data-ttu-id="75fb9-138">-Audit</span><span class="sxs-lookup"><span data-stu-id="75fb9-138">-Audit</span></span>

<span data-ttu-id="75fb9-139">システム アクセス制御リスト (SACL) からセキュリティ記述子の監査データを取得します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-139">Gets the audit data for the security descriptor from the system access control list (SACL).</span></span>

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

### <span data-ttu-id="75fb9-140">-除外</span><span class="sxs-lookup"><span data-stu-id="75fb9-140">-Exclude</span></span>

<span data-ttu-id="75fb9-141">指定した項目を除外します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-141">Omits the specified items.</span></span> <span data-ttu-id="75fb9-142">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-142">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="75fb9-143">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-143">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="75fb9-144">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-144">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="75fb9-145">-Filter</span><span class="sxs-lookup"><span data-stu-id="75fb9-145">-Filter</span></span>

<span data-ttu-id="75fb9-146">プロバイダーの形式や言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-146">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="75fb9-147">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-147">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="75fb9-148">ワイルドカードを使用できるかどうかなど、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="75fb9-148">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="75fb9-149">フィルターは他のパラメーターよりも効率的です。これは、オブジェクトを取得した後に PowerShell がオブジェクトをフィルター処理するのではなく、オブジェクトの取得時にプロバイダーによって適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="75fb9-149">Filters are more efficient than other parameters, because the provider applies them when getting the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="75fb9-150">-Include</span><span class="sxs-lookup"><span data-stu-id="75fb9-150">-Include</span></span>

<span data-ttu-id="75fb9-151">指定された項目だけを取得します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-151">Gets only the specified items.</span></span> <span data-ttu-id="75fb9-152">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-152">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="75fb9-153">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-153">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="75fb9-154">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-154">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="75fb9-155">-Path</span><span class="sxs-lookup"><span data-stu-id="75fb9-155">-Path</span></span>

<span data-ttu-id="75fb9-156">リソースへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-156">Specifies the path to a resource.</span></span> <span data-ttu-id="75fb9-157">`Get-Acl` パスによって示されるリソースのセキュリティ記述子を取得します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-157">`Get-Acl` gets the security descriptor of the resource indicated by the path.</span></span> <span data-ttu-id="75fb9-158">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-158">Wildcards are permitted.</span></span> <span data-ttu-id="75fb9-159">**Path** パラメーターを省略した場合、は `Get-Acl` 現在のディレクトリのセキュリティ記述子を取得します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-159">If you omit the **Path** parameter, `Get-Acl` gets the security descriptor of the current directory.</span></span>

<span data-ttu-id="75fb9-160">パラメーター名 ("Path") は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="75fb9-160">The parameter name ("Path") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="75fb9-161">-AllCentralAccessPolicies</span><span class="sxs-lookup"><span data-stu-id="75fb9-161">-AllCentralAccessPolicies</span></span>

<span data-ttu-id="75fb9-162">コンピューター上で有効になっているすべての集約型アクセス ポリシーに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-162">Gets information about all central access policies that are enabled on the computer.</span></span>

<span data-ttu-id="75fb9-163">Windows Server 2012 以降では、管理者は Active Directory とグループポリシーを使用して、ユーザーとグループの集約型アクセスポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-163">Beginning in Windows Server 2012, administrators can use Active Directory and Group Policy to set central access policies for users and groups.</span></span> <span data-ttu-id="75fb9-164">詳細については、「 [Dynamic Access Control: シナリオの概要](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75fb9-164">For more information, see [Dynamic Access Control: Scenario Overview](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span></span>

<span data-ttu-id="75fb9-165">このパラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="75fb9-165">This parameter is introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="75fb9-166">-InputObject</span><span class="sxs-lookup"><span data-stu-id="75fb9-166">-InputObject</span></span>

<span data-ttu-id="75fb9-167">指定したオブジェクトのセキュリティ記述子を取得します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-167">Gets the security descriptor for the specified object.</span></span> <span data-ttu-id="75fb9-168">オブジェクトが格納されている変数、またはオブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-168">Enter a variable that contains the object or a command that gets the object.</span></span>

<span data-ttu-id="75fb9-169">パイプを使用してパス以外のオブジェクトをにパイプすることはできません `Get-Acl` 。</span><span class="sxs-lookup"><span data-stu-id="75fb9-169">You cannot pipe an object, other than a path, to `Get-Acl`.</span></span> <span data-ttu-id="75fb9-170">代わりに、 **InputObject** パラメーターをコマンド内で明示的に使用します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-170">Instead, use the **InputObject** parameter explicitly in the command.</span></span>

<span data-ttu-id="75fb9-171">このパラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="75fb9-171">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75fb9-172">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="75fb9-172">-LiteralPath</span></span>

<span data-ttu-id="75fb9-173">リソースへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-173">Specifies the path to a resource.</span></span> <span data-ttu-id="75fb9-174">**Path** と異なり、 **LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-174">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="75fb9-175">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="75fb9-175">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="75fb9-176">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-176">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="75fb9-177">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="75fb9-177">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="75fb9-178">このパラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="75fb9-178">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="75fb9-179">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="75fb9-179">-UseTransaction</span></span>

<span data-ttu-id="75fb9-180">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-180">Includes the command in the active transaction.</span></span>
<span data-ttu-id="75fb9-181">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="75fb9-181">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="75fb9-182">詳細については、「about_Transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75fb9-182">For more information, see about_Transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75fb9-183">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="75fb9-183">CommonParameters</span></span>

<span data-ttu-id="75fb9-184">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="75fb9-184">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="75fb9-185">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75fb9-185">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="75fb9-186">入力</span><span class="sxs-lookup"><span data-stu-id="75fb9-186">INPUTS</span></span>

### <span data-ttu-id="75fb9-187">System.String</span><span class="sxs-lookup"><span data-stu-id="75fb9-187">System.String</span></span>

<span data-ttu-id="75fb9-188">パイプを使用して、パスを含む文字列をにパイプすることができ `Get-Acl` ます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-188">You can pipe a string that contains a path to `Get-Acl`.</span></span>

## <span data-ttu-id="75fb9-189">出力</span><span class="sxs-lookup"><span data-stu-id="75fb9-189">OUTPUTS</span></span>

### <span data-ttu-id="75fb9-190">Accesscontrol-namespace、System.security.accesscontrol.filesecurity、Accesscontrol-namespace、Accesscontrol-namespace、およびの各セキュリティについてのセキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-190">System.Security.AccessControl.FileSecurity, System.Security.AccessControl.DirectorySecurity, System.Security.AccessControl.RegistrySecurity</span></span>

<span data-ttu-id="75fb9-191">`Get-Acl` 取得する Acl を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-191">`Get-Acl` returns an object that represents the ACLs that it gets.</span></span> <span data-ttu-id="75fb9-192">オブジェクトの種類は、ACL の種類に依存します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-192">The object type depends upon the ACL type.</span></span>

## <span data-ttu-id="75fb9-193">注</span><span class="sxs-lookup"><span data-stu-id="75fb9-193">NOTES</span></span>

<span data-ttu-id="75fb9-194">既定では、リソース `Get-Acl` () への PowerShell パス、 `<provider>::<resource-path>` リソースの所有者、およびリソースの随意アクセス制御リスト (DACL) のアクセス制御エントリのリスト (配列) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-194">By default, `Get-Acl` displays the PowerShell path to the resource (`<provider>::<resource-path>`), the owner of the resource, and "Access", a list (array) of the access control entries in the discretionary access control list (DACL) for the resource.</span></span> <span data-ttu-id="75fb9-195">DACL リストは、リソースの所有者によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-195">The DACL list is controlled by the resource owner.</span></span>

<span data-ttu-id="75fb9-196">結果をリストとして書式設定すると ( `Get-Acl | Format-List` )、パス、所有者、アクセスの一覧に加えて、PowerShell では次のプロパティとプロパティ値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-196">When you format the result as a list, (`Get-Acl | Format-List`), in addition to the path, owner, and access list, PowerShell displays the following properties and property values:</span></span>

- <span data-ttu-id="75fb9-197">**グループ** : 所有者のセキュリティグループ。</span><span class="sxs-lookup"><span data-stu-id="75fb9-197">**Group** : The security group of the owner.</span></span>
- <span data-ttu-id="75fb9-198">**Audit** : システムアクセス制御リスト (SACL) 内のエントリのリスト (配列)。</span><span class="sxs-lookup"><span data-stu-id="75fb9-198">**Audit** :  A list (array) of entries in the system access control list (SACL).</span></span> <span data-ttu-id="75fb9-199">SACL は、Windows が監査レコードを生成するアクセス試行の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-199">The SACL specifies the types of access attempts for which Windows generates audit records.</span></span>
- <span data-ttu-id="75fb9-200">**Sddl** : セキュリティ記述子定義言語形式の単一のテキスト文字列に表示されるリソースのセキュリティ記述子。</span><span class="sxs-lookup"><span data-stu-id="75fb9-200">**Sddl** : The security descriptor of the resource displayed in a single text string in Security Descriptor Definition Language format.</span></span> <span data-ttu-id="75fb9-201">PowerShell では、セキュリティ記述子の **Getsddlform** メソッドを使用して、このデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="75fb9-201">PowerShell uses the **GetSddlForm** method of security descriptors to get this data.</span></span>

<span data-ttu-id="75fb9-202">`Get-Acl`はファイルシステムとレジストリプロバイダーによってサポートされているため、を使用して、ファイル `Get-Acl` やディレクトリなどのファイルシステムオブジェクトの ACL と、レジストリキーやエントリなどのレジストリオブジェクトを表示できます。</span><span class="sxs-lookup"><span data-stu-id="75fb9-202">Because `Get-Acl` is supported by the file system and registry providers, you can use `Get-Acl` to view the ACL of file system objects, such as files and directories, and registry objects, such as registry keys and entries.</span></span>

## <span data-ttu-id="75fb9-203">関連リンク</span><span class="sxs-lookup"><span data-stu-id="75fb9-203">RELATED LINKS</span></span>

[<span data-ttu-id="75fb9-204">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="75fb9-204">Set-Acl</span></span>](Set-Acl.md)
