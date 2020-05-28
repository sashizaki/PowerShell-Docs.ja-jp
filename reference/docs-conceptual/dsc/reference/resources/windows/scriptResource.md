---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Script リソース
ms.openlocfilehash: 50d4667396c8c619079288ec51599152ed2d6cd5
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557024"
---
# <a name="dsc-script-resource"></a>DSC Script リソース

> 適用先:Windows PowerShell 4.0、Windows PowerShell 5.x

Windows PowerShell Desired State Configuration (DSC) の **Script** リソースは、ターゲット ノードで Windows PowerShell スクリプトのブロックを実行するためのメカニズムを備えています。 **Script** リソースでは、対応する DSC 状態操作を実行するために、定義するスクリプト ブロックを含む **GetScript**、**SetScript**、および **TestScript** プロパティを使用します。

## <a name="syntax"></a>構文

```Syntax
Script [string] #ResourceName
{
    GetScript = [string]
    SetScript = [string]
    TestScript = [string]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

> [!NOTE]
> **GetScript**、**TestScript**、および **SetScript** ブロックは文字列として格納されます。

## <a name="properties"></a>Properties

|プロパティ |説明 |
|---|---|
|GetScript |ノードの現在の状態を返すスクリプト ブロック。 |
|SetScript |ノードが目的の状態になっていない場合に、コンプライアンスを適用するために DSC が使用するスクリプト ブロック。 |
|TestScript |ノードが目的の状態になっているかどうかを判定するスクリプト ブロック。 |
|資格情報 |資格情報が必要な場合、このスクリプトの実行に使用する資格情報を示します。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|PsDscRunAsCredential |リソース全体を実行するための資格情報を設定します。 |

> [!NOTE]
> **PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。 詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。

### <a name="additional-information"></a>関連情報

#### <a name="getscript"></a>GetScript

DSC では **GetScript** からの出力が使用されません。 [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) コマンドレットでは **GetScript** を実行してノードの現在の状態を取得します。 **GetScript** からの戻り値は必須ではありません。 戻り値を指定する場合は、値が String の **Result** キーを含むハッシュテーブルにする必要があります。

#### <a name="testscript"></a>TestScript

**TestScript** は DSC によって実行され、**SetScript** を実行する必要があるかどうかを決定します。 **TestScript** から `$false` が返される場合、DSC では **SetScript** を実行してノードを目的の状態に戻します。 ブール値を返す必要があります。 結果が `$true` の場合、ノードが準拠しており **SetScript** が実行されるべきではないことを示します。

[Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) コマンドレットでは、**TestScript** を実行して、**Script** リソースに準拠しているノードを取得します。
ただし、この場合、**TestScript** がどのように返されるかに関係なく、**SetScript** は実行されません。

> [!NOTE]
> **TestScript** のすべての出力が戻り値の一部になります。 PowerShell は、抑制されていない出力を非ゼロとして解釈します。これは、ノードの状態に関係なく、**TestScript** から `$true` が返されることを意味します。 これにより、誤検知という予期しない結果となり、トラブルシューティングの際に困難が生じます。

#### <a name="setscript"></a>SetScript

**SetScript** ではノードを変更して、目的の状態を適用します。 **TestScript** スクリプト ブロックから `$false` が返される場合、これが DSC によって呼び出されます。 **SetScript** には戻り値がありません。

## <a name="examples"></a>例

### <a name="example-1-write-sample-text-using-a-script-resource"></a>例 1:Script リソースを使用して、サンプル テキストを作成する

この例では、各ノード上の `C:\TempFolder\TestFile.txt` の有無についてテストします。 このファイルがない場合は、`SetScript` を使用してファイルを作成します。 `GetScript` はファイルのコンテンツを返し、その戻り値は使用されません。

```powershell
Configuration ScriptTest
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

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

### <a name="example-2-compare-version-information-using-a-script-resource"></a>例 2:Script リソースを使用してバージョン情報を比較する

この例は、オーサリング コンピューター上のテキスト ファイルから *compliant* バージョン情報を取得して、これを `$version` 変数に格納します。 ノードの MOF ファイルを生成するときに、各スクリプト ブロックの `$using:version` 変数は、DSC によって `$version` 変数の値に置き換えられます。
実行時に *compliant* バージョンが各ノード上のテキスト ファイルに格納され、以降の実行で比較され更新されます。

```powershell
$version = Get-Content 'version.txt'

Configuration ScriptTest
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

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

### <a name="example-3-utilizing-parameters-in-a-script-resource"></a>例 3: スクリプト リソースでパラメーターを使用する

この例では、`using` スコープを使用して、スクリプト リソース内からパラメーターにアクセスします。 なお、**ConfigurationData** も同様の方法でアクセスできます。 例 2 と同様に、バージョンはターゲット ノードのローカル ファイル内に格納されます。 ローカル ファイル パスとそのバージョンは両方とも構成できますが、構成データからコードを分離する必要があります。

```powershell
Configuration ScriptTest
{
    param
    (
        [Version]
        $Version,

        [string]
        $FilePath
    )

    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script UpdateConfigurationVersion
        {
            GetScript = {
                $currentVersion = Get-Content -Path $using:FilePath
                return @{ 'Result' = "$currentVersion" }
            }
            TestScript = {
                # Create and invoke a scriptblock using the $GetScript automatic variable, which contains a string representation of the GetScript.
                $state = [scriptblock]::Create($GetScript).Invoke()

                if( $state['Result'] -eq $using:Version )
                {
                    Write-Verbose -Message ('{0} -eq {1}' -f $state['Result'],$using:version)
                    return $true
                }

                Write-Verbose -Message ('Version up-to-date: {0}' -f $using:version)
                return $false
            }
            SetScript = {
                Set-Content -Path $using:FilePath -Value $using:Version
            }
        }
    }
}
```

生成される MOF ファイルには、`using` スコープを通じてアクセスされる変数とその値が含まれます。
これらは、この変数を使用する各スクリプトブロックに挿入されます。 TestScript と SetScript は、簡潔にするために削除しています。

```Output
instance of MSFT_ScriptResource as $MSFT_ScriptResource1ref
{
 GetScript = "$FilePath ='C:\\Config.ini'\n\n $currentVersion = Get-Content -Path $FilePath\n return @{ 'Result' = \"$currentVersion\" }\n";
 TestScript = ...;
 SetScript = ...;
};
```
