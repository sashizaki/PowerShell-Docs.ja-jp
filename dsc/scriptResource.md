# DSC Script リソース

 
> 適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

Windows PowerShell Desired State Configuration (DSC) の **Script** リソースは、ターゲット ノードで Windows PowerShell スクリプトのブロックを実行するためのメカニズムを備えています。

## 構文

```
Script [string] #ResourceName
{
    GetScript = [string]
    SetScript = [string]
    TestScript = [string]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
}
```

## プロパティ

|  プロパティ  |  説明   | 
|---|---| 
| GetScript| [Get-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407379.aspx) コマンドレットを呼び出すと実行される Windows PowerShell スクリプトのブロックを提供します。 このブロックでは、ハッシュ テーブルを返す必要があります。| 
| SetScript| Windows PowerShell スクリプトのブロックを提供します。 [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) コマンドレットを呼び出すと、**TestScript** ブロックが最初に実行されます。 **TestScript** ブロックが **$false** を返した場合は、**SetScript** ブロックが実行されます。 **TestScript** ブロックが **$true** を返した場合は、**SetScript** ブロックが実行されません。| 
| TestScript| Windows PowerShell スクリプトのブロックを提供します。 [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) コマンドレットを呼び出すと、このブロックが実行されます。 これが **$false** を返した場合は、SetScript ブロックが実行されます。 これが **$true** を返した場合は、SetScript ブロックが実行されません。 [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) コマンドレットを呼び出すと、**TestScript** ブロックも実行されます。 ただし、この場合、TestScript ブロックがどのような値を返すかに関係なく、**SetScript** ブロックは実行されません。 **TestScript** ブロックは、実際の構成が現在の Desired State Configuration と一致する場合には True を返す必要があり、一致しない場合には False を返す必要があります  (現在の Desired State Configuration は DSC を使用しているノードに適用された最後の構成です)。| 
| Credential| 資格情報が必要な場合、このスクリプトの実行に使用する資格情報を示します。| 
| DependsOn| このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。

## 例
```powershell
Script ScriptExample
{
    SetScript = { 
        $sw = New-Object System.IO.StreamWriter("C:\TempFolder\TestFile.txt")
        $sw.WriteLine("Some sample string")
        $sw.Close()
    }
    TestScript = { Test-Path "C:\TempFolder\TestFile.txt" }
    GetScript = { <# This must return a hash table #> }          
}
```

<!--HONumber=Feb16_HO4-->
