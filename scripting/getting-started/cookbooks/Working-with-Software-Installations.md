---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "ソフトウェア インストールの操作"
ms.assetid: 51a12fe9-95f6-4ffc-81a5-4fa72a5bada9
ms.openlocfilehash: 2078376a8be19c9ff8ecc44183eb89f14bc388ed
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="working-with-software-installations"></a><span data-ttu-id="42700-103">ソフトウェア インストールの操作</span><span class="sxs-lookup"><span data-stu-id="42700-103">Working with Software Installations</span></span>
<span data-ttu-id="42700-104">Windows インストーラーを使用するように設計されているアプリケーションは、WMI の **Win32_Product** クラスからアクセスできますが、今日使用されているすべてのアプリケーションが Windows インストーラーを使用しているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="42700-104">Applications that are designed to use Windows Installer can be accessed through WMI's **Win32_Product** class, but not all applications in use today use the Windows Installer.</span></span> <span data-ttu-id="42700-105">Windows インストーラーは、インストール可能なアプリケーションを操作するための標準的な手法を最も広範囲に提供しているため、主にこれらのアプリケーションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="42700-105">Because the Windows Installer provides the widest range of standard techniques for working with installable applications, we will focus primarily on those applications.</span></span> <span data-ttu-id="42700-106">代替のセットアップ ルーチンを使用するアプリケーションは、通常 Windows インストーラーによって管理されません。</span><span class="sxs-lookup"><span data-stu-id="42700-106">Applications that use alternate setup routines will generally not be managed by the Windows Installer.</span></span> <span data-ttu-id="42700-107">これらのアプリケーションを処理する具体的な方法は、インストーラーのソフトウェアとアプリケーションの開発者によってなされた決定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="42700-107">Specific techniques for working with those applications will depend on the installer software and decisions made by the application developer.</span></span>

> [!NOTE]
> <span data-ttu-id="42700-108">コンピューターにアプリケーションのファイルをコピーすることによってインストールされているアプリケーションは、通常、ここで紹介されている手法を使用してで管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="42700-108">Applications that are installed by copying the application files to the computer usually cannot be managed by using techniques discussed here.</span></span> <span data-ttu-id="42700-109">これらのアプリケーションは、「ファイルとフォルダーの操作」セクションで説明した手法を使用することで、ファイルやフォルダーとして管理できます。</span><span class="sxs-lookup"><span data-stu-id="42700-109">You can manage these applications as files and folders by using the techniques discussed in the "Working With Files and Folders" section.</span></span>

### <a name="listing-windows-installer-applications"></a><span data-ttu-id="42700-110">Windows インストーラー アプリケーションを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="42700-110">Listing Windows Installer Applications</span></span>
<span data-ttu-id="42700-111">ローカルまたはリモート システムに Windows インストーラーを使用してインストールされているアプリケーションの一覧を表示するには、次の単純な WMI クエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="42700-111">To list the applications installed with the Windows Installer on a local or remote system, use the following simple WMI query:</span></span>

```
PS> Get-WmiObject -Class Win32_Product -ComputerName .
IdentifyingNumber : {7131646D-CD3C-40F4-97B9-CD9E4E6262EF}
Name              : Microsoft .NET Framework 2.0
Vendor            : Microsoft Corporation
Version           : 2.0.50727
Caption           : Microsoft .NET Framework 2.0
```

<span data-ttu-id="42700-112">Win32_Product オブジェクトのすべてのプロパティを画面に表示するには、Format-List コマンドレットなど、書式設定のコマンドレットの Properties パラメーターに \* (all) の値を指定して使用します。</span><span class="sxs-lookup"><span data-stu-id="42700-112">To display all of the properties of the Win32_Product object to the display, use the Properties parameter of the formatting cmdlets, such as the Format-List cmdlet, with a value of \* (all).</span></span>

```
PS> Get-WmiObject -Class Win32_Product -ComputerName . | Where-Object -FilterScript {$_.Name -eq "Microsoft .NET Framework 2.0"} | Format-List -Property *
Name              : Microsoft .NET Framework 2.0
Version           : 2.0.50727
InstallState      : 5
Caption           : Microsoft .NET Framework 2.0
Description       : Microsoft .NET Framework 2.0
IdentifyingNumber : {7131646D-CD3C-40F4-97B9-CD9E4E6262EF}
InstallDate       : 20060506
InstallDate2      : 20060506000000.000000-000
InstallLocation   :
PackageCache      : C:\WINDOWS\Installer\619ab2.msi
SKUNumber         :
Vendor            : Microsoft Corporation
```

<span data-ttu-id="42700-113">または、**Get-WmiObject Filter** パラメーターを使用して、Microsoft .NET Framework 2.0 のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="42700-113">Or, you could use the **Get-WmiObject Filter** parameter to select only Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="42700-114">このコマンドで使用されているフィルターは WMI フィルターであるため、Windows PowerShell の構文ではなく、WMI クエリ言語 (WQL) 構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="42700-114">Because the filter used in this command is a WMI filter, it uses WMI Query Language (WQL) syntax, not Windows PowerShell syntax.</span></span> <span data-ttu-id="42700-115">代わりに、</span><span class="sxs-lookup"><span data-stu-id="42700-115">Instead,:</span></span>

```
Get-WmiObject -Class Win32_Product -ComputerName . -Filter "Name='Microsoft .NET Framework 2.0'"| Format-List -Property *
```

<span data-ttu-id="42700-116">WQL クエリは、スペースや等号など、Windows PowerShell で特別な意味を持つ文字を頻繁に使用することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="42700-116">Note that WQL queries frequently use characters, such as spaces or equal signs, that have a special meaning in Windows PowerShell.</span></span> <span data-ttu-id="42700-117">このため、フィルターのパラメーターの値は、常に引用符で囲むのが安全です。</span><span class="sxs-lookup"><span data-stu-id="42700-117">For this reason, it is prudent to always enclose the value of the Filter parameter in quotation marks.</span></span> <span data-ttu-id="42700-118">また、読みやすさは向上しませんが、Windows PowerShell のエスケープ文字であるバックティック (\\`) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="42700-118">You can also use the Windows PowerShell escape character, a backtick (\\`), although it may not improve readability.</span></span> <span data-ttu-id="42700-119">次のコマンドは前のコマンドと同等で、同様の結果を返しますが、フィルター文字列全体を引用符で囲むのではなく、バックティックを使用して説くス文字をエスケープします。</span><span class="sxs-lookup"><span data-stu-id="42700-119">The following command is equivalent to the previous command and returns the same results, but uses the backtick to escape special characters, instead of quoting the entire filter string.</span></span>

```
Get-WmiObject -Class Win32_Product -ComputerName . -Filter Name`=`'Microsoft` .NET` Framework` 2.0`' | Format-List -Property *
```

<span data-ttu-id="42700-120">関心のあるプロパティのみの一覧を表示するには、書式設定コマンドレットの Property パラメーターを使用して、必要なプロパティの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="42700-120">To list only the properties that interest you, use the Property parameter of the formatting cmdlets to list the desired properties.</span></span>

```
Get-WmiObject -Class Win32_Product -ComputerName . | Format-List -Property Name,InstallDate,InstallLocation,PackageCache,Vendor,Version,IdentifyingNumber
...
Name              : HighMAT Extension to Microsoft Windows XP CD Writing Wizard
InstallDate       : 20051022
InstallLocation   : C:\Program Files\HighMAT CD Writing Wizard\
PackageCache      : C:\WINDOWS\Installer\113b54.msi
Vendor            : Microsoft Corporation
Version           : 1.1.1905.1
IdentifyingNumber : {FCE65C4E-B0E8-4FBD-AD16-EDCBE6CD591F}
...
```

<span data-ttu-id="42700-121">最後に、インストールされたアプリケーションの名前のみを検索するには、単純な **Format-Wide** ステートメントにより、出力が簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="42700-121">Finally, to find only the names of installed applications, a simple **Format-Wide** statement simplifies the output:</span></span>

```
Get-WmiObject -Class Win32_Product -ComputerName .  | Format-Wide -Column 1
```

<span data-ttu-id="42700-122">これまでインストールに Windows インストーラーを使用したアプリケーションを検索する方法をいくつか確認しましたが、他のアプリケーションはまだ検討していません。</span><span class="sxs-lookup"><span data-stu-id="42700-122">Although we now have several ways to look at applications that used the Windows Installer for installation, we have not considered other applications.</span></span> <span data-ttu-id="42700-123">ほとんどの標準的なアプリケーションはアンインストーラーを Windows に登録するため、Windows レジストリでこれらを検索することで、ローカルで操作できます。</span><span class="sxs-lookup"><span data-stu-id="42700-123">Because most standard applications register their uninstaller with Windows, we can work with those locally by finding them in the Windows registry.</span></span>

### <a name="listing-all-uninstallable-applications"></a><span data-ttu-id="42700-124">アンインストール可能なすべてのアプリケーションを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="42700-124">Listing All Uninstallable Applications</span></span>
<span data-ttu-id="42700-125">システム上のすべてのアプリケーションを検索する確実な方法はありませんが、[プログラム追加と削除] ダイアログ ボックスに表示される一覧ですべてのプログラムを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="42700-125">Although there is no guaranteed way to find every application on a system, it is possible to find all programs with listings displayed in the Add or Remove Programs dialog box.</span></span> <span data-ttu-id="42700-126">[プログラム追加と削除] は、次のレジストリ キーでこれらのアプリケーションを検索します。</span><span class="sxs-lookup"><span data-stu-id="42700-126">Add or Remove Programs finds these applications in the following registry key:</span></span>

<span data-ttu-id="42700-127">**HKEY_LOCAL_MACHINE\\Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall**</span><span class="sxs-lookup"><span data-stu-id="42700-127">**HKEY_LOCAL_MACHINE\\Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall**.</span></span>

<span data-ttu-id="42700-128">また、このキーを確認してアプリケーションを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="42700-128">We can also examine this key to find applications.</span></span> <span data-ttu-id="42700-129">Uninstall キーを簡単に表示できるように、このレジストリの場所に Windows PowerShell ドライブをマップできます。</span><span class="sxs-lookup"><span data-stu-id="42700-129">To make it easier to view the Uninstall key, we can map a Windows PowerShell drive to this registry location:</span></span>

```
PS> New-PSDrive -Name Uninstall -PSProvider Registry -Root HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall    

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
Uninstall  Registry      HKEY_LOCAL_MACHINE\SOFTWARE\Micr...
```

> [!NOTE]
> <span data-ttu-id="42700-130">**HKLM:** ドライブは、**HKEY_LOCAL_MACHINE** のルートにマップされているので、このドライブを Uninstall キーのパスに使用しました。</span><span class="sxs-lookup"><span data-stu-id="42700-130">The **HKLM:** drive is mapped to the root of **HKEY_LOCAL_MACHINE**, so we used that drive in the path to the Uninstall key.</span></span> <span data-ttu-id="42700-131">**HKLM:** の代わりに、**HKLM** または **HKEY_LOCAL_MACHINE** のいずれかを使用して、レジストリのパスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="42700-131">Instead of **HKLM:** we could have specified the registry path by using either **HKLM** or **HKEY_LOCAL_MACHINE**.</span></span> <span data-ttu-id="42700-132">既存のレジストリ ドライブを使用する利点は、タブ補完を利用してキーの名前を入力できるため、ユーザーが入力する必要がないことです。</span><span class="sxs-lookup"><span data-stu-id="42700-132">The advantage of using an existing registry drive is that we can use tab-completion to fill in the keys names, so we do not need to type them.</span></span>

<span data-ttu-id="42700-133">これで、"Uninstall" という名前のドライブができ、これを利用することでアプリケーションのインストールの検索が迅速かつ便利になります。</span><span class="sxs-lookup"><span data-stu-id="42700-133">We now have a drive named "Uninstall" that can be used to quickly and conveniently look for application installations.</span></span> <span data-ttu-id="42700-134">Uninstall: Windows PowerShell ドライブで、レジストリ キーの数をカウントすることによって、インストールされているアプリケーションの数がわかります。</span><span class="sxs-lookup"><span data-stu-id="42700-134">We can find the number of installed applications by counting the number of registry keys in the Uninstall: Windows PowerShell drive:</span></span>

```
PS> (Get-ChildItem -Path Uninstall:).Count
459
```

<span data-ttu-id="42700-135">**Get-ChildItem** をはじめとするさまざまな方法を利用して、アプリケーションの一覧を詳細に検索できます。</span><span class="sxs-lookup"><span data-stu-id="42700-135">We can search this list of applications further by using a variety of techniques, beginning with **Get-ChildItem**.</span></span> <span data-ttu-id="42700-136">アプリケーションの一覧を取得して、**$UninstallableApplications** 変数に保存するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="42700-136">To get a list of applications and save them in the **$UninstallableApplications** variable, use the following command:</span></span>

```
$UninstallableApplications = Get-ChildItem -Path Uninstall:
```

> [!NOTE]
> <span data-ttu-id="42700-137">ここでは、わかりやすくするために長い変数名を使用しています。</span><span class="sxs-lookup"><span data-stu-id="42700-137">We are using a lengthy variable name here for clarity.</span></span> <span data-ttu-id="42700-138">実際に使用するときは、長い名前を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="42700-138">In actual use, there is no reason to use long names.</span></span> <span data-ttu-id="42700-139">変数名にタブ補完を使用できますが、1 ～ 2 文字の名前を使用すると時間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="42700-139">Although you can use tab-completion for variable names, you can also use 1-2 character names for speed.</span></span> <span data-ttu-id="42700-140">長くわかりやすい名前は、再利用するためのコードを開発する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="42700-140">Longer, descriptive names are most useful when you are developing code for reuse.</span></span>

<span data-ttu-id="42700-141">Uninstall の下のレジストリ キーにレジストリ エントリの値を表示するには、レジストリ キーの GetValue メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="42700-141">To display the values of the registry entries in the registry keys under Uninstall, use the GetValue method of the registry keys.</span></span> <span data-ttu-id="42700-142">メソッドの値は、レジストリ エントリの名前です。</span><span class="sxs-lookup"><span data-stu-id="42700-142">The value of the method is the name of the registry entry.</span></span>

<span data-ttu-id="42700-143">たとえば、Uninstall キーの下でアプリケーションの表示名を検索するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="42700-143">For example, to find the display names of applications in the Uninstall key, use the following command:</span></span>

```
PS> Get-ChildItem -Path Uninstall: | ForEach-Object -Process { $_.GetValue("DisplayName") }
```

<span data-ttu-id="42700-144">これらの値が一意である保証はありません。</span><span class="sxs-lookup"><span data-stu-id="42700-144">There is no guarantee that these values are unique.</span></span> <span data-ttu-id="42700-145">次の例では、インストールされている 2 つの項目が "Windows Media エンコーダー 9 シリーズ" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="42700-145">In the following example, two installed items appear as "Windows Media Encoder 9 Series":</span></span>

```
PS> Get-ChildItem -Path Uninstall: | Where-Object -FilterScript { $_.GetValue("DisplayName") -eq "Windows Media Encoder 9 Series"}

   Hive: Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Micros
oft\Windows\CurrentVersion\Uninstall

SKC  VC Name                           Property
---  -- ----                           --------
  0   3 Windows Media Encoder 9        {DisplayName, DisplayIcon, UninstallS...
  0  24 {E38C00D0-A68B-4318-A8A6-F7... {AuthorizedCDFPrefix, Comments, Conta...
```

### <a name="installing-applications"></a><span data-ttu-id="42700-146">アプリケーションのインストール</span><span class="sxs-lookup"><span data-stu-id="42700-146">Installing Applications</span></span>
<span data-ttu-id="42700-147">**Win32_Product** クラスを使用して、リモートまたはローカルで、Windows インストーラー パッケージをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="42700-147">You can use the **Win32_Product** class to install Windows Installer packages, remotely or locally.</span></span>

> [!NOTE]
> <span data-ttu-id="42700-148">Windows Vista、Windows Server 2008、およびそれ以降のバージョンの Windows では、アプリケーションをインストールするには、[管理者として実行] オプションを使用して Windows PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42700-148">On Windows Vista, Windows Server 2008, and later versions of Windows, to install an application, you must start Windows PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="42700-149">リモートでインストールする場合は、WMI のサブシステムが Windows PowerShell のパスを認識しないため、.msi パッケージへのパスを指定するのに、汎用名前付け規則 (UNC) のネットワーク パスを使用します。</span><span class="sxs-lookup"><span data-stu-id="42700-149">When installing remotely, use a Universal Naming Convention (UNC) network path to specify the path to the .msi package, because the WMI subsystem does not understand Windows PowerShell paths.</span></span> <span data-ttu-id="42700-150">たとえば、リモート コンピューター PC01 のネットワーク共有 \\\\AppServ\\dsp にある NewPackage.msi パッケージをインストールするには、Windows PowerShell プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="42700-150">For example, to install the NewPackage.msi package located in the network share \\\\AppServ\\dsp on the remote computer PC01, type the following command at the Windows PowerShell prompt:</span></span>

```
(Get-WMIObject -ComputerName PC01 -List | Where-Object -FilterScript {$_.Name -eq "Win32_Product"}).Install(\\AppSrv\dsp\NewPackage.msi)
```

<span data-ttu-id="42700-151">Windows インストーラー テクノロジを使用しないアプリケーションは、展開の自動化に利用できるアプリケーション固有の方法があります。</span><span class="sxs-lookup"><span data-stu-id="42700-151">Applications that do not use Windows Installer technology may have application-specific methods available for automated deployment.</span></span> <span data-ttu-id="42700-152">展開を自動化するための方法があるかどうかを確認するには、アプリケーションのマニュアルを参照するか、アプリケーション ベンダーのサポート システムを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42700-152">To determine whether there is a method for deployment automation, check the documentation for the application or consult the application vendor's support system.</span></span> <span data-ttu-id="42700-153">場合によっては、アプリケーション ベンダーが特にインストールの自動化に対応するようアプリケーションを設計していなくても、インストーラー ソフトウェアの製造元が自動化のためのテクニックをいくつか持っていることがあります。</span><span class="sxs-lookup"><span data-stu-id="42700-153">In some cases, even if the application vendor did not specifically design the application for installation automation, the installer software manufacturer may have some techniques for automation.</span></span>

### <a name="removing-applications"></a><span data-ttu-id="42700-154">アプリケーションの削除</span><span class="sxs-lookup"><span data-stu-id="42700-154">Removing Applications</span></span>
<span data-ttu-id="42700-155">Windows PowerShell を使用した Windows インストーラー パッケージの削除は、パッケージのインストールとほとんど同じ方法で機能します。</span><span class="sxs-lookup"><span data-stu-id="42700-155">Removing a Windows Installer package by using Windows PowerShell works in approximately the same way as installing a package.</span></span> <span data-ttu-id="42700-156">名前に基づいてアンインストールするパッケージを選択する例を以下に示します。場合によっては、**IdentifyingNumber** を使用してフィルター処理した方が簡単になることがあります。</span><span class="sxs-lookup"><span data-stu-id="42700-156">Here is an example that selects the package to uninstall based on its name; in some cases it may be easier to filter with the **IdentifyingNumber**:</span></span>

```
(Get-WmiObject -Class Win32_Product -Filter "Name='ILMerge'" -ComputerName . ).Uninstall()
```

<span data-ttu-id="42700-157">他のアプリケーションの削除は、ローカルで実行する場合でも、それほど単純ではありません。</span><span class="sxs-lookup"><span data-stu-id="42700-157">Removing other applications is not quite so simple, even when done locally.</span></span> <span data-ttu-id="42700-158">**UninstallString** プロパティを抽出することで、これらのアプリケーションに対するコマンド ラインのアンインストール文字列を検索できます。</span><span class="sxs-lookup"><span data-stu-id="42700-158">We can find the command line uninstallation strings for these applications by extracting the **UninstallString** property.</span></span> <span data-ttu-id="42700-159">このメソッドは、Windows インストーラー アプリケーションや Uninstall キーの下に表示される古いプログラムに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="42700-159">This method works for Windows Installer applications and for older programs appearing under the Uninstall key:</span></span>

```
Get-ChildItem -Path Uninstall: | ForEach-Object -Process { $_.GetValue("UninstallString") }
```

<span data-ttu-id="42700-160">必要であれば、出力を表示名でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="42700-160">You can filter the output by the display name, if you like:</span></span>

```
Get-ChildItem -Path Uninstall: | Where-Object -FilterScript { $_.GetValue("DisplayName") -like "Win*"} | ForEach-Object -Process { $_.GetValue("UninstallString") }
```

<span data-ttu-id="42700-161">ただし、これらの文字列は、Windows PowerShell プロンプトから直接使用するには、いくつか変更が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="42700-161">However, these strings may not be directly usable from the Windows PowerShell prompt without some modification.</span></span>

### <a name="upgrading-windows-installer-applications"></a><span data-ttu-id="42700-162">Windows インストーラー アプリケーションのアップグレード</span><span class="sxs-lookup"><span data-stu-id="42700-162">Upgrading Windows Installer Applications</span></span>
<span data-ttu-id="42700-163">アプリケーションをアップグレードするには、アプリケーションの名前、およびアプリケーションのアップグレード パッケージのパスを認識している必要があります。</span><span class="sxs-lookup"><span data-stu-id="42700-163">To upgrade an application, you need to know the name of the application and the path to the application upgrade package.</span></span> <span data-ttu-id="42700-164">その情報があれば、1 つの Windows PowerShell コマンドを使用してアプリケーションをアップグレードすることができます。</span><span class="sxs-lookup"><span data-stu-id="42700-164">With that information, you can upgrade an application with a single Windows PowerShell command:</span></span>

```
(Get-WmiObject -Class Win32_Product -ComputerName . -Filter "Name='OldAppName'").Upgrade(\\AppSrv\dsp\OldAppUpgrade.msi)
```

