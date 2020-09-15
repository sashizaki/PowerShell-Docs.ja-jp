---
ms.date: 07/16/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Registry リソース
ms.openlocfilehash: da4be9152a58d9945051f9c811270e871612ca0d
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463620"
---
# <a name="dsc-registry-resource"></a><span data-ttu-id="16e51-103">DSC Registry リソース</span><span class="sxs-lookup"><span data-stu-id="16e51-103">DSC Registry Resource</span></span>

> <span data-ttu-id="16e51-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="16e51-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="16e51-105">Windows PowerShell Desired State Configuration (DSC) の **Registry** リソースは、ターゲット ノードでレジストリ キーと値を管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="16e51-105">The **Registry** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage registry keys and values on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="16e51-106">構文</span><span class="sxs-lookup"><span data-stu-id="16e51-106">Syntax</span></span>

```Syntax
Registry [string] #ResourceName
{
    Key = [string]
    ValueName = [string]
    [ Force =  [bool]   ]
    [ Hex = [bool] ]
    [ ValueData = [string[]] ]
    [ ValueType = [string] { Binary | Dword | ExpandString | MultiString | Qword | String }  ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Present | Absent }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="16e51-107">Properties</span><span class="sxs-lookup"><span data-stu-id="16e51-107">Properties</span></span>

|<span data-ttu-id="16e51-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="16e51-108">Property</span></span> |<span data-ttu-id="16e51-109">説明</span><span class="sxs-lookup"><span data-stu-id="16e51-109">Description</span></span> |
|---|---|
|<span data-ttu-id="16e51-110">Key</span><span class="sxs-lookup"><span data-stu-id="16e51-110">Key</span></span> |<span data-ttu-id="16e51-111">特定の状態を確認するレジストリ キーのパスを示します。</span><span class="sxs-lookup"><span data-stu-id="16e51-111">Indicates the path of the registry key for which you want to ensure a specific state.</span></span> <span data-ttu-id="16e51-112">このパスには、ハイブを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="16e51-112">This path must include the hive.</span></span> |
|<span data-ttu-id="16e51-113">ValueName</span><span class="sxs-lookup"><span data-stu-id="16e51-113">ValueName</span></span> |<span data-ttu-id="16e51-114">レジストリ値の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="16e51-114">Indicates the name of the registry value.</span></span> <span data-ttu-id="16e51-115">レジストリ キーを追加または削除するには、**ValueType** または **ValueData** を指定せずに、このプロパティを空の文字列で指定します。</span><span class="sxs-lookup"><span data-stu-id="16e51-115">To add or remove a registry key, specify this property as an empty string without specifying **ValueType** or **ValueData**.</span></span> <span data-ttu-id="16e51-116">レジストリ キーの既定値を変更または削除するには、**ValueType** または **ValueData** を指定し、このプロパティを空の文字列で指定します。</span><span class="sxs-lookup"><span data-stu-id="16e51-116">To modify or remove the default value of a registry key, specify this property as an empty string while also specifying **ValueType** or **ValueData**.</span></span> |
|<span data-ttu-id="16e51-117">Force</span><span class="sxs-lookup"><span data-stu-id="16e51-117">Force</span></span> |<span data-ttu-id="16e51-118">指定のレジストリ キーが存在する場合、**Force** はそのキーを新しい値で上書きします。</span><span class="sxs-lookup"><span data-stu-id="16e51-118">If the specified registry key is present, **Force** overwrites it with the new value.</span></span> <span data-ttu-id="16e51-119">レジストリ キーをサブキーと共に削除する場合は、これが `$true` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="16e51-119">If deleting a registry key with subkeys, this needs to be `$true`.</span></span> |
|<span data-ttu-id="16e51-120">Hex</span><span class="sxs-lookup"><span data-stu-id="16e51-120">Hex</span></span> |<span data-ttu-id="16e51-121">16 進形式でデータを表現するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="16e51-121">Indicates if data will be expressed in hexadecimal format.</span></span> <span data-ttu-id="16e51-122">指定した場合、DWORD/QWORD 値データが 16 進形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="16e51-122">If specified, the DWORD/QWORD value data is presented in hexadecimal format.</span></span> <span data-ttu-id="16e51-123">その他の種類に対しては無効です。</span><span class="sxs-lookup"><span data-stu-id="16e51-123">Not valid for other types.</span></span> <span data-ttu-id="16e51-124">既定値は `$false` です。</span><span class="sxs-lookup"><span data-stu-id="16e51-124">The default value is `$false`.</span></span> |
|<span data-ttu-id="16e51-125">ValueData</span><span class="sxs-lookup"><span data-stu-id="16e51-125">ValueData</span></span> |<span data-ttu-id="16e51-126">レジストリ値のデータ。</span><span class="sxs-lookup"><span data-stu-id="16e51-126">The data for the registry value.</span></span> |
|<span data-ttu-id="16e51-127">ValueType</span><span class="sxs-lookup"><span data-stu-id="16e51-127">ValueType</span></span> |<span data-ttu-id="16e51-128">値の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="16e51-128">Indicates the type of the value.</span></span> <span data-ttu-id="16e51-129">サポートされている型は次のとおりです。**String** (REG_SZ)、**Binary** (REG-BINARY)、**Dword** (32 ビット REG_DWORD)、**Qword** (64 ビット REG_QWORD)、**MultiString** (REG_MULTI_SZ)、**ExpandString** (REG_EXPAND_SZ)。</span><span class="sxs-lookup"><span data-stu-id="16e51-129">The supported types are: **String** (REG_SZ), **Binary** (REG-BINARY), **Dword** (32-bit REG_DWORD), **Qword** (64-bit REG_QWORD), **MultiString** (REG_MULTI_SZ), **ExpandString** (REG_EXPAND_SZ).</span></span> |

## <a name="common-properties"></a><span data-ttu-id="16e51-130">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="16e51-130">Common properties</span></span>

|<span data-ttu-id="16e51-131">プロパティ</span><span class="sxs-lookup"><span data-stu-id="16e51-131">Property</span></span> |<span data-ttu-id="16e51-132">説明</span><span class="sxs-lookup"><span data-stu-id="16e51-132">Description</span></span> |
|---|---|
|<span data-ttu-id="16e51-133">DependsOn</span><span class="sxs-lookup"><span data-stu-id="16e51-133">DependsOn</span></span> |<span data-ttu-id="16e51-134">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="16e51-134">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="16e51-135">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="16e51-135">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="16e51-136">Ensure</span><span class="sxs-lookup"><span data-stu-id="16e51-136">Ensure</span></span> |<span data-ttu-id="16e51-137">キーと値が存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="16e51-137">Indicates if the key and value exist.</span></span> <span data-ttu-id="16e51-138">それらが確実に実行されるようにするには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="16e51-138">To ensure that they do, set this property to **Present**.</span></span> <span data-ttu-id="16e51-139">それらが存在しないことを保証するには、このプロパティを **Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="16e51-139">To ensure that they do not exist, set the property to **Absent**.</span></span> <span data-ttu-id="16e51-140">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="16e51-140">The default value is **Present**.</span></span> |
|<span data-ttu-id="16e51-141">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="16e51-141">PsDscRunAsCredential</span></span> |<span data-ttu-id="16e51-142">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="16e51-142">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="16e51-143">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="16e51-143">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="16e51-144">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16e51-144">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="examples"></a><span data-ttu-id="16e51-145">例</span><span class="sxs-lookup"><span data-stu-id="16e51-145">Examples</span></span>

### <a name="example-1-ensure-specified-value-and-data-under-specified-registry-key"></a><span data-ttu-id="16e51-146">例 1:指定された値とデータが指定されたレジストリ キーの下に存在することを確認する</span><span class="sxs-lookup"><span data-stu-id="16e51-146">Example 1: Ensure specified Value and Data under specified registry key</span></span>

<span data-ttu-id="16e51-147">この例では、"ExampleKey1" という名前のキーの下にあるレジストリ値 "TestValue" が `HKEY\_LOCAL\_MACHINE` ハイブに存在し、データ "TestData" を含んでいることを確認します。</span><span class="sxs-lookup"><span data-stu-id="16e51-147">This example ensures that the registry value "TestValue" under a key named "ExampleKey1" is present in the `HKEY\_LOCAL\_MACHINE` hive and has the data "TestData".</span></span>

```powershell
Configuration RegistryTest
{
    Registry RegistryExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Key         = "HKEY_LOCAL_MACHINE\SOFTWARE\ExampleKey1"
        ValueName   = "TestValue"
        ValueData   = "TestData"
    }
}
```

### <a name="example-2-ensure-specified-registry-key-exists"></a><span data-ttu-id="16e51-148">例 2:指定されたレジストリ キーが存在することを確認する</span><span class="sxs-lookup"><span data-stu-id="16e51-148">Example 2: Ensure specified registry key exists</span></span>

<span data-ttu-id="16e51-149">次の例では、"ExampleKey2" という名前のキーが **HKEY\_LOCAL\_MACHINE** ハイブに存在していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="16e51-149">This example ensures that a key named "ExampleKey2" is present in the **HKEY\_LOCAL\_MACHINE** hive.</span></span>

```powershell
Configuration RegistryTest
{
    Registry RegistryExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Key         = "HKEY_LOCAL_MACHINE\SOFTWARE\ExampleKey2"
        ValueName   = ""
    }
}
```

> [!NOTE]
> <span data-ttu-id="16e51-150">`HKEY_CURRENT_USER` ハイブのレジストリ設定を変更するには、構成がシステムとしてではなく、ユーザーの資格情報を使用して実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="16e51-150">Changing a registry setting in the `HKEY_CURRENT_USER` hive requires that the configuration runs with user credentials, rather than as the system.</span></span> <span data-ttu-id="16e51-151">**PsDscRunAsCredential** プロパティを使用すれば、構成に対してユーザー資格情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="16e51-151">You can use the **PsDscRunAsCredential** property to specify user credentials for the configuration.</span></span> <span data-ttu-id="16e51-152">例については、「[ユーザーの資格情報を指定して DSC を実行する](../../../configurations/runAsUser.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="16e51-152">For an example, see [Running DSC with user credentials](../../../configurations/runAsUser.md).</span></span>
