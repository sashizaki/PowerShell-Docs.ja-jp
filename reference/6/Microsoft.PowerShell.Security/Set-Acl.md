---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-acl?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Acl
ms.openlocfilehash: 0f5757d7e9fb2615149fd08473685491bfccada7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216888"
---
# <span data-ttu-id="cfcfa-103">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="cfcfa-103">Set-Acl</span></span>

## <span data-ttu-id="cfcfa-104">概要</span><span class="sxs-lookup"><span data-stu-id="cfcfa-104">SYNOPSIS</span></span>
<span data-ttu-id="cfcfa-105">ファイルやレジストリ キーなど、指定した項目のセキュリティ記述子を変更します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-105">Changes the security descriptor of a specified item, such as a file or a registry key.</span></span>

## <span data-ttu-id="cfcfa-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cfcfa-106">SYNTAX</span></span>

### <span data-ttu-id="cfcfa-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="cfcfa-107">ByPath (Default)</span></span>

```
Set-Acl [-Path] <String[]> [-AclObject] <Object> [-ClearCentralAccessPolicy] [-Passthru] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cfcfa-108">ByInputObject</span><span class="sxs-lookup"><span data-stu-id="cfcfa-108">ByInputObject</span></span>

```
Set-Acl [-InputObject] <PSObject> [-AclObject] <Object> [-Passthru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cfcfa-109">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="cfcfa-109">ByLiteralPath</span></span>

```
Set-Acl -LiteralPath <String[]> [-AclObject] <Object> [-ClearCentralAccessPolicy] [-Passthru]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cfcfa-110">Description</span><span class="sxs-lookup"><span data-stu-id="cfcfa-110">DESCRIPTION</span></span>

<span data-ttu-id="cfcfa-111">`Set-Acl`このコマンドレットは、指定した項目 (ファイルやレジストリキーなど) のセキュリティ記述子を、指定したセキュリティ記述子の値と一致するように変更します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-111">The `Set-Acl` cmdlet changes the security descriptor of a specified item, such as a file or a registry key, to match the values in a security descriptor that you supply.</span></span>

<span data-ttu-id="cfcfa-112">を使用するに `Set-Acl` は、 **Path** または **InputObject** パラメーターを使用して、セキュリティ記述子を変更する項目を識別します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-112">To use `Set-Acl`, use the **Path** or **InputObject** parameter to identify the item whose security descriptor you want to change.</span></span> <span data-ttu-id="cfcfa-113">次に、 **AclObject** または **SecurityDescriptor** パラメーターを使用して、適用する値が含まれるセキュリティ記述子を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-113">Then, use the **AclObject** or **SecurityDescriptor** parameters to supply a security descriptor that has the values you want to apply.</span></span> <span data-ttu-id="cfcfa-114">`Set-Acl` 指定されたセキュリティ記述子を適用します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-114">`Set-Acl` applies the security descriptor that is supplied.</span></span> <span data-ttu-id="cfcfa-115">**AclObject** パラメーターの値をモデルとして使用し、項目のセキュリティ記述子の値を **AclObject** パラメーターの値と一致するように変更します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-115">It uses the value of the **AclObject** parameter as a model and changes the values in the item's security descriptor to match the values in the **AclObject** parameter.</span></span>

## <span data-ttu-id="cfcfa-116">例</span><span class="sxs-lookup"><span data-stu-id="cfcfa-116">EXAMPLES</span></span>

### <span data-ttu-id="cfcfa-117">例 1: あるファイルから別のファイルにセキュリティ記述子をコピーする</span><span class="sxs-lookup"><span data-stu-id="cfcfa-117">Example 1: Copy a security descriptor from one file to another</span></span>

```powershell
$DogACL = Get-Acl -Path "C:\Dog.txt"
Set-Acl -Path "C:\Cat.txt" -AclObject $DogACL
```

<span data-ttu-id="cfcfa-118">これらのコマンドは、Dog.txt ファイルのセキュリティ記述子から Cat.txt ファイルのセキュリティ記述子に値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-118">These commands copy the values from the security descriptor of the Dog.txt file to the security descriptor of the Cat.txt file.</span></span> <span data-ttu-id="cfcfa-119">コマンドが完了すると、Dog.txt ファイルと Cat.txt ファイルのセキュリティ記述子は同一となります。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-119">When the commands complete, the security descriptors of the Dog.txt and Cat.txt files are identical.</span></span>

<span data-ttu-id="cfcfa-120">最初のコマンドは、 `Get-Acl` コマンドレットを使用して、Dog.txt ファイルのセキュリティ記述子を取得します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-120">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>
<span data-ttu-id="cfcfa-121">代入演算子 () は、 `=` $DogACL 変数の値にセキュリティ記述子を格納します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-121">The assignment operator (`=`) stores the security descriptor in the value of the $DogACL variable.</span></span>

<span data-ttu-id="cfcfa-122">2番目のコマンドは、を使用して `Set-Acl` Cat.txt の ACL の値をの値に変更し `$DogACL` ます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-122">The second command uses `Set-Acl` to change the values in the ACL of Cat.txt to the values in `$DogACL`.</span></span>

<span data-ttu-id="cfcfa-123">**Path** パラメーターの値は、Cat.txt ファイルへのパスです。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-123">The value of the **Path** parameter is the path to the Cat.txt file.</span></span> <span data-ttu-id="cfcfa-124">**Aclobject** パラメーターの値は、モデル acl (この場合は、変数に保存されている Dog.txt の acl) です `$DogACL` 。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-124">The value of the **AclObject** parameter is the model ACL, in this case, the ACL of Dog.txt as saved in the `$DogACL` variable.</span></span>

### <span data-ttu-id="cfcfa-125">例 2: パイプライン演算子を使用して記述子を渡す</span><span class="sxs-lookup"><span data-stu-id="cfcfa-125">Example 2: Use the pipeline operator to pass a descriptor</span></span>

```powershell
Get-Acl -Path "C:\Dog.txt" | Set-Acl -Path "C:\Cat.txt"
```

<span data-ttu-id="cfcfa-126">このコマンドは、前の例のコマンドとほぼ同じですが、パイプライン演算子 () を使用してコマンドからコマンドにセキュリティ記述子を送信する点が異なり `|` `Get-Acl` `Set-Acl` ます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-126">This command is almost the same as the command in the previous example, except that it uses a pipeline operator (`|`) to send the security descriptor from a `Get-Acl` command to a `Set-Acl` command.</span></span>

<span data-ttu-id="cfcfa-127">最初のコマンドは、 `Get-Acl` コマンドレットを使用して、Dog.txt ファイルのセキュリティ記述子を取得します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-127">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span> <span data-ttu-id="cfcfa-128">パイプライン演算子 () は、 `|` Dog.txt セキュリティ記述子を表すオブジェクトを `Set-Acl` コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-128">The pipeline operator (`|`) passes an object that represents the Dog.txt security descriptor to the `Set-Acl` cmdlet.</span></span>

<span data-ttu-id="cfcfa-129">2番目のコマンドは、を使用して `Set-Acl` Dog.txt のセキュリティ記述子を Cat.txt に適用します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-129">The second command uses `Set-Acl` to apply the security descriptor of Dog.txt to Cat.txt.</span></span>
<span data-ttu-id="cfcfa-130">コマンドが完了すると、Dog.txt ファイルと Cat.txt ファイルの ACL は同一となります。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-130">When the command completes, the ACLs of the Dog.txt and Cat.txt files are identical.</span></span>

### <span data-ttu-id="cfcfa-131">例 3: 複数のファイルにセキュリティ記述子を適用する</span><span class="sxs-lookup"><span data-stu-id="cfcfa-131">Example 3: Apply a security descriptor to multiple files</span></span>

```powershell
$NewAcl = Get-Acl File0.txt
Get-ChildItem -Path "C:\temp" -Recurse -Include "*.txt" -Force | Set-Acl -AclObject $NewAcl
```

<span data-ttu-id="cfcfa-132">これらのコマンドは、File0.txt ファイル内のセキュリティ記述子を、 `C:\Temp` ディレクトリとそのすべてのサブディレクトリ内のすべてのテキストファイルに適用します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-132">These commands apply the security descriptors in the File0.txt file to all text files in the `C:\Temp` directory and all of its subdirectories.</span></span>

<span data-ttu-id="cfcfa-133">最初のコマンドは、現在のディレクトリ内の File0.txt ファイルのセキュリティ記述子を取得し、代入演算子 () を使用し `=` て変数に格納し `$NewACL` ます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-133">The first command gets the security descriptor of the File0.txt file in the current directory and uses the assignment operator (`=`) to store it in the `$NewACL` variable.</span></span>

<span data-ttu-id="cfcfa-134">パイプラインの最初のコマンドは、Get-ChildItem コマンドレットを使用して、ディレクトリ内のすべてのテキストファイルを取得し `C:\Temp` ます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-134">The first command in the pipeline uses the Get-ChildItem cmdlet to get all of the text files in the `C:\Temp` directory.</span></span> <span data-ttu-id="cfcfa-135">**再帰** パラメーターは、のすべてのサブディレクトリに対してコマンドを拡張し `C:\temp` ます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-135">The **Recurse** parameter extends the command to all subdirectories of `C:\temp`.</span></span> <span data-ttu-id="cfcfa-136">**Include** パラメーターは、ファイル名拡張子を持つファイルに取得されるファイルを制限し `.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-136">The **Include** parameter limits the files retrieved to those with the `.txt` file name extension.</span></span> <span data-ttu-id="cfcfa-137">**Force** パラメーターは、隠しファイルを取得します。このパラメーターが指定されない場合、隠しファイルは除外されます</span><span class="sxs-lookup"><span data-stu-id="cfcfa-137">The **Force** parameter gets hidden files, which would otherwise be excluded.</span></span> <span data-ttu-id="cfcfa-138">(を使用することはできません `c:\temp\*.txt` 。これは、 **再帰** パラメーターは、ファイルではなくディレクトリで動作するためです)。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-138">(You cannot use `c:\temp\*.txt`, because the **Recurse** parameter works on directories, not on files.)</span></span>

<span data-ttu-id="cfcfa-139">パイプライン演算子 () は、 `|` 取得したファイルを表すオブジェクトをコマンドレットに送信します。これにより、 `Set-Acl` **aclobject** パラメーターのセキュリティ記述子がパイプライン内のすべてのファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-139">The pipeline operator (`|`) sends the objects representing the retrieved files to the `Set-Acl` cmdlet, which applies the security descriptor in the **AclObject** parameter to all of the files in the pipeline.</span></span>

<span data-ttu-id="cfcfa-140">実際には、複数の項目に影響を与える可能性のあるすべてのコマンドで **WhatIf** パラメーターを使用することをお勧めし `Set-Acl` ます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-140">In practice, it is best to use the **WhatIf** parameter with all `Set-Acl` commands that can affect more than one item.</span></span> <span data-ttu-id="cfcfa-141">この場合、パイプラインの2番目のコマンドはになり `Set-Acl -AclObject $NewAcl -WhatIf` ます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-141">In this case, the second command in the pipeline would be `Set-Acl -AclObject $NewAcl -WhatIf`.</span></span> <span data-ttu-id="cfcfa-142">このコマンドは、コマンドによって影響を受けるファイルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-142">This command lists the files that would be affected by the command.</span></span> <span data-ttu-id="cfcfa-143">結果を確認した後、 **WhatIf** パラメーターを指定せずにコマンドを再度実行できます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-143">After reviewing the result, you can run the command again without the **WhatIf** parameter.</span></span>

### <span data-ttu-id="cfcfa-144">例 4: 継承を無効にし、継承されたアクセス規則を保持する</span><span class="sxs-lookup"><span data-stu-id="cfcfa-144">Example 4: Disable inheritance and preserve inherited access rules</span></span>

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
$isProtected = $true
$preserveInheritance = $true
$NewAcl.SetAccessRuleProtection($isProtected, $preserveInheritance)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

<span data-ttu-id="cfcfa-145">これらのコマンドは、既存の継承されたアクセス規則を保持したまま、親フォルダーからのアクセス継承を無効にします。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-145">These commands is will disable access inheritance from parent folders, while still preserving the existing inherited access rules.</span></span>

<span data-ttu-id="cfcfa-146">最初のコマンドは、 `Get-Acl` コマンドレットを使用して、Dog.txt ファイルのセキュリティ記述子を取得します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-146">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>

<span data-ttu-id="cfcfa-147">次に、継承されたアクセス規則を明示的なアクセス規則に変換するための変数が作成されます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-147">Next, variables are created to convert the inherited access rules to explicit access rules.</span></span> <span data-ttu-id="cfcfa-148">このに関連付けられているアクセス規則を継承から保護するには、 `$isProtected` 変数をに設定 `$true` します。継承を許可するには、 `$isProtected` をに設定し `$false` ます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-148">To protect the access rules associated with this from inheritance, set the `$isProtected` variable to `$true`.to allow inheritance, set `$isProtected` to `$false`.</span></span> <span data-ttu-id="cfcfa-149">詳細については、「 [アクセス規則の保護の設定](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-149">For more information, see [set access rule protection](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection).</span></span>
<span data-ttu-id="cfcfa-150">継承された `$preserveInheritance` アクセス規則を保持するためにに設定された変数 `$true` 。継承されたアクセス規則を削除する場合は false。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-150">The `$preserveInheritance` variable set to `$true` to preserve inherited access rules; false to remove inherited access rules.</span></span> <span data-ttu-id="cfcfa-151">次に、 **Setaccessruleprotection ()** メソッドを使用して、アクセス規則の保護を更新します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-151">Then the access rule protection is updated using the **SetAccessRuleProtection()** method.</span></span>

<span data-ttu-id="cfcfa-152">最後のコマンドは、を使用して、 `Set-Acl` のセキュリティ記述子を Dog.txt に適用します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-152">The last command uses `Set-Acl` to apply the security descriptor of to Dog.txt.</span></span> <span data-ttu-id="cfcfa-153">コマンドが完了すると、ペットフォルダーから継承された Dog.txt の Acl が Dog.txt に直接適用され、ペットに追加された新しいアクセスポリシーによって Dog.txt へのアクセスが変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-153">When the command completes, the ACLs of the Dog.txt that were inherited from the Pets folder will be applied directly to Dog.txt, and new access policies added to Pets will not change the access to Dog.txt.</span></span>

### <span data-ttu-id="cfcfa-154">例 5: 管理者にファイルのフルコントロールを付与する</span><span class="sxs-lookup"><span data-stu-id="cfcfa-154">Example 5: Grant Administrators Full Control of the file</span></span>

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

<span data-ttu-id="cfcfa-155">このコマンドを実行すると、 **BUILTIN\Administrators** グループに Dog.txt ファイルのフルコントロールが与えられます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-155">This command will grant the **BUILTIN\Administrators** group Full control of the Dog.txt file.</span></span>

<span data-ttu-id="cfcfa-156">最初のコマンドは、 `Get-Acl` コマンドレットを使用して、Dog.txt ファイルのセキュリティ記述子を取得します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-156">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>

<span data-ttu-id="cfcfa-157">次の変数が作成され、Dog.txt ファイルのフルコントロールを **BUILTIN\Administrators** グループに付与します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-157">Next variables are created to grant the **BUILTIN\Administrators** group full control of the Dog.txt file.</span></span> <span data-ttu-id="cfcfa-158">`$identity`[ユーザーアカウント](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor)の名前に設定された変数。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-158">The `$identity` variable set to the name of a [user account](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor).</span></span>
<span data-ttu-id="cfcfa-159">`$fileSystemRights`変数が FullControl に設定されています。また、アクセス規則に関連付けられている操作の種類を指定する[filesystemrights](/dotnet/api/system.security.accesscontrol.filesystemrights)値のいずれかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-159">The `$fileSystemRights` variable set to FullControl, and can be any one of the [FileSystemRights](/dotnet/api/system.security.accesscontrol.filesystemrights) values that specifies the type of operation associated with the access rule.</span></span> <span data-ttu-id="cfcfa-160">`$type`操作を許可するか拒否するかを指定する変数が "allow" に設定されています。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-160">The `$type` variable set to "Allow" to specifies whether to allow or deny the operation.</span></span> <span data-ttu-id="cfcfa-161">`$fileSystemAccessRuleArgumentList`変数は、新しい **Filesystemaccessrule** オブジェクトを作成するときに渡される引数リストです。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-161">The `$fileSystemAccessRuleArgumentList` variable is an argument list is to be passed when making the new **FileSystemAccessRule** object.</span></span> <span data-ttu-id="cfcfa-162">次に、新しい **Filesystemaccessrule** オブジェクトが作成され、 **Filesystemaccessrule** オブジェクトが **setaccessrule ()** メソッドに渡され、新しいアクセス規則が追加されます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-162">Then a new **FileSystemAccessRule** object is created, and the **FileSystemAccessRule** object is passed to the **SetAccessRule()** method, adds the new access rule.</span></span>

<span data-ttu-id="cfcfa-163">最後のコマンドは、を使用して、 `Set-Acl` のセキュリティ記述子を Dog.txt に適用します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-163">The last command uses `Set-Acl` to apply the security descriptor of to Dog.txt.</span></span>
<span data-ttu-id="cfcfa-164">コマンドが完了すると、 **BUILTIN\Administrators** グループは Dog.txt を完全に制御できるようになります。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-164">When the command completes, the **BUILTIN\Administrators** group will have full control of the Dog.txt.</span></span>

## <span data-ttu-id="cfcfa-165">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cfcfa-165">PARAMETERS</span></span>

### <span data-ttu-id="cfcfa-166">-AclObject</span><span class="sxs-lookup"><span data-stu-id="cfcfa-166">-AclObject</span></span>

<span data-ttu-id="cfcfa-167">目的のプロパティの値を備えた　ACL を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-167">Specifies an ACL with the desired property values.</span></span> <span data-ttu-id="cfcfa-168">`Set-Acl` 指定したセキュリティオブジェクトの値と一致するように、 **Path** または **InputObject** パラメーターで指定された項目の ACL を変更します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-168">`Set-Acl` changes the ACL of item specified by the **Path** or **InputObject** parameter to match the values in the specified security object.</span></span>

<span data-ttu-id="cfcfa-169">コマンドの出力を `Get-Acl` 変数に保存し、 **Aclobject** パラメーターを使用して変数を渡すことも、コマンドを入力することもでき `Get-Acl` ます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-169">You can save the output of a `Get-Acl` command in a variable and then use the **AclObject** parameter to pass the variable, or type a `Get-Acl` command.</span></span>

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

### <span data-ttu-id="cfcfa-170">-ClearCentralAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="cfcfa-170">-ClearCentralAccessPolicy</span></span>

<span data-ttu-id="cfcfa-171">指定された項目から、集約型アクセス ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-171">Removes the central access policy from the specified item.</span></span>

<span data-ttu-id="cfcfa-172">Windows Server 2012 以降では、管理者は Active Directory とグループポリシーを使用して、ユーザーとグループの集約型アクセスポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-172">Beginning in Windows Server 2012, administrators can use Active Directory and Group Policy to set central access policies for users and groups.</span></span> <span data-ttu-id="cfcfa-173">詳細については、「 [Dynamic Access Control: シナリオの概要](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-173">For more information, see [Dynamic Access Control: Scenario Overview](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span></span>

<span data-ttu-id="cfcfa-174">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-174">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="cfcfa-175">-除外</span><span class="sxs-lookup"><span data-stu-id="cfcfa-175">-Exclude</span></span>

<span data-ttu-id="cfcfa-176">指定した項目を除外します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-176">Omits the specified items.</span></span> <span data-ttu-id="cfcfa-177">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-177">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="cfcfa-178">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-178">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="cfcfa-179">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-179">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="cfcfa-180">-Filter</span><span class="sxs-lookup"><span data-stu-id="cfcfa-180">-Filter</span></span>

<span data-ttu-id="cfcfa-181">プロバイダーの形式や言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-181">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="cfcfa-182">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-182">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="cfcfa-183">ワイルドカードを使用できるかどうかなど、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-183">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="cfcfa-184">フィルターは他のパラメーターよりも効率的です。これは、オブジェクトを取得した後に PowerShell がオブジェクトをフィルター処理するのではなく、オブジェクトを取得するときにプロバイダーが適用するためです。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-184">Filters are more efficient than other parameters, because the provider applies them when retrieving the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="cfcfa-185">-Include</span><span class="sxs-lookup"><span data-stu-id="cfcfa-185">-Include</span></span>

<span data-ttu-id="cfcfa-186">指定した項目だけを変更します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-186">Changes only the specified items.</span></span> <span data-ttu-id="cfcfa-187">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-187">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="cfcfa-188">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-188">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="cfcfa-189">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-189">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="cfcfa-190">-InputObject</span><span class="sxs-lookup"><span data-stu-id="cfcfa-190">-InputObject</span></span>

<span data-ttu-id="cfcfa-191">指定されたオブジェクトのセキュリティ記述子を変更します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-191">Changes the security descriptor of the specified object.</span></span> <span data-ttu-id="cfcfa-192">オブジェクトが格納されている変数、またはオブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-192">Enter a variable that contains the object or a command that gets the object.</span></span>

<span data-ttu-id="cfcfa-193">パイプを使用して変更するオブジェクトをにパイプすることはできません `Set-Acl` 。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-193">You cannot pipe the object to be changed to `Set-Acl`.</span></span> <span data-ttu-id="cfcfa-194">代わりに、 **InputObject** パラメーターをコマンド内で明示的に使用します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-194">Instead, use the **InputObject** parameter explicitly in the command.</span></span>

<span data-ttu-id="cfcfa-195">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-195">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="cfcfa-196">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="cfcfa-196">-LiteralPath</span></span>

<span data-ttu-id="cfcfa-197">指定した項目のセキュリティ記述子を変更します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-197">Changes the security descriptor of the specified item.</span></span> <span data-ttu-id="cfcfa-198">**Path** と異なり、 **LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-198">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="cfcfa-199">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-199">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="cfcfa-200">パスにエスケープ文字が含まれている場合は、単一引用符 () で囲み `'` ます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-200">If the path includes escape characters, enclose it in single quotation marks (`'`).</span></span>
<span data-ttu-id="cfcfa-201">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-201">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="cfcfa-202">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-202">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="cfcfa-203">-Passthru</span><span class="sxs-lookup"><span data-stu-id="cfcfa-203">-Passthru</span></span>

<span data-ttu-id="cfcfa-204">変更されたセキュリティ記述子を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-204">Returns an object that represents the security descriptor that was changed.</span></span> <span data-ttu-id="cfcfa-205">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-205">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="cfcfa-206">-Path</span><span class="sxs-lookup"><span data-stu-id="cfcfa-206">-Path</span></span>

<span data-ttu-id="cfcfa-207">指定した項目のセキュリティ記述子を変更します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-207">Changes the security descriptor of the specified item.</span></span> <span data-ttu-id="cfcfa-208">ファイルまたはレジストリ キーへのパスなどの項目へのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-208">Enter the path to an item, such as a path to a file or registry key.</span></span> <span data-ttu-id="cfcfa-209">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-209">Wildcards are permitted.</span></span>

<span data-ttu-id="cfcfa-210">`Set-Acl`( **Aclobject** または **SecurityDescriptor** パラメーターを使用するか、セキュリティオブジェクトを Get-Acl からに渡すことによって) セキュリティオブジェクトをに渡し `Set-Acl` 、 **path** パラメーター (name と value) を省略すると、は `Set-Acl` セキュリティオブジェクトに含まれているパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-210">If you pass a security object to `Set-Acl` (either by using the **AclObject** or **SecurityDescriptor** parameters or by passing a security object from Get-Acl to `Set-Acl`), and you omit the **Path** parameter (name and value), `Set-Acl` uses the path that is included in the security object.</span></span>

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

### <span data-ttu-id="cfcfa-211">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cfcfa-211">-Confirm</span></span>

<span data-ttu-id="cfcfa-212">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-212">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="cfcfa-213">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cfcfa-213">-WhatIf</span></span>

<span data-ttu-id="cfcfa-214">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-214">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="cfcfa-215">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-215">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="cfcfa-216">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="cfcfa-216">CommonParameters</span></span>

<span data-ttu-id="cfcfa-217">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-217">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cfcfa-218">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-218">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cfcfa-219">入力</span><span class="sxs-lookup"><span data-stu-id="cfcfa-219">INPUTS</span></span>

### <span data-ttu-id="cfcfa-220">Accesscontrol-namespace、Accesscontrol-namespace、...... CommonSecurityDescriptor</span><span class="sxs-lookup"><span data-stu-id="cfcfa-220">System.Security.AccessControl.ObjectSecurity, System.Security.AccessControl.CommonSecurityDescriptor</span></span>

<span data-ttu-id="cfcfa-221">パイプを使用して、ACL オブジェクトまたはセキュリティ記述子をにパイプすることができ `Set-Acl` ます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-221">You can pipe an ACL object or a security descriptor to `Set-Acl`.</span></span>

## <span data-ttu-id="cfcfa-222">出力</span><span class="sxs-lookup"><span data-stu-id="cfcfa-222">OUTPUTS</span></span>

### <span data-ttu-id="cfcfa-223">Accesscontrol-namespace. System.security.accesscontrol.filesecurity</span><span class="sxs-lookup"><span data-stu-id="cfcfa-223">System.Security.AccessControl.FileSecurity</span></span>

<span data-ttu-id="cfcfa-224">既定で `Set-Acl` は、は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-224">By default, `Set-Acl` does not generate any output.</span></span>
<span data-ttu-id="cfcfa-225">ただし、 **Passthru** パラメーターを使用すると、セキュリティ オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-225">However, if you use the **Passthru** parameter, it generates a security object.</span></span>
<span data-ttu-id="cfcfa-226">セキュリティ オブジェクトの種類は、項目の種類に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-226">The type of the security object depends on the type of the item.</span></span>

## <span data-ttu-id="cfcfa-227">注</span><span class="sxs-lookup"><span data-stu-id="cfcfa-227">NOTES</span></span>

 <span data-ttu-id="cfcfa-228">`Set-Acl`コマンドレットは、PowerShell ファイルシステムとレジストリプロバイダーによってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-228">The `Set-Acl` cmdlet is supported by the PowerShell file system and registry providers.</span></span> <span data-ttu-id="cfcfa-229">そのため、そのコマンドレットを使用して、ファイル、ディレクトリ、およびレジストリ キーのセキュリティ記述子を変更できます。</span><span class="sxs-lookup"><span data-stu-id="cfcfa-229">As such, you can use it to change the security descriptors of files, directories, and registry keys.</span></span>

## <span data-ttu-id="cfcfa-230">関連リンク</span><span class="sxs-lookup"><span data-stu-id="cfcfa-230">RELATED LINKS</span></span>

[<span data-ttu-id="cfcfa-231">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="cfcfa-231">Get-Acl</span></span>](Get-Acl.md)

[<span data-ttu-id="cfcfa-232">FileSystemAccessRule</span><span class="sxs-lookup"><span data-stu-id="cfcfa-232">FileSystemAccessRule</span></span>](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor)

[<span data-ttu-id="cfcfa-233">ObjectSecurity. SetAccessRuleProtection</span><span class="sxs-lookup"><span data-stu-id="cfcfa-233">ObjectSecurity.SetAccessRuleProtection</span></span>](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection)

[<span data-ttu-id="cfcfa-234">FileSystemRights</span><span class="sxs-lookup"><span data-stu-id="cfcfa-234">FileSystemRights</span></span>](/dotnet/api/system.security.accesscontrol.filesystemrights)
