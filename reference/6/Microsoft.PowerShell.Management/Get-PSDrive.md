---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psdrive?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSDrive
ms.openlocfilehash: f5000ec88defda441d5f31f6ead5d8c37412857b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216323"
---
# <span data-ttu-id="48748-103">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="48748-103">Get-PSDrive</span></span>

## <span data-ttu-id="48748-104">概要</span><span class="sxs-lookup"><span data-stu-id="48748-104">SYNOPSIS</span></span>
<span data-ttu-id="48748-105">現在のセッションのドライブを取得します。</span><span class="sxs-lookup"><span data-stu-id="48748-105">Gets drives in the current session.</span></span>

## <span data-ttu-id="48748-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="48748-106">SYNTAX</span></span>

### <span data-ttu-id="48748-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="48748-107">Name (Default)</span></span>

```
Get-PSDrive [[-Name] <String[]>] [-Scope <String>] [-PSProvider <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="48748-108">LiteralName</span><span class="sxs-lookup"><span data-stu-id="48748-108">LiteralName</span></span>

```
Get-PSDrive [-LiteralName] <String[]> [-Scope <String>] [-PSProvider <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="48748-109">Description</span><span class="sxs-lookup"><span data-stu-id="48748-109">DESCRIPTION</span></span>

<span data-ttu-id="48748-110">`Get-PSDrive`コマンドレットは、現在のセッションのドライブを取得します。</span><span class="sxs-lookup"><span data-stu-id="48748-110">The `Get-PSDrive` cmdlet gets the drives in the current session.</span></span> <span data-ttu-id="48748-111">セッション内の特定のドライブを取得することも、すべてのドライブを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="48748-111">You can get a particular drive or all drives in the session.</span></span>

<span data-ttu-id="48748-112">このコマンドレットは、次の種類のドライブを取得します。</span><span class="sxs-lookup"><span data-stu-id="48748-112">This cmdlet gets the following types of drives:</span></span>

- <span data-ttu-id="48748-113">ネットワーク共有にマップされたドライブを含む、コンピューター上の Windows 論理ドライブ。</span><span class="sxs-lookup"><span data-stu-id="48748-113">Windows logical drives on the computer, including drives mapped to network shares.</span></span>
- <span data-ttu-id="48748-114">PowerShell プロバイダーによって公開されるドライブ (証明書:、関数:、エイリアス: ドライブなど)、Windows PowerShell レジストリプロバイダーによって公開される HKLM: および HKCU: ドライブ。</span><span class="sxs-lookup"><span data-stu-id="48748-114">Drives exposed by PowerShell providers (such as the Certificate:, Function:, and Alias: drives) and the HKLM: and HKCU: drives that are exposed by the Windows PowerShell Registry provider.</span></span>
- <span data-ttu-id="48748-115">New-PSDrive コマンドレットを使用して作成した、セッションで指定された一時ドライブと永続的にマップされたネットワークドライブ。</span><span class="sxs-lookup"><span data-stu-id="48748-115">Session-specified temporary drives and persistent mapped network drives that you create by using the New-PSDrive cmdlet.</span></span>

<span data-ttu-id="48748-116">Windows PowerShell 3.0 以降では、コマンドレットの **Persist** パラメーターを使用して、マップされ `New-PSDrive` たネットワークドライブを作成し、ローカルコンピューターに保存し、他のセッションで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="48748-116">Beginning in Windows PowerShell 3.0, the **Persist** parameter of the `New-PSDrive` cmdlet can create mapped network drives that are saved on the local computer and are available in other sessions.</span></span> <span data-ttu-id="48748-117">詳細については、「PSDrive」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48748-117">For more information, see New-PSDrive.</span></span>

<span data-ttu-id="48748-118">また、Windows PowerShell 3.0 以降では、外部ドライブがコンピューターに接続されている場合、Windows PowerShell は新しいドライブを表す PSDrive をファイル システムに自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="48748-118">Also, beginning in Windows PowerShell 3.0, when an external drive is connected to the computer, Windows PowerShell automatically adds a PSDrive to the file system that represents the new drive.</span></span>
<span data-ttu-id="48748-119">Windows PowerShell を再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="48748-119">You do not need to restart Windows PowerShell.</span></span> <span data-ttu-id="48748-120">同様に、外部ドライブがコンピューターから取り外された場合、Windows PowerShell は取り外されたドライブを表す PSDrive を自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="48748-120">Similarly, when an external drive is disconnected from the computer, Windows PowerShell automatically deletes the PSDrive that represents the removed drive.</span></span>

## <span data-ttu-id="48748-121">例</span><span class="sxs-lookup"><span data-stu-id="48748-121">EXAMPLES</span></span>

### <span data-ttu-id="48748-122">例 1: 現在のセッションのドライブを取得する</span><span class="sxs-lookup"><span data-stu-id="48748-122">Example 1: Get drives in the current session</span></span>

```
PS C:\> Get-PSDrive

Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
Alias                                  Alias
C                 202.06      23718.91 FileSystem    C:\
Cert                                   Certificate   \
D                1211.06     123642.32 FileSystem    D:\
Env                                    Environment
Function                               Function
HKCU                                   Registry      HKEY_CURRENT_USER
HKLM                                   Registry      HKEY_LOCAL_MACHINE
Variable                               Variable
```

<span data-ttu-id="48748-123">このコマンドは、現在のセッションにあるドライブを取得します。</span><span class="sxs-lookup"><span data-stu-id="48748-123">This command gets the drives in the current session.</span></span>

<span data-ttu-id="48748-124">出力には、ハードドライブ (C:)、CD-ROM ドライブ (D:)、Windows PowerShell プロバイダーによって公開されているドライブ (Alias:、Cert:、Env:、Function:、HKCU:、HKLM:、Variable:) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48748-124">The output shows the hard drive (C:), CD-ROM drive (D:), and the drives exposed by the Windows PowerShell providers (Alias:, Cert:, Env:, Function:, HKCU:, HKLM:, and Variable:).</span></span>

### <span data-ttu-id="48748-125">例 2: コンピューターのドライブを取得する</span><span class="sxs-lookup"><span data-stu-id="48748-125">Example 2: Get a drive on the computer</span></span>

```
PS C:\foo> Get-PSDrive D

Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
D                1211.06     123642.32 FileSystem    D:\
```

<span data-ttu-id="48748-126">このコマンドは、コンピューターの D: ドライブを取得します。</span><span class="sxs-lookup"><span data-stu-id="48748-126">This command gets the D: drive on the computer.</span></span> <span data-ttu-id="48748-127">コマンドではドライブ文字の後にコロンを指定していないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="48748-127">Note that the drive letter in the command is not followed by a colon.</span></span>

### <span data-ttu-id="48748-128">例 3: Windows PowerShell ファイルシステムプロバイダーでサポートされているすべてのドライブを取得する</span><span class="sxs-lookup"><span data-stu-id="48748-128">Example 3: Get all the drives that are supported by the Windows PowerShell file system provider</span></span>

```
PS C:\> Get-PSDrive -PSProvider FileSystem
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                                    A:\
C                 202.06      23718.91 FileSystem    C:\
D                1211.06     123642.32 FileSystem    D:\
G                 202.06        710.91 FileSystem    \\Music\GratefulDead
```

<span data-ttu-id="48748-129">このコマンドは、Windows PowerShell FileSystem プロバイダーによってサポートされているすべてのドライブを取得します。</span><span class="sxs-lookup"><span data-stu-id="48748-129">This command gets all of the drives that are supported by the Windows PowerShell FileSystem provider.</span></span> <span data-ttu-id="48748-130">これには、固定ドライブ、論理パーティション、マップされたネットワークドライブ、および New-PSDrive コマンドレットを使用して作成した一時ドライブが含まれます。</span><span class="sxs-lookup"><span data-stu-id="48748-130">This includes fixed drives, logical partitions, mapped network drives, and temporary drives that you create by using the New-PSDrive cmdlet.</span></span>

### <span data-ttu-id="48748-131">例 4: ドライブが Windows PowerShell ドライブ名として使用されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="48748-131">Example 4: Check to see if a drive is in use as a Windows PowerShell drive name</span></span>

```powershell
if (Get-PSDrive X -ErrorAction SilentlyContinue) {
    Write-Host 'The X: drive is already in use.'
} else {
    New-PSDrive -Name X -PSProvider Registry -Root HKLM:\SOFTWARE
}
```

<span data-ttu-id="48748-132">このコマンドは、X ドライブが Windows PowerShell ドライブ名として既に使用されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="48748-132">This command checks to see whether the X drive is already in use as a Windows PowerShell drive name.</span></span>
<span data-ttu-id="48748-133">そうでない場合は、コマンドレットを使用して、 `New-PSDrive` HKLM:\ SOFTWARE レジストリキーにマップされている一時ドライブを作成します。</span><span class="sxs-lookup"><span data-stu-id="48748-133">If it is not, the command uses the `New-PSDrive` cmdlet to create a temporary drive that is mapped to the HKLM:\SOFTWARE registry key.</span></span>

### <span data-ttu-id="48748-134">例 5: ファイルシステムドライブの種類を比較する</span><span class="sxs-lookup"><span data-stu-id="48748-134">Example 5: Compare the types of files system drives</span></span>

```
PS C:\> Get-PSDrive -PSProvider FileSystem
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                                    A:\
C                 202.06      23718.91 FileSystem    C:\
D                1211.06     123642.32 FileSystem    D:\
G                 202.06        710.91 FileSystem    \\Music\GratefulDead
X                                      Registry      HKLM:\Network

PS C:\> net use
New connections will be remembered.
Status       Local     Remote                    Network
-------------------------------------------------------------------------------
OK           G:        \\Server01\Public         Microsoft Windows Network

PS C:\> [System.IO.DriveInfo]::GetDrives() | Format-Table
Name DriveType DriveFormat IsReady AvailableFreeSpace TotalFreeSpace TotalSize     RootDirectory VolumeLabel
---- --------- ----------- ------- ------------------ -------------- ---------     ------------- -----------
A:\    Network               False                                                 A:\
C:\      Fixed NTFS          True  771920580608       771920580608   988877418496  C:\           Windows
D:\      Fixed NTFS          True  689684144128       689684144128   1990045179904 D:\           Big Drive
E:\      CDRom               False                                                 E:\
G:\    Network NTFS          True      69120000           69120000       104853504 G:\           GratefulDead

PS N:\> Get-CimInstance -Class Win32_LogicalDisk

DeviceID DriveType ProviderName   VolumeName         Size          FreeSpace
-------- --------- ------------   ----------         ----          ---------
A:       4
C:       3                        Windows            988877418496  771926069248
D:       3                        Big!              1990045179904  689684144128
E:       5
G:       4         \\Music\GratefulDead              988877418496  771926069248


PS C:\> Get-CimInstance -Class Win32_NetworkConnection
LocalName RemoteName            ConnectionState Status
--------- ----------            --------------- ------
G:        \\Music\GratefulDead  Connected       OK
```

<span data-ttu-id="48748-135">この例では、に表示されているファイルシステムドライブの種類 `Get-PSDrive` を、他の方法で表示されているものと比較します。</span><span class="sxs-lookup"><span data-stu-id="48748-135">This example compares the types of file system drives that are displayed by `Get-PSDrive` to those displayed by using other methods.</span></span> <span data-ttu-id="48748-136">この例は、Windows PowerShell でドライブを表示するさまざまな方法を示しています。また、New-PSDrive コマンドレットを使用して作成されたセッション固有のドライブには、Windows PowerShell でのみアクセスできることが示されています。</span><span class="sxs-lookup"><span data-stu-id="48748-136">This example demonstrates different ways to display drives in Windows PowerShell, and it shows that session-specific drives created by using the New-PSDrive cmdlet are accessible only in Windows PowerShell.</span></span>

<span data-ttu-id="48748-137">最初のコマンドは、を使用して、 `Get-PSDrive` セッション内のすべてのファイルシステムドライブを取得します。</span><span class="sxs-lookup"><span data-stu-id="48748-137">The first command uses `Get-PSDrive` to get all of the file system drives in the session.</span></span> <span data-ttu-id="48748-138">これには、固定ドライブ (C: および D:)、マップされたネットワークドライブ (G:) が含まれます。の **Persist** パラメーターを使用して作成された、 `New-PSDrive` PowerShell ドライブ (T:) `New-PSDrive` **Persist** パラメーターを指定せずにを使用して作成された。</span><span class="sxs-lookup"><span data-stu-id="48748-138">This includes the fixed drives (C: and D:), a mapped network drive (G:) that was created by using the **Persist** parameter of `New-PSDrive`, and a PowerShell drive (T:) that was created by using `New-PSDrive` without the **Persist** parameter.</span></span>

<span data-ttu-id="48748-139">**Net use** コマンドは、Windows のマップされたネットワークドライブを表示します。この場合は、G ドライブのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48748-139">The **net use** command displays Windows mapped network drives, in this case it displays only the G drive.</span></span> <span data-ttu-id="48748-140">によって作成された X: ドライブは表示されません `New-PSDrive` 。</span><span class="sxs-lookup"><span data-stu-id="48748-140">It does not display the X: drive that was created by `New-PSDrive`.</span></span> <span data-ttu-id="48748-141">これは、G: ドライブが Music GratefulDead にもマップされていることを示して \\ \\ \\ います。</span><span class="sxs-lookup"><span data-stu-id="48748-141">It shows that the G: drive is also mapped to \\\\Music\\GratefulDead.</span></span>

<span data-ttu-id="48748-142">3 番目のコマンドは、Microsoft .NET Framework **System.IO.DriveInfo** クラスの **GetDrives** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="48748-142">The third command uses the **GetDrives** method of the Microsoft .NET Framework **System.IO.DriveInfo** class.</span></span> <span data-ttu-id="48748-143">このコマンドは、ドライブ G: を含む Windows ファイルシステムドライブを取得しますが、によって作成されたドライブは取得しません `New-PSDrive` 。</span><span class="sxs-lookup"><span data-stu-id="48748-143">This command gets the Windows file system drives, including drive G:, but it does not get the drives created by `New-PSDrive`.</span></span>

<span data-ttu-id="48748-144">4 番目のコマンドは、`Get-CimInstance` コマンドレットを使用して、 **Win32_LogicalDisk** クラスのインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="48748-144">The fourth command uses the `Get-CimInstance` cmdlet to get the instances of the **Win32_LogicalDisk** class.</span></span> <span data-ttu-id="48748-145">A:、C:、D:、E:、および G: ドライブを返しますが、によって作成されたドライブは返しません `New-PSDrive` 。</span><span class="sxs-lookup"><span data-stu-id="48748-145">It returns the A:, C:, D:, E:, and G: drives, but not the drives created by `New-PSDrive`.</span></span>

<span data-ttu-id="48748-146">最後のコマンドは、`Get-CimInstance` コマンドレットを使用して、 **Win32_NetworkConnection** クラスのインスタンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="48748-146">The last command uses the `Get-CimInstance` cmdlet to display the instances of the **Win32_NetworkConnection** class.</span></span> <span data-ttu-id="48748-147">**Net use** と同様に、は、によって作成された永続的な G: ドライブのみを返し `New-PSDrive` ます。</span><span class="sxs-lookup"><span data-stu-id="48748-147">Like **net use** , it returns only the persistent G: drive created by `New-PSDrive`.</span></span>

## <span data-ttu-id="48748-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="48748-148">PARAMETERS</span></span>

### <span data-ttu-id="48748-149">-LiteralName</span><span class="sxs-lookup"><span data-stu-id="48748-149">-LiteralName</span></span>

<span data-ttu-id="48748-150">ドライブの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="48748-150">Specifies the name of the drive.</span></span>

<span data-ttu-id="48748-151">**LiteralName** の値は、入力した内容のまま使用されます。</span><span class="sxs-lookup"><span data-stu-id="48748-151">The value of **LiteralName** is used exactly as it is typed.</span></span> <span data-ttu-id="48748-152">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="48748-152">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="48748-153">名前にエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="48748-153">If the name includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="48748-154">単一引用符で囲んだ文字はエスケープ シーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="48748-154">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="48748-155">-Name</span><span class="sxs-lookup"><span data-stu-id="48748-155">-Name</span></span>

<span data-ttu-id="48748-156">文字列配列として、このコマンドレットが操作で取得するドライブの名前または名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="48748-156">Specifies, as a string array, the name or name of drives that this cmdlet gets in the operation.</span></span>
<span data-ttu-id="48748-157">ドライブ名または文字をコロン (:) なしで入力します。</span><span class="sxs-lookup"><span data-stu-id="48748-157">Type the drive name or letter without a colon (:).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="48748-158">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="48748-158">-PSProvider</span></span>

<span data-ttu-id="48748-159">Windows PowerShell プロバイダーを文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="48748-159">Specifies, as a string array, the Windows PowerShell provider.</span></span> <span data-ttu-id="48748-160">このコマンドレットは、このプロバイダーによってサポートされるドライブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="48748-160">This cmdlet gets only the drives supported by this provider.</span></span> <span data-ttu-id="48748-161">FileSystem、Registry、Certificate など、プロバイダーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="48748-161">Type the name of a provider, such as FileSystem, Registry, or Certificate.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="48748-162">-スコープ</span><span class="sxs-lookup"><span data-stu-id="48748-162">-Scope</span></span>

<span data-ttu-id="48748-163">このコマンドレットがドライブを取得するスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="48748-163">Specifies the scope in which this cmdlet gets the drives.</span></span>

<span data-ttu-id="48748-164">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="48748-164">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="48748-165">グローバル</span><span class="sxs-lookup"><span data-stu-id="48748-165">Global</span></span>
- <span data-ttu-id="48748-166">ローカル</span><span class="sxs-lookup"><span data-stu-id="48748-166">Local</span></span>
- <span data-ttu-id="48748-167">スクリプト</span><span class="sxs-lookup"><span data-stu-id="48748-167">Script</span></span>
- <span data-ttu-id="48748-168">現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1はその親)。</span><span class="sxs-lookup"><span data-stu-id="48748-168">a number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span> <span data-ttu-id="48748-169">既定値は "Local" です。</span><span class="sxs-lookup"><span data-stu-id="48748-169">"Local" is the default.</span></span>

<span data-ttu-id="48748-170">詳細については、「 [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48748-170">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="48748-171">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="48748-171">CommonParameters</span></span>

<span data-ttu-id="48748-172">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="48748-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="48748-173">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48748-173">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="48748-174">入力</span><span class="sxs-lookup"><span data-stu-id="48748-174">INPUTS</span></span>

### <span data-ttu-id="48748-175">なし</span><span class="sxs-lookup"><span data-stu-id="48748-175">None</span></span>

<span data-ttu-id="48748-176">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="48748-176">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="48748-177">出力</span><span class="sxs-lookup"><span data-stu-id="48748-177">OUTPUTS</span></span>

### <span data-ttu-id="48748-178">System.Management.Automation.PSDriveInfo</span><span class="sxs-lookup"><span data-stu-id="48748-178">System.Management.Automation.PSDriveInfo</span></span>

<span data-ttu-id="48748-179">このコマンドレットは、セッション内のドライブを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="48748-179">This cmdlet returns objects that represent the drives in the session.</span></span>

## <span data-ttu-id="48748-180">注</span><span class="sxs-lookup"><span data-stu-id="48748-180">NOTES</span></span>

* <span data-ttu-id="48748-181">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="48748-181">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="48748-182">セッションで使用可能なプロバイダーの一覧を表示するには、`Get-PSProvider` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="48748-182">To list the providers available in your session, use the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="48748-183">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48748-183">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
* <span data-ttu-id="48748-184">New-PSDrive コマンドレットの **Persist** パラメーターを使用して作成されたマップされたネットワークドライブは、ユーザーアカウントに固有です。</span><span class="sxs-lookup"><span data-stu-id="48748-184">Mapped network drives that are created by using the **Persist** parameter of the New-PSDrive cmdlet are specific to a user account.</span></span> <span data-ttu-id="48748-185">[管理者として実行] オプションまたは別のユーザーの資格情報で開始されたセッションで作成したマップ済みネットワークドライブは、明示的な資格情報または現在のユーザーの資格情報を使用せずに開始されたセッションには表示されません。</span><span class="sxs-lookup"><span data-stu-id="48748-185">Mapped network drives that you create in sessions that are started with the Run as administrator option or with the credentials of another user are not visible in sessions that are started without explicit credentials or with the credentials of the current user.</span></span>

## <span data-ttu-id="48748-186">関連リンク</span><span class="sxs-lookup"><span data-stu-id="48748-186">RELATED LINKS</span></span>

[<span data-ttu-id="48748-187">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="48748-187">New-PSDrive</span></span>](New-PSDrive.md)

[<span data-ttu-id="48748-188">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="48748-188">Remove-PSDrive</span></span>](Remove-PSDrive.md)

[<span data-ttu-id="48748-189">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="48748-189">Get-PSProvider</span></span>](Get-PSProvider.md)
