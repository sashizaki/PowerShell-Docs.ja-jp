# DSC WindowsProcess リソース

> 適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

Windows PowerShell Desired State Configuration (DSC) の **WindowsProcess** リソースは、ターゲット ノードにプロセスを構成するためのメカニズムを備えています。

## 構文

```
WindowsProcess [string] #ResourceName
{
    Arguments = [string]
    Path = [string]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ DependsOn = [string[]] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ StandardOutputPath = [string] ]
    [ WorkingDirectory = [string] ]
}
```

## プロパティ
|  プロパティ  |  説明   | 
|---|---| 
| 引数| プロセスに渡す引数の文字列をそのまま示します。 複数の引数を渡す必要がある場合は、そのすべてをこの文字列内に配置します。| 
| パス| プロセスの実行可能ファイルへのパスを示します。 このプロパティを実行可能ファイルの名前に設定すると、DSC は __Path__ 変数を参照します。 完全修飾ドメイン名を指定した場合は、DSC が __Path__ 変数を参照しないため、そのドメインにプロセスが存在する必要があります。| 
| Credential| プロセスを開始するための資格情報を示します。| 
| Ensure| プロセスが存在するかどうかを示します。 プロセスが存在することを保証するには、このプロパティを "Present" に設定します。 それ以外の場合は、"Absent" に設定します。 既定は "Present" です。| 
| DependsOn | このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は DependsOn = "[ResourceType]ResourceName" になります。| 
| StandardErrorPath| 標準エラーを書き込むディレクトリ パスを示します。 既存のファイルは上書きされます。| 
| StandardInputPath| 標準入力の場所を示します。| 
| StandardOutputPath| 標準出力の書き込み場所を示します。 既存のファイルは上書きされます。| 
| WorkingDirectory| プロセスの現在の作業ディレクトリとして使用される場所を示します。| 


<!--HONumber=Feb16_HO4-->


