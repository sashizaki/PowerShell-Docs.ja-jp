---
ms.date: 07/16/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Script リソース
ms.openlocfilehash: 9b89981c17e87b3681c6416c7dee44a75c432ea1
ms.sourcegitcommit: eb6a7c01e6385809656ac828b9211683e0b1a6fe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2020
ms.locfileid: "89041131"
---
# <a name="dsc-script-resource"></a><span data-ttu-id="7360d-103">DSC Script リソース</span><span class="sxs-lookup"><span data-stu-id="7360d-103">DSC Script Resource</span></span>

> <span data-ttu-id="7360d-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="7360d-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="7360d-105">Windows PowerShell Desired State Configuration (DSC) の `Script` リソースは、ターゲット ノードで Windows PowerShell スクリプトのブロックを実行するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="7360d-105">The `Script` resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to run Windows PowerShell script blocks on target nodes.</span></span> <span data-ttu-id="7360d-106">`Script` リソースでは、対応する DSC 状態操作を実行するために定義したスクリプト ブロックが含まれる `GetScript`、
`SetScript`、`TestScript` の各プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="7360d-106">The `Script` resource uses `GetScript`
`SetScript`, and `TestScript` properties that contain script blocks you define to perform the corresponding DSC state operations.</span></span>

## <a name="syntax"></a><span data-ttu-id="7360d-107">構文</span><span class="sxs-lookup"><span data-stu-id="7360d-107">Syntax</span></span>

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
> <span data-ttu-id="7360d-108">`GetScript`、`TestScript`、および `SetScript` の各ブロックは、文字列として格納されます。</span><span class="sxs-lookup"><span data-stu-id="7360d-108">`GetScript` `TestScript`, and `SetScript` blocks are stored as strings.</span></span>

## <a name="properties"></a><span data-ttu-id="7360d-109">Properties</span><span class="sxs-lookup"><span data-stu-id="7360d-109">Properties</span></span>

|  <span data-ttu-id="7360d-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7360d-110">Property</span></span>  |                                          <span data-ttu-id="7360d-111">説明</span><span class="sxs-lookup"><span data-stu-id="7360d-111">Description</span></span>                                          |
| ---------- | --------------------------------------------------------------------------------------------- |
| <span data-ttu-id="7360d-112">GetScript</span><span class="sxs-lookup"><span data-stu-id="7360d-112">GetScript</span></span>  | <span data-ttu-id="7360d-113">ノードの現在の状態を返すスクリプト ブロック。</span><span class="sxs-lookup"><span data-stu-id="7360d-113">A script block that returns the current state of the Node.</span></span>                                    |
| <span data-ttu-id="7360d-114">SetScript</span><span class="sxs-lookup"><span data-stu-id="7360d-114">SetScript</span></span>  | <span data-ttu-id="7360d-115">ノードが目的の状態になっていない場合に、コンプライアンスを適用するために DSC が使用するスクリプト ブロック。</span><span class="sxs-lookup"><span data-stu-id="7360d-115">A script block that DSC uses to enforce compliance when the Node is not in the desired state.</span></span> |
| <span data-ttu-id="7360d-116">TestScript</span><span class="sxs-lookup"><span data-stu-id="7360d-116">TestScript</span></span> | <span data-ttu-id="7360d-117">ノードが目的の状態になっているかどうかを判定するスクリプト ブロック。</span><span class="sxs-lookup"><span data-stu-id="7360d-117">A script block that determines if the Node is in the desired state.</span></span>                           |
| <span data-ttu-id="7360d-118">資格情報</span><span class="sxs-lookup"><span data-stu-id="7360d-118">Credential</span></span> | <span data-ttu-id="7360d-119">資格情報が必要な場合、このスクリプトの実行に使用する資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7360d-119">Indicates the credentials to use for running this script, if credentials are required.</span></span>        |

## <a name="common-properties"></a><span data-ttu-id="7360d-120">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="7360d-120">Common properties</span></span>

|       <span data-ttu-id="7360d-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7360d-121">Property</span></span>       |                                            <span data-ttu-id="7360d-122">説明</span><span class="sxs-lookup"><span data-stu-id="7360d-122">Description</span></span>                                            |
| -------------------- | ------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="7360d-123">DependsOn</span><span class="sxs-lookup"><span data-stu-id="7360d-123">DependsOn</span></span>            | <span data-ttu-id="7360d-124">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="7360d-124">Indicates that the configuration of another resource must run before this resource is configured.</span></span> |
| <span data-ttu-id="7360d-125">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="7360d-125">PsDscRunAsCredential</span></span> | <span data-ttu-id="7360d-126">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="7360d-126">Sets the credential for running the entire resource as.</span></span>                                           |

> [!NOTE]
> <span data-ttu-id="7360d-127">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="7360d-127">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="7360d-128">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7360d-128">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

### <a name="additional-information"></a><span data-ttu-id="7360d-129">関連情報</span><span class="sxs-lookup"><span data-stu-id="7360d-129">Additional information</span></span>

#### <a name="getscript"></a><span data-ttu-id="7360d-130">GetScript</span><span class="sxs-lookup"><span data-stu-id="7360d-130">GetScript</span></span>

<span data-ttu-id="7360d-131">DSC では、`GetScript` からの出力は使用されません。[Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) コマンドレットでは、`GetScript` を実行して、ノードの現在の状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="7360d-131">DSC does not use the output from `GetScript` The [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet executes `GetScript` to retrieve a node's current state.</span></span> <span data-ttu-id="7360d-132">戻り値は、`GetScript` では必要ありません。戻り値を指定する場合は、値が String の **Result** キーが含まれるハッシュテーブルにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7360d-132">A return value is not required from `GetScript` If you specify a return value, it must be a hashtable containing a **Result** key whose value is a String.</span></span>

#### <a name="testscript"></a><span data-ttu-id="7360d-133">TestScript</span><span class="sxs-lookup"><span data-stu-id="7360d-133">TestScript</span></span>

<span data-ttu-id="7360d-134">`TestScript` は DSC によって実行され、`SetScript` を実行する必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="7360d-134">`TestScript` is executed by DSC to determine if `SetScript` should be run.</span></span> <span data-ttu-id="7360d-135">`TestScript` から `$false` が返される場合、DSC では `SetScript` を実行してノードを目的の状態に戻します。</span><span class="sxs-lookup"><span data-stu-id="7360d-135">If `TestScript` returns `$false`, DSC executes `SetScript` to bring the node back to the desired state.</span></span> <span data-ttu-id="7360d-136">ブール値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7360d-136">It must return a boolean value.</span></span> <span data-ttu-id="7360d-137">結果が `$true` の場合、ノードが準拠しており `SetScript` が実行されるべきではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="7360d-137">A result of `$true` indicates that the node is compliant and `SetScript` should not executed.</span></span>

<span data-ttu-id="7360d-138">[Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) コマンドレットでは、`TestScript` を実行して、`Script` リソースに準拠しているノードを取得します。</span><span class="sxs-lookup"><span data-stu-id="7360d-138">The [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) cmdlet, executes `TestScript` to retrieve the nodes compliance with the `Script` resources.</span></span> <span data-ttu-id="7360d-139">ただし、この場合、`TestScript` がどのように返されるかに関係なく、`SetScript` は実行されません。</span><span class="sxs-lookup"><span data-stu-id="7360d-139">However, in this case, `SetScript` does not run, no matter what `TestScript` block returns.</span></span>

> [!NOTE]
> <span data-ttu-id="7360d-140">`TestScript` からの出力はすべて、戻り値の一部です。</span><span class="sxs-lookup"><span data-stu-id="7360d-140">All output from your `TestScript` is part of its return value.</span></span> <span data-ttu-id="7360d-141">PowerShell は、抑制されていない出力を非ゼロとして解釈します。これは、ノードの状態に関係なく、`TestScript` は `$true` を返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="7360d-141">PowerShell interprets unsuppressed output as non-zero, which means that your `TestScript` will return `$true` regardless of your node's state.</span></span> <span data-ttu-id="7360d-142">これにより、誤検知という予期しない結果となり、トラブルシューティングの際に困難が生じます。</span><span class="sxs-lookup"><span data-stu-id="7360d-142">This results in unpredictable results, false positives, and causes difficulty during troubleshooting.</span></span>

#### <a name="setscript"></a><span data-ttu-id="7360d-143">SetScript</span><span class="sxs-lookup"><span data-stu-id="7360d-143">SetScript</span></span>

<span data-ttu-id="7360d-144">`SetScript` ではノードを変更して、目的の状態を適用します。</span><span class="sxs-lookup"><span data-stu-id="7360d-144">`SetScript` modifies the node to enforce the desired state.</span></span> <span data-ttu-id="7360d-145">これは、`TestScript` スクリプト ブロックから `$false` が返された場合に、DSC によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="7360d-145">It is called by DSC if the `TestScript` script block returns `$false`.</span></span> <span data-ttu-id="7360d-146">`SetScript` には、戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="7360d-146">The `SetScript` should have no return value.</span></span>

## <a name="examples"></a><span data-ttu-id="7360d-147">例</span><span class="sxs-lookup"><span data-stu-id="7360d-147">Examples</span></span>

### <a name="example-1-write-sample-text-using-a-script-resource"></a><span data-ttu-id="7360d-148">例 1:Script リソースを使用して、サンプル テキストを作成する</span><span class="sxs-lookup"><span data-stu-id="7360d-148">Example 1: Write sample text using a Script resource</span></span>

<span data-ttu-id="7360d-149">この例では、各ノード上の `C:\TempFolder\TestFile.txt` の有無についてテストします。</span><span class="sxs-lookup"><span data-stu-id="7360d-149">This example tests for the existence of `C:\TempFolder\TestFile.txt` on each node.</span></span> <span data-ttu-id="7360d-150">このファイルがない場合は、`SetScript` を使用してファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7360d-150">If it does not exist, it creates it using the `SetScript`.</span></span> <span data-ttu-id="7360d-151">`GetScript` はファイルのコンテンツを返し、その戻り値は使用されません。</span><span class="sxs-lookup"><span data-stu-id="7360d-151">The `GetScript` returns the contents of the file, and its return value is not used.</span></span>

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

### <a name="example-2-compare-version-information-using-a-script-resource"></a><span data-ttu-id="7360d-152">例 2:Script リソースを使用してバージョン情報を比較する</span><span class="sxs-lookup"><span data-stu-id="7360d-152">Example 2: Compare version information using a Script resource</span></span>

<span data-ttu-id="7360d-153">この例は、オーサリング コンピューター上のテキスト ファイルから _compliant_ バージョン情報を取得して、これを `$version` 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="7360d-153">This example retrieves the _compliant_ version information from a text file on the authoring computer and stores it in the `$version` variable.</span></span> <span data-ttu-id="7360d-154">ノードの MOF ファイルを生成するときに、各スクリプト ブロックの `$using:version` 変数は、DSC によって `$version` 変数の値に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="7360d-154">When generating the node's MOF file, DSC replaces the `$using:version` variables in each script block with the value of the `$version` variable.</span></span>
<span data-ttu-id="7360d-155">実行時に _compliant_ バージョンが各ノード上のテキスト ファイルに格納され、以降の実行で比較され更新されます。</span><span class="sxs-lookup"><span data-stu-id="7360d-155">During execution, the _compliant_ version is stored in a text file on each Node and compared and updated on subsequent executions.</span></span>

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

                if( $state.Result -eq $using:version )
                {
                    Write-Verbose -Message ('{0} -eq {1}' -f $state.Result,$using:version)
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

### <a name="example-3-utilizing-parameters-in-a-script-resource"></a><span data-ttu-id="7360d-156">例 3: スクリプト リソースでパラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="7360d-156">Example 3: Utilizing parameters in a Script resource</span></span>

<span data-ttu-id="7360d-157">この例では、`using` スコープを使用して、スクリプト リソース内からパラメーターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="7360d-157">This example accesses parameters from within the Script resource by making use of the `using` scope.</span></span>
<span data-ttu-id="7360d-158">なお、**ConfigurationData** も同様の方法でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7360d-158">Please note that **ConfigurationData** can be accessed in a similar way.</span></span> <span data-ttu-id="7360d-159">例 2 と同様に、バージョンはターゲット ノードのローカル ファイル内に格納されます。</span><span class="sxs-lookup"><span data-stu-id="7360d-159">Like example 2, a version is expected to be stored inside a local file on the target node.</span></span> <span data-ttu-id="7360d-160">ローカル ファイル パスとそのバージョンは両方とも構成できますが、構成データからコードを分離する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7360d-160">Both the local file path as well as the version are configurable however, decoupling code from configuration data.</span></span>

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

<span data-ttu-id="7360d-161">生成される MOF ファイルには、`using` スコープを通じてアクセスされる変数とその値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7360d-161">The resulting MOF file includes the variables and their values accessed through the `using` scope.</span></span>
<span data-ttu-id="7360d-162">これらは、この変数を使用する各スクリプトブロックに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="7360d-162">They are injected into each scriptblock which uses the variables.</span></span> <span data-ttu-id="7360d-163">TestScript と SetScript は、簡潔にするために削除しています。</span><span class="sxs-lookup"><span data-stu-id="7360d-163">Test and Set scripts have been removed for brevity:</span></span>

```Output
instance of MSFT_ScriptResource as $MSFT_ScriptResource1ref
{
 GetScript = "$FilePath ='C:\\Config.ini'\n\n $currentVersion = Get-Content -Path $FilePath\n return @{ 'Result' = \"$currentVersion\" }\n";
 TestScript = ...;
 SetScript = ...;
};
```

### <a name="known-limitations"></a><span data-ttu-id="7360d-164">既知の制限事項</span><span class="sxs-lookup"><span data-stu-id="7360d-164">Known Limitations</span></span>

- <span data-ttu-id="7360d-165">プルまたはプッシュ サーバー モデルを使用する場合、スクリプト リソース内で渡される資格情報は、常に信頼できるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="7360d-165">Credentials being passed within a script resource are not always reliable when using a pull or push server model.</span></span> <span data-ttu-id="7360d-166">この場合は、スクリプト リソースを使用するのではなく、完全なリソースを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7360d-166">It is recommended to use a full resource rather than use a script resource in this case.</span></span>
