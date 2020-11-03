---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: d73d8d6a30e6b7c08b5a0b7988ea2327be34002a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215312"
---
# <span data-ttu-id="ecab0-103">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="ecab0-103">Invoke-DscResource</span></span>

## <span data-ttu-id="ecab0-104">概要</span><span class="sxs-lookup"><span data-stu-id="ecab0-104">SYNOPSIS</span></span>
<span data-ttu-id="ecab0-105">指定された DSC リソースのメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ecab0-105">Runs a method of a specified DSC resource.</span></span>

## <span data-ttu-id="ecab0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ecab0-106">SYNTAX</span></span>

```
Invoke-DscResource [-Name] <String> [-Method] <String> -ModuleName <ModuleSpecification> -Property <Hashtable>
 [<CommonParameters>]
```

## <span data-ttu-id="ecab0-107">Description</span><span class="sxs-lookup"><span data-stu-id="ecab0-107">DESCRIPTION</span></span>
<span data-ttu-id="ecab0-108">**DscResource** コマンドレットは、指定された Windows PowerShell Desired State CONFIGURATION (DSC) リソースのメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ecab0-108">The **Invoke-DscResource** cmdlet runs a method of a specified Windows PowerShell Desired State Configuration (DSC) resource.</span></span>
<span data-ttu-id="ecab0-109">このコマンドレットを実行する前に、ローカル Configuration Manager (LCM) の更新モードを [無効] に設定します。</span><span class="sxs-lookup"><span data-stu-id="ecab0-109">Before you run this cmdlet, set the refresh mode of the Local Configuration Manager (LCM) to Disabled.</span></span>

<span data-ttu-id="ecab0-110">このコマンドレットは、構成ドキュメントを作成せずに、DSC リソースを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ecab0-110">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span>
<span data-ttu-id="ecab0-111">このコマンドレットを使用すると、構成管理製品は DSC リソースを使用して windows を管理できます。</span><span class="sxs-lookup"><span data-stu-id="ecab0-111">Using this cmdlet, configuration management products can manage windows by using DSC resources.</span></span>
<span data-ttu-id="ecab0-112">このコマンドレットは、DSC エンジンまたは LCM がデバッグを有効にして実行されている場合にも、リソースのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ecab0-112">This cmdlet also enables debugging of resources when the DSC engine or LCM is running with debugging enabled.</span></span>

## <span data-ttu-id="ecab0-113">例</span><span class="sxs-lookup"><span data-stu-id="ecab0-113">EXAMPLES</span></span>

### <span data-ttu-id="ecab0-114">例 1: 必須プロパティを指定してリソースの Set メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="ecab0-114">Example 1: Invoke the Set method of a resource by specifying its mandatory properties</span></span>

```
PS C:\> Invoke-DscResource -Name Log -Method Set -Property @{Message = 'Hello World'} -ModuleName PSDesiredStateConfiguration
```

<span data-ttu-id="ecab0-115">このコマンドは、Log という名前のリソースの **Set** メソッドを呼び出し、その **メッセージ** のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="ecab0-115">This command invokes the **Set** method of a resource named Log and specifies a **Message** property for it.</span></span>

### <span data-ttu-id="ecab0-116">例 2: 指定したモジュールのリソースのテストメソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="ecab0-116">Example 2: Invoke the Test method of a resource for a specified module</span></span>

```
PS C:\> Invoke-DscResource -Name WindowsProcess -Method Test -Property @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''} -ModuleName PSDesiredStateConfiguration
```

<span data-ttu-id="ecab0-117">このコマンドは、PSDesiredStateConfiguration という名前のモジュール内にある WindowsProcess という名前のリソースの **Test** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ecab0-117">This command invokes the **Test** method of a resource named WindowsProcess, which is in the module named PSDesiredStateConfiguration.</span></span>

## <span data-ttu-id="ecab0-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ecab0-118">PARAMETERS</span></span>

### <span data-ttu-id="ecab0-119">-メソッド</span><span class="sxs-lookup"><span data-stu-id="ecab0-119">-Method</span></span>
<span data-ttu-id="ecab0-120">このコマンドレットが呼び出すリソースのメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="ecab0-120">Specifies the method of the resource that this cmdlet invokes.</span></span> <span data-ttu-id="ecab0-121">このパラメーターに指定できる値は、Get、Set、および Test です。</span><span class="sxs-lookup"><span data-stu-id="ecab0-121">The acceptable values for this parameter are: Get, Set, and Test.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ecab0-122">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="ecab0-122">-ModuleName</span></span>
<span data-ttu-id="ecab0-123">このコマンドレットが指定されたリソースを呼び出すモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ecab0-123">Specifies the name of the module from which this cmdlet invokes the specified resource.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ecab0-124">-Name</span><span class="sxs-lookup"><span data-stu-id="ecab0-124">-Name</span></span>
<span data-ttu-id="ecab0-125">開始する DSC リソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ecab0-125">Specifies the name of the DSC resource to start.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ecab0-126">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="ecab0-126">-Property</span></span>
<span data-ttu-id="ecab0-127">ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。</span><span class="sxs-lookup"><span data-stu-id="ecab0-127">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="ecab0-128">リソースのプロパティと種類を検出するには、 **Get-DscResource** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ecab0-128">Use the **Get-DscResource** cmdlet to discover resource properties and their types.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ecab0-129">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ecab0-129">CommonParameters</span></span>
<span data-ttu-id="ecab0-130">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ecab0-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ecab0-131">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecab0-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ecab0-132">入力</span><span class="sxs-lookup"><span data-stu-id="ecab0-132">INPUTS</span></span>

## <span data-ttu-id="ecab0-133">出力</span><span class="sxs-lookup"><span data-stu-id="ecab0-133">OUTPUTS</span></span>

### <span data-ttu-id="ecab0-134">CimInstance, system.string のようになります。</span><span class="sxs-lookup"><span data-stu-id="ecab0-134">Microsoft.Management.Infrastructure.CimInstance, System.Boolean</span></span>

## <span data-ttu-id="ecab0-135">注</span><span class="sxs-lookup"><span data-stu-id="ecab0-135">NOTES</span></span>

## <span data-ttu-id="ecab0-136">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ecab0-136">RELATED LINKS</span></span>

[<span data-ttu-id="ecab0-137">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="ecab0-137">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="ecab0-138">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="ecab0-138">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="ecab0-139">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="ecab0-139">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="ecab0-140">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="ecab0-140">Get-DscResource</span></span>](Get-DscResource.md)

[<span data-ttu-id="ecab0-141">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="ecab0-141">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="ecab0-142">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="ecab0-142">Set-DscLocalConfigurationManager</span></span>](Set-DscLocalConfigurationManager.md)

[<span data-ttu-id="ecab0-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="ecab0-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="ecab0-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="ecab0-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
