---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC Registry リソース"
ms.openlocfilehash: 649cb60578c053c04a7fcc7446881fb76daee26a
ms.sourcegitcommit: 79e8f03afb8d0b0bb0a167e56464929b27f51990
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2017
---
# <a name="dsc-registry-resource"></a><span data-ttu-id="92a49-103">DSC Registry リソース</span><span class="sxs-lookup"><span data-stu-id="92a49-103">DSC Registry Resource</span></span>

> <span data-ttu-id="92a49-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="92a49-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="92a49-105">Windows PowerShell Desired State Configuration (DSC) の **Registry** リソースは、ターゲット ノードでレジストリ キーと値を管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="92a49-105">The **Registry** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage registry keys and values on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="92a49-106">構文</span><span class="sxs-lookup"><span data-stu-id="92a49-106">Syntax</span></span>

```
Registry [string] #ResourceName
{
    Key = [string]
    ValueName = [string]
    [ Ensure = [string] { Enable | Disable }  ]
    [ Force =  [bool]   ]
    [ Hex = [bool] ]
    [ DependsOn = [string[]] ]
    [ ValueData = [string[]] ]
    [ ValueType = [string] { Binary | Dword | ExpandString | MultiString | Qword | String }  ]
}
```

## <a name="properties"></a><span data-ttu-id="92a49-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="92a49-107">Properties</span></span>
|  <span data-ttu-id="92a49-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="92a49-108">Property</span></span>  |  <span data-ttu-id="92a49-109">説明</span><span class="sxs-lookup"><span data-stu-id="92a49-109">Description</span></span>   | 
|---|---| 
| <span data-ttu-id="92a49-110">キー</span><span class="sxs-lookup"><span data-stu-id="92a49-110">Key</span></span>| <span data-ttu-id="92a49-111">特定の状態を確認するレジストリ キーのパスを示します。</span><span class="sxs-lookup"><span data-stu-id="92a49-111">Indicates the path of the registry key for which you want to ensure a specific state.</span></span> <span data-ttu-id="92a49-112">このパスには、ハイブを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a49-112">This path must include the hive.</span></span>| 
| <span data-ttu-id="92a49-113">ValueName</span><span class="sxs-lookup"><span data-stu-id="92a49-113">ValueName</span></span>| <span data-ttu-id="92a49-114">レジストリ値の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="92a49-114">Indicates the name of the registry value.</span></span> <span data-ttu-id="92a49-115">レジストリ キーを追加または削除するには、ValueType または ValueData を指定せずに、このプロパティを空の文字列で指定します。</span><span class="sxs-lookup"><span data-stu-id="92a49-115">To add or remove a registry key, specify this property as an empty string without specifying ValueType or ValueData.</span></span> <span data-ttu-id="92a49-116">レジストリ キーの既定値を変更または削除するには、ValueType または ValueData を指定し、このプロパティを空の文字列で指定します。</span><span class="sxs-lookup"><span data-stu-id="92a49-116">To modify or remove the default value of a registry key, specify this property as an empty string while also specifying ValueType or ValueData.</span></span>| 
| <span data-ttu-id="92a49-117">Ensure</span><span class="sxs-lookup"><span data-stu-id="92a49-117">Ensure</span></span>| <span data-ttu-id="92a49-118">キーと値が存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="92a49-118">Indicates if the key and value exist.</span></span> <span data-ttu-id="92a49-119">それらが存在することを保証するには、このプロパティを "Present" に設定します。</span><span class="sxs-lookup"><span data-stu-id="92a49-119">To ensure that they do, set this property to "Present".</span></span> <span data-ttu-id="92a49-120">それらが存在しないことを保証するには、このプロパティを "Absent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="92a49-120">To ensure that they do not exist, set the property to "Absent".</span></span> <span data-ttu-id="92a49-121">既定値は "Present" です。</span><span class="sxs-lookup"><span data-stu-id="92a49-121">The default value is "Present".</span></span>| 
| <span data-ttu-id="92a49-122">Force</span><span class="sxs-lookup"><span data-stu-id="92a49-122">Force</span></span>| <span data-ttu-id="92a49-123">指定のレジストリ キーが存在する場合、__Force__ はそのキーを新しい値で上書きします。</span><span class="sxs-lookup"><span data-stu-id="92a49-123">If the specified registry key is present, __Force__ overwrites it with the new value.</span></span> <span data-ttu-id="92a49-124">レジストリ キーをサブキーと共に削除する場合は、これが __$true__ である必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a49-124">If deleting a registry key with subkeys, this needs to be __$true__</span></span>| 
| <span data-ttu-id="92a49-125">Hex</span><span class="sxs-lookup"><span data-stu-id="92a49-125">Hex</span></span>| <span data-ttu-id="92a49-126">16 進形式でデータを表現するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="92a49-126">Indicates if data will be expressed in hexadecimal format.</span></span> <span data-ttu-id="92a49-127">指定した場合、DWORD/QWORD 値データが 16 進形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="92a49-127">If specified, the DWORD/QWORD value data is presented in hexadecimal format.</span></span> <span data-ttu-id="92a49-128">その他の種類に対しては無効です。</span><span class="sxs-lookup"><span data-stu-id="92a49-128">Not valid for other types.</span></span> <span data-ttu-id="92a49-129">既定値は __$false__ です。</span><span class="sxs-lookup"><span data-stu-id="92a49-129">The default value is __$false__.</span></span>| 
| <span data-ttu-id="92a49-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="92a49-130">DependsOn</span></span>| <span data-ttu-id="92a49-131">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="92a49-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="92a49-132">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="92a49-132">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>| 
| <span data-ttu-id="92a49-133">ValueData</span><span class="sxs-lookup"><span data-stu-id="92a49-133">ValueData</span></span>| <span data-ttu-id="92a49-134">レジストリ値のデータ。</span><span class="sxs-lookup"><span data-stu-id="92a49-134">The data for the registry value.</span></span>| 
| <span data-ttu-id="92a49-135">ValueType</span><span class="sxs-lookup"><span data-stu-id="92a49-135">ValueType</span></span>| <span data-ttu-id="92a49-136">値の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="92a49-136">Indicates the type of the value.</span></span> <span data-ttu-id="92a49-137">サポートされている型は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="92a49-137">The supported types are:</span></span> 
<ul><li><span data-ttu-id="92a49-138">文字列 (REG_SZ)</span><span class="sxs-lookup"><span data-stu-id="92a49-138">String (REG_SZ)</span></span></li>


<li><span data-ttu-id="92a49-139">バイナリ (REG-BINARY)</span><span class="sxs-lookup"><span data-stu-id="92a49-139">Binary (REG-BINARY)</span></span></li>


<li><span data-ttu-id="92a49-140">Dword 32 ビット (REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="92a49-140">Dword 32-bit (REG_DWORD)</span></span></li>


<li><span data-ttu-id="92a49-141">Qword 64 ビット (REG_QWORD)</span><span class="sxs-lookup"><span data-stu-id="92a49-141">Qword 64-bit (REG_QWORD)</span></span></li>


<li><span data-ttu-id="92a49-142">複数行文字列 (REG_MULTI_SZ)</span><span class="sxs-lookup"><span data-stu-id="92a49-142">Multi-string (REG_MULTI_SZ)</span></span></li>


<li><span data-ttu-id="92a49-143">展開可能な文字列 (REG_EXPAND_SZ)</span><span class="sxs-lookup"><span data-stu-id="92a49-143">Expandable string (REG_EXPAND_SZ)</span></span></li></ul>

## <a name="example"></a><span data-ttu-id="92a49-144">例</span><span class="sxs-lookup"><span data-stu-id="92a49-144">Example</span></span>
<span data-ttu-id="92a49-145">次の例では、"ExampleKey" という名前のキーが **HKEY\_LOCAL\_MACHINE** ハイブに存在していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="92a49-145">This example ensures that a key named "ExampleKey" is present in the **HKEY\_LOCAL\_MACHINE** hive.</span></span>
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

><span data-ttu-id="92a49-146">**注:** **HKEY\_CURRENT\_USER** レジストリ設定を変更するには、構成がシステムとしてではなくユーザーの資格情報で実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a49-146">**Note:** Changing a registry setting in the **HKEY\_CURRENT\_USER** hive requires that the configuration runs with user credentials, rather than as the system.</span></span>
><span data-ttu-id="92a49-147">**PsDscRunAsCredential** プロパティを使用すれば、構成に対してユーザー資格情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="92a49-147">You can use the **PsDscRunAsCredential** property to specify user credentials for the configuration.</span></span> <span data-ttu-id="92a49-148">例については、「[ユーザーの資格情報を指定して DSC を実行する](runAsUser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92a49-148">For an example, see [Running DSC with user credentials](runAsUser.md)</span></span>



