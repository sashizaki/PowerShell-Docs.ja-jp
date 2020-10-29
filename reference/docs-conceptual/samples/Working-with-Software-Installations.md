---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: ソフトウェア インストールの操作
description: この記事では、WMI を使用して Windows にインストールされたソフトウェアを管理する方法を示します。
ms.openlocfilehash: 3cf8e3c58e9f2814e2551b3602bd7b47b375aed8
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500880"
---
# <a name="working-with-software-installations"></a><span data-ttu-id="ad731-104">ソフトウェア インストールの操作</span><span class="sxs-lookup"><span data-stu-id="ad731-104">Working with Software Installations</span></span>

<span data-ttu-id="ad731-105">Windows インストーラーを使用するように設計されているアプリケーションは、WMI の **Win32_Product** クラスからアクセスできますが、今日使用されているすべてのアプリケーションが Windows インストーラーを使用しているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="ad731-105">Applications that are designed to use Windows Installer can be accessed through WMI's **Win32_Product** class, but not all applications in use today use the Windows Installer.</span></span>
<span data-ttu-id="ad731-106">代替のセットアップ ルーチンが使われるアプリケーションは、通常 Windows インストーラーによって管理されません。</span><span class="sxs-lookup"><span data-stu-id="ad731-106">Applications that use alternate setup routines are not usually managed by the Windows Installer.</span></span>
<span data-ttu-id="ad731-107">このようなアプリケーションを処理するための具体的な方法は、インストーラー ソフトウェアおよびアプリケーション開発者による決定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ad731-107">Specific techniques for working with those applications depends on the installer software and decisions made by the application developer.</span></span> <span data-ttu-id="ad731-108">たとえば、コンピューター上のフォルダーにファイルをコピーすることでインストールするアプリケーションは、通常、ここで紹介している手法を使用して管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="ad731-108">For example, applications installed by copying the files to a folder on the computer usually cannot be managed by using techniques discussed here.</span></span> <span data-ttu-id="ad731-109">このようなファイルとフォルダーとしてのアプリケーションは、「[ファイルとフォルダーの操作](Working-with-Files-and-Folders.md)」で説明されている手法を使って管理できます。</span><span class="sxs-lookup"><span data-stu-id="ad731-109">You can manage these applications as files and folders by using the techniques discussed in [Working With Files and Folders](Working-with-Files-and-Folders.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="ad731-110">**Win32_Product** クラスはクエリ用に最適化されていません。</span><span class="sxs-lookup"><span data-stu-id="ad731-110">The **Win32_Product** class is not query optimized.</span></span> <span data-ttu-id="ad731-111">クエリでワイルドカード フィルターが使われると、インストールされているすべての製品を列挙するため WMI によって MSI のプロバイダーが使われ、その後フィルターを処理するために完全な一覧が順次解析されます。</span><span class="sxs-lookup"><span data-stu-id="ad731-111">Queries that use wildcard filters cause WMI to use the MSI provider to enumerate all installed products then parse the full list sequentially to handle the filter.</span></span> <span data-ttu-id="ad731-112">これによってインストールされているパッケージの整合性チェックも開始され、インストールの検証および修復が行われます。</span><span class="sxs-lookup"><span data-stu-id="ad731-112">This also initiates a consistency check of packages installed, verifying and repairing the install.</span></span> <span data-ttu-id="ad731-113">この検証は時間のかかるプロセスで、イベント ログにエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ad731-113">The validation is a slow process and may result in errors in the event logs.</span></span> <span data-ttu-id="ad731-114">詳細については、[サポート技術情報の記事 974524](https://support.microsoft.com/help/974524) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ad731-114">For more information seek [KB article 974524](https://support.microsoft.com/help/974524).</span></span>

## <a name="listing-windows-installer-applications"></a><span data-ttu-id="ad731-115">Windows インストーラー アプリケーションを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="ad731-115">Listing Windows Installer Applications</span></span>

<span data-ttu-id="ad731-116">ローカルまたはリモート システムに Windows インストーラーを使用してインストールされているアプリケーションの一覧を表示するには、次の単純な WMI クエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad731-116">To list the applications installed with the Windows Installer on a local or remote system, use the following simple WMI query:</span></span>

```powershell
Get-CimInstance -Class Win32_Product |
  Where-Object Name -eq "Microsoft .NET Core Runtime - 2.1.5 (x64)"
```

```Output
Name             Caption                   Vendor                    Version       IdentifyingNumber
----             -------                   ------                    -------       -----------------
Microsoft .NET … Microsoft .NET Core Runt… Microsoft Corporation     16.84.26919   {BEB59D04-C6DD-4926-AFE…
```

<span data-ttu-id="ad731-117">**Win32_Product** オブジェクトのすべてのプロパティを画面に表示するには、`Format-List` コマンドレットなど、書式設定のコマンドレットの **Properties** パラメーターに `*` (all) の値を指定して使用します。</span><span class="sxs-lookup"><span data-stu-id="ad731-117">To display all the properties of the **Win32_Product** object to the display, use the **Properties** parameter of the formatting cmdlets, such as the `Format-List` cmdlet, with a value of `*` (all).</span></span>

```powershell
Get-CimInstance -Class Win32_Product |
  Where-Object Name -eq "Microsoft .NET Core Runtime - 2.1.5 (x64)" |
    Format-List -Property *
```

```Output
Name                  : Microsoft .NET Core Runtime - 2.1.5 (x64)
Version               : 16.84.26919
InstallState          : 5
Caption               : Microsoft .NET Core Runtime - 2.1.5 (x64)
Description           : Microsoft .NET Core Runtime - 2.1.5 (x64)
IdentifyingNumber     : {BEB59D04-C6DD-4926-AFEB-410CBE2EBCE4}
SKUNumber             :
Vendor                : Microsoft Corporation
AssignmentType        : 1
HelpLink              :
HelpTelephone         :
InstallDate           : 20181105
InstallDate2          :
InstallLocation       :
InstallSource         : C:\ProgramData\Package Cache\{BEB59D04-C6DD-4926-AFEB-410CBE2EBCE4}v16.84.26919\
Language              : 1033
LocalPackage          : C:\WINDOWS\Installer\4f97a771.msi
PackageCache          : C:\WINDOWS\Installer\4f97a771.msi
PackageCode           : {9A271A10-039D-49EA-8D24-043D91B9F915}
PackageName           : dotnet-runtime-2.1.5-win-x64.msi
ProductID             :
RegCompany            :
RegOwner              :
Transforms            :
URLInfoAbout          :
URLUpdateInfo         :
WordCount             : 0
PSComputerName        :
CimClass              : root/cimv2:Win32_Product
CimInstanceProperties : {Caption, Description, IdentifyingNumber, Name...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

<span data-ttu-id="ad731-118">または、`Get-CimInstance` **Filter** パラメーターを使用して、Microsoft .NET 2.0 Runtime のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ad731-118">Or, you could use the `Get-CimInstance` **Filter** parameter to select only Microsoft .NET 2.0 Runtime.</span></span> <span data-ttu-id="ad731-119">**Filter** パラメーターの値に対しては、Windows PowerShell の構文ではなく、WMI Query Language (WQL) の構文が使われます。</span><span class="sxs-lookup"><span data-stu-id="ad731-119">The value of the **Filter** parameter uses WMI Query Language (WQL) syntax, not Windows PowerShell syntax.</span></span> <span data-ttu-id="ad731-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ad731-120">For example:</span></span>

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='Microsoft .NET Core Runtime - 2.1.5 (x64)'" |
  Format-List -Property *
```

<span data-ttu-id="ad731-121">関心のあるプロパティだけを一覧表示させるには、書式設定コマンドレットの **Property** パラメーターを使用して必要なプロパティを一覧表示させます。</span><span class="sxs-lookup"><span data-stu-id="ad731-121">To list only the properties that interest you, use the **Property** parameter of the formatting cmdlets to list the desired properties.</span></span>

```powershell
Get-CimInstance -Class Win32_Product  -Filter "Name='Microsoft .NET Core Runtime - 2.1.5 (x64)'" |
  Format-List -Property Name,InstallDate,InstallLocation,PackageCache,Vendor,Version,IdentifyingNumber
```

```Output
Name              : Microsoft .NET Core Runtime - 2.1.5 (x64)
InstallDate       : 20180816
InstallLocation   :
PackageCache      : C:\WINDOWS\Installer\4f97a771.msi
Vendor            : Microsoft Corporation
Version           : 16.72.26629
IdentifyingNumber : {ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}
```

## <a name="listing-all-uninstallable-applications"></a><span data-ttu-id="ad731-122">アンインストール可能なすべてのアプリケーションを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="ad731-122">Listing All Uninstallable Applications</span></span>

<span data-ttu-id="ad731-123">ほとんどの標準的なアプリケーションでは Windows にアンインストーラーが登録されるため、Windows レジストリでこれらを検索することで、ローカルで操作できます。</span><span class="sxs-lookup"><span data-stu-id="ad731-123">Because most standard applications register an uninstaller with Windows, we can work with those locally by finding them in the Windows registry.</span></span> <span data-ttu-id="ad731-124">システム上のすべてのアプリケーションを検索する確実な方法はありません。</span><span class="sxs-lookup"><span data-stu-id="ad731-124">There is no guaranteed way to find every application on a system.</span></span> <span data-ttu-id="ad731-125">ただし、次のレジストリ キーで **[プログラムの追加と削除]** に表示されるリストを備えているプログラムをすべて検索することは可能です。</span><span class="sxs-lookup"><span data-stu-id="ad731-125">However, it is possible to find all programs with listings displayed in **Add or Remove Programs** in the following registry key:</span></span>

<span data-ttu-id="ad731-126">`HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Uninstall`.</span><span class="sxs-lookup"><span data-stu-id="ad731-126">`HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Uninstall`.</span></span>

<span data-ttu-id="ad731-127">このキーを調べて、アプリケーションを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="ad731-127">We can examine this key to find applications.</span></span> <span data-ttu-id="ad731-128">Uninstall キーを簡単に表示できるように、このレジストリの場所に PowerShell ドライブをマップできます。</span><span class="sxs-lookup"><span data-stu-id="ad731-128">To make it easier to view the Uninstall key, we can map a PowerShell drive to this registry location:</span></span>

```powershell
New-PSDrive -Name Uninstall -PSProvider Registry -Root HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall
```

```Output
Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
Uninstall  Registry      HKEY_LOCAL_MACHINE\SOFTWARE\Micr...
```

<span data-ttu-id="ad731-129">これで "Uninstall:" という名前のドライブができました。これを使うと、アプリケーションのインストールをすばやく便利に検索できます。</span><span class="sxs-lookup"><span data-stu-id="ad731-129">We now have a drive named "Uninstall:" that can be used to quickly and conveniently look for application installations.</span></span> <span data-ttu-id="ad731-130">Uninstall のレジストリ キーの数をカウントすることによって、インストールされているアプリケーションの数がわかります。PowerShell ドライブ:</span><span class="sxs-lookup"><span data-stu-id="ad731-130">We can find the number of installed applications by counting the number of registry keys in the Uninstall: PowerShell drive:</span></span>

```powershell
(Get-ChildItem -Path Uninstall:).Count
```

```Output
459
```

<span data-ttu-id="ad731-131">`Get-ChildItem` をはじめとするさまざまな方法を利用して、アプリケーションの一覧を詳細に検索できます。</span><span class="sxs-lookup"><span data-stu-id="ad731-131">We can search this list of applications further by using a variety of techniques, beginning with `Get-ChildItem`.</span></span> <span data-ttu-id="ad731-132">アプリケーションの一覧を取得して、`$UninstallableApplications` 変数に保存するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad731-132">To get a list of applications and save them in the `$UninstallableApplications` variable, use the following command:</span></span>

```powershell
$UninstallableApplications = Get-ChildItem -Path Uninstall:
```

<span data-ttu-id="ad731-133">Uninstall の下のレジストリ キーにレジストリ エントリの値を表示するには、レジストリ キーの GetValue メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad731-133">To display the values of the registry entries in the registry keys under Uninstall, use the GetValue method of the registry keys.</span></span> <span data-ttu-id="ad731-134">メソッドの値は、レジストリ エントリの名前です。</span><span class="sxs-lookup"><span data-stu-id="ad731-134">The value of the method is the name of the registry entry.</span></span>

<span data-ttu-id="ad731-135">たとえば、Uninstall キーの下でアプリケーションの表示名を検索するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad731-135">For example, to find the display names of applications in the Uninstall key, use the following command:</span></span>

```powershell
$UninstallableApplications | ForEach-Object -Process { $_.GetValue('DisplayName') }
```

<span data-ttu-id="ad731-136">これらの値が一意である保証はありません。</span><span class="sxs-lookup"><span data-stu-id="ad731-136">There is no guarantee that these values are unique.</span></span> <span data-ttu-id="ad731-137">次の例では、インストールされている 2 つの項目が "Windows Media エンコーダー 9 シリーズ" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad731-137">In the following example, two installed items appear as "Windows Media Encoder 9 Series":</span></span>

```powershell
$UninstallableApplications | Where-Object -FilterScript {
  $_.GetValue("DisplayName") -eq "Microsoft Silverlight"
}
```

```Output
    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall

Name                           Property
----                           --------
{89F4137D-6C26-4A84-BDB8-2E5A4 AuthorizedCDFPrefix :
BB71E00}                       Comments            :
                               Contact             :
                               DisplayVersion      : 5.1.50918.0
                               HelpLink            : https://go.microsoft.com/fwlink/?LinkID=91955
                               HelpTelephone       :
                               InstallDate         : 20190115
                               InstallLocation     : C:\Program Files\Microsoft Silverlight\
                               InstallSource       : c:\ef64c54526db9c34cd477c103e68a254\
                               ModifyPath          : MsiExec.exe /X{89F4137D-6C26-4A84-BDB8-2E5A4BB71E00}
                               NoModify            : 1
                               NoRepair            : 1
                               Publisher           : Microsoft Corporation
                               Readme              :
                               Size                :
                               EstimatedSize       : 236432
                               UninstallString     : MsiExec.exe /X{89F4137D-6C26-4A84-BDB8-2E5A4BB71E00}
                               URLInfoAbout        :
                               URLUpdateInfo       :
                               VersionMajor        : 5
                               VersionMinor        : 1
                               WindowsInstaller    : 1
                               Version             : 84002534
                               Language            : 1033
                               DisplayName         : Microsoft Silverlight
                               sEstimatedSize2     : 79214
```

## <a name="installing-applications"></a><span data-ttu-id="ad731-138">アプリケーションのインストール</span><span class="sxs-lookup"><span data-stu-id="ad731-138">Installing Applications</span></span>

<span data-ttu-id="ad731-139">**Win32_Product** クラスを使用して、リモートまたはローカルで、Windows インストーラー パッケージをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ad731-139">You can use the **Win32_Product** class to install Windows Installer packages, remotely or locally.</span></span>

> [!NOTE]
> <span data-ttu-id="ad731-140">アプリケーションをインストールするには、[管理者として実行] オプションを指定して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad731-140">To install an application, you must start PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="ad731-141">リモートでインストールする場合、WMI のサブシステムによって PowerShell のパスが認識されないため、汎用名前付け規則 (UNC) のネットワーク パスを使って .msi パッケージへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad731-141">When installing remotely, use a Universal Naming Convention (UNC) network path to specify the path to the .msi package, because the WMI subsystem does not understand PowerShell paths.</span></span> <span data-ttu-id="ad731-142">たとえば、リモート コンピューター PC01 のネットワーク共有 `\\AppServ\dsp` にある NewPackage.msi パッケージをインストールするには、PowerShell プロンプトに次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ad731-142">For example, to install the NewPackage.msi package located in the network share `\\AppServ\dsp` on the remote computer PC01, type the following command at the PowerShell prompt:</span></span>

```powershell
Invoke-CimMethod -ClassName Win32_Product -MethodName Install -Arguments @{PackageLocation='\\AppSrv\dsp\NewPackage.msi'}
```

<span data-ttu-id="ad731-143">Windows インストーラーのテクノロジが使われないアプリケーションには、展開を自動化するためのアプリケーション固有の方法がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="ad731-143">Applications that do not use Windows Installer technology may have application-specific methods for automated deployment.</span></span> <span data-ttu-id="ad731-144">そのアプリケーションのドキュメントをチェックするか、アプリケーション ベンダーのサポート システムをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="ad731-144">Check the documentation for the application or consult the application vendor's support system.</span></span>

## <a name="removing-applications"></a><span data-ttu-id="ad731-145">アプリケーションの削除</span><span class="sxs-lookup"><span data-stu-id="ad731-145">Removing Applications</span></span>

<span data-ttu-id="ad731-146">PowerShell を使用した Windows インストーラー パッケージの削除は、パッケージのインストールとほとんど同じ方法で機能します。</span><span class="sxs-lookup"><span data-stu-id="ad731-146">Removing a Windows Installer package using PowerShell works in approximately the same way as installing a package.</span></span> <span data-ttu-id="ad731-147">名前に基づいてアンインストールするパッケージを選択する例を以下に示します。場合によっては、 **IdentifyingNumber** を使用してフィルター処理した方が簡単になることがあります。</span><span class="sxs-lookup"><span data-stu-id="ad731-147">Here is an example that selects the package to uninstall based on its name; in some cases it may be easier to filter with the **IdentifyingNumber** :</span></span>

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='ILMerge'" | Invoke-CimMethod -MethodName Uninstall
```

<span data-ttu-id="ad731-148">他のアプリケーションの削除は、ローカルで実行する場合でも、それほど単純ではありません。</span><span class="sxs-lookup"><span data-stu-id="ad731-148">Removing other applications is not quite so simple, even when done locally.</span></span> <span data-ttu-id="ad731-149">**UninstallString** プロパティを抽出することで、これらのアプリケーションに対するコマンド ラインのアンインストール文字列を検索できます。</span><span class="sxs-lookup"><span data-stu-id="ad731-149">We can find the command line uninstallation strings for these applications by extracting the **UninstallString** property.</span></span>
<span data-ttu-id="ad731-150">このメソッドは、Windows インストーラー アプリケーションや Uninstall キーの下に表示される古いプログラムに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="ad731-150">This method works for Windows Installer applications and for older programs appearing under the Uninstall key:</span></span>

```powershell
Get-ChildItem -Path Uninstall: | ForEach-Object -Process { $_.GetValue('UninstallString') }
```

<span data-ttu-id="ad731-151">必要であれば、出力を表示名でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="ad731-151">You can filter the output by the display name, if you like:</span></span>

```powershell
Get-ChildItem -Path Uninstall: |
    Where-Object -FilterScript { $_.GetValue('DisplayName') -like 'Win*'} |
        ForEach-Object -Process { $_.GetValue('UninstallString') }
```

<span data-ttu-id="ad731-152">ただし、これらの文字列は、変更なしでは PowerShell プロンプトから直接使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ad731-152">However, these strings may not be directly usable from the PowerShell prompt without some modification.</span></span>

## <a name="upgrading-windows-installer-applications"></a><span data-ttu-id="ad731-153">Windows インストーラー アプリケーションのアップグレード</span><span class="sxs-lookup"><span data-stu-id="ad731-153">Upgrading Windows Installer Applications</span></span>

<span data-ttu-id="ad731-154">アプリケーションをアップグレードするには、アプリケーションの名前、およびアプリケーションのアップグレード パッケージのパスを認識している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad731-154">To upgrade an application, you need to know the name of the application and the path to the application upgrade package.</span></span> <span data-ttu-id="ad731-155">その情報があれば、1 つの PowerShell コマンドを使用してアプリケーションをアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="ad731-155">With that information, you can upgrade an application with a single PowerShell command:</span></span>

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='OldAppName'" |
  Invoke-CimMethod -MethodName Upgrade -Arguments @{PackageLocation='\\AppSrv\dsp\OldAppUpgrade.msi'}
```
