# DSC リソースのデバッグ

> 適用先: Windows PowerShell 5.0

PowerShell 5.0 では、構成が適用されているときに DSC リソースをデバッグできる新機能が Desired State Configuraiton (DSC) に導入されました。

## DSC デバッグの有効化
リソースをデバッグする前に、[Enable-DscDebug](https://technet.microsoft.com/en-us/library/mt517870.aspx) コマンドレットを呼び出すことによって、デバッグを有効にする必要があります。 このコマンドレットは、必須パラメーター **BreakAll** を受け取ります。 [Get-DscLocalConfigurationManager](https://technet.microsoft.com/en-us/library/dn407378.aspx) への呼び出しの結果を参照して、デバッグが有効になっていることを確認できます。 次の PowerShell 出力は、デバッグを有効にした結果を示しています。


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


## デバッグを有効にした構成の開始
DSC リソースをデバッグするには、そのリソースを呼び出す構成を開始します。 この例では、"WindowsPowerShellWebAccess" 機能がインストールされていることを確認するために [WindowsFeature](windowsfeatureResource.md) リソースを呼び出す単純な構成を見ていきます。

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
構成をコンパイルした後、[Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) を呼び出して開始します。 構成は、
ローカル構成マネージャー (LCM) が構成の最初のリソースを呼び出したときに停止します。 `-Verbose` および `-Wait` パラメーターを使用した場合、デバッグを開始するために入力する必要がある行が
出力に表示されます。

```powershell
PS C:\DebugTest> Start-DscConfiguration .\PSWebAccess -Wait -Verbose
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
WARNING: [TEST-SRV]:                            [[WindowsFeature]PSWA] Resource is waiting for PowerShell script debugger to attach.  Use the follow
ing commands to begin debugging this resource script:
Enter-PSSession -ComputerName TEST-SRV -Credential <credentials>
Enter-PSHostProcess -Id 9000 -AppDomainName DscPsPluginWkr_AppDomain
Debug-Runspace -Id 9
```
この時点で、LCM はリソースを呼び出し、最初のブレーク ポイントに到達しています。 出力の最後の 3 行は、プロセスに接続し、リソース スクリプトのデバッグを開始する方法を示しています。

## リソース スクリプトのデバッグ

PowerShell ISE の新しいインスタンスを開始します。 コンソール ウィンドウで、`Start-DscConifiguration` 出力から出力の最後の 3 行をコマンドとして入力し、`<credentials>` を
有効なユーザー資格情報に置き換えます。 次に、結果の出力を示します。



<!--HONumber=Feb16_HO4-->
