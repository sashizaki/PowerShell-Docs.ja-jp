---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: 8425c3e68573fe214ec5de465c8492e0bf99b309
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "93219536"
---
# <span data-ttu-id="a5bdb-103">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="a5bdb-103">Invoke-DscResource</span></span>

## <span data-ttu-id="a5bdb-104">概要</span><span class="sxs-lookup"><span data-stu-id="a5bdb-104">SYNOPSIS</span></span>
<span data-ttu-id="a5bdb-105">指定された PowerShell Desired State Configuration (DSC) リソースのメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-105">Runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

## <span data-ttu-id="a5bdb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a5bdb-106">SYNTAX</span></span>

```
Invoke-DscResource [-Name] <String> [[-ModuleName] <ModuleSpecification>] [-Method] <String>
 [-Property] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="a5bdb-107">Description</span><span class="sxs-lookup"><span data-stu-id="a5bdb-107">DESCRIPTION</span></span>

<span data-ttu-id="a5bdb-108">`Invoke-DscResource` コマンドレットは、指定された PowerShell Desired State Configuration (DSC) リソースのメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-108">The `Invoke-DscResource` cmdlet runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

<span data-ttu-id="a5bdb-109">このコマンドレットは、構成ドキュメントを作成せずに、DSC リソースを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-109">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span> <span data-ttu-id="a5bdb-110">このコマンドレットを使用すると、構成管理製品は DSC リソースを使用して windows または Linux を管理できます。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-110">Using this cmdlet, configuration management products can manage windows or Linux by using DSC resources.</span></span> <span data-ttu-id="a5bdb-111">DSC エンジンの実行中、デバッグが有効になっている場合は、このコマンドレットでリソースのデバッグを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-111">This cmdlet also enables debugging of resources when the DSC engine is running with debugging enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="a5bdb-112">`Invoke-DscResource` は、PowerShell 7 の試験的な機能です。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-112">`Invoke-DscResource` is an experimental feature in PowerShell 7.</span></span> <span data-ttu-id="a5bdb-113">コマンドレットを使用するには、次のコマンドを使用して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-113">To use the cmdlet, you must enable it using the following command.</span></span>
>
> `Enable-ExperimentalFeature PSDesiredStateConfiguration.InvokeDscResource`

## <span data-ttu-id="a5bdb-114">例</span><span class="sxs-lookup"><span data-stu-id="a5bdb-114">EXAMPLES</span></span>

### <span data-ttu-id="a5bdb-115">例 1: 必須プロパティを指定してリソースの Set メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="a5bdb-115">Example 1: Invoke the Set method of a resource by specifying its mandatory properties</span></span>

<span data-ttu-id="a5bdb-116">この例では、 **Windowsprocess** という名前のリソースの **Set** メソッドを呼び出し、指定された Windows プロセスを開始するための必須の **パス** と **引数** のプロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-116">This example invokes the **Set** method of a resource named **WindowsProcess** and provides the mandatory **Path** and **Arguments** properties to start the specified Windows process.</span></span>

```powershell
Invoke-DscResource -Name WindowsProcess -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'
  Arguments = ''
}
```

### <span data-ttu-id="a5bdb-117">例 2: 指定したモジュールのリソースのテストメソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="a5bdb-117">Example 2: Invoke the Test method of a resource for a specified module</span></span>

<span data-ttu-id="a5bdb-118">この例では、 **Windowsprocess** という名前のリソースの **Test** メソッドを呼び出します。これは **PSDesiredStateConfiguration** という名前のモジュールにあります。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-118">This example invokes the **Test** method of a resource named **WindowsProcess** , which is in the module named **PSDesiredStateConfiguration**.</span></span>

```powershell
$SplatParam = @{
  Name = 'WindowsProcess'
  ModuleName = 'PSDesiredStateConfiguration'
  Property = @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''}
  Method = Test
}

Invoke-DscResource @SplatParam
```

## <span data-ttu-id="a5bdb-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a5bdb-119">PARAMETERS</span></span>

### <span data-ttu-id="a5bdb-120">-メソッド</span><span class="sxs-lookup"><span data-stu-id="a5bdb-120">-Method</span></span>

<span data-ttu-id="a5bdb-121">このコマンドレットが呼び出すリソースのメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-121">Specifies the method of the resource that this cmdlet invokes.</span></span> <span data-ttu-id="a5bdb-122">このパラメーターに指定できる値は、 **Get** 、 **Set** 、および **Test** です。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-122">The acceptable values for this parameter are: **Get** , **Set** , and **Test**.</span></span>

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

### <span data-ttu-id="a5bdb-123">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="a5bdb-123">-ModuleName</span></span>

<span data-ttu-id="a5bdb-124">このコマンドレットが指定されたリソースを呼び出すモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-124">Specifies the name of the module from which this cmdlet invokes the specified resource.</span></span>

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

### <span data-ttu-id="a5bdb-125">-Name</span><span class="sxs-lookup"><span data-stu-id="a5bdb-125">-Name</span></span>

<span data-ttu-id="a5bdb-126">開始する DSC リソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-126">Specifies the name of the DSC resource to start.</span></span>

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

### <span data-ttu-id="a5bdb-127">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="a5bdb-127">-Property</span></span>

<span data-ttu-id="a5bdb-128">ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-128">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span>

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

### <span data-ttu-id="a5bdb-129">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5bdb-129">CommonParameters</span></span>

<span data-ttu-id="a5bdb-130">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a5bdb-131">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a5bdb-132">入力</span><span class="sxs-lookup"><span data-stu-id="a5bdb-132">INPUTS</span></span>

### <span data-ttu-id="a5bdb-133">System.String</span><span class="sxs-lookup"><span data-stu-id="a5bdb-133">System.String</span></span>

### <span data-ttu-id="a5bdb-134">Microsoft. PowerShell. コマンドの通知</span><span class="sxs-lookup"><span data-stu-id="a5bdb-134">Microsoft.PowerShell.Commands.ModuleSpecification</span></span>

## <span data-ttu-id="a5bdb-135">出力</span><span class="sxs-lookup"><span data-stu-id="a5bdb-135">OUTPUTS</span></span>

### <span data-ttu-id="a5bdb-136">System.Object</span><span class="sxs-lookup"><span data-stu-id="a5bdb-136">System.Object</span></span>

## <span data-ttu-id="a5bdb-137">注</span><span class="sxs-lookup"><span data-stu-id="a5bdb-137">NOTES</span></span>

- <span data-ttu-id="a5bdb-138">以前は、Windows PowerShell 5.1 のリソースは、 **PsDscRunAsCredential** キーを使用してユーザーコンテキストで指定されていない限り、システムコンテキストで実行されていました。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-138">Previously, Windows PowerShell 5.1 resources ran under System context unless specified with user context using the key **PsDscRunAsCredential**.</span></span> <span data-ttu-id="a5bdb-139">PowerShell 7.0 では、リソースはユーザーのコンテキストで実行され、 **PsDscRunAsCredential** はサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-139">In PowerShell 7.0, Resources run in the user's context, and **PsDscRunAsCredential** is no longer supported.</span></span> <span data-ttu-id="a5bdb-140">このキーを使用する以前の構成では、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-140">Previous configurations using this key will throw an exception.</span></span>

- <span data-ttu-id="a5bdb-141">PowerShell 7 の時点で、は `Invoke-DscResource` WMI DSC リソースの呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-141">As of PowerShell 7, `Invoke-DscResource` no longer supports invoking WMI DSC resources.</span></span> <span data-ttu-id="a5bdb-142">これには、 **PSDesiredStateConfiguration** の **ファイル** リソースと **ログ** リソースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a5bdb-142">This includes the **File** and **Log** resources in **PSDesiredStateConfiguration**.</span></span>

## <span data-ttu-id="a5bdb-143">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a5bdb-143">RELATED LINKS</span></span>

[<span data-ttu-id="a5bdb-144">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="a5bdb-144">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="a5bdb-145">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="a5bdb-145">Get-DscResource</span></span>](Get-DscResource.md)
