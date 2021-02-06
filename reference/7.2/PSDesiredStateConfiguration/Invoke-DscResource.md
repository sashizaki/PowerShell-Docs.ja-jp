---
external help file: PSDesiredStateConfiguration-help.xml
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: 732db5a049a68e059db6062d2f6c3f850d579adc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600999"
---
# <span data-ttu-id="80d46-102">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="80d46-102">Invoke-DscResource</span></span>

## <span data-ttu-id="80d46-103">概要</span><span class="sxs-lookup"><span data-stu-id="80d46-103">SYNOPSIS</span></span>
<span data-ttu-id="80d46-104">指定された PowerShell Desired State Configuration (DSC) リソースのメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="80d46-104">Runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

## <span data-ttu-id="80d46-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="80d46-105">SYNTAX</span></span>

```
Invoke-DscResource [-Name] <String> [[-ModuleName] <ModuleSpecification>] [-Method] <String>
 [-Property] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="80d46-106">Description</span><span class="sxs-lookup"><span data-stu-id="80d46-106">DESCRIPTION</span></span>

<span data-ttu-id="80d46-107">`Invoke-DscResource` コマンドレットは、指定された PowerShell Desired State Configuration (DSC) リソースのメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="80d46-107">The `Invoke-DscResource` cmdlet runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

<span data-ttu-id="80d46-108">このコマンドレットは、構成ドキュメントを作成せずに、DSC リソースを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="80d46-108">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span> <span data-ttu-id="80d46-109">このコマンドレットを使用すると、構成管理製品は DSC リソースを使用して windows または Linux を管理できます。</span><span class="sxs-lookup"><span data-stu-id="80d46-109">Using this cmdlet, configuration management products can manage windows or Linux by using DSC resources.</span></span> <span data-ttu-id="80d46-110">DSC エンジンの実行中、デバッグが有効になっている場合は、このコマンドレットでリソースのデバッグを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="80d46-110">This cmdlet also enables debugging of resources when the DSC engine is running with debugging enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="80d46-111">`Invoke-DscResource` は、PowerShell 7 の試験的な機能です。</span><span class="sxs-lookup"><span data-stu-id="80d46-111">`Invoke-DscResource` is an experimental feature in PowerShell 7.</span></span> <span data-ttu-id="80d46-112">コマンドレットを使用するには、次のコマンドを使用して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80d46-112">To use the cmdlet, you must enable it using the following command.</span></span>
>
> `Enable-ExperimentalFeature PSDesiredStateConfiguration.InvokeDscResource`

## <span data-ttu-id="80d46-113">例</span><span class="sxs-lookup"><span data-stu-id="80d46-113">EXAMPLES</span></span>

### <span data-ttu-id="80d46-114">例 1: 必須プロパティを指定してリソースの Set メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="80d46-114">Example 1: Invoke the Set method of a resource by specifying its mandatory properties</span></span>

<span data-ttu-id="80d46-115">この例では、 **Windowsprocess** という名前のリソースの **Set** メソッドを呼び出し、指定された Windows プロセスを開始するための必須の **パス** と **引数** のプロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="80d46-115">This example invokes the **Set** method of a resource named **WindowsProcess** and provides the mandatory **Path** and **Arguments** properties to start the specified Windows process.</span></span>

```powershell
Invoke-DscResource -Name WindowsProcess -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'
  Arguments = ''
}
```

### <span data-ttu-id="80d46-116">例 2: 指定したモジュールのリソースのテストメソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="80d46-116">Example 2: Invoke the Test method of a resource for a specified module</span></span>

<span data-ttu-id="80d46-117">この例では、 **Windowsprocess** という名前のリソースの **Test** メソッドを呼び出します。これは **PSDesiredStateConfiguration** という名前のモジュールにあります。</span><span class="sxs-lookup"><span data-stu-id="80d46-117">This example invokes the **Test** method of a resource named **WindowsProcess**, which is in the module named **PSDesiredStateConfiguration**.</span></span>

```powershell
$SplatParam = @{
  Name = 'WindowsProcess'
  ModuleName = 'PSDesiredStateConfiguration'
  Property = @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''}
  Method = Test
}

Invoke-DscResource @SplatParam
```

## <span data-ttu-id="80d46-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="80d46-118">PARAMETERS</span></span>

### <span data-ttu-id="80d46-119">-メソッド</span><span class="sxs-lookup"><span data-stu-id="80d46-119">-Method</span></span>

<span data-ttu-id="80d46-120">このコマンドレットが呼び出すリソースのメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="80d46-120">Specifies the method of the resource that this cmdlet invokes.</span></span> <span data-ttu-id="80d46-121">このパラメーターに指定できる値は、 **Get**、 **Set**、および **Test** です。</span><span class="sxs-lookup"><span data-stu-id="80d46-121">The acceptable values for this parameter are: **Get**, **Set**, and **Test**.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="80d46-122">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="80d46-122">-ModuleName</span></span>

<span data-ttu-id="80d46-123">このコマンドレットが指定されたリソースを呼び出すモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="80d46-123">Specifies the name of the module from which this cmdlet invokes the specified resource.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="80d46-124">-Name</span><span class="sxs-lookup"><span data-stu-id="80d46-124">-Name</span></span>

<span data-ttu-id="80d46-125">開始する DSC リソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="80d46-125">Specifies the name of the DSC resource to start.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="80d46-126">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="80d46-126">-Property</span></span>

<span data-ttu-id="80d46-127">ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。</span><span class="sxs-lookup"><span data-stu-id="80d46-127">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="80d46-128">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="80d46-128">CommonParameters</span></span>

<span data-ttu-id="80d46-129">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="80d46-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="80d46-130">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80d46-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="80d46-131">入力</span><span class="sxs-lookup"><span data-stu-id="80d46-131">INPUTS</span></span>

### <span data-ttu-id="80d46-132">System.String</span><span class="sxs-lookup"><span data-stu-id="80d46-132">System.String</span></span>

### <span data-ttu-id="80d46-133">Microsoft. PowerShell. コマンドの通知</span><span class="sxs-lookup"><span data-stu-id="80d46-133">Microsoft.PowerShell.Commands.ModuleSpecification</span></span>

## <span data-ttu-id="80d46-134">出力</span><span class="sxs-lookup"><span data-stu-id="80d46-134">OUTPUTS</span></span>

### <span data-ttu-id="80d46-135">System.Object</span><span class="sxs-lookup"><span data-stu-id="80d46-135">System.Object</span></span>

## <span data-ttu-id="80d46-136">注</span><span class="sxs-lookup"><span data-stu-id="80d46-136">NOTES</span></span>

- <span data-ttu-id="80d46-137">以前は、Windows PowerShell 5.1 のリソースは、 **PsDscRunAsCredential** キーを使用してユーザーコンテキストで指定されていない限り、システムコンテキストで実行されていました。</span><span class="sxs-lookup"><span data-stu-id="80d46-137">Previously, Windows PowerShell 5.1 resources ran under System context unless specified with user context using the key **PsDscRunAsCredential**.</span></span> <span data-ttu-id="80d46-138">PowerShell 7.0 では、リソースはユーザーのコンテキストで実行され、 **PsDscRunAsCredential** はサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="80d46-138">In PowerShell 7.0, Resources run in the user's context, and **PsDscRunAsCredential** is no longer supported.</span></span> <span data-ttu-id="80d46-139">このキーを使用する以前の構成では、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="80d46-139">Previous configurations using this key will throw an exception.</span></span>

- <span data-ttu-id="80d46-140">PowerShell 7 の時点で、は `Invoke-DscResource` WMI DSC リソースの呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="80d46-140">As of PowerShell 7, `Invoke-DscResource` no longer supports invoking WMI DSC resources.</span></span> <span data-ttu-id="80d46-141">これには、**PSDesiredStateConfiguration** の **ファイル** リソースと **ログ** リソースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="80d46-141">This includes the **File** and **Log** resources in **PSDesiredStateConfiguration**.</span></span>

## <span data-ttu-id="80d46-142">関連リンク</span><span class="sxs-lookup"><span data-stu-id="80d46-142">RELATED LINKS</span></span>

[<span data-ttu-id="80d46-143">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="80d46-143">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="80d46-144">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="80d46-144">Get-DscResource</span></span>](Get-DscResource.md)
