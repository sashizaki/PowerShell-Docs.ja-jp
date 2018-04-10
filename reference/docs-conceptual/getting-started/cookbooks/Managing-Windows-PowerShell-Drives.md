---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: Windows PowerShell ドライブの管理
ms.assetid: bd809e38-8de9-437a-a250-f30a667d11b4
ms.openlocfilehash: cfc5418e9d2efb1a786817e1b941d75e22291742
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="managing-windows-powershell-drives"></a><span data-ttu-id="5d871-103">Windows PowerShell ドライブの管理</span><span class="sxs-lookup"><span data-stu-id="5d871-103">Managing Windows PowerShell Drives</span></span>

<span data-ttu-id="5d871-104">*Windows PowerShell ドライブ*は、Windows PowerShell のファイル システム ドライブのようにアクセスできるデータ格納場所です。</span><span class="sxs-lookup"><span data-stu-id="5d871-104">A *Windows PowerShell drive* is a data store location that you can access like a file system drive in Windows PowerShell.</span></span> <span data-ttu-id="5d871-105">Windows PowerShell プロバイダーは、ファイル システムのドライブ (C: および D: を含む)、レジストリ ドライブ (HKCU: および HKLM:)、および証明書ドライブ (Cert:) など、いくつかのドライブを作成して、独自の Windows PowerShell ドライブを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5d871-105">The Windows PowerShell providers create some drives for you, such as the file system drives (including C: and D:), the registry drives (HKCU: and HKLM:), and the certificate drive (Cert:), and you can create your own Windows PowerShell drives.</span></span> <span data-ttu-id="5d871-106">これらのドライブは非常に便利ですが、Windows PowerShell 内でのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="5d871-106">These drives are very useful, but they are available only within Windows PowerShell.</span></span> <span data-ttu-id="5d871-107">ファイル エクスプローラーや Cmd.exe など、他の Windows ツールを使用してアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5d871-107">You cannot access them by using other Windows tools, such as File Explorer or Cmd.exe.</span></span>

<span data-ttu-id="5d871-108">Windows PowerShell ドライブに対して使用できるコマンドには、**PSDrive** という名詞が使用されています。</span><span class="sxs-lookup"><span data-stu-id="5d871-108">Windows PowerShell uses the noun, **PSDrive**, for commands that work with Windows PowerShell drives.</span></span> <span data-ttu-id="5d871-109">Windows PowerShell セッションに存在する Windows PowerShell ドライブを一覧表示するには、**Get-PSDrive** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d871-109">For a list of the Windows PowerShell drives in your Windows PowerShell session, use the **Get-PSDrive** cmdlet.</span></span>

```
PS> Get-PSDrive

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
A          FileSystem    A:\
Alias      Alias
C          FileSystem    C:\                                 ...And Settings\me
cert       Certificate   \
D          FileSystem    D:\
Env        Environment
Function   Function
HKCU       Registry      HKEY_CURRENT_USER
HKLM       Registry      HKEY_LOCAL_MACHINE
Variable   Variable
```

<span data-ttu-id="5d871-110">表示されるドライブはシステムのドライブに応じて異なりますが、一覧は上記の **Get-PSDrive** コマンドの出力のようになります。</span><span class="sxs-lookup"><span data-stu-id="5d871-110">Although the drives in the display vary with the drives on your system, the listing will look similar to the output of the **Get-PSDrive** command shown above.</span></span>

<span data-ttu-id="5d871-111">ファイル システムのドライブは、Windows PowerShell ドライブのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="5d871-111">File system drives are a subset of the Windows PowerShell drives.</span></span> <span data-ttu-id="5d871-112">[プロバイダー] 列の FileSystem のエントリによって、ファイル システムのドライブを識別できます。</span><span class="sxs-lookup"><span data-stu-id="5d871-112">You can identify the file system drives by the FileSystem entry in the Provider column.</span></span> <span data-ttu-id="5d871-113">(Windows PowerShell のファイル システムのドライブは、Windows PowerShell FileSystem プロバイダーによってサポートされます。)</span><span class="sxs-lookup"><span data-stu-id="5d871-113">(The file system drives in Windows PowerShell are supported by the Windows PowerShell FileSystem provider.)</span></span>

<span data-ttu-id="5d871-114">**Get-PSDrive** コマンドレットの構文を表示するには、**Get-Command** コマンドに **Syntax** パラメーターを指定して入力します。</span><span class="sxs-lookup"><span data-stu-id="5d871-114">To see the syntax of the **Get-PSDrive** cmdlet, type a **Get-Command** command with the **Syntax** parameter:</span></span>

```
PS> Get-Command -Name Get-PSDrive -Syntax

Get-PSDrive [[-Name] <String[]>] [-Scope <String>] [-PSProvider <String[]>] [-V
erbose] [-Debug] [-ErrorAction <ActionPreference>] [-ErrorVariable <String>] [-
OutVariable <String>] [-OutBuffer <Int32>]
```

<span data-ttu-id="5d871-115">**PSProvider** パラメーターでは、特定のプロバイダーによってサポートされている Windows PowerShell ドライブのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5d871-115">The **PSProvider** parameter lets you display only the Windows PowerShell drives that are supported by a particular provider.</span></span> <span data-ttu-id="5d871-116">たとえば、Windows PowerShell FileSystem プロバイダーによってサポートされる Windows PowerShell ドライブのみを表示するには、**Get-PSDrive** コマンドに **PSProvider** パラメーターと **FileSystem** の値を指定して入力します。</span><span class="sxs-lookup"><span data-stu-id="5d871-116">For example, to display only the Windows PowerShell drives that are supported by the Windows PowerShell FileSystem provider, type a **Get-PSDrive** command with the **PSProvider** parameter and the **FileSystem** value:</span></span>

```
PS> Get-PSDrive -PSProvider FileSystem

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
A          FileSystem    A:\
C          FileSystem    C:\                           ...nd Settings\PowerUser
D          FileSystem    D:\
```

<span data-ttu-id="5d871-117">レジストリ ハイブを表す Windows PowerShell ドライブを表示するには、**PSProvider** パラメーターを使用して、Windows PowerShell Registry プロバイダーによってサポートされる Windows PowerShell ドライブのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="5d871-117">To view the Windows PowerShell drives that represent registry hives, use the **PSProvider** parameter to display only the Windows PowerShell drives that are supported by the Windows PowerShell Registry provider:</span></span>

```
PS> Get-PSDrive -PSProvider Registry

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
HKCU       Registry      HKEY_CURRENT_USER
HKLM       Registry      HKEY_LOCAL_MACHINE
```

<span data-ttu-id="5d871-118">また、Windows PowerShell ドライブに標準的な Location コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d871-118">You can also use the standard Location cmdlets with the Windows PowerShell drives:</span></span>

```
PS> Set-Location HKLM:\SOFTWARE
PS> Push-Location .\Microsoft
PS> Get-Location

Path
----
HKLM:\SOFTWARE\Microsoft
```

### <a name="adding-new-windows-powershell-drives-new-psdrive"></a><span data-ttu-id="5d871-119">新しい Windows PowerShell ドライブの追加 (New-PSDrive)</span><span class="sxs-lookup"><span data-stu-id="5d871-119">Adding New Windows PowerShell Drives (New-PSDrive)</span></span>

<span data-ttu-id="5d871-120">**New-PSDrive** コマンドを使用して、独自の Windows PowerShell ドライブを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5d871-120">You can add your own Windows PowerShell drives by using the **New-PSDrive** command.</span></span> <span data-ttu-id="5d871-121">**New-PSDrive** コマンドの構文を取得するには、**Get-Command** コマンドに **Syntax** パラメーターを指定して入力します。</span><span class="sxs-lookup"><span data-stu-id="5d871-121">To get the syntax for the **New-PSDrive** command, enter the **Get-Command** command with the **Syntax** parameter:</span></span>

```
PS> Get-Command -Name New-PSDrive -Syntax

New-PSDrive [-Name] <String> [-PSProvider] <String> [-Root] <String> [-Descript
ion <String>] [-Scope <String>] [-Credential <PSCredential>] [-Verbose] [-Debug
] [-ErrorAction <ActionPreference>] [-ErrorVariable <String>] [-OutVariable <St
ring>] [-OutBuffer <Int32>] [-WhatIf] [-Confirm]
```

<span data-ttu-id="5d871-122">新しい Windows PowerShell ドライブを作成するには、3 つのパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d871-122">To create a new Windows PowerShell drive, you must supply three parameters:</span></span>

- <span data-ttu-id="5d871-123">ドライブの名前 (有効な Windows PowerShell の名前を使用できます)</span><span class="sxs-lookup"><span data-stu-id="5d871-123">A name for the drive (you can use any valid Windows PowerShell name)</span></span>

- <span data-ttu-id="5d871-124">PSProvider (ファイル システムの場所には "FileSystem" を、レジストリの場所には "Registry" を使用します)</span><span class="sxs-lookup"><span data-stu-id="5d871-124">The PSProvider (use "FileSystem" for file system locations and "Registry" for registry locations)</span></span>

- <span data-ttu-id="5d871-125">ルート、つまり、新しいドライブのルートのパス</span><span class="sxs-lookup"><span data-stu-id="5d871-125">The root, that is, the path to the root of the new drive</span></span>

<span data-ttu-id="5d871-126">たとえば、**C:\\Program Files\\Microsoft Office\\OFFICE11** のように、コンピューターの Microsoft Office アプリケーションを含むフォルダーにマップされる、"Office" という名前のドライブを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5d871-126">For example, you can create a drive named "Office" that is mapped to the folder that contains the Microsoft Office applications on your computer, such as **C:\\Program Files\\Microsoft Office\\OFFICE11**.</span></span> <span data-ttu-id="5d871-127">ドライブを作成するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="5d871-127">To create the drive, type the following command:</span></span>

```
PS> New-PSDrive -Name Office -PSProvider FileSystem -Root "C:\Program Files\Micr
osoft Office\OFFICE11"

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
Office     FileSystem    C:\Program Files\Microsoft Offic...
```

> [!NOTE]
> <span data-ttu-id="5d871-128">一般的に、パスは大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="5d871-128">In general, paths are not case-sensitive.</span></span>

<span data-ttu-id="5d871-129">すべての Windows PowerShell ドライブと同様に、名前の後にコロン (**:**) を指定して、新しい Windows PowerShell ドライブを参照します。</span><span class="sxs-lookup"><span data-stu-id="5d871-129">You refer to the new Windows PowerShell drive as you do all Windows PowerShell drives -- by its name followed by a colon (**:**).</span></span>

<span data-ttu-id="5d871-130">Windows PowerShell ドライブにより、多数のタスクが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="5d871-130">A Windows PowerShell drive can make many tasks much simpler.</span></span> <span data-ttu-id="5d871-131">たとえば、Windows レジストリ内の最も重要なキーのいくつかが、極端に長いパスを持っていて、アクセスが煩雑で覚えにくいものがあります。</span><span class="sxs-lookup"><span data-stu-id="5d871-131">For example, some of the most important keys in the Windows registry have extremely long paths, making them cumbersome to access and difficult to remember.</span></span> <span data-ttu-id="5d871-132">重要な設定情報が **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion** にあります。</span><span class="sxs-lookup"><span data-stu-id="5d871-132">Critical configuration information resides under **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion**.</span></span> <span data-ttu-id="5d871-133">CurrentVersion レジストリ キーの項目を表示して変更するために、次のように入力して、そのキーのルートになる Windows PowerShell ドライブを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5d871-133">To view and change items in the CurrentVersion registry key, you can create a Windows PowerShell drive that is rooted in that key by typing:</span></span>

```
PS> New-PSDrive -Name cvkey -PSProvider Registry -Root HKLM\Software\Microsoft\W
indows\CurrentVersion

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
cvkey      Registry      HKLM\Software\Microsoft\Windows\...
```

<span data-ttu-id="5d871-134">**cvkey:** ドライブに場所を移動するには、他のドライブと同様、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5d871-134">You can then change location to the **cvkey:** drive as you would any other drive:``</span></span>

`PS> cd cvkey:`

<span data-ttu-id="5d871-135">または</span><span class="sxs-lookup"><span data-stu-id="5d871-135">or:</span></span>

```
PS> Set-Location cvkey: -PassThru

Path
----
cvkey:\
```

<span data-ttu-id="5d871-136">New-PsDrive コマンドレットが、現在の Windows PowerShell セッションのみに新しいドライブを追加します。</span><span class="sxs-lookup"><span data-stu-id="5d871-136">The New-PsDrive cmdlet adds the new drive only to the current Windows PowerShell session.</span></span> <span data-ttu-id="5d871-137">Windows PowerShell ウィンドウを閉じると、新しいドライブは失われます。</span><span class="sxs-lookup"><span data-stu-id="5d871-137">If you close the Windows PowerShell window, the new drive is lost.</span></span> <span data-ttu-id="5d871-138">Windows PowerShell ドライブを保存するには、Export-Console コマンドレットを使用して、現在の Windows PowerShell セッションをエクスポートし、PowerShell.exe **PSConsoleFile** パラメーターを使用してインポートします。</span><span class="sxs-lookup"><span data-stu-id="5d871-138">To save a Windows PowerShell drive, use the Export-Console cmdlet to export the current Windows PowerShell session, and then use the PowerShell.exe **PSConsoleFile** parameter to import it.</span></span> <span data-ttu-id="5d871-139">または、新しいドライブを Windows PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="5d871-139">Or, add the new drive to your Windows PowerShell profile.</span></span>

### <a name="deleting-windows-powershell-drives-remove-psdrive"></a><span data-ttu-id="5d871-140">Windows PowerShell ドライブの削除 (Remove-PSDrive)</span><span class="sxs-lookup"><span data-stu-id="5d871-140">Deleting Windows PowerShell Drives (Remove-PSDrive)</span></span>

<span data-ttu-id="5d871-141">**Remove-PSDrive** コマンドレットを使用して、Windows PowerShell からドライブを削除できます。</span><span class="sxs-lookup"><span data-stu-id="5d871-141">You can delete drives from Windows PowerShell by using the **Remove-PSDrive** cmdlet.</span></span> <span data-ttu-id="5d871-142">**Remove-PSDrive** コマンドレットは簡単に使用できます。特定の Windows PowerShell ドライブを削除するには、Windows PowerShell ドライブの名前を指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="5d871-142">The **Remove-PSDrive** cmdlet is easy to use; to delete a specific Windows PowerShell drive, you just supply the Windows PowerShell drive name.</span></span>

<span data-ttu-id="5d871-143">たとえば、**New-PSDrive** のトピックでは、**Office:** という Windows PowerShell ドライブを追加しました。このドライブを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5d871-143">For example, if you added the **Office:** Windows PowerShell drive, as shown in the **New-PSDrive** topic, you can delete it by typing:</span></span>

```powershell
Remove-PSDrive -Name Office
```

<span data-ttu-id="5d871-144">**New-PSDrive** トピックで使用した **cvkey:** という Windows PowerShell ドライブを削除するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d871-144">To delete the **cvkey:** Windows PowerShell drive, also shown in the **New-PSDrive** topic, use the following command:</span></span>

```powershell
Remove-PSDrive -Name cvkey
```

<span data-ttu-id="5d871-145">Windows PowerShell ドライブを削除するのは簡単ですが、そのドライブにいる間は削除できません。</span><span class="sxs-lookup"><span data-stu-id="5d871-145">It's easy to delete a Windows PowerShell drive, but you can't delete it while you are in the drive.</span></span> <span data-ttu-id="5d871-146">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5d871-146">For example:</span></span>

```
PS> cd office:
PS Office:\> remove-psdrive -name office
Remove-PSDrive : Cannot remove drive 'Office' because it is in use.
At line:1 char:15
+ remove-psdrive  <<<< -name office
```

### <a name="adding-and-removing-drives-outside-windows-powershell"></a><span data-ttu-id="5d871-147">Windows PowerShell の外部のドライブを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="5d871-147">Adding and Removing Drives Outside Windows PowerShell</span></span>

<span data-ttu-id="5d871-148">Windows PowerShell は、マップされるネットワーク ドライブ、挿入される USB ドライブ、削除されるドライブ (Windows Script Host (WSH) スクリプトから **net use** コマンドまたは **WScript.NetworkMapNetworkDrive**、**RemoveNetworkDrive** メソッドを使用) など、Windows に追加または削除されるファイル システムのドライブを検出します。</span><span class="sxs-lookup"><span data-stu-id="5d871-148">Windows PowerShell detects file system drives that are added or removed in Windows, including network drives that are mapped, USB drives that are attached, and drives that are deleted by using either the **net use** command or the **WScript.NetworkMapNetworkDrive** and **RemoveNetworkDrive** methods from a Windows Script Host (WSH) script.</span></span>