---
ms.date: 12/12/2018
keywords: dsc,powershell,リソース,ギャラリー,セットアップ
title: 構成にパラメーターを追加する
ms.openlocfilehash: 9dd9f2be58c13840be2b24e7e21a0d4af79b67cc
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "80263154"
---
# <a name="add-parameters-to-a-configuration"></a><span data-ttu-id="63e67-103">構成にパラメーターを追加する</span><span class="sxs-lookup"><span data-stu-id="63e67-103">Add Parameters to a Configuration</span></span>

<span data-ttu-id="63e67-104">関数と同様に、[構成](configurations.md)もパラメーター化し、ユーザー入力に基づいて構成をいっそう動的にすることができます。</span><span class="sxs-lookup"><span data-stu-id="63e67-104">Like Functions, [Configurations](configurations.md) can be parameterized to allow more dynamic configurations based on user input.</span></span> <span data-ttu-id="63e67-105">手順は、「[Functions with Parameters (パラメーターを使用する関数)](/powershell/module/microsoft.powershell.core/about/about_functions)」で説明されているものと似ています。</span><span class="sxs-lookup"><span data-stu-id="63e67-105">The steps are similar to those described in [Functions with Parameters](/powershell/module/microsoft.powershell.core/about/about_functions).</span></span>

<span data-ttu-id="63e67-106">この例では、"スプーラー" サービスを "実行中" に構成する基本的な構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="63e67-106">This example starts with a basic Configuration that configures the "Spooler" service to be "Running".</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node localhost
    {
        Service 'Spooler'
        {
            Name = 'Spooler'
            State = 'Running'
        }
    }
}
```

## <a name="built-in-configuration-parameters"></a><span data-ttu-id="63e67-107">組み込み構成パラメーター</span><span class="sxs-lookup"><span data-stu-id="63e67-107">Built-in Configuration parameters</span></span>

<span data-ttu-id="63e67-108">関数とは異なり、[CmdletBinding](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute) 属性では機能は追加されません。</span><span class="sxs-lookup"><span data-stu-id="63e67-108">Unlike a Function though, the [CmdletBinding](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute) attribute adds no functionality.</span></span> <span data-ttu-id="63e67-109">[共通パラメーター](/powershell/module/microsoft.powershell.core/about/about_commonparameters)に加えて、構成では次の組み込みパラメーターを定義せずに使用できます。</span><span class="sxs-lookup"><span data-stu-id="63e67-109">In addition to [Common Parameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters), Configurations can also use the following built in parameters, without requiring you to define them.</span></span>

|        <span data-ttu-id="63e67-110">パラメーター</span><span class="sxs-lookup"><span data-stu-id="63e67-110">Parameter</span></span>        |                                         <span data-ttu-id="63e67-111">説明</span><span class="sxs-lookup"><span data-stu-id="63e67-111">Description</span></span>                                          |
| ----------------------- | -------------------------------------------------------------------------------------------- |
| `-InstanceName`         | <span data-ttu-id="63e67-112">[複合構成](compositeconfigs.md)の定義で使用されます</span><span class="sxs-lookup"><span data-stu-id="63e67-112">Used in defining [Composite Configurations](compositeconfigs.md)</span></span>                             |
| `-DependsOn`            | <span data-ttu-id="63e67-113">[複合構成](compositeconfigs.md)の定義で使用されます</span><span class="sxs-lookup"><span data-stu-id="63e67-113">Used in defining [Composite Configurations](compositeconfigs.md)</span></span>                             |
| `-PSDSCRunAsCredential` | <span data-ttu-id="63e67-114">[複合構成](compositeconfigs.md)の定義で使用されます</span><span class="sxs-lookup"><span data-stu-id="63e67-114">Used in defining [Composite Configurations](compositeconfigs.md)</span></span>                             |
| `-ConfigurationData`    | <span data-ttu-id="63e67-115">構成で使用する構造化[構成データ](configData.md)を渡すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="63e67-115">Used to pass in structured [Configuration Data](configData.md) for use in the Configuration.</span></span> |
| `-OutputPath`           | <span data-ttu-id="63e67-116">"\<コンピューター名\>.mof" ファイルがコンパイルされる場所を指定するために使用されます</span><span class="sxs-lookup"><span data-stu-id="63e67-116">Used to specify where your "\<computername\>.mof" file will be compiled</span></span>                      |

## <a name="adding-your-own-parameters-to-configurations"></a><span data-ttu-id="63e67-117">構成に独自のパラメーターを追加する</span><span class="sxs-lookup"><span data-stu-id="63e67-117">Adding your own parameters to Configurations</span></span>

<span data-ttu-id="63e67-118">組み込みパラメーターに加えて、独自のパラメーターを構成に追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="63e67-118">In addition to the built-in parameters, you can also add your own parameters to your Configurations.</span></span>
<span data-ttu-id="63e67-119">関数と同様、パラメーター ブロックを構成の宣言内で直接指定します。</span><span class="sxs-lookup"><span data-stu-id="63e67-119">The parameter block goes directly inside the Configuration declaration, just like a Function.</span></span> <span data-ttu-id="63e67-120">構成のパラメーター ブロックは、すべての**ノード**宣言の外部で、すべての "*インポート*" ステートメントより上に置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="63e67-120">A Configuration parameter block should be outside any **Node** declarations, and above any *import* statements.</span></span> <span data-ttu-id="63e67-121">パラメーターを追加することにより、構成をいっそう堅牢で動的にすることができます。</span><span class="sxs-lookup"><span data-stu-id="63e67-121">By adding parameters, you can make your Configurations more robust and dynamic.</span></span>

```powershell
Configuration TestConfig
{
    param
    (

    )
```

### <a name="add-a-computername-parameter"></a><span data-ttu-id="63e67-122">ComputerName パラメーターを追加する</span><span class="sxs-lookup"><span data-stu-id="63e67-122">Add a ComputerName parameter</span></span>

<span data-ttu-id="63e67-123">追加する可能性がある最初のパラメーターは `-Computername` で、構成に渡した `-Computername` に対して ".mof" ファイルを動的にコンパイルできるようにします。</span><span class="sxs-lookup"><span data-stu-id="63e67-123">The first parameter you might add is a `-Computername` parameter so you can dynamically compile a ".mof" file for any `-Computername` you pass to your configuration.</span></span> <span data-ttu-id="63e67-124">関数と同様、ユーザーが `-ComputerName` に値を渡さない場合のため、既定値を定義することもできます</span><span class="sxs-lookup"><span data-stu-id="63e67-124">Like Functions, you can also define a default value, in case the user does not pass in a value for `-ComputerName`</span></span>

```powershell
param
(
    [String]
    $ComputerName="localhost"
)
```

<span data-ttu-id="63e67-125">構成内では、Node ブロックを定義するときに独自の `-ComputerName` パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="63e67-125">Within your configuration, you can then specify your `-ComputerName` parameter when defining your Node block.</span></span>

```powershell
Node $ComputerName
{

}
```

### <a name="calling-your-configuration-with-parameters"></a><span data-ttu-id="63e67-126">パラメーターを持つ構成を呼び出す</span><span class="sxs-lookup"><span data-stu-id="63e67-126">Calling your Configuration with parameters</span></span>

<span data-ttu-id="63e67-127">構成にパラメーターを追加した後は、コマンドレットの場合と同じように使用できます。</span><span class="sxs-lookup"><span data-stu-id="63e67-127">After you have added parameters to your Configuration, you can use them just like you would with a cmdlet.</span></span>

```powershell
TestConfig -ComputerName "server01"
```

### <a name="compiling-multiple-mof-files"></a><span data-ttu-id="63e67-128">複数の .mof ファイルをコンパイルする</span><span class="sxs-lookup"><span data-stu-id="63e67-128">Compiling multiple .mof files</span></span>

<span data-ttu-id="63e67-129">Node ブロックでは、コンマ区切りのコンピューター名のリストを受け取ることもでき、それぞれに対して ".mof" ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="63e67-129">The Node block can also accept a comma-separated list of computer names and will generate ".mof" files for each.</span></span> <span data-ttu-id="63e67-130">次の例を実行し、`-ComputerName` パラメーターに渡されるすべてのコンピューターに対して ".mof" ファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="63e67-130">You can run the following example to generate ".mof" files for all of the computers passed to the `-ComputerName` parameter.</span></span>

```powershell
Configuration TestConfig
{
    param
    (
        [String]
        $ComputerName="localhost"
    )

    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service 'Spooler'
        {
            Name = 'Spooler'
            State = 'Running'
        }
    }
}

TestConfig -ComputerName "server01", "server02", "server03"
```

## <a name="advanced-parameters-in-configurations"></a><span data-ttu-id="63e67-131">構成の高度なパラメーター</span><span class="sxs-lookup"><span data-stu-id="63e67-131">Advanced parameters in Configurations</span></span>

<span data-ttu-id="63e67-132">`-ComputerName` パラメーターに加えて、サービス名と状態のパラメーターを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="63e67-132">In addition to a `-ComputerName` parameter, we can add parameters for the service name and state.</span></span>
<span data-ttu-id="63e67-133">次の例では、`-ServiceName` パラメーターでパラメーター ブロックを追加し、それを使用して **Service** リソース ブロックを動的に定義しています。</span><span class="sxs-lookup"><span data-stu-id="63e67-133">The following example adds a parameter block with a `-ServiceName` parameter and uses it to dynamically define the **Service** resource block.</span></span> <span data-ttu-id="63e67-134">また、`-State` パラメーターを追加し、**Service** リソース ブロック内で **State** を動的に定義しています。</span><span class="sxs-lookup"><span data-stu-id="63e67-134">It also adds a `-State` parameter to dynamically define the **State** in the **Service** resource block.</span></span>

```powershell
Configuration TestConfig
{
    param
    (
        [String]
        $ServiceName,

        [String]
        $State,

        [String]
        $ComputerName="localhost"
    )

    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service $ServiceName
        {
            Name = $ServiceName
            State = $State
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="63e67-135">より高度なシナリオでは、動的データを構造化された[構成データ](configData.md)に移動した方が合理的な場合があります。</span><span class="sxs-lookup"><span data-stu-id="63e67-135">In more advanced scenarios, it might make more sense to move your dynamic data into a structured [Configuration Data](configData.md).</span></span>

<span data-ttu-id="63e67-136">現在の例の構成では、動的な `$ServiceName` を受け取っていますが、指定されないと、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="63e67-136">The example Configuration now takes a dynamic `$ServiceName`, but if one is not specified, compiling results in an error.</span></span> <span data-ttu-id="63e67-137">次の例のように、既定値を追加できます。</span><span class="sxs-lookup"><span data-stu-id="63e67-137">You could add a default value like this example.</span></span>

```powershell
[String]
$ServiceName="Spooler"
```

<span data-ttu-id="63e67-138">ただし、この場合は、`$ServiceName` パラメーターの値の指定をユーザーに単に強制する方が適切です。</span><span class="sxs-lookup"><span data-stu-id="63e67-138">In this instance though, it makes more sense to simply force the user to specify a value for the `$ServiceName` parameter.</span></span> <span data-ttu-id="63e67-139">`parameter` 属性を使用すると、構成のパラメーターにさらに検証とパイプラインのサポートを追加できます。</span><span class="sxs-lookup"><span data-stu-id="63e67-139">The `parameter` attribute allows you to add further validation and pipeline support to your Configuration's parameters.</span></span>

<span data-ttu-id="63e67-140">次の例のように、すべてのパラメーター宣言の上に `parameter` 属性ブロックを追加します。</span><span class="sxs-lookup"><span data-stu-id="63e67-140">Above any parameter declaration, add the `parameter` attribute block as in the example below.</span></span>

```powershell
[parameter()]
[String]
$ServiceName
```

<span data-ttu-id="63e67-141">各 `parameter` 属性に対して引数を指定し、定義されているパラメーターの要素を制御できます。</span><span class="sxs-lookup"><span data-stu-id="63e67-141">You can specify arguments to each `parameter` attribute, to control aspects of the defined parameter.</span></span> <span data-ttu-id="63e67-142">次の例では、`$ServiceName` を**必須**パラメーターにしています。</span><span class="sxs-lookup"><span data-stu-id="63e67-142">The following example makes the `$ServiceName` a **Mandatory** parameter.</span></span>

```powershell
[parameter(Mandatory)]
[String]
$ServiceName
```

<span data-ttu-id="63e67-143">`$State` パラメーターでは、事前に定義されているセット (Running、Stopped など) 以外の値をユーザーが指定するのを防ぐため、`ValidationSet*` 属性でユーザーがそのような値を指定できないようにします。</span><span class="sxs-lookup"><span data-stu-id="63e67-143">For the `$State` parameter, we would like to prevent the user from specifying values outside of a predefined set (like Running, Stopped) the `ValidationSet*`attribute would prevent the user from specifying values outside of a predefined set (like Running, Stopped).</span></span> <span data-ttu-id="63e67-144">次の例では、`ValidationSet` 属性を `$State` パラメーターに追加しています。</span><span class="sxs-lookup"><span data-stu-id="63e67-144">The following example adds the `ValidationSet` attribute to the `$State` parameter.</span></span> <span data-ttu-id="63e67-145">`$State` パラメーターを**必須**にはしたくないので、既定値を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63e67-145">Since we do not want to make the `$State` parameter **Mandatory**, we will need to add a default value for it.</span></span>

```powershell
[ValidateSet("Running", "Stopped")]
[String]
$State="Running"
```

> [!NOTE]
> <span data-ttu-id="63e67-146">`validation` 属性を使用するときは、`parameter` 属性を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="63e67-146">You do not need to specify a `parameter` attribute when using a `validation` attribute.</span></span>

<span data-ttu-id="63e67-147">`parameter` および検証属性について詳しくは、[関数の高度なパラメーター](/powershell/module/microsoft.powershell.core/about/about_Functions_Advanced_Parameters)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63e67-147">You can read more about the `parameter` and validation attributes in [about_Functions_Advanced_Parameters](/powershell/module/microsoft.powershell.core/about/about_Functions_Advanced_Parameters).</span></span>

## <a name="fully-parameterized-configuration"></a><span data-ttu-id="63e67-148">完全にパラメーター化された構成</span><span class="sxs-lookup"><span data-stu-id="63e67-148">Fully parameterized Configuration</span></span>

<span data-ttu-id="63e67-149">ユーザーに `-InstanceName` と `-ServiceName` の指定を強制し、`-State` パラメーターを検証する、パラメーター化された構成ができました。</span><span class="sxs-lookup"><span data-stu-id="63e67-149">We now have a parameterized Configuration that forces the user to specify an `-InstanceName`, `-ServiceName`, and validates the `-State` parameter.</span></span>

```powershell
Configuration TestConfig
{
    param
    (
        [parameter(Mandatory)]
        [String]
        $ServiceName,

        [ValidateSet("Running","Stopped")]
        [String]
        $State="Running",

        [String]
        $ComputerName="localhost",
    )

    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service $ServiceName
        {
            Name = $ServiceName
            State = $State
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="63e67-150">参照</span><span class="sxs-lookup"><span data-stu-id="63e67-150">See also</span></span>

- [<span data-ttu-id="63e67-151">DSC 構成のヘルプを作成する</span><span class="sxs-lookup"><span data-stu-id="63e67-151">Write help for DSC configurations</span></span>](configHelp.md)
- [<span data-ttu-id="63e67-152">動的な構成</span><span class="sxs-lookup"><span data-stu-id="63e67-152">Dynamic Configurations</span></span>](flow-control-in-configurations.md)
- [<span data-ttu-id="63e67-153">構成で構成データを使用する</span><span class="sxs-lookup"><span data-stu-id="63e67-153">Use Configuration Data in your Configurations</span></span>](configData.md)
- [<span data-ttu-id="63e67-154">構成と環境データを分離する</span><span class="sxs-lookup"><span data-stu-id="63e67-154">Separate configuration and environment data</span></span>](separatingEnvData.md)
