# 適用することなく構成ドキュメントを提供する

**Publish-DscConfiguration** コマンドレットでは、構成の MOF ファイルをターゲット ノードにコピーしますが、その構成は適用されません。 この構成が適用されるは、次の一貫性パス中、または `Update-DscConfiguration` コマンドレットの実行時です。

```powershell
Publish-DscConfiguration [-Path] <string> [[-ComputerName] <string[]>] [-Force] [-Credential <pscredential>] [-ThrottleLimit <int>] [-WhatIf] [-Confirm] [<CommonParameters>]

Publish-DscConfiguration [-Path] <string> -CimSession <CimSession[]> [-Force] [-ThrottleLimit <int>] [-WhatIf] [-Confirm] [<CommonParameters>]
```
<!--HONumber=Mar16_HO2-->
