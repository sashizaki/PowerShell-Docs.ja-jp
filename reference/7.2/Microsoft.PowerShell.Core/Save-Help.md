---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/save-help?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Help
ms.openlocfilehash: 6996decc6b2f8b99ab9c04d96c487c37f2609c9e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603012"
---
# <span data-ttu-id="626fb-102">Save-Help</span><span class="sxs-lookup"><span data-stu-id="626fb-102">Save-Help</span></span>

## <span data-ttu-id="626fb-103">概要</span><span class="sxs-lookup"><span data-stu-id="626fb-103">SYNOPSIS</span></span>
<span data-ttu-id="626fb-104">最新のヘルプ ファイルをダウンロードしてファイル システム ディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="626fb-104">Downloads and saves the newest help files to a file system directory.</span></span>

## <span data-ttu-id="626fb-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="626fb-105">SYNTAX</span></span>

### <span data-ttu-id="626fb-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="626fb-106">Path (Default)</span></span>

```
Save-Help [-DestinationPath] <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

### <span data-ttu-id="626fb-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="626fb-107">LiteralPath</span></span>

```
Save-Help -LiteralPath <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

## <span data-ttu-id="626fb-108">Description</span><span class="sxs-lookup"><span data-stu-id="626fb-108">DESCRIPTION</span></span>

<span data-ttu-id="626fb-109">`Save-Help`コマンドレットは、PowerShell モジュールの最新のヘルプファイルをダウンロードし、指定したディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="626fb-109">The `Save-Help` cmdlet downloads the newest help files for PowerShell modules and saves them to a directory that you specify.</span></span> <span data-ttu-id="626fb-110">この機能を使用すると、インターネットにアクセスできないコンピューター上のヘルプ ファイルを更新でき、複数のコンピューター上のヘルプ ファイルを更新しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="626fb-110">This feature lets you update the help files on computers that do not have access to the Internet, and makes it easier to update the help files on multiple computers.</span></span>

<span data-ttu-id="626fb-111">Windows PowerShell 3.0 では、 `Save-Help` ローカルコンピューターにインストールされているモジュールに対してのみ動作しました。</span><span class="sxs-lookup"><span data-stu-id="626fb-111">In Windows PowerShell 3.0, `Save-Help` worked only for modules that are installed on the local computer.</span></span> <span data-ttu-id="626fb-112">リモートコンピューターからモジュールをインポートしたり、PowerShell リモート処理を使用してリモートコンピューターから **PSModuleInfo** オブジェクトへの参照を取得したりすることはできましたが、 **Helpinfouri** プロパティは保持されず、 `Save-Help` リモートモジュールのヘルプでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="626fb-112">Although it was possible to import a module from a remote computer, or obtain a reference to a **PSModuleInfo** object from a remote computer by using PowerShell remoting, the **HelpInfoUri** property was not preserved, and `Save-Help` would not work for remote module Help.</span></span>

<span data-ttu-id="626fb-113">Windows PowerShell 4.0 では、 **Helpinfouri** プロパティが PowerShell リモート処理によって保持されます。これにより、 `Save-Help` リモートコンピューターにインストールされているモジュールでを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="626fb-113">In Windows PowerShell 4.0, the **HelpInfoUri** property is preserved over PowerShell remoting, which enables `Save-Help` to work for modules that are installed on remote computers.</span></span> <span data-ttu-id="626fb-114">また、インターネットにアクセスできないコンピューターでを実行して、 **PSModuleInfo** オブジェクトをディスクまたはリムーバブルメディアに保存することもでき `Export-Clixml` ます。その場合、インターネットにアクセスできるコンピューターにオブジェクトをインポートし、 `Save-Help` **PSModuleInfo** オブジェクトでを実行します。</span><span class="sxs-lookup"><span data-stu-id="626fb-114">It is also possible to save a **PSModuleInfo** object to disk or removable media by running `Export-Clixml` on a computer that does not have Internet access, import the object on a computer that does have Internet access, and then run `Save-Help` on the **PSModuleInfo** object.</span></span> <span data-ttu-id="626fb-115">保存されたヘルプは、USB ドライブなどのリムーバブル記憶域メディアを使用してリモートコンピューターに転送できます。</span><span class="sxs-lookup"><span data-stu-id="626fb-115">The saved help can be transported to the remote computer by using removable storage media, such as a USB drive.</span></span> <span data-ttu-id="626fb-116">を実行して、リモートコンピューターにヘルプをインストールでき `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="626fb-116">The help can be installed on the remote computer by running `Update-Help`.</span></span> <span data-ttu-id="626fb-117">このプロセスを使用すれば、どのようなネットワーク アクセスも実行できないコンピューターにヘルプをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="626fb-117">This process can be used to install help on computers that do not have any kind of network access.</span></span>

<span data-ttu-id="626fb-118">保存されたヘルプファイルをインストールするには、コマンドレットを実行し `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="626fb-118">To install saved help files, run the `Update-Help` cmdlet.</span></span> <span data-ttu-id="626fb-119">その **SourcePath** パラメーターを追加して、ヘルプファイルを保存したフォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="626fb-119">Add its **SourcePath** parameter to specify the folder in which you saved the Help files.</span></span>

<span data-ttu-id="626fb-120">パラメーターを指定しない場合、コマンドは、 `Save-Help` セッション内のすべてのモジュールの最新のヘルプと、 **PSModulePath** 環境変数に示されている場所にコンピューターにインストールされているモジュールの最新のヘルプをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="626fb-120">Without parameters, a `Save-Help` command downloads the newest help for all modules in the session and for modules that are installed on the computer in a location listed in the **PSModulePath** environment variable.</span></span> <span data-ttu-id="626fb-121">この操作により、更新可能なヘルプをサポートしていないモジュールは警告なしにスキップされます。</span><span class="sxs-lookup"><span data-stu-id="626fb-121">This action skips modules that do not support Updatable Help without warning.</span></span>

<span data-ttu-id="626fb-122">コマンドレットでは、 `Save-Help` 対象フォルダー内のヘルプファイルのバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="626fb-122">The `Save-Help` cmdlet checks the version of any help files in the destination folder.</span></span> <span data-ttu-id="626fb-123">新しいヘルプファイルが使用可能な場合、このコマンドレットは、インターネットから最新のヘルプファイルをダウンロードし、フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="626fb-123">If newer help files are available, this cmdlet downloads the newest help files from the Internet, and then saves them in the folder.</span></span> <span data-ttu-id="626fb-124">`Save-Help`コマンドレットはコマンドレットと同じように動作し `Update-Help` ますが、ダウンロードされたキャビネット (.cab) ファイルを保存し、コンピューターにインストールするのではなく、ダウンロードしたキャビネット (.cab) ファイルを保存する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="626fb-124">The `Save-Help` cmdlet works just like the `Update-Help` cmdlet, except that it saves the downloaded cabinet (.cab) files, instead of extracting the help files from the cabinet files and installing them on the computer.</span></span>

<span data-ttu-id="626fb-125">保存されたモジュール用ヘルプはそれぞれ、UI カルチャごとに、ヘルプ情報 (HelpInfo XML) ファイル 1 つと、ヘルプ ファイルのキャビネット (.cab) ファイル 1 つで構成されます。</span><span class="sxs-lookup"><span data-stu-id="626fb-125">The saved help for each module consists of one help information (HelpInfo XML) file and one cabinet (.cab) file for the help files each UI culture.</span></span> <span data-ttu-id="626fb-126">キャビネットファイルからヘルプファイルを抽出する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="626fb-126">You do not have to extract the help files from the cabinet file.</span></span> <span data-ttu-id="626fb-127">`Update-Help`コマンドレットは、ヘルプファイルを抽出し、XML の安全性を検証した後、モジュールフォルダーの言語固有のサブフォルダーにヘルプファイルとヘルプ情報ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="626fb-127">The `Update-Help` cmdlet extracts the help files, validates the XML for safety, and then installs the help files and the help information file in a language-specific subfolder of the module folder.</span></span>

<span data-ttu-id="626fb-128">PowerShell のインストールフォルダー () にモジュールのヘルプファイルを保存するに `$pshome\Modules` は、[管理者として実行] オプションを使用して powershell を起動します。</span><span class="sxs-lookup"><span data-stu-id="626fb-128">To save the help files for modules in the PowerShell installation folder (`$pshome\Modules`), start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="626fb-129">これらのモジュールのヘルプ ファイルをダウンロードするには、そのコンピューターの Administrators グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="626fb-129">You must be a member of the Administrators group on the computer to download the help files for these modules.</span></span>

<span data-ttu-id="626fb-130">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="626fb-130">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="626fb-131">例</span><span class="sxs-lookup"><span data-stu-id="626fb-131">EXAMPLES</span></span>

### <span data-ttu-id="626fb-132">例 1: DhcpServer モジュールのヘルプを保存する</span><span class="sxs-lookup"><span data-stu-id="626fb-132">Example 1: Save the help for the DhcpServer module</span></span>

```powershell
# Option 1: Run Invoke-Command to get the PSModuleInfo object for the remote DHCP Server module,
# save the PSModuleInfo object in the variable $m, and then run Save-Help.

$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock { Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 2: Open a PSSession--targeted at the remote computer that is running the DhcpServer
# module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$s = New-PSSession -ComputerName "RemoteServer"
$m = Get-Module -PSSession $s -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 3: Open a CIM session--targeted at the remote computer that is running the DhcpServer
# module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$c = New-CimSession -ComputerName "RemoteServer"
$m = Get-Module -CimSession $c -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"
```

<span data-ttu-id="626fb-133">この例では、を使用し `Save-Help` て、ローカルコンピューターに **DhcpServer** モジュールまたは DHCP サーバーの役割をインストールせずに、インターネットに接続されたクライアントコンピューターから **DhcpServer** モジュールのヘルプを保存する3つの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="626fb-133">This example shows three different ways to use `Save-Help` to save the help for the **DhcpServer** module from an Internet-connected client computer, without installing the **DhcpServer** module or the DHCP Server role on the local computer.</span></span>

### <span data-ttu-id="626fb-134">例 2: DhcpServer モジュールのヘルプをインストールする</span><span class="sxs-lookup"><span data-stu-id="626fb-134">Example 2: Install help for the DhcpServer module</span></span>

```powershell
# First, run Export-CliXml to export the PSModuleInfo object to a shared folder or to removable media.

$m = Get-Module -Name "DhcpServer" -ListAvailable
Export-CliXml -Path "E:\UsbFlashDrive\DhcpModule.xml" -InputObject $m

# Next, transport the removable media to a computer that has Internet access, and then import the
# PSModuleInfo object with Import-CliXml. Run Save-Help to save the Help for the imported DhcpServer
# module PSModuleInfo object.

$deserialized_m = Import-CliXml "E:\UsbFlashDrive\DhcpModule.xml"
Save-Help -Module $deserialized_m -DestinationPath "E:\UsbFlashDrive\SavedHelp"

# Finally, transport the removable media back to the computer that does not have network access, and
# then install the help by running Update-Help.

Update-Help -Module DhcpServer -SourcePath "E:\UsbFlashDrive\SavedHelp"
```

<span data-ttu-id="626fb-135">この例では、例1でインターネットにアクセスできないコンピューターの **DhcpServer** モジュールのヘルプをインストールする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="626fb-135">This example shows how to install help that you saved in Example 1 for the **DhcpServer** module on a computer that does not have Internet access.</span></span>

### <span data-ttu-id="626fb-136">例 3: すべてのモジュールのヘルプを保存する</span><span class="sxs-lookup"><span data-stu-id="626fb-136">Example 3: Save help for all modules</span></span>

```powershell
Save-Help -DestinationPath "\\Server01\FileShare01"
```

<span data-ttu-id="626fb-137">このコマンドは、ローカル コンピューター上の Windows に設定された UI カルチャに該当するすべてのモジュールの最新のヘルプ ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="626fb-137">This command downloads the newest help files for all modules in the UI culture set for Windows on the local computer.</span></span> <span data-ttu-id="626fb-138">ヘルプファイルはフォルダーに保存され `\\Server01\Fileshare01` ます。</span><span class="sxs-lookup"><span data-stu-id="626fb-138">It saves the help files in the `\\Server01\Fileshare01` folder.</span></span>

### <span data-ttu-id="626fb-139">例 4: コンピューターのモジュールのヘルプを保存する</span><span class="sxs-lookup"><span data-stu-id="626fb-139">Example 4: Save help for a module on the computer</span></span>

```powershell
Save-Help -Module ServerManager -DestinationPath "\\Server01\FileShare01" -Credential Domain01/Admin01
```

<span data-ttu-id="626fb-140">このコマンドは、 **ServerManager** モジュールの最新のヘルプファイルをダウンロードし、フォルダーに保存し `\\Server01\Fileshare01` ます。</span><span class="sxs-lookup"><span data-stu-id="626fb-140">This command downloads the newest help files for the **ServerManager** module, and then saves them in the `\\Server01\Fileshare01` folder.</span></span>

<span data-ttu-id="626fb-141">モジュールをコンピューターにインストールする際、モジュールが現在のセッションにインポートされていない場合でも、モジュール名を **Module** パラメーターの値として入力できます。</span><span class="sxs-lookup"><span data-stu-id="626fb-141">When a module is installed on the computer, you can type the module name as the value of the **Module** parameter, even if the module is not imported into the current session.</span></span>

<span data-ttu-id="626fb-142">このコマンドは、**Credential** パラメーターを使用して、ファイル共有への書き込みアクセス許可を持つユーザーの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="626fb-142">The command uses the **Credential** parameter to supply the credentials of a user who has permission to write to the file share.</span></span>

### <span data-ttu-id="626fb-143">例 5: 別のコンピューターにモジュールのヘルプを保存する</span><span class="sxs-lookup"><span data-stu-id="626fb-143">Example 5: Save help for a module on a different computer</span></span>

```powershell
Invoke-Command -ComputerName Server02 {Get-Module -Name CustomSQL -ListAvailable} | Save-Help -DestinationPath \\Server01\FileShare01 -Credential Domain01\Admin01
```

<span data-ttu-id="626fb-144">これらのコマンドは、 **Customsql** モジュールの最新のヘルプファイルをダウンロードし、フォルダーに保存し `\\Server01\Fileshare01` ます。</span><span class="sxs-lookup"><span data-stu-id="626fb-144">These commands download the newest help files for the **CustomSQL** module and save them in the `\\Server01\Fileshare01` folder.</span></span>

<span data-ttu-id="626fb-145">**Customsql** モジュールがコンピューターにインストールされていないため、このシーケンスには、 `Invoke-Command` Server02 コンピューターから customsql モジュールのモジュールオブジェクトを取得し、そのモジュールオブジェクトをコマンドレットにパイプするコマンドが含まれてい `Save-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="626fb-145">Because the **CustomSQL** module is not installed on the computer, the sequence includes an `Invoke-Command` command that gets the module object for the CustomSQL module from the Server02 computer and then pipes the module object to the `Save-Help` cmdlet.</span></span>

<span data-ttu-id="626fb-146">コンピューターにモジュールがインストールされていない場合、には `Save-Help` モジュールオブジェクトが必要です。これには、最新のヘルプファイルの場所に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="626fb-146">When a module is not installed on the computer, `Save-Help` needs the module object, which includes information about the location of the newest help files.</span></span>

### <span data-ttu-id="626fb-147">例 6: モジュールのヘルプを複数の言語で保存する</span><span class="sxs-lookup"><span data-stu-id="626fb-147">Example 6: Save help for a module in multiple languages</span></span>

```powershell
Save-Help -Module Microsoft.PowerShell* -UICulture de-DE, en-US, fr-FR, ja-JP -DestinationPath "D:\Help"
```

<span data-ttu-id="626fb-148">このコマンドは、4つの異なる UI カルチャの PowerShell コアモジュールのヘルプを保存します。</span><span class="sxs-lookup"><span data-stu-id="626fb-148">This command saves help for the PowerShell Core modules in four different UI cultures.</span></span> <span data-ttu-id="626fb-149">これらのロケールの言語パックは、コンピューターにインストールされている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="626fb-149">The language packs for these locales do not have to be installed on the computer.</span></span>

<span data-ttu-id="626fb-150">`Save-Help` では、モジュールの所有者が翻訳されたファイルをインターネットで使用できるようにする場合にのみ、さまざまな UI カルチャのモジュールのヘルプファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="626fb-150">`Save-Help` can download help files for modules in different UI cultures only when the module owner makes the translated files available on the Internet.</span></span>

### <span data-ttu-id="626fb-151">例 7: 1 日に複数回ヘルプを保存する</span><span class="sxs-lookup"><span data-stu-id="626fb-151">Example 7: Save help more than one time each day</span></span>

```powershell
Save-Help -Force -DestinationPath "\\Server3\AdminShare\Help"
```

<span data-ttu-id="626fb-152">このコマンドは、コンピューターにインストールされているすべてのモジュールのヘルプを保存します。</span><span class="sxs-lookup"><span data-stu-id="626fb-152">This command saves help for all modules that are installed on the computer.</span></span> <span data-ttu-id="626fb-153">このコマンドは、 コマンド `Save-Help` レットが24時間ごとに複数回ダウンロードできないようにするルールを上書きする Force パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="626fb-153">The command specifies the **Force** parameter to override the rule that prevents the `Save-Help` cmdlet from downloading help more than once in each 24-hour period.</span></span>

<span data-ttu-id="626fb-154">**Force** パラメーターは、1 GB の制限もオーバーライドし、バージョンのチェックを回避します。</span><span class="sxs-lookup"><span data-stu-id="626fb-154">The **Force** parameter also overrides the 1 GB restriction and circumvents version checking.</span></span>
<span data-ttu-id="626fb-155">そのため、対象のフォルダーのバージョンよりも前のバージョンであっても、ファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="626fb-155">Therefore, you can download files even if the version is not later than the version in the destination folder.</span></span>

<span data-ttu-id="626fb-156">コマンドは、コマンドレットを使用して、 `Save-Help` 指定したフォルダーにヘルプファイルをダウンロードして保存します。</span><span class="sxs-lookup"><span data-stu-id="626fb-156">The command uses the `Save-Help` cmdlet to download and save the help files to the specified folder.</span></span>
<span data-ttu-id="626fb-157">**Force** パラメーターは、1日に複数回コマンドを実行する必要がある場合に必要です `Save-Help` 。</span><span class="sxs-lookup"><span data-stu-id="626fb-157">The **Force** parameter is required when you have to run a `Save-Help` command more than one time each day.</span></span>

## <span data-ttu-id="626fb-158">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="626fb-158">PARAMETERS</span></span>

### <span data-ttu-id="626fb-159">-Credential</span><span class="sxs-lookup"><span data-stu-id="626fb-159">-Credential</span></span>

<span data-ttu-id="626fb-160">ユーザー資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="626fb-160">Specifies a user credential.</span></span> <span data-ttu-id="626fb-161">このコマンドレットは、 **DestinationPath** パラメーターで指定したファイルシステムの場所にアクセスする権限を持つユーザーの資格情報を使用して、コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="626fb-161">This cmdlet runs the command by using credentials of a user who has permission to access the file system location specified by the **DestinationPath** parameter.</span></span> <span data-ttu-id="626fb-162">このパラメーターは、コマンドで **DestinationPath** パラメーターまたは **LiteralPath** パラメーターが使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="626fb-162">This parameter is valid only when the **DestinationPath** or **LiteralPath** parameter is used in the command.</span></span>

<span data-ttu-id="626fb-163">このパラメーターを使用すると `Save-Help` 、リモートコンピューターで **DestinationPath** パラメーターを使用するコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="626fb-163">This parameter enables you to run `Save-Help` commands that use the **DestinationPath** parameter on remote computers.</span></span> <span data-ttu-id="626fb-164">明示的な資格情報を指定することにより、リモートコンピューターでコマンドを実行し、アクセス拒否エラーが発生しないか、CredSSP 認証を使用して資格情報を委任することなく、3台目のコンピューター上のファイル共有にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="626fb-164">By providing explicit credentials, you can run the command on a remote computer and access a file share on a third computer without encountering an access denied error or using CredSSP authentication to delegate credentials.</span></span>

<span data-ttu-id="626fb-165">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="626fb-165">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="626fb-166">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="626fb-166">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="626fb-167">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="626fb-167">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="626fb-168">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="626fb-168">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="626fb-169">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="626fb-169">-DestinationPath</span></span>

<span data-ttu-id="626fb-170">ヘルプファイルを保存するフォルダーのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="626fb-170">Specifies the path of the folder in which the help files are saved.</span></span> <span data-ttu-id="626fb-171">ファイル名やファイル名拡張子を指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="626fb-171">Do not specify a file name or file name extension.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="626fb-172">-Force</span><span class="sxs-lookup"><span data-stu-id="626fb-172">-Force</span></span>

<span data-ttu-id="626fb-173">このコマンドレットが1日に1回の制限に従っていないことを示し、バージョンチェックをスキップし、1 GB の制限を超えるファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="626fb-173">Indicates that this cmdlet does not follow the once-per-day limitation, skips version checking, and downloads files that exceed the 1 GB limit.</span></span>

<span data-ttu-id="626fb-174">このパラメーターを指定しない場合、各 `Save-Help` モジュールに対して24時間ごとに1つのコマンドのみが許可されます。ダウンロードはモジュールごとに 1 GB の非圧縮コンテンツに制限され、モジュールのヘルプファイルはコンピューター上のファイルよりも新しい場合にのみインストールされます。</span><span class="sxs-lookup"><span data-stu-id="626fb-174">Without this parameter, only one `Save-Help` command for each module is permitted in each 24-hour period, downloads are limited to 1 GB of uncompressed content per module, and help files for a module are installed only when they are newer than the files on the computer.</span></span>

<span data-ttu-id="626fb-175">1日に1回の制限により、ヘルプファイルをホストするサーバーが保護され、PowerShell プロファイルにコマンドを追加できるようになり `Save-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="626fb-175">The once-per-day limit protects the servers that host the help files, and makes it practical for you to add a `Save-Help` command to your PowerShell profile.</span></span>

<span data-ttu-id="626fb-176">**Force** パラメーターを指定せずに複数の ui カルチャのモジュールのヘルプを保存するには、次のように、すべての ui カルチャを同じコマンドに含めます。`Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`</span><span class="sxs-lookup"><span data-stu-id="626fb-176">To save help for a module in multiple UI cultures without the **Force** parameter, include all UI cultures in the same command, such as: `Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`</span></span>

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

### <span data-ttu-id="626fb-177">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="626fb-177">-FullyQualifiedModule</span></span>

<span data-ttu-id="626fb-178">**Modul特定** のオブジェクトの形式で指定された名前を持つモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="626fb-178">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span> <span data-ttu-id="626fb-179">「 [Modulの認識コンストラクター (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_)」の「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="626fb-179">See the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="626fb-180">たとえば、 **FullyQualifiedModule** パラメーターは、次のいずれかの形式で指定されたモジュール名を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="626fb-180">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in either of these formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="626fb-181">**ModuleName** と **ModuleVersion** は必須ですが、**Guid** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="626fb-181">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span> <span data-ttu-id="626fb-182">**モジュール** パラメーターと同じコマンドで **FullyQualifiedModule** パラメーターを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="626fb-182">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="626fb-183">2つのパラメーターは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="626fb-183">the two parameters are mutually exclusive.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="626fb-184">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="626fb-184">-LiteralPath</span></span>

<span data-ttu-id="626fb-185">コピー先フォルダーのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="626fb-185">Specifies a path of the destination folder.</span></span> <span data-ttu-id="626fb-186">**DestinationPath** パラメーターの値とは異なり、 **LiteralPath** パラメーターの値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="626fb-186">Unlike the value of the **DestinationPath** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="626fb-187">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="626fb-187">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="626fb-188">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="626fb-188">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="626fb-189">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="626fb-189">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="626fb-190">-モジュール</span><span class="sxs-lookup"><span data-stu-id="626fb-190">-Module</span></span>

<span data-ttu-id="626fb-191">このコマンドレットがヘルプをダウンロードするモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="626fb-191">Specifies modules for which this cmdlet downloads help.</span></span> <span data-ttu-id="626fb-192">1つ以上のモジュール名または名前のパターンを、コンマ区切りのリスト、または各行に1つのモジュール名を持つファイルに入力します。</span><span class="sxs-lookup"><span data-stu-id="626fb-192">Enter one or more module names or name patters in a comma-separated list or in a file that has one module name on each line.</span></span> <span data-ttu-id="626fb-193">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="626fb-193">Wildcard characters are permitted.</span></span> <span data-ttu-id="626fb-194">パイプを使用して、モジュールオブジェクトをコマンドレットからにパイプすることもでき `Get-Module` `Save-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="626fb-194">You can also pipe module objects from the `Get-Module` cmdlet to `Save-Help`.</span></span>

<span data-ttu-id="626fb-195">既定では、は `Save-Help` 更新可能なヘルプをサポートし、 **PSModulePath** 環境変数に示されている場所にローカルコンピューターにインストールされているすべてのモジュールのヘルプをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="626fb-195">By default, `Save-Help` downloads help for all modules that support Updatable Help and are installed on the local computer in a location listed in the **PSModulePath** environment variable.</span></span>

<span data-ttu-id="626fb-196">コンピューターにインストールされていないモジュールのヘルプを保存するには、 `Get-Module` リモートコンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="626fb-196">To save help for modules that are not installed on the computer, run a `Get-Module` command on a remote computer.</span></span> <span data-ttu-id="626fb-197">次に、結果として得られるモジュールオブジェクトをコマンドレットにパイプするか、モジュール `Save-Help` オブジェクトを **モジュール** または **InputObject** パラメーターの値として送信します。</span><span class="sxs-lookup"><span data-stu-id="626fb-197">Then pipe the resulting module objects to the `Save-Help` cmdlet or submit the module objects as the value of the **Module** or **InputObject** parameters.</span></span>

<span data-ttu-id="626fb-198">指定したモジュールがコンピューターにインストールされている場合は、モジュール名またはモジュール オブジェクトを入力できます。</span><span class="sxs-lookup"><span data-stu-id="626fb-198">If the module that you specify is installed on the computer, you can enter the module name or a module object.</span></span> <span data-ttu-id="626fb-199">モジュールがコンピューターにインストールされていない場合は、コマンドレットによって返されるようなモジュールオブジェクトを入力する必要があり `Get-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="626fb-199">If the module is not installed on the computer, you must enter a module object, such as one returned by the `Get-Module` cmdlet.</span></span>

<span data-ttu-id="626fb-200">コマンドレットの **module** パラメーターは、 `Save-Help` モジュールファイルまたはモジュールマニフェストファイルの完全なパスを受け入れません。</span><span class="sxs-lookup"><span data-stu-id="626fb-200">The **Module** parameter of the `Save-Help` cmdlet does not accept the full path of a module file or module manifest file.</span></span> <span data-ttu-id="626fb-201">**PSModulePath** の場所にないモジュールのヘルプを保存するには、コマンドを実行する前に、現在のセッションにモジュールをインポートし `Save-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="626fb-201">To save help for a module that is not in a **PSModulePath** location, import the module into the current session before you run the `Save-Help` command.</span></span>

<span data-ttu-id="626fb-202">"\*" (すべて) の値は、コンピューターにインストールされているすべてのモジュールのヘルプを更新しようとします。</span><span class="sxs-lookup"><span data-stu-id="626fb-202">A value of "\*" (all) attempts to update help for all modules that are installed on the computer.</span></span>
<span data-ttu-id="626fb-203">これには、更新可能なヘルプをサポートしていないモジュールも含まれます。</span><span class="sxs-lookup"><span data-stu-id="626fb-203">This includes modules that do not support Updatable Help.</span></span> <span data-ttu-id="626fb-204">この値は、更新可能なヘルプをサポートしていないモジュールがコマンドによって検出された場合にエラーを生成することがあります。</span><span class="sxs-lookup"><span data-stu-id="626fb-204">This value might generate errors when the command encounters modules that do not support Updatable Help.</span></span>

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="626fb-205">-UICulture</span><span class="sxs-lookup"><span data-stu-id="626fb-205">-UICulture</span></span>

<span data-ttu-id="626fb-206">このコマンドレットが更新されたヘルプファイルを取得する UI カルチャの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="626fb-206">Specifies UI culture values for which this cmdlet gets updated help files.</span></span> <span data-ttu-id="626fb-207">1つまたは複数の言語コードを入力し `es-ES` ます。たとえば、カルチャオブジェクトを含む変数や、またはコマンドなどのカルチャオブジェクトを取得するコマンドを入力し `Get-Culture` `Get-UICulture` ます。</span><span class="sxs-lookup"><span data-stu-id="626fb-207">Enter one or more language codes, such as `es-ES`, a variable that contains culture objects, or a command that gets culture objects, such as a `Get-Culture` or `Get-UICulture` command.</span></span>

<span data-ttu-id="626fb-208">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="626fb-208">Wildcard characters are not permitted.</span></span> <span data-ttu-id="626fb-209">"De" などの部分言語コードを指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="626fb-209">Do not specify a partial language code, such as "de".</span></span>

<span data-ttu-id="626fb-210">既定で `Save-Help` は、は、Windows またはそのフォールバックカルチャに設定されている UI カルチャのヘルプファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="626fb-210">By default, `Save-Help` gets help files in the UI culture set for Windows or its fallback culture.</span></span>
<span data-ttu-id="626fb-211">**UICulture** パラメーターを指定すると、は、 `Save-Help` フォールバックカルチャではなく、指定された UI カルチャに対してのみヘルプを検索します。</span><span class="sxs-lookup"><span data-stu-id="626fb-211">If you specify the **UICulture** parameter, `Save-Help` looks for help only for the specified UI culture, not in any fallback culture.</span></span>

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: Current UI culture
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="626fb-212">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="626fb-212">-UseDefaultCredentials</span></span>

<span data-ttu-id="626fb-213">このコマンドレットが、web ダウンロードなどのコマンドを、現在のユーザーの資格情報を使用して実行することを示します。</span><span class="sxs-lookup"><span data-stu-id="626fb-213">Indicates that this cmdlet runs the command, including the web download, with the credentials of the current user.</span></span> <span data-ttu-id="626fb-214">既定では、コマンドは明示的な資格情報がない状態で実行されます。</span><span class="sxs-lookup"><span data-stu-id="626fb-214">By default, the command runs without explicit credentials.</span></span>

<span data-ttu-id="626fb-215">このパラメーターは、Web ダウンロードが、NTLM、Negotiate、または Kerberos ベース認証を使用する場合に限り有効です。</span><span class="sxs-lookup"><span data-stu-id="626fb-215">This parameter is effective only when the web download uses NTLM, negotiate, or Kerberos-based authentication.</span></span>

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

### <span data-ttu-id="626fb-216">-スコープ</span><span class="sxs-lookup"><span data-stu-id="626fb-216">-Scope</span></span>

<span data-ttu-id="626fb-217">このパラメーターは、このコマンドレットでは何も行いません。</span><span class="sxs-lookup"><span data-stu-id="626fb-217">This paramater does nothing in this cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.UpdateHelpScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="626fb-218">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="626fb-218">CommonParameters</span></span>

<span data-ttu-id="626fb-219">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="626fb-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="626fb-220">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="626fb-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="626fb-221">入力</span><span class="sxs-lookup"><span data-stu-id="626fb-221">INPUTS</span></span>

### <span data-ttu-id="626fb-222">PSModuleInfo (システム管理)</span><span class="sxs-lookup"><span data-stu-id="626fb-222">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="626fb-223">パイプを使用して、モジュールオブジェクトを `Get-Module` コマンドレットからの **module** パラメーターに渡し `Save-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="626fb-223">You can pipe a module object from the `Get-Module` cmdlet to the **Module** parameter of `Save-Help`.</span></span>

## <span data-ttu-id="626fb-224">出力</span><span class="sxs-lookup"><span data-stu-id="626fb-224">OUTPUTS</span></span>

### <span data-ttu-id="626fb-225">なし</span><span class="sxs-lookup"><span data-stu-id="626fb-225">None</span></span>

<span data-ttu-id="626fb-226">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="626fb-226">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="626fb-227">注</span><span class="sxs-lookup"><span data-stu-id="626fb-227">NOTES</span></span>

- <span data-ttu-id="626fb-228">モジュールのヘルプを [$pshome] \ [モジュール] フォルダーに保存するには、[管理者として実行] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="626fb-228">To save help for modules in the $pshome\Modules folder, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="626fb-229">コンピューターの Administrators グループのメンバーだけが、$pshome \ modules フォルダー内のモジュールのヘルプをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="626fb-229">Only members of the Administrators group on the computer can download help for modules in the $pshome\Modules folder.</span></span>
- <span data-ttu-id="626fb-230">保存されたモジュール用ヘルプはそれぞれ、UI カルチャごとに、ヘルプ情報 (HelpInfo XML) ファイル 1 つと、ヘルプ ファイルのキャビネット (.cab) ファイル 1 つで構成されます。</span><span class="sxs-lookup"><span data-stu-id="626fb-230">The saved help for each module consists of one help information (HelpInfo XML) file and one cabinet (.cab) file for the help files each UI culture.</span></span> <span data-ttu-id="626fb-231">キャビネットファイルからヘルプファイルを抽出する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="626fb-231">You do not have to extract the help files from the cabinet file.</span></span> <span data-ttu-id="626fb-232">コマンドレットにより、 `Update-Help` ヘルプファイルが抽出され、XML が検証された後、モジュールフォルダーの言語固有のサブフォルダーにヘルプファイルとヘルプ情報ファイルがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="626fb-232">The `Update-Help` cmdlet extracts the help files, validates the XML, and then installs the help files and the help information file in a language-specific subfolder of the module folder.</span></span>
- <span data-ttu-id="626fb-233">コマンドレットでは、 `Save-Help` コンピューターにインストールされていないモジュールのヘルプを保存できます。</span><span class="sxs-lookup"><span data-stu-id="626fb-233">The `Save-Help` cmdlet can save help for modules that are not installed on the computer.</span></span> <span data-ttu-id="626fb-234">ただし、ヘルプファイルはモジュールフォルダーにインストールされるため、 `Update-Help` コマンドレットでは、コンピューターにインストールされているモジュールに対してのみ更新されたヘルプファイルをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="626fb-234">However, because help files are installed in the module folder, the `Update-Help` cmdlet can install updated help file only for modules that are installed on the computer.</span></span>
- <span data-ttu-id="626fb-235">に `Save-Help` よって、モジュールの更新されたヘルプファイルが見つからない場合、または指定された言語で更新されたヘルプファイルが見つからない場合は、エラーメッセージを表示せずに、警告なしで続行されます。</span><span class="sxs-lookup"><span data-stu-id="626fb-235">If `Save-Help` cannot find updated help files for a module, or cannot find updated help files in the specified language, it continues silently without displaying an error message.</span></span> <span data-ttu-id="626fb-236">コマンドによって保存されたファイルを確認するには、 **Verbose** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="626fb-236">To see which files were saved by the command, specify the **Verbose** parameter.</span></span>
- <span data-ttu-id="626fb-237">モジュールは、更新可能なヘルプの最小単位です。</span><span class="sxs-lookup"><span data-stu-id="626fb-237">Modules are the smallest unit of updatable help.</span></span> <span data-ttu-id="626fb-238">特定のコマンドレットのヘルプは保存できません。モジュール内のすべてのコマンドレットに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="626fb-238">You cannot save help for a particular cmdlet, only for all cmdlets in module.</span></span> <span data-ttu-id="626fb-239">特定のコマンドレットを含むモジュールを見つけるには、 **ModuleName** プロパティをコマンドレットと共に使用します。次に例を示します。 `Get-Command``(Get-Command \<cmdlet-name\>).ModuleName`</span><span class="sxs-lookup"><span data-stu-id="626fb-239">To find the module that contains a particular cmdlet, use the **ModuleName** property together with the `Get-Command` cmdlet, for example, `(Get-Command \<cmdlet-name\>).ModuleName`</span></span>
- <span data-ttu-id="626fb-240">`Save-Help` では、すべてのモジュールと PowerShell Core スナップインがサポートされています。その他のスナップインはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="626fb-240">`Save-Help` supports all modules and the PowerShell Core snap-ins. It does not support any other snap-ins.</span></span>
- <span data-ttu-id="626fb-241">`Update-Help`およびコマンドレットは、次のポートを使用して `Save-Help` ヘルプファイルをダウンロードします。 HTTP の場合はポート80、HTTPS の場合はポート443を使用します。</span><span class="sxs-lookup"><span data-stu-id="626fb-241">The `Update-Help` and `Save-Help` cmdlets use the following ports to download help files: Port 80 for HTTP and port 443 for HTTPS.</span></span>
- <span data-ttu-id="626fb-242">`Update-Help`および `Save-Help` コマンドレットは、Windows Preinstallation Environment (Windows PE) ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="626fb-242">The `Update-Help` and `Save-Help` cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="626fb-243">関連リンク</span><span class="sxs-lookup"><span data-stu-id="626fb-243">RELATED LINKS</span></span>

[<span data-ttu-id="626fb-244">Get-Help</span><span class="sxs-lookup"><span data-stu-id="626fb-244">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="626fb-245">Get-Module</span><span class="sxs-lookup"><span data-stu-id="626fb-245">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="626fb-246">Update-Help</span><span class="sxs-lookup"><span data-stu-id="626fb-246">Update-Help</span></span>](Update-Help.md)
