---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/get-wsmaninstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WSManInstance
ms.openlocfilehash: c60d17631d0603e4285c34b91dd0971e4e358af0
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224808"
---
# <span data-ttu-id="b1b4b-103">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b1b4b-103">Get-WSManInstance</span></span>

## <span data-ttu-id="b1b4b-104">概要</span><span class="sxs-lookup"><span data-stu-id="b1b4b-104">SYNOPSIS</span></span>
<span data-ttu-id="b1b4b-105">リソース URI で指定されたリソース インスタンスの管理情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-105">Displays management information for a resource instance specified by a Resource URI.</span></span>

## <span data-ttu-id="b1b4b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b1b4b-106">SYNTAX</span></span>

### <span data-ttu-id="b1b4b-107">GetInstance (既定値)</span><span class="sxs-lookup"><span data-stu-id="b1b4b-107">GetInstance (Default)</span></span>

```
Get-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-ConnectionURI <Uri>] [-Dialect <Uri>]
 [-Fragment <String>] [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet <Hashtable>]
 [-SessionOption <SessionOption>] [-UseSSL] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="b1b4b-108">[列挙]</span><span class="sxs-lookup"><span data-stu-id="b1b4b-108">Enumerate</span></span>

```
Get-WSManInstance [-ApplicationName <String>] [-BasePropertiesOnly] [-ComputerName <String>]
 [-ConnectionURI <Uri>] [-Dialect <Uri>] [-Enumerate] [-Filter <String>] [-OptionSet <Hashtable>]
 [-Port <Int32>] [-Associations] [-ResourceURI] <Uri> [-ReturnType <String>] [-SessionOption <SessionOption>]
 [-Shallow] [-UseSSL] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="b1b4b-109">Description</span><span class="sxs-lookup"><span data-stu-id="b1b4b-109">DESCRIPTION</span></span>
<span data-ttu-id="b1b4b-110">**Get wsmaninstance** コマンドレットは、リソース UNIFORM RESOURCE IDENTIFIER (URI) によって指定された管理リソースのインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-110">The **Get-WSManInstance** cmdlet retrieves an instance of a management resource that is specified by a resource Uniform Resource Identifier (URI).</span></span>
<span data-ttu-id="b1b4b-111">取得される情報は、複雑な XML 情報セット (オブジェクトまたは単純な値) にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-111">The information that is retrieved can be a complex XML information set, which is an object, or a simple value.</span></span>
<span data-ttu-id="b1b4b-112">このコマンドレットは、標準の Web Services for Management (WS-MANAGEMENT) **Get** コマンドに相当します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-112">This cmdlet is the equivalent to the standard Web Services for Management (WS-Management) **Get** command.</span></span>

<span data-ttu-id="b1b4b-113">このコマンドレットは、WS-Management の接続/トランスポート層を使用して、情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-113">This cmdlet uses the WS-Management connection/transport layer to retrieve information.</span></span>

## <span data-ttu-id="b1b4b-114">例</span><span class="sxs-lookup"><span data-stu-id="b1b4b-114">EXAMPLES</span></span>

### <span data-ttu-id="b1b4b-115">例 1: WMI からすべての情報を取得する</span><span class="sxs-lookup"><span data-stu-id="b1b4b-115">Example 1: Get all information from WMI</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI wmicimv2/win32_service -SelectorSet @{name="winrm"} -ComputerName "Server01"
xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_Service_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : true
Caption                 : Windows Remote Management (WS-Management)
CheckPoint              : 0
CreationClassName       : Win32_Service
Description             : Windows Remote Management (WinRM) service implements the WS-Management protocol for remote
management. WS-Management is a standard web services protocol used for remote software and
hardware management. The WinRM service listens on the network for WS-Management requests
and processes them. The WinRM Service needs to be configured with a listener using the
winrm.cmd command line tool or through Group Policy in order for it to listen over the
network. The WinRM service provides access to WMI data and enables event collection. Event
collection and subscription to events require that the service is running. WinRM messages
use HTTP and HTTPS as transports. The WinRM service does not depend on IIS but is
preconfigured to share a port with IIS on the same computer.  The WinRM service reserves the
/wsman URL prefix. To prevent conflicts with IIS, administrators should ensure that any
websites hosted on IIS do not use the /wsman URL prefix.
DesktopInteract         : false
DisplayName             : Windows Remote Management (WS-Management)
ErrorControl            : Normal
ExitCode                : 0
InstallDate             : InstallDate
Name                    : winrm
PathName                : C:\Windows\System32\svchost.exe -k NetworkService
ProcessId               : 948
ServiceSpecificExitCode : 0
ServiceType             : Share Process
Started                 : true
StartMode               : Auto
StartName               : NT AUTHORITY\NetworkService
State                   : Running
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : SERVER01
TagId                   : 0
WaitHint                : 0
```

<span data-ttu-id="b1b4b-116">このコマンドは、Windows Management Instrumentation (WMI) がリモート server01 コンピューター上の **WinRM** サービスについて公開しているすべての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-116">This command returns all of the information that Windows Management Instrumentation (WMI) exposes about the **WinRM** service on the remote server01 computer.</span></span>

### <span data-ttu-id="b1b4b-117">例 2: スプーラサービスの状態を取得する</span><span class="sxs-lookup"><span data-stu-id="b1b4b-117">Example 2: Get the status of the Spooler service</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI wmicimv2/win32_service -SelectorSet @{name="spooler"} -Fragment Status -ComputerName "Server01"
XmlFragment=OK
```

<span data-ttu-id="b1b4b-118">このコマンドは、リモート server01 コンピューター上の **スプーラ** サービスの状態のみを返します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-118">This command returns only the status of the **Spooler** service on the remote server01 computer.</span></span>

### <span data-ttu-id="b1b4b-119">例 3: すべてのサービスのエンドポイント参照を取得する</span><span class="sxs-lookup"><span data-stu-id="b1b4b-119">Example 3: Get endpoint references for all services</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -ResourceURI wmicimv2/win32_service -ReturnType EPR
xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_Service_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : false
Caption                 : Visual Studio 2008 Remote Debugger
CheckPoint              : 0
CreationClassName       : Win32_Service
Description             : Allows members of the Administrators group to remotely debug server applications using Visual
Studio 2008. Use the Visual Studio 2008 Remote Debugging Configuration Wizard to enable this
service.
DesktopInteract         : false
DisplayName             : Visual Studio 2008 Remote Debugger
ErrorControl            : Ignore
ExitCode                : 1077
InstallDate             : InstallDate
Name                    : msvsmon90
PathName                : "C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\Remote Debugger\x86\msvsmon.exe" /service msvsmon90
ProcessId               : 0
ServiceSpecificExitCode : 0
ServiceType             : Own Process
Started                 : false
StartMode               : Disabled
StartName               : LocalSystem
State                   : Stopped
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : COMPUTER01
TagId                   : 0
WaitHint                : 0
...
```

<span data-ttu-id="b1b4b-120">このコマンドは、ローカル コンピューター上のすべてのサービスに対応するエンドポイント参照を返します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-120">This command returns endpoint references that correspond to all the services on the local computer.</span></span>

### <span data-ttu-id="b1b4b-121">例 4: 指定した条件を満たすサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="b1b4b-121">Example 4: Get services that meet specified criteria</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -ResourceURI wmicimv2/* -Filter "select * from win32_service where StartMode = 'Auto' and State = 'Stopped'" -ComputerName "Server01"
xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_Service_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : false
Caption                 : Windows Media Center Service Launcher
CheckPoint              : 0
CreationClassName       : Win32_Service
Description             : Starts Windows Media Center Scheduler and Windows Media Center Receiver services
at startup if TV is enabled within Windows Media Center.
DesktopInteract         : false
DisplayName             : Windows Media Center Service Launcher
ErrorControl            : Ignore
ExitCode                : 0
InstallDate             : InstallDate
Name                    : ehstart
PathName                : C:\Windows\system32\svchost.exe -k LocalServiceNoNetwork
ProcessId               : 0
ServiceSpecificExitCode : 0
ServiceType             : Share Process
Started                 : false
StartMode               : Auto
StartName               : NT AUTHORITY\LocalService
State                   : Stopped
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : Server01
TagId                   : 0
WaitHint                : 0
...
```

<span data-ttu-id="b1b4b-122">このコマンドは、リモートの Server01 コンピューター上で、次の条件を満たすすべてのサービスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-122">This command lists all of the services that meet the following criteria on the remote Server01 computer:</span></span>

- <span data-ttu-id="b1b4b-123">サービスのスタートアップの種類は Automatic です。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-123">The startup type of the service is Automatic.</span></span>
- <span data-ttu-id="b1b4b-124">サービスが停止しています。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-124">The service is stopped.</span></span>

### <span data-ttu-id="b1b4b-125">例 5: ローカルコンピューターの条件に一致するリスナー構成を取得する</span><span class="sxs-lookup"><span data-stu-id="b1b4b-125">Example 5: Get listener configuration that matches criteria on the local computer</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI winrm/config/listener -SelectorSet @{Address="*";Transport="http"}
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 80
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {100.0.0.1, 123.123.123.123, ::1, 2001:4898:0:fff:0:5efe:123.123.123.123...}
```

<span data-ttu-id="b1b4b-126">このコマンドは、ローカル コンピューター上の、セレクター セットの条件と一致する WS-Management リスナーの構成を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-126">This command lists the WS-Management listener configuration on the local computer for the listener that matches the criteria in the selector set.</span></span>

### <span data-ttu-id="b1b4b-127">例 6: リモートコンピューターの条件に一致するリスナー構成を取得する</span><span class="sxs-lookup"><span data-stu-id="b1b4b-127">Example 6: Get listener configuration that matches criteria on a remote computer</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI winrm/config/listener -SelectorSet @{Address="*";Transport="http"} -ComputerName "Server01"
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 80
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {100.0.0.1, 123.123.123.124, ::1, 2001:4898:0:fff:0:5efe:123.123.123.124...}
```

<span data-ttu-id="b1b4b-128">このコマンドは、server01 リモート コンピューター上の、セレクター セットの条件と一致する WS-Management リスナーの構成を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-128">This command lists the WS-Management listener configuration on the remote server01 computer for the listener that matches the criteria in the selector set.</span></span>

### <span data-ttu-id="b1b4b-129">例 7: 指定したインスタンスに関連付けられているインスタンスを取得する</span><span class="sxs-lookup"><span data-stu-id="b1b4b-129">Example 7: Get associated instances related to a specified instance</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -Dialect Association -Filter "{Object=win32_service?name=winrm}" -ResourceURI wmicimv2/*
xsi                       : http://www.w3.org/2001/XMLSchema-instance
p                         : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_ComputerSystem
cim                       : http://schemas.dmtf.org/wbem/wscim/1/common
type                      : p:Win32_ComputerSystem_Type
lang                      : en-US
AdminPasswordStatus       : 1
AutomaticManagedPagefile  : true
AutomaticResetBootOption  : true
AutomaticResetCapability  : true
BootOptionOnLimit         : BootOptionOnLimit
BootOptionOnWatchDog      : BootOptionOnWatchDog
BootROMSupported          : true
BootupState               : Normal boot
Caption                   : SERVER01
ChassisBootupState        : 3
CreationClassName         : Win32_ComputerSystem
CurrentTimeZone           : -480
DaylightInEffect          : false
Description               : AT/AT COMPATIBLE
DNSHostName               : server01
Domain                    : site01.corp.fabrikam.com
DomainRole                : 1
EnableDaylightSavingsTime : true
FrontPanelResetStatus     : 2
InfraredSupported         : false
InstallDate               : InstallDate
KeyboardPasswordStatus    : 2
LastLoadInfo              : LastLoadInfo
Manufacturer              : Dell Inc.
Model                     : OptiPlex 745
Name                      : SERVER01
NameFormat                : NameFormat
NetworkServerModeEnabled  : true
NumberOfLogicalProcessors : 2
NumberOfProcessors        : 1
OEMStringArray            : www.dell.com
PartOfDomain              : true
PauseAfterReset           : -1
PCSystemType              : 5
PowerManagementSupported  : PowerManagementSupported
PowerOnPasswordStatus     : 1
PowerState                : 0
PowerSupplyState          : 3
PrimaryOwnerContact       : PrimaryOwnerContact
PrimaryOwnerName          : testuser01
ResetCapability           : 1
ResetCount                : -1
ResetLimit                : -1
Roles                     : {LM_Workstation, LM_Server, SQLServer, NT}
Status                    : OK
SystemStartupDelay        : SystemStartupDelay
SystemStartupSetting      : SystemStartupSetting
SystemType                : X86-based PC
ThermalState              : 3
TotalPhysicalMemory       : 3217760256
UserName                  : FABRIKAM\testuser01
WakeUpType                : 6
Workgroup                 : Workgroup
xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_Service_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : false
Caption                 : Remote Procedure Call (RPC)
CheckPoint              : 0
CreationClassName       : Win32_Service
Description             : Serves as the endpoint mapper and COM Service Control Manager. If this service is stopped
or disabled, programs using COM or Remote Procedure Call (RPC) services will not function
properly.
DesktopInteract         : false
DisplayName             : Remote Procedure Call (RPC)
ErrorControl            : Normal
ExitCode                : 0
InstallDate             : InstallDate
Name                    : RpcSs
PathName                : C:\Windows\system32\svchost.exe -k rpcss
ProcessId               : 1100
ServiceSpecificExitCode : 0
ServiceType             : Share Process
Started                 : true
StartMode               : Auto
StartName               : NT AUTHORITY\NetworkService
State                   : Running
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : SERVER01
TagId                   : 0
WaitHint                : 0

xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_SystemDriver
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_SystemDriver_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : true
Caption                 : HTTP
CreationClassName       : Win32_SystemDriver
Description             : HTTP
DesktopInteract         : false
DisplayName             : HTTP
ErrorControl            : Normal
ExitCode                : 0
InstallDate             : InstallDate
Name                    : HTTP
PathName                : C:\Windows\system32\drivers\HTTP.sys
ServiceSpecificExitCode : 0
ServiceType             : Kernel Driver
Started                 : true
StartMode               : Manual
StartName               :
State                   : Running
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : SERVER01
TagId                   : 0
```

<span data-ttu-id="b1b4b-130">このコマンドは、指定されたインスタンス (winrm) に関連付けられているインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-130">This command gets the associated instances that are related to the specified instance (winrm).</span></span>

<span data-ttu-id="b1b4b-131">次の例に示すように、フィルターを二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-131">You must enclose the filter in quotation marks, as shown in the example.</span></span>

### <span data-ttu-id="b1b4b-132">例 8: 指定したインスタンスに関連する関連付けインスタンスを取得する</span><span class="sxs-lookup"><span data-stu-id="b1b4b-132">Example 8: Get association instances related to a specified instance</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -Dialect Association -Associations -Filter "{Object=win32_service?name=winrm}" -ResourceURI wmicimv2/*
```

<span data-ttu-id="b1b4b-133">このコマンドは、指定されたインスタンス (winrm) の関連付けインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-133">This command gets association instances that are related to the specified instance (winrm).</span></span>
<span data-ttu-id="b1b4b-134">*Dialect* 値は association *で、association パラメーターが* 使用されるため、このコマンドは関連付けられているインスタンスではなく関連付けインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-134">Because the *Dialect* value is association and the *Associations* parameter is used, this command returns association instances, not associated instances.</span></span>

<span data-ttu-id="b1b4b-135">次の例に示すように、フィルターを二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-135">You must enclose the filter in quotation marks, as shown in the example.</span></span>

## <span data-ttu-id="b1b4b-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b1b4b-136">PARAMETERS</span></span>

### <span data-ttu-id="b1b4b-137">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="b1b4b-137">-ApplicationName</span></span>
<span data-ttu-id="b1b4b-138">接続のアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-138">Specifies the application name in the connection.</span></span>
<span data-ttu-id="b1b4b-139">*ApplicationName* パラメーターの既定値は WSMAN です。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-139">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="b1b4b-140">リモート エンドポイントの完全な識別子は、次の形式です。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-140">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="b1b4b-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="b1b4b-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="b1b4b-142">例: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="b1b4b-142">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="b1b4b-143">セッションをホストするインターネット インフォメーション サービス (IIS) は、このエンドポイントで、指定されたアプリケーションに要求を転送します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-143">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="b1b4b-144">この WSMAN の既定の設定は、ほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-144">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="b1b4b-145">このパラメーターは、多くのコンピューターが PowerShell を実行する1台のコンピューターへのリモート接続を確立する場合に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-145">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="b1b4b-146">この場合、IIS は効率を上げるために WS-Management をホストします。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-146">In this case, IIS hosts WS-Management for efficiency.</span></span>

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

### <span data-ttu-id="b1b4b-147">-関連付け</span><span class="sxs-lookup"><span data-stu-id="b1b4b-147">-Associations</span></span>
<span data-ttu-id="b1b4b-148">このコマンドレットが関連付けられているインスタンスではなく、関連付けインスタンスを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-148">Indicates that this cmdlet gets association instances, not associated instances.</span></span>
<span data-ttu-id="b1b4b-149">このパラメーターは、 *Dialect* パラメーターの値が Association の場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-149">You can use this parameter only when the *Dialect* parameter has a value of Association.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enumerate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-150">-認証</span><span class="sxs-lookup"><span data-stu-id="b1b4b-150">-Authentication</span></span>
<span data-ttu-id="b1b4b-151">サーバーで使用される認証メカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-151">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="b1b4b-152">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-152">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b1b4b-153">基本。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-153">Basic.</span></span>
<span data-ttu-id="b1b4b-154">Basic は、ユーザー名およびパスワードがクリア テキストでサーバーまたはプロキシに送信されるスキームです。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-154">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="b1b4b-155">既定値。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-155">Default.</span></span>
<span data-ttu-id="b1b4b-156">WS-Management プロトコルによって実装されている認証方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-156">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="b1b4b-157">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-157">This is the default.</span></span>
- <span data-ttu-id="b1b4b-158">ダイジェスト。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-158">Digest.</span></span>
<span data-ttu-id="b1b4b-159">Digest は、サーバーで指定されたデータ文字列をチャレンジで使用するチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-159">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="b1b4b-160">Kerberos。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-160">Kerberos.</span></span>
<span data-ttu-id="b1b4b-161">クライアント コンピューターとサーバーが Kerberos 証明書を使用して相互に認証します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-161">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="b1b4b-162">Negotiate</span><span class="sxs-lookup"><span data-stu-id="b1b4b-162">Negotiate.</span></span>
<span data-ttu-id="b1b4b-163">Negotiate は、認証で使用するスキームを特定するために、サーバーまたはプロキシとネゴシエートするチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-163">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="b1b4b-164">たとえば、このパラメーター値を指定すると、Kerberos プロトコルと NTLM のどちらが使用されているかをネゴシエーションで判断できます。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-164">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="b1b4b-165">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="b1b4b-165">CredSSP.</span></span>
<span data-ttu-id="b1b4b-166">Credential Security Support Provider (CredSSP) 認証を使用して、ユーザーが資格情報を委任できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-166">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="b1b4b-167">このオプションは、1 台のリモート コンピューターで実行するが、他のリモート コンピューターからデータを収集するコマンドや、他のリモート コンピューターで追加のコマンドを実行するコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-167">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="b1b4b-168">注意: CredSSP は、ローカルコンピューターからリモートコンピューターにユーザーの資格情報を委任します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-168">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="b1b4b-169">そのため、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-169">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="b1b4b-170">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡された資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-170">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am
Accepted values: None, Default, Digest, Negotiate, Basic, Kerberos, ClientCertificate, Credssp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-171">-BasePropertiesOnly</span><span class="sxs-lookup"><span data-stu-id="b1b4b-171">-BasePropertiesOnly</span></span>
<span data-ttu-id="b1b4b-172">このコマンドレットが、 *ResourceURI* パラメーターで指定された基本クラスの一部であるプロパティだけを列挙することを示します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-172">Indicates that this cmdlet enumerates only the properties that are part of the base class that is specified by the *ResourceURI* parameter.</span></span>
<span data-ttu-id="b1b4b-173">このパラメーターは、 *簡易* パラメーターが指定されている場合には効果がありません。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-173">This parameter has no effect if the *Shallow* parameter is specified.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enumerate
Aliases: UBPO, Base

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-174">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="b1b4b-174">-CertificateThumbprint</span></span>
<span data-ttu-id="b1b4b-175">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-175">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="b1b4b-176">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-176">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="b1b4b-177">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-177">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="b1b4b-178">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-178">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="b1b4b-179">証明書の拇印を取得するには、PowerShell Cert: ドライブで Get-Item または Get-ChildItem コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-179">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="b1b4b-180">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="b1b4b-180">-ComputerName</span></span>
<span data-ttu-id="b1b4b-181">管理操作を実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-181">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="b1b4b-182">値には、完全修飾ドメイン名、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-182">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="b1b4b-183">ローカル コンピューターを指定するには、ローカル コンピューター名、localhost、またはドット (.) を使用します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-183">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="b1b4b-184">ローカル コンピューターは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-184">The local computer is the default.</span></span>
<span data-ttu-id="b1b4b-185">リモート コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-185">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="b1b4b-186">パイプを使用して、このパラメーターの値をコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-186">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-187">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="b1b4b-187">-ConnectionURI</span></span>
<span data-ttu-id="b1b4b-188">接続エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-188">Specifies the connection endpoint.</span></span>
<span data-ttu-id="b1b4b-189">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-189">The format of this string is as follows:</span></span>

<span data-ttu-id="b1b4b-190">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="b1b4b-190">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="b1b4b-191">次の文字列は、このパラメーターに対して正しく書式設定された値です。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-191">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="b1b4b-192">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-192">The URI must be fully qualified.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: CURI, CU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-193">-Credential</span><span class="sxs-lookup"><span data-stu-id="b1b4b-193">-Credential</span></span>
<span data-ttu-id="b1b4b-194">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-194">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="b1b4b-195">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-195">The default is the current user.</span></span>
<span data-ttu-id="b1b4b-196">User01、Domain01\user01」、などのユーザー名を入力し User@Domain.com ます。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-196">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="b1b4b-197">または、Get-Credential コマンドレットによって返されるような **PSCredential** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-197">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="b1b4b-198">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-198">When you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: cred, c

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-199">-言語</span><span class="sxs-lookup"><span data-stu-id="b1b4b-199">-Dialect</span></span>
<span data-ttu-id="b1b4b-200">フィルター述語で使用する言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-200">Specifies the dialect to use in the filter predicate.</span></span>
<span data-ttu-id="b1b4b-201">リモート サービスでサポートされている任意の言語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-201">This can be any dialect that is supported by the remote service.</span></span>
<span data-ttu-id="b1b4b-202">言語の URI には、次のエイリアスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-202">The following aliases can be used for the dialect URI:</span></span>

- <span data-ttu-id="b1b4b-203">WQL `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span><span class="sxs-lookup"><span data-stu-id="b1b4b-203">WQL `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span></span>
- <span data-ttu-id="b1b4b-204">選択肢 `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span><span class="sxs-lookup"><span data-stu-id="b1b4b-204">Selector `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span></span>
- <span data-ttu-id="b1b4b-205">づける `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span><span class="sxs-lookup"><span data-stu-id="b1b4b-205">Association `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-206">-列挙</span><span class="sxs-lookup"><span data-stu-id="b1b4b-206">-Enumerate</span></span>
<span data-ttu-id="b1b4b-207">このコマンドレットが管理リソースのすべてのインスタンスを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-207">Indicates that this cmdlet returns all of the instances of a management resource.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enumerate
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-208">-Filter</span><span class="sxs-lookup"><span data-stu-id="b1b4b-208">-Filter</span></span>
<span data-ttu-id="b1b4b-209">列挙体のフィルター式を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-209">Specifies the filter expression for the enumeration.</span></span>
<span data-ttu-id="b1b4b-210">このパラメーターを指定する場合は、 *Dialect* も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-210">If you specify this parameter, you must also specify *Dialect* .</span></span>

<span data-ttu-id="b1b4b-211">このパラメーターの有効な値は、 *dialect* で指定されている言語によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-211">The valid values of this parameter depend on the dialect that is specified in *Dialect* .</span></span>
<span data-ttu-id="b1b4b-212">たとえば、 *Dialect* が WQL の場合、 *Filter* パラメーターには文字列を含める必要があり、文字列には次のクエリのような有効な WQL クエリが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-212">For example, if *Dialect* is WQL, the *Filter* parameter must contain a string, and the string must contain a valid WQL query such as the following query:</span></span>

`"Select * from Win32_Service where State != Running"`

<span data-ttu-id="b1b4b-213">*Dialect* が Association の場合、 *filter* には文字列を含める必要があり、文字列には次のフィルターのような有効なフィルターが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-213">If *Dialect* is Association, *Filter* must contain a string, and the string must contain a valid filter, such as the following filter:</span></span>

`-filter:Object=EPR\[;AssociationClassName=AssocClassName\]\[;ResultClassName=ClassName\]\[;Role=RefPropertyName\]\[;ResultRole=RefPropertyName\]}`

```yaml
Type: System.String
Parameter Sets: Enumerate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-214">-Fragment</span><span class="sxs-lookup"><span data-stu-id="b1b4b-214">-Fragment</span></span>
<span data-ttu-id="b1b4b-215">指定された操作で更新または取得するインスタンス内のセクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-215">Specifies a section inside the instance that is to be updated or retrieved for the specified operation.</span></span>
<span data-ttu-id="b1b4b-216">たとえば、スプーラサービスの状態を取得するには、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-216">For example, to get the status of a spooler service, specify the following:</span></span>

`-Fragment Status`

```yaml
Type: System.String
Parameter Sets: GetInstance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-217">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="b1b4b-217">-OptionSet</span></span>
<span data-ttu-id="b1b4b-218">要求の性質を変更または調整するための一連のスイッチをサービスに指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-218">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="b1b4b-219">これらは、サービス固有であるため、コマンドラインシェルで使用されるスイッチに似ています。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-219">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="b1b4b-220">任意の数のオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-220">Any number of options can be specified.</span></span>

<span data-ttu-id="b1b4b-221">次の例では、a、b、および c パラメーターに値 1、2、および 3 を渡す構文を示します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-221">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: OS

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-222">-Port</span><span class="sxs-lookup"><span data-stu-id="b1b4b-222">-Port</span></span>
<span data-ttu-id="b1b4b-223">クライアントが WinRM サービスに接続するときに使用するポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-223">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="b1b4b-224">トランスポートが HTTP の場合、既定のポートは 80 です。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-224">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="b1b4b-225">トランスポートが HTTPS の場合、既定のポートは 443 です。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-225">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="b1b4b-226">HTTPS をトランスポートとして使用する場合は、 *ComputerName* パラメーターの値がサーバーの証明書共通名 (CN) と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-226">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="b1b4b-227">ただし、 *Sessionoption* パラメーターの一部として *skipcncheck* パラメーターを指定した場合、サーバーの証明書の共通名がサーバーのホスト名と一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-227">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="b1b4b-228">*Skipcncheck* パラメーターは、信頼されたコンピューターに対してのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-228">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="b1b4b-229">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="b1b4b-229">-ResourceURI</span></span>
<span data-ttu-id="b1b4b-230">リソースクラスまたはインスタンスの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-230">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="b1b4b-231">URI は、コンピューター上の特定の種類のリソース (ディスクやプロセスなど) を識別します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-231">The URI identifies a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="b1b4b-232">URI は、リソースのプレフィックスとパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-232">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="b1b4b-233">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-233">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: RURI

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-234">-ReturnType</span><span class="sxs-lookup"><span data-stu-id="b1b4b-234">-ReturnType</span></span>
<span data-ttu-id="b1b4b-235">返されるデータの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-235">Specifies the type of data to be returned.</span></span>
<span data-ttu-id="b1b4b-236">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-236">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b1b4b-237">Object</span><span class="sxs-lookup"><span data-stu-id="b1b4b-237">Object</span></span>
- <span data-ttu-id="b1b4b-238">EPR</span><span class="sxs-lookup"><span data-stu-id="b1b4b-238">EPR</span></span>
- <span data-ttu-id="b1b4b-239">ObjectAndEPR</span><span class="sxs-lookup"><span data-stu-id="b1b4b-239">ObjectAndEPR</span></span>

<span data-ttu-id="b1b4b-240">既定値は Object です。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-240">The default value is Object.</span></span>

<span data-ttu-id="b1b4b-241">オブジェクトを指定した場合、またはこのパラメーターを指定しなかった場合、このコマンドレットはオブジェクトのみを返します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-241">If you specify Object or do not specify this parameter, this cmdlet returns only objects.</span></span>
<span data-ttu-id="b1b4b-242">エンドポイント参照 (EPR) を指定すると、このコマンドレットはオブジェクトのエンドポイント参照のみを返します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-242">If you specify endpoint reference (EPR) this cmdlet returns only the endpoint references of the objects.</span></span>
<span data-ttu-id="b1b4b-243">エンドポイント参照には、インスタンスのリソース URI とセレクターに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-243">Endpoint references contain information about the resource URI and the selectors for the instance.</span></span>
<span data-ttu-id="b1b4b-244">ObjectAndEPR を指定した場合、このコマンドレットはオブジェクトとそれに関連付けられているエンドポイント参照の両方を返します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-244">If you specify ObjectAndEPR, this cmdlet returns both the object and its associated endpoint references.</span></span>

```yaml
Type: System.String
Parameter Sets: Enumerate
Aliases: RT
Accepted values: object, epr, objectandepr

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-245">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="b1b4b-245">-SelectorSet</span></span>
<span data-ttu-id="b1b4b-246">特定の管理リソース インスタンスの選択に使用する値のペアのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-246">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="b1b4b-247">*SelectorSet* パラメーターは、リソースの複数のインスタンスが存在する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-247">The *SelectorSet* parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="b1b4b-248">*SelectorSet* パラメーターの値は、ハッシュテーブルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-248">The value of the *SelectorSet* parameter must be a hash table.</span></span>

<span data-ttu-id="b1b4b-249">次の例では、このパラメーターの値を入力する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-249">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: GetInstance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-250">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="b1b4b-250">-SessionOption</span></span>
<span data-ttu-id="b1b4b-251">WS-Management セッションの拡張オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-251">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="b1b4b-252">New-WSManSessionOption コマンドレットを使用して作成する **Sessionoption** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-252">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="b1b4b-253">使用可能なオプションの詳細については、「」と入力 `Get-Help New-WSManSessionOption` してください。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-253">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

```yaml
Type: Microsoft.WSMan.Management.SessionOption
Parameter Sets: (All)
Aliases: SO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-254">-浅い</span><span class="sxs-lookup"><span data-stu-id="b1b4b-254">-Shallow</span></span>
<span data-ttu-id="b1b4b-255">このコマンドレットが、リソース URI で指定された基本クラスのインスタンスのみを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-255">Indicates that this cmdlet returns only instances of the base class that is specified in the resource URI.</span></span>
<span data-ttu-id="b1b4b-256">このパラメーターを指定しない場合、このコマンドレットは、URI およびそのすべての派生クラスに指定されている基本クラスのインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-256">If you do not specify this parameter,, this cmdlet returns instances of the base class that is specified in the URI and in all its derived classes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enumerate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-257">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="b1b4b-257">-UseSSL</span></span>
<span data-ttu-id="b1b4b-258">リモートコンピューターへの接続を確立するために Secure Sockets Layer (SSL) プロトコルを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-258">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="b1b4b-259">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-259">By default, SSL is not used.</span></span>

<span data-ttu-id="b1b4b-260">WS-Management は、ネットワークを介して転送されるすべての Windows PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-260">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="b1b4b-261">*UseSSL* パラメーターを使用すると、HTTP ではなく HTTPS の追加の保護を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-261">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="b1b4b-262">接続に使用するポートで SSL が使用できない場合、このパラメーターを指定すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-262">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SSL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4b-263">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1b4b-263">CommonParameters</span></span>
<span data-ttu-id="b1b4b-264">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-264">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b1b4b-265">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-265">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b1b4b-266">入力</span><span class="sxs-lookup"><span data-stu-id="b1b4b-266">INPUTS</span></span>

### <span data-ttu-id="b1b4b-267">なし</span><span class="sxs-lookup"><span data-stu-id="b1b4b-267">None</span></span>
<span data-ttu-id="b1b4b-268">このコマンドは入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-268">This command does not accept any input.</span></span>

## <span data-ttu-id="b1b4b-269">出力</span><span class="sxs-lookup"><span data-stu-id="b1b4b-269">OUTPUTS</span></span>

### <span data-ttu-id="b1b4b-270">System.Xml.Xml要素</span><span class="sxs-lookup"><span data-stu-id="b1b4b-270">System.Xml.XmlElement</span></span>
<span data-ttu-id="b1b4b-271">このコマンドレットは、 **XMLElement** オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="b1b4b-271">This cmdlet generates an **XMLElement** object.</span></span>

## <span data-ttu-id="b1b4b-272">注</span><span class="sxs-lookup"><span data-stu-id="b1b4b-272">NOTES</span></span>

## <span data-ttu-id="b1b4b-273">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b1b4b-273">RELATED LINKS</span></span>

[<span data-ttu-id="b1b4b-274">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="b1b4b-274">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="b1b4b-275">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b1b4b-275">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="b1b4b-276">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="b1b4b-276">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="b1b4b-277">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b1b4b-277">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="b1b4b-278">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b1b4b-278">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="b1b4b-279">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="b1b4b-279">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="b1b4b-280">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b1b4b-280">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="b1b4b-281">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="b1b4b-281">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="b1b4b-282">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b1b4b-282">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="b1b4b-283">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b1b4b-283">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="b1b4b-284">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="b1b4b-284">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="b1b4b-285">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="b1b4b-285">Test-WSMan</span></span>](Test-WSMan.md)
