---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/get-wsmaninstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WSManInstance
ms.openlocfilehash: 00680a466c9cc9dd719fbce3d66f4eb10ec47860
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602169"
---
# <span data-ttu-id="c4dc4-102">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="c4dc4-102">Get-WSManInstance</span></span>

## <span data-ttu-id="c4dc4-103">概要</span><span class="sxs-lookup"><span data-stu-id="c4dc4-103">SYNOPSIS</span></span>
<span data-ttu-id="c4dc4-104">リソース URI で指定されたリソース インスタンスの管理情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-104">Displays management information for a resource instance specified by a Resource URI.</span></span>

## <span data-ttu-id="c4dc4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c4dc4-105">SYNTAX</span></span>

### <span data-ttu-id="c4dc4-106">GetInstance (既定値)</span><span class="sxs-lookup"><span data-stu-id="c4dc4-106">GetInstance (Default)</span></span>

```
Get-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-ConnectionURI <Uri>] [-Dialect <Uri>]
 [-Fragment <String>] [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet <Hashtable>]
 [-SessionOption <SessionOption>] [-UseSSL] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="c4dc4-107">[列挙]</span><span class="sxs-lookup"><span data-stu-id="c4dc4-107">Enumerate</span></span>

```
Get-WSManInstance [-ApplicationName <String>] [-BasePropertiesOnly] [-ComputerName <String>]
 [-ConnectionURI <Uri>] [-Dialect <Uri>] [-Enumerate] [-Filter <String>] [-OptionSet <Hashtable>]
 [-Port <Int32>] [-Associations] [-ResourceURI] <Uri> [-ReturnType <String>] [-SessionOption <SessionOption>]
 [-Shallow] [-UseSSL] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="c4dc4-108">Description</span><span class="sxs-lookup"><span data-stu-id="c4dc4-108">DESCRIPTION</span></span>
<span data-ttu-id="c4dc4-109">**Get wsmaninstance** コマンドレットは、リソース UNIFORM RESOURCE IDENTIFIER (URI) によって指定された管理リソースのインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-109">The **Get-WSManInstance** cmdlet retrieves an instance of a management resource that is specified by a resource Uniform Resource Identifier (URI).</span></span>
<span data-ttu-id="c4dc4-110">取得される情報は、複雑な XML 情報セット (オブジェクトまたは単純な値) にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-110">The information that is retrieved can be a complex XML information set, which is an object, or a simple value.</span></span>
<span data-ttu-id="c4dc4-111">このコマンドレットは、標準の Web Services for Management (WS-MANAGEMENT) **Get** コマンドに相当します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-111">This cmdlet is the equivalent to the standard Web Services for Management (WS-Management) **Get** command.</span></span>

<span data-ttu-id="c4dc4-112">このコマンドレットは、WS-Management の接続/トランスポート層を使用して、情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-112">This cmdlet uses the WS-Management connection/transport layer to retrieve information.</span></span>

## <span data-ttu-id="c4dc4-113">例</span><span class="sxs-lookup"><span data-stu-id="c4dc4-113">EXAMPLES</span></span>

### <span data-ttu-id="c4dc4-114">例 1: WMI からすべての情報を取得する</span><span class="sxs-lookup"><span data-stu-id="c4dc4-114">Example 1: Get all information from WMI</span></span>

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

<span data-ttu-id="c4dc4-115">このコマンドは、Windows Management Instrumentation (WMI) がリモート server01 コンピューター上の **WinRM** サービスについて公開しているすべての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-115">This command returns all of the information that Windows Management Instrumentation (WMI) exposes about the **WinRM** service on the remote server01 computer.</span></span>

### <span data-ttu-id="c4dc4-116">例 2: スプーラサービスの状態を取得する</span><span class="sxs-lookup"><span data-stu-id="c4dc4-116">Example 2: Get the status of the Spooler service</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI wmicimv2/win32_service -SelectorSet @{name="spooler"} -Fragment Status -ComputerName "Server01"
XmlFragment=OK
```

<span data-ttu-id="c4dc4-117">このコマンドは、リモート server01 コンピューター上の **スプーラ** サービスの状態のみを返します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-117">This command returns only the status of the **Spooler** service on the remote server01 computer.</span></span>

### <span data-ttu-id="c4dc4-118">例 3: すべてのサービスのエンドポイント参照を取得する</span><span class="sxs-lookup"><span data-stu-id="c4dc4-118">Example 3: Get endpoint references for all services</span></span>

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

<span data-ttu-id="c4dc4-119">このコマンドは、ローカル コンピューター上のすべてのサービスに対応するエンドポイント参照を返します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-119">This command returns endpoint references that correspond to all the services on the local computer.</span></span>

### <span data-ttu-id="c4dc4-120">例 4: 指定した条件を満たすサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="c4dc4-120">Example 4: Get services that meet specified criteria</span></span>

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

<span data-ttu-id="c4dc4-121">このコマンドは、リモートの Server01 コンピューター上で、次の条件を満たすすべてのサービスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-121">This command lists all of the services that meet the following criteria on the remote Server01 computer:</span></span>

- <span data-ttu-id="c4dc4-122">サービスのスタートアップの種類は Automatic です。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-122">The startup type of the service is Automatic.</span></span>
- <span data-ttu-id="c4dc4-123">サービスが停止しています。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-123">The service is stopped.</span></span>

### <span data-ttu-id="c4dc4-124">例 5: ローカルコンピューターの条件に一致するリスナー構成を取得する</span><span class="sxs-lookup"><span data-stu-id="c4dc4-124">Example 5: Get listener configuration that matches criteria on the local computer</span></span>

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

<span data-ttu-id="c4dc4-125">このコマンドは、ローカル コンピューター上の、セレクター セットの条件と一致する WS-Management リスナーの構成を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-125">This command lists the WS-Management listener configuration on the local computer for the listener that matches the criteria in the selector set.</span></span>

### <span data-ttu-id="c4dc4-126">例 6: リモートコンピューターの条件に一致するリスナー構成を取得する</span><span class="sxs-lookup"><span data-stu-id="c4dc4-126">Example 6: Get listener configuration that matches criteria on a remote computer</span></span>

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

<span data-ttu-id="c4dc4-127">このコマンドは、server01 リモート コンピューター上の、セレクター セットの条件と一致する WS-Management リスナーの構成を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-127">This command lists the WS-Management listener configuration on the remote server01 computer for the listener that matches the criteria in the selector set.</span></span>

### <span data-ttu-id="c4dc4-128">例 7: 指定したインスタンスに関連付けられているインスタンスを取得する</span><span class="sxs-lookup"><span data-stu-id="c4dc4-128">Example 7: Get associated instances related to a specified instance</span></span>

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

<span data-ttu-id="c4dc4-129">このコマンドは、指定されたインスタンス (winrm) に関連付けられているインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-129">This command gets the associated instances that are related to the specified instance (winrm).</span></span>

<span data-ttu-id="c4dc4-130">次の例に示すように、フィルターを二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-130">You must enclose the filter in quotation marks, as shown in the example.</span></span>

### <span data-ttu-id="c4dc4-131">例 8: 指定したインスタンスに関連する関連付けインスタンスを取得する</span><span class="sxs-lookup"><span data-stu-id="c4dc4-131">Example 8: Get association instances related to a specified instance</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -Dialect Association -Associations -Filter "{Object=win32_service?name=winrm}" -ResourceURI wmicimv2/*
```

<span data-ttu-id="c4dc4-132">このコマンドは、指定されたインスタンス (winrm) の関連付けインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-132">This command gets association instances that are related to the specified instance (winrm).</span></span>
<span data-ttu-id="c4dc4-133">*Dialect* 値は association *で、association パラメーターが* 使用されるため、このコマンドは関連付けられているインスタンスではなく関連付けインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-133">Because the *Dialect* value is association and the *Associations* parameter is used, this command returns association instances, not associated instances.</span></span>

<span data-ttu-id="c4dc4-134">次の例に示すように、フィルターを二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-134">You must enclose the filter in quotation marks, as shown in the example.</span></span>

## <span data-ttu-id="c4dc4-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c4dc4-135">PARAMETERS</span></span>

### <span data-ttu-id="c4dc4-136">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="c4dc4-136">-ApplicationName</span></span>
<span data-ttu-id="c4dc4-137">接続のアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-137">Specifies the application name in the connection.</span></span>
<span data-ttu-id="c4dc4-138">*ApplicationName* パラメーターの既定値は WSMAN です。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-138">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="c4dc4-139">リモート エンドポイントの完全な識別子は、次の形式です。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-139">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="c4dc4-140">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="c4dc4-140">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="c4dc4-141">例: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="c4dc4-141">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="c4dc4-142">セッションをホストするインターネット インフォメーション サービス (IIS) は、このエンドポイントで、指定されたアプリケーションに要求を転送します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-142">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="c4dc4-143">この WSMAN の既定の設定は、ほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-143">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="c4dc4-144">このパラメーターは、多くのコンピューターが PowerShell を実行する1台のコンピューターへのリモート接続を確立する場合に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-144">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="c4dc4-145">この場合、IIS は効率を上げるために WS-Management をホストします。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-145">In this case, IIS hosts WS-Management for efficiency.</span></span>

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

### <span data-ttu-id="c4dc4-146">-関連付け</span><span class="sxs-lookup"><span data-stu-id="c4dc4-146">-Associations</span></span>
<span data-ttu-id="c4dc4-147">このコマンドレットが関連付けられているインスタンスではなく、関連付けインスタンスを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-147">Indicates that this cmdlet gets association instances, not associated instances.</span></span>
<span data-ttu-id="c4dc4-148">このパラメーターは、 *Dialect* パラメーターの値が Association の場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-148">You can use this parameter only when the *Dialect* parameter has a value of Association.</span></span>

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

### <span data-ttu-id="c4dc4-149">-認証</span><span class="sxs-lookup"><span data-stu-id="c4dc4-149">-Authentication</span></span>
<span data-ttu-id="c4dc4-150">サーバーで使用される認証メカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-150">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="c4dc4-151">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-151">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c4dc4-152">基本。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-152">Basic.</span></span>
<span data-ttu-id="c4dc4-153">Basic は、ユーザー名およびパスワードがクリア テキストでサーバーまたはプロキシに送信されるスキームです。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-153">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="c4dc4-154">既定値。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-154">Default.</span></span>
<span data-ttu-id="c4dc4-155">WS-Management プロトコルによって実装されている認証方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-155">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="c4dc4-156">既定値です。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-156">This is the default.</span></span>
- <span data-ttu-id="c4dc4-157">ダイジェスト。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-157">Digest.</span></span>
<span data-ttu-id="c4dc4-158">Digest は、サーバーで指定されたデータ文字列をチャレンジで使用するチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-158">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="c4dc4-159">Kerberos。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-159">Kerberos.</span></span>
<span data-ttu-id="c4dc4-160">クライアント コンピューターとサーバーが Kerberos 証明書を使用して相互に認証します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-160">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="c4dc4-161">Negotiate</span><span class="sxs-lookup"><span data-stu-id="c4dc4-161">Negotiate.</span></span>
<span data-ttu-id="c4dc4-162">Negotiate は、認証で使用するスキームを特定するために、サーバーまたはプロキシとネゴシエートするチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-162">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="c4dc4-163">たとえば、このパラメーター値を指定すると、Kerberos プロトコルと NTLM のどちらが使用されているかをネゴシエーションで判断できます。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-163">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="c4dc4-164">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="c4dc4-164">CredSSP.</span></span>
<span data-ttu-id="c4dc4-165">Credential Security Support Provider (CredSSP) 認証を使用して、ユーザーが資格情報を委任できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-165">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="c4dc4-166">このオプションは、1 台のリモート コンピューターで実行するが、他のリモート コンピューターからデータを収集するコマンドや、他のリモート コンピューターで追加のコマンドを実行するコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-166">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="c4dc4-167">注意: CredSSP は、ローカルコンピューターからリモートコンピューターにユーザーの資格情報を委任します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-167">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="c4dc4-168">そのため、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-168">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="c4dc4-169">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡された資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-169">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="c4dc4-170">-BasePropertiesOnly</span><span class="sxs-lookup"><span data-stu-id="c4dc4-170">-BasePropertiesOnly</span></span>
<span data-ttu-id="c4dc4-171">このコマンドレットが、 *ResourceURI* パラメーターで指定された基本クラスの一部であるプロパティだけを列挙することを示します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-171">Indicates that this cmdlet enumerates only the properties that are part of the base class that is specified by the *ResourceURI* parameter.</span></span>
<span data-ttu-id="c4dc4-172">このパラメーターは、 *簡易* パラメーターが指定されている場合には効果がありません。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-172">This parameter has no effect if the *Shallow* parameter is specified.</span></span>

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

### <span data-ttu-id="c4dc4-173">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="c4dc4-173">-CertificateThumbprint</span></span>
<span data-ttu-id="c4dc4-174">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-174">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="c4dc4-175">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-175">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="c4dc4-176">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-176">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="c4dc4-177">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-177">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="c4dc4-178">証明書の拇印を取得するには、PowerShell Cert: ドライブで Get-Item または Get-ChildItem コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-178">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="c4dc4-179">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="c4dc4-179">-ComputerName</span></span>
<span data-ttu-id="c4dc4-180">管理操作を実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-180">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="c4dc4-181">値には、完全修飾ドメイン名、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-181">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="c4dc4-182">ローカル コンピューターを指定するには、ローカル コンピューター名、localhost、またはドット (.) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-182">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="c4dc4-183">ローカル コンピューターは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-183">The local computer is the default.</span></span>
<span data-ttu-id="c4dc4-184">リモート コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-184">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="c4dc4-185">パイプを使用して、このパラメーターの値をコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-185">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="c4dc4-186">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="c4dc4-186">-ConnectionURI</span></span>
<span data-ttu-id="c4dc4-187">接続エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-187">Specifies the connection endpoint.</span></span>
<span data-ttu-id="c4dc4-188">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-188">The format of this string is as follows:</span></span>

<span data-ttu-id="c4dc4-189">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="c4dc4-189">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="c4dc4-190">次の文字列は、このパラメーターに対して正しく書式設定された値です。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-190">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="c4dc4-191">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-191">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="c4dc4-192">-Credential</span><span class="sxs-lookup"><span data-stu-id="c4dc4-192">-Credential</span></span>
<span data-ttu-id="c4dc4-193">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-193">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="c4dc4-194">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-194">The default is the current user.</span></span>
<span data-ttu-id="c4dc4-195">User01、Domain01\user01」、などのユーザー名を入力し User@Domain.com ます。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-195">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="c4dc4-196">または、Get-Credential コマンドレットによって返されるような **PSCredential** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-196">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="c4dc4-197">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-197">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="c4dc4-198">-言語</span><span class="sxs-lookup"><span data-stu-id="c4dc4-198">-Dialect</span></span>
<span data-ttu-id="c4dc4-199">フィルター述語で使用する言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-199">Specifies the dialect to use in the filter predicate.</span></span>
<span data-ttu-id="c4dc4-200">リモート サービスでサポートされている任意の言語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-200">This can be any dialect that is supported by the remote service.</span></span>
<span data-ttu-id="c4dc4-201">言語の URI には、次のエイリアスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-201">The following aliases can be used for the dialect URI:</span></span>

- <span data-ttu-id="c4dc4-202">WQL `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span><span class="sxs-lookup"><span data-stu-id="c4dc4-202">WQL `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span></span>
- <span data-ttu-id="c4dc4-203">選択肢 `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span><span class="sxs-lookup"><span data-stu-id="c4dc4-203">Selector `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span></span>
- <span data-ttu-id="c4dc4-204">づける `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span><span class="sxs-lookup"><span data-stu-id="c4dc4-204">Association `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span></span>

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

### <span data-ttu-id="c4dc4-205">-列挙</span><span class="sxs-lookup"><span data-stu-id="c4dc4-205">-Enumerate</span></span>
<span data-ttu-id="c4dc4-206">このコマンドレットが管理リソースのすべてのインスタンスを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-206">Indicates that this cmdlet returns all of the instances of a management resource.</span></span>

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

### <span data-ttu-id="c4dc4-207">-Filter</span><span class="sxs-lookup"><span data-stu-id="c4dc4-207">-Filter</span></span>
<span data-ttu-id="c4dc4-208">列挙体のフィルター式を指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-208">Specifies the filter expression for the enumeration.</span></span>
<span data-ttu-id="c4dc4-209">このパラメーターを指定する場合は、 *Dialect* も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-209">If you specify this parameter, you must also specify *Dialect*.</span></span>

<span data-ttu-id="c4dc4-210">このパラメーターの有効な値は、 *dialect* で指定されている言語によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-210">The valid values of this parameter depend on the dialect that is specified in *Dialect*.</span></span>
<span data-ttu-id="c4dc4-211">たとえば、 *Dialect* が WQL の場合、 *Filter* パラメーターには文字列を含める必要があり、文字列には次のクエリのような有効な WQL クエリが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-211">For example, if *Dialect* is WQL, the *Filter* parameter must contain a string, and the string must contain a valid WQL query such as the following query:</span></span>

`"Select * from Win32_Service where State != Running"`

<span data-ttu-id="c4dc4-212">*Dialect* が Association の場合、 *filter* には文字列を含める必要があり、文字列には次のフィルターのような有効なフィルターが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-212">If *Dialect* is Association, *Filter* must contain a string, and the string must contain a valid filter, such as the following filter:</span></span>

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

### <span data-ttu-id="c4dc4-213">-Fragment</span><span class="sxs-lookup"><span data-stu-id="c4dc4-213">-Fragment</span></span>
<span data-ttu-id="c4dc4-214">指定された操作で更新または取得するインスタンス内のセクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-214">Specifies a section inside the instance that is to be updated or retrieved for the specified operation.</span></span>
<span data-ttu-id="c4dc4-215">たとえば、スプーラサービスの状態を取得するには、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-215">For example, to get the status of a spooler service, specify the following:</span></span>

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

### <span data-ttu-id="c4dc4-216">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="c4dc4-216">-OptionSet</span></span>
<span data-ttu-id="c4dc4-217">要求の性質を変更または調整するための一連のスイッチをサービスに指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-217">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="c4dc4-218">これらは、サービス固有であるため、コマンドラインシェルで使用されるスイッチに似ています。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-218">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="c4dc4-219">任意の数のオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-219">Any number of options can be specified.</span></span>

<span data-ttu-id="c4dc4-220">次の例では、a、b、および c パラメーターに値 1、2、および 3 を渡す構文を示します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-220">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="c4dc4-221">-Port</span><span class="sxs-lookup"><span data-stu-id="c4dc4-221">-Port</span></span>
<span data-ttu-id="c4dc4-222">クライアントが WinRM サービスに接続するときに使用するポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-222">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="c4dc4-223">トランスポートが HTTP の場合、既定のポートは 80 です。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-223">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="c4dc4-224">トランスポートが HTTPS の場合、既定のポートは 443 です。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-224">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="c4dc4-225">HTTPS をトランスポートとして使用する場合は、 *ComputerName* パラメーターの値がサーバーの証明書共通名 (CN) と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-225">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="c4dc4-226">ただし、 *Sessionoption* パラメーターの一部として *skipcncheck* パラメーターを指定した場合、サーバーの証明書の共通名がサーバーのホスト名と一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-226">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="c4dc4-227">*Skipcncheck* パラメーターは、信頼されたコンピューターに対してのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-227">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="c4dc4-228">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="c4dc4-228">-ResourceURI</span></span>
<span data-ttu-id="c4dc4-229">リソースクラスまたはインスタンスの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-229">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="c4dc4-230">URI は、コンピューター上の特定の種類のリソース (ディスクやプロセスなど) を識別します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-230">The URI identifies a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="c4dc4-231">URI は、リソースのプレフィックスとパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-231">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="c4dc4-232">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-232">For example:</span></span>

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

### <span data-ttu-id="c4dc4-233">-ReturnType</span><span class="sxs-lookup"><span data-stu-id="c4dc4-233">-ReturnType</span></span>
<span data-ttu-id="c4dc4-234">返されるデータの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-234">Specifies the type of data to be returned.</span></span>
<span data-ttu-id="c4dc4-235">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-235">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c4dc4-236">Object</span><span class="sxs-lookup"><span data-stu-id="c4dc4-236">Object</span></span>
- <span data-ttu-id="c4dc4-237">EPR</span><span class="sxs-lookup"><span data-stu-id="c4dc4-237">EPR</span></span>
- <span data-ttu-id="c4dc4-238">ObjectAndEPR</span><span class="sxs-lookup"><span data-stu-id="c4dc4-238">ObjectAndEPR</span></span>

<span data-ttu-id="c4dc4-239">既定値は Object です。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-239">The default value is Object.</span></span>

<span data-ttu-id="c4dc4-240">オブジェクトを指定した場合、またはこのパラメーターを指定しなかった場合、このコマンドレットはオブジェクトのみを返します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-240">If you specify Object or do not specify this parameter, this cmdlet returns only objects.</span></span>
<span data-ttu-id="c4dc4-241">エンドポイント参照 (EPR) を指定すると、このコマンドレットはオブジェクトのエンドポイント参照のみを返します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-241">If you specify endpoint reference (EPR) this cmdlet returns only the endpoint references of the objects.</span></span>
<span data-ttu-id="c4dc4-242">エンドポイント参照には、インスタンスのリソース URI とセレクターに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-242">Endpoint references contain information about the resource URI and the selectors for the instance.</span></span>
<span data-ttu-id="c4dc4-243">ObjectAndEPR を指定した場合、このコマンドレットはオブジェクトとそれに関連付けられているエンドポイント参照の両方を返します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-243">If you specify ObjectAndEPR, this cmdlet returns both the object and its associated endpoint references.</span></span>

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

### <span data-ttu-id="c4dc4-244">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="c4dc4-244">-SelectorSet</span></span>
<span data-ttu-id="c4dc4-245">特定の管理リソース インスタンスの選択に使用する値のペアのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-245">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="c4dc4-246">*SelectorSet* パラメーターは、リソースの複数のインスタンスが存在する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-246">The *SelectorSet* parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="c4dc4-247">*SelectorSet* パラメーターの値は、ハッシュテーブルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-247">The value of the *SelectorSet* parameter must be a hash table.</span></span>

<span data-ttu-id="c4dc4-248">次の例では、このパラメーターの値を入力する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-248">The following example shows how to enter a value for this parameter:</span></span>

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

### <span data-ttu-id="c4dc4-249">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="c4dc4-249">-SessionOption</span></span>
<span data-ttu-id="c4dc4-250">WS-Management セッションの拡張オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-250">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="c4dc4-251">New-WSManSessionOption コマンドレットを使用して作成する **Sessionoption** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-251">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="c4dc4-252">使用可能なオプションの詳細については、「」と入力 `Get-Help New-WSManSessionOption` してください。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-252">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="c4dc4-253">-浅い</span><span class="sxs-lookup"><span data-stu-id="c4dc4-253">-Shallow</span></span>
<span data-ttu-id="c4dc4-254">このコマンドレットが、リソース URI で指定された基本クラスのインスタンスのみを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-254">Indicates that this cmdlet returns only instances of the base class that is specified in the resource URI.</span></span>
<span data-ttu-id="c4dc4-255">このパラメーターを指定しない場合、このコマンドレットは、URI およびそのすべての派生クラスに指定されている基本クラスのインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-255">If you do not specify this parameter,, this cmdlet returns instances of the base class that is specified in the URI and in all its derived classes.</span></span>

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

### <span data-ttu-id="c4dc4-256">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="c4dc4-256">-UseSSL</span></span>
<span data-ttu-id="c4dc4-257">リモートコンピューターへの接続を確立するために Secure Sockets Layer (SSL) プロトコルを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-257">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="c4dc4-258">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-258">By default, SSL is not used.</span></span>

<span data-ttu-id="c4dc4-259">WS-Management は、ネットワーク経由で転送されるすべての PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-259">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="c4dc4-260">*UseSSL* パラメーターを使用すると、HTTP ではなく HTTPS の追加の保護を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-260">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="c4dc4-261">接続に使用するポートで SSL が使用できない場合、このパラメーターを指定すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-261">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="c4dc4-262">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c4dc4-262">CommonParameters</span></span>
<span data-ttu-id="c4dc4-263">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-263">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c4dc4-264">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-264">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c4dc4-265">入力</span><span class="sxs-lookup"><span data-stu-id="c4dc4-265">INPUTS</span></span>

### <span data-ttu-id="c4dc4-266">なし</span><span class="sxs-lookup"><span data-stu-id="c4dc4-266">None</span></span>
<span data-ttu-id="c4dc4-267">このコマンドは入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-267">This command does not accept any input.</span></span>

## <span data-ttu-id="c4dc4-268">出力</span><span class="sxs-lookup"><span data-stu-id="c4dc4-268">OUTPUTS</span></span>

### <span data-ttu-id="c4dc4-269">System.Xml.Xml要素</span><span class="sxs-lookup"><span data-stu-id="c4dc4-269">System.Xml.XmlElement</span></span>
<span data-ttu-id="c4dc4-270">このコマンドレットは、 **XMLElement** オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="c4dc4-270">This cmdlet generates an **XMLElement** object.</span></span>

## <span data-ttu-id="c4dc4-271">注</span><span class="sxs-lookup"><span data-stu-id="c4dc4-271">NOTES</span></span>

## <span data-ttu-id="c4dc4-272">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c4dc4-272">RELATED LINKS</span></span>

[<span data-ttu-id="c4dc4-273">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="c4dc4-273">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="c4dc4-274">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="c4dc4-274">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="c4dc4-275">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="c4dc4-275">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="c4dc4-276">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="c4dc4-276">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="c4dc4-277">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="c4dc4-277">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="c4dc4-278">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="c4dc4-278">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="c4dc4-279">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="c4dc4-279">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="c4dc4-280">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="c4dc4-280">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="c4dc4-281">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="c4dc4-281">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="c4dc4-282">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="c4dc4-282">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="c4dc4-283">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="c4dc4-283">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="c4dc4-284">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="c4dc4-284">Test-WSMan</span></span>](Test-WSMan.md)

