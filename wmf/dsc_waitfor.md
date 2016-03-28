# ノードの相互依存関係の指定

組み込みの WaitFor\* リソース (WaitForAll、WaitForAny、および WaitForSome) を使えば、コンピューター間の依存関係を外部の指揮なしで構成の実行中に指定できます。 各 WaitFor\* リソースの動作は次のとおりです。

* **WaitForAll** では、NodeName プロパティで定義されている*すべての*ターゲット ノード上の指定されたリソースが必要な状態になるのを待機します。
* **WaitForAny** では、NodeName プロパティで定義されている*いずれかの*ターゲット ノード上の指定されたリソースが必要な状態になるのを待機します。
* **WaitForSome** NodeName プロパティで定義されているターゲット ノード上の指定されたリソースが、NodeCount プロパティで定義された個数まで必要な状態になるのを待機します。

これらのリソースは、WS-Man プロトコルで CIM 接続を使用して、ノード間の同期を提供します。 これらのリソースを使うと、別のコンピューターの特定のリソースの状態が変化するのを待機してから、構成を続行することができます。 

たとえば、次の構成では、ターゲット ノードは **MyDC** ノード上の **xADDomain** リソースが完了するまで何回か再試行しながら待機した後で、ドメインに参加できるようになります。

```PowerShell
Configuration JoinDomain

{
    Import-DscResource -Module xComputerManagement

    WaitForAll DC
    {
        ResourceName      = '[xADDomain]NewDomain'
        NodeName          = 'MyDC'
        RetryIntervalSec  = 15
        RetryCount        = 30
    }

    xComputer JoinDomain
    {
        Name             = 'MyPC'
        DomainName       = 'Contoso.com'
        Credential       = (get-credential)
        DependsOn        ='[WaitForAll]DC'
    }
}
```
**ヒント:** WaitFor\* リソースは、既定では、1 回試行してから失敗します。そのため、必須ではありませんが、通常は再試行の間隔と回数を指定することをお勧めします。
<!--HONumber=Mar16_HO2-->
