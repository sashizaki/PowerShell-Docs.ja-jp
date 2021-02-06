---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-PSSessionConfigurationFile
ms.openlocfilehash: c6d6d305b283522215d43b7339683b1617a85804
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603053"
---
# <span data-ttu-id="31b8f-102">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="31b8f-102">Test-PSSessionConfigurationFile</span></span>

## <span data-ttu-id="31b8f-103">概要</span><span class="sxs-lookup"><span data-stu-id="31b8f-103">SYNOPSIS</span></span>
<span data-ttu-id="31b8f-104">セッション構成ファイル内のキーと値を確認します。</span><span class="sxs-lookup"><span data-stu-id="31b8f-104">Verifies the keys and values in a session configuration file.</span></span>

## <span data-ttu-id="31b8f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="31b8f-105">SYNTAX</span></span>

```
Test-PSSessionConfigurationFile [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="31b8f-106">Description</span><span class="sxs-lookup"><span data-stu-id="31b8f-106">DESCRIPTION</span></span>

<span data-ttu-id="31b8f-107">このコマンドレットは、セッション構成ファイルに有効なキーが含まれていること、および値が正しい型であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="31b8f-107">This cmdlet verifies that a session configuration file contains valid keys and the values are of the correct type.</span></span> <span data-ttu-id="31b8f-108">列挙値の場合、コマンドレットは、指定した値が有効であることを検証します。</span><span class="sxs-lookup"><span data-stu-id="31b8f-108">For enumerated values, the cmdlet verifies that the specified values are valid.</span></span>

<span data-ttu-id="31b8f-109">このコマンドレットは、 `$True` ファイルがすべてのテストに合格している場合はを返し、 `$False` そうでない場合はを返します。</span><span class="sxs-lookup"><span data-stu-id="31b8f-109">The cmdlet returns `$True` if the file passes all tests and `$False` if it does not.</span></span> <span data-ttu-id="31b8f-110">エラーを検索するには、 **Verbose** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="31b8f-110">To find any errors, use the **Verbose** parameter.</span></span>

<span data-ttu-id="31b8f-111">`Test-PSSessionConfigurationFile` コマンドレットによって作成されたものなど、セッション構成ファイルを検証し `New-PSSessionConfigurationFile` ます。</span><span class="sxs-lookup"><span data-stu-id="31b8f-111">`Test-PSSessionConfigurationFile` verifies the session configuration files, such as those created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="31b8f-112">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31b8f-112">For information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span> <span data-ttu-id="31b8f-113">セッション構成ファイルの詳細については、「 [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31b8f-113">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="31b8f-114">このコマンドレットは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31b8f-114">This cmdlet was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="31b8f-115">例</span><span class="sxs-lookup"><span data-stu-id="31b8f-115">EXAMPLES</span></span>

### <span data-ttu-id="31b8f-116">例 1: セッション構成ファイルをテストする</span><span class="sxs-lookup"><span data-stu-id="31b8f-116">Example 1: Test a session configuration file</span></span>

```powershell
Test-PSSessionConfigurationFile -Path "FullLanguage.pssc"
```

```Output
True
```

### <span data-ttu-id="31b8f-117">例 2: セッション構成のセッション構成ファイルをテストする</span><span class="sxs-lookup"><span data-stu-id="31b8f-117">Example 2: Test the session configuration file of a session configuration</span></span>

<span data-ttu-id="31b8f-118">この例では、 **制限** されたセッション構成で使用される構成ファイルをテストします。</span><span class="sxs-lookup"><span data-stu-id="31b8f-118">In this example, we test the configuration file used in the **Restricted** session configuration.</span></span>
<span data-ttu-id="31b8f-119">**Path** パラメーターの値は、制限された `Get-PSSessionConfiguration` セッション構成を取得するコマンドの結果です。</span><span class="sxs-lookup"><span data-stu-id="31b8f-119">The value of the **Path** parameter is the result of the `Get-PSSessionConfiguration` command that gets the **Restricted** session configuration.</span></span> <span data-ttu-id="31b8f-120">セッション構成ファイルのパスは、セッション構成の **Configfilepath** プロパティの値に格納されます。</span><span class="sxs-lookup"><span data-stu-id="31b8f-120">The path of the session configuration file is stored in the value of the **ConfigFilePath** property of the session configuration.</span></span>

```powershell
Test-PSSessionConfigurationFile -Path (Get-PSSessionConfiguration -Name Restricted).ConfigFilePath
```

### <span data-ttu-id="31b8f-121">例 3: すべてのセッション構成ファイルをテストする</span><span class="sxs-lookup"><span data-stu-id="31b8f-121">Example 3: Test all session configuration files</span></span>

<span data-ttu-id="31b8f-122">この例の関数は、ローカルコンピューター上のすべてのセッション構成ファイルをテストします。</span><span class="sxs-lookup"><span data-stu-id="31b8f-122">The function in this example tests all session configuration files on the local computer.</span></span> <span data-ttu-id="31b8f-123">関数は、コマンドレットを使用して `Get-PSSessionConfiguration` すべてのセッション構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="31b8f-123">The function uses the `Get-PSSessionConfiguration` cmdlet to get all session configurations.</span></span> <span data-ttu-id="31b8f-124">ループ内のコードは、 `ForEach-Object` ファイルパスを表示し、各セッション構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="31b8f-124">The code inside the `ForEach-Object` loop displays the file path and tests each of the session configurations.</span></span>

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

<span data-ttu-id="31b8f-125">セッション構成の **Configfilepath** プロパティには、セッション構成で使用されるセッション構成ファイルのパス (存在する場合) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="31b8f-125">The **ConfigFilePath** property of a session configuration contains the path of the session configuration file that is used in the session configuration, if any.</span></span>

<span data-ttu-id="31b8f-126">**ConfigFilePath** プロパティの値が入力されている場合 (true の場合)、コマンドは **ConfigFilePath** プロパティの値を取得 (出力) します。</span><span class="sxs-lookup"><span data-stu-id="31b8f-126">If the value of the **ConfigFilePath** property is populated (is true), the command gets (prints) the **ConfigFilePath** property value.</span></span> <span data-ttu-id="31b8f-127">次に、コマンドレットを使用して、 `Test-PSSessionConfigurationFile` **configfilepath** 値内のファイルをテストします。</span><span class="sxs-lookup"><span data-stu-id="31b8f-127">Then it uses the `Test-PSSessionConfigurationFile` cmdlet to test the file in the **ConfigFilePath** value.</span></span> <span data-ttu-id="31b8f-128">**Verbose** パラメーターは、ファイルがテストに合格しなかった場合に、ファイル エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="31b8f-128">The **Verbose** parameter returns the file error when the file fails the test.</span></span>

## <span data-ttu-id="31b8f-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="31b8f-129">PARAMETERS</span></span>

### <span data-ttu-id="31b8f-130">-Path</span><span class="sxs-lookup"><span data-stu-id="31b8f-130">-Path</span></span>

<span data-ttu-id="31b8f-131">セッション構成ファイル (.pssc) のパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="31b8f-131">Specifies the path and filename of a session configuration file (.pssc).</span></span> <span data-ttu-id="31b8f-132">パスを省略した場合、既定値は現在のフォルダーになります。</span><span class="sxs-lookup"><span data-stu-id="31b8f-132">If you omit the path, the default is the current folder.</span></span> <span data-ttu-id="31b8f-133">ワイルドカード文字はサポートされていますが、1つのファイルに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31b8f-133">Wildcard characters are supported, but they must resolve to a single file.</span></span> <span data-ttu-id="31b8f-134">パイプを使用して、セッション構成ファイルのパスをにパイプすることもでき `Test-PSSessionConfigurationFile` ます。</span><span class="sxs-lookup"><span data-stu-id="31b8f-134">You can also pipe a session configuration file path to `Test-PSSessionConfigurationFile`.</span></span>

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

### <span data-ttu-id="31b8f-135">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="31b8f-135">CommonParameters</span></span>

<span data-ttu-id="31b8f-136">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="31b8f-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="31b8f-137">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31b8f-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="31b8f-138">入力</span><span class="sxs-lookup"><span data-stu-id="31b8f-138">INPUTS</span></span>

### <span data-ttu-id="31b8f-139">System.String</span><span class="sxs-lookup"><span data-stu-id="31b8f-139">System.String</span></span>

<span data-ttu-id="31b8f-140">パイプを使用して、セッション構成ファイルのパスをにパイプすることができ `Test-PSSessionConfigurationFile` ます。</span><span class="sxs-lookup"><span data-stu-id="31b8f-140">You can pipe a session configuration file path to `Test-PSSessionConfigurationFile`.</span></span>

## <span data-ttu-id="31b8f-141">出力</span><span class="sxs-lookup"><span data-stu-id="31b8f-141">OUTPUTS</span></span>

### <span data-ttu-id="31b8f-142">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="31b8f-142">System.Boolean</span></span>

## <span data-ttu-id="31b8f-143">注</span><span class="sxs-lookup"><span data-stu-id="31b8f-143">NOTES</span></span>

<span data-ttu-id="31b8f-144">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="31b8f-144">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="31b8f-145">関連リンク</span><span class="sxs-lookup"><span data-stu-id="31b8f-145">RELATED LINKS</span></span>

[<span data-ttu-id="31b8f-146">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="31b8f-146">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="31b8f-147">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="31b8f-147">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="31b8f-148">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="31b8f-148">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="31b8f-149">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="31b8f-149">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="31b8f-150">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="31b8f-150">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="31b8f-151">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="31b8f-151">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="31b8f-152">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="31b8f-152">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="31b8f-153">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="31b8f-153">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="31b8f-154">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="31b8f-154">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="31b8f-155">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="31b8f-155">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="31b8f-156">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="31b8f-156">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="31b8f-157">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="31b8f-157">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
