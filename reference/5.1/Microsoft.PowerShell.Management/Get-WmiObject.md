---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmiObject
ms.openlocfilehash: ed759ff3d0dd35cd55f9dac5a2d76e36eac4dc6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215392"
---
# <span data-ttu-id="471de-103">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="471de-103">Get-WmiObject</span></span>

## <span data-ttu-id="471de-104">概要</span><span class="sxs-lookup"><span data-stu-id="471de-104">SYNOPSIS</span></span>
<span data-ttu-id="471de-105">Windows Management Instrumentation (WMI) クラスのインスタンスまたは使用可能なクラスに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="471de-105">Gets instances of Windows Management Instrumentation (WMI) classes or information about the available classes.</span></span>

## <span data-ttu-id="471de-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="471de-106">SYNTAX</span></span>

### <span data-ttu-id="471de-107">query (既定値)</span><span class="sxs-lookup"><span data-stu-id="471de-107">query (Default)</span></span>

```
Get-WmiObject [-Class] <String> [[-Property] <String[]>] [-Filter <String>] [-Amended] [-DirectRead]
 [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="471de-108">list</span><span class="sxs-lookup"><span data-stu-id="471de-108">list</span></span>

```
Get-WmiObject [[-Class] <String>] [-Recurse] [-Amended] [-List] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="471de-109">WQLQuery</span><span class="sxs-lookup"><span data-stu-id="471de-109">WQLQuery</span></span>

```
Get-WmiObject [-Amended] [-DirectRead] -Query <String> [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="471de-110">class</span><span class="sxs-lookup"><span data-stu-id="471de-110">class</span></span>

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="471de-111">path</span><span class="sxs-lookup"><span data-stu-id="471de-111">path</span></span>

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

## <span data-ttu-id="471de-112">Description</span><span class="sxs-lookup"><span data-stu-id="471de-112">DESCRIPTION</span></span>

<span data-ttu-id="471de-113">PowerShell 3.0 以降では、このコマンドレットはに置き換えられてい `Get-CimInstance` ます。</span><span class="sxs-lookup"><span data-stu-id="471de-113">Starting in PowerShell 3.0, this cmdlet has been superseded by `Get-CimInstance`.</span></span>

<span data-ttu-id="471de-114">この `Get-WmiObject` コマンドレットは、wmi クラスのインスタンス、または使用可能な wmi クラスに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="471de-114">The `Get-WmiObject` cmdlet gets instances of WMI classes or information about the available WMI classes.</span></span> <span data-ttu-id="471de-115">リモート コンピューターを指定するには、 **ComputerName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="471de-115">To specify a remote computer, use the **ComputerName** parameter.</span></span> <span data-ttu-id="471de-116">**List** パラメーターを指定すると、指定された名前空間内で使用可能な WMI クラスに関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="471de-116">If the **List** parameter is specified, the cmdlet gets information about the WMI classes that are available in a specified namespace.</span></span> <span data-ttu-id="471de-117">**Query** パラメーターを指定すると、WMI Query Language (WQL) ステートメントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="471de-117">If the **Query** parameter is specified, the cmdlet runs a WMI query language (WQL) statement.</span></span>

<span data-ttu-id="471de-118">`Get-WmiObject`コマンドレットは、リモート操作を実行するために Windows PowerShell リモート処理を使用しません。</span><span class="sxs-lookup"><span data-stu-id="471de-118">The `Get-WmiObject` cmdlet does not use Windows PowerShell remoting to perform remote operations.</span></span>
<span data-ttu-id="471de-119">**ComputerName** `Get-WmiObject` コンピューターが windows powershell リモート処理の要件を満たしていない場合や、windows powershell のリモート処理用に構成されていない場合でも、コマンドレットの ComputerName パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="471de-119">You can use the **ComputerName** parameter of the `Get-WmiObject` cmdlet even if your computer does not meet the requirements for Windows PowerShell remoting or is not configured for remoting in Windows PowerShell.</span></span>

<span data-ttu-id="471de-120">Windows PowerShell 3.0 以降では、を返すオブジェクトの **__Server** プロパティには、 `Get-WmiObject` **PSComputerName** エイリアスがあります。</span><span class="sxs-lookup"><span data-stu-id="471de-120">Beginning in Windows PowerShell 3.0, the **__Server** property of the object that `Get-WmiObject` returns has a **PSComputerName** alias.</span></span> <span data-ttu-id="471de-121">これにより、ソース コンピューター名を出力およびレポートに簡単に含められるようになりました。</span><span class="sxs-lookup"><span data-stu-id="471de-121">This makes it easier to include the source computer name in output and reports.</span></span>

## <span data-ttu-id="471de-122">例</span><span class="sxs-lookup"><span data-stu-id="471de-122">EXAMPLES</span></span>

### <span data-ttu-id="471de-123">例 1: ローカルコンピューター上のプロセスを取得する</span><span class="sxs-lookup"><span data-stu-id="471de-123">Example 1: Get processes on the local computer</span></span>

<span data-ttu-id="471de-124">この例では、ローカルコンピューター上のプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="471de-124">This example get the processes on the local computer.</span></span>

```powershell
Get-WmiObject -Class Win32_Process
```

### <span data-ttu-id="471de-125">例 2: リモートコンピューター上のサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="471de-125">Example 2: Gets services on a remote computer</span></span>

<span data-ttu-id="471de-126">この例では、リモートコンピューター上のサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="471de-126">This example gets the services on a remote computer.</span></span> <span data-ttu-id="471de-127">**ComputerName** パラメーターは、リモートコンピューターの IP アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="471de-127">The **ComputerName** parameter specifies the IP address of a remote computer.</span></span> <span data-ttu-id="471de-128">既定では、現在のユーザーアカウントは、リモートコンピューターの **Administrators** グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="471de-128">By default, the current user account must be a member of the **Administrators** group on the remote computer.</span></span>

```powershell
Get-WmiObject -Class Win32_Service -ComputerName 10.1.4.62
```

### <span data-ttu-id="471de-129">例 3: ローカルコンピューターのルートまたは既定の名前空間で WMI クラスを取得する</span><span class="sxs-lookup"><span data-stu-id="471de-129">Example 3: Get WMI classes in the root or default namespace of the local computer</span></span>

<span data-ttu-id="471de-130">この例では、ローカルコンピューターのルートまたは既定の名前空間にある WMI クラスを取得します。</span><span class="sxs-lookup"><span data-stu-id="471de-130">This example gets the WMI classes in the root or default namespace of the local computer.</span></span>

```powershell
Get-WmiObject -Namespace "root/default" -List
```

### <span data-ttu-id="471de-131">例 4: 複数のコンピューター上の名前付きサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="471de-131">Example 4: Get a named service on multiple computers</span></span>

<span data-ttu-id="471de-132">この例では、 **ComputerName** パラメーターの値によって指定されたコンピューター上の WinRM サービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="471de-132">This example gets the WinRM service on the computers specified by the value of the **ComputerName** parameter.</span></span>

```powershell
Get-WmiObject -Query "select * from win32_service where name='WinRM'" -ComputerName Server01, Server02 |
  Format-List -Property PSComputerName, Name, ExitCode, Name, ProcessID, StartMode, State, Status
```

```Output
PSComputerName : SERVER01
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 844
StartMode      : Auto
State          : Running
Status         : OK

PSComputerName : SERVER02
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 932
StartMode      : Auto
State          : Running
Status         : OK
```

<span data-ttu-id="471de-133">出力はパイプライン演算子 (|) によって `Format-List` コマンドレットに送られ、 **PSComputerName** プロパティが既定の出力に追加されます。</span><span class="sxs-lookup"><span data-stu-id="471de-133">A pipeline operator (|) sends the output to the `Format-List` cmdlet, which adds the **PSComputerName** property to the default output.</span></span> <span data-ttu-id="471de-134">**PSComputerName** は、が返すオブジェクトの **__Server** プロパティのエイリアスです `Get-WmiObject` 。</span><span class="sxs-lookup"><span data-stu-id="471de-134">**PSComputerName** is an alias of the **__Server** property of the objects that `Get-WmiObject` returns.</span></span> <span data-ttu-id="471de-135">このエイリアスは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="471de-135">This alias was introduced in PowerShell 3.0.</span></span>

### <span data-ttu-id="471de-136">例 5: リモートコンピューター上のサービスを停止する</span><span class="sxs-lookup"><span data-stu-id="471de-136">Example 5: Stop a service on a remote computer</span></span>

<span data-ttu-id="471de-137">この例では、リモートコンピューター上の WinRM サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="471de-137">This example stops the WinRM service on a remote computer.</span></span> <span data-ttu-id="471de-138">`Get-WmiObject` Server01 上の WinRM サービスオブジェクトのインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="471de-138">`Get-WmiObject` gets the instance of the WinRM service object on Server01.</span></span> <span data-ttu-id="471de-139">次に、そのオブジェクトの **Win32_Service** WMI クラスの **stopservice** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="471de-139">Then, it invokes the **StopService** method of the **Win32_Service** WMI class on that object.</span></span>

```powershell
(Get-WmiObject -Class Win32_Service -Filter "name='WinRM'" -ComputerName Server01).StopService()
```

<span data-ttu-id="471de-140">これは、コマンドレットを使用することと同じです `Stop-Service` 。</span><span class="sxs-lookup"><span data-stu-id="471de-140">This is equivalent to using the `Stop-Service` cmdlet.</span></span>

### <span data-ttu-id="471de-141">例 6: ローカルコンピューターの BIOS を取得する</span><span class="sxs-lookup"><span data-stu-id="471de-141">Example 6: Get the BIOS on the local computer</span></span>

<span data-ttu-id="471de-142">この例では、ローカルコンピューターから BIOS 情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="471de-142">This example gets the BIOS information from the local computer.</span></span> <span data-ttu-id="471de-143">コマンドレットの **Property** パラメーターを使用して、 `Format-List` 返されたオブジェクトのすべてのプロパティを一覧に表示します。</span><span class="sxs-lookup"><span data-stu-id="471de-143">The **Property** parameter of the `Format-List` cmdlet is used to display all properties of the returned object in a list.</span></span> <span data-ttu-id="471de-144">既定では、構成ファイルで定義されているプロパティのサブセットのみ `Types.ps1xml` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="471de-144">By default, only the subset of properties defined in the `Types.ps1xml` configuration file are displayed.</span></span>

```powershell
Get-WmiObject -Class Win32_Bios | Format-List -Property *
```

```Output
Status                : OK
Name                  : Phoenix ROM BIOS PLUS Version 1.10 A05
Caption               : Phoenix ROM BIOS PLUS Version 1.10 A05
SMBIOSPresent         : True
__GENUS               : 2
__CLASS               : Win32_BIOS
__SUPERCLASS          : CIM_BIOSElement
__DYNASTY             : CIM_ManagedSystemElement
__RELPATH             : Win32_BIOS.Name="Phoenix ROM BIOS PLUS Version 1.10
__PROPERTY_COUNT      : 27
__DERIVATION          : {CIM_BIOSElement, CIM_SoftwareElement, CIM_LogicalElement,
__SERVER              : Server01
__NAMESPACE           : root\cimv2
__PATH                : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
BiosCharacteristics   : {7, 9, 10, 11...}
BIOSVersion           : {DELL   - 15, Phoenix ROM BIOS PLUS Version 1.10 A05}
BuildNumber           :
CodeSet               :
CurrentLanguage       : en|US|iso8859-1
Description           : Phoenix ROM BIOS PLUS Version 1.10 A05
IdentificationCode    :
InstallableLanguages  : 1
InstallDate           :
LanguageEdition       :
ListOfLanguages       : {en|US|iso8859-1}
Manufacturer          : Dell Inc.
OtherTargetOS         :
PrimaryBIOS           : True
ReleaseDate           : 20101103000000.000000+000
SerialNumber          : 8VDM9P1
SMBIOSBIOSVersion     : A05
SMBIOSMajorVersion    : 2
SMBIOSMinorVersion    : 6
SoftwareElementID     : Phoenix ROM BIOS PLUS Version 1.10 A05
SoftwareElementState  : 3
TargetOperatingSystem : 0
Version               : DELL   - 15
Scope                 : System.Management.ManagementScope
Path                  : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
Options               : System.Management.ObjectGetOptions
ClassPath             : \\JUNE-PC\root\cimv2:Win32_BIOS
Properties            : {BiosCharacteristics, BIOSVersion, BuildNumber, Caption...}
SystemProperties      : {__GENUS, __CLASS, __SUPERCLASS, __DYNASTY...}
Qualifiers            : {dynamic, Locale, provider, UUID}
Site                  :
Container             :
```

### <span data-ttu-id="471de-145">例 7: リモートコンピューター上のサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="471de-145">Example 7: Get the services on a remote computer</span></span>

<span data-ttu-id="471de-146">この例では、コマンドレットの **Credential** パラメーターを使用して、 `Get-WmiObject` リモートコンピューター上のサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="471de-146">This example uses the **Credential** parameter of the `Get-WmiObject` cmdlet to get the services on a remote computer.</span></span> <span data-ttu-id="471de-147">**Credential** パラメーターの値は、ユーザー アカウント名です。</span><span class="sxs-lookup"><span data-stu-id="471de-147">The value of the **Credential** parameter is a user account name.</span></span> <span data-ttu-id="471de-148">ユーザーにパスワードの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="471de-148">The user is prompted for a password.</span></span>

```powershell
Get-WmiObject Win32_Service -Credential FABRIKAM\administrator -ComputerName Fabrikam
```

> [!NOTE]
> <span data-ttu-id="471de-149">ローカルコンピューターをターゲットにしている場合は、資格情報を使用できません。</span><span class="sxs-lookup"><span data-stu-id="471de-149">Credentials cannot be used when targeting the local computer.</span></span>

## <span data-ttu-id="471de-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="471de-150">PARAMETERS</span></span>

### <span data-ttu-id="471de-151">-修正済み</span><span class="sxs-lookup"><span data-stu-id="471de-151">-Amended</span></span>

<span data-ttu-id="471de-152">変更された情報を WMI から返されるオブジェクトに含めるかどうかを指定する値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="471de-152">Gets or sets a value that indicates whether the objects that are returned from WMI should contain amended information.</span></span> <span data-ttu-id="471de-153">通常、変更された情報は、オブジェクトやプロパティの説明など、WMI オブジェクトに付属するローカライズ可能な情報です。</span><span class="sxs-lookup"><span data-stu-id="471de-153">Typically, amended information is localizable information, such as object and property descriptions, that is attached to the WMI object.</span></span>

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

### <span data-ttu-id="471de-154">-AsJob</span><span class="sxs-lookup"><span data-stu-id="471de-154">-AsJob</span></span>

<span data-ttu-id="471de-155">バックグラウンド ジョブとしてコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="471de-155">Runs the command as a background job.</span></span> <span data-ttu-id="471de-156">完了に時間のかかるコマンドを実行するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="471de-156">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="471de-157">**AsJob** パラメーターを使用すると、バックグラウンド ジョブを表すオブジェクトが返され、その後コマンド プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="471de-157">When you use the **AsJob** parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span> <span data-ttu-id="471de-158">ジョブが完了しても、引き続きセッションで作業できます。</span><span class="sxs-lookup"><span data-stu-id="471de-158">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="471de-159">`Get-WmiObject`がリモートコンピューターで使用されている場合、ジョブはローカルコンピューター上に作成され、リモートコンピューターからの結果は自動的にローカルコンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="471de-159">If `Get-WmiObject` is used on a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="471de-160">ジョブを管理するには、"Job" を含むコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="471de-160">To manage the job, use the cmdlets that contain the Job cmdlets.</span></span> <span data-ttu-id="471de-161">ジョブの結果を取得するには、`Receive-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="471de-161">To get the job results, use the `Receive-Job` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="471de-162">このパラメーターをリモート コンピューターで使用するには、ローカル コンピューターおよびリモート コンピューターをリモート処理用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="471de-162">To use this parameter with remote computers, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="471de-163">さらに、Windows Vista 以降のバージョンの Windows では、[管理者として実行] を使用して Windows PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="471de-163">Additionally, you must start Windows PowerShell by using the "Run as administrator" option in Windows Vista and later versions of Windows.</span></span> <span data-ttu-id="471de-164">詳細については、「[about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="471de-164">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="471de-165">Windows PowerShell のバックグラウンドジョブの詳細については、「 [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md) 」および「 [about_Remote_Jobs](../Microsoft.PowerShell.Core/about/about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="471de-165">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/about/about_Remote_Jobs.md).</span></span>

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

### <span data-ttu-id="471de-166">-認証</span><span class="sxs-lookup"><span data-stu-id="471de-166">-Authentication</span></span>

<span data-ttu-id="471de-167">WMI 接続に使用する認証レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="471de-167">Specifies the authentication level to be used with the WMI connection.</span></span>
<span data-ttu-id="471de-168">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="471de-168">Valid values are:</span></span>

- <span data-ttu-id="471de-169">-1: Unchanged</span><span class="sxs-lookup"><span data-stu-id="471de-169">-1: Unchanged</span></span>
- <span data-ttu-id="471de-170">0: Default</span><span class="sxs-lookup"><span data-stu-id="471de-170">0: Default</span></span>
- <span data-ttu-id="471de-171">1: None (認証は行われません)</span><span class="sxs-lookup"><span data-stu-id="471de-171">1: None (No authentication in performed.)</span></span>
- <span data-ttu-id="471de-172">2: Connect (認証は、クライアントとアプリケーションの関係が確立されるときのみ実行されます)</span><span class="sxs-lookup"><span data-stu-id="471de-172">2: Connect (Authentication is performed only when the client establishes a relationship with the application.)</span></span>
- <span data-ttu-id="471de-173">3: Call (認証は、アプリケーションが要求を受信するときに各呼び出しの始めにだけ実行されます)</span><span class="sxs-lookup"><span data-stu-id="471de-173">3: Call (Authentication is performed only at the beginning of each call when the application receives the request.)</span></span>
- <span data-ttu-id="471de-174">4: Packet (認証はクライアントから受信されるすべてのデータで実行されます)</span><span class="sxs-lookup"><span data-stu-id="471de-174">4: Packet (Authentication is performed on all the data that is received from the client.)</span></span>
- <span data-ttu-id="471de-175">5: PacketIntegrity (クライアントとアプリケーション間で転送されるすべてのデータが認証および検証されます)。</span><span class="sxs-lookup"><span data-stu-id="471de-175">5: PacketIntegrity (All the data that is transferred between the client and the application is authenticated and verified.)</span></span>
- <span data-ttu-id="471de-176">6: PacketPrivacy (他の認証レベルのプロパティが使用され、すべてのデータが暗号化されます)</span><span class="sxs-lookup"><span data-stu-id="471de-176">6: PacketPrivacy (The properties of the other authentication levels are used, and all the data is encrypted.)</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="471de-177">-Authority</span><span class="sxs-lookup"><span data-stu-id="471de-177">-Authority</span></span>

<span data-ttu-id="471de-178">WMI 接続の認証に使用する機関を指定します。</span><span class="sxs-lookup"><span data-stu-id="471de-178">Specifies the authority to use to authenticate the WMI connection.</span></span> <span data-ttu-id="471de-179">標準の NTLM 認証または Kerberos 認証を指定できます。</span><span class="sxs-lookup"><span data-stu-id="471de-179">You can specify standard NTLM or Kerberos authentication.</span></span> <span data-ttu-id="471de-180">NTLM を使用するには、authority 設定をに設定し `ntlmdomain:<DomainName>` ます。ここで、は `<DomainName>` 有効な ntlm ドメイン名を示します。</span><span class="sxs-lookup"><span data-stu-id="471de-180">To use NTLM, set the authority setting to `ntlmdomain:<DomainName>`, where `<DomainName>` identifies a valid NTLM domain name.</span></span> <span data-ttu-id="471de-181">Kerberos を使用するには、を指定し `kerberos:<DomainName>\<ServerName>` ます。</span><span class="sxs-lookup"><span data-stu-id="471de-181">To use Kerberos, specify `kerberos:<DomainName>\<ServerName>`.</span></span> <span data-ttu-id="471de-182">ローカル コンピューターへの接続時に認証設定を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="471de-182">You cannot include the authority setting when you connect to the local computer.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="471de-183">-クラス</span><span class="sxs-lookup"><span data-stu-id="471de-183">-Class</span></span>

<span data-ttu-id="471de-184">WMI クラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="471de-184">Specifies the name of a WMI class.</span></span> <span data-ttu-id="471de-185">このパラメーターを使用した場合は、WMI クラスのインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="471de-185">When this parameter is used, the cmdlet retrieves instances of the WMI class.</span></span>

```yaml
Type: System.String
Parameter Sets: query, list
Aliases: ClassName

Required: True (query), False (list)
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="471de-186">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="471de-186">-ComputerName</span></span>

<span data-ttu-id="471de-187">管理操作のターゲット コンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="471de-187">Specifies the target computer for the management operation.</span></span> <span data-ttu-id="471de-188">完全修飾ドメイン名 (FQDN)、NetBIOS 名、または IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="471de-188">Enter a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="471de-189">リモート コンピューターがローカル コンピューターとは異なるドメインにある場合は、完全修飾ドメイン名が必要です。</span><span class="sxs-lookup"><span data-stu-id="471de-189">When the remote computer is in a different domain than the local computer, the fully qualified domain name is required.</span></span>

<span data-ttu-id="471de-190">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="471de-190">The default is the local computer.</span></span> <span data-ttu-id="471de-191">コンピューター名の一覧などでローカル コンピューターを指定するには、「localhost」、ローカル コンピューター名、またはドット (.) を使用します。</span><span class="sxs-lookup"><span data-stu-id="471de-191">To specify the local computer, such as in a list of computer names, use "localhost", the local computer name, or a dot (.).</span></span>

<span data-ttu-id="471de-192">このパラメーターは、WS-Management を使用する Windows PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="471de-192">This parameter does not rely on Windows PowerShell remoting, which uses WS-Management.</span></span> <span data-ttu-id="471de-193">**ComputerName** `Get-WmiObject` コンピューターがリモートコマンド WS-Management 実行するように構成されていない場合でも、の ComputerName パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="471de-193">You can use the **ComputerName** parameter of `Get-WmiObject` even if your computer is not configured to run WS-Management remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="471de-194">-Credential</span><span class="sxs-lookup"><span data-stu-id="471de-194">-Credential</span></span>

<span data-ttu-id="471de-195">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="471de-195">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="471de-196">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="471de-196">The default is the current user.</span></span> <span data-ttu-id="471de-197">「User01」、「Domain01\user01」」、「」などのユーザー名を入力し User@Contoso.com ます。</span><span class="sxs-lookup"><span data-stu-id="471de-197">Type a user name, such as "User01", "Domain01\User01", or User@Contoso.com.</span></span> <span data-ttu-id="471de-198">または、  コマンドレットで返されるような `Get-Credential` オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="471de-198">Or, enter a **PSCredential** object, such as an object that is returned by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="471de-199">ユーザー名を入力すると、パスワードの入力を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="471de-199">When you type a user name, you are prompted for a password.</span></span> <span data-ttu-id="471de-200">ローカルコンピューターをターゲットにしている場合は、資格情報を使用できません。</span><span class="sxs-lookup"><span data-stu-id="471de-200">Credentials cannot be used when targeting the local computer.</span></span>

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

### <span data-ttu-id="471de-201">-DirectRead</span><span class="sxs-lookup"><span data-stu-id="471de-201">-DirectRead</span></span>

<span data-ttu-id="471de-202">基底クラスまたは派生クラスに関係なく、指定したクラスには WMI プロバイダーへの直接アクセスが必要かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="471de-202">Specifies whether direct access to the WMI provider is requested for the specified class without any regard to its base class or to its derived classes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: query, WQLQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="471de-203">-EnableAllPrivileges</span><span class="sxs-lookup"><span data-stu-id="471de-203">-EnableAllPrivileges</span></span>

<span data-ttu-id="471de-204">コマンドが WMI 呼び出しを実行する前に、現在のユーザーのすべての特権を有効にします。</span><span class="sxs-lookup"><span data-stu-id="471de-204">Enables all the privileges of the current user before the command makes the WMI call.</span></span>

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

### <span data-ttu-id="471de-205">-Filter</span><span class="sxs-lookup"><span data-stu-id="471de-205">-Filter</span></span>

<span data-ttu-id="471de-206">フィルターとして使用する **Where** 句を指定します。</span><span class="sxs-lookup"><span data-stu-id="471de-206">Specifies a **Where** clause to use as a filter.</span></span> <span data-ttu-id="471de-207">WMI Query Language (WQL) の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="471de-207">Uses the syntax of the WMI Query Language (WQL).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="471de-208">パラメーターの値には **Where** キーワードを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="471de-208">Do not include the **Where** keyword in the value of the parameter.</span></span> <span data-ttu-id="471de-209">たとえば、次のコマンドは、 **Where** キーワードを使用しないで、 **DeviceID** が "c:" の論理ディスクと名前が "WinRM" のサービスのみを返します。</span><span class="sxs-lookup"><span data-stu-id="471de-209">For example, the following commands return only the logical disks that have a **DeviceID** of 'c:' and services that have the name 'WinRM' without using the **Where** keyword.</span></span>

`Get-WmiObject Win32_LogicalDisk -filter "DeviceID = 'c:' "`

`Get-WmiObject win32_service -filter "name='WinRM'"`

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="471de-210">-偽装</span><span class="sxs-lookup"><span data-stu-id="471de-210">-Impersonation</span></span>

<span data-ttu-id="471de-211">使用する偽装レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="471de-211">Specifies the impersonation level to use.</span></span>

<span data-ttu-id="471de-212">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="471de-212">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="471de-213">0: Default。</span><span class="sxs-lookup"><span data-stu-id="471de-213">0: Default.</span></span> <span data-ttu-id="471de-214">既定の偽装レベルのローカルレジストリを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="471de-214">Reads the local registry for the default impersonation level.</span></span> <span data-ttu-id="471de-215">既定値は、通常、 **Impersonate** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="471de-215">The default is usually set to **Impersonate** .</span></span>
- <span data-ttu-id="471de-216">1: Anonymous。</span><span class="sxs-lookup"><span data-stu-id="471de-216">1: Anonymous.</span></span> <span data-ttu-id="471de-217">呼び出し元の資格情報は非表示になります。</span><span class="sxs-lookup"><span data-stu-id="471de-217">Hides the credentials of the caller.</span></span>
- <span data-ttu-id="471de-218">2: Identify。</span><span class="sxs-lookup"><span data-stu-id="471de-218">2: Identify.</span></span> <span data-ttu-id="471de-219">オブジェクトによる呼び出し元の資格情報のクエリが許可されます。</span><span class="sxs-lookup"><span data-stu-id="471de-219">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="471de-220">3: Impersonate。</span><span class="sxs-lookup"><span data-stu-id="471de-220">3: Impersonate.</span></span> <span data-ttu-id="471de-221">オブジェクトによる呼び出し元の資格情報の使用が許可されます。</span><span class="sxs-lookup"><span data-stu-id="471de-221">Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="471de-222">4: Delegate。</span><span class="sxs-lookup"><span data-stu-id="471de-222">4: Delegate.</span></span> <span data-ttu-id="471de-223">オブジェクトが呼び出し元の資格情報の使用を他のオブジェクトに許可できるようにします。</span><span class="sxs-lookup"><span data-stu-id="471de-223">Allows objects to permit other objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="471de-224">-List</span><span class="sxs-lookup"><span data-stu-id="471de-224">-List</span></span>

<span data-ttu-id="471de-225">**Namespace** パラメーターで指定された、WMI リポジトリ名前空間にある WMI クラスの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="471de-225">Gets the names of the WMI classes in the WMI repository namespace that is specified by the **Namespace** parameter.</span></span>

<span data-ttu-id="471de-226">**List** パラメーターを指定しても、 **Namespace** パラメーターを指定しない場合、では `Get-WmiObject` 既定で **Root\Cimv2** 名前空間が使用されます。</span><span class="sxs-lookup"><span data-stu-id="471de-226">If you specify the **List** parameter, but not the **Namespace** parameter, `Get-WmiObject` uses the **Root\Cimv2** namespace by default.</span></span> <span data-ttu-id="471de-227">このコマンドレットは、既定の名前空間を決定するために、レジストリキーの既定の **名前空間** レジストリエントリを使用しません `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WBEM\Scripting` 。</span><span class="sxs-lookup"><span data-stu-id="471de-227">This cmdlet does not use the **Default Namespace** registry entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WBEM\Scripting` registry key to determine the default namespace.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="471de-228">-ロケール</span><span class="sxs-lookup"><span data-stu-id="471de-228">-Locale</span></span>

<span data-ttu-id="471de-229">WMI オブジェクトの優先ロケールを指定します。</span><span class="sxs-lookup"><span data-stu-id="471de-229">Specifies the preferred locale for WMI objects.</span></span>
<span data-ttu-id="471de-230">値を MS_\<LCID\> 形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="471de-230">Enter a value in MS_\<LCID\> format.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="471de-231">-Namespace</span><span class="sxs-lookup"><span data-stu-id="471de-231">-Namespace</span></span>

<span data-ttu-id="471de-232">**Class** パラメーターと共に使用する場合、 **Namespace** パラメーターは、指定された WMI クラスがある WMI リポジトリ名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="471de-232">When used with the **Class** parameter, the **Namespace** parameter specifies the WMI repository namespace where the specified WMI class is located.</span></span> <span data-ttu-id="471de-233">**List** パラメーターと共に使用する場合は、WMI クラス情報を収集する名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="471de-233">When used with the **List** parameter, it specifies the namespace from which to gather WMI class information.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="471de-234">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="471de-234">-Property</span></span>

<span data-ttu-id="471de-235">このコマンドレットが情報を取得する WMI クラスのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="471de-235">Specifies the WMI class properties that this cmdlet gets information from.</span></span> <span data-ttu-id="471de-236">プロパティ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="471de-236">Enter the property names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: query
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="471de-237">-Query</span><span class="sxs-lookup"><span data-stu-id="471de-237">-Query</span></span>

<span data-ttu-id="471de-238">指定された WMI Query Language (WQL) のステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="471de-238">Runs the specified WMI Query Language (WQL) statement.</span></span> <span data-ttu-id="471de-239">このパラメーターは、イベント クエリをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="471de-239">This parameter does not support event queries.</span></span>

```yaml
Type: System.String
Parameter Sets: WQLQuery
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="471de-240">-再帰</span><span class="sxs-lookup"><span data-stu-id="471de-240">-Recurse</span></span>

<span data-ttu-id="471de-241">**Class** パラメーターで指定されたクラス名を現在の名前空間および他のすべての名前空間で検索します。</span><span class="sxs-lookup"><span data-stu-id="471de-241">Searches the current namespace and all other namespaces for the class name that is specified by the **Class** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="471de-242">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="471de-242">-ThrottleLimit</span></span>

<span data-ttu-id="471de-243">同時に実行できる WMI 操作の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="471de-243">Specifies the maximum number of WMI operations that can be executed simultaneously.</span></span> <span data-ttu-id="471de-244">このパラメーターは、 **AsJob** パラメーターがコマンドで使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="471de-244">This parameter is valid only when the **AsJob** parameter is used in the command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="471de-245">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="471de-245">CommonParameters</span></span>

<span data-ttu-id="471de-246">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="471de-246">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="471de-247">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="471de-247">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="471de-248">入力</span><span class="sxs-lookup"><span data-stu-id="471de-248">INPUTS</span></span>

### <span data-ttu-id="471de-249">なし</span><span class="sxs-lookup"><span data-stu-id="471de-249">None</span></span>

<span data-ttu-id="471de-250">入力をにパイプすることはできません `Get-WmiObject` 。</span><span class="sxs-lookup"><span data-stu-id="471de-250">You cannot pipe input to `Get-WmiObject`.</span></span>

## <span data-ttu-id="471de-251">出力</span><span class="sxs-lookup"><span data-stu-id="471de-251">OUTPUTS</span></span>

### <span data-ttu-id="471de-252">PSObject または system.servicemodel. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="471de-252">PSObject or System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="471de-253">**AsJob** パラメーターを使用すると、コマンドレットはジョブ オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="471de-253">When you use the **AsJob** parameter, the cmdlet returns a job object.</span></span> <span data-ttu-id="471de-254">それ以外の場合、 `Get-WmiObject` を返すオブジェクトは、 **Class** パラメーターの値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="471de-254">Otherwise, the object that `Get-WmiObject` returns depends on the value of the **Class** parameter.</span></span>

## <span data-ttu-id="471de-255">注</span><span class="sxs-lookup"><span data-stu-id="471de-255">NOTES</span></span>

<span data-ttu-id="471de-256">リモート コンピューターの WMI 情報にアクセスするには、リモート コンピューターのローカル管理者グループに属しているアカウントでこのコマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="471de-256">To access WMI information on a remote computer, the cmdlet must run under an account that is a member of the local administrators group on the remote computer.</span></span> <span data-ttu-id="471de-257">また、リモート リポジトリの WMI 名前空間に対する既定のアクセス制御を変更して、他のアカウントにアクセス権を許可する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="471de-257">Or, the default access control on the WMI namespace of the remote repository can be changed to give access rights to other accounts.</span></span>

<span data-ttu-id="471de-258">既定では、各 WMI クラスの一部のプロパティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="471de-258">Only some of the properties of each WMI class are displayed by default.</span></span> <span data-ttu-id="471de-259">各 WMI クラスで表示されるプロパティのセットは、構成ファイル Types.ps1xml で指定します。</span><span class="sxs-lookup"><span data-stu-id="471de-259">The set of properties that is displayed for each WMI class is specified in the Types.ps1xml configuration file.</span></span> <span data-ttu-id="471de-260">WMI オブジェクトのすべてのプロパティを取得するに `Get-Member` は、 `Format-List` コマンドレットまたはコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="471de-260">To get all properties of a WMI object, use the `Get-Member` or `Format-List` cmdlets.</span></span>

## <span data-ttu-id="471de-261">関連リンク</span><span class="sxs-lookup"><span data-stu-id="471de-261">RELATED LINKS</span></span>

[<span data-ttu-id="471de-262">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="471de-262">Invoke-WmiMethod</span></span>](Invoke-WmiMethod.md)

[<span data-ttu-id="471de-263">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="471de-263">Remove-WmiObject</span></span>](Remove-WmiObject.md)

[<span data-ttu-id="471de-264">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="471de-264">Set-WmiInstance</span></span>](Set-WmiInstance.md)

[<span data-ttu-id="471de-265">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="471de-265">Get-WSManInstance</span></span>](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[<span data-ttu-id="471de-266">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="471de-266">Invoke-WSManAction</span></span>](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[<span data-ttu-id="471de-267">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="471de-267">New-WSManInstance</span></span>](../Microsoft.WsMan.Management/New-WSManInstance.md)

[<span data-ttu-id="471de-268">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="471de-268">Remove-WSManInstance</span></span>](../Microsoft.WsMan.Management/Remove-WSManInstance.md)
