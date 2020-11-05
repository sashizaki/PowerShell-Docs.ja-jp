---
ms.date: 08/11/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC リソース メソッドの直接呼び出し
description: Invoke-DscResource コマンドレットは、DSC リソースの関数またはメソッドを呼び出すために使用できます。 これは、DSC リソースを使用するサード パーティが使用したり、リソースの開発中に役立つツールとして利用したりできます。
ms.openlocfilehash: 5ccf0f589b60cef4ec197d1e0a583af9ed60d5e7
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650990"
---
# <a name="calling-dsc-resource-methods-directly"></a><span data-ttu-id="0b703-105">DSC リソース メソッドの直接呼び出し</span><span class="sxs-lookup"><span data-stu-id="0b703-105">Calling DSC resource methods directly</span></span>

> <span data-ttu-id="0b703-106">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="0b703-106">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="0b703-107">[Invoke DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) コマンドレットを使用すると、DSC リソースの関数またはメソッド (MOF ベースのリソースの `Get-TargetResource` 関数、`Set-TargetResource` 関数、`Test-TargetResource` 関数、またはクラスベースのリソースの **Get** メソッド、 **Set** メソッド、 **Test** メソッド) を直接呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="0b703-107">You can use the [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) cmdlet to directly call the functions or methods of a DSC resource (The `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource` functions of a MOF-based resource, or the **Get** , **Set** , and **Test** methods of a class-based resource).</span></span> <span data-ttu-id="0b703-108">これは、DSC リソースを使用するサード パーティが使用したり、リソースの開発中に役立つツールとして利用したりできます。</span><span class="sxs-lookup"><span data-stu-id="0b703-108">This can be used by third-parties that want to use DSC resources, or as a helpful tool while developing resources.</span></span>

> [!NOTE]
> <span data-ttu-id="0b703-109">PowerShell 7.0 以降では、`Invoke-DscResource` は WMI DSC リソースの呼び出しをサポートしなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0b703-109">In PowerShell 7.0+, `Invoke-DscResource` no longer supports invoking WMI DSC resources.</span></span> <span data-ttu-id="0b703-110">これには、 **PSDesiredStateConfiguration** の **ファイル** リソースと **ログ** リソースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0b703-110">This includes the **File** and **Log** resources in **PSDesiredStateConfiguration**.</span></span>

<span data-ttu-id="0b703-111">通常このコマンドレットは、メタ構成プロパティ `refreshMode = 'Disabled'` と組み合わせて使用されますが、どの **refreshMode** が設定されているかに関係なく使用できます。</span><span class="sxs-lookup"><span data-stu-id="0b703-111">This cmdlet is typically used in combination with a metaconfiguration property `refreshMode = 'Disabled'`, but it can be used no matter what **refreshMode** is set to.</span></span>

<span data-ttu-id="0b703-112">`Invoke-DscResource` コマンドレットを呼び出すときに、 **Method** パラメーターを使用して、呼び出すメソッドまたは関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="0b703-112">When calling the `Invoke-DscResource` cmdlet, you specify which method or function to call by using the **Method** parameter.</span></span> <span data-ttu-id="0b703-113">リソースのプロパティを指定するには、ハッシュ テーブルを、 **Property** パラメーターの値として渡します。</span><span class="sxs-lookup"><span data-stu-id="0b703-113">You specify the properties of the resource by passing a hashtable as the value of the **Property** parameter.</span></span>

<span data-ttu-id="0b703-114">リソースのメソッドを直接呼び出す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0b703-114">The following are examples of directly calling resource methods:</span></span>

## <a name="ensure-a-file-is-present"></a><span data-ttu-id="0b703-115">ファイルが存在することを確認します</span><span class="sxs-lookup"><span data-stu-id="0b703-115">Ensure a file is present</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Set -Property @{
              DestinationPath = "$env:SystemDrive\\DirectAccess.txt";
              Contents = 'This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="test-that-a-file-is-present"></a><span data-ttu-id="0b703-116">ファイルが存在することをテストします</span><span class="sxs-lookup"><span data-stu-id="0b703-116">Test that a file is present</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Test -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="get-the-contents-of-file"></a><span data-ttu-id="0b703-117">ファイルの内容を取得します</span><span class="sxs-lookup"><span data-stu-id="0b703-117">Get the contents of file</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Get -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result.ItemValue | fl
```

> [!NOTE]
> <span data-ttu-id="0b703-118">複合リソースのメソッドを直接呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="0b703-118">Directly calling composite resource methods is not supported.</span></span> <span data-ttu-id="0b703-119">代わりに、複合リソースの基になるリソースのメソッドを呼び出してください。</span><span class="sxs-lookup"><span data-stu-id="0b703-119">Instead, call the methods of the underlying resources that make up the composite resource.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b703-120">参照</span><span class="sxs-lookup"><span data-stu-id="0b703-120">See Also</span></span>

- [<span data-ttu-id="0b703-121">MOF を使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="0b703-121">Writing a custom DSC resource with MOF</span></span>](../resources/authoringResourceMOF.md)
- [<span data-ttu-id="0b703-122">PowerShell クラスを使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="0b703-122">Writing a custom DSC resource with PowerShell classes</span></span>](../resources/authoringResourceClass.md)
- [<span data-ttu-id="0b703-123">DSC リソースのデバッグ</span><span class="sxs-lookup"><span data-stu-id="0b703-123">Debugging DSC resources</span></span>](../troubleshooting/debugResource.md)
