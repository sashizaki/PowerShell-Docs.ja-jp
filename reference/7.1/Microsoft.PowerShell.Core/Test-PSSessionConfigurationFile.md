---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-PSSessionConfigurationFile
ms.openlocfilehash: 625611246ea5a07fba16ecb86a2c8c48345d9ea5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212667"
---
# <span data-ttu-id="de02f-103">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="de02f-103">Test-PSSessionConfigurationFile</span></span>

## <span data-ttu-id="de02f-104">概要</span><span class="sxs-lookup"><span data-stu-id="de02f-104">SYNOPSIS</span></span>
<span data-ttu-id="de02f-105">セッション構成ファイル内のキーと値を確認します。</span><span class="sxs-lookup"><span data-stu-id="de02f-105">Verifies the keys and values in a session configuration file.</span></span>

## <span data-ttu-id="de02f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="de02f-106">SYNTAX</span></span>

```
Test-PSSessionConfigurationFile [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="de02f-107">Description</span><span class="sxs-lookup"><span data-stu-id="de02f-107">DESCRIPTION</span></span>

<span data-ttu-id="de02f-108">このコマンドレットは、セッション構成ファイルに有効なキーが含まれていること、および値が正しい型であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="de02f-108">This cmdlet verifies that a session configuration file contains valid keys and the values are of the correct type.</span></span> <span data-ttu-id="de02f-109">列挙値の場合、コマンドレットは、指定した値が有効であることを検証します。</span><span class="sxs-lookup"><span data-stu-id="de02f-109">For enumerated values, the cmdlet verifies that the specified values are valid.</span></span>

<span data-ttu-id="de02f-110">このコマンドレットは、 `$True` ファイルがすべてのテストに合格している場合はを返し、 `$False` そうでない場合はを返します。</span><span class="sxs-lookup"><span data-stu-id="de02f-110">The cmdlet returns `$True` if the file passes all tests and `$False` if it does not.</span></span> <span data-ttu-id="de02f-111">エラーを検索するには、 **Verbose** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="de02f-111">To find any errors, use the **Verbose** parameter.</span></span>

<span data-ttu-id="de02f-112">`Test-PSSessionConfigurationFile` コマンドレットによって作成されたものなど、セッション構成ファイルを検証し `New-PSSessionConfigurationFile` ます。</span><span class="sxs-lookup"><span data-stu-id="de02f-112">`Test-PSSessionConfigurationFile` verifies the session configuration files, such as those created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="de02f-113">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de02f-113">For information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span> <span data-ttu-id="de02f-114">セッション構成ファイルの詳細については、「 [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de02f-114">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="de02f-115">このコマンドレットは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="de02f-115">This cmdlet was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="de02f-116">例</span><span class="sxs-lookup"><span data-stu-id="de02f-116">EXAMPLES</span></span>

### <span data-ttu-id="de02f-117">例 1: セッション構成ファイルをテストする</span><span class="sxs-lookup"><span data-stu-id="de02f-117">Example 1: Test a session configuration file</span></span>

```powershell
Test-PSSessionConfigurationFile -Path "FullLanguage.pssc"
```

```Output
True
```

### <span data-ttu-id="de02f-118">例 2: セッション構成のセッション構成ファイルをテストする</span><span class="sxs-lookup"><span data-stu-id="de02f-118">Example 2: Test the session configuration file of a session configuration</span></span>

<span data-ttu-id="de02f-119">この例では、 **制限** されたセッション構成で使用される構成ファイルをテストします。</span><span class="sxs-lookup"><span data-stu-id="de02f-119">In this example, we test the configuration file used in the **Restricted** session configuration.</span></span>
<span data-ttu-id="de02f-120">**Path** パラメーターの値は、制限された `Get-PSSessionConfiguration` セッション構成を取得する **Restricted** コマンドの結果です。</span><span class="sxs-lookup"><span data-stu-id="de02f-120">The value of the **Path** parameter is the result of the `Get-PSSessionConfiguration` command that gets the **Restricted** session configuration.</span></span> <span data-ttu-id="de02f-121">セッション構成ファイルのパスは、セッション構成の **Configfilepath** プロパティの値に格納されます。</span><span class="sxs-lookup"><span data-stu-id="de02f-121">The path of the session configuration file is stored in the value of the **ConfigFilePath** property of the session configuration.</span></span>

```powershell
Test-PSSessionConfigurationFile -Path (Get-PSSessionConfiguration -Name Restricted).ConfigFilePath
```

### <span data-ttu-id="de02f-122">例 3: すべてのセッション構成ファイルをテストする</span><span class="sxs-lookup"><span data-stu-id="de02f-122">Example 3: Test all session configuration files</span></span>

<span data-ttu-id="de02f-123">この例の関数は、ローカルコンピューター上のすべてのセッション構成ファイルをテストします。</span><span class="sxs-lookup"><span data-stu-id="de02f-123">The function in this example tests all session configuration files on the local computer.</span></span> <span data-ttu-id="de02f-124">関数は、コマンドレットを使用して `Get-PSSessionConfiguration` すべてのセッション構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="de02f-124">The function uses the `Get-PSSessionConfiguration` cmdlet to get all session configurations.</span></span> <span data-ttu-id="de02f-125">ループ内のコードは、 `ForEach-Object` ファイルパスを表示し、各セッション構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="de02f-125">The code inside the `ForEach-Object` loop displays the file path and tests each of the session configurations.</span></span>

```powershell
function Test-AllConfigFiles
{
    Get-PSSessionConfiguration | ForEach-Object {
        if ($_.ConfigFilePath) {
            $_.ConfigFilePath
            Test-PSSessionConfigurationFile -Verbose -Path $_.ConfigFilePath
        }
    }
}
Test-AllConfigFiles
```

```Output
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Empty_6fd77bf6-e084-4372-bd8a-af3e207354d3.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc
VERBOSE: The member 'AliasDefinitions' must contain the required key 'Description'. Add the require key
to the fileC:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc.
False
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RestrictedLang_b6bd9474-0a6c-4e06-8722-c2c95bb10d3e.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RRS_3fb29420-2c87-46e5-a402-e21436331efc.pssc
True
```

<span data-ttu-id="de02f-126">セッション構成の **Configfilepath** プロパティには、セッション構成で使用されるセッション構成ファイルのパス (存在する場合) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="de02f-126">The **ConfigFilePath** property of a session configuration contains the path of the session configuration file that is used in the session configuration, if any.</span></span>

<span data-ttu-id="de02f-127">**ConfigFilePath** プロパティの値が入力されている場合 (true の場合)、コマンドは **ConfigFilePath** プロパティの値を取得 (出力) します。</span><span class="sxs-lookup"><span data-stu-id="de02f-127">If the value of the **ConfigFilePath** property is populated (is true), the command gets (prints) the **ConfigFilePath** property value.</span></span> <span data-ttu-id="de02f-128">次に、コマンドレットを使用して、 `Test-PSSessionConfigurationFile` **configfilepath** 値内のファイルをテストします。</span><span class="sxs-lookup"><span data-stu-id="de02f-128">Then it uses the `Test-PSSessionConfigurationFile` cmdlet to test the file in the **ConfigFilePath** value.</span></span> <span data-ttu-id="de02f-129">**Verbose** パラメーターは、ファイルがテストに合格しなかった場合に、ファイル エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="de02f-129">The **Verbose** parameter returns the file error when the file fails the test.</span></span>

## <span data-ttu-id="de02f-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="de02f-130">PARAMETERS</span></span>

### <span data-ttu-id="de02f-131">-Path</span><span class="sxs-lookup"><span data-stu-id="de02f-131">-Path</span></span>

<span data-ttu-id="de02f-132">セッション構成ファイル (.pssc) のパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="de02f-132">Specifies the path and filename of a session configuration file (.pssc).</span></span> <span data-ttu-id="de02f-133">パスを省略した場合、既定値は現在のフォルダーになります。</span><span class="sxs-lookup"><span data-stu-id="de02f-133">If you omit the path, the default is the current folder.</span></span> <span data-ttu-id="de02f-134">ワイルドカード文字はサポートされていますが、1つのファイルに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de02f-134">Wildcard characters are supported, but they must resolve to a single file.</span></span> <span data-ttu-id="de02f-135">パイプを使用して、セッション構成ファイルのパスをにパイプすることもでき `Test-PSSessionConfigurationFile` ます。</span><span class="sxs-lookup"><span data-stu-id="de02f-135">You can also pipe a session configuration file path to `Test-PSSessionConfigurationFile`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="de02f-136">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="de02f-136">CommonParameters</span></span>

<span data-ttu-id="de02f-137">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="de02f-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="de02f-138">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de02f-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="de02f-139">入力</span><span class="sxs-lookup"><span data-stu-id="de02f-139">INPUTS</span></span>

### <span data-ttu-id="de02f-140">System.String</span><span class="sxs-lookup"><span data-stu-id="de02f-140">System.String</span></span>

<span data-ttu-id="de02f-141">パイプを使用して、セッション構成ファイルのパスをにパイプすることができ `Test-PSSessionConfigurationFile` ます。</span><span class="sxs-lookup"><span data-stu-id="de02f-141">You can pipe a session configuration file path to `Test-PSSessionConfigurationFile`.</span></span>

## <span data-ttu-id="de02f-142">出力</span><span class="sxs-lookup"><span data-stu-id="de02f-142">OUTPUTS</span></span>

### <span data-ttu-id="de02f-143">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="de02f-143">System.Boolean</span></span>

## <span data-ttu-id="de02f-144">注</span><span class="sxs-lookup"><span data-stu-id="de02f-144">NOTES</span></span>

## <span data-ttu-id="de02f-145">関連リンク</span><span class="sxs-lookup"><span data-stu-id="de02f-145">RELATED LINKS</span></span>

[<span data-ttu-id="de02f-146">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="de02f-146">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="de02f-147">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="de02f-147">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="de02f-148">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="de02f-148">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="de02f-149">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="de02f-149">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="de02f-150">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="de02f-150">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="de02f-151">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="de02f-151">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="de02f-152">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="de02f-152">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="de02f-153">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="de02f-153">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="de02f-154">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="de02f-154">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="de02f-155">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="de02f-155">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="de02f-156">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="de02f-156">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="de02f-157">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="de02f-157">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)

