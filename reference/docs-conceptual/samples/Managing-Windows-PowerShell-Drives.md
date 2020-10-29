---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: Windows PowerShell ドライブの管理
description: PowerShell ドライブは、PowerShell でファイル システム ドライブのようにアクセスできるデータ ストアの場所です。 PowerShell には既定で、ファイル システム、レジストリ、証明書ストアなどをサポートするプロバイダーが含まれます。
ms.openlocfilehash: e4e5347c3f3458f25cea31c8e5a499474985220a
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500336"
---
# <a name="managing-windows-powershell-drives"></a><span data-ttu-id="97639-105">Windows PowerShell ドライブの管理</span><span class="sxs-lookup"><span data-stu-id="97639-105">Managing Windows PowerShell Drives</span></span>

<span data-ttu-id="97639-106">*Windows PowerShell ドライブ* は、Windows PowerShell のファイル システム ドライブのようにアクセスできるデータ格納場所です。</span><span class="sxs-lookup"><span data-stu-id="97639-106">A *Windows PowerShell drive* is a data store location that you can access like a file system drive in Windows PowerShell.</span></span> <span data-ttu-id="97639-107">Windows PowerShell プロバイダーは、ファイル システムのドライブ (C: および D: を含む)、レジストリ ドライブ (HKCU: および HKLM:)、および証明書ドライブ (Cert:) など、いくつかのドライブを作成して、独自の Windows PowerShell ドライブを作成できます。</span><span class="sxs-lookup"><span data-stu-id="97639-107">The Windows PowerShell providers create some drives for you, such as the file system drives (including C: and D:), the registry drives (HKCU: and HKLM:), and the certificate drive (Cert:), and you can create your own Windows PowerShell drives.</span></span> <span data-ttu-id="97639-108">これらのドライブは非常に便利ですが、Windows PowerShell 内でのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="97639-108">These drives are very useful, but they are available only within Windows PowerShell.</span></span> <span data-ttu-id="97639-109">ファイル エクスプローラーや Cmd.exe など、他の Windows ツールを使用してアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="97639-109">You cannot access them by using other Windows tools, such as File Explorer or Cmd.exe.</span></span>

<span data-ttu-id="97639-110">Windows PowerShell は、名詞 **PSDrive** を Windows PowerShell ドライブを操作するコマンドに使用します。</span><span class="sxs-lookup"><span data-stu-id="97639-110">Windows PowerShell uses the noun, **PSDrive** , for commands that work with Windows PowerShell drives.</span></span> <span data-ttu-id="97639-111">Windows PowerShell セッションの Windows PowerShell ドライブの一覧では、 **Get-PSDrive** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="97639-111">For a list of the Windows PowerShell drives in your Windows PowerShell session, use the **Get-PSDrive** cmdlet.</span></span>

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

<span data-ttu-id="97639-112">表示内のドライブは、システムのドライブに応じて異なりますが、一覧は上記の **Get-PSDrive** コマンドの出力のようになります。</span><span class="sxs-lookup"><span data-stu-id="97639-112">Although the drives in the display vary with the drives on your system, the listing will look similar to the output of the **Get-PSDrive** command shown above.</span></span>

<span data-ttu-id="97639-113">ファイル システムのドライブは、Windows PowerShell ドライブのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="97639-113">File system drives are a subset of the Windows PowerShell drives.</span></span> <span data-ttu-id="97639-114">[プロバイダー] 列の FileSystem のエントリによって、ファイル システムのドライブを識別できます。</span><span class="sxs-lookup"><span data-stu-id="97639-114">You can identify the file system drives by the FileSystem entry in the Provider column.</span></span> <span data-ttu-id="97639-115">(Windows PowerShell のファイル システムのドライブは、Windows PowerShell FileSystem プロバイダーによってサポートされます。)</span><span class="sxs-lookup"><span data-stu-id="97639-115">(The file system drives in Windows PowerShell are supported by the Windows PowerShell FileSystem provider.)</span></span>

<span data-ttu-id="97639-116">**Get-PSDrive** コマンドレットの構文を表示するには、 **Get-Command** コマンドに **Syntax** パラメーターを指定して入力します。</span><span class="sxs-lookup"><span data-stu-id="97639-116">To see the syntax of the **Get-PSDrive** cmdlet, type a **Get-Command** command with the **Syntax** parameter:</span></span>

```
PS> Get-Command -Name Get-PSDrive -Syntax

Get-PSDrive [[-Name] <String[]>] [-Scope <String>] [-PSProvider <String[]>] [-V
erbose] [-Debug] [-ErrorAction <ActionPreference>] [-ErrorVariable <String>] [-
OutVariable <String>] [-OutBuffer <Int32>]
```

<span data-ttu-id="97639-117">**PSProvider** パラメーターでは、特定のプロバイダーによってサポートされている Windows PowerShell ドライブのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="97639-117">The **PSProvider** parameter lets you display only the Windows PowerShell drives that are supported by a particular provider.</span></span> <span data-ttu-id="97639-118">たとえば、Windows PowerShell FileSystem プロバイダーによってサポートされる Windows PowerShell ドライブのみを表示するには、 **Get-PSDrive** コマンドに **PSProvider** パラメーターと **FileSystem** の値を指定して入力します。</span><span class="sxs-lookup"><span data-stu-id="97639-118">For example, to display only the Windows PowerShell drives that are supported by the Windows PowerShell FileSystem provider, type a **Get-PSDrive** command with the **PSProvider** parameter and the **FileSystem** value:</span></span>

```
PS> Get-PSDrive -PSProvider FileSystem

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
A          FileSystem    A:\
C          FileSystem    C:\                           ...nd Settings\PowerUser
D          FileSystem    D:\
```

<span data-ttu-id="97639-119">レジストリ ハイブを表す Windows PowerShell ドライブを表示するには、 **PSProvider** パラメーターを使用して、Windows PowerShell Registry プロバイダーによってサポートされる Windows PowerShell ドライブのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="97639-119">To view the Windows PowerShell drives that represent registry hives, use the **PSProvider** parameter to display only the Windows PowerShell drives that are supported by the Windows PowerShell Registry provider:</span></span>

```
PS> Get-PSDrive -PSProvider Registry

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
HKCU       Registry      HKEY_CURRENT_USER
HKLM       Registry      HKEY_LOCAL_MACHINE
```

<span data-ttu-id="97639-120">また、Windows PowerShell ドライブに標準的な Location コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="97639-120">You can also use the standard Location cmdlets with the Windows PowerShell drives:</span></span>

```
PS> Set-Location HKLM:\SOFTWARE
PS> Push-Location .\Microsoft
PS> Get-Location

Path
----
HKLM:\SOFTWARE\Microsoft
```

## <a name="adding-new-windows-powershell-drives-new-psdrive"></a><span data-ttu-id="97639-121">新しい Windows PowerShell ドライブの追加 (New-PSDrive)</span><span class="sxs-lookup"><span data-stu-id="97639-121">Adding New Windows PowerShell Drives (New-PSDrive)</span></span>

<span data-ttu-id="97639-122">**New-PSDrive** コマンドを使用して、独自の Windows PowerShell ドライブを追加できます。</span><span class="sxs-lookup"><span data-stu-id="97639-122">You can add your own Windows PowerShell drives by using the **New-PSDrive** command.</span></span> <span data-ttu-id="97639-123">**New-PSDrive** コマンドの構文を取得するには、 **Get-Command** コマンドに **Syntax** パラメーターを指定して入力します。</span><span class="sxs-lookup"><span data-stu-id="97639-123">To get the syntax for the **New-PSDrive** command, enter the **Get-Command** command with the **Syntax** parameter:</span></span>

```
PS> Get-Command -Name New-PSDrive -Syntax

New-PSDrive [-Name] <String> [-PSProvider] <String> [-Root] <String> [-Descript
ion <String>] [-Scope <String>] [-Credential <PSCredential>] [-Verbose] [-Debug
] [-ErrorAction <ActionPreference>] [-ErrorVariable <String>] [-OutVariable <St
ring>] [-OutBuffer <Int32>] [-WhatIf] [-Confirm]
```

<span data-ttu-id="97639-124">新しい Windows PowerShell ドライブを作成するには、3 つのパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97639-124">To create a new Windows PowerShell drive, you must supply three parameters:</span></span>

- <span data-ttu-id="97639-125">ドライブの名前 (有効な Windows PowerShell の名前を使用できます)</span><span class="sxs-lookup"><span data-stu-id="97639-125">A name for the drive (you can use any valid Windows PowerShell name)</span></span>

- <span data-ttu-id="97639-126">PSProvider (ファイル システムの場所には "FileSystem" を、レジストリの場所には "Registry" を使用します)</span><span class="sxs-lookup"><span data-stu-id="97639-126">The PSProvider (use "FileSystem" for file system locations and "Registry" for registry locations)</span></span>

- <span data-ttu-id="97639-127">ルート、つまり、新しいドライブのルートのパス</span><span class="sxs-lookup"><span data-stu-id="97639-127">The root, that is, the path to the root of the new drive</span></span>

<span data-ttu-id="97639-128">たとえば、 **C:\\Program Files\\Microsoft Office\\OFFICE11** のように、コンピューターの Microsoft Office アプリケーションを含むフォルダーにマップされる、"Office" という名前のドライブを作成できます。</span><span class="sxs-lookup"><span data-stu-id="97639-128">For example, you can create a drive named "Office" that is mapped to the folder that contains the Microsoft Office applications on your computer, such as **C:\\Program Files\\Microsoft Office\\OFFICE11** .</span></span> <span data-ttu-id="97639-129">ドライブを作成するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="97639-129">To create the drive, type the following command:</span></span>

```
PS> New-PSDrive -Name Office -PSProvider FileSystem -Root "C:\Program Files\Microsoft Office\OFFICE11"

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
Office     FileSystem    C:\Program Files\Microsoft Offic...
```

> [!NOTE]
> <span data-ttu-id="97639-130">一般的に、パスは大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="97639-130">In general, paths are not case-sensitive.</span></span>

<span data-ttu-id="97639-131">すべての Windows PowerShell ドライブと同様に、名前の後にコロン ( **:** ) を指定して、新しい Windows PowerShell ドライブを参照します。</span><span class="sxs-lookup"><span data-stu-id="97639-131">You refer to the new Windows PowerShell drive as you do all Windows PowerShell drives -- by its name followed by a colon ( **:** ).</span></span>

<span data-ttu-id="97639-132">Windows PowerShell ドライブにより、多数のタスクが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="97639-132">A Windows PowerShell drive can make many tasks much simpler.</span></span> <span data-ttu-id="97639-133">たとえば、Windows レジストリ内の最も重要なキーのいくつかが、極端に長いパスを持っていて、アクセスが煩雑で覚えにくいものがあります。</span><span class="sxs-lookup"><span data-stu-id="97639-133">For example, some of the most important keys in the Windows registry have extremely long paths, making them cumbersome to access and difficult to remember.</span></span> <span data-ttu-id="97639-134">重要な設定情報が **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion** にあります。</span><span class="sxs-lookup"><span data-stu-id="97639-134">Critical configuration information resides under **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion** .</span></span> <span data-ttu-id="97639-135">CurrentVersion レジストリ キーの項目を表示して変更するために、次のように入力して、そのキーのルートになる Windows PowerShell ドライブを作成できます。</span><span class="sxs-lookup"><span data-stu-id="97639-135">To view and change items in the CurrentVersion registry key, you can create a Windows PowerShell drive that is rooted in that key by typing:</span></span>

```
PS> New-PSDrive -Name cvkey -PSProvider Registry -Root HKLM\Software\Microsoft\Windows\CurrentVersion

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
cvkey      Registry      HKLM\Software\Microsoft\Windows\...
```

<span data-ttu-id="97639-136">他のドライブと同様に、 **cvkey:** ドライブに場所を変更できます。</span><span class="sxs-lookup"><span data-stu-id="97639-136">You can then change location to the **cvkey:** drive as you would any other drive:</span></span>

```
PS> cd cvkey:
```

<span data-ttu-id="97639-137">または</span><span class="sxs-lookup"><span data-stu-id="97639-137">or:</span></span>

```
PS> Set-Location cvkey: -PassThru

Path
----
cvkey:\
```

<span data-ttu-id="97639-138">New-PsDrive コマンドレットが、現在の Windows PowerShell セッションのみに新しいドライブを追加します。</span><span class="sxs-lookup"><span data-stu-id="97639-138">The New-PsDrive cmdlet adds the new drive only to the current Windows PowerShell session.</span></span> <span data-ttu-id="97639-139">Windows PowerShell ウィンドウを閉じると、新しいドライブは失われます。</span><span class="sxs-lookup"><span data-stu-id="97639-139">If you close the Windows PowerShell window, the new drive is lost.</span></span> <span data-ttu-id="97639-140">Windows PowerShell ドライブを保存するには、Export-Console コマンドレットを使用して、現在の Windows PowerShell セッションをエクスポートし、PowerShell.exe **PSConsoleFile** パラメーターを使用してインポートします。</span><span class="sxs-lookup"><span data-stu-id="97639-140">To save a Windows PowerShell drive, use the Export-Console cmdlet to export the current Windows PowerShell session, and then use the PowerShell.exe **PSConsoleFile** parameter to import it.</span></span> <span data-ttu-id="97639-141">または、新しいドライブを Windows PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="97639-141">Or, add the new drive to your Windows PowerShell profile.</span></span>

## <a name="deleting-windows-powershell-drives-remove-psdrive"></a><span data-ttu-id="97639-142">Windows PowerShell ドライブの削除 (Remove-PSDrive)</span><span class="sxs-lookup"><span data-stu-id="97639-142">Deleting Windows PowerShell Drives (Remove-PSDrive)</span></span>

<span data-ttu-id="97639-143">**Remove-PSDrive** コマンドレットを使用して、Windows PowerShell からドライブを削除できます。</span><span class="sxs-lookup"><span data-stu-id="97639-143">You can delete drives from Windows PowerShell by using the **Remove-PSDrive** cmdlet.</span></span> <span data-ttu-id="97639-144">**Remove-PSDrive** コマンドレットは簡単に使用できます。特定の Windows PowerShell ドライブを削除するには、Windows PowerShell ドライブの名前を指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="97639-144">The **Remove-PSDrive** cmdlet is easy to use; to delete a specific Windows PowerShell drive, you just supply the Windows PowerShell drive name.</span></span>

<span data-ttu-id="97639-145">たとえば、 **Office:** Windows PowerShell ドライブを **New-PSDrive** のトピックに示すように追加した場合、次のように入力して削除できます。</span><span class="sxs-lookup"><span data-stu-id="97639-145">For example, if you added the **Office:** Windows PowerShell drive, as shown in the **New-PSDrive** topic, you can delete it by typing:</span></span>

```powershell
Remove-PSDrive -Name Office
```

<span data-ttu-id="97639-146">**cvkey:** Windows PowerShell ドライブを削除するには、 **New-PSDrive** のトピックに示すように、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="97639-146">To delete the **cvkey:** Windows PowerShell drive, also shown in the **New-PSDrive** topic, use the following command:</span></span>

```powershell
Remove-PSDrive -Name cvkey
```

<span data-ttu-id="97639-147">Windows PowerShell ドライブを削除するのは簡単ですが、そのドライブにいる間は削除できません。</span><span class="sxs-lookup"><span data-stu-id="97639-147">It's easy to delete a Windows PowerShell drive, but you can't delete it while you are in the drive.</span></span> <span data-ttu-id="97639-148">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="97639-148">For example:</span></span>

```
PS> cd office:
PS Office:\> remove-psdrive -name office
Remove-PSDrive : Cannot remove drive 'Office' because it is in use.
At line:1 char:15
+ remove-psdrive  <<<< -name office
```

## <a name="adding-and-removing-drives-outside-windows-powershell"></a><span data-ttu-id="97639-149">Windows PowerShell の外部のドライブを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="97639-149">Adding and Removing Drives Outside Windows PowerShell</span></span>

<span data-ttu-id="97639-150">Windows PowerShell は、マップされるネットワーク ドライブ、挿入される USB ドライブ、削除されるドライブ (Windows Script Host (WSH) スクリプトから **net use** コマンドまたは **WScript.NetworkMapNetworkDrive** 、 **RemoveNetworkDrive** メソッドを使用) など、Windows に追加または削除されるファイル システムのドライブを検出します。</span><span class="sxs-lookup"><span data-stu-id="97639-150">Windows PowerShell detects file system drives that are added or removed in Windows, including network drives that are mapped, USB drives that are attached, and drives that are deleted by using either the **net use** command or the **WScript.NetworkMapNetworkDrive** and **RemoveNetworkDrive** methods from a Windows Script Host (WSH) script.</span></span>
