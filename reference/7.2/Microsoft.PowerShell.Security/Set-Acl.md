---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-acl?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Acl
ms.openlocfilehash: 90155472f8455fc479b0f49122182dcec06f6d93
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601400"
---
# <span data-ttu-id="fbfac-102">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="fbfac-102">Set-Acl</span></span>

## <span data-ttu-id="fbfac-103">概要</span><span class="sxs-lookup"><span data-stu-id="fbfac-103">SYNOPSIS</span></span>
<span data-ttu-id="fbfac-104">ファイルやレジストリ キーなど、指定した項目のセキュリティ記述子を変更します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-104">Changes the security descriptor of a specified item, such as a file or a registry key.</span></span>

## <span data-ttu-id="fbfac-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fbfac-105">SYNTAX</span></span>

### <span data-ttu-id="fbfac-106">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="fbfac-106">ByPath (Default)</span></span>

```
Set-Acl [-Path] <String[]> [-AclObject] <Object> [-ClearCentralAccessPolicy] [-Passthru] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fbfac-107">ByInputObject</span><span class="sxs-lookup"><span data-stu-id="fbfac-107">ByInputObject</span></span>

```
Set-Acl [-InputObject] <PSObject> [-AclObject] <Object> [-Passthru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fbfac-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="fbfac-108">ByLiteralPath</span></span>

```
Set-Acl -LiteralPath <String[]> [-AclObject] <Object> [-ClearCentralAccessPolicy] [-Passthru]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fbfac-109">Description</span><span class="sxs-lookup"><span data-stu-id="fbfac-109">DESCRIPTION</span></span>

<span data-ttu-id="fbfac-110">`Set-Acl`このコマンドレットは、指定した項目 (ファイルやレジストリキーなど) のセキュリティ記述子を、指定したセキュリティ記述子の値と一致するように変更します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-110">The `Set-Acl` cmdlet changes the security descriptor of a specified item, such as a file or a registry key, to match the values in a security descriptor that you supply.</span></span>

<span data-ttu-id="fbfac-111">を使用するに `Set-Acl` は、 **Path** または **InputObject** パラメーターを使用して、セキュリティ記述子を変更する項目を識別します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-111">To use `Set-Acl`, use the **Path** or **InputObject** parameter to identify the item whose security descriptor you want to change.</span></span> <span data-ttu-id="fbfac-112">次に、**AclObject** または **SecurityDescriptor** パラメーターを使用して、適用する値が含まれるセキュリティ記述子を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-112">Then, use the **AclObject** or **SecurityDescriptor** parameters to supply a security descriptor that has the values you want to apply.</span></span> <span data-ttu-id="fbfac-113">`Set-Acl` 指定されたセキュリティ記述子を適用します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-113">`Set-Acl` applies the security descriptor that is supplied.</span></span> <span data-ttu-id="fbfac-114">**AclObject** パラメーターの値をモデルとして使用し、項目のセキュリティ記述子の値を **AclObject** パラメーターの値と一致するように変更します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-114">It uses the value of the **AclObject** parameter as a model and changes the values in the item's security descriptor to match the values in the **AclObject** parameter.</span></span>

## <span data-ttu-id="fbfac-115">例</span><span class="sxs-lookup"><span data-stu-id="fbfac-115">EXAMPLES</span></span>

### <span data-ttu-id="fbfac-116">例 1: あるファイルから別のファイルにセキュリティ記述子をコピーする</span><span class="sxs-lookup"><span data-stu-id="fbfac-116">Example 1: Copy a security descriptor from one file to another</span></span>

```powershell
$DogACL = Get-Acl -Path "C:\Dog.txt"
Set-Acl -Path "C:\Cat.txt" -AclObject $DogACL
```

<span data-ttu-id="fbfac-117">これらのコマンドは、Dog.txt ファイルのセキュリティ記述子から Cat.txt ファイルのセキュリティ記述子に値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="fbfac-117">These commands copy the values from the security descriptor of the Dog.txt file to the security descriptor of the Cat.txt file.</span></span> <span data-ttu-id="fbfac-118">コマンドが完了すると、Dog.txt ファイルと Cat.txt ファイルのセキュリティ記述子は同一となります。</span><span class="sxs-lookup"><span data-stu-id="fbfac-118">When the commands complete, the security descriptors of the Dog.txt and Cat.txt files are identical.</span></span>

<span data-ttu-id="fbfac-119">最初のコマンドは、 `Get-Acl` コマンドレットを使用して、Dog.txt ファイルのセキュリティ記述子を取得します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-119">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>
<span data-ttu-id="fbfac-120">代入演算子 () は、 `=` $DogACL 変数の値にセキュリティ記述子を格納します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-120">The assignment operator (`=`) stores the security descriptor in the value of the $DogACL variable.</span></span>

<span data-ttu-id="fbfac-121">2番目のコマンドは、を使用して `Set-Acl` Cat.txt の ACL の値をの値に変更し `$DogACL` ます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-121">The second command uses `Set-Acl` to change the values in the ACL of Cat.txt to the values in `$DogACL`.</span></span>

<span data-ttu-id="fbfac-122">**Path** パラメーターの値は、Cat.txt ファイルへのパスです。</span><span class="sxs-lookup"><span data-stu-id="fbfac-122">The value of the **Path** parameter is the path to the Cat.txt file.</span></span> <span data-ttu-id="fbfac-123">**Aclobject** パラメーターの値は、モデル acl (この場合は、変数に保存されている Dog.txt の acl) です `$DogACL` 。</span><span class="sxs-lookup"><span data-stu-id="fbfac-123">The value of the **AclObject** parameter is the model ACL, in this case, the ACL of Dog.txt as saved in the `$DogACL` variable.</span></span>

### <span data-ttu-id="fbfac-124">例 2: パイプライン演算子を使用して記述子を渡す</span><span class="sxs-lookup"><span data-stu-id="fbfac-124">Example 2: Use the pipeline operator to pass a descriptor</span></span>

```powershell
Get-Acl -Path "C:\Dog.txt" | Set-Acl -Path "C:\Cat.txt"
```

<span data-ttu-id="fbfac-125">このコマンドは、前の例のコマンドとほぼ同じですが、パイプライン演算子 () を使用してコマンドからコマンドにセキュリティ記述子を送信する点が異なり `|` `Get-Acl` `Set-Acl` ます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-125">This command is almost the same as the command in the previous example, except that it uses a pipeline operator (`|`) to send the security descriptor from a `Get-Acl` command to a `Set-Acl` command.</span></span>

<span data-ttu-id="fbfac-126">最初のコマンドは、 `Get-Acl` コマンドレットを使用して、Dog.txt ファイルのセキュリティ記述子を取得します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-126">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span> <span data-ttu-id="fbfac-127">パイプライン演算子 () は、 `|` Dog.txt セキュリティ記述子を表すオブジェクトを `Set-Acl` コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-127">The pipeline operator (`|`) passes an object that represents the Dog.txt security descriptor to the `Set-Acl` cmdlet.</span></span>

<span data-ttu-id="fbfac-128">2番目のコマンドは、を使用して `Set-Acl` Dog.txt のセキュリティ記述子を Cat.txt に適用します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-128">The second command uses `Set-Acl` to apply the security descriptor of Dog.txt to Cat.txt.</span></span>
<span data-ttu-id="fbfac-129">コマンドが完了すると、Dog.txt ファイルと Cat.txt ファイルの ACL は同一となります。</span><span class="sxs-lookup"><span data-stu-id="fbfac-129">When the command completes, the ACLs of the Dog.txt and Cat.txt files are identical.</span></span>

### <span data-ttu-id="fbfac-130">例 3: 複数のファイルにセキュリティ記述子を適用する</span><span class="sxs-lookup"><span data-stu-id="fbfac-130">Example 3: Apply a security descriptor to multiple files</span></span>

```powershell
$NewAcl = Get-Acl File0.txt
Get-ChildItem -Path "C:\temp" -Recurse -Include "*.txt" -Force | Set-Acl -AclObject $NewAcl
```

<span data-ttu-id="fbfac-131">これらのコマンドは、File0.txt ファイル内のセキュリティ記述子を、 `C:\Temp` ディレクトリとそのすべてのサブディレクトリ内のすべてのテキストファイルに適用します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-131">These commands apply the security descriptors in the File0.txt file to all text files in the `C:\Temp` directory and all of its subdirectories.</span></span>

<span data-ttu-id="fbfac-132">最初のコマンドは、現在のディレクトリ内の File0.txt ファイルのセキュリティ記述子を取得し、代入演算子 () を使用し `=` て変数に格納し `$NewACL` ます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-132">The first command gets the security descriptor of the File0.txt file in the current directory and uses the assignment operator (`=`) to store it in the `$NewACL` variable.</span></span>

<span data-ttu-id="fbfac-133">パイプラインの最初のコマンドは、Get-ChildItem コマンドレットを使用して、ディレクトリ内のすべてのテキストファイルを取得し `C:\Temp` ます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-133">The first command in the pipeline uses the Get-ChildItem cmdlet to get all of the text files in the `C:\Temp` directory.</span></span> <span data-ttu-id="fbfac-134">**再帰** パラメーターは、のすべてのサブディレクトリに対してコマンドを拡張し `C:\temp` ます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-134">The **Recurse** parameter extends the command to all subdirectories of `C:\temp`.</span></span> <span data-ttu-id="fbfac-135">**Include** パラメーターは、ファイル名拡張子を持つファイルに取得されるファイルを制限し `.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-135">The **Include** parameter limits the files retrieved to those with the `.txt` file name extension.</span></span> <span data-ttu-id="fbfac-136">**Force** パラメーターは、隠しファイルを取得します。このパラメーターが指定されない場合、隠しファイルは除外されます</span><span class="sxs-lookup"><span data-stu-id="fbfac-136">The **Force** parameter gets hidden files, which would otherwise be excluded.</span></span> <span data-ttu-id="fbfac-137">(を使用することはできません `c:\temp\*.txt` 。これは、 **再帰** パラメーターは、ファイルではなくディレクトリで動作するためです)。</span><span class="sxs-lookup"><span data-stu-id="fbfac-137">(You cannot use `c:\temp\*.txt`, because the **Recurse** parameter works on directories, not on files.)</span></span>

<span data-ttu-id="fbfac-138">パイプライン演算子 () は、 `|` 取得したファイルを表すオブジェクトをコマンドレットに送信します。これにより、 `Set-Acl` **aclobject** パラメーターのセキュリティ記述子がパイプライン内のすべてのファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-138">The pipeline operator (`|`) sends the objects representing the retrieved files to the `Set-Acl` cmdlet, which applies the security descriptor in the **AclObject** parameter to all of the files in the pipeline.</span></span>

<span data-ttu-id="fbfac-139">実際には、複数の項目に影響を与える可能性のあるすべてのコマンドで **WhatIf** パラメーターを使用することをお勧めし `Set-Acl` ます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-139">In practice, it is best to use the **WhatIf** parameter with all `Set-Acl` commands that can affect more than one item.</span></span> <span data-ttu-id="fbfac-140">この場合、パイプラインの2番目のコマンドはになり `Set-Acl -AclObject $NewAcl -WhatIf` ます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-140">In this case, the second command in the pipeline would be `Set-Acl -AclObject $NewAcl -WhatIf`.</span></span> <span data-ttu-id="fbfac-141">このコマンドは、コマンドによって影響を受けるファイルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-141">This command lists the files that would be affected by the command.</span></span> <span data-ttu-id="fbfac-142">結果を確認した後、 **WhatIf** パラメーターを指定せずにコマンドを再度実行できます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-142">After reviewing the result, you can run the command again without the **WhatIf** parameter.</span></span>

### <span data-ttu-id="fbfac-143">例 4: 継承を無効にし、継承されたアクセス規則を保持する</span><span class="sxs-lookup"><span data-stu-id="fbfac-143">Example 4: Disable inheritance and preserve inherited access rules</span></span>

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
$isProtected = $true
$preserveInheritance = $true
$NewAcl.SetAccessRuleProtection($isProtected, $preserveInheritance)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

<span data-ttu-id="fbfac-144">これらのコマンドは、既存の継承されたアクセス規則を保持したまま、親フォルダーからのアクセス継承を無効にします。</span><span class="sxs-lookup"><span data-stu-id="fbfac-144">These commands is will disable access inheritance from parent folders, while still preserving the existing inherited access rules.</span></span>

<span data-ttu-id="fbfac-145">最初のコマンドは、 `Get-Acl` コマンドレットを使用して、Dog.txt ファイルのセキュリティ記述子を取得します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-145">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>

<span data-ttu-id="fbfac-146">次に、継承されたアクセス規則を明示的なアクセス規則に変換するための変数が作成されます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-146">Next, variables are created to convert the inherited access rules to explicit access rules.</span></span> <span data-ttu-id="fbfac-147">このに関連付けられているアクセス規則を継承から保護するには、 `$isProtected` 変数をに設定 `$true` します。継承を許可するには、 `$isProtected` をに設定し `$false` ます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-147">To protect the access rules associated with this from inheritance, set the `$isProtected` variable to `$true`.to allow inheritance, set `$isProtected` to `$false`.</span></span> <span data-ttu-id="fbfac-148">詳細については、「 [アクセス規則の保護の設定](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbfac-148">For more information, see [set access rule protection](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection).</span></span>
<span data-ttu-id="fbfac-149">継承された `$preserveInheritance` アクセス規則を保持するためにに設定された変数 `$true` 。継承されたアクセス規則を削除する場合は false。</span><span class="sxs-lookup"><span data-stu-id="fbfac-149">The `$preserveInheritance` variable set to `$true` to preserve inherited access rules; false to remove inherited access rules.</span></span> <span data-ttu-id="fbfac-150">次に、 **Setaccessruleprotection ()** メソッドを使用して、アクセス規則の保護を更新します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-150">Then the access rule protection is updated using the **SetAccessRuleProtection()** method.</span></span>

<span data-ttu-id="fbfac-151">最後のコマンドは、を使用して、 `Set-Acl` のセキュリティ記述子を Dog.txt に適用します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-151">The last command uses `Set-Acl` to apply the security descriptor of to Dog.txt.</span></span> <span data-ttu-id="fbfac-152">コマンドが完了すると、ペットフォルダーから継承された Dog.txt の Acl が Dog.txt に直接適用され、ペットに追加された新しいアクセスポリシーによって Dog.txt へのアクセスが変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="fbfac-152">When the command completes, the ACLs of the Dog.txt that were inherited from the Pets folder will be applied directly to Dog.txt, and new access policies added to Pets will not change the access to Dog.txt.</span></span>

### <span data-ttu-id="fbfac-153">例 5: 管理者にファイルのフルコントロールを付与する</span><span class="sxs-lookup"><span data-stu-id="fbfac-153">Example 5: Grant Administrators Full Control of the file</span></span>

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
# Set properties
$identity = "BUILTIN\Administrators"
$fileSystemRights = "FullControl"
$type = "Allow"
# Create new rule
$fileSystemAccessRuleArgumentList = $identity, $fileSystemRights, $type
$fileSystemAccessRule = New-Object -TypeName System.Security.AccessControl.FileSystemAccessRule -ArgumentList $fileSystemAccessRuleArgumentList
# Apply new rule
$NewAcl.SetAccessRule($fileSystemAccessRule)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

<span data-ttu-id="fbfac-154">このコマンドを実行すると、 **BUILTIN\Administrators** グループに Dog.txt ファイルのフルコントロールが与えられます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-154">This command will grant the **BUILTIN\Administrators** group Full control of the Dog.txt file.</span></span>

<span data-ttu-id="fbfac-155">最初のコマンドは、 `Get-Acl` コマンドレットを使用して、Dog.txt ファイルのセキュリティ記述子を取得します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-155">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>

<span data-ttu-id="fbfac-156">次の変数が作成され、Dog.txt ファイルのフルコントロールを **BUILTIN\Administrators** グループに付与します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-156">Next variables are created to grant the **BUILTIN\Administrators** group full control of the Dog.txt file.</span></span> <span data-ttu-id="fbfac-157">`$identity`[ユーザーアカウント](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor)の名前に設定された変数。</span><span class="sxs-lookup"><span data-stu-id="fbfac-157">The `$identity` variable set to the name of a [user account](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor).</span></span> <span data-ttu-id="fbfac-158">`$fileSystemRights`変数が FullControl に設定されています。また、アクセス規則に関連付けられている操作の種類を指定する[filesystemrights](/dotnet/api/system.security.accesscontrol.filesystemrights)値のいずれかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-158">The `$fileSystemRights` variable set to FullControl, and can be any one of the [FileSystemRights](/dotnet/api/system.security.accesscontrol.filesystemrights) values that specifies the type of operation associated with the access rule.</span></span> <span data-ttu-id="fbfac-159">`$type`操作を許可するか拒否するかを指定する変数が "allow" に設定されています。</span><span class="sxs-lookup"><span data-stu-id="fbfac-159">The `$type` variable set to "Allow" to specifies whether to allow or deny the operation.</span></span> <span data-ttu-id="fbfac-160">`$fileSystemAccessRuleArgumentList`変数は、新しい **Filesystemaccessrule** オブジェクトを作成するときに渡される引数リストです。</span><span class="sxs-lookup"><span data-stu-id="fbfac-160">The `$fileSystemAccessRuleArgumentList` variable is an argument list is to be passed when making the new **FileSystemAccessRule** object.</span></span> <span data-ttu-id="fbfac-161">次に、新しい **Filesystemaccessrule** オブジェクトが作成され、 **Filesystemaccessrule** オブジェクトが **setaccessrule ()** メソッドに渡され、新しいアクセス規則が追加されます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-161">Then a new **FileSystemAccessRule** object is created, and the **FileSystemAccessRule** object is passed to the **SetAccessRule()** method, adds the new access rule.</span></span>

<span data-ttu-id="fbfac-162">最後のコマンドは、を使用して、 `Set-Acl` のセキュリティ記述子を Dog.txt に適用します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-162">The last command uses `Set-Acl` to apply the security descriptor of to Dog.txt.</span></span> <span data-ttu-id="fbfac-163">コマンドが完了すると、 **BUILTIN\Administrators** グループは Dog.txt を完全に制御できるようになります。</span><span class="sxs-lookup"><span data-stu-id="fbfac-163">When the command completes, the **BUILTIN\Administrators** group will have full control of the Dog.txt.</span></span>

## <span data-ttu-id="fbfac-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fbfac-164">PARAMETERS</span></span>

### <span data-ttu-id="fbfac-165">-AclObject</span><span class="sxs-lookup"><span data-stu-id="fbfac-165">-AclObject</span></span>

<span data-ttu-id="fbfac-166">目的のプロパティの値を備えた　ACL を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-166">Specifies an ACL with the desired property values.</span></span> <span data-ttu-id="fbfac-167">`Set-Acl` 指定したセキュリティオブジェクトの値と一致するように、 **Path** または **InputObject** パラメーターで指定された項目の ACL を変更します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-167">`Set-Acl` changes the ACL of item specified by the **Path** or **InputObject** parameter to match the values in the specified security object.</span></span>

<span data-ttu-id="fbfac-168">コマンドの出力を `Get-Acl` 変数に保存し、 **Aclobject** パラメーターを使用して変数を渡すことも、コマンドを入力することもでき `Get-Acl` ます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-168">You can save the output of a `Get-Acl` command in a variable and then use the **AclObject** parameter to pass the variable, or type a `Get-Acl` command.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fbfac-169">-ClearCentralAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="fbfac-169">-ClearCentralAccessPolicy</span></span>

<span data-ttu-id="fbfac-170">指定された項目から、集約型アクセス ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-170">Removes the central access policy from the specified item.</span></span>

<span data-ttu-id="fbfac-171">Windows Server 2012 以降では、管理者は Active Directory とグループポリシーを使用して、ユーザーとグループの集約型アクセスポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-171">Beginning in Windows Server 2012, administrators can use Active Directory and Group Policy to set central access policies for users and groups.</span></span> <span data-ttu-id="fbfac-172">詳細については、「 [Dynamic Access Control: シナリオの概要](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbfac-172">For more information, see [Dynamic Access Control: Scenario Overview](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span></span>

<span data-ttu-id="fbfac-173">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fbfac-173">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByPath, ByLiteralPath
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbfac-174">-除外</span><span class="sxs-lookup"><span data-stu-id="fbfac-174">-Exclude</span></span>

<span data-ttu-id="fbfac-175">指定した項目を除外します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-175">Omits the specified items.</span></span> <span data-ttu-id="fbfac-176">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-176">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="fbfac-177">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-177">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="fbfac-178">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-178">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="fbfac-179">-Filter</span><span class="sxs-lookup"><span data-stu-id="fbfac-179">-Filter</span></span>

<span data-ttu-id="fbfac-180">プロバイダーの形式や言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-180">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="fbfac-181">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-181">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="fbfac-182">ワイルドカードを使用できるかどうかなど、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="fbfac-182">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="fbfac-183">フィルターは他のパラメーターよりも効率的です。これは、オブジェクトを取得した後に PowerShell がオブジェクトをフィルター処理するのではなく、オブジェクトを取得するときにプロバイダーが適用するためです。</span><span class="sxs-lookup"><span data-stu-id="fbfac-183">Filters are more efficient than other parameters, because the provider applies them when retrieving the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="fbfac-184">-Include</span><span class="sxs-lookup"><span data-stu-id="fbfac-184">-Include</span></span>

<span data-ttu-id="fbfac-185">指定した項目だけを変更します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-185">Changes only the specified items.</span></span> <span data-ttu-id="fbfac-186">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-186">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="fbfac-187">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-187">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="fbfac-188">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-188">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="fbfac-189">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fbfac-189">-InputObject</span></span>

<span data-ttu-id="fbfac-190">指定されたオブジェクトのセキュリティ記述子を変更します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-190">Changes the security descriptor of the specified object.</span></span> <span data-ttu-id="fbfac-191">オブジェクトが格納されている変数、またはオブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-191">Enter a variable that contains the object or a command that gets the object.</span></span>

<span data-ttu-id="fbfac-192">パイプを使用して変更するオブジェクトをにパイプすることはできません `Set-Acl` 。</span><span class="sxs-lookup"><span data-stu-id="fbfac-192">You cannot pipe the object to be changed to `Set-Acl`.</span></span> <span data-ttu-id="fbfac-193">代わりに、**InputObject** パラメーターをコマンド内で明示的に使用します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-193">Instead, use the **InputObject** parameter explicitly in the command.</span></span>

<span data-ttu-id="fbfac-194">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fbfac-194">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fbfac-195">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="fbfac-195">-LiteralPath</span></span>

<span data-ttu-id="fbfac-196">指定した項目のセキュリティ記述子を変更します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-196">Changes the security descriptor of the specified item.</span></span> <span data-ttu-id="fbfac-197">**Path** と異なり、**LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-197">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="fbfac-198">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="fbfac-198">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="fbfac-199">パスにエスケープ文字が含まれている場合は、単一引用符 () で囲み `'` ます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-199">If the path includes escape characters, enclose it in single quotation marks (`'`).</span></span>
<span data-ttu-id="fbfac-200">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="fbfac-200">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="fbfac-201">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fbfac-201">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fbfac-202">-Passthru</span><span class="sxs-lookup"><span data-stu-id="fbfac-202">-Passthru</span></span>

<span data-ttu-id="fbfac-203">変更されたセキュリティ記述子を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-203">Returns an object that represents the security descriptor that was changed.</span></span> <span data-ttu-id="fbfac-204">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="fbfac-204">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="fbfac-205">-Path</span><span class="sxs-lookup"><span data-stu-id="fbfac-205">-Path</span></span>

<span data-ttu-id="fbfac-206">指定した項目のセキュリティ記述子を変更します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-206">Changes the security descriptor of the specified item.</span></span> <span data-ttu-id="fbfac-207">ファイルまたはレジストリ キーへのパスなどの項目へのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-207">Enter the path to an item, such as a path to a file or registry key.</span></span> <span data-ttu-id="fbfac-208">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-208">Wildcards are permitted.</span></span>

<span data-ttu-id="fbfac-209">`Set-Acl`( **Aclobject** または **SecurityDescriptor** パラメーターを使用するか、セキュリティオブジェクトを Get-Acl からに渡すことによって) セキュリティオブジェクトをに渡し `Set-Acl` 、 **path** パラメーター (name と value) を省略すると、は `Set-Acl` セキュリティオブジェクトに含まれているパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-209">If you pass a security object to `Set-Acl` (either by using the **AclObject** or **SecurityDescriptor** parameters or by passing a security object from Get-Acl to `Set-Acl`), and you omit the **Path** parameter (name and value), `Set-Acl` uses the path that is included in the security object.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="fbfac-210">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fbfac-210">-Confirm</span></span>

<span data-ttu-id="fbfac-211">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-211">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fbfac-212">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fbfac-212">-WhatIf</span></span>

<span data-ttu-id="fbfac-213">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-213">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="fbfac-214">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="fbfac-214">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fbfac-215">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fbfac-215">CommonParameters</span></span>

<span data-ttu-id="fbfac-216">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="fbfac-216">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fbfac-217">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbfac-217">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fbfac-218">入力</span><span class="sxs-lookup"><span data-stu-id="fbfac-218">INPUTS</span></span>

### <span data-ttu-id="fbfac-219">Accesscontrol-namespace、Accesscontrol-namespace、...... CommonSecurityDescriptor</span><span class="sxs-lookup"><span data-stu-id="fbfac-219">System.Security.AccessControl.ObjectSecurity, System.Security.AccessControl.CommonSecurityDescriptor</span></span>

<span data-ttu-id="fbfac-220">パイプを使用して、ACL オブジェクトまたはセキュリティ記述子をにパイプすることができ `Set-Acl` ます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-220">You can pipe an ACL object or a security descriptor to `Set-Acl`.</span></span>

## <span data-ttu-id="fbfac-221">出力</span><span class="sxs-lookup"><span data-stu-id="fbfac-221">OUTPUTS</span></span>

### <span data-ttu-id="fbfac-222">Accesscontrol-namespace. System.security.accesscontrol.filesecurity</span><span class="sxs-lookup"><span data-stu-id="fbfac-222">System.Security.AccessControl.FileSecurity</span></span>

<span data-ttu-id="fbfac-223">既定で `Set-Acl` は、は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="fbfac-223">By default, `Set-Acl` does not generate any output.</span></span> <span data-ttu-id="fbfac-224">ただし、**Passthru** パラメーターを使用すると、セキュリティ オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="fbfac-224">However, if you use the **Passthru** parameter, it generates a security object.</span></span> <span data-ttu-id="fbfac-225">セキュリティ オブジェクトの種類は、項目の種類に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="fbfac-225">The type of the security object depends on the type of the item.</span></span>

## <span data-ttu-id="fbfac-226">注</span><span class="sxs-lookup"><span data-stu-id="fbfac-226">NOTES</span></span>

<span data-ttu-id="fbfac-227">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-227">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="fbfac-228">`Set-Acl`コマンドレットは、PowerShell ファイルシステムとレジストリプロバイダーによってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fbfac-228">The `Set-Acl` cmdlet is supported by the PowerShell file system and registry providers.</span></span> <span data-ttu-id="fbfac-229">そのため、そのコマンドレットを使用して、ファイル、ディレクトリ、およびレジストリ キーのセキュリティ記述子を変更できます。</span><span class="sxs-lookup"><span data-stu-id="fbfac-229">As such, you can use it to change the security descriptors of files, directories, and registry keys.</span></span>

## <span data-ttu-id="fbfac-230">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fbfac-230">RELATED LINKS</span></span>

[<span data-ttu-id="fbfac-231">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="fbfac-231">Get-Acl</span></span>](Get-Acl.md)

[<span data-ttu-id="fbfac-232">FileSystemAccessRule</span><span class="sxs-lookup"><span data-stu-id="fbfac-232">FileSystemAccessRule</span></span>](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor)

[<span data-ttu-id="fbfac-233">ObjectSecurity. SetAccessRuleProtection</span><span class="sxs-lookup"><span data-stu-id="fbfac-233">ObjectSecurity.SetAccessRuleProtection</span></span>](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection)

[<span data-ttu-id="fbfac-234">FileSystemRights</span><span class="sxs-lookup"><span data-stu-id="fbfac-234">FileSystemRights</span></span>](/dotnet/api/system.security.accesscontrol.filesystemrights)
