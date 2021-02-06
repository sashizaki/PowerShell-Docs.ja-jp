---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-hotfix?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HotFix
ms.openlocfilehash: 5b5b5939d4dcae8a99b1030b533fe6a85bcc601a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601388"
---
# <span data-ttu-id="02a14-102">Get-HotFix</span><span class="sxs-lookup"><span data-stu-id="02a14-102">Get-HotFix</span></span>

## <span data-ttu-id="02a14-103">概要</span><span class="sxs-lookup"><span data-stu-id="02a14-103">SYNOPSIS</span></span>
<span data-ttu-id="02a14-104">ローカルコンピューターまたはリモートコンピューターにインストールされている修正プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="02a14-104">Gets the hotfixes that are installed on local or remote computers.</span></span>

## <span data-ttu-id="02a14-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="02a14-105">SYNTAX</span></span>

### <span data-ttu-id="02a14-106">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="02a14-106">Default (Default)</span></span>

```
Get-HotFix [[-Id] <String[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
[<CommonParameters>]
```

### <span data-ttu-id="02a14-107">説明</span><span class="sxs-lookup"><span data-stu-id="02a14-107">Description</span></span>

```
Get-HotFix [-Description <String[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
[<CommonParameters>]
```

## <span data-ttu-id="02a14-108">Description</span><span class="sxs-lookup"><span data-stu-id="02a14-108">DESCRIPTION</span></span>

<span data-ttu-id="02a14-109">`Get-Hotfix`コマンドレットは、ローカルコンピューターまたは指定されたリモートコンピューターにインストールされている修正プログラム (更新プログラム) を取得します。</span><span class="sxs-lookup"><span data-stu-id="02a14-109">The `Get-Hotfix` cmdlet gets hotfixes, or updates, that are installed on the local computer or specified remote computers.</span></span> <span data-ttu-id="02a14-110">更新プログラムは、Windows Update、Microsoft Update、Windows Server Update Services、または手動でインストールすることによってインストールできます。</span><span class="sxs-lookup"><span data-stu-id="02a14-110">The updates can be installed by Windows Update, Microsoft Update, Windows Server Update Services, or manually installed.</span></span>

## <span data-ttu-id="02a14-111">例</span><span class="sxs-lookup"><span data-stu-id="02a14-111">EXAMPLES</span></span>

### <span data-ttu-id="02a14-112">例 1: ローカルコンピューター上のすべての修正プログラムを取得する</span><span class="sxs-lookup"><span data-stu-id="02a14-112">Example 1: Get all hotfixes on the local computer</span></span>

<span data-ttu-id="02a14-113">`Get-Hotfix`コマンドレットは、ローカルコンピューターにインストールされているすべての修正プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="02a14-113">The `Get-Hotfix` cmdlet gets all hotfixes installed on the local computer.</span></span>

```powershell
Get-HotFix
```

```output
Source         Description      HotFixID      InstalledBy          InstalledOn
------         -----------      --------      -----------          -----------
Server01       Update           KB4495590     NT AUTHORITY\SYSTEM  5/16/2019 00:00:00
Server01       Security Update  KB4470788     NT AUTHORITY\SYSTEM  1/22/2019 00:00:00
Server01       Update           KB4480056     NT AUTHORITY\SYSTEM  1/24/2019 00:00:00
```

### <span data-ttu-id="02a14-114">例 2: 文字列によってフィルター処理された複数のコンピューターから修正プログラムを取得する</span><span class="sxs-lookup"><span data-stu-id="02a14-114">Example 2: Get hotfixes from multiple computers filtered by a string</span></span>

<span data-ttu-id="02a14-115">この `Get-Hotfix` コマンドは、パラメーターを使用して、リモートコンピューターにインストールされている修正プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="02a14-115">The `Get-Hotfix` command uses parameters to get hotfixes installed on remote computers.</span></span> <span data-ttu-id="02a14-116">結果は、指定された説明文字列によってフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="02a14-116">The results are filtered by a specified description string.</span></span>

```
PS> Get-HotFix -Description Security* -ComputerName Server01, Server02 -Credential Domain01\admin01
```

<span data-ttu-id="02a14-117">`Get-Hotfix`**Description** パラメーターと、アスタリスク () ワイルドカードを含む文字列 **セキュリティ** を使用して、出力をフィルター処理し `*` ます。</span><span class="sxs-lookup"><span data-stu-id="02a14-117">`Get-Hotfix` filters the output with the **Description** parameter and the string **Security** that includes the asterisk (`*`) wildcard.</span></span> <span data-ttu-id="02a14-118">**ComputerName** パラメーターには、リモートコンピューター名をコンマで区切った文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="02a14-118">The **ComputerName** parameter includes a comma-separated string of remote computer names.</span></span> <span data-ttu-id="02a14-119">**Credential** パラメーターは、リモートコンピューターにアクセスしてコマンドを実行するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="02a14-119">The **Credential** parameter specifies a user account that has permission to access the remote computers and run commands.</span></span>

### <span data-ttu-id="02a14-120">例 3: 更新プログラムがインストールされているかどうかを確認し、コンピューター名をファイルに書き込む</span><span class="sxs-lookup"><span data-stu-id="02a14-120">Example 3: Verify if an update is installed and write computer names to a file</span></span>

<span data-ttu-id="02a14-121">この例のコマンドは、特定の更新プログラムがインストールされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="02a14-121">The commands in this example verify whether a particular update installed.</span></span> <span data-ttu-id="02a14-122">更新プログラムがインストールされていない場合、コンピューター名はテキストファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="02a14-122">If the update isn't installed, the computer name is written to a text file.</span></span>

```
PS> $A = Get-Content -Path ./Servers.txt
PS> $A | ForEach-Object { if (!(Get-HotFix -Id KB957095 -ComputerName $_))
         { Add-Content $_ -Path ./Missing-KB957095.txt }}
```

<span data-ttu-id="02a14-123">変数には、 `$A` によってテキストファイルから取得されたコンピューター名が含まれてい `Get-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="02a14-123">The `$A` variable contains computer names that were obtained by `Get-Content` from a text file.</span></span> <span data-ttu-id="02a14-124">内のオブジェクト `$A` は、パイプラインからに送信され `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="02a14-124">The objects in `$A` are sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="02a14-125">ステートメントでは、コマンドレットを使用して、 `if` `Get-Hotfix` **id** パラメーターと、コンピューター名ごとに特定の id 番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="02a14-125">An `if` statement uses the `Get-Hotfix` cmdlet with the **Id** parameter and a specific Id number for each computer name.</span></span> <span data-ttu-id="02a14-126">コンピューターに指定された修正プログラム Id がインストールされていない場合、 `Add-Content` コマンドレットはコンピューター名をファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="02a14-126">If a computer doesn't have the specified hotfix Id installed, the `Add-Content` cmdlet writes the computer name to a file.</span></span>

### <span data-ttu-id="02a14-127">例 4: ローカルコンピューターで最新の修正プログラムを取得する</span><span class="sxs-lookup"><span data-stu-id="02a14-127">Example 4: Get the most recent hotfix on the local computer</span></span>

<span data-ttu-id="02a14-128">この例では、コンピューターにインストールされている最新の修正プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="02a14-128">This example gets the most recent hotfix installed on a computer.</span></span>

```powershell
(Get-HotFix | Sort-Object -Property InstalledOn)[-1]
```

<span data-ttu-id="02a14-129">`Get-Hotfix` オブジェクトをパイプラインからコマンドレットに送信し `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="02a14-129">`Get-Hotfix` sends the objects down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="02a14-130">`Sort-Object` オブジェクトを昇順で並べ替え、 **プロパティ** パラメーターを使用して、各更新された日付 **を** 評価します。</span><span class="sxs-lookup"><span data-stu-id="02a14-130">`Sort-Object` sorts objects by ascending order and uses the **Property** parameter to evaluate each **InstalledOn** date.</span></span> <span data-ttu-id="02a14-131">配列表記は、 `[-1]` 最新のインストールされている修正プログラムを選択します。</span><span class="sxs-lookup"><span data-stu-id="02a14-131">The array notation `[-1]` selects the most recent installed hotfix.</span></span>

## <span data-ttu-id="02a14-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="02a14-132">PARAMETERS</span></span>

### <span data-ttu-id="02a14-133">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="02a14-133">-ComputerName</span></span>

<span data-ttu-id="02a14-134">リモート コンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="02a14-134">Specifies a remote computer.</span></span> <span data-ttu-id="02a14-135">リモートコンピューターの NetBIOS 名、インターネットプロトコル (IP) アドレス、または完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="02a14-135">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name (FQDN) of a remote computer.</span></span>

<span data-ttu-id="02a14-136">**ComputerName** パラメーターが指定されていない場合、は `Get-Hotfix` ローカルコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="02a14-136">When the **ComputerName** parameter isn't specified, `Get-Hotfix` runs on the local computer.</span></span>

<span data-ttu-id="02a14-137">**ComputerName** パラメーターは、Windows PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="02a14-137">The **ComputerName** parameter doesn't rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="02a14-138">コンピューターがリモートコマンドを実行するように構成されていない場合は、 **ComputerName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="02a14-138">If your computer isn't configured to run remote commands, use the **ComputerName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __Server, IPAddress

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="02a14-139">-Credential</span><span class="sxs-lookup"><span data-stu-id="02a14-139">-Credential</span></span>

<span data-ttu-id="02a14-140">コンピューターにアクセスしてコマンドを実行するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="02a14-140">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="02a14-141">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="02a14-141">The default is the current user</span></span>

<span data-ttu-id="02a14-142">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="02a14-142">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="02a14-143">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="02a14-143">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="02a14-144">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="02a14-144">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="02a14-145">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02a14-145">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="02a14-146">-Description</span><span class="sxs-lookup"><span data-stu-id="02a14-146">-Description</span></span>

<span data-ttu-id="02a14-147">`Get-HotFix`**Description** パラメーターを使用して、修正プログラムの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="02a14-147">`Get-HotFix` uses the **Description** parameter to specify hotfix types.</span></span> <span data-ttu-id="02a14-148">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="02a14-148">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Description
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="02a14-149">-Id</span><span class="sxs-lookup"><span data-stu-id="02a14-149">-Id</span></span>

<span data-ttu-id="02a14-150">`Get-HotFix`特定の修正プログラム id の結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="02a14-150">Filters the `Get-HotFix` results for specific hotfix Ids.</span></span> <span data-ttu-id="02a14-151">ワイルドカードは受け入れられません。</span><span class="sxs-lookup"><span data-stu-id="02a14-151">Wildcards aren't accepted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: HFID

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="02a14-152">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="02a14-152">CommonParameters</span></span>

<span data-ttu-id="02a14-153">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="02a14-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="02a14-154">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02a14-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="02a14-155">入力</span><span class="sxs-lookup"><span data-stu-id="02a14-155">INPUTS</span></span>

### <span data-ttu-id="02a14-156">String</span><span class="sxs-lookup"><span data-stu-id="02a14-156">String</span></span>

<span data-ttu-id="02a14-157">パイプを使用して1つまたは複数のコンピューター名を修正することができます。</span><span class="sxs-lookup"><span data-stu-id="02a14-157">You can pipe one or more computer names to Get-HotFix.</span></span>

## <span data-ttu-id="02a14-158">出力</span><span class="sxs-lookup"><span data-stu-id="02a14-158">OUTPUTS</span></span>

### <span data-ttu-id="02a14-159">System.management.managementobject # root\CIMV2\ Win32_QuickFixEngineering</span><span class="sxs-lookup"><span data-stu-id="02a14-159">System.Management.ManagementObject#root\CIMV2\Win32_QuickFixEngineering</span></span>

<span data-ttu-id="02a14-160">`Get-HotFix` コンピューター上の修正プログラムを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="02a14-160">`Get-HotFix` returns objects that represent the hotfixes on the computer.</span></span>

## <span data-ttu-id="02a14-161">注</span><span class="sxs-lookup"><span data-stu-id="02a14-161">NOTES</span></span>

<span data-ttu-id="02a14-162">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="02a14-162">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="02a14-163">**Win32_QuickFixEngineering** [WMI クラス](/windows/desktop/WmiSdk/retrieving-a-class)は、現在のオペレーティングシステムに適用される、通常はクイック修正エンジニアリング (QFE) の更新と呼ばれる、システム全体の小さな更新プログラムを表します。</span><span class="sxs-lookup"><span data-stu-id="02a14-163">The **Win32_QuickFixEngineering** [WMI class](/windows/desktop/WmiSdk/retrieving-a-class) represents a small system-wide update, commonly referred to as a quick-fix engineering (QFE) update, applied to the current operating system.</span></span> <span data-ttu-id="02a14-164">このクラスは、コンポーネントベースのサービス (CBS) によって提供される更新プログラムのみを返します。</span><span class="sxs-lookup"><span data-stu-id="02a14-164">This class returns only the updates supplied by Component Based Servicing (CBS).</span></span> <span data-ttu-id="02a14-165">これらの更新プログラムは、レジストリには記載されていません。</span><span class="sxs-lookup"><span data-stu-id="02a14-165">These updates are not listed in the registry.</span></span> <span data-ttu-id="02a14-166">Microsoft Windows インストーラー (MSI) または [Windows Update](https://update.microsoft.com) サイトによって提供される更新プログラムは **Win32_QuickFixEngineering** によって返されません。</span><span class="sxs-lookup"><span data-stu-id="02a14-166">Updates supplied by Microsoft Windows Installer (MSI) or the [Windows Update](https://update.microsoft.com) site are not returned by **Win32_QuickFixEngineering**.</span></span> <span data-ttu-id="02a14-167">詳細については、「 [Win32_QuickFixEngineering クラス](/windows/desktop/CIMWin32Prov/win32-quickfixengineering)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02a14-167">For more information, see [Win32_QuickFixEngineering class](/windows/desktop/CIMWin32Prov/win32-quickfixengineering).</span></span>

<span data-ttu-id="02a14-168">出力は、 `Get-HotFix` オペレーティングシステムによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="02a14-168">The `Get-HotFix` output might vary on different operating systems.</span></span>

## <span data-ttu-id="02a14-169">関連リンク</span><span class="sxs-lookup"><span data-stu-id="02a14-169">RELATED LINKS</span></span>

[<span data-ttu-id="02a14-170">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="02a14-170">about_Arrays</span></span>](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[<span data-ttu-id="02a14-171">Add-Content</span><span class="sxs-lookup"><span data-stu-id="02a14-171">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="02a14-172">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="02a14-172">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="02a14-173">Win32_QuickFixEngineering クラス</span><span class="sxs-lookup"><span data-stu-id="02a14-173">Win32_QuickFixEngineering class</span></span>](/windows/desktop/CIMWin32Prov/win32-quickfixengineering)
