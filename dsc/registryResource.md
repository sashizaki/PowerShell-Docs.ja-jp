---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Registry リソース
ms.openlocfilehash: 8d74473d167b70182c3a16c1d39d2a9e797afb1b
ms.sourcegitcommit: c3f1a83b59484651119630f3089aa51b6e7d4c3c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2018
ms.locfileid: "39267723"
---
# <a name="dsc-registry-resource"></a><span data-ttu-id="4dd41-103">DSC Registry リソース</span><span class="sxs-lookup"><span data-stu-id="4dd41-103">DSC Registry Resource</span></span>

<span data-ttu-id="4dd41-104">_適用対象: Windows PowerShell 4.0、Windows PowerShell 5.0_</span><span class="sxs-lookup"><span data-stu-id="4dd41-104">_Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0_</span></span>

<span data-ttu-id="4dd41-105">Windows PowerShell Desired State Configuration (DSC) の **Registry** リソースは、ターゲット ノードでレジストリ キーと値を管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="4dd41-105">The **Registry** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage registry keys and values on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="4dd41-106">構文</span><span class="sxs-lookup"><span data-stu-id="4dd41-106">Syntax</span></span>

```
Registry [string] #ResourceName
{
    Key = [string]
    ValueName = [string]
    [ Ensure = [string] { Present | Absent }  ]
    [ Force =  [bool]   ]
    [ Hex = [bool] ]
    [ DependsOn = [string[]] ]
    [ ValueData = [string[]] ]
    [ ValueType = [string] { Binary | Dword | ExpandString | MultiString | Qword | String }  ]
}
```

## <a name="properties"></a><span data-ttu-id="4dd41-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4dd41-107">Properties</span></span>

| <span data-ttu-id="4dd41-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4dd41-108">Property</span></span> | <span data-ttu-id="4dd41-109">説明</span><span class="sxs-lookup"><span data-stu-id="4dd41-109">Description</span></span> |
| --- | --- |
| <span data-ttu-id="4dd41-110">キー</span><span class="sxs-lookup"><span data-stu-id="4dd41-110">Key</span></span>| <span data-ttu-id="4dd41-111">特定の状態を確認するレジストリ キーのパスを示します。</span><span class="sxs-lookup"><span data-stu-id="4dd41-111">Indicates the path of the registry key for which you want to ensure a specific state.</span></span> <span data-ttu-id="4dd41-112">このパスには、ハイブを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dd41-112">This path must include the hive.</span></span>|
| <span data-ttu-id="4dd41-113">ValueName</span><span class="sxs-lookup"><span data-stu-id="4dd41-113">ValueName</span></span>| <span data-ttu-id="4dd41-114">レジストリ値の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="4dd41-114">Indicates the name of the registry value.</span></span> <span data-ttu-id="4dd41-115">レジストリ キーを追加または削除するには、ValueType または ValueData を指定せずに、このプロパティを空の文字列で指定します。</span><span class="sxs-lookup"><span data-stu-id="4dd41-115">To add or remove a registry key, specify this property as an empty string without specifying ValueType or ValueData.</span></span> <span data-ttu-id="4dd41-116">レジストリ キーの既定値を変更または削除するには、ValueType または ValueData を指定し、このプロパティを空の文字列で指定します。</span><span class="sxs-lookup"><span data-stu-id="4dd41-116">To modify or remove the default value of a registry key, specify this property as an empty string while also specifying ValueType or ValueData.</span></span>|
| <span data-ttu-id="4dd41-117">Ensure</span><span class="sxs-lookup"><span data-stu-id="4dd41-117">Ensure</span></span>| <span data-ttu-id="4dd41-118">キーと値が存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4dd41-118">Indicates if the key and value exist.</span></span> <span data-ttu-id="4dd41-119">それらが存在することを保証するには、このプロパティを "Present" に設定します。</span><span class="sxs-lookup"><span data-stu-id="4dd41-119">To ensure that they do, set this property to "Present".</span></span> <span data-ttu-id="4dd41-120">それらが存在しないことを保証するには、このプロパティを "Absent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="4dd41-120">To ensure that they do not exist, set the property to "Absent".</span></span> <span data-ttu-id="4dd41-121">既定値は "Present" です。</span><span class="sxs-lookup"><span data-stu-id="4dd41-121">The default value is "Present".</span></span>|
| <span data-ttu-id="4dd41-122">Force</span><span class="sxs-lookup"><span data-stu-id="4dd41-122">Force</span></span>| <span data-ttu-id="4dd41-123">指定のレジストリ キーが存在する場合、**Force** はそのキーを新しい値で上書きします。</span><span class="sxs-lookup"><span data-stu-id="4dd41-123">If the specified registry key is present, **Force** overwrites it with the new value.</span></span> <span data-ttu-id="4dd41-124">レジストリ キーをサブキーと共に削除する場合は、これが **$true** である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dd41-124">If deleting a registry key with subkeys, this needs to be **$true**</span></span> |
| <span data-ttu-id="4dd41-125">Hex</span><span class="sxs-lookup"><span data-stu-id="4dd41-125">Hex</span></span>| <span data-ttu-id="4dd41-126">16 進形式でデータを表現するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4dd41-126">Indicates if data will be expressed in hexadecimal format.</span></span> <span data-ttu-id="4dd41-127">指定した場合、DWORD/QWORD 値データが 16 進形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dd41-127">If specified, the DWORD/QWORD value data is presented in hexadecimal format.</span></span> <span data-ttu-id="4dd41-128">その他の種類に対しては無効です。</span><span class="sxs-lookup"><span data-stu-id="4dd41-128">Not valid for other types.</span></span> <span data-ttu-id="4dd41-129">既定値は **$false** です。</span><span class="sxs-lookup"><span data-stu-id="4dd41-129">The default value is **$false**.</span></span>|
| <span data-ttu-id="4dd41-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="4dd41-130">DependsOn</span></span>| <span data-ttu-id="4dd41-131">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="4dd41-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="4dd41-132">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="4dd41-132">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="4dd41-133">ValueData</span><span class="sxs-lookup"><span data-stu-id="4dd41-133">ValueData</span></span>| <span data-ttu-id="4dd41-134">レジストリ値のデータ。</span><span class="sxs-lookup"><span data-stu-id="4dd41-134">The data for the registry value.</span></span>|
| <span data-ttu-id="4dd41-135">ValueType</span><span class="sxs-lookup"><span data-stu-id="4dd41-135">ValueType</span></span>| <span data-ttu-id="4dd41-136">値の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="4dd41-136">Indicates the type of the value.</span></span> <span data-ttu-id="4dd41-137">サポートされる型は次のとおりです。文字列 (REG_SZ)、バイナリ (REG-BINARY)、Dword 32 ビット (REG_DWORD)、Qword 64 ビット (REG_QWORD)、複数行文字列 (REG_MULTI_SZ)、展開可能な文字列値 (REG_EXPAND_SZ)</span><span class="sxs-lookup"><span data-stu-id="4dd41-137">The supported types are: String (REG_SZ), Binary (REG-BINARY), Dword 32-bit (REG_DWORD), Qword 64-bit (REG_QWORD), Multi-string (REG_MULTI_SZ), Expandable string (REG_EXPAND_SZ)</span></span> |

## <a name="example"></a><span data-ttu-id="4dd41-138">例</span><span class="sxs-lookup"><span data-stu-id="4dd41-138">Example</span></span>

<span data-ttu-id="4dd41-139">次の例では、"ExampleKey" という名前のキーが **HKEY\_LOCAL\_MACHINE** ハイブに存在していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4dd41-139">This example ensures that a key named "ExampleKey" is present in the **HKEY\_LOCAL\_MACHINE** hive.</span></span>

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
> <span data-ttu-id="4dd41-140">`HKEY\CURRENT\USER` ハイブのレジストリ設定を変更するには、構成がシステムとしてではなく、ユーザーの資格情報を使用して実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dd41-140">Changing a registry setting in the `HKEY\CURRENT\USER` hive requires that the configuration runs with user credentials, rather than as the system.</span></span> <span data-ttu-id="4dd41-141">**PsDscRunAsCredential** プロパティを使用すれば、構成に対してユーザー資格情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4dd41-141">You can use the **PsDscRunAsCredential** property to specify user credentials for the configuration.</span></span> <span data-ttu-id="4dd41-142">例については、「[ユーザーの資格情報を指定して DSC を実行する](runAsUser.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4dd41-142">For an example, see [Running DSC with user credentials](runAsUser.md).</span></span>