---
ms.date: 08/24/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Script リソース
ms.openlocfilehash: 86dfb74bf52d8907686bb955fd722f4fb8b9131b
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2019
ms.locfileid: "58054758"
---
# <a name="dsc-script-resource"></a>DSC Script リソース

> 適用先:Windows PowerShell 4.0、Windows PowerShell 5.x

Windows PowerShell Desired State Configuration (DSC) の **Script** リソースは、ターゲット ノードで Windows PowerShell スクリプトのブロックを実行するためのメカニズムを備えています。 **Script** リソースでは、該当の DSC 状態の操作を実行するために定義したスクリプト ブロックを含む `GetScript`、`SetScript`、および `TestScript` プロパティを使用します。

## <a name="syntax"></a>構文

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

> [!NOTE]
> `GetScript`、`TestScript`、および `SetScript` ブロックは、文字列として格納されます。

## <a name="properties"></a>プロパティ

|プロパティ|説明|
|--------|-----------|
|GetScript|ノードの現在の状態を返すスクリプト ブロック。|
|SetScript|ノードが目的の状態になっていない場合に、コンプライアンスを適用するために DSC が使用するスクリプト ブロック。|
|TestScript|ノードが目的の状態になっているかどうかを判定するスクリプト ブロック。|
|Credential| 資格情報が必要な場合、このスクリプトの実行に使用する資格情報を示します。|
|DependsOn| このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。

### <a name="getscript"></a>GetScript

DSC は `GetScript` からの出力を使用しません。 [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) コマンドレットは `GetScript` を実行して、ノードの現在の状態を取得します。 戻り値は `GetScript` からは必要とされません。 戻り値を指定した場合は、値が `String` の **Result** キーを含む `hashtable` になっている必要があります。

### <a name="testscript"></a>TestScript

`TestScript` は、`SetScript` が実行される必要があるかどうかを判定するために、DSC によって実行されます。 `TestScript` から `$false` が返された場合、DSC は `SetScript` を実行して、ノードを目的の状態に戻します。 `boolean` 値を返す必要があります。 結果が `$true` の場合、ノードが準拠しており `SetScript` が実行されるべきではないことを示します。

[Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) コマンドレットでは、`TestScript` を実行して、**Script** リソースに準拠しているノードを取得します。 ただし、この場合は、`TestScript` ブロックによって返される値に関わらず、`SetScript` は実行されません。

> [!NOTE]
> `TestScript` からの出力はすべて、戻り値の一部です。 PowerShell は、抑制されていない出力を非ゼロとして解釈します。これは、ノードの状態に関係なく、`TestScript` は `$true` を返すことを意味します。
> これにより、誤検知という予期しない結果となり、トラブルシューティングの際に困難が生じます。

### <a name="setscript"></a>SetScript

`SetScript` はノードを変更して、目的の状態を適用します。 これは、`TestScript` スクリプト ブロックから `$false` が返された場合に、DSC によって呼び出されます。 `SetScript` には、戻り値はありません。

## <a name="examples"></a>例

### <a name="example-1-write-sample-text-using-a-script-resource"></a>例 1:Script リソースを使用して、サンプル テキストを作成する

この例では、各ノード上の `C:\TempFolder\TestFile.txt` の有無についてテストします。 このファイルがない場合は、`SetScript` を使用してファイルを作成します。 `GetScript` はファイルのコンテンツを返し、その戻り値は使用されません。

```powershell
Configuration ScriptTest
{
    Import-DscResource –ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script ScriptExample
        {
            SetScript = {
                $sw = New-Object System.IO.StreamWriter("C:\TempFolder\TestFile.txt")
                $sw.WriteLine("Some sample string")
                $sw.Close()
            }
            TestScript = { Test-Path "C:\TempFolder\TestFile.txt" }
            GetScript = { @{ Result = (Get-Content C:\TempFolder\TestFile.txt) } }
        }
    }
}
```

### <a name="example-2-compare-version-information-using-a-script-resource"></a>例 2: Script リソースを使用してバージョン情報を比較する

この例は、オーサリング コンピューター上のテキスト ファイルから *compliant* バージョン情報を取得して、これを `$version` 変数に格納します。 ノードの MOF ファイルを生成するときに、各スクリプト ブロックの `$using:version` 変数は、DSC によって `$version` 変数の値に置き換えられます。 実行時に *compliant* バージョンが各ノード上のテキスト ファイルに格納され、以降の実行で比較され更新されます。

```powershell
$version = Get-Content 'version.txt'

Configuration ScriptTest
{
    Import-DscResource –ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script UpdateConfigurationVersion
        {
            GetScript = {
                $currentVersion = Get-Content (Join-Path -Path $env:SYSTEMDRIVE -ChildPath 'version.txt')
                return @{ 'Result' = "$currentVersion" }
            }
            TestScript = {
                # Create and invoke a scriptblock using the $GetScript automatic variable, which contains a string representation of the GetScript.
                $state = [scriptblock]::Create($GetScript).Invoke()

                if( $state['Result'] -eq $using:version )
                {
                    Write-Verbose -Message ('{0} -eq {1}' -f $state['Result'],$using:version)
                    return $true
                }
                Write-Verbose -Message ('Version up-to-date: {0}' -f $using:version)
                return $false
            }
            SetScript = {
                $using:version | Set-Content -Path (Join-Path -Path $env:SYSTEMDRIVE -ChildPath 'version.txt')
            }
        }
    }
}
```