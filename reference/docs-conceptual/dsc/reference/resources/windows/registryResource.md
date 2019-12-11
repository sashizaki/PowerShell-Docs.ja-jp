---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Registry リソース
ms.openlocfilehash: be2f9134368784ad2d208362104ce046c49492e0
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953079"
---
# <a name="dsc-registry-resource"></a><span data-ttu-id="6b2cb-103">DSC Registry リソース</span><span class="sxs-lookup"><span data-stu-id="6b2cb-103">DSC Registry Resource</span></span>

> <span data-ttu-id="6b2cb-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="6b2cb-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="6b2cb-105">Windows PowerShell Desired State Configuration (DSC) の **Registry** リソースは、ターゲット ノードでレジストリ キーと値を管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-105">The **Registry** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage registry keys and values on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="6b2cb-106">構文</span><span class="sxs-lookup"><span data-stu-id="6b2cb-106">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="6b2cb-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6b2cb-107">Properties</span></span>

|<span data-ttu-id="6b2cb-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6b2cb-108">Property</span></span> |<span data-ttu-id="6b2cb-109">説明</span><span class="sxs-lookup"><span data-stu-id="6b2cb-109">Description</span></span> |
|---|---|
|<span data-ttu-id="6b2cb-110">キー</span><span class="sxs-lookup"><span data-stu-id="6b2cb-110">Key</span></span> |<span data-ttu-id="6b2cb-111">特定の状態を確認するレジストリ キーのパスを示します。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-111">Indicates the path of the registry key for which you want to ensure a specific state.</span></span> <span data-ttu-id="6b2cb-112">このパスには、ハイブを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-112">This path must include the hive.</span></span> |
|<span data-ttu-id="6b2cb-113">ValueName</span><span class="sxs-lookup"><span data-stu-id="6b2cb-113">ValueName</span></span> |<span data-ttu-id="6b2cb-114">レジストリ値の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-114">Indicates the name of the registry value.</span></span> <span data-ttu-id="6b2cb-115">レジストリ キーを追加または削除するには、**ValueType** または **ValueData** を指定せずに、このプロパティを空の文字列で指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-115">To add or remove a registry key, specify this property as an empty string without specifying **ValueType** or **ValueData**.</span></span> <span data-ttu-id="6b2cb-116">レジストリ キーの既定値を変更または削除するには、**ValueType** または **ValueData** を指定し、このプロパティを空の文字列で指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-116">To modify or remove the default value of a registry key, specify this property as an empty string while also specifying **ValueType** or **ValueData**.</span></span> |
|<span data-ttu-id="6b2cb-117">Force</span><span class="sxs-lookup"><span data-stu-id="6b2cb-117">Force</span></span> |<span data-ttu-id="6b2cb-118">指定のレジストリ キーが存在する場合、**Force** はそのキーを新しい値で上書きします。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-118">If the specified registry key is present, **Force** overwrites it with the new value.</span></span> <span data-ttu-id="6b2cb-119">レジストリ キーをサブキーと共に削除する場合は、これが `$true` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-119">If deleting a registry key with subkeys, this needs to be `$true`.</span></span> |
|<span data-ttu-id="6b2cb-120">Hex</span><span class="sxs-lookup"><span data-stu-id="6b2cb-120">Hex</span></span> |<span data-ttu-id="6b2cb-121">16 進形式でデータを表現するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-121">Indicates if data will be expressed in hexadecimal format.</span></span> <span data-ttu-id="6b2cb-122">指定した場合、DWORD/QWORD 値データが 16 進形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-122">If specified, the DWORD/QWORD value data is presented in hexadecimal format.</span></span> <span data-ttu-id="6b2cb-123">その他の種類に対しては無効です。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-123">Not valid for other types.</span></span> <span data-ttu-id="6b2cb-124">既定値は `$false` です。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-124">The default value is `$false`.</span></span> |
|<span data-ttu-id="6b2cb-125">ValueData</span><span class="sxs-lookup"><span data-stu-id="6b2cb-125">ValueData</span></span> |<span data-ttu-id="6b2cb-126">レジストリ値のデータ。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-126">The data for the registry value.</span></span> |
|<span data-ttu-id="6b2cb-127">ValueType</span><span class="sxs-lookup"><span data-stu-id="6b2cb-127">ValueType</span></span> |<span data-ttu-id="6b2cb-128">値の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-128">Indicates the type of the value.</span></span> <span data-ttu-id="6b2cb-129">サポートされている型は次のとおりです。**String** (REG_SZ)、**Binary** (REG-BINARY)、**Dword** (32 ビット REG_DWORD)、**Qword** (64 ビット REG_QWORD)、**MultiString** (REG_MULTI_SZ)、**ExpandString** (REG_EXPAND_SZ)。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-129">The supported types are: **String** (REG_SZ), **Binary** (REG-BINARY), **Dword** (32-bit REG_DWORD), **Qword** (64-bit REG_QWORD), **MultiString** (REG_MULTI_SZ), **ExpandString** (REG_EXPAND_SZ).</span></span> |

## <a name="common-properties"></a><span data-ttu-id="6b2cb-130">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="6b2cb-130">Common properties</span></span>

|<span data-ttu-id="6b2cb-131">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6b2cb-131">Property</span></span> |<span data-ttu-id="6b2cb-132">説明</span><span class="sxs-lookup"><span data-stu-id="6b2cb-132">Description</span></span> |
|---|---|
|<span data-ttu-id="6b2cb-133">DependsOn</span><span class="sxs-lookup"><span data-stu-id="6b2cb-133">DependsOn</span></span> |<span data-ttu-id="6b2cb-134">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-134">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="6b2cb-135">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-135">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="6b2cb-136">Ensure</span><span class="sxs-lookup"><span data-stu-id="6b2cb-136">Ensure</span></span> |<span data-ttu-id="6b2cb-137">キーと値が存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-137">Indicates if the key and value exist.</span></span> <span data-ttu-id="6b2cb-138">それらが確実に実行されるようにするには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-138">To ensure that they do, set this property to **Present**.</span></span> <span data-ttu-id="6b2cb-139">それらが存在しないことを保証するには、このプロパティを **Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-139">To ensure that they do not exist, set the property to **Absent**.</span></span> <span data-ttu-id="6b2cb-140">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-140">The default value is **Present**.</span></span> |
|<span data-ttu-id="6b2cb-141">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="6b2cb-141">PsDscRunAsCredential</span></span> |<span data-ttu-id="6b2cb-142">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-142">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="6b2cb-143">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-143">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="6b2cb-144">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-144">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="6b2cb-145">例</span><span class="sxs-lookup"><span data-stu-id="6b2cb-145">Example</span></span>

<span data-ttu-id="6b2cb-146">次の例では、"ExampleKey" という名前のキーが **HKEY\_LOCAL\_MACHINE** ハイブに存在していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-146">This example ensures that a key named "ExampleKey" is present in the **HKEY\_LOCAL\_MACHINE** hive.</span></span>

```powershell
Configuration RegistryTest
{
    Registry RegistryExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Key         = "HKEY_LOCAL_MACHINE\SOFTWARE\ExampleKey"
        ValueName   = "TestValue"
        ValueData   = "TestData"
    }
}
```

> [!NOTE]
> <span data-ttu-id="6b2cb-147">`HKEY_CURRENT_USER` ハイブのレジストリ設定を変更するには、構成がシステムとしてではなく、ユーザーの資格情報を使用して実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-147">Changing a registry setting in the `HKEY_CURRENT_USER` hive requires that the configuration runs with user credentials, rather than as the system.</span></span> <span data-ttu-id="6b2cb-148">**PsDscRunAsCredential** プロパティを使用すれば、構成に対してユーザー資格情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-148">You can use the **PsDscRunAsCredential** property to specify user credentials for the configuration.</span></span> <span data-ttu-id="6b2cb-149">例については、「[ユーザーの資格情報を指定して DSC を実行する](../../../configurations/runAsUser.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b2cb-149">For an example, see [Running DSC with user credentials](../../../configurations/runAsUser.md).</span></span>