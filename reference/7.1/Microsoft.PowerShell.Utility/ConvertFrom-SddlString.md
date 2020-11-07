---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-sddlstring?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SddlString
ms.openlocfilehash: 7ec2c3025f62a64cd24298c0749d40fa5eff4904
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346090"
---
# <span data-ttu-id="6da02-103">ConvertFrom-SddlString</span><span class="sxs-lookup"><span data-stu-id="6da02-103">ConvertFrom-SddlString</span></span>

## <span data-ttu-id="6da02-104">概要</span><span class="sxs-lookup"><span data-stu-id="6da02-104">SYNOPSIS</span></span>
<span data-ttu-id="6da02-105">SDDL 文字列をカスタムオブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="6da02-105">Converts a SDDL string to a custom object.</span></span>

## <span data-ttu-id="6da02-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6da02-106">SYNTAX</span></span>

### <span data-ttu-id="6da02-107">すべて</span><span class="sxs-lookup"><span data-stu-id="6da02-107">All</span></span>

```
ConvertFrom-SddlString [-Sddl] <String> [-Type <AccessRightTypeNames>] [<CommonParameters>]
```

## <span data-ttu-id="6da02-108">Description</span><span class="sxs-lookup"><span data-stu-id="6da02-108">DESCRIPTION</span></span>

<span data-ttu-id="6da02-109">`ConvertFrom-SddlString`コマンドレットは、セキュリティ記述子定義言語の文字列を、Owner、Group、DiscretionaryAcl、SystemAcl、RawDescriptor の各プロパティを持つカスタム **Pscustomobject** オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="6da02-109">The `ConvertFrom-SddlString` cmdlet converts a Security Descriptor Definition Language string to a custom **PSCustomObject** object with the following properties: Owner, Group, DiscretionaryAcl, SystemAcl and RawDescriptor.</span></span>

<span data-ttu-id="6da02-110">Owner、Group、DiscretionaryAcl、および SystemAcl の各プロパティには、SDDL 文字列で指定されたアクセス権の読み取り可能なテキスト表現が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6da02-110">Owner, Group, DiscretionaryAcl and SystemAcl properties contain a readable text representation of the access rights specified in a SDDL string.</span></span>

<span data-ttu-id="6da02-111">このコマンドレットは、PowerShell 5.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6da02-111">This cmdlet was introduced in PowerShell 5.0.</span></span>

## <span data-ttu-id="6da02-112">例</span><span class="sxs-lookup"><span data-stu-id="6da02-112">EXAMPLES</span></span>

### <span data-ttu-id="6da02-113">例 1: ファイルシステムアクセス権 SDDL を PSCustomObject 変換する</span><span class="sxs-lookup"><span data-stu-id="6da02-113">Example 1: Convert file system access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl -Path C:\Windows
ConvertFrom-SddlString -Sddl $acl.Sddl
```

<span data-ttu-id="6da02-114">最初のコマンドは、 `Get-Acl` コマンドレットを使用して C:\Windows フォルダーのセキュリティ記述子を取得し、変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="6da02-114">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the C:\Windows folder and saves it in the variable.</span></span>

<span data-ttu-id="6da02-115">2番目のコマンドは、コマンドレットを使用して、 `ConvertFrom-SddlString` sddl 文字列のテキスト表現を取得します。これは、セキュリティ記述子を表すオブジェクトの sddl プロパティに含まれています。</span><span class="sxs-lookup"><span data-stu-id="6da02-115">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

### <span data-ttu-id="6da02-116">例 2: レジストリアクセス権 SDDL を PSCustomObject 変換する</span><span class="sxs-lookup"><span data-stu-id="6da02-116">Example 2: Convert registry access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl HKLM:\SOFTWARE\Microsoft\
ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights
```

<span data-ttu-id="6da02-117">最初のコマンドは、コマンドレットを使用して、 `Get-Acl` HKLM:\ SOFTWARE\Microsoft\ key のセキュリティ記述子を取得し、変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="6da02-117">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="6da02-118">2番目のコマンドは、コマンドレットを使用して、 `ConvertFrom-SddlString` sddl 文字列のテキスト表現を取得します。これは、セキュリティ記述子を表すオブジェクトの sddl プロパティに含まれています。</span><span class="sxs-lookup"><span data-stu-id="6da02-118">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="6da02-119">この例では、パラメーターを使用して、 `-Type` SDDL 文字列がレジストリセキュリティ記述子を表すことを指定しています。</span><span class="sxs-lookup"><span data-stu-id="6da02-119">It uses the `-Type` parameter to specify that SDDL string represents a registry security descriptor.</span></span>

### <span data-ttu-id="6da02-120">例 3: パラメーターを指定せずに ConvertFrom-SddlString を使用して、レジストリアクセス権 SDDL を PSCustomObject 変換する `-Type`</span><span class="sxs-lookup"><span data-stu-id="6da02-120">Example 3: Convert registry access rights SDDL to a PSCustomObject by using ConvertFrom-SddlString with and without the `-Type` parameter</span></span>

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Microsoft\

ConvertFrom-SddlString -Sddl $acl.Sddl | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateDirectories, Delete, ExecuteKey, FullControl, GenericExecute, GenericWrite, ListDirectory, ReadExtendedAttributes, ReadPermissions, TakeOwnership, Traverse, WriteData, WriteExtendedAttributes, WriteKey)

ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateLink, CreateSubKey, Delete, EnumerateSubKeys, ExecuteKey, FullControl, GenericExecute, GenericWrite, Notify, QueryValues, ReadPermissions, SetValue, TakeOwnership, WriteKey)
```

<span data-ttu-id="6da02-121">最初のコマンドは、コマンドレットを使用して、 `Get-Acl` HKLM:\ SOFTWARE\Microsoft\ key のセキュリティ記述子を取得し、変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="6da02-121">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="6da02-122">2番目のコマンドは、コマンドレットを使用して、 `ConvertFrom-SddlString` sddl 文字列のテキスト表現を取得します。これは、セキュリティ記述子を表すオブジェクトの sddl プロパティに含まれています。</span><span class="sxs-lookup"><span data-stu-id="6da02-122">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="6da02-123">パラメーターを使用しない `-Type` ので、表示されるアクセス権はファイルシステム用です。</span><span class="sxs-lookup"><span data-stu-id="6da02-123">It doesn't use the `-Type` parameter, so the access rights shown are for file system.</span></span>

<span data-ttu-id="6da02-124">3番目のコマンドは、パラメーターを指定 `ConvertFrom-SddlString` してコマンドレットを使用する `-Type` ため、返されるアクセス権はレジストリ用です。</span><span class="sxs-lookup"><span data-stu-id="6da02-124">The third command uses the `ConvertFrom-SddlString` cmdlet with the `-Type` parameter, so the access rights returned are for registry.</span></span>

## <span data-ttu-id="6da02-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6da02-125">PARAMETERS</span></span>

### <span data-ttu-id="6da02-126">-Sddl</span><span class="sxs-lookup"><span data-stu-id="6da02-126">-Sddl</span></span>

<span data-ttu-id="6da02-127">SDDL 構文のセキュリティ記述子を表す文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="6da02-127">Specifies the string representing the security descriptor in SDDL syntax.</span></span>

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

### <span data-ttu-id="6da02-128">-Type</span><span class="sxs-lookup"><span data-stu-id="6da02-128">-Type</span></span>

<span data-ttu-id="6da02-129">SDDL 文字列が表す権限の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6da02-129">Specifies the type of rights that SDDL string represents.</span></span>

<span data-ttu-id="6da02-130">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6da02-130">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="6da02-131">FileSystemRights</span><span class="sxs-lookup"><span data-stu-id="6da02-131">FileSystemRights</span></span>
- <span data-ttu-id="6da02-132">RegistryRights</span><span class="sxs-lookup"><span data-stu-id="6da02-132">RegistryRights</span></span>
- <span data-ttu-id="6da02-133">ActiveDirectoryRights</span><span class="sxs-lookup"><span data-stu-id="6da02-133">ActiveDirectoryRights</span></span>
- <span data-ttu-id="6da02-134">MutexRights</span><span class="sxs-lookup"><span data-stu-id="6da02-134">MutexRights</span></span>
- <span data-ttu-id="6da02-135">SemaphoreRights</span><span class="sxs-lookup"><span data-stu-id="6da02-135">SemaphoreRights</span></span>
- <span data-ttu-id="6da02-136">CryptoKeyRights</span><span class="sxs-lookup"><span data-stu-id="6da02-136">CryptoKeyRights</span></span>
- <span data-ttu-id="6da02-137">EventWaitHandleRights</span><span class="sxs-lookup"><span data-stu-id="6da02-137">EventWaitHandleRights</span></span>

<span data-ttu-id="6da02-138">既定では、コマンドレットはファイルシステム権限を使用します。</span><span class="sxs-lookup"><span data-stu-id="6da02-138">By default cmdlet uses file system rights.</span></span>

<span data-ttu-id="6da02-139">CryptoKeyRights と ActiveDirectoryRights は、PowerShell Core ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6da02-139">CryptoKeyRights and ActiveDirectoryRights are not supported in PowerShell Core.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ConvertFromSddlStringCommand+AccessRightTypeNames
Parameter Sets: (All)
Aliases:
Accepted values: FileSystemRights, RegistryRights, ActiveDirectoryRights, MutexRights, SemaphoreRights, CryptoKeyRights, EventWaitHandleRights

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6da02-140">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6da02-140">CommonParameters</span></span>

<span data-ttu-id="6da02-141">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6da02-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6da02-142">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6da02-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6da02-143">入力</span><span class="sxs-lookup"><span data-stu-id="6da02-143">INPUTS</span></span>

### <span data-ttu-id="6da02-144">System.String</span><span class="sxs-lookup"><span data-stu-id="6da02-144">System.String</span></span>

<span data-ttu-id="6da02-145">SDDL 文字列をにパイプすることができ `ConvertFrom-SddlString` ます。</span><span class="sxs-lookup"><span data-stu-id="6da02-145">You can pipe a SDDL string to `ConvertFrom-SddlString`.</span></span>

## <span data-ttu-id="6da02-146">出力</span><span class="sxs-lookup"><span data-stu-id="6da02-146">OUTPUTS</span></span>

## <span data-ttu-id="6da02-147">注</span><span class="sxs-lookup"><span data-stu-id="6da02-147">NOTES</span></span>

<span data-ttu-id="6da02-148">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6da02-148">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="6da02-149">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6da02-149">RELATED LINKS</span></span>

[<span data-ttu-id="6da02-150">セキュリティ記述子定義言語</span><span class="sxs-lookup"><span data-stu-id="6da02-150">Security Descriptor Definition Language</span></span>](/windows/win32/secauthz/security-descriptor-definition-language)
