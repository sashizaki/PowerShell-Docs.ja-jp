---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC リソースのデバッグ
ms.openlocfilehash: c088e13a25ba31ceebaf52b2d24b5d32b96ae2fc
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076805"
---
# <a name="debugging-dsc-resources"></a><span data-ttu-id="d8878-103">DSC リソースのデバッグ</span><span class="sxs-lookup"><span data-stu-id="d8878-103">Debugging DSC resources</span></span>

> <span data-ttu-id="d8878-104">適用先:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="d8878-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="d8878-105">PowerShell 5.0 では、構成が適用されているときに DSC リソースをデバッグできる新機能が Desired State Configuraiton (DSC) に導入されました。</span><span class="sxs-lookup"><span data-stu-id="d8878-105">In PowerShell 5.0, a new feature was introduced in Desired State Configuration (DSC) that allows you to debug a DSC resource as a configuration is being applied.</span></span>

## <a name="enabling-dsc-debugging"></a><span data-ttu-id="d8878-106">DSC デバッグの有効化</span><span class="sxs-lookup"><span data-stu-id="d8878-106">Enabling DSC debugging</span></span>
<span data-ttu-id="d8878-107">リソースをデバッグする前に、[Enable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug) コマンドレットを呼び出すことによって、デバッグを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8878-107">Before you can debug a resource, you have to enable debugging by calling the [Enable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug) cmdlet.</span></span>
<span data-ttu-id="d8878-108">このコマンドレットは、必須パラメーター **BreakAll** を取ります。</span><span class="sxs-lookup"><span data-stu-id="d8878-108">This cmdlet takes a mandatory parameter, **BreakAll**.</span></span>

<span data-ttu-id="d8878-109">[Get-DscLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager) への呼び出しの結果を参照して、デバッグが有効になっていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d8878-109">You can verify that debugging has been enabled by looking at the result of a call to [Get-DscLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager).</span></span>

<span data-ttu-id="d8878-110">次の PowerShell 出力は、デバッグを有効にした結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="d8878-110">The following PowerShell output shows the result of enabling debugging:</span></span>


```powershell
PS C:\DebugTest> $LCM = Get-DscLocalConfigurationManager

PS C:\DebugTest> $LCM.DebugMode
NONE

PS C:\DebugTest> Enable-DscDebug -BreakAll

PS C:\DebugTest> $LCM = Get-DscLocalConfigurationManager

PS C:\DebugTest> $LCM.DebugMode
ForceModuleImport
ResourceScriptBreakAll

PS C:\DebugTest>
```


## <a name="starting-a-configuration-with-debug-enabled"></a><span data-ttu-id="d8878-111">デバッグを有効にした構成の開始</span><span class="sxs-lookup"><span data-stu-id="d8878-111">Starting a configuration with debug enabled</span></span>
<span data-ttu-id="d8878-112">DSC リソースをデバッグするには、そのリソースを呼び出す構成を開始します。</span><span class="sxs-lookup"><span data-stu-id="d8878-112">To debug a DSC resource, you start a configuration that calls that resource.</span></span>
<span data-ttu-id="d8878-113">この例では、"WindowsPowerShellWebAccess" 機能がインストールされていることを確認するために **WindowsFeature** リソースを呼び出す単純な構成を見ていきます。</span><span class="sxs-lookup"><span data-stu-id="d8878-113">For this example, we'll look at a simple configuration that calls the **WindowsFeature** resource to ensure that the "WindowsPowerShellWebAccess" feature is installed:</span></span>

```powershell
Configuration PSWebAccess
    {
    Import-DscResource -ModuleName 'PsDesiredStateConfiguration'
    Node localhost
        {
        WindowsFeature PSWA
            {
            Name = 'WindowsPowerShellWebAccess'
            Ensure = 'Present'
            }
        }
    }
PSWebAccess
```
<span data-ttu-id="d8878-114">構成をコンパイルした後、[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) を呼び出して開始します。</span><span class="sxs-lookup"><span data-stu-id="d8878-114">After compiling the configuration, start it by calling [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span></span>
<span data-ttu-id="d8878-115">構成は、ローカル構成マネージャー (LCM) が構成の最初のリソースを呼び出したときに停止します。</span><span class="sxs-lookup"><span data-stu-id="d8878-115">The configuration will stop when the Local Configuration Manager (LCM) calls into the first resource in the configuration.</span></span>
<span data-ttu-id="d8878-116">`-Verbose` および `-Wait` パラメーターを使用した場合、デバッグを開始するために入力する必要がある行が出力に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8878-116">If you use the `-Verbose` and `-Wait` parameters, the output displays the lines you need to enter to start debugging.</span></span>

```powershell
Start-DscConfiguration .\PSWebAccess -Wait -Verbose
VERBOSE: Perform operation 'Invoke CimMethod' with following parameters, ''methodName' = SendConfigurationApply,'className' = MSFT_DSCLocalConfiguration
Manager,'namespaceName' = root/Microsoft/Windows/DesiredStateConfiguration'.
VERBOSE: An LCM method call arrived from computer TEST-SRV with user sid S-1-5-21-2127521184-1604012920-1887927527-108583.
VERBOSE: An LCM method call arrived from computer TEST-SRV with user sid S-1-5-21-2127521184-1604012920-1887927527-108583.
VERBOSE: [TEST-SRV]: LCM:  [ Start  Set      ]
WARNING: [TEST-SRV]:                            [DSCEngine] Warning LCM is in Debug 'ResourceScriptBreakAll' mode.  Resource script processing will
be stopped to wait for PowerShell script debugger to attach.
VERBOSE: [TEST-SRV]:                            [DSCEngine] Importing the module C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateCo
nfiguration\DscResources\MSFT_RoleResource\MSFT_RoleResource.psm1 in force mode.
VERBOSE: [TEST-SRV]: LCM:  [ Start  Resource ]  [[WindowsFeature]PSWA]
VERBOSE: [TEST-SRV]: LCM:  [ Start  Test     ]  [[WindowsFeature]PSWA]
VERBOSE: [TEST-SRV]:                            [[WindowsFeature]PSWA] Importing the module MSFT_RoleResource in force mode.
WARNING: [TEST-SRV]:                            [[WindowsFeature]PSWA] Resource is waiting for PowerShell script debugger to attach.
Use the following commands to begin debugging this resource script:
Enter-PSSession -ComputerName TEST-SRV -Credential <credentials>
Enter-PSHostProcess -Id 9000 -AppDomainName DscPsPluginWkr_AppDomain
Debug-Runspace -Id 9
```
<span data-ttu-id="d8878-117">この時点で、LCM はリソースを呼び出し、最初のブレーク ポイントに到達しています。</span><span class="sxs-lookup"><span data-stu-id="d8878-117">At this point, the LCM has called the resource, and come to the first break point.</span></span>
<span data-ttu-id="d8878-118">出力の最後の 3 行は、プロセスに接続し、リソース スクリプトのデバッグを開始する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d8878-118">The last three lines in the output show you how to attach to the process and start debugging the resource script.</span></span>

## <a name="debugging-the-resource-script"></a><span data-ttu-id="d8878-119">リソース スクリプトのデバッグ</span><span class="sxs-lookup"><span data-stu-id="d8878-119">Debugging the resource script</span></span>

<span data-ttu-id="d8878-120">PowerShell ISE の新しいインスタンスを開始します。</span><span class="sxs-lookup"><span data-stu-id="d8878-120">Start a new instance of the PowerShell ISE.</span></span>
<span data-ttu-id="d8878-121">コンソール ウィンドウで、`Start-DscConfiguration` 出力から出力の最後の 3 行をコマンドとして入力し、`<credentials>` を有効なユーザー資格情報に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d8878-121">In the console pane, enter the last three lines of output from the `Start-DscConfiguration` output as commands, replacing `<credentials>` with valid user credentials.</span></span>
<span data-ttu-id="d8878-122">次のようなプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8878-122">You should now see a prompt that looks similar to:</span></span>

```powershell
[TEST-SRV]: [DBG]: [Process:9000]: [RemoteHost]: PS C:\DebugTest>>
```

<span data-ttu-id="d8878-123">スクリプト ウィンドウが開いてリソース スクリプトが表示され、**Test-TargetResource** 関数の最初の行 (クラスベースのリソースの **Test()** メソッド) でデバッガーが停止します。</span><span class="sxs-lookup"><span data-stu-id="d8878-123">The resource script will open in the script pane, and the debugger is stopped at the first line of the **Test-TargetResource** function (the **Test()** method of a class-based resource).</span></span>
<span data-ttu-id="d8878-124">ISE でデバッグ コマンドを使うと、リソース スクリプトをステップ実行したり、変数の値を確認したり、呼び出し履歴を表示したりできます。</span><span class="sxs-lookup"><span data-stu-id="d8878-124">Now you can use the debug commands in the ISE to step through the resource script, look at variable values, view the call stack, and so on.</span></span> <span data-ttu-id="d8878-125">リソース スクリプト (またはクラス) のすべての行がブレークポイントとして設定されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d8878-125">Remember that every line in the resource script (or class) is set as a break point.</span></span>

## <a name="disabling-dsc-debugging"></a><span data-ttu-id="d8878-126">DSC デバッグの無効化</span><span class="sxs-lookup"><span data-stu-id="d8878-126">Disabling DSC debugging</span></span>

<span data-ttu-id="d8878-127">[Enable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug)を呼び出した後では、[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) を呼び出すたびに構成でデバッガー中断が行われるようになります。</span><span class="sxs-lookup"><span data-stu-id="d8878-127">After calling [Enable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug), all calls to [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) will result in the configuration breaking into the debugger.</span></span> <span data-ttu-id="d8878-128">構成を通常どおりに実行できるようにするには、[Disable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Disable-DscDebug) コマンドレットを呼び出してデバッグを無効化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8878-128">To allow configurations to run normally, you must disable debugging by calling the [Disable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Disable-DscDebug) cmdlet.</span></span>

><span data-ttu-id="d8878-129">**注:** 再起動をしても、LCM のデバッグ状態は変更されません。</span><span class="sxs-lookup"><span data-stu-id="d8878-129">**Note:** Rebooting does not change the debug state of the LCM.</span></span> <span data-ttu-id="d8878-130">デバッグが有効になっている場合、再起動後に構成を開始してもデバッグ中断が行われます。</span><span class="sxs-lookup"><span data-stu-id="d8878-130">If debugging is enabled, starting a configuration will still break into the debugger after a reboot.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8878-131">参照</span><span class="sxs-lookup"><span data-stu-id="d8878-131">See Also</span></span>

- [<span data-ttu-id="d8878-132">MOF を使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="d8878-132">Writing a custom DSC resource with MOF</span></span>](../resources/authoringResourceMOF.md)
- [<span data-ttu-id="d8878-133">PowerShell クラスを使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="d8878-133">Writing a custom DSC resource with PowerShell classes</span></span>](../resources/authoringResourceClass.md)
